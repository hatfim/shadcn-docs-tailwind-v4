<template>
  <UseTemplate>
    <ShCard
      class="relative h-full overflow-hidden transition-all"
      :class="[
        to && 'hover:bg-muted',
        inStack && 'mb-0 rounded-none border-none shadow-none',
      ]"
    >
      <NuxtImg
        v-if="img"
        :src="img"
        class="w-full"
      />
      <ShCardHeader v-if="icon || title || $slots.title || description || $slots.description" :class="{ 'flex-row items-center gap-5': horizontal }">
        <SmartIcon v-if="icon" :name="icon" :size="iconSize" :class="{ 'mb-2': !horizontal }" />
        <div class="flex flex-col gap-1.5">
          <ShCardTitle v-if="title || $slots.title">
            <ContentSlot :use="$slots.title" unwrap="p" />
            {{ title }}
          </ShCardTitle>
          <ShCardDescription v-if="description || $slots.description">
            <ContentSlot :use="$slots.description" unwrap="p" />
            {{ description }}
          </ShCardDescription>
        </div>
      </ShCardHeader>
      <ShCardContent v-if="content || $slots.content || $slots.default">
        <ContentSlot :use="$slots.content" unwrap="p" />
        <ContentSlot unwrap="p" />
      </ShCardContent>
      <ShCardFooter v-if="footer || $slots.footer">
        <ContentSlot :use="$slots.footer" unwrap="p" />
        {{ footer }}
      </ShCardFooter>
      <SmartIcon v-if="to && showLinkIcon" name="lucide:arrow-up-right" class="absolute right-4 top-4" />
    </ShCard>
  </UseTemplate>

  <div class="group-has-[div]:mt-0 [&:not(:first-child)]:mt-5">
    <NuxtLink v-if="to" :to :target>
      <CardInner />
    </NuxtLink>
    <CardInner v-else />
  </div>
</template>

<script setup lang="ts">
const {
  showLinkIcon = true,
  horizontal = false,
  iconSize = 24,
} = defineProps<{
  title?: string;
  description?: string;
  footer?: string;
  content?: string;
  to?: string;
  target?: Target;
  icon?: string;
  iconSize?: number;
  inStack?: boolean;
  img?: string;
  showLinkIcon?: boolean;
  horizontal?: boolean;
}>();

defineSlots();

const [UseTemplate, CardInner] = createReusableTemplate();
</script>

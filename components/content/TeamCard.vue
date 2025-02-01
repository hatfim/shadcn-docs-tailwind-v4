<template>
  <ShCard>
    <ShCardHeader>
      <div class="flex flex-col gap-3" :class="{ 'text-center': center }">
        <ShAvatar :class="{ 'mx-auto': center }">
          <ShAvatarImage :src="avatar" :alt="name" />
        </ShAvatar>
        <div>
          <div class="text-lg font-bold">
            {{ name }}
          </div>
          <div class="text-sm text-muted-foreground">
            {{ title }}
          </div>
        </div>
        <div class="flex gap-3 text-subtle-foreground" :class="{ 'mx-auto': center }">
          <NuxtLink v-for="link in links" :key="link.to" :to="link.to" :target="link.target">
            <SmartIcon :name="link.icon" />
          </NuxtLink>
        </div>
      </div>
    </ShCardHeader>
  </ShCard>
</template>

<script setup lang="ts">
const { center = true } = defineProps<{
  avatar: string;
  name: string;
  title?: string;
  links?: ({
    icon: string;
    to: string;
    target?: Target;
  })[];
  center?: boolean;
}>();
</script>

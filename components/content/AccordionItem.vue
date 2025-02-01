<template>
  <ShAccordionItem :value="value ?? autoValue">
    <ShAccordionTrigger>
      <ContentSlot :use="$slots.title" unwrap="p" />
      {{ title }}
    </ShAccordionTrigger>
    <ShAccordionContent>
      <ContentSlot :use="$slots.content" unwrap="p" />
      {{ content }}
    </ShAccordionContent>
  </ShAccordionItem>
</template>

<script setup lang="ts">
import { useId } from 'radix-vue';

defineProps<{
  value?: string;
  title?: string;
  content?: string;
}>();

defineSlots();

const autoValue = useId();
</script>

<template>
  <DialogDescription
    v-bind="forwardedProps"
    :class="className('text-sm text-muted-foreground', props.class)"
  >
    <slot />
  </DialogDescription>
</template>

<script setup lang="ts">
import type { DialogDescriptionProps } from 'radix-vue';
import type { HTMLAttributes } from 'vue';
import { className } from '@DOCS/lib/utils';
import { DialogDescription, useForwardProps } from 'radix-vue';
import { computed } from 'vue';

const props = defineProps<DialogDescriptionProps & { class?: HTMLAttributes['class'] }>();

const delegatedProps = computed(() => {
  const { class: _, ...delegated } = props;

  return delegated;
});

const forwardedProps = useForwardProps(delegatedProps);
</script>

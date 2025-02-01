<template>
  <h3
    :class="
      className('text-2xl font-semibold leading-none tracking-tight', props.class)
    "
  >
    <slot />
  </h3>
</template>

<script setup lang="ts">
import type { HTMLAttributes } from 'vue';
import { className } from '@DOCS/lib/utils';

const props = defineProps<{
  class?: HTMLAttributes['class'];
}>();
</script>

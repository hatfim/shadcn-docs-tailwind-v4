<template>
  <p :class="className('text-sm text-muted-foreground', props.class)">
    <slot />
  </p>
</template>

<script setup lang="ts">
import type { HTMLAttributes } from 'vue';
import { className } from '@DOCS/lib/utils';

const props = defineProps<{
  class?: HTMLAttributes['class'];
}>();
</script>

<template>
  <div :class="className('text-sm [&_p]:leading-relaxed', props.class)">
    <slot />
  </div>
</template>

<script setup lang="ts">
import type { HTMLAttributes } from 'vue';
import { className } from '@DOCS/lib/utils';

const props = defineProps<{
  class?: HTMLAttributes['class'];
}>();
</script>

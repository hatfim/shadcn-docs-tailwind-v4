<template>
  <h5 :class="className('mb-1 font-medium leading-none tracking-tight', props.class)">
    <slot />
  </h5>
</template>

<script setup lang="ts">
import type { HTMLAttributes } from 'vue';
import { className } from '@/lib/utils';

const props = defineProps<{
  class?: HTMLAttributes['class'];
}>();
</script>

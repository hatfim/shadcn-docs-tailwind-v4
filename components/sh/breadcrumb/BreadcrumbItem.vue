<template>
  <li
    :class="className('inline-flex items-center gap-1.5', props.class)"
  >
    <slot />
  </li>
</template>

<script lang="ts" setup>
import type { HTMLAttributes } from 'vue';
import { className } from '@DOCS/lib/utils';

const props = defineProps<{
  class?: HTMLAttributes['class'];
}>();
</script>

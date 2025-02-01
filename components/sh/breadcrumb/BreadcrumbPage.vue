<template>
  <span
    role="link"
    aria-disabled="true"
    aria-current="page"
    :class="className('font-normal text-foreground', props.class)"
  >
    <slot />
  </span>
</template>

<script lang="ts" setup>
import type { HTMLAttributes } from 'vue';
import { className } from '@DOCS/lib/utils';

const props = defineProps<{
  class?: HTMLAttributes['class'];
}>();
</script>

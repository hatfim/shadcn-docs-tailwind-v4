<template>
  <div :class="className(badgeVariants({ variant }), props.class)">
    <slot />
  </div>
</template>

<script setup lang="ts">
import type { HTMLAttributes } from 'vue';
import type { BadgeVariants } from '.';
import { className } from '@DOCS/lib/utils';
import { badgeVariants } from '.';

const props = defineProps<{
  variant?: BadgeVariants['variant'];
  class?: HTMLAttributes['class'];
}>();
</script>

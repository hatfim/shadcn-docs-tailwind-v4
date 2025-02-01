<template>
  <div :class="className(alertVariants({ variant }), props.class)" role="alert">
    <slot />
  </div>
</template>

<script setup lang="ts">
import type { HTMLAttributes } from 'vue';
import type { AlertVariants } from '.';
import { className } from '@/lib/utils';
import { alertVariants } from '.';

const props = defineProps<{
  class?: HTMLAttributes['class'];
  variant?: AlertVariants['variant'];
}>();
</script>

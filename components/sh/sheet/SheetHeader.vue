<template>
  <div
    :class="
      className('flex flex-col gap-y-2 text-center sm:text-left', props.class)
    "
  >
    <slot />
  </div>
</template>

<script setup lang="ts">
import type { HTMLAttributes } from 'vue';
import { className } from '@DOCS/lib/utils';

const props = defineProps<{ class?: HTMLAttributes['class'] }>();
</script>

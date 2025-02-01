<template>
  <div
    :class="
      className(
        'flex flex-col-reverse sm:flex-row sm:justify-end sm:gap-x-2',
        props.class,
      )
    "
  >
    <slot />
  </div>
</template>

<script setup lang="ts">
import type { HTMLAttributes } from 'vue';
import { className } from '@/lib/utils';

const props = defineProps<{ class?: HTMLAttributes['class'] }>();
</script>

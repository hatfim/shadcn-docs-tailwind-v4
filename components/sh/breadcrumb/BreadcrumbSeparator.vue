<template>
  <li
    role="presentation"
    aria-hidden="true"
    :class="className('[&>svg]:size-3.5', props.class)"
  >
    <slot>
      <Icon name="lucide:chevron-right" class="block size-3.5" />
    </slot>
  </li>
</template>

<script lang="ts" setup>
import type { HTMLAttributes } from 'vue';
import { className } from '@/lib/utils';

const props = defineProps<{
  class?: HTMLAttributes['class'];
}>();
</script>

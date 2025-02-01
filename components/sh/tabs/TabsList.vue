<template>
  <TabsList
    v-bind="delegatedProps"
    :class="className(
      'inline-flex h-10 items-center justify-center rounded-md bg-muted p-1 text-muted-foreground',
      props.class,
    )"
  >
    <slot />
  </TabsList>
</template>

<script setup lang="ts">
import type { TabsListProps } from 'radix-vue';
import type { HTMLAttributes } from 'vue';
import { className } from '@DOCS/lib/utils';
import { TabsList } from 'radix-vue';
import { computed } from 'vue';

const props = defineProps<TabsListProps & { class?: HTMLAttributes['class'] }>();

const delegatedProps = computed(() => {
  const { class: _, ...delegated } = props;

  return delegated;
});
</script>

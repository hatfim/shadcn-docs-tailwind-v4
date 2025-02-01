<template>
  <ShPopover>
    <ShPopoverTrigger as-child>
      <ShButton variant="ghost" size="icon">
        <Icon name="lucide:paintbrush" size="16" />
      </ShButton>
    </ShPopoverTrigger>
    <ShPopoverContent
      class="w-[23rem]"
      :align="breakpoints.isGreaterOrEqual('md') ? 'end' : 'center'"
    >
      <ThemeCustomizer />
    </ShPopoverContent>
  </ShPopover>
</template>

<script setup lang="ts">
import { breakpointsTailwind, useBreakpoints } from '@vueuse/core';

const breakpoints = useBreakpoints(breakpointsTailwind);
</script>

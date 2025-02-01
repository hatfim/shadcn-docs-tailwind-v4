<template>
  <ShSheet v-model:open="open">
    <ShSheetTrigger as-child>
      <ShButton
        variant="ghost"
        size="icon"
        class="md:hidden"
      >
        <Icon name="lucide:menu" size="18" />
      </ShButton>
    </ShSheetTrigger>
    <ShSheetContent side="left" class="pr-0">
      <LayoutHeaderLogo />
      <LayoutAside is-mobile />
      <ShDialogTitle class="sr-only" />
      <ShDialogDescription class="sr-only" />
    </ShSheetContent>
  </ShSheet>
</template>

<script setup lang="ts">
const open = ref(false);

// Close sheet on navigation
watch(() => useRoute().path, () => {
  open.value = false;
});
</script>

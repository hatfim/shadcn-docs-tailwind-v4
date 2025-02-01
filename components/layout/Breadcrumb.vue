<template>
  <ShBreadcrumb>
    <ShBreadcrumbList>
      <template v-for="(breadcrumb, index) in breadcrumbs" :key="breadcrumb.title">
        <ShBreadcrumbItem>
          <NuxtLink
            :href="index === 0 ? undefined : breadcrumb.href"
            class="transition-colors hover:text-foreground"
            :class="{ 'text-foreground': index === breadcrumbs.length - 1 }"
          >
            {{ breadcrumb.title }}
          </NuxtLink>
        </ShBreadcrumbItem>
        <ShBreadcrumbSeparator v-if="index !== breadcrumbs.length - 1" />
      </template>
    </ShBreadcrumbList>
  </ShBreadcrumb>
</template>

<script setup lang="ts">
const route = useRoute();

const breadcrumbs = computed(() => useBreadcrumb(route.path));
</script>

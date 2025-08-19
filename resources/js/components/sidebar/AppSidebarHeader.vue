<script setup lang="ts">
import Breadcrumbs from '@/components/app/Breadcrumbs.vue';
import { SidebarTrigger } from '@/components/shadcn/sidebar';
import type { BreadcrumbItemType } from '@/types';
// import ThemeToggle from './ThemeToggle.vue';
import ThemeToggle from '../theme/ThemeToggle.vue';

withDefaults(
    defineProps<{
        breadcrumbs?: BreadcrumbItemType[];
    }>(),
    {
        breadcrumbs: () => [],
    },
);
</script>

<template>
  <header
    class="flex h-16 shrink-0 items-center border-b border-sidebar-border/70 px-6 transition-[width,height] ease-linear md:px-4"
  >
    <div class="flex items-center w-full justify-between">
      <!-- Left Section -->
      <div class="flex items-center gap-3">
        <SidebarTrigger class="-ml-1" />

        <template v-if="breadcrumbs && breadcrumbs.length > 0">
          <Breadcrumbs :breadcrumbs="breadcrumbs" />
        </template>
      </div>

      <!-- Right Section -->
      <div class="flex items-center gap-3">
        <ThemeToggle />
      </div>
    </div>
  </header>
</template>


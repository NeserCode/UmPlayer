<script lang="ts" setup></script>

<template>
  <aside class="app-sidebar">
    <span class="te"> Side </span>
  </aside>
</template>

<style lang="postcss" scoped>
.app-sidebar {
  @apply w-fit min-w-36 max-w-xs h-full
  flex flex-col justify-between items-center py-6
  border-r border-gray-200 dark:border-gray-600
  bg-gray-50 dark:bg-gray-800
  transition-all ease-in-out duration-200;
}
</style>

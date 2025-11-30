<script lang="ts" setup>
import Titlebar from "./components/frameworks/Titlebar.vue";
import Sidebar from "./components/frameworks/Sidebar.vue";

import { Toaster } from "vue-sonner";
import { computed } from "vue";

import { useDark } from "./composables/useDark";

const { isDark } = useDark();
const computedColorSchemeClass = computed(() =>
  isDark.value ? "dark" : "light"
);
</script>

<template>
  <div id="app-main">
    <Titlebar />
    <Toaster :theme="computedColorSchemeClass" richColors />

    <main class="main-container">
      <Sidebar />
      <router-view></router-view>
    </main>
  </div>
</template>

<style lang="postcss" scoped>
#app-main {
  @apply flex flex-col justify-start items-center h-screen
	bg-white dark:bg-slate-800
	transition-colors ease-in-out duration-200;
}

.main-container {
  @apply flex flex-row justify-start items-stretch w-full h-full min-w-full
  overflow-x-hidden overflow-y-auto;
  max-height: clac(100vh - 2rem - 1px);
}
</style>

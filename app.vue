<script setup lang="ts">
import { useDark, useToggle } from '@vueuse/core';
import IconLightMode from "~icons/feather/sun"
import IconDarkMode from "~icons/feather/moon"
const route = useRoute()
const isDark = useDark()
const toggleDark = useToggle(isDark)

const navBlobClass = computed(() => {
  switch (route.name) {
    case "index":
      return "bg-yellow-200 dark:bg-yellow-500 left-2"
    case "about":
      return "bg-purple-200 dark:bg-purple-500  left-18  md:left-22"
    case "project":
      return "bg-blue-200 dark:bg-blue-500  left-34  md:left-42"
    case "blog":
    case "blog-slug":
      return "bg-red-300 dark:bg-red-500  left-50  md:left-62"
  }
})
</script>
<template>
  <div
    class="-z-10 w-full min-h-screen flex justify-center bg-white dark:bg-dark-900 text-dark-200 dark:text-light-900 transition duration-300">
    <div class="max-w-screen-lg w-full relative p-4 sm:p-6 md:p-8 flex flex-col items-center justify-between">
      <div class="z-10 w-full flex justify-end items-center mb-6 md:mb-12">
        <nav class="relative flex space-x-4 md:space-x-6 items-center text-base md:text-lg font-space">
          <NuxtLink to="/">Home</NuxtLink>
          <NuxtLink to="/blog">Blog</NuxtLink>
          <NuxtLink to="/project">Project</NuxtLink>
          <NuxtLink to="/about">About</NuxtLink>

          <Blob :class="navBlobClass" class="top-0 !ml-0 !w-8 !h-8 !blur-md !animate-none"></Blob>
        </nav>
        <button class="mt-2 ml-4 text-lg md:text-2xl" aria-label="Toggle Dark mode" @click="toggleDark()">
          <transition name="fade" mode="out-in">
            <IconLightMode v-if="isDark"></IconLightMode>
            <IconDarkMode v-else></IconDarkMode>
          </transition>
        </button>
      </div>


    </div>
  </div>
</template>
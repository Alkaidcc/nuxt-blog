<script setup lang="ts">
import IconArrow from "~icons/feather/arrow-right"
import Avatar from '@/assets/avatar.png'
import IconGithub from "~icons/simple-icons/github"
import IconVue from "~icons/simple-icons/vuedotjs"
import IconNuxt from "~icons/simple-icons/nuxtdotjs"
import IconTypescript from "~icons/simple-icons/typescript"
import IconVite from "~icons/simple-icons/vite"
import IconTailwind from "~icons/simple-icons/tailwindcss"
import IconPython from '~icons/simple-icons/python'
definePageMeta({
  pageTransition: {
    name: "fade",
    mode: "out-in",
  },
})
</script>
<template>
  <section class="w-full flex flex-col items-center">
    <div
      class="w-full max-w-screen-md px-6 sm:px-8 md:px-16 py-6 md:py-12 shadow-inset-white dark:shadow-none rounded-4xl flex flex-col items-center">
      <h1 class="font-bold text-5xl md:text-7xl text-center font-space tracking-tight">Alkaidcc</h1>
      <h2 class="mt-4 text-xl md:text-2xl text-center text-gray-500 dark:text-gray-300">
        Self-taught Frontend Developer <br />
      </h2>
      <div class="mt-12 flex flex-col items-center">
        <img :src="Avatar" alt="Alkaidcc" class="rounded-4xl w-full max-w-96" />
        <div class="info mt-12">
          <div>
            <h5>Basic</h5>
            <p>
              I'm 22 years old, I'm a student of Computer Science at the University of ZAFU. I like Open Source and create some useful tools.
              Also, I'm interested in design but still learning.
            </p>
          </div>

          <div class="flex flex-col md:flex-row w-full">
            <div class="md:w-1/2">
              <h5>Language/Framework</h5>
              <p class="framework text-gray-300 flex flex-wrap text-3xl">
                <IconVue />
                <IconNuxt />
                <IconTypescript />
                <IconVite />
                <IconTailwind />
                <IconPython />
              </p>
            </div>
          </div>

          <div>
            <h5>Contact Me</h5>
            <ul>
              <li>alkaidcc@qq.com</li>
              <li class="text-gray-300 gap-4 text-3xl flex mt-4">
                <a href="https://github.com/alkaidcc" target="_blank">
                  <IconGithub />
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>
      <NuxtLink to="/project" class="button-next group mt-12">
        Project
        <IconArrow class="w-6 h-6 duration transition-all ml-2 group-hover:ml-3" />
      </NuxtLink>
    </div>
  </section>
</template>
<style lang="postcss">
.info {
  @apply flex flex-col justify-center;
}

.info h5 {
  @apply text-lg md: text-xl font-bold text-gray-500 dark:text-warm-gray-500 mb-4;
}

.info>div {
  @apply mb-12;
}

.framework>svg {
  @apply mb-2 mr-2;
}
</style>
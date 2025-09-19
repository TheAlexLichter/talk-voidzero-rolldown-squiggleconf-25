<script setup lang="ts">
import { computed } from 'vue'
// @ts-ignore
import { isDark } from '@slidev/client/logic/dark.ts'

defineProps({
  website: {
    type: String,
  },
  hideLogoInCorner: {
    type: Boolean
  }
})

const voidZeroImgSuffix = computed(() => isDark.value ? '-white' : '')
const voidZeroImg = computed(() => `https://voidzero.dev/icon${voidZeroImgSuffix.value}.svg`)
const logoImgPrefix = computed(() => isDark.value ? 'white' : 'black')
const logoImg = computed(() => `https://raw.githubusercontent.com/manniL/lichter.io/main/public/img/logo/glyph-${logoImgPrefix.value}-colored.svg`)
</script>

<template>
  <footer
    class="flex flex-col justify-between w-full mt-auto text-black dark:text-white"
  >
    <div class="flex justify-between w-full dark:text-white">
      <a :href="website || $slidev.configs.website" class="flex gap-2 border-b-0!">
        <img v-show="!hideLogoInCorner && !$slidev.configs.hideLogoInCorner" class="w-4 h-4" :src="voidZeroImg" />
        <img v-show="!hideLogoInCorner && !$slidev.configs.hideLogoInCorner" class="w-4 h-4" :src="logoImg" />
      </a>
      <span>{{ $slidev.nav.currentPage }}</span>
    </div>
  </footer>
  <div class="absolute h-1.5 opacity-90 w-full bg-gradient-to-r from-[#6bb5f0] to-[#bd34fe] bottom-0 left-0">
  </div>
</template>
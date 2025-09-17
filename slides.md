---
theme: ./theme
title: "Rolldown: How Vite Bundles at the Speed of Rust"
website: lichter.io
handle: TheAlexLichter
favicon: https://lichter.io/img/me@2x.jpg
highlighter: shiki
lineNumbers: true
layout: intro
transition: fade
---

---
layout: intro
---

<!--

TODO

* What is a bundler
* What is a builder

* Graphs for Slide 17
* 

TODO: Questions at the end

-->

## What do all these frameworks have in common?


---
layout: intro
preload: false
transition: none
---

<div class="flex justify-center items-center h-full w-full">

<div class="grid grid-cols-4 gap-y-8 gap-x-32 items-center">

  <!-- Row 1 -->
  <logos-analog size="4rem" />
  <logos-angular-icon size="4rem" />
  <logos-react size="4rem" />
  <logos-vue size="4rem" />

  <!-- Row 2 -->
  <logos-svelte-icon size="4rem" />
  <logos-solidjs-icon size="4rem" />
  <logos-ember size="4rem" />
  <logos-remix-icon class="filter filter-invert" size="4rem" />

  <!-- Row 3 -->
  <img src="https://github.com/TanStack/tanstack.com/blob/main/src/images/logo-600w.png?raw=true" class="w-20" />
  <logos-laravel size="4rem" />
  <logos-ruby size="4rem" />
  <logos-marko size="4rem" />

  <!-- Row 4 -->
  <img src="https://vitepress.dev/vitepress-logo-large.svg" alt="VitePress" class="w-16 ml-2" />
  <logos-qwik-icon size="4rem" />
  <logos-redwoodjs size="4rem" />
  <logos-nuxt-icon size="4rem" />

</div>

</div>

---
layout: intro
preload: false
transition: none
---
<h1 class="mt-12 flex justify-center items-center" v-motion :initial="{ scale: 0.1 }" :enter="{ scale: 3, transition: { duration: 500 } }">

<logos-vitejs class="text-10xl"/>

</h1>

---
layout: intro
---

# Rolldown <VoidzeroIconsRolldown size="4rem" class="rounded-full shadow-2xl border-2 border-black/50" />

## How Vite Bundles at the Speed of Rust 

### SquiggleConf 2025

<style>

h2 {
  @apply !mt-16;
}

h3 {
  @apply !mt-32 !text-lg;
}
</style>

---
layout: two-cols
heading: About me
---

<template v-slot:default>
<div class="flex flex-col justify-center items-center h-full">
  <img class="w-75 rounded-full" src="https://lichter.io/img/me@2x.webp" />
  <h2 class="mt-4">Alexander Lichter</h2>
</div>
</template>

<template v-slot:right>
<VClicks class="space-y-2 mt-10 text-xl h-full">

* DevRel at <VoidzeroIconsVoidzeroLogo class="text-white" width="4rem" height="auto" />
* <mdi-account-check class="dark:text-green-100 text-green-700" /> **Web Engineering Consultant**
* <mdi-microphone /> Speaker & Instructor
* <logos-nuxt-icon /> Nuxt.js Team
* <mdi-github /><logos-bluesky class="text-sm mb-1 text-blue-400" /><mdi-youtube class="text-red-500" /><mdi-twitch class="text-purple-700" /> @TheAlexLichter
* <mdi-web /> [https://lichter.io](https://lichter.io)

</VClicks>
</template>

---

# Current Vite "Stack"

<div class="flex flex-col items-center justify-center space-y-8">

  <!-- Vite Logo -->
  <logos-vitejs class="text-9xl mb-4" />

  <!-- Tool Logos and Responsibilities with swirl animation -->
  <div class="grid grid-cols-3 gap-12 mt-6">
    <div
      v-motion
      v-click
      :initial="{ x: -120, y: 0, scale: 0.7, opacity: 0.7 }"
      :enter="{ x: 0, y: 0, scale: 0.9, opacity: 1, transition: { delay: 100, duration: 500 } }"
      class="flex flex-col items-center"
    >
      <logos-esbuild size="2.5rem" />
      <span class="font-semibold mt-2">esbuild</span>
      <span class="text-center text-xs text-gray-400 mt-1">
        Pre-bundling, Transforms,<br>
        and Minification
      </span>
    </div>
    <div
      v-motion
      v-click
      :initial="{ y: 80, scale: 0.7, opacity: 0.7 }"
      :enter="{ y: 0, scale: 0.9, opacity: 1, transition: { delay: 200, duration: 500 } }"
      class="flex flex-col items-center"
    >
      <logos-rollup size="2.5rem" />
      <span class="font-semibold mt-2">Rollup</span>
      <span class="text-center text-xs text-gray-400 mt-1">
        Bundling, Plugins,<br>
        and (limited) Chunk Control
      </span>
    </div>
    <div
      v-motion v-click
      :initial="{ x: 120, y: 0, scale: 0.7, opacity: 0.7 }"
      :enter="{ x: 0, y: 0, scale: 0.9, opacity: 1, transition: { delay: 300, duration: 500 } }"
      class="flex flex-col items-center"
    >
      <logos-swc size="2.5rem" />
      <span class="font-semibold mt-2">SWC</span>
      <span class="text-center text-xs text-gray-400 mt-1">
        Alternative for Transforms<br>
        React Fast Refresh
      </span>
    </div>
  </div>

</div>

---
layout: intro
---

# Why not <span class="underline">unifying</span> <br>the underlying bundler?

---


# Current Vite "Stack"

<div class="flex flex-col items-center justify-center space-y-8">

  <!-- Vite Logo -->
  <logos-vitejs class="text-9xl mb-4" />

  <!-- Tool Logos and Responsibilities with swirl animation -->
  <div class="grid grid-cols-3 gap-12 mt-6">
    <div class="flex flex-col items-center">
      <logos-esbuild size="2.5rem" />
      <span class="font-semibold mt-2">esbuild</span>
      <span class="text-center text-xs text-gray-400 mt-1">
        Pre-bundling, Transforms,<br>
        and Minification
      </span>
    </div>
    <div class="flex flex-col items-center">
      <logos-rollup size="2.5rem" />
      <span class="font-semibold mt-2">Rollup</span>
      <span class="text-center text-xs text-gray-400 mt-1">
        Bundling, Plugins,<br>
        and (limited) Chunk Control
      </span>
    </div>
    <div class="flex flex-col items-center">
      <logos-swc size="2.5rem" />
      <span class="font-semibold mt-2">SWC</span>
      <span class="text-center text-xs text-gray-400 mt-1">
        Alternative for Transforms<br>
        React Fast Refresh
      </span>
    </div>
  </div>

</div>

---

# Rolldown-Vite

<div class="flex flex-col items-center justify-center space-y-8">

  <!-- Vite Logo -->
  <logos-vitejs class="text-9xl mb-4"
    v-motion
    :initial="{ scale: 1 }"
    :enter="{ scale: 1.5, y: 40, transition: { delay: 1000, duration: 600 } }" />

  <!-- Tool Logos and Responsibilities with swirl animation -->
  <div class="grid grid-cols-3 gap-12 mt-6">
    <div
      v-motion
      :initial="{ x: 0, y: 0, scale: 0.9, opacity: 1 }"
      :enter="{ x: -120, y: 0, scale: 0.9, opacity: 0, transition: { delay: 100, duration: 500 } }"
      class="flex flex-col items-center"
    >
      <logos-esbuild size="2.5rem" />
      <span class="font-semibold mt-2">esbuild</span>
      <span class="text-center text-xs text-gray-400 mt-1">
        Pre-bundling, Transforms,<br>
        and Minification
      </span>
    </div>
    <div
      v-motion
      :initial="{ y: 0, scale: 0.9, opacity: 1 }"
      :enter="{ y: 80, scale: 0.7, opacity: 0, transition: { delay: 200, duration: 500 } }"
      class="flex flex-col items-center"
    >
      <logos-rollup size="2.5rem" />
      <span class="font-semibold mt-2">Rollup</span>
      <span class="text-center text-xs text-gray-400 mt-1">
        Bundling, Plugins,<br>
        and (limited) Chunk Control
      </span>
    </div>
    <div
      v-motion
      :initial="{ x: 0, y: 0, scale: 0.9, opacity: 0.9 }"
      :enter="{ x: 120, y: 0, scale: 0.7, opacity: 0, transition: { delay: 300, duration: 500 } }"
      class="flex flex-col items-center"
    >
      <logos-swc size="2.5rem" />
      <span class="font-semibold mt-2">SWC</span>
      <span class="text-center text-xs text-gray-400 mt-1">
        Alternative for Transforms<br>
        React Fast Refresh
      </span>
    </div>
  </div>
</div>

---

# Rolldown-Vite

<div class="flex flex-col items-center justify-center space-y-8">
  <div class="relative">
    <div class="relative inline-block">
      <logos-vitejs size="15rem" class="mb-4" />
      <span class="absolute bottom-0 right-2">
        <VoidzeroIconsRolldown size="7rem" class="rounded-full shadow-2xl border-2 border-black/50" />
      </span>
    </div>
  </div>
</div>

---
layout: intro
---

# Why another bundler?!

---

# Why another bundler?!

<VClicks>

* Multiple bundlers under the hood lead to **increased complexity**
* Also **inconsistencies** between development and production
* Limitations per bundler / features that neither Rollup nor esbuild supports (out of scope)
* Production builds could be way faster

</VClicks>

---

<h1 class="text-center">Time to meet Rolldown</h1>
<div class="grid grid-cols-5">
  <div class="col-span-4">

  * <span class="underline font-bold">More</span> **than a "rustified" Rollup!**

  <VClicks depth="2">

  * Combines the best parts of prior art:
    * Rollup's API and compat to the plugin ecosystem
    * Speed and behavior from esbuild (such as `inject`)
    * Optimization features that you know from webpack (advanced chunking)
  * Experimental features:
    * Module Federation support (WIP)
    * HMR built-in
    * Import Map generation
    * CSS Bundling
  * Minification via [Oxc](https://oxc.rs/)

  </VClicks>

</div>

  <div class="col-span-1">
    <div class="h-full flex justify-end items-center">      
      <VoidzeroIconsRolldown size="10rem" />
    </div>
  </div>
</div>
---
layout: intro
---

# It does not stop there!

<VClicks>

## To build a bundler, you need a lot of tools - a foundation.

</VClicks>

---
layout: intro
---

<VoidzeroIconsOxc class="text-9xl mb-4" />

# Oxc

## The JavaScript Oxidation Compiler

---

# Oxc Components

<VClicks depth="2">

* [Fastest](https://github.com/oxc-project/bench-javascript-parser-written-in-rust) Parser (3x than `swc`), spec-conform (passing all Test262 stage 4 tests)
* [Fastest](https://github.com/oxc-project/bench-resolver) Resolver (26x faster than `enhanced-resolve`)
* [Fastest](https://github.com/oxc-project/bench-transformer) Transformer (40x Babel, 4x `swc`)
  * DTS emits (with Isolated Declarations) are ~20-45x faster than `tsc`
* Fastest Linter - Oxlint (50~100x faster than ESLint)
* Minifier with [best speed/compression combo](https://github.com/privatenumber/minification-benchmarks)
* Prettier-compatible & performant Formatter is work in progress

</VClicks>

<!--

Ecmascript comformance test suits

-->

---

# Updates on Oxlint

<VClicks depth="2">

* 50-100x faster than ESLint
* 500+ rules ported from popular ESLint plugins
* Used in [Preact](https://github.com/preactjs/preact/blob/main/oxlint.json), [Bun](https://github.com/oven-sh/bun/blob/main/oxlint.json), [Vue](https://github.com/vuejs/core/pull/13326) (PR open), Shopify, Airbnb, Mercedes-Benz, and many other projects
* Stable, but a lot of features are in the making:
  * Type-Aware linting (in preview already!)
  * JS Plugin support (custom lint rules)
  * Goal: Good balance: Performance <-> Compatibility
  * Fine-grained (per-glob) configuration

</VClicks>

<VClick>

```
Finished in 22.5s on 264925 files with 101 rules using 10 threads.
```

</VClick>

---
layout: intro
---

# Challenges

---

<img src="https://external-preview.redd.it/IAMB6TV2YcGBo67tBJGJLpE9T2HnPTR_acYEe4uJrG8.png?auto=webp&s=d8f1ca2c748425d0c6a81f5de20c9297739e56a1" class="h-100 mx-auto">

---


# Challenges


<VClicks depth="2">

* Just (re-)writing JS tooling in Rust **is not enough**
* How to reduce overhead between JS and Rust (e.g. rollup/rolldown plugins)?
* How to transfer data, AST, and instructions efficiently?
* How to have interop with other tooling (such as `ts-go`) in other languages?
* How to make sure people can still write their integrations/plugins in JS and TS?
* And so on...

</VClicks>

---

# Hook Filters for Plugins

---

# Hook Filters for Plugins

<Code file="rolldown-or-rollup-plugin.ts">

````md magic-move
```ts {all|5|all}
export default function myPlugin() {
  return {
    name: 'example',
    transform(code, id) {
      if (!id.endsWith('.data')) {
        // early return
        return
      }
      // perform actual transform
      return transformedCode
    },
  }
}
```
```ts {all|4-7,9}
export default function myPlugin() {
  return {
    name: 'example',
    transform: {
      filter: {
        id: /\.data$/
      },
      handler (code) {
        // perform actual transform
        return transformedCode
      },
    }
  }
}
```
````

</Code>

<VClicks>

* Don't execute hook each time
* Filter out by regex
* Works in Rolldown, Vite and Rollup

</VClicks>

---

# Raw Transform & More

<VClicks depth="2">

* How to serialize the AST and send it from Rust to JS?
  * **You don't!** Transferring it raw instead as memory block via `SharedArrayBuffer`
* Also allows **Lazy Deserialization**
  * Only parse the AST nodes you are interested in
* Magic-String like API, but executed on the Rust side
  * Send only "instructions", let Rust handle the AST modification
* Exploring how to run rules in parallel on the JS side too
  * For example by spawning worker threads
  * Will also help for a more efficient `transform` hook in Rolldown

</VClicks>

---
layout: two-cols
heading: Future plans of Rolldown-Vite
---

<VClicks depth="2">

* Phase 1 (current)
  * Separate package to stabilize and test `rolldown-vite`
* Phase 2
  * Full Bundle Mode as opt-in
  * Merge changes into `vite` when stable
  * Rolldown is now the default Bundler for `vite`
* Phase 3
  * Full Bundle Mode as default
 
</VClicks>

<template #right>

<div class="flex flex-col items-center justify-center space-y-8 mt-16">
  <div class="relative">
    <div class="relative inline-block">
      <logos-vitejs size="15rem" class="mb-4" />
      <span class="absolute bottom-0 right-2">
        <VoidzeroIconsRolldown size="7rem" class="rounded-full shadow-2xl border-2 border-black/50" />
      </span>
    </div>
  </div>
</div>

</template>

---

# Full Bundle Mode?

<VClicks depth="2">

* Vite's Dev Server is *unbundled* and fast
* Slow **Dev** Server with large (enterprise-level) projects
  * Tens of thousands of requests as no bundling exist
  * Would perform better with bundling
* Goals
  * Same or better dev server perf for small to medium projects
  * Better dev server startup / hard reload performance for large projects

</VClicks>

---

# Ready to use it?

2.5-16x build time reduction for production builds

<div class="flex flex-col items-center justify-center space-y-8">
  <div class="relative">
    <div class="relative inline-block">
      <logos-vitejs size="12rem" class="mb-4" />
      <span class="absolute bottom-0 right-2">
        <VoidzeroIconsRolldown size="5rem" class="rounded-full shadow-2xl border-2 border-black/50" />
      </span>
    </div>
  </div>
</div>

<div class="mx-auto text-center mt-8 space-y-4">

## Available to try now as `rolldown-vite`

### [vite.dev/rolldown](https://vite.dev/rolldown)

</div>

---
layout: intro
---

# That's not the end yet!

<VClicks> 

## We want to unify the whole toolchain

</VClicks>

<VoidzeroIconsVoidzeroLogo class="text-white mx-auto" size="15rem" />


---


# Thanks a lot to my sponsors!
<img src="https://raw.githubusercontent.com/manniL/static/main/sponsors.svg" class="h-80 mx-auto" alt="My GitHub sponsors">

---
layout: two-cols
heading: Thank you for your attention!
---

<template v-slot:default>

<div class="flex flex-col justify-center items-center h-full">
<img
  class="w-75 rounded-full"
  src="https://lichter.io/img/me@2x.webp"
  />
  <h2 class="mt-4">Alexander Lichter</h2>
</div>

</template>

<template v-slot:right>

<div class="space-y-2 mt-10 text-xl h-full">

* DevRel at <VoidzeroIconsVoidzeroLogo class="text-white" width="4rem" height="auto" />
* <mdi-account-check class="dark:text-green-100 text-green-700" /> Web Engineering Consultant
* <mdi-microphone /> Speaker & Instructor
* <logos-nuxt-icon /> Nuxt.js Team
* <mdi-github /><logos-bluesky class="text-sm mb-1 text-blue-400" /><mdi-youtube class="text-red-500" /><mdi-twitch class="text-purple-700" /> @TheAlexLichter
* <mdi-web /> [https://lichter.io](https://lichter.io)

</div>

</template>
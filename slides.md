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
  <img src="https://raw.githubusercontent.com/TanStack/tanstack.com/refs/heads/main/public/images/logos/logo-color-600.png" class="w-20" />
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
layout: intro
---

# What is a bundler?!

<VClicks>

And why do I need one?

</VClicks>

---

<img src="https://user-images.githubusercontent.com/1402241/126045972-c0a1e9db-d3fc-46a4-b836-1567043a65ce.png" class="h-90 mx-auto">
<span class="text-xs">

[Source](https://github.com/pahen/madge/issues/289)

</span>

---

<img src="/tree-chart.png" class="h-100 mx-auto">

---
layout: intro
---

# Why?

---

<img src="https://pbs.twimg.com/media/F8K5cyBawAAtbDh?format=jpg&name=large" alt="No build!?" class="h-100 mx-auto"> 

<noto-cross-mark v-click class="text-6xl text-red-500 transition-all duration-200" v-drag="[440,87,249,214]" />

---

````md magic-move
```jsx
function HelloWorld() {
  return (
    <div>
      <h1>Hello SquiggleConf!</h1>
      <p>This is a simple React SFC component.</p>
    </div>
  );
}
```
```vue
<script setup>
import { ref } from 'vue';
const message = ref('Hello SquiggleConf!');
</script>

<template>
  <div>
    <h1>{{ message }}</h1>
    <p>This is a simple Vue SFC component.</p>
    <input v-model="message" />
  </div>
</template>
```
```ts
const a: number = '1'
```
```ts
const a: number = '1'
```
```js
import { format } from 'date-fns'
console.log(format(new Date(), 'yyyy-MM-dd'))
```
```js
const e=6048e5,t=3600*24;t*7,t*365.2425;const n=Symbol.for(`constructDateFrom`);
function r(e,t){return typeof e==`function`?e(t):e&&typeof e==`object`&&
n in e?e[n](t):e instanceof Date?new e.constructor(t):new Date(t)}
function i(e,t){return r(t||e,e)}let a={};function o(){return a}
function s(e,t){let n=o(),r=t?.weekStartsOn??t?.locale?.options?.weekStartsOn??
n.weekStartsOn??n.locale?.options?.weekStartsOn??0,a=i(e,t?.in),s=a.getDay(),
c=(s<r?7:0)+s-r;
return a.setDate(a.getDate()-c),a.setHours(0,0,0,0),a}function c(e,t){
return s(e,{...t,weekStartsOn:1})}function l(e,t){let n=i(e,t?.in),
a=n.getFullYear(),o=r(n,0);o.setFullYear(a+1,0,4),o.setHours(0,0,0,0);
let s=c(o),l=r(n,0);l.setFullYear(a,0,4),l.setHours(0,0,0,0);let u=c(l);
return n.getTime()>=s.getTime()?a+1:n.getTime()>=u.getTime()?a:a-1}
function u(e){let t=i(e),n=new Date(Date.UTC(t.getFullYear(),
t.getMonth(),t.getDate(),t.getHours(),t.getMinutes(),t.getSeconds(),t.getMilliseconds()));
return n.setUTCFullYear(t.getFullYear()),e-+n}function d(e,...t)
{let n=r.bind(null,e||t.find(e=>typeof e==`object`));return t.map(n)}
function f(e,t){let n=i(e,t?.in);return n.setHours(0,0,0,0),n}
function p(e,t,n){let[r,i]=d(n?.in,e,t),a=f(r),o=f(i),s=+a-u(a),c=+o-u(o);
return Math.round((s-c)/864e5)}function m(e,t){let n=l(e,t),i=r(t?.in||e,0);
return i.setFullYear(n,0,4),i.setHours(0,0,0,0),c(i)} /*...*/ 
```
````

<svg v-click="[3,4]" v-drag="[78,72,157,40]" xmlns="http://www.w3.org/2000/svg" width="450" height="17" fill="none">
  <path stroke="#F14C4C" stroke-linecap="round" stroke-width="8.4" d="m182.791 7.132-2.337 2.56c-2.591 2.841-5.9 2.914-8.534.187l-2.367-2.45c-2.61-2.702-5.887-2.657-8.47.118l-1.984 2.13c-2.648 2.843-6.016 2.816-8.647-.07l-2.259-2.475c-2.654-2.911-6.055-2.911-8.711 0l-2.213 2.426c-2.655 2.911-6.056 2.911-8.711 0l-2.214-2.426c-2.655-2.911-6.055-2.911-8.71 0l-2.214 2.426c-2.655 2.911-6.055 2.911-8.711 0l-2.133-2.338c-2.697-2.956-6.157-2.907-8.824.125l-1.759 2c-2.666 3.032-6.127 3.081-8.823.125l-2.134-2.338c-2.654-2.911-6.055-2.911-8.71 0l-2.214 2.426c-2.655 2.911-6.056 2.911-8.711 0l-2.213-2.426c-2.656-2.911-6.057-2.911-8.711 0l-2.214 2.426c-2.655 2.911-6.056 2.911-8.71 0l-2.26-2.476c-2.655-2.91-6.169-2.861-8.823.05L28.336 9.47c-2.696 2.956-6.157 2.907-8.823-.125l-1.76-2C15.088 4.313 11.697 4.176 9 7.132L5 11.5m177.791-4.368c2.655-2.911 6.056-2.911 8.71 0m-8.71 0c2.696-2.956 6.044-3.032 8.71 0m0 0 2.214 2.426m0 0c2.655 2.911 6.056 2.911 8.71 0m-8.71 0c2.667 3.032 6.015 2.956 8.71 0m0 0 2.214-2.426c2.655-2.911 6.056-2.911 8.712 0l2.213 2.426m0 0c2.655 2.911 6.056 2.911 8.711 0m-8.711 0c2.654 2.911 6.056 2.911 8.711 0m0 0 2.213-2.426m0 0c2.656-2.911 8.045-2.911 10.7 0m-10.7 0c2.655-2.911 8.044-2.911 10.7 0m0 0 2.213 2.426m0 0c2.696 2.956 4.089 2.819 6.755-.213m-6.755.213c2.655 2.911 4.1 2.697 6.755-.213m0 0 1.759-2c2.667-3.032 8.425-3.169 11.121-.213m-12.88 2.213 1.956-2c2.655-2.91 8.27-3.124 10.924-.213m0 0 2.134 2.338c2.696 2.956 6.157 2.907 8.823-.125l1.759-2c2.667-3.032 6.127-3.081 8.824-.125l2.133 2.338c2.656 2.911 6.056 2.911 8.711 0l2.214-2.426c2.655-2.911 6.055-2.911 8.71 0l2.214 2.426c2.655 2.911 6.056 2.911 8.711 0l2.213-2.426c2.656-2.911 6.057-2.911 8.711 0l2.259 2.476c2.631 2.885 5.999 2.912 8.647.07l1.984-2.13c2.583-2.776 5.86-2.821 8.47-.119l2.367 2.45c2.634 2.727 5.943 2.655 8.534-.187l2.337-2.56c2.655-2.911 6.056-2.911 8.71 0l2.214 2.426c2.655 2.911 6.056 2.911 8.71 0l2.215-2.426c2.654-2.911 6.055-2.911 8.711 0l2.213 2.426c2.655 2.911 6.056 2.911 8.711 0l2.213-2.426c2.656-2.911 6.057-2.911 8.711 0l2.134 2.338c2.696 2.956 6.157 2.907 8.823-.125l1.759-2c2.667-3.032 6.127-3.081 8.824-.125l1.594 2.25c2.696 2.956 6.157 2.907 8.823-.125l1.759-2"/>
</svg>

---

# What is a bundler?!
And why do I need one?


<VClicks depth="2"> 

* Transforms your non-JS code into JavaScript
* Removes unused code from dependencies
* Combines/spreads your code and dependencies into files (chunks)
  * Allows to load unneeded JS on demand and not initially
  * Reduce network requests and waterfalls
* Smaller bundles due to minification

</VClicks>

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
  <VClicks depth="2">

  * <span class="underline font-bold">More</span> **than a "rustified" Rollup!**
  * Combines the best parts of prior art:
    * Rollup's API and compat to the plugin ecosystem
    * Speed and behavior from esbuild (such as `inject`)
    * Optimization features that you know from webpack (advanced chunking)
  * Experimental features:
    * Module Federation support (WIP)
    * HMR built-in
    * Import map generation
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

# Raw Transfer & More

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

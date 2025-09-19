---
theme: ./theme
title: "Rolldown: How Vite Bundles at the Speed of Rust"
website: lichter.io
handle: TheAlexLichter
favicon: https://lichter.io/img/me@2x.jpg
highlighter: shiki
lineNumbers: true
layout: intro
---

---
layout: intro
preload: false
transition: none
---

<div class="flex justify-center items-center h-full w-full">

<div class="grid grid-cols-4 gap-y-8 gap-x-32 items-center">
  <!-- Row 1 -->
  <logos-analog
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 100, duration: 400 } }"
  />
  <logos-angular-icon
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 200, duration: 400 } }"
  />
  <logos-react
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 300, duration: 400 } }"
  />
  <logos-vue
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 400, duration: 400 } }"
  />

  <!-- Row 2 -->
  <logos-svelte-icon
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 500, duration: 400 } }"
  />
  <logos-solidjs-icon
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 600, duration: 400 } }"
  />
  <logos-ember
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 700, duration: 400 } }"
  />
  <logos-remix-icon
    class="filter filter-invert"
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 800, duration: 400 } }"
  />

  <!-- Row 3 -->
  <img
    src="https://raw.githubusercontent.com/TanStack/tanstack.com/refs/heads/main/public/images/logos/logo-color-600.png"
    class="w-20"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 900, duration: 400 } }"
  />
  <logos-laravel
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 1000, duration: 400 } }"
  />
  <logos-ruby
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 1100, duration: 400 } }"
  />
  <logos-marko
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 1200, duration: 400 } }"
  />

  <!-- Row 4 -->
  <img
    src="https://vitepress.dev/vitepress-logo-large.svg"
    alt="VitePress"
    class="w-16 ml-2"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 1300, duration: 400 } }"
  />
  <logos-qwik-icon
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 1400, duration: 400 } }"
  />
  <logos-redwoodjs
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 1500, duration: 400 } }"
  />
  <logos-nuxt-icon
    size="4rem"
    v-motion
    :initial="{ y: -60, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { delay: 1600, duration: 400 } }"
  />
</div>

</div>

---
layout: intro
---

# What do all these frameworks have in common?


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

<img src="/treemap-chart.png" class="h-100 mx-auto">

---
layout: intro
---

# Why?

---

<img src="https://pbs.twimg.com/media/F8K5cyBawAAtbDh?format=jpg&name=large" alt="No build!?" class="h-100 mx-auto"> 

<noto-cross-mark v-click class="text-6xl text-red-500 transition-all duration-200" v-drag="[414,119,167,147]" />

---

````md magic-move
```jsx
function HelloWorld() {
  return (
    <div>
      <h1>Hello SquiggleConf!</h1>
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
    <p>This is a simple SFC component.</p>
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

<svg v-click="[3,4]" v-drag="[127,49,12,40]" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 6 3" enable-background="new 0 0 6 3" height="6" width="12"><g fill="#f14c4c"><polygon points="5.5,0 2.5,3 1.1,3 4.1,0"/><polygon points="4,0 6,2 6,0.6 5.4,0"/><polygon points="0,2 1,3 2.4,3 0,0.6"/></g></svg>

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

<VoidzeroIconsRolldown size="7.5rem" class="mx-auto mt-12" />

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
    * Inspiration for optimization features from webpack (advanced chunking)
  * Experimental features:
    * Built-in HMR
    * Import map generation
    * CSS Bundling
    * First class Module Federation (WIP)
  * Minification via [Oxc](https://oxc.rs/)

  </VClicks>

</div>

  <div class="col-span-1">
    <div class="h-full flex justify-end items-center">      
      <VoidzeroIconsRolldown
        size="10rem"
        v-motion
        :initial="{ y: -400, rotate: 0, opacity: 0 }"
        :enter="{ y: 0, rotate: 360, opacity: 1, transition: { duration: 800 } }"
      />
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

---

# Parser

<VClicks depth="2">

* Transforms JavaScript/TypeScript code into an AST (Abstract Syntax Tree)
* `oxc-parser` is the **[fastest](https://github.com/oxc-project/bench-javascript-parser-written-in-rust) JavaScript parser**
* Spec-conform (passes all Test262 stage 4 tests)
* 3x faster than `swc`, 5x faster than `Biome`

</VClicks>

---

# Parser 

<BarChart
  :tools="[{name: 'oxc', value: 52}, {name: 'swc', value: 164.5}, {name: 'biome', value: 296.5}]"
  title="Speed comparison parsing typescript.js (parallel)"
  unitLegend="Time to parse (in ms)" 
   />

---

# Resolver

<VClicks depth="2">

* Module resolver for JavaScript/TypeScript
* Implements for both ESM and CJS module resolution
* Built-in support for tsconfig (`extends`, `paths` aliases, project reference support)
* 28x faster than `enhanced-resolve`, [fastest](https://github.com/oxc-project/bench-resolver) resolver

</VClicks>

---

# Resolver

<BarChart
  :tools="[{name: 'oxc-resolver', value: 0.0243}, { name: 'enhanced-resolve', value: 0.9026}]"
  title="Speed comparison for module resolution (lower is better)"
  unitLegend="Time to resolve (in ms)" 
   />


---

# Transformer

<VClicks depth="2">

* Transforms non-JS code such as TypeScript or JSX to ESNext
* Built-in React Refresh
* Syntax lowering possible (e.g. ESNext to ES2015)
* Can emit `.d.ts` files, faster than using `tsc` (but needs `isolatedDeclarations`)
* Built-in support for `styled-components`
* [Fastest](https://github.com/oxc-project/bench-transformer) transformer

</VClicks>

---

# Transformer: Emitting `.d.ts`

<BarChart
  :tools="[{name: 'oxc', value: 0.1272 }, { name: 'tsc', value: 12.4706 }]"
  title="Speed comparison for emitting .d.ts files (lower is better)"
  unitLegend="Time to emit (in ms)"
   />

---

# Transformer: Transforming and lowering

<BarChart
  :tools="[{name: 'oxc', value: 0.1952 }, { name: 'swc', value: 0.7636 }, { name: 'babel', value: 11.6479 }]"
  title="Speed comparison for transforming & lowering to ES2015 (lower is better)"
  unitLegend="Time to transform (in ms)"
   />

---

# Oxlint (Linter)

<VClicks depth="3">

* Linter for JavaScript and TypeScript (including JSX/TSX)
* Partial custom component support for now (`<script>` part of Vue/Svelte/... components)
* 50~100x faster than ESLint
* 570+ rules ported from popular ESLint plugins
* Used in [Preact](https://github.com/preactjs/preact/blob/main/oxlint.json), [Bun](https://github.com/oven-sh/bun/blob/main/oxlint.json), [Vue](https://github.com/vuejs/core/pull/13326) (PR open), Shopify, Airbnb, Mercedes-Benz, and many other projects
* Stable, but a lot of features are being worked on:
  * Type-Aware linting (in preview already!)
  * JS Plugin support (custom lint rules)
    * Goal: Performant while being as ESLint-compatible as possible
  * Fine-grained (per-glob) configuration

</VClicks>

<VClick>

```
Finished in 22.5s on 264925 files with 101 rules using 10 threads.
```

</VClick>

---

# Oxlint: Custom JS Plugins

<img src="https://pbs.twimg.com/media/G1DoFzLakAASrOt?format=jpg&name=large" alt="Code demo" class="h-90 mx-auto">

---

# Minifier

<VClicks depth="2">

* **Not** the fastest minifier
* **Not** the minifier with the best compression
* Minifier with one of the **best** compression/speed tradeoffs
* [Detailed benchmark](https://github.com/privatenumber/minification-benchmarks#-results) by `privatenumber`

</VClicks>

---

# Formatter

<VClicks depth="2">

* Work-in-progress

* Performant formatter with prettier-compatible defaults
* Addressing issues such as line wrapping, print width
* Built-in sorting
* First class Tailwind Support planned
* Current state:
  * JavaScript | 620/699 (88.70%) -> 645/699 (92.27%)
  * TypeScript | 329/573 (57.42%) -> 331/573 (57.77%)
* [RFC open](https://github.com/oxc-project/oxc/discussions/13608) - please share your thoughts!

</VClicks>


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
* How to reduce overhead between JS and Rust (e.g. for Rollup/Rolldown or custom Oxlint plugins)?
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

# Transferring AST

<div class="grid grid-cols-5">
  <div class="col-span-2">
<VClicks>

* AST transfer between Rust and JS is expensive!
* Large cost of serializing/deserializing it
* So how to reduce the overhead?

</VClicks>
  </div>
  <div v-click="4" class="col-span-3 overflow-y-scroll h-90">
````md magic-move {at: 5}
```rust
Vec([
  VariableDeclaration(
    VariableDeclaration {
      span: Span {
        start: 0,
        end: 11,
      },
      declarations: Vec(
        [
          VariableDeclarator {
            span: Span {
              start: 6,
              end: 11,
            },
            id: BindingPattern {
              kind: BindingIdentifier(
                BindingIdentifier {
                  span: Span {
                    start: 6,
                    end: 7,
                  },
                  name: "a",
                  symbol_id: Cell {
                    value: Some(
                      SymbolId(
                        0,
                      ),
                    ),
                  },
                },
              ),
              type_annotation: None,
              optional: false,
            },
            init: Some(
              NumericLiteral(
                NumericLiteral {
                  span: Span {
                    start: 10,
                    end: 11,
                  },
                  value: 1.0,
                  raw: Some(
                    "1",
                  ),
                  base: Decimal,
                },
              ),
            ),
            kind: Const,
            definite: false,
          },
        ],
      ),
      kind: Const,
      declare: false,
    },
  )
])
```
```js
{
  "type": "Program",
  "body": [
    {
      "type": "VariableDeclaration",
      "kind": "const",
      "declarations": [
        {
          "type": "VariableDeclarator",
          "id": {
            "type": "Identifier",
            "decorators": [],
            "name": "a",
            "optional": false,
            "typeAnnotation": null,
            "start": 6,
            "end": 7
          },
          "init": {
            "type": "Literal",
            "value": 1,
            "raw": "1",
            "start": 10,
            "end": 11
          },
          "definite": false,
          "start": 6,
          "end": 11
        }
      ],
      "declare": false,
      "start": 0,
      "end": 11
    }
  ],
  "sourceType": "module",
  "hashbang": null,
  "start": 0,
  "end": 11
}
```
```js
const a = 1
```
````
  </div>
</div>


---
layout: intro
---

# **No serialization!**

---

# Raw transfer

<VClicks>

* JS creates an `ArrayBuffer` and passes it to Rust.
* Rust creates an `Allocator` and uses the buffer as backing memory.
* Rust parses the AST into that allocator
* Rust also converts module record and errors into arena types, and writes them into the allocator.
* Insert the offset at which data begins in the buffer at the end of the buffer.
* Control passes back to JS.
* JS code decodes data in the buffer, and creates JS objects fitting the ESTree shape.

</VClicks>

---

<img src="https://pbs.twimg.com/media/Gohwe6aWMAAW1CA?format=jpg&name=medium" class="h-90 mx-auto filter filter-invert">

<span class="text-xs">[Made by Herrington Darkholme](https://x.com/hd_nvim/status/1911901720982024321/photo/1)</span>

---
layout: intro
---

# ~5x speedup
## compared to classic serialization, in typical cases

---

# And there is more...

<VClicks depth="2">

* Also allows to explore **Lazy Deserialization**
  * Do not decode the buffer anymore
  * Only deserialize the AST nodes you are accessing on-demand
  * Approx **~3x faster** than "just raw transfer"
* And this can also work for the opposite operation
  * Magic-String like API, but executed on the Rust side
  * Send only "instructions", let Rust handle the AST modification
* On another note: Exploring how to run rules in parallel on the JS side too
  * For example by spawning worker threads
  * Will also help for a more efficient `transform` hook in Rolldown

</VClicks>

---
clicks: 4
---

<div
  class="flex flex-col items-center justify-center"
  v-motion
  :initial="{ y: 0 }"
  :enter="{y: 150 }"
  :click-1="{ y: 0, transition: { duration: 600 } }"
  :click-2="{ y: -150, transition: { duration: 600 } }"
  :click-3="{ y: -300, scale: 1, transition: { duration: 600 } }"
  :click-4="{ y: 150, scale: 2.5, transition: { duration: 600 } }"
>
  <!-- Framework Level -->
  <div class="flex flex-col items-center">
    <span class="text-3xl font-bold mb-2">Your Framework</span>
    <span class="text-gray-400 text-sm mt-1">Application code, UI, logic</span>
  </div>

  <!-- Down Arrow -->
  <span :class="$clicks < 1 && 'invisible'" class="text-4xl">↓</span>

  <!-- Vite Level -->
  <div :class="$clicks < 1 && 'invisible'" class="flex flex-col items-center">
    <logos-vitejs size="4rem" class="mb-2" />
    <span class="text-2xl font-semibold">Vite</span>
    <span class="text-gray-400 text-sm mt-1">Build tool, dev server, plugin system</span>
  </div>

  <!-- Down Arrow -->
  <span :class="($clicks < 2 || $clicks > 3) && 'invisible'" class="text-4xl">↓</span>

  <!-- Rolldown Level -->
  <div :class="$clicks < 2 && 'invisible'" class="flex flex-col items-center">
    <VoidzeroIconsRolldown size="4rem" class="mb-2 rounded-full shadow-2xl border-2 border-black/50" />
    <span class="text-xl font-semibold">Rolldown</span>
    <span class="text-gray-400 text-sm mt-1">Bundler, DCE & Treeshaking, Chunking</span>
  </div>

  <!-- Down Arrow -->
  <span :class="$clicks < 3 && 'invisible'" class="text-4xl my-2">↓</span>

  <!-- Oxc Level -->
  <div :class="$clicks < 3 && 'invisible'" class="flex flex-col items-center">
    <VoidzeroIconsOxc size="4rem" class="mb-2" />
    <span class="text-lg font-semibold">Oxc</span>
    <span class="text-gray-400 text-sm mt-1">Parser, Resolver, Transformer,  Minifier, Linter, Formatter</span>
  </div>
</div>

---
layout: two-cols
heading: Future plans of Rolldown-Vite
---

<VClicks depth="2">

* Phase 1 (current)
  * Separate package to stabilize and test `rolldown-vite`
* Phase 2
  * Vite 8 beta
  * No separate package anymore
* Phase 3
  * Merge changes into `vite` when stable
  * Rolldown is now the default Bundler for `vite`
 
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

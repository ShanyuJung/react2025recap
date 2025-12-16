---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Welcome to Slidev
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply UnoCSS classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# duration of the presentation
duration: 35min
---

# React 2025 Recap

Not that kind recap you think

---

## 來回顧一下 2025 React 生態圈的大事

<div class="flex justify-center items-center gap-12 mt-20">
<div>

<br>
<br>
<br>
<br>

<v-click at="1">

<div :class="$clicks >= 2 ? 'line-through' : ''">

## React 19

</div>

</v-click>

<span></span>

<br>

<v-click at="3">

<div :class="$clicks >= 4 ? 'line-through' : ''">

## React conf 2025

</div>

</v-click>

<v-click at='4'>
<span></span>
</v-click>

</div>

<div class="flex items-center justify-center">
  <v-click at="2">
    <img src="/assets/img/thinking meme.jpg" class="w-80 rounded-xl shadow-lg" />
  </v-click>
</div>
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---

<div class='flex items-center justify-center h-full'>
 <h1> 把時間倒轉一下，回到 2025 年 3 月 21 日 </h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class="flex items-center justify-center h-full">
  <img src="/assets/img/cve202529927.png" class="h-100 rounded-xl shadow-lg" />
</div>

---

<div class="flex items-center justify-center h-full">
  <img src="/assets/img/authMiddleware.png" class="h-100 rounded-xl shadow-lg" />
</div>

---

<div class="flex items-center justify-center h-full">
  <img src="/assets/img/middle.png" class="h-100 rounded-xl shadow-lg" />
</div>

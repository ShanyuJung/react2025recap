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

---

<div class='flex flex-col items-center justify-center h-full'>
 <h1>Next.js 當然也有類似的服務</h1>
 <v-click>
  <h1>但跟其他的服務不同 Vercel 開源 Next.js</h1>
  <h1>是為了幫自家雲服務搶占市場</h1>
 </v-click>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class="flex items-center justify-center h-full">
  <img src="/assets/img/vercel1.png" class="w-150 rounded-xl shadow-lg" />
</div>

---

<div class="flex items-center justify-center h-full">
  <img src="/assets/img/vercel2.png" class="w-150 rounded-xl shadow-lg" />
</div>

---

<div class='flex flex-col items-center justify-center h-full'>
 <h1>但有個小問題，如果 middleware 沒考慮 CDN 部屬場景的話</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class="flex items-center justify-center h-full">
  <img src="/assets/img/vercel3.png" class="w-150 rounded-xl shadow-lg" />
</div>

---

<div class='flex flex-col items-center justify-center h-full'>
 <h1>當然 Vercel 發現了這個問題並做出修正</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class="flex items-center justify-center h-full">
  <img src="/assets/img/next30282.png" class="w-150 rounded-xl shadow-lg" />
</div>

---

<div class='flex flex-col items-center justify-center h-full'>
```ts {all|5}
function getFetchHeaders(middleware: string, init: RequestInit) {
  const headers = new Headers(init.headers ?? {});
  const prevsub = headers.get(`x-middleware-subrequest`) || "";
  const value = prevsub.split(":").concat(middleware).join(":");
  headers.set(`x-middleware-subrequest`, value);
  headers.set(`user-agent`, `Next.js Middleware`);
  return headers;
}
```
<br>

<h1>方法就是幫請求加上特殊的 header 來標記他是由 middleware 發出的請求</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class="flex items-center justify-center h-full">
  <img src="/assets/img/next30282-2.png" class="w-150 rounded-xl shadow-lg" />
</div>

---

<div class='flex flex-col items-center justify-center h-full'>
<div class="flex items-center justify-center h-full">
  <img src="/assets/img/thinking meme.jpg" class="h-100 rounded-xl shadow-lg" />
</div>
<h1>聽起來好像有點奇怪</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class='flex flex-col items-center justify-center h-full'>
 <h1>header 應該是可以隨意填的，如果我假造一個 header 會被判定成 middleware 的請求嗎?</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class='flex flex-col items-center justify-center h-full'>
 <h1>還真的可以</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class='flex flex-col items-center justify-center h-full'>
 <h1>從發布 MR 一直到 2025/3/1 有外部資安專家發現並回報 vercel 才發現這個漏洞</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class='flex flex-col items-center justify-center h-full'>
```ts
  const randomBytes = new Uint8Array(8)
  crypto.getRandomValues(randomBytes)
  const middlewareSubrequestId = Buffer.from(randomBytes).toString('hex')
  ;(globalThis as any)[Symbol.for('@next/middleware-subrequest-id')] =
    middlewareSubrequestId
```

<br>

<h1>方法就是再加一個隨機數的 header</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class='flex flex-col items-center justify-center h-full'>
<div class="flex items-center justify-center h-full">
  <img src="/assets/img/thinking meme.jpg" class="h-100 rounded-xl shadow-lg" />
</div>
<h1>所以問題解決了?</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class='flex flex-col items-center justify-center h-full'>
 <h1>並沒有</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class='flex flex-col items-center justify-center h-full'>
  <ul>
    <li>在CDN這種冷啟動環境，產生隨機數的成本不低</li>
    <li>重新導向的請求不一定會回到同一個session</li>
    <li>部分CDN設計甚至不是回到同一台機器上</li>
  </ul>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class='flex flex-col items-center justify-center h-full'>
 <h1>一週後 Vercel 發了新的 PR</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

---

<div class='flex flex-col items-center justify-center h-full'>
<div class="flex items-center justify-center h-full">
  <img src="/assets/img/next77474.png" class="h-100 rounded-xl shadow-lg" />
</div>
<h1>你們自己想辦法吧 ovob</h1>
</div>

<style>
  h1{
    color: black;
  }
</style>

<!-- app/pages/index.vue -->
<script setup>
useHead({
  title: 'Inicio',
  meta: [
    { name: 'description', content: 'Página de información del sitio' }
  ]
})
</script>


<template>
  <main>
    <TheHeader />
    <h1>Home Page</h1>
    <ul>
      <li><NuxtLink to="/about">About</NuxtLink></li>
      <li><NuxtLink to="/blog">Blog</NuxtLink></li>
      <li><a href="https://nuxt.com">Nuxt.com</a></li>
    </ul>
    <TheFooter />
  </main>
</template>

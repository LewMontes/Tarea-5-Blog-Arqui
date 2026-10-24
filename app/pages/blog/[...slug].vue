<!-- app/pages/blog/[...slug].vue -->
<script setup>
const route = useRoute()
const { data: article } = await useAsyncData(route.path, () => {
  return queryCollection('blog').path(route.path).first()
})

if (!article.value) {
  throw createError({ statusCode: 404, statusMessage: 'Artículo no encontrado' })
}

const { data: surround } = await useAsyncData(`surround-${route.path}`, () => {
  return queryCollectionItemSurroundings('blog', route.path)
    .where('category', '=', article.value?.category)
    .order('date', 'DESC')
})
</script>

<template>
  <article class="container">
    <h1>{{ article.title }}</h1>
    <ContentRenderer :value="article" />
    <Author :author="article.author" />
    <PrevNext :prev="surround?.[0]" :next="surround?.[1]" />
    <h3>Comentarios</h3>
    <CommentsUtterances repo="LewMontes/Tarea-5-Blog-Arqui" />
  </article>
</template>

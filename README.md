# Tarea 5 - Luis Antonio Montes de Oca Ruiz

**Sitio publicado (Netlify):** https://dreamy-lolly-a1a361.netlify.app/

Ejemplo de artículo con comentarios: https://dreamy-lolly-a1a361.netlify.app/blog/deportes/kendall-waston

**Repositorio de comentarios (Utterances):** https://github.com/LewMontes/Tarea-5-Blog-Arqui

## Cambios realizados

- Se creó un repositorio público de GitHub dedicado a los comentarios y se instaló la aplicación de Utterances (github.com/apps/utterances).
- Nuevo componente `app/components/CommentsUtterances.vue`, que inserta el script de Utterances al montarse y lo vuelve a cargar cuando cambia la ruta.
- Se usa `issue-term` basado en la ruta (pathname), de modo que cada noticia del blog tiene su propio issue y su propio hilo de comentarios.
- El componente se agregó a la página de contenido del blog `app/pages/blog/[...slug].vue`, por lo que todas las noticias (sucesos, deportes y espectáculos) muestran comentarios.

## Ejecución

```bash
npm install
npm run dev        # desarrollo
npm run generate   # genera el sitio estático en .output/public
```

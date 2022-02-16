2---
aliases: null
date created: 2022-02-15 18:10
date updated:
---

### dynamic URLs
Путь каждой страницы зависит от внешних данных. Next.js позволяет статически генерировать страницы с путями, зависящими от внешних данных.

![[Pasted image 20220215181347.png]]


### Как статически генерировать страницы с динамическими маршрутами
- Надо чтобы каждый пост имел путь `/posts/<id>`, где `<id>` — это имя файла md в каталоге постов верхнего уровня.
- Поскольку у нас есть ssg-ssr.md и pre-rendering.md, пути должны быть /posts/ssg-ssr и /posts/pre-rendering.

1. Во-первых, создадим страницу с именем [id].js в разделе pages/posts. Страницы, начинающиеся с `[` и заканчивающиеся на `]`, являются динамическими маршрутами в Next.js

```jsx
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}
```

2. Экспортируем асинхронную функцию getStaticPaths с этой страницы. В этой функции нам нужно вернуть список возможных значений для id.

```jsx
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}
```

3. Наконец,  нужно снова реализовать getStaticProps — на этот раз, чтобы получить необходимые данные для записи в блоге с заданным идентификатором. getStaticProps получает параметры, содержащие идентификатор (поскольку имя файла [id].js).
4. 
Finally, we need to implement [`getStaticProps`](https://nextjs.org/docs/basic-features/data-fetching#getstaticprops-static-generation) again - this time, to fetch necessary data for the blog post with a given `id`. [`getStaticProps`](https://nextjs.org/docs/basic-features/data-fetching#getstaticprops-static-generation) is given `params`, which contains `id` (because the file name is `[id].js`).

```jsx
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}

export async function getStaticProps({ params }) {
  // Fetch necessary data for the blog post using params.id
}
```

![[Pasted image 20220215182603.png]]

**Более подробная реализация**
- [Implement getStaticPaths](https://nextjs.org/learn/basics/dynamic-routes/implement-getstaticpaths)
- Implement getStaticProps 

---

###### Citation
- [Dynamic Routes](https://nextjs.org/docs/routing/dynamic-routes)
- https://nextjs.org/docs/basic-features/data-fetching/overview#the-paths-key-required
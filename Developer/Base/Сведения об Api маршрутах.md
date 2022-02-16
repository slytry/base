---
aliases: null
date created: 2022-02-16 12:24
date updated:
---

### Нельзя fetch'ить API Route из  `getStaticProps`  или `getStaticPaths`
Они никогда не отработают на стороне клиента, только на стороне сервера
(воообще не ясно)

### Где использовать API Route
Хорошим вариантом использования API Routes является обработка ввода формы. Например, вы можете создать форму на своей странице и отправить запрос POST на ваш маршрут API. Затем вы можете написать код, чтобы напрямую сохранить его в своей базе данных. Код маршрута API не будет частью вашего клиентского пакета, поэтому вы можете безопасно писать код на стороне сервера.

### Preview Mode

[Static Generation](https://nextjs.org/docs/basic-features/pages#static-generation-recommended) is useful when your pages fetch data from a headless CMS. However, it’s not ideal when you’re writing a draft on your headless CMS and want to **preview** the draft immediately on your page. You’d want Next.js to render these pages at **request time** instead of build time and fetch the draft content instead of the published content. You’d want Next.js to bypass Static Generation only for this specific case.

Next.js has a feature called **Preview Mode** to solve the problem above, and it utilizes [API Routes](https://nextjs.org/docs/api-routes/introduction). To learn more about it take a look at our [Preview Mode](https://nextjs.org/docs/advanced-features/preview-mode) documentation.

### Dynamic API Routes

API Routes can be dynamic, just like regular pages. Take a look at our [Dynamic API Routes](https://nextjs.org/docs/api-routes/dynamic-api-routes) documentation to learn more.


---

###### Citation


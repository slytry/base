---
aliases: null
date created: 2022-02-14 17:46
date updated:
---

Вместо стандартного тэга head используется компонент Head

```js
import Head from 'next/head'

```

```jsx
<Head>
  <title>Create Next App</title>
  <link rel="icon" href="/favicon.ico" />
</Head>
```


---

###### Citation
To learn more about the `Head` component, check out the [API reference for `next/head`](https://nextjs.org/docs/api-reference/next/head).

If you want to customize the `<html>` tag, for example to add the `lang` attribute, you can do so by creating a `pages/_document.js` file. Learn more in the [custom `Document` documentation](https://nextjs.org/docs/advanced-features/custom-document).

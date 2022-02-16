---
aliases: null
date created: 2022-02-14 17:54
date updated:
---

Сторонний js, такой как ститистика, виджеты, реклама в next можно подключить двумя способами:
1. Через стандартный тэг scrip  в компоненте Head
```jsx
<Head>
  <title>First Post</title>
  <script src="https://connect.facebook.net/en_US/sdk.js" />
</Head>
```
Но в таком случае не понятно когда это скрипт будет загружен относительно других скриптов

2. Встроенный компонент - расширения для стандартного тэга

```jsx
import Script from 'next/script'
```


```jsx
export default function FirstPost() {
  return (
    <>
      <Head>
        <title>First Post</title>
      </Head>
      <Script
        src="https://connect.facebook.net/en_US/sdk.js"
        strategy="lazyOnload"
        onLoad={() =>
          console.log(`script loaded correctly, window.FB has been populated`)
        }
      />
      <h1>First Post</h1>
      <h2>
        <Link href="/">
          <a>Back to home</a>
        </Link>
      </h2>
    </>
  )
}
```

- `strategy`  - контролирует, когда должен загружаться сторонний скрипт. Значение lazyOnload указывает Next.js лениво загружать этот конкретный скрипт во время простоя браузера.
- `onLoad` - onLoad используется для запуска любого кода JavaScript сразу после завершения загрузки скрипта.

То есть в тэг Script уже встроен обработчик события и способ загрузки скрипта



---

###### Citation
To learn more about the `Script` component, check out the [documentation](https://nextjs.org/docs/basic-features/script).

---
aliases: 
tags: 
date created: Tuesday, July 5th 2022, 9:15:43 pm
date modified: Tuesday, July 5th 2022, 9:54:39 pm
---

# Изменение document

Next позволяет кастомизировать  документ. Можно поменять структуру либо добавить нужные атрибуты

Например lang на html)) или класс на body

```jsx
import { Html, Head, Main, NextScript } from 'next/document'

export default function Document() {
  return (
    <Html>
      <Head />
      <body>
        <Main />
        <NextScript />
      </body>
    </Html>
  )
}
```

- Компонет Head отилчается от компонента из  `next/head`.  Тут стоит использовать `next/head` только если хотим изменяить что-то для всех страницыц. Этот компонент будет переиспользован для всех страниц
- Сюда нельзя добовлять другие компоненты или css свойства

---

###### References

- [Custom Document documentation](https://nextjs.org/docs/advanced-features/custom-document).

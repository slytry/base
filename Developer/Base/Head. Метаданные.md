---
tags: 
aliases: null
date created: 2022-02-14 17:46
date modified: Tuesday, July 5th 2022, 9:14:32 pm
date modified: Tuesday, July 5th 2022, 9:14:32 pm
---

# Head компонент

Вместо стандартного тэга head используется компонент Head

Head может использоваться с нескольких компонентах на странице. Next соберет значения каждого Head и добавит все в один тэг. 

Для того что бы не дублировать повторяющиеся значения можно использовать атрибут `key`.  При одинаковом ключе будет применен тэг более глубокого компонента.

```jsx
 <Head>
        <title>My page title</title>
        <meta property="og:title" content="My page title" key="title" />
  </Head>
  <Head>
        <meta property="og:title" content="My new title" key="title" />
  </Head>
```

Тэг `title` не дублируется по-умолчанию. Будет также применент наиболее глубокий

Тэги в хэде могут иметь лишь вложенность в один <React.Fragment> или массив.

При размонтировании компонента его Head будет тоже удален, следует это учитывать

---

###### References

- [next/head](https://nextjs.org/docs/api-reference/next/head).


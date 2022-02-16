---
aliases: null
date created: 2022-02-16 10:03
date updated:
---

Для рендеринга Markdown  использовать библиотеку  [`remark`](https://github.com/remarkjs/remark) . Во-первых, установим:

```
npm install remark remark-html
```


Затем откройте lib/posts.js и добавьте следующие импорт

```jsx
import { remark } from 'remark'
import html from 'remark-html'
```


И обновите функцию getPostData() в том же файле следующим образом, чтобы использовать `remark`:


```jsx
export async function getPostData(id) {
  const fullPath = path.join(postsDirectory, `${id}.md`)
  const fileContents = fs.readFileSync(fullPath, 'utf8')

  // Use gray-matter to parse the post metadata section
  const matterResult = matter(fileContents)

  // Use remark to convert markdown into HTML string
  const processedContent = await remark()
    .use(html)
    .process(matterResult.content)
  const contentHtml = processedContent.toString()

  // Combine the data with the id and contentHtml
  return {
    id,
    contentHtml,
    ...matterResult.data
  }
}
```

В ф-ю добавлен async, для того чтобы мы могли ждать remark. Следовательно  метод [`getStaticProps`](https://nextjs.org/docs/basic-features/data-fetching#getstaticprops-static-generation) в `pages/posts/[id].js`  надо использовать await при вызове getPostData:


Наконец, обновите компонент `Post` в `pages/posts/[id].js`, чтобы отрисовывать `contentHtml` с помощью [`dangerouslySetInnerHTML`](https://reactjs.org/docs/dom-elements.html#dangerouslysetinnerhtml):

```jsx
export default function Post({ postData }) {
  return (
    <Layout>
      {postData.title}
      <br />
      {postData.id}
      <br />
      {postData.date}
      <br />
      <div dangerouslySetInnerHTML={{ __html: postData.contentHtml }} />
    </Layout>
  )
}
```


**Далее добавим заголовок**
```jsx
// Add this import
import Head from 'next/head'

export default function Post({ postData }) {
  return (
    <Layout>
      {/* Add this <Head> tag */}
      <Head>
        <title>{postData.title}</title>
      </Head>

      {/* Keep the existing code here */}
    </Layout>
  )
}
```

**Форматируем дату**

Для форматирования даты мы будем использовать библиотеку `date-fns`. 

```
npm install date-fns
```


Затем создайте файл с именем `components/date.js` и добавьте следующий компонент `Date`:

```jsx
import { parseISO, format } from 'date-fns'

export default function Date({ dateString }) {
  const date = parseISO(dateString)
  return <time dateTime={dateString}>{format(date, 'LLLL d, yyyy')}</time>
}
```

Теперь откройте `pages/posts/[id].js`, добавьте импорт для компонента `Date` вверху файла и используйте его поверх `{postData.date}`:

```jsx
// Add this import
import Date from '../../components/date'

export default function Post({ postData }) {
  return (
    <Layout>
      {/* Keep the existing code here */}

      {/* Replace {postData.date} with this */}
      <Date dateString={postData.date} />

      {/* Keep the existing code here */}
    </Layout>
  )
}
```
Было
![[Pasted image 20220216110013.png]]
Стало
![[Pasted image 20220216105948.png]]


**Добавим CSS**

Наконец, давайте добавим немного CSS, используя файл `styles/utils.module.css`, который мы добавили ранее. 
Импортируем стили и добавим их в `Post`

```jsx
// Add this import at the top of the file
import utilStyles from '../../styles/utils.module.css'

export default function Post({ postData }) {
  return (
    <Layout>
      <Head>
        <title>{postData.title}</title>
      </Head>
      <article>
        <h1 className={utilStyles.headingXl}>{postData.title}</h1>
        <div className={utilStyles.lightText}>
          <Date dateString={postData.date} />
        </div>
        <div dangerouslySetInnerHTML={{ __html: postData.contentHtml }} />
      </article>
    </Layout>
  )
}
```

##### Подправим Index Page
Добавим на индексную страницу ссылки на статьи. Добавим импорты на страницу 

```js
import Link from 'next/link'
import Date from '../components/date'
```

Затем внизу компонента home менят тэг li на код 

```jsx
<li className={utilStyles.listItem} key={id}>
  <Link href={`/posts/${id}`}>
    <a>{title}</a>
  </Link>
  <br />
  <small className={utilStyles.lightText}>
    <Date dateString={date} />
  </small>
</li>
```

---

###### Citation


]]
---
aliases: null
date created: 2022-02-15 10:06
date updated:
---
Надо создать папку components на верхнем уровне. Создать внутри файл layout.js. 
Внутри которого может быть такой код:

```jsx
import styles from './layout.module.css';

export default function Layout({ children }) {
  return <div className={styles.container}>{children}</div>;
}

```

Мы создает компонент Layout для задания общей структуры страницы. В дальнейшем будет импортировать этот компонет там где нужны его стили и оборачивать им другие компоненты.

```jsx
  <Layout>
      <Head>
        <title>First Post</title>
      </Head>
      <h1>First Post</h1>
      <h2>
        <Link href="/">
          <a>Back to home</a>
        </Link>
      </h2>
    </Layout>
```

---

###### Citation


---
aliases: null
date created: 2022-03-15 10:55
date updated:
---


В этом примере все перестаивается в одну колонку с помощью отмены свойств. Так работает свойсво gap и можно менять местами блоки. Но можно просто задавать родителю display: block

На тэге body есть padding. Он нужен для стабильности разменки. Тут он сделан на body в качестве примера. На релаьной странице будет лучше сделать еще один div

### html

```html
<div class="page-wrap">
  <header class="page-header">
    Header
  </header>
  <nav class="page-nav">
    Nav
  </nav>
  <main class="page-main">
    <article>
      <details>
        <summary>Article</summary>
        <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dignissimos laborum cumque incidunt, enim ipsa dicta? Porro illo doloribus, consectetur eum exercitationem sit ipsam, est nesciunt maxime, eius animi dolor? Harum.</p>
        
        <p>Officia ea repellat ad, sapiente eligendi modi magni quos temporibus totam culpa corporis, dignissimos quibusdam mollitia dolore eaque suscipit soluta beatae ipsam! Aperiam doloremque vero soluta pariatur possimus. Cupiditate, fuga.</p>
      </details>
    </article>
  </main>
  <aside class="page-sidebar">
    Aside
  </aside>
  <footer class="page-footer">
    Footer
  </footer>
</div>
```

### SCSS

```css
* {
  box-sizing: border-box;
}
body {
  background: #e4e4e4;
  padding: 5px;
  height: 100vh;
  margin: 0;

  font: 500 100% system-ui, sans-serif;
  text-transform: uppercase;
}
.page-wrap {
  background: white;
  height: calc(100vh - 10px);
  box-shadow: 0 0 3px rgba(black, 0.33);

  display: grid;
  grid-template-columns: minmax(10px, 1fr) minmax(10px, 3fr);
  grid-template-rows: min-content min-content 1fr min-content;
  gap: 1px;

  > * {
    padding: 1rem;
    text-align: center;
  }

  @media (max-width: 600px) {
    grid-template-columns: 100%;
    grid-template-rows: auto;
    > * {
      grid-column: 1 / -1 !important;
      grid-row: auto !important;
    }
  }
}

.page-header {
  grid-column: 1 / -1;
  background: #ffcdd2;
}

.page-sidebar {
  grid-column: 1 / 2;
  grid-row: 2 / 4;
  background: #e1bee7;
}
.page-nav {
  grid-column: 2 / 3;
  background: #bbdefb;
}
.page-main {
  grid-column: 2 / 3;
  background: #dcedc8;
}
.page-footer {
  grid-column: 1 / -1;
  background: #ffecb3;
}

details p {
  text-transform: none;
  text-align: left;
}
```



---

###### Citation


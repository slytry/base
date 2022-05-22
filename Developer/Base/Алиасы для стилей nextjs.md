---
aliases: 
tags: 
date created: Friday, May 20th 2022, 5:49:44 pm
date modified: Friday, May 20th 2022, 10:10:04 pm
---

# Алиасы для стилей nextjs

Обычные алиасы в tsconfig или jsconig не работают для импорта стилей

Надо настраивать сам лоадер для webpack

Сделать это можно расширив конфигурацию в файле next.config.js

```js
const path = require('path')

module.exports = {
  sassOptions: {
    includePaths: [path.join(__dirname, 'styles')],
  },
}
```

__dirname - путь в корневой папке (там где лежит .git).
Такая конфигурация означанет что папка  'styles' лежит в корне. Если бы папка styles лежала в папке src то путь был бы 'src/styles'

---

###### References

- [Customizing Sass Options](https://nextjs.org/docs/basic-features/built-in-css-support#customizing-sass-options)
- [sass-loader](https://webpack.js.org/loaders/sass-loader/)

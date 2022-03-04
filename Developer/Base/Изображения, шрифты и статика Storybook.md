---
aliases: null
date created: 2022-03-03 11:03
date updated:
---
Есть несколько путей добавть статику к сторису

### Настройка конфига для статитки (рекомендованный способ)
>Мы рекомендуем этот метод для ресурсов, которые часто используются вашими компонентами, таких как логотипы, шрифты и значки.

1. Добавляем в конфиг 

Прописываем один или несколько путей к папка хранения в staticDirs

```js
// .storybook/main.js

module.exports = {
  stories: [],
  addons: [],
  staticDirs: ['../public', '../static'],
};
```

2. Используем в компоненте

```js
// MyComponent.stories.js|jsx

import React from 'react';

export default {
  /* 👇 The title prop is optional.
  * See https://storybook.js.org/docs/react/configure/overview#configure-story-loading
  * to learn how to generate automatic titles
  */
  title: 'img',
};

// Assume image.png is located in the "public" directory.
export const WithAnImage = () => <img src="/image.png" alt="my image" />;
```



### Импортировать в сторис

Если исползуется свой конфиг WP, надо будет исползовать [лоадеры](https://v4.webpack.js.org/loaders/)

Пример из доки

```js
// MyComponent.stories.js|jsx

import React from 'react';

import imageFile from './static/image.png';

export default {
  /* 👇 The title prop is optional.
  * See https://storybook.js.org/docs/react/configure/overview#configure-story-loading
  * to learn how to generate automatic titles
  */
  title: 'img',
};

const image = {
  src: imageFile,
  alt: 'my image',
};

export const WithAnImage = () => <img src={image.src} alt={image.alt} />;
```



---

###### Citation

https://storybook.js.org/docs/react/configure/images-and-assets#serving-static-files-via-storybook
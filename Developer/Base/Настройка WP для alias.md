---
tags: 
aliases: null
date created: 2022-03-09 11:36
date modified: Friday, June 17th 2022, 11:00:47 am
date modified: Friday, June 17th 2022, 11:00:47 am
---

# Настройка WP для alias

Есть несколько путей настроить алиасы

### Ручное управление
Shortest:
```js
const path = require("path")

webpackFinal: async (config) => {
  config.resolve.alias['~'] = path.resolve(__dirname, '../src/');
  return config;
},
```

Short:
```js
const path = require("path")

webpackFinal: async (config) => {
  config.resolve.alias = {
    ...config.resolve?.alias,
    '~': path.resolve(__dirname, '../src/'),
  };
  return config;
},
```

### Автоматизация для typescript

 С помощью плагина можно выгрузить aliases с tsconfig файла

#### Синтаксис с официальной документации

```ts
// .storybook/main.js

const TsconfigPathsPlugin = require('tsconfig-paths-webpack-plugin');

module.exports = {
  webpackFinal: async (config) => {
    config.resolve.plugins = [
      ...(config.resolve.plugins || []),
      new TsconfigPathsPlugin({
        extensions: config.resolve.extensions,
      }),
    ];
    return config;
  },
};
```

#### Более короткий синтаксис с issue github

```ts
 webpackFinal: async (config) => {
    config.resolve.plugins = [new TsconfigPathsPlugin({ extensions: config.resolve.extensions })]
    return config
  },
```

---

###### Citation

- [Cant add aliases in storybook config #11989](https://github.com/storybookjs/storybook/issues/11989)
- [TypeScript Module Resolution](https://storybook.js.org/docs/react/builders/webpack#typescript-module-resolution:~:text=TypeScript%20Module%20Resolution)
---
tags: 
aliases: null
date created: 2022-03-03 10:28
date modified: Friday, June 17th 2022, 3:03:22 pm
date modified: Friday, June 17th 2022, 3:03:22 pm
---

# Установка scss в Storybook

Конфигурация webpack в sb поддерживает нативный css, но препроцессоры не будут работать.
Надо установить необходимые лоадеры и настроить WP

### Чтобы работал scss

##### Установить пакеты

```
npm i -D sass style-loader css-loader sass-loader
```

##### Настроить конфиг webpack

Файл main.js. в папку .storybook

```js
const path = require('path');

module.exports = {
	
  webpackFinal: async (config, { configType }) => {
    config.module.rules.push({
      test: /\.scss$/,
      use: ['style-loader', 'css-loader', 'sass-loader'],
      include: path.resolve(__dirname, '../'),
    });

    return config;
  },
};

```

---

###### Citation

- https://github.com/webpack-contrib/sass-loader/issues/344
- https://storybook.js.org/docs/react/builders/webpack#typescript-module-resolution:~:text=subsequent%20startup%20times.-,Extending%20Storybook%E2%80%99s%20Webpack%20config,-To%20extend%20the
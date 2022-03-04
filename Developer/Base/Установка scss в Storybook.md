---
aliases: null
date created: 2022-03-03 10:28
date updated:
---

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
//тут другие настройки
	
	
  //Надо добавить
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


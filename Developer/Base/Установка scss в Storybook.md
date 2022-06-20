---
tags: 
aliases: null
date created: 2022-03-03 10:28
date modified: Saturday, June 18th 2022, 11:12:52 am
date modified: Saturday, June 18th 2022, 11:12:52 am
---

# Установка scss в Storybook

Конфигурация webpack в sb поддерживает нативный css, но препроцессоры не будут работать.
Надо установить необходимые лоадеры и настроить WP

### Установить пакеты
### Чтобы работал scss

##### Установить пакеты

```
npm i -D sass style-loader css-loader sass-loader
```

### Настроить конфиг webpack

Файл main.js. в папку .storybook
- Если внутри стилевых файлов хотим использовать алиасы а не относительные пути, над добавить эту настройку

```js
sassOptions: {
		includePaths: [path.join(__dirname, '../styles/')],
			 },
```

- Конфигурация находится  в `src/.storybook/main.js`. Надо попросить веб пак выйти в паку src и там смотреть. 
> Возможно есть более изящное решение. Наверняка можно задать корневую папку для всего WP. Но на момент когда я это настраивал на вертикали небыло времене. К тому же я уже задал root путь при [[Добавить шрифты Storybook|подключениее шрифтов]]. Я там указал `../public/`. Сейчас есть мысль что можно рут сделать `../` а уже подключение шрифта настроить более детально. 

```js
include: path.resolve(__dirname, '../'), 
```


```js
//.storybook/main.js
const path = require('path');

module.exports = {

  webpackFinal: async (config, { configType }) => {
 	config.module.rules.push({
			test: /\.scss$/i,
			use: [
				'style-loader',
				'css-loader',
				{
					loader: 'sass-loader',
					options: {
						sassOptions: {
							includePaths: [path.join(__dirname, '../styles/')],
						},
					},
				},
			],
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
- https://storybook.js.org/docs/react/builders/webpack#typescript-module-resolution:~:text=subsequent%20startup%20times.-,Extending%20Storybook%E2%80%99s%20Webpack%20config,-To%20extend%20the

---
tags: 
aliases: 
---
#### Gulp
```
npm i -g gulp-cli 
npm i -D gulp
```
**gulp ограничения по ES6 модулям на 27.12.21  ** 
1. Модули ES не работают при сплите галп файла и помещение файла входа в одну папку с другими задачами. Возникает ошибка: ES6 модули не могут импортировать каталоги. При использовании comonjs так делать можно. В доке описан такой способ, не хочется его терять. 
2. Не работает деструктуризация. Сам gulp на модулях ComonJs.
3. Не работает плагин обшей подгрузки других плагинов gulp-load-plugins

#### Чтобы все заработало надо babel
1. Установить babel и пресет для работы последнего ES
`npm i -D @babel/core @babel/register @babel/preset-env`
2. Добавить пресет в package.json
```json
"babel": {
	"presets": [
	"@babel/preset-env"
	]
},
```
3. Либо создать файл .babelrc. На выбор
```json
{
  "presets": ["@babel/preset-env"]
}
```
4. Добавить брузерлист
```json
 "browserslist": [
    "> 1%",
    "last 2 versions",
    "not dead",
    "not IE 11"
  ],
```
---
###### Citation
Date: 2021-12-27T21:32

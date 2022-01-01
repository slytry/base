---
tags: 
aliases: 
---
Babel — трансплитер
Его подключаю как модуль к сборщику модулей. WP
Гибкий инструмет, разумеется, есть туча настроек. Но есть и пресеты настроек. 
К команде с сайта по установке babel есть настройка env, подходит для большинства проектов. `npm install --save-dev @babel/core @babel/cli @babel/preset-env`

В package надо прописать поддерживаемые браузеры


Файл конфигурации
```json
'use strict';

let path = require('path');

module.exports = {
  mode: 'production',
  entry: './js/index.js',
  output: {
    filename: 'main.js',
    path: __dirname + '/dist/js'
  },
  watch: true,

  devtool: "source-map",

  module: {
    rules: [
      {
        test: /\.m?js$/, //находим все js файлы
        exclude: /(node_modules|bower_components)/, //исключаем файлы
        use: {
          loader: 'babel-loader', //означает что будет использовать babel с WP. Его над установить  'npm i --save-dev babel-loader'
          options: {
            presets: [['@babel/preset-env', { //пресет
                debug: true, //показывает информацию о компиляции
                corejs: 3, //библиотека для подключения полифилов Его над установить  'npm i --save-dev core-js'
                useBuiltIns: "usage" //оставляет только нужные поифилы. Не мусоря всей бибилиотекой
            }]]
          }
        }
      }
    ]
  }
};
```

### Ручное исправление
Всегда что-то может пойти не так. Некоторые полифилы могут не сработать и т.д

**Ручное написание полифилов**
1. Определить что не работает
2. Найти полифил. Просто загуглить
3. Подключаем полифил в ручную по инструкции
> Hint. Все полифилы попадают в папку модулей. Мы может импортироват эти модули в код с помощью синтаксиса ES6 modules. Просто написать `import 'muduleName';`. Так мы можем подключать любые библиотеки, модули в наш код, и на выходе получиться один скриптовый файл. (если делать 'как обычно' то в конце документа будет подключенно куча скриптов этих библиотек)

---
###### Citation
[Usage Guide](https://babeljs.io/docs/en/usage)
[core-js](https://github.com/zloirock/core-js)
Date: 2021-11-16T15:36

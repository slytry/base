---
tags: 
aliases: 
---
### ES Lint
#### Установка
```
npm install eslint --save-dev
```
И скачать расширение для редактора, чтобы в самом редакторе подсвечивались ошибки

**Создать файл конфигурации (package.json уже должен быть )**
```
npx eslint --init
```
Задаст несколько вопросов в консоли, ответив на них можно тут же получить файл и установить разные варианты настроек например от air-bnb

**Но можно и ручками**
```
npm i -D eslint-config-airbnb-base eslint-plugin-import
```

И файл конфигурации. Можно встроить в package можно в отдельный файл
```json
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": ["airbnb-base"],
  "parser": "@babel/eslint-parser", //эксперементальные фичи
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "rules": {
    "import/no-extraneous-dependencies": [
      "warn",
      {
        "devDependencies": false,
        "optionalDependencies": false,
        "peerDependencies": false
      }
    ]
  }
}
```

**Экспериментальный синтаксис**
ES lint поддерживает последний вышедший стандарт. Чтобы он не ругался на все что не вышло (но пользоваться можно) надо подключить плагин @babel/eslint-parser
```
npm i -D @babel/eslint-parser
```
Чтобы заработал надо добавить в конфиг

**Настройка редактора**
В vscode надо внести настройки чтобы работало
```json
  //Закрепляет еслинт в трей
  "eslint.alwaysShowStatus": true,
  //Фключает форматирование, после этого eslint появлятеся в списке форматеров
  "eslint.format.enable": true,
  //дефолтный форматер для JS
  "[javascript]": {
    "editor.defaultFormatter": "dbaeumer.vscode-eslint"
  },
  "editor.codeActionsOnSave": {
    "source.organizeImports": true // удаляет неиспользуемые операторы import и расположит сверху импорты с глобальными путями
  },
```

#### Плагины
[eslint-plugin-babel](https://github.com/babel/eslint-plugin-babel)
``` 
npm install @babel/eslint-plugin --save-dev -g
```
``` 
npm install @babel/eslint-plugin --save-dev
```

[eslint-plugin-react](https://www.npmjs.com/package/eslint-plugin-react)
```
 npm install eslint-plugin-react --save-dev -g
```

```
 npm install eslint-plugin-react --save-dev
```

---
###### Citation
[Сложно о простом: ESLint в команде](https://habr.com/ru/post/322550/)
<https://www.jscamp.app/ru/docs/typescript10/>
Date: 2021-11-18T19:10

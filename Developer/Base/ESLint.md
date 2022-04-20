---
tags: 
aliases: 
date created: Thursday, March 17th 2022, 9:36:45 am
date modified: Thursday, March 31st 2022, 6:16:24 pm
title: ESLint
---

# ESLint

### Установка

[[ESLint CRA Typescript]]

```
npm i eslint --D
```

И скачать расширение для редактора, чтобы в самом редакторе подсвечивались ошибки.

##### Создать файл конфигурации (package.json уже должен быть )

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

##### Экспериментальный синтаксис

ES lint поддерживает последний вышедший стандарт. Чтобы он не ругался на все что не вышло (но пользоваться можно) надо подключить плагин @babel/eslint-parser

```
npm i -D @babel/eslint-parser
```

Чтобы заработал надо добавить в конфиг

##### Настройка редактора

```json
{
	   //Отключаем дефольтный линтер
  "javascript.validate.enable": false,
  "typescript.validate.enable": false,
  //Закрепляет еслинт в трей
  "eslint.alwaysShowStatus": true,
  //Фключает форматирование, после этого eslint появлятеся в списке форматеров
  "eslint.format.enable": true,
	
	
  //Не ясно для чего и так работает. Задаем языки для ESlint
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    "typescript",
    "typescriptreact"
  ],
	
 //Опционально, можно во время работы устанавливать
  "[javascript]": {
    "editor.defaultFormatter": "dbaeumer.vscode-eslint"
  },
  "[javascriptreact]": {
    "editor.defaultFormatter": "dbaeumer.vscode-eslint"
  },
  "[typescript]": {
    "editor.defaultFormatter": "dbaeumer.vscode-eslint"
  },
  "[typescriptreact]": {
    "editor.defaultFormatter": "dbaeumer.vscode-eslint"
  },
	
	 // ActionsOnSave
  "editor.codeActionsOnSave": {
	  //..."source.organizeImports": true,
	"source.fixAll.eslint": true,
  },
	
}
```

#### eslint-config-airbnb

>Если не нужен react [eslint-config-airbnb-base](https://npmjs.com/eslint-config-airbnb-base).

Требует:
- `eslint`
- `eslint-plugin-import`
- `eslint-plugin-react`
- `eslint-plugin-react-hooks`
- `eslint-plugin-jsx-a11y`

1. Установить все необходимое
Все необходимые зависимости можно посмотреть по команде:

```
npm info "eslint-config-airbnb@latest" peerDependencies
```

Команда для быстрой установки:

```
npx install-peerdeps --dev eslint-config-airbnb
```

2. Добавить в настройки  `.eslintrc`

```json
"extends": ["airbnb", "airbnb/hooks"]
```

Полные настройки для next, sb & react

```json
{
  "extends": [
    "airbnb",
    "airbnb/hooks",
    "next/core-web-vitals", //что то конфлитовало с расширеним "airbnb/hooks" Отключил временно
    "plugin:storybook/recommended"
  ],

  "rules": {
    "import/prefer-default-export": "off", //хотел чтобы экспорт по дефолту, дурачок
    "react/function-component-definition": [
      //Меняет все стрелочные ф-и на декларэйшин (причина в типизации, но пока я не умею)
      "warn",
      {
        "namedComponents": "arrow-function",
        "unnamedComponents": "arrow-function"
      }
    ],
    "react/button-has-type": "off", //Не назначен тип кнопки. Но defaultProps не видит - пришлось выключить
    "react/jsx-props-no-spreading": "warn", //Запрещает спредить props
    "no-param-reassign": [
      //запрещает менять взодящие параментры в ф-и. Но для некоторых циклов это правило не имеет смысла
      "warn",
      { "ignorePropertyModificationsFor": ["item", "element"] }
    ],
    "jsx-a11y/label-has-associated-control": "warn" //Ошибочные срабатывания.
  }
}

```

---

###### Citation
https://www.youtube.com/watch?v=RXaltL8yIlc
<https://github.com/airbnb/javascript/tree/HEAD/packages/eslint-config-airbnb#eslint-config-airbnbhooks>
[Сложно о простом: ESLint в команде](https://habr.com/ru/post/322550/)
<https://www.jscamp.app/ru/docs/typescript10/>

https://nuancesprog.ru/p/5767/

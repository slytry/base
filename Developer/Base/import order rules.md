---
aliases: 
tags: 
date created: Wednesday, May 25th 2022, 2:40:07 pm
date modified: Tuesday, June 14th 2022, 11:26:48 am
---

# Order rules

Настройка плагина для автоматической сортировки импортов ESlint

## Логика очередности

1. Dependencies / Built-in modules (eg ‘react’, ‘react-router-dom’)
2. Internal routes of absolute folders (eg ‘components’, ‘assets’)
3. Relative routes (eg ./, ../)

## Конфигурация

### groups: [array]

Принимает массив строк. Правило для определения порядка импортов

#### Типы

`"builtin"` - node "builtin" modules

```js
import fs from 'fs';
import path from 'path';
```

`"external"` -

```js
import _ from 'lodash';
import chalk from 'chalk';
```

`"internal"` - если настроили свой путь или веб-пакет для обработки внутренних путей по-разному

```js
import foo from 'src/foo';
```

`"parent"` - для относительного импорта из родителя

```js
import foo from '../foo';
import qux from '../../foo/qux';
```

`"sibling"` - для импортно с одной вложенности

```js
import bar from './bar';
import baz from './bar/baz';
```

`"index"` - "индекс" текущего каталога

```js
import main from './'
```

`"object"` - "object"-импорт (доступно только в TypeScript)

```js
import log = console.log;
```

`"type"` - импорт типа (доступно только в Flow и TypeScript)

```js
import type { Foo } from 'foo';
```

`"unknown"` - для всего остального

Значение по умолчанию: ["builtin", "external", "parent", "sibling", "index"]

#### Несколько типов можно объединять в один

Незаданные явно типы окажутся в конце

```json
[
  'builtin', 
  ['sibling', 'parent'], // Объединение
  'index',
  'object',
]
```

### pathGroups: [array of objects]

Можно самому определять группу по паттерну

```json
"pathGroups": [
      {
        "pattern": "~/**", Может быть ругуляркой
        "group": "external", одна из разрешенных групп
		"position":   "after" or "before"  определяет, где вокруг группы будет располагаться импорт
		"patternOptions":
      }
    ]
```

### pathGroupsExcludedImportTypes: [array]

Это определяет типы импорта, которые не обрабатываются сконфигурированными группами путей.

Это в основном необходимо, когда вы хотите обрабатывать группы путей, которые выглядят как внешний импорт.

```json
{
  "import/order": ["error", {
    "pathGroups": [
      {
        "pattern": "@app/**",
        "group": "external",
        "position": "after"
      }
    ],
    "pathGroupsExcludedImportTypes": ["builtin"]
  }]
}

```

Дифолтное значение ["builtin", "external", "object"]

### newlines-between: [ignore|always|always-and-inside-groups|never]

### alphabetize: {order: asc|desc|ignore, caseInsensitive: true|false}

### warnOnUnassignedImports: true|false

## Пример настройки (с проекта "Vertical")

```json
"import/order": [
			"error",
			{
				"newlines-between": "always",
				"alphabetize": {
					"caseInsensitive": false,
					"order": "asc"
				},
				"warnOnUnassignedImports": true,
				"groups": [
					"builtin",
					"external",
					"internal",
					"parent",
					"sibling",
					"index",
					"type",
					"object"
				],
				"pathGroups": [
					{
						"pattern": "./**/**.scss",
						"group": "object",
						"position": "after"
					},
					{
						"pattern": "**/**.svg",
						"group": "object",
						"position": "before"
					}
				]
			}
		],
```

---

###### References

- [How to quickly configure ESLint for import sorting](https://dev.to/diballesteros/how-to-quickly-configure-eslint-for-import-sorting-2h73)
- [import/order: Enforce a convention in module import order](https://github.com/import-js/eslint-plugin-import/blob/main/docs/rules/order.md)

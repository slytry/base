---
tags: 
aliases: null
date created: 2022-02-17 13:17
date modified: Friday, July 1st 2022, 1:11:45 pm
date modified: Friday, July 1st 2022, 1:11:45 pm
---

# Структура React проекта

## Примеры структур

- [react-rest-api-typescript-boilerplate](https://github.com/gduke3/react-rest-api-typescript-boilerplate)

## Организация

SSR: NextJs
Стеэйт менеджер: MobX
Типизация: TypeScript
Подход: By function (components, hooks, helpers…)


```
.
└── /src
		├── /.storybook
		├── /components
		├── /pages (routes)
		├── /helpers
		├── /utils
		├── /public (assets)
		├── /store
		├── /config
		├── /hooks
		├── /constants?
		├── /services
		├── /styles
		└── /types
```

## components
```
.
└── /components
		├── /shared (UI, base) - компоненты для замены нативных
		├── /layout компоненты повторяющиеся на каждой странице
		├── /pages - сборка страниц (аналог контейнеров)
		└── /simple 
```

#### Сложные компоненты

Иногда сложный компонент будет иметь кучу связанных файлов. Это включает:

- «Подкомпоненты», более мелкие компоненты, используемые исключительно основным компонентом.
- Вспомогательные функции (helpers)
- Пользовательские хуки
- Константы или данные, совместно используемые компонентом и связанными с ним файлами

```
│   └── FileViewer/
│       ├── FileViewer.tsx 			- основной комонент
│       ├── FileContent.tsx 		- внутренный компонент для отрисовки кода
│       ├── FileViewer.types.ts 	- типы 
│       ├── FileViewer.stories.tsx 	- сторис
│       ├── FileViewer.test.ts 		- тест
│       ├── Sidebar.tsx 			- внутренный компонент 
│       ├── FileViewer.data.ts 		- внутренный компонент 
│       └── FileViewer.helpers.ts 	- вспомогательная ф-я

```


## Разделение кода

Логика используемая в только в одном компонента может и должна быть вынесена в отдельный файл. Но этот файл должен находится в тойже дирректории что и сам компонент.

Сущность из папок ниже (папки лежащие в корне) должны исопьзоваться в более чем 2-х компонентах.

### hooks

Кастомные хуки

### helpers

Вспомогательные функции на ванильном js. Сортировки, преобразоваели данных и т.д

### utils

Помощник (helpers ) — это что-то конкретное для данного проекта. Обычно не имеет смысла переносить помощников между проектами. Утилита (utils) — это общая функция, которая выполняет абстрактную задачу. Согласно определению, почти каждая функция в библиотеке lodash является утилитой.

Выбирает случайный элемент из массива:

```
export const sampleOne = (arr) => {
  return arr[Math.floor(Math.random() * arr.length)];
};
```


### types

В данной папке хранятся вспомогательные типы, а также декларации модулей.

```
│   └── types/
│       ├── Models/ 			
│ 		│	└── product.models.ts - описание типов с бэка
│       └── types.ts 			  - вспомогательная ф-я

```


### constants?

 Этот файл содержит константы для всего приложения. Большинство из них связаны со стилем (например, цвета, размеры шрифта, точки останова), но я также храню здесь открытые ключи и другие «данные приложения», сообщения об ошибках и предупреждениях
 

### config

Конфигурационные файлы приложения (например в ней можно хранить данные, необходимы для взаимодействия с бэкендом)

### services

В данной папке хранятся сами сервисы, благодаря которым и происходит общение с бэкендом.

### store


---

###### Citation

- [React Architecture: How to Structure and Organize a React Application](https://www.taniarascia.com/react-architecture-directory-structure/)
- [Структура React REST API приложения + TypeScript + Styled-Components](https://vc.ru/u/758273-nikita-osin/220656-struktura-react-rest-api-prilozheniya-typescript-styled-components)
- [Delightful React File/Directory Structure](https://www.joshwcomeau.com/react/file-structure/#introduction)

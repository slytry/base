---
tags: 
aliases: 
---
### ES Lint
#### Установка

Глобально 
```
npm install eslint --global 
```

Локально
```
npm install eslint --save-dev
```
Создать файл конфигурации (package.json уже должен быть `npm init`)
```
npx eslint --init
```
Запустить ESLint на файле 
```
npx eslint yourfile.js
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


#### Конфигурация


---
###### Citation
[Держи свой код чистым с помощью ESLint](https://frontend-stuff.com/blog/eslint/)
[Сложно о простом: ESLint в команде](https://habr.com/ru/post/322550/)
Date: 2021-11-18T19:10

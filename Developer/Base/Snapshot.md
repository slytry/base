---
aliases: null
date created: 2022-03-04 16:19
date updated:
---

Идея теста в том: делаем снимок с заведома хорошими данными и при каждом изменение компонента проверяем все ли еще работает.

### Установка 
Такое тестирование  создается с помощью надстройки  [Storyshots addon](https://github.com/storybooks/storybook/tree/master/addons/storyshots) для каждой из историй. 


```bash
yarn add -D @storybook/addon-storyshots react-test-renderer
```


Затем создаем документ src/storybook.test.js

```js
import initStoryshots from '@storybook/addon-storyshots';
initStoryshots();
```

и тогда после команды

```bash
yarn test --watchAll
```

---

###### Citation


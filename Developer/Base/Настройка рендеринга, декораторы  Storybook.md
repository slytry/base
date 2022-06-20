---
tags: 
aliases: null
date created: 2022-03-03 10:55
date modified: Saturday, June 18th 2022, 11:02:07 am
date modified: Saturday, June 18th 2022, 11:02:07 am
---

# Настройка рендеринга, декораторы  Storybook

### Декораторы

Это возможность добавить тэги и стили к конкретному стори, ко всем сторисам компонент или глобально.

**Оборачиваем все сторисы**

```js
// YourComponent.stories.js|jsx

import { YourComponent } from './YourComponent';


export default {
  title: 'YourComponent',
  component: YourComponent,
  decorators: [(Story) => <div style={{ margin: '3em' }}>{Story()}</div>],
};
```

>Можно исползовать компоненту <Story/>, либо Story ф-ю.  {Story()} предпочтительней, она может предотвратить полную перерисовку компонента.

**Один сторис**

```js
// Button.stories.js|jsx

import React from 'react';

export default {
  title: 'Button',
  component: Button,
};

const Template = (args) => <Button {...args} />;

export const Primary = Template.bind({});
Primary.decorators = [(Story) => <div style={{ margin: '3em' }}>{Story()}</div>];
```

**Глобально**

```js
// .storybook/preview.js

import React from 'react';

export const decorators = [
  (Story) => (
    <div style={{ margin: '3em' }}>
      <Story />
    </div>
  ),
];
```

** “Context” для mocking **

```js
// .storybook/preview.js

import React from 'react';

import { ThemeProvider } from 'styled-components';

export const decorators = [
  (Story) => (
    <ThemeProvider theme="default">
      {Story()}
    </ThemeProvider>
  ),
];
```

### Взаимодействие в документом iframe

Комопоненты в sb отображаются как iframe. То есть как отдельная страничка в большой странице sb.
Эта страница контролируется WP. Но можно напрямую воздействовать на нее

##### Стилизация окна body

Что бы стилизовать боди надо создать `.storybook/preview-body.html`
И так может быть что-то такое:

```html
<!-- .storybook/preview-body.html -->

<style>
  html {
    font-size: 15px;
  }
</style>

<div id="custom-root"></div>
```

##### Добавление шрифтов head

Что бы умравлять head надо создать `.storybook/preview-head.html`
И взаимодействовать как с отдельным блоком head.
Можно делать все тоже самое. В том числе и подключать шрифты. Но лучше будет хранить шрифты локально ([[Изображения, шрифты и статика Storybook]])

##### Тоже самое в файле main.js

Ф-и `previewHead` и `previewBody` позволяют сделать тоже самое в конфигурации

```js
// .storybook/main.js

module.exports = {
  previewHead: (head) => (`
    ${head}
    <style>
      #main {
        background-color: yellow;
      }
    </style>
  `);
};
```

---

###### Citation

- [Story rendering](https://storybook.js.org/docs/react/configure/story-rendering#adding-to-head)
- [Decorators](https://storybook.js.org/docs/react/writing-stories/decorators)

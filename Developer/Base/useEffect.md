---
tags: 
aliases: null
date created: 2022-01-28 15:08
date updated: 2022-01-28 15:50
date modified: Friday, March 18th 2022, 8:19:42 pm
---

# useEffect

Хук эффекта, по имени `useEffect`, предоставляет возможность выполнять побочные эффекты из функционального компонента.Он служит тем же целям, что и `componentDidMount`, `componentDidUpdate` и `componentWillUnmount` в классах React, но объединен в единый API.

Первым параметром данного хука является функция, в которой инициализируется логика эффекта. В этой функции можно написать код, который будет выполнятся при рендере функционального компонента

### Зависимость для пересировки []

Вторым параметром useEffect является массив с зависимостями, главная цель которого следить за обновлениями в состоянии и при их изменении перерендеривать компонент (соотвественно снова вызывать useEffect)

Если мы используем в useEffect функцию из пропсов, то надо ее добавить в массив зависимостей

> Более того, здесь кроекта проблема. Если ф-я которая передается из пропса, есть просто ф-я переданная в качестве обработчика события, то при каждой перерисовке будет срабатывать useEffect, так как формально ф-я изменилась. Для решения этой проблемы существует хук [[useCallback]]

### После размонтирования надо убрать все слушатели

Для реализации логики, которая произойдет после удаления компонента, надо вернуть ф-ю из ф-и

```js
useEffect(() => {
	console.log('render')
  return () => {
    console.log('will unmount');
  }
}, []);
```

### Пример: Динамическое изменение заголовка

Например, этот компонент установит заголовок документа после того, как React обновит DOM:

```jsx
  import { useState, useEffect } from 'react';
  
  function Example() {
    const [count, setCount] = useState(0);
   useEffect(() => {
      document.title = `Вы кликнули ${count} раз`;
    });
  
    return (
      <div>
        <p>Вы кликнули {count} раз</p>
        <button onClick={() => setCount(count + 1)}>
          Кликни меня
        </button>
      </div>
    );
  }
```

---

###### Citation

<https://ru.reactjs.org/docs/hooks-effect.html>
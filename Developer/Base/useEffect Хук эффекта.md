---
aliases: null
date created: 2022-01-28 15:08
date updated: 2022-01-28 15:50
---

Хук эффекта, по имени `useEffect`, предоставляет возможность выполнять побочные эффекты из функционального компонента.Он служит тем же целям, что и `componentDidMount`, `componentDidUpdate` и `componentWillUnmount` в классах React, но объединен в единый API.

Первым параметром данного хука является функция, в которой инициализируется логика эффекта. В этой функции можно написать код, который будет выполнятся при рендере функционального компонента

Вторым параметром useEffect является массив с зависимостями, главная цель которого следить за обновлениями в состоянии и при их изменении перерендеривать компонент (соотвественно снова вызывать useEffect)

```jsx
useEffect(() => { 
  console.log('render')
}, []);
```

Для реализации логики, которая произойдет после удаления компонента, надо вернуть ф-ю из ф-и 

```js
useEffect(() => {
  return () => {
    console.log('will unmount');
  }
}, []);
```


Например, этот компонент установит заголовок документа после того, как React обновит DOM:

```jsx
  import { useState, useEffect } from 'react';
  
  function Example() {
    const [count, setCount] = useState(0);
  
    // Подобен componentDidMount и componentDidUpdate:
    useEffect(() => {
      // Обновление заголовка документа, используя API браузера
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
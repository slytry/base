---
aliases: null
date created: 2022-01-28 15:08
date updated: 2022-01-28 15:50
---

Хук эффекта, по имени `useEffect`, предоставляет возможность выполнять побочные эффекты из функционального компонента.Он служит тем же целям, что и `componentDidMount`, `componentDidUpdate` и `componentWillUnmount` в классах React, но объединен в единый API.

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

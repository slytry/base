---
aliases: null
date created: 2022-01-28 12:51
date updated: 2022-01-28 15:07
---

Хук для управления состоянием

```jsx
 import { useState } from 'react';

  function Example() {
    // Объявляем новую переменную состояния, которую назовём "count"
    const [count, setCount] = useState(0);
  
    return (
      <div>
        <p>Вы кликнули {count} раз</p>
        <button onClick={() => setCount(count + 1)}>
          Кликни меня!
        </button>
      </div>
    );
  }
```

`useState` возвращает пару: **текущее** значение состояния и функцию, которая позволяет вам обновлять его.

Единственный аргумент для хука `useState()` - это начальное состояние.


---

###### Citation

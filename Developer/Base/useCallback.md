---
tags: 
aliases: null
date created: 2022-03-01 18:16
date modified: Monday, June 27th 2022, 9:09:04 pm
date modified: Monday, June 27th 2022, 9:09:04 pm
---

# useCallback

Этот хук позволяет создать стабильную ссылку на ф-ю. То есть при каждой перерисовке не будет создаваться новая ф-и, и она не будет попусту инициировать useEffect. Ф-я в js это объект. А объект равен только самому себе

```
function factory() {
  return (a, b) => a + b;
}
const sum1 = factory();
const sum2 = factory();
sum1(1, 2); // => 3
sum2(1, 2); // => 3
sum1 === sum2; // => false
sum1 === sum1; // => true
```

Новая ф-я создается в любом случае. Потом сравнивается новая ф-я и предыдущая и если они не  отличаются возвращается старая. Происходит значительно больше действий. Стоит использовать useCallback, только когда действительно нужная стабильная ссылка на ф-и. Первое, что надо сделать для ускорения работы это профилирование (вкладка profile в devtools). Операция по созданию функции - дешевая. Легче чем use Callback

### Сигнатура

Внутрь хука помещаем ф-и с какой-то логикой, и вторым параметром передаем зависимости при изменение которых будет создаваться новая ф-я. Если оставить пустой масси, то ф-я создаться один раз и будет максимально стабильна

```jsx
const memoizedCallback = useCallback(
  () => {
    doSomething(a, b);
  },
  [a, b],
);
```

### Использование

Когда реально нужет useCallback


1. Компонент обернут в react.memo  и принимает ф-ю пропсом
2. Когда ф-я является зависимостью для других хуков. useEffect(..., [callback]). Иначе бесконечный цикл ререндеров
3. Если ф-я имеет какое-то внутренне состояние ([Debounce and Throttle Callbacks in React](https://dmitripavlutin.com/react-throttle-debounce/#2-debouncing-a-callback-the-first-attempt))

### Не надо мемоизировать обработчик события

Мемоизация обработчика события не даст прироста в скорости.

- Ф-я будет все равно создаваться каждый раз, useCallback будет просто отбрасывать ее.
- Это усложнит код 
- Ресурсы на стравнения двух объектов превысят выгоду от стабильой ссылки.

Так делать не надо
```jsx
import { useCallback } from 'react';
function MyComponent() {
  const handleClick = () => {
    // handle the click event
  };
  return <MyChild onClick={handleClick} />;
}
function MyChild ({ onClick }) {
  return <button onClick={onClick}>I am a child</button>;
}
```


---

###### Citation

- [Your Guide to React.useCallback()](https://dmitripavlutin.com/dont-overuse-react-usecallback/)

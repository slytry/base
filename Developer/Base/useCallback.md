---
aliases: null
date created: 2022-03-01 18:16
date updated:
---

Этот хук позволяет создать стабильную ссылку на ф-ю. То есть при каждой перерисовке не будет создаваться новая ф-и, и она не будет попусту инициировать useEffect.


```jsx
const memoizedCallback = useCallback(
  () => {
    doSomething(a, b);
  },
  [a, b],
);
```

---

###### Citation


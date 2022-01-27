---
aliases: null
date created: 2022-01-12 12:49
date updated: 2022-01-22 14:20
---

Универсальный методы для работы со сложными структурами. Это такае полезные и необходимые методы которые мы должны и сами реализовать, если будем создавать собственную структуру данных

### Object.keys, values, entries

- [Object.keys(obj)](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Object/keys) – возвращает массив ключей. А вот к массив имеет свойство `length` так можно узнать количество ключей объекта.
- [Object.values(obj)](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Object/values) – возвращает массив значений.
- [Object.entries(obj)](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Object/entries) – возвращает массив пар `[ключ, значение]`.

##### Существует отличия работы этих методов.

Для **Обычных объектов**
Синтаксис представлен выше. Такой симнткаксис сделан для гибкости.   У нас может быть объект `data`, который реализует свой собственный метод `data.values()`. И мы всё ещё можем применять к нему стандартный метод `Object.values(data)`.
Второе отличие в том, что методы вида `Object.*` возвращают «реальные» массивы, а не просто итерируемые объекты.

Для **`Map`, `Set`, `Array`.**

Синтаксис:

- `map.keys()` – возвращает итерируемый объект по ключам,
- `map.values()` – возвращает итерируемый объект по значениям,
- `map.entries()` – возвращает итерируемый объект по парам вида `[ключ, значение]`, этот вариант используется по умолчанию в `for..of`.

Возвращает перебираемый объект.

**Object.keys/values/entries игнорируют символьные свойства**

Так же, как и цикл `for..in`, эти методы игнорируют свойства, использующие `Symbol(...)` в качестве ключей.

Но если требуется учитывать и символьные ключи, то для этого существует отдельный метод [Object.getOwnPropertySymbols](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertySymbols), возвращающий массив только символьных ключей. Также, существует метод [Reflect.ownKeys(obj)](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Reflect/ownKeys), который возвращает _все_ ключи.

### Трансформации объекта

У объектов нет множества методов, которые есть в массивах, например `map`, `filter` и других.
Если мы хотели бы их применить, то можно использовать `Object.entries` с последующим вызовом `Object.fromEntries`:

1. Вызов `Object.entries(obj)` возвращает массив пар ключ/значение для `obj`.
2. На нём вызываем методы массива, например, `map`.
3. Используем `Object.fromEntries(array)` на результате, чтобы преобразовать его обратно в объект.

---

###### Citation

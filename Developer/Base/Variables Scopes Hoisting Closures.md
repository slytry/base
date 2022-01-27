---
aliases: null
date created: 2022-01-23 16:01
date updated: 2022-01-23 16:03
---
### Словарь
- `Scope` is determining where variables, functions, and objects are accessible in your code during run-time.
- `Hoisting` Механизм в js, который обрабатывает все объявления переменных, как если бы они были объявлены в верхней части функциональной области (если объявлены внутри функции) или глобальной области (если объявлены вне функции), независимо от того, где происходит фактическое объявление. По сути, это и есть “подъем”. Это значит что можно объявить переменную после того как что-то присвоить ей.
- `Closure` gives you access to an outer function's scope from an inner function.



  ### Question 1

```js
var variable = 10;
(()=>{
   console.log(variable);
   var variable = 20;
   console.log(variable);
})();
```

Тут будет undefined 20. Это происзошло из за механика хостинга.
Это можно пеерписать так:

```js
var variable = 10;
(()=>{
   var variable;
   console.log(variable);   // undefined
   variable = 20;
   console.log(variable);   // 20
})();
```

### Question 2


```js
var variable = 10;
(()=>{
   console.log(variable);   // undefined
   variable = 20;
   console.log(variable);   // 20
})();
```
 Ответ: `10 and 20`. 
 Тут произошло замыкание. Это когда функция берет значение из внешнего окружения.


### Question Simples


```js
var variable = 10;
(()=>{
   console.log(variable);   // undefined
   variable = 20;
   console.log(variable);   // 20
})();
var variable = 30;
console.log(variable);
```
Ответ`10 20 30` тут все просто


```js
var variable;
variable = 10;
(()=>{
   var variable;
   console.log(variable);   // undefined
   variable = 20;
   console.log(variable);   // 20
})();
console.log(variable);
variable = 30;
```
Ответ `undefined 20 10`. тут все просто

### Question 4


```js
var variable = 10;
(()=>{
   console.log(variable);   // undefined
   variable = 20;
   console.log(variable);   // 20
})();

console.log(variable);
var variable = 30;
```

Ответ `10 20 20`. Внешня переменная переобределилась внутри анонимной ф-и

### Question 5


```js
var variable = 10;
(()=>{
   variable_3 = 35;
   console.log(variable_3); // 35
   var variable_3 = 45;
   variable_2 = 15;
   console.log(variable);   // 10
})();

console.log(variable_2); //15 
console.log(variable_3); //ReferenceError переменная не определена
var variable=30;
```

variable_2 эта переменная находится в глобальной области видимости, так была инициализированна без объявления переменной.

---

###### Citation

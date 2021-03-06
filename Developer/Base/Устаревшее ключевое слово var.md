---
aliases: null
date created: 2022-01-26 21:12
date updated: 2022-01-26 21:46
---

### «var» обрабатываются в начале запуска функции

Происходит хостинг.

Объявления переменных `var` обрабатываются в начале выполнения функции (или запуска скрипта, если переменная является глобальной).

Другими словами, переменные `var` считаются объявленными с самого начала исполнения функции вне зависимости от того, в каком месте функции реально находятся их объявления (при условии, что они не находятся во вложенной функции).

### Для «var» не существует блочной области видимости

Область видимости переменных `var` ограничивается либо функцией, либо, если переменная глобальная, то скриптом. Такие переменные доступны за пределами блока.

Переменная, объявленная через `let`, видна только в рамках блока `{...}`, в котором объявлена.

Это, в частности, влияет на объявления внутри `if`, `while` или `for`.

Переменная `var` – одна на все итерации цикла и видна даже после цикла:

```js
for(var i=0; i<10; i++) { /* … */ }

alert(i); // 10
```

С переменной `let` – всё по-другому.

Каждому повторению цикла соответствует своя независимая переменная `let`. Если внутри цикла есть вложенные объявления функций, то в замыкании каждой будет та переменная, которая была при соответствующей итерации

### «var» допускает повторное объявление

Если в блоке кода дважды объявить одну и ту же переменную `let`, будет ошибка
Используя `var`, можно переобъявлять переменную сколько угодно раз. Повторные `var` игнорируются

---

###### Citation

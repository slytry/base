---
aliases: null
date updated: 2022-01-22 17:02
---

JSON (JavaScript Object Notation) – это общий формат для представления значений и объектов. Файл представляет из себя набор свойств и ключей. Каждая такая пара должна быть в  двойных кавычках. Такая элементарная база данных.

Применяется для:

1. глубокое копирования объектов
2. передача информации на бэк энд
3. вывод данный об объекте

Мы не можем на прямую передавать объекты на бэк энд. Данный надо “подготовить”. Надо перевести их в строку. Можно было бы написать цикл, и для каждого вложенного объекта еще один цикл. К састью есть метод которые сам преобразовывает объект в строку.ю

### JSON.stringify

Метод `JSON.stringify` записывает все свойства объекта в строку и обертывает в двойные кавычки как надо.  Вложенные объекты поддерживаются и конвертируются автоматически.

Полученная строка `json` называется _JSON-форматированным_ или _сериализованным_ объектом. Мы можем отправить его по сети или поместить в обычное хранилище данных.

`JSON.stringify` может быть применён и к примитивам.

JSON поддерживает следующие типы данных:

- Объекты `{ ... }`
- Массивы `[ ... ]`
- Примитивы:
  - строки,
  - числа,
  - логические значения `true/false`,
  - `null`.

JSON является независимой от языка спецификацией для данных, поэтому `JSON.stringify` пропускает некоторые специфические свойства объектов JavaScript.

А именно:

- Свойства-функции (методы).
- Символьные свойства.
- Свойства, содержащие `undefined`.

Важное ограничение: не должно быть циклических ссылок. Это когда два объекта ссылаются друг на друга.

### Исключаем и преобразуем: replacer

```js
let json = JSON.stringify(value[, replacer, space])
```

**value** Значение для кодирования.

**replacer** Массив свойств для кодирования или функция соответствия `function(key, value)`.

**space** Дополнительное пространство (отступы), используемое для форматирования.

В большинстве случаев `JSON.stringify` используется только с первым аргументом. Но если нам нужно настроить процесс замены, например, отфильтровать циклические ссылки, то можно использовать второй аргумент `JSON.stringify`.

Если мы передадим ему массив свойств, будут закодированы только эти свойства.

Так как свойств может быть очень много, удобнее использовать ф-ю.
Функция будет вызываться для каждой пары `(key, value)`, и она должна возвращать заменённое значение, которое будет использоваться вместо исходного. Или `undefined`, чтобы пропустить значение.

```js
let room = {
  number: 23
};

let meetup = {
  title: "Conference",
  participants: [{name: "John"}, {name: "Alice"}],
  place: room // meetup ссылается на room
};

room.occupiedBy = meetup; // room ссылается на meetup

alert( JSON.stringify(meetup, function replacer(key, value) {
  alert(`${key}: ${value}`);
  return (key == 'occupiedBy') ? undefined : value;
}));
/* пары ключ:значение, которые приходят в replacer:
:             [object Object]
title:        Conference
participants: [object Object],[object Object]
0:            [object Object]
name:         John
1:            [object Object]
name:         Alice
place:        [object Object]
number:       23
*/
```

Функция `replacer` получает каждую пару ключ/значение, включая вложенные объекты и элементы массива. И она применяется рекурсивно. Значение `this` внутри `replacer` – это объект, который содержит текущее свойство.

Первый вызов – особенный. Ему передаётся специальный «объект-обёртка»: `{"": meetup}`. Другими словами, первая `(key, value)` пара имеет пустой ключ, а значением является целевой объект в общем. Вот почему первая строка из примера выше будет `":[object Object]"`.

Идея состоит в том, чтобы дать как можно больше возможностей `replacer` – у него есть возможность проанализировать и заменить/пропустить даже весь объект целиком, если это необходимо.

### Форматирование: space

Третий аргумент в `JSON.stringify(value, replacer, space)` – это количество пробелов, используемых для удобного форматирования (увеличивает отступы). Параметр `space` применяется для логирования и красивого вывода.

### Пользовательский «toJSON»

Как и `toString` для преобразования строк, объект может предоставлять метод `toJSON` для преобразования в JSON. `JSON.stringify` автоматически вызывает его, если он есть.

```js
let room = {
  number: 23
};

let meetup = {
  title: "Conference",
  date: new Date(Date.UTC(2017, 0, 1)),
  room
};

alert( JSON.stringify(meetup) );
/*
  {
    "title":"Conference",
    "date":"2017-01-01T00:00:00.000Z",  // (1)
    "room": {"number":23}               // (2)
  }
*/
```

`date` `(1)` стал строкой. Это потому, что все объекты типа `Date` имеют встроенный метод `toJSON`, который возвращает такую строку.

Добавим собственную реализацию метода `toJSON` в  объект `room` `(2)`:

```js
let room = {
  number: 23,
  toJSON() {
    return this.number;
  }
};

let meetup = {
  title: "Conference",
  room
};

alert( JSON.stringify(room) ); // 23

alert( JSON.stringify(meetup) );
/*
  {
    "title":"Conference",
    "room": 23
  }
*/
```

`toJSON` используется как при прямом вызове `JSON.stringify(room)`, так и когда `room` вложен в другой сериализуемый объект.

### JSON.parse

Чтобы декодировать JSON-строку, нам нужен другой метод с именем [JSON.parse](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse).

```js
let value = JSON.parse(str, [reviver]);
```

**str** JSON для преобразования в объект.

**reviver** Необязательная функция, которая будет вызываться для каждой пары `(ключ, значение)` и может преобразовывать значение.

JSON может быть настолько сложным, насколько это необходимо, объекты и массивы могут включать другие объекты и массивы. Но они должны быть в том же JSON-формате.

Вот типичные ошибки в написанном от руки JSON (иногда приходится писать его для отладки):

```json
let json = `{
  name: "John",                     // Ошибка: имя свойства без кавычек
  "surname": 'Smith',               // Ошибка: одинарные кавычки в значении (должны быть двойными)
  'isAdmin': false                  // Ошибка: одинарные кавычки в ключе (должны быть двойными)
  "birthday": new Date(2000, 2, 3), // Ошибка: не допускается конструктор "new", только значения.
  "friends": [0,1,2,3]                     // Здесь всё в порядке
}`;
```

Кроме того, JSON не поддерживает комментарии. Добавление комментария в JSON делает его недействительным.

Существует ещё один формат [JSON5](http://json5.org/), который поддерживает ключи без кавычек, комментарии и т.д. Но это самостоятельная библиотека, а не спецификация языка.

**Глубокая копия**
Вот так делается полная копия объекта через json.
`const clone = JSON.parce(JSON.stringify(obj)`

### Использование reviver
Для некоторых структур данных надо описать как их востанавливать.

```js
let str = '{"title":"Conference","date":"2017-11-30T12:00:00.000Z"}';

let meetup = JSON.parse(str);

alert( meetup.date.getDate() ); // Error!
```

 JSON.parce не различает объект Date, надо научить переводить в дату. 

```js
let str = '{"title":"Conference","date":"2017-11-30T12:00:00.000Z"}';

let meetup = JSON.parse(str, function(key, value) {
  if (key == 'date') return new Date(value);
  return value;
});

alert( meetup.date.getDate() ); // 30 - теперь работает!
```



---

###### Citation

<https://learn.javascript.ru/json#isklyuchaem-i-preobrazuem-replacer>

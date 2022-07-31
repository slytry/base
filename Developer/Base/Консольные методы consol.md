---
tags: 
aliases: null
date created: 2022-03-22 12:34
date updated:
date modified: Wednesday, July 20th 2022, 8:38:16 pm
---

# Консольные методы consol

Создает точку остановы

```js
dedugger
```

```js
consol.log()
```

Улучшенный вывод дом элементов. Выводыт как объект. Можно оборачивать в фигурные скобки, тогда будет объект со свойством

```js
consol.dir(div)
consol.dir({div})
```

Удобный вывод объектов, масивов особенно

```js
consol.table()
```

Проверка условия

```js
consol.assert(тело условия, что будет выводиться)
```

Вывод ошибки

Можно оборачивать в if будет как assert

```js
consol.error()
```

```js
consol.warn()
```

Скорость выпонения кода

```js
consol.time()

Код

consol.timeEnd()
```

---

###### Citation

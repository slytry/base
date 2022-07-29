---
tags: 
aliases: 
date created: Wednesday, July 20th 2022, 8:38:16 pm
date modified: Wednesday, July 20th 2022, 8:38:16 pm
---

# Fetch API

Воспользуемся фуйковым сервеом для работы [JSONPlaceholder](https://jsonplaceholder.typicode.com/)

Пример кода с этого сайта

```js
fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => response.json())
  .then(json => console.log(json))
```

1. просто пишем фетч и получаем гет запросна url
2. Есть JSON.parce но в fetch есть встроенный инструмент для преобразования оыщт в обхект. Просто .json.

### Другие запросы

Для того что бы делать не только GET, а еще POST или там PUT. Надо поднастроить fetch, передаем в аргумент не только url а еще и объект с настройками.

```js
fetch('https://jsonplaceholder.typicode.com/posts',{
method: "POST",
body: JSON.stringify({name: 'ivan'}) // сама посылка
headers: {
	'Content-type': 'appltcation/json' //заголовок, определили тип передаваемого сообщения
}
})
  .then(response => response.json())
  .then(json => console.log(json))
```

---

###### Related

---

###### Citation

https://javascript.info/fetch-apihttps://javascript.info/fetch-api

Date: 2021-11-12T11:42

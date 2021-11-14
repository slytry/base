Копирование создание нового объекта.
```js
const formData = new FormData(form);

	const object = {};
	formData.forEach(function(value, key){
			object[key] = value;
	});

postData('http://localhost:3000/requests', JSON.stringify(object))
```

- Тут мы создаем пакет данных с форм через new `FormData`
- Там объект, но этот объект нельзя преобразовать сразу в json. По этому мыкопируем его через forEach
- И потом при отправке преобразовываем в json `JSON.stringify(object)`

Более эллегантный способ.
```js
const formData = new FormData(form);

  const json = JSON.stringify(Object.fromEntries(formData.entries()));

		
postData('http://localhost:3000/requests', json)
			
```

По сути делаем тоже самое. Разбиваем объект потом пересобираем. Просто удобнее пишется.
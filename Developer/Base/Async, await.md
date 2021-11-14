---
tags: 
aliases: 
---
Написали fetch (асинхронный запрос без перезагрузки страницы), обернули его в функцию что бы управлять параметрами. Ретерним результат запроса. 
```
const postData = (url, data) => {
		const res = fetch(url, {
			method: 'POST',
			headers: {
					'Content-Type': 'application/json'
			},
			body: data
		});

		return res.json();
	};
```
 Запрос от сервера может итди долго, а ретерн сработает сразу. Будет ошибка. Для решения этой проблеммы есть `async/await`
 
 ### async
 Перед ф. пишем async  и все понимают что в этой ф. асинхронный код.
 А потом пише await перед тем кодом, который надо дождаться. Эти две команды используются только партно. И все, JS подождет ответа сервера.
 ```
const postData = async (url, data) => {
		const res = await fetch(url, {
			method: 'POST',
			headers: {
					'Content-Type': 'application/json'
			},
			body: data
		});

		return await res.json();
	};
```
 Второй await перед преобразованием json  в объект есть, потому что может быть очень много информации, и сколько она будет обрабатываться неизвестно.
 
---
###### Citation
https://javascript.info/async-await
Date: 2021-11-12T21:21

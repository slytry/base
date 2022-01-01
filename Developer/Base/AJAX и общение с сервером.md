---
tags: 
aliases: 
---
AJAX ("Asynchronous JavaScript and XML) - технология обновления только некоторых частей страницы, без перезагрузки всего документа. Дает красоту, удобство, экономоия трафика, скорость реакции интерфейса. 

AJAX варианты исполнения
- XMLHttpRequest

### XMLHttpRequest
Им уже не надо пользоваться. Устарел (пользуемся fetch)
```js
'use strict'

const inputRub =  document.querySelector('#rub'),
	inputUsd =  document.querySelector('#usd');
	inputRub.addEventListener('input', () => {
		const request = new XMLHttpRequest();
		
		request.open('GET', 'js/current.json');
		//request.open(method, url, async, login, pass);
		request.setRequestHeader('Content-type', 'application/json; charset=utf-8');
		request.send();
		request.addEventListener('load', () => {
		if (request.status === 200) {
			const data = JSON.parse(request.response);
			const calcd = (+inputRub.value / data.current.usd).toFixed(0);
			inputUsd.value = calcd;
		} else {
			inputUsd.value = 'не получится'
		}
		});			
	}); 
```
- method - как будем связываться с сервером. GET/POST два основных метода для HTTP
- url -  путь этого сервера
- async - значения да/нет. Ассинхронно будет работать или нет 
- login, pass - может мы хотим чтобы не для всех это рабтало

`setRequestHeader` — информация о том, что мы отправляем в XML запросе. Какая это информация, в чем она закодирована, и [так далее ](https://ru.wikipedia.org/wiki/%D0%97%D0%B0%D0%B3%D0%BE%D0%BB%D0%BE%D0%B2%D0%BA%D0%B8_HTTP). Это нужно для сервера, на основании этого он решает как ему поступить с запросом

В ответ нам приходят свойства
`status` - как прошла связь с сервером. Вот эти вот 404 и [так далее](https://ru.wikipedia.org/wiki/%D0%A1%D0%BF%D0%B8%D1%81%D0%BE%D0%BA_%D0%BA%D0%BE%D0%B4%D0%BE%D0%B2_%D1%81%D0%BE%D1%81%D1%82%D0%BE%D1%8F%D0%BD%D0%B8%D1%8F_HTTP). 200 - означает что все прошл успешно
`response` - само тело ответа, то что програмист бэкэндер подготовил для нас.
[`readyState`](https://developer.mozilla.org/ru/docs/Web/API/XMLHttpRequest/readyState) - в каком сотоянии находится наш запрос. Послднее состояние имеет код  4 и означает что ответ пришел.

У этого запрора есть события на которые можно повесить обработчики.
`readystatechange `- когда сменяется статут процессы запроса.
`load` - когда загрузился ответ



---
###### Related 
[[Формат JSON, метод toJSON Глубокая копия объекта]]

---
###### Citation

[XMLHttpRequest](https://developer.mozilla.org/ru/docs/Web/API/XMLHttpRequest)
[Использование XMLHttpRequest](https://developer.mozilla.org/ru/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest)
[Использование Объектов FormData](https://developer.mozilla.org/ru/docs/Web/API/FormData/Using_FormData_Objects)
[HOW TO CONVERT FORMDATA TO JSON OBJECT](https://ilikekillnerds.com/2017/09/convert-formdata-json-object/)
Date: 2021-11-10T16:24

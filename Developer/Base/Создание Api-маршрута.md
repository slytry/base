---
aliases: null
date created: 2022-02-16 12:07
date updated:
---

[API Routes](https://nextjs.org/docs/api-routes/introduction) позволяют создавать API endpoint внутри NextJs приложения. Для этого надо создать в папке pages новую папку api. Файлы в ней будут такого формата

```js
// req = HTTP incoming message, res = HTTP server response
export default function handler(req, res) {
  // ...
}
```

#### Создание просто API endpoint
```jsx
export default function handler(req, res) {
  res.status(200).json({ text: 'Hello' })
}
```

Теперь по <http://localhost:3000/api/hello > получим
![[Pasted image 20220216122231.png]]

- `req` is an instance of [http.IncomingMessage](https://nodejs.org/api/http.html#http_class_http_incomingmessage), plus some pre-built [middlewares](https://nextjs.org/docs/api-routes/api-middlewares).
- `res` is an instance of [http.ServerResponse](https://nodejs.org/api/http.html#http_class_http_serverresponse), plus some [helper functions](https://nextjs.org/docs/api-routes/response-helpers).


####

####


---

###### Citation


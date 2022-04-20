---
aliases: 
tags: 
date created: Tuesday, April 19th 2022, 12:54:27 pm
date modified: Tuesday, April 19th 2022, 12:54:56 pm
---

# useNavigate

Хук useNavigate возвращает функцию, которая позволяет программно перемещаться, например, после отправки формы.

```jsx
import { useNavigate } from "react-router-dom";

function SignupForm() {
  let navigate = useNavigate();

  async function handleSubmit(event) {
    event.preventDefault();
    await submitForm(event.target);
    navigate("../success", { replace: true });
  }

  return <form onSubmit={handleSubmit}>{/* ... */}</form>;
}
```

Функция навигации имеет две подписи: 
- Либо передайте значение To (того же типа, что и <Link to>) с необязательным вторым аргументом { replace, state }, либо 
- **Передайте дельту, которую вы хотите пройти в стеке истории. Например, навигация (-1) эквивалентна нажатию кнопки «Назад».


---

###### References

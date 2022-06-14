---
aliases: 
tags: 
date created: Monday, May 16th 2022, 12:03:59 pm
date modified: Monday, May 16th 2022, 3:42:49 pm
---

# §MOBX
**Pros**
- Меньше кода писать его легче. Так как нет редьюсеров диспатчей.
- MOBX реализует парадигму ООП, и все отсюда вытекающие совйста ООП. Например наследование


**Cons**
- Больше свободы по сравнению с редаксом. Не каждый програмист может написать хорошо на MOBX
- MOBX тяжело дебажить. Изменения неочевидны, так как реализуется паттерн наблюдатель. Dev tools не такой хороший
- Весит больше чем Redux 


- [[Концепция MOBX]]
- [[Root Store Pattern]]
- [[Связь с бэком на NEXT.JS]]

### Запросы на сервер

https://dev.to/ndrean/fetch-with-mobx-in-react-1omi
https://mono.software/2019/04/16/async-webapi-calls-using-react-with-mobx/

### Экосистема

**Основа**

[mobx-react-lite](https://github.com/mobxjs/mobx/tree/main/packages/mobx-react-lite) - облегченая связь с реактом (только функциональные компоненты)
[mobx-state-tree]()

**Окружение**

- [[Формы на MOBX]]

### ООП

- [[Как что писать в констукторе]]

### Примеры GITHUB

##### [Ivan V.](https://dev.to/ivandotv)

- [Mobx server side rendering with Next.js](https://github.com/ivandotv/mobx-nextjs-root-store)

---

###### References

- [10 minute interactive introduction to MobX and React](https://mobx.js.org/getting-started)
- [docs (Guided tour)](https://mobx.js.org/about-this-documentation.html#:~:text=6%20cheat%20sheet-,Guided%20tour,-To%20get%20an)
- [Практическое руководство по именованию классов, функций и переменных](https://habr.com/ru/post/558874/)

Яндекс Фронтенд [# 005. MobX: управление состоянием без боли – Азат Разетдинов](https://www.youtube.com/watch?v=9rZeCNLfeuk&t=59s&ab_channel=%D0%A4%D1%80%D0%BE%D0%BD%D1%82%D0%B5%D0%BD%D0%B4)

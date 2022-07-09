---
tags: 
aliases: null
date created: 2022-03-01 22:44
date modified: Friday, July 1st 2022, 6:38:07 pm
date modified: Friday, July 1st 2022, 6:38:07 pm
---

# Compound Components

Этот шаблон позволяет создавать выразительные и декларативные компоненты без излишнего пробрасывания ([prop drilling](https://kentcdodds.com/blog/prop-drilling) (англ.)). 

Применение этого шаблона стоит рассматривать, когда:

- требуется получить широко настраиваемый компонент с более четким разделением ответственности и понятным API.
- Хотим объединить несколько компонентов в одну логическую сущность
- Видим, что рендер становиться перегруженным условиями на основе пропсов - флагов

### Суть

Проектируем переиспоьзуемые компоненты так, чтобы была возможность передавать другие компоненты в children.
- У нас есть какая логика на уровне компоненты.
- Мы оборачиваем children в контекст провайдер

Минус: негибкость. Все пропсы одинакого распростанятся на все children компоненты

---

###### Citation

- [Compound Components In React](https://www.smashingmagazine.com/2021/08/compound-components-react/)
- [Александр Дунай — Улучшаем качество кода React-приложения с помощью Compound Components](https://www.youtube.com/watch?v=4BByJUk5x7M)
- [Улучшаем дизайн React приложения с помощью Compound components](https://habr.com/ru/company/alfa/blog/647013/)

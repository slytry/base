---
aliases: поиск react, поиск
tags: 
date created: Monday, June 27th 2022, 9:39:24 pm
date modified: Monday, June 27th 2022, 10:06:36 pm
---

# Debounce and Throttle in React

Для событий таких как:  window resize, scrolling, user typing into an input. Румно "смягчить" обработчики этих событий.

Если это не сделть есть вероятность получиться на пару секунд зависающее приложение. Техники Debounce и Throttle помогут в управление вызовами ф-и обработчиков.

## Debounce Throttle

Весто множественного вызовав ф-и. Ф-я будет вызвана один раз. Пакеты формируюется раз в определенный временной период.

## **Throttle**

Делат тоже самое с одной разницей, что есть одной гарантиированное срабатывает один раз в период. Например нам надо динамически подгрузать ajax запросом бесконечную страницу. Debounce будет вызван только когда пользователь прекратит скролить. Но нам надо подгружить новые посты не дожидаясь этого. С Throttle есть гарантия что мы будет регулярно проверять насколько далеко мы от дна

###  `immediate` instead of `leading`

У такой техники есть настройка. Можно ловить первое событие в все последущие за пероидо отбрасывать -  `immediate` (оно же leading). Либо `trailing` - срабатывает в конце периода

## Имплементация

https://github.com/lodash/lodash/blob/4.8.0-npm/throttle.js

## requestAnimationFrame (rAF)

---

###### References

- [Debouncing and Throttling Explained Through Examples](https://css-tricks.com/debouncing-throttling-explained-examples/)
- [How to Correctly Debounce and Throttle Callbacks in React](https://dmitripavlutin.com/react-throttle-debounce/#2-debouncing-a-callback-the-first-attempt)

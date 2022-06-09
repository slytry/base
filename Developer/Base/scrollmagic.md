---
aliases: 
tags: 
date created: Thursday, June 9th 2022, 1:07:32 pm
date modified: Thursday, June 9th 2022, 1:33:16 pm
---

# scrollmagic

Верстаешь всё последовательно. Создаёшь контроллер сцены и саму сцену. На сцену добавляешь события: связываешь триггер с нужной анимацией. Триггер - это селектор или элемент. Когда скролл доходит до элемента-триггера, библиотека производит необходимые трансформации. Вместо временной шкалы для анимации используется положение скролла относительно начала элемента. Сами анимации можно описывать с помощью [этой либы](https://greensock.com/gsap). Анимации применяются (обычно) к тому же элементу, хотя можно всё настроить. В анимациях указываешь как изменяются css-атрибуты. Ты можешь описывать либо начальное положение элемента (а конечное будет такое, как было бы согласно вёрстке без запуска этой библиотеки), либо конечное (начальное положение будет согласно вёрстке), либо и начальное и конечное.

## Cheatsheet

![[Pasted image 20220609132305.png]]

---

###### References

- [Дока](http://scrollmagic.io/docs/index.html)
- [ScrollMagic Examples](http://scrollmagic.io/examples/index.html)

Статьи

- [ScrollMagic инструкция – полноэкранное слайдшоу](http://www.creative-seo.ru/blog/plagin-scrollmagic-polnoekrannoe-slideshow/)

ihatetomatoes

1. [A Simple ScrollMagic Template](https://ihatetomatoes.net/5-days-with-scrollmagic/#scrollmagic-template-01) 
2. [A Simple One Page Template Using ScrollMagic](https://ihatetomatoes.net/a-simple-one-page-template-using-scrollmagic/)
3. [A Simple Parallax Template Using ScrollMagic And GreenSock](https://ihatetomatoes.net/a-simple-parallax-template-using-scrollmagic-and-greensock/)
4. [A Simple One Page Template With A Preloading Screen](https://ihatetomatoes.net/a-simple-one-page-template-with-a-preloading-screen/)
5. [A Simple ScrollMagic Template With Pinned Sections](https://ihatetomatoes.net/a-simple-scrollmagic-template-with-pinned-sections/)
6. [5 Days With ScrollMagic](https://ihatetomatoes.net/5-days-with-scrollmagic/)
7. [SVG Scrolling Animation Triggered By ScrollMagic]()

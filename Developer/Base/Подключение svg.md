---
tags: 
aliases: 
date created: Thursday, March 17th 2022, 9:36:45 am
date modified: Tuesday, June 21st 2022, 1:11:36 pm
---

# Подключение svg

#### Подключение извне:

- ``<img>``: для контентных картинок
- фон CSS: для оформительских картинок
- object/embed/iframe: для интерактивных svg

#### Встраивание внуть  HTML:

- инлайн ``<svg>`` в HTML: svg - часть DOM, полный контроль из CSS и JS
- инлайн в ``<img>``: для минимизация запросов к серверу [URL-encoder for SVG](https://yoksel.github.io/url-encoder/)
- инлайн в фон CSS: все картинки встроенны в css и кэшируются [URL-encoder for SVG](https://yoksel.github.io/url-encoder/)

### Спрайт

Для удобства все svg помещаеются в один файл и подключаеются с помощью тэга `<use>`, дабы не засорять html ([SVG спрайты](https://snipp.ru/html-css/svg-sprite), [SVG: группировка и переиспользование элементов](http://css.yoksel.ru/svg-groups-use/))

---

###### Citation

- [Используем SVG на сайте](https://habr.com/ru/post/260645/)
- [Как вставить](https://only-to-top.ru/blog/coding/2019-06-08-kak-vstavit-svg.html)
- [SVG в вебе Практическое руководство](https://svgontheweb.com/ru/)
- [Понимание viewbox (Scaling SVG Elements)](https://wattenberger.com/guide/scaling-svg)

Date: 2021-11-20T21:26

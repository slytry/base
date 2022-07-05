---
tags: 
aliases: 
date created: Friday, April 15th 2022, 9:23:24 am
date modified: Tuesday, July 5th 2022, 11:44:48 am
---

# Где использовать

### Шрифт

 [калькулятор](https://codesandbox.io/s/clamp-linear-intepolation-based-on-viewport-width-builder-xgkft?from-embed), который поможет вычислить правильные значения атрибутов clamp для шрифтов.

```css
div {  
// other CSS...  
font-size: clamp(1.1rem, 0.7153rem + 1.6368vw, 1.5rem);  
}
```

```css
.title {  
 font-size: clamp(16px, 5vw, 50px);
 //or
font-size: clamp(1.5rem, 5vw, 4rem);  
}
```

>**Warning**: Limiting how large text can get with `max()` or `clamp()` can cause a WCAG failure under [1.4.4 Resize text (AA)](https://www.w3.org/WAI/WCAG21/quickref/?showtechniques=144#resize-text) , because a user may be unable to scale the text to 200% of its original size. Be certain to [test the results with zoom](https://adrianroselli.com/2019/12/responsive-type-and-zoom.html).

То есть, вполне правильно использовать `vw` в качестве вычисляемого значения для размера шрифта. А именно, речь идёт о том, что это вызовет проблемы с доступностью в том случае, если пользователь изменит масштаб страницы в браузере.
этому лучше поступить так:  

```css
.title {
    font-size: clamp(16px, (1rem + 5vw), 50px);
}
```

### Ширина контейнера

Как создать подобный контейнер? Обычно в такой ситуации поступают примерно так:  
  ```css
.container {
    max-width: 780px;
    width: 80%;
}
```

  
Но использование функции `min()` позволяет ограничить максимальную ширину контейнера так:  
  ```css
.container {
    max-width: min(80%, 780px);
}
```

### Динамические внешние отступы и внутриние

 Установки минимального и максимального размера отступа между секциями.
 Установка границ в зависимости от[ ширины контейнера.](https://css-tricks.com/using-max-for-an-inner-element-max-width/)
 

```css
footer {
  --contentWidth: 400px;
  
  background: lightcoral;
  padding: 2rem max(2rem, 50vw - var(--contentWidth) / 2);
}
```

Еще вариант

```css
.section {
  padding: clamp(2rem, 10vmax, 10rem) 1rem;
}
```

 Еще

```css
h1, h2, h3, h4, h5 {
    margin: min(7vh, 2.75rem) 0 1.05rem;
}
```

[Вот](https://codepen.io/shadeed/pen/94dd79cb803a6b9bced68e4a5d35d537?editors=0100) рабочий пример

Благодаря использованию функции `min()` мы задаём максимальное значение отступа в `2.75rem`. Как видите, это очень просто и удобно.

### Границы и тени

В некоторых случаях в дизайне страниц используются элементы с широкими границами и с большими радиусами скругления углов. При выводе подобных элементов на мобильных экранах их границы нужно сделать меньше. То же самое касается и радиусов скругления углов. Использование функции `clamp()` позволяет динамически настраивать параметры границ, привязывая их к ширине области просмотра.

```
.element {
    box-shadow: 0 3px 10px 0 red;
    border: min(1vw, 10px) solid #468eef;
    border-radius: clamp(7px, 2vw, 20px);
    box-shadow: 0 3px clamp(5px, 4vw, 50px) 0 rgba(0, 0, 0, 0.2);
}
```

[Здесь](https://codepen.io/shadeed/pen/7b5c7979e09573ca32150ebfc7f74a66?editors=1100) можно поэкспериментировать с рабочим примером.

### Боковая панель и основная область страницы

расширить возможности боковой панели и сделать её более динамичной, сделать так, чтобы она, при достаточно большой области просмотра, занимала бы больше места

```css
.wrapper {
    display: flex;
}
aside {
  flex-basis: max(30vw, 150px);
}
main {
  flex-grow: 1;
}

```

 

### Декоративные заголовки

Ну во первых что это [такое и как сделать](https://codepen.io/shadeed/pen/e0128b73de7c84cb9b98cf733a3835c4?editors=1100)
Для формирования такого заголовка можно воспользоваться функцией `max()` с передачей ей значения, выраженного в единицах измерения `vw`. Это позволит сделать так, чтобы размер шрифта не был бы меньше заданного значения.

### Вывод плавных градиентов в разных областях просмотра

При настройке градиентов средствами CSS может понадобиться их динамическая настройка, направленная на то, чтобы сделать градиенты, выводимые на экранах мобильных устройств, более плавными.
Можем использовать CSS-функцию `min()`.  [Кодпен пример](https://codepen.io/shadeed/pen/2c4bf2ded32f66390fdef13409be4a10?editors=1100)
  

```css
.element {
    background: linear-gradient(135deg, #2c3e50, #2c3e50 min(20vw, 60%), #3498db);
}
```

### Полупрозрачный градиент

Когда нужно разместить текст поверх фотографии, то под него следует «подложить» градиент. Это позволит облегчить чтение текста. Так же, как и в предыдущем примере, параметры градиента должны зависеть от размеров области просмотра.

```css
.element {
    background: linear-gradient(to top, #000 0, transparent max(20%, 20vw));
}
```

### CSS Grid — адаптивная сетка

адаптивное расстояние между столбцами CSS grid для экранов мобильных устройств. С помощью clamp это довольно просто реализовать.

```css
.wrapper {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  grid-gap: clamp(1rem, 2vw, 24px);
}
```

 ### Резервные механизмы для браузеров, не поддерживающих min(), max() и clamp()
  
Как и в случае с любыми другими новыми возможностями CSS, применяя функции `min()`, `max()` и `clamp()`, нужно позаботиться о резервных механизмах. Для создания этих механизмов можно воспользоваться одним из следующих подходов.  
  

#### 1. Ручная настройка резервного механизма

Здесь под ручной настройкой понимается добавление в код свойства, пользующегося широкой поддержкой браузеров. Это свойство должно быть расположено перед свойством, в котором используются CSS-функции сравнения. Вот как это может выглядеть:  

```
.hero {
    padding: 4rem 1rem;
    padding: clamp(2rem, 10vmax, 10rem) 1rem;
}
```

Здесь браузеры, поддерживающие `clamp()`, проигнорируют первое выражение. А те, которые эту функцию не поддерживают, воспользуются первым способом настройки отступа.  
  

#### 2. Использование CSS-директивы [supports](https://habr.com/ru/users/supports/)

Директиву `@supports`, предназначенную для проверки поддержки браузерами различных технологий, можно использовать для выяснения того, умеет ли браузер работать с CSS-функциями сравнения. Я предпочитаю пользоваться этим решением, а не тем, ручным, которое описано в первом пункте. Дело в том, что любой браузер, поддерживающий функции сравнения, должен поддерживать и директиву `@supports`.  

```
.hero {
    /* Используется по умолчанию в браузерах, не поддерживающих min() */
    padding: 4rem 1rem;
}

@supports (width: min(10px, 5vw)) {
   /* Улучшение для браузеров, которые поддерживают min() */
  .hero {
    padding: clamp(2rem, 10vmax, 10rem) 1rem;
  }
}
```

---

###### References

Основы

- [Улучшаем адаптивность сайта с помощью CSS функции clamp()](https://tproger.ru/articles/uluchshaem-adaptivnost-sajta-s-pomoshhju-css-funkcii-clamp/) — перевод на русский с [CSS Clamp(): The Responsive Combination We’ve All Been Waiting For](https://blog.bitsrc.io/css-clamp-the-responsive-combination-weve-all-been-waiting-for-f1ce1981ea6e)
- [Три логические CSS-функции: min (), max () и clamp ()](https://xhtml.ru/2020/css/min-max-clamp/) перевод на русский с [min(), max(), and clamp(): three logical CSS functions to use today](https://web.dev/min-max-clamp/)

Много примеров использования, практически все отсюда

- [CSS-функции min(), max() и clamp()](https://habr.com/ru/company/ruvds/blog/501634/)

Гайд по работе со шрифтами

- [Linearly Scale font-size with CSS clamp() Based on the Viewport](https://css-tricks.com/linearly-scale-font-size-with-css-clamp-based-on-the-viewport/#for-those-who-dont-mind-that-edge-case)

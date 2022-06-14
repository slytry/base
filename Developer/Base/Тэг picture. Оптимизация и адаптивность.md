---
tags: 
aliases: 
date created: Friday, March 18th 2022, 8:19:42 pm
date modified: Monday, June 13th 2022, 10:35:22 am
---

# Тэг picture. Оптимизация и адаптивность

Изображения с высоким разрешением может долго загружаться при при мобильном интернете и на устройсвах с низким разрешением изображение может заргружаться сверху вниз.

### Тэг `picture`

Решает две проблеммы:
1. Смена разрешения — проблема передачи изображений меньшего размера для устройств с маленькими экранами.
2. Ориентация графики — проблема отображения различных изображений при разных размерах экрана.

##### Синтаксис

```html
<picture>
   <source
      srcset="small-car-image.jpg 400w,
              medium-car-image.jpg 800w,
              large-car-image.jpg 1200w"
      sizes="(min-width: 1280px) 1200px,
             (min-width: 768px) 400px,
             100vw">
   <img src="medium-car-image.jpg" alt="Car">
</picture>
```

Атрибут `srcset` может принимать несколько изображений с соответствующей шириной в пикселях, а браузер использует эти значения для выбора между указанными изображениями. Делает это на свою усмотренние, большн любит округлять в меньшую сторону.
Атрибут `sizes` задаёт пространство, которое изображение будет занимать на экране. В показанном выше примере изображение займёт до 1200px, если минимальная ширина экрана равна 1280px. Говорим браузеру какие картинки ему выбрать.

Так как в примере выше можно писать, но незачем. Современный img может тоже самое.

```html
<img srcset="small-car-image.jpg 400w,
             medium-car-image.jpg 800w,
             large-car-image.jpg 1200w"
     sizes="(min-width: 1280px) 1200px,
            (min-width: 768px) 400px,
            100vw"
     
     src="medium-car-image.jpg" alt="Car">
```

Мы сразу сообщаем браузеру какакие картинки у нас есть и какая у каждой ширина в тэге `srcset`. src тэг осталяем для поддержки сратых браузеров.  

Проблема: если уменьшать окно плавно то картинка не смениться. Нужно сразу заходит с устройсва с маленьким экраном. Этот метод создан для экономии трафика, а не для дизайнаж. Более того, картинка попадает в КЭШ. После перезагрузки страницы она не изменится уже. Если надо чтобы изображение менялось можно так.

```html
<picture>
  <source media="(min-width: 768px)" srcset="small-car-image.jpg">
  <source media="(min-width: 1280px)" srcset="large-car-image.jpg">
  <img src="car-image.jpg" alt="test image">
</picture>
```

##### Для чего реально пригодиться:

1. Если есть желание исползовать webp или другие современные форматы, но они работают не во всех брузерах.

```html
<picture>
  <source srcset="test.avif" type="image/avif">
  <source srcset="test.webp" type="image/webp">
  <img src="test.png" alt="test image">
</picture>
```

Указываем несколько источников для частично поддерживаемых форматов.
Во вкладке Rendering инструментов DevTools есть две новые эмуляции для эмулирования частично поддерживаемых типов изображений.

2. Если есть необходимость менять картинку не только в зависимости от ширины экрана, но и от других параметром, ориентации и так даллее.

Полная реализация ориентации графики и смены разрешения при помощи тега `picture`.

```html
<picture>
     
   <source media="(orientation: landscape)"
             
      srcset="land-small-car-image.jpg 200w,
              land-medium-car-image.jpg 600w,
              land-large-car-image.jpg 1000w"
             
      sizes="(min-width: 700px) 500px,
             (min-width: 600px) 400px,
             100vw">
     
   <source media="(orientation: portrait)"
             
      srcset="port-small-car-image.jpg 700w,
              port-medium-car-image.jpg 1200w,
              port-large-car-image.jpg 1600w"
             
      sizes="(min-width: 768px) 700px,
             (min-width: 1024px) 600px,
             500px">
     
   <img src="land-medium-car-image.jpg" alt="Car">
</picture>
```

В данном примере браузер будет отображать разные наборы изображений в зависимости от ориентации. В отличие от продвинутого img здесь добавляются полноценные медиа выражения для source.

3. Для ретина дисплеев
![[Pasted image 20211218143808.png]]

---

###### Citation

- [A Guide to the Responsive Images Syntax in HTML](https://css-tricks.com/a-guide-to-the-responsive-images-syntax-in-html/)

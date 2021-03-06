---
tags: 
aliases: 
---
**Общая картина иерархии свойств DOM объекта**
![[Pasted image 20211025101834.png]]
Свойства DOM объектов наследуются друг от друга.
<br />

### Свойство «nodeType»

`elem.nodeType` —  способ узнать «тип» DOM-узла (устаревший). Возвращает число, кажое число соответствует [виду узла](https://dom.spec.whatwg.org/#node)
В современных скриптах, чтобы узнать тип узла, мы можем использовать метод `instanceof`.
<br />

### Тег: nodeName и tagName
Получив DOM-узел, мы можем узнать имя его тега из свойств `nodeName` и `tagName`
-   Свойство `tagName` есть только у элементов `Element`.
-   Свойство `nodeName` определено для любых узлов `Node`:
    -   для элементов оно равно `tagName`.
    -   для остальных типов узлов (текст, комментарий и т.д.) оно содержит строку с типом узла.

<br />

### innerHTML: содержимое элемента
Свойство [innerHTML](https://w3c.github.io/DOM-Parsing/#widl-Element-innerHTML) позволяет получить HTML-содержимое элемента в виде строки. Мы также можем изменять его. Это один из самых мощных способов менять содержимое на странице.

 - `element.innerHTML` —  Добавляем в выбранный тег любой текст HTML 

>Скрипты не выполнятся
>Если `innerHTML` вставляет в документ тег `<script>` – он становится частью HTML, но не запускается.

Мы можем использовать конструкцию `innerHTML+=` для дополнения HTML, но фактически осуществляется перезапись.
Другими словами, `innerHTML+=` делает следующее:

1.  Старое содержимое удаляется.
2.  На его место становится новое значение `innerHTML` (с добавленной строкой).

**Так как содержимое «обнуляется» и переписывается заново, все изображения и другие ресурсы будут перезагружены**
Если существующий текст выделен мышкой, то при переписывании `innerHTML` большинство браузеров снимут выделение. А если это поле ввода `<input>` с текстом, введённым пользователем, то текст будет удалён. Есть и другие способы добавить содержимое, об этом позже.

<br />

### outerHTML: HTML элемента целиком
Свойство `outerHTML` содержит HTML элемента целиком. Это как `innerHTML` плюс сам элемент.

Это потому, что использование `outerHTML` не изменяет DOM-элемент, а удаляет его из внешнего контекста и вставляет вместо него новый HTML-код.

>Будьте осторожны: в отличие от `innerHTML`, запись в `outerHTML` не изменяет элемент. Вместо этого элемент заменяется целиком во внешнем контексте.

То есть, при `div.outerHTML=...` произошло следующее:

-   `div` был удалён из документа.
-   Вместо него был вставлен другой HTML `<p>Новый элемент</p>`.
-   В `div` осталось старое значение. Новый HTML не сохранён ни в какой переменной.

Здесь легко сделать ошибку: заменить `div.outerHTML`, а потом продолжить работать с `div`, как будто там новое содержимое. Но это не так. Подобное верно для `innerHTML`, но не для `outerHTML`.

Мы можем писать в `elem.outerHTML`, но надо иметь в виду, что это не меняет элемент, в который мы пишем. Вместо этого создаётся новый HTML на его месте. Мы можем получить ссылки на новые элементы, обратившись к DOM.
<br />

### nodeValue/data: содержимое текстового узла
Свойство `innerHTML` есть только у узлов-элементов.

У других типов узлов, в частности, у текстовых, есть свои аналоги: свойства `nodeValue` и `data`. Эти свойства очень похожи при использовании, есть лишь небольшие различия в спецификации. Мы будем использовать `data`, потому что оно короче.

<br />

### textContent: просто текст

 `textContent`  — предоставляет доступ к _тексту_ внутри элемента за вычетом всех `<тегов>`, как если бы все `<теги>` были вырезаны, но текст в них остался. На практике редко появляется необходимость читать текст таким образом.

>Намного полезнее возможность записывать текст в `textContent`, т.к. позволяет писать текст «безопасным способом».

### Свойство «hidden»
Атрибут и DOM-свойство «hidden» указывает на то, видим ли мы элемент или нет. Технически, `hidden` работает так же, как `style="display:none"`

---
###### Related 
---
###### Citation
Date: 12:08 12:08

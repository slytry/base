---
aliases: null
date created: 2022-03-19 11:52
date updated:
---
 
Добавление стилей. По умолчание стили будут добавлениы в тэг style в тэге head  в html. Можно задать атрибут inline="inline" и такие стили будут инлайн.

> Из одного компонента получиться несколько вложенных тэгов. Для лучшей отзывчивости стили будут применены на максимально внешные элеметы. При желании можно посмотреть сгенерированный html  и скоректировать селекторы
 
 
```html
<mjml>
  <mj-head>
    <mj-attributes>
      <mj-class name="mjclass" color="green" font-size="30px" />
    </mj-attributes>
    <mj-style inline="inline">
      .blue-text div {
        color: blue !important;
      }
    </mj-style>
    <mj-style>
      .red-text div {
        color: red !important;
        text-decoration: underline !important;
      }
    </mj-style>
  </mj-head>
  <mj-body>
    <mj-section>
      <mj-column>
        <mj-text css-class="red-text">I'm red and underlined</mj-text>
        <mj-text css-class="blue-text">I'm blue because of inline</mj-text>
        <mj-text mj-class="mjclass">I'm green</mj-text>
      </mj-column>
    </mj-section>
  </mj-body>
</mjml>
```

---

###### Citation


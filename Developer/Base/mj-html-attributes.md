---
aliases: null
date created: 2022-03-19 11:46
date updated:
---
Один компонент mjml оказывается набором вложенный тэгом, обращение к которым оказывается невозможным из mjml разметки.
`mj-html-attributes` вместе с `mj-selector`  позволяет создавать атрибуты для генерируемых тэгов.
Что бы этим пользоваться надо сгенерировать html  и посмотреть на разметку чтобы понять где нам нужно добавлять атрибуты.
Для большинства писем этого не потребуется.


```
<mjml>
  <mj-head>
    <mj-html-attributes>
      <mj-selector path=".custom div">
        <mj-html-attribute name="data-id">42</mj-html-attribute>
      </mj-selector>
    </mj-html-attributes>
  </mj-head>
  <mj-body>
    <mj-section>
      <mj-column>
        <mj-text css-class="custom">
          Hello World!
        </mj-text>
      </mj-column>
    </mj-section>
  </mj-body>
</mjml
```

---

###### Citation


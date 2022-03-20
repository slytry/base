---
aliases: null
date created: 2022-03-19 11:34
date updated:
---
В этом тэге можно:
1. переопределять дефолтные css свойства для компонентов
2. Задавть глабальные стили в `mj-all`
3. Создавать кастомные классы со стилями `mj-class` 

```html
<mjml>
  <mj-head>
    <mj-attributes>
      <mj-text padding="0" />
      <mj-class name="blue" color="blue" />
      <mj-class name="big" font-size="20px" />
      <mj-all font-family="Arial" />
    </mj-attributes>
  </mj-head>
  <mj-body>
    <mj-section>
      <mj-column>
        <mj-text mj-class="blue big">
          Hello World!
        </mj-text>
      </mj-column>
    </mj-section>
  </mj-body>
</mjml>
```

---

###### Citation


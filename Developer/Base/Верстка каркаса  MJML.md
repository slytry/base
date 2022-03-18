---
aliases: null
date created: 2022-03-17 10:41
date updated:
---

Структура начинается с тэга mjml 

Внутри тэг mj-head и mj-body аналогично обычной структуре

Страницу делим на section ( `<mj-section>`) и внури могут быть колонки (`<mj-column>`). 
Даже если не нужны колонки должна быть хотябы одна колонка, на этом завязан адаптив.

```html
<mjml>
  <mj-body>
    <mj-section>
      <mj-column>
        <mj-image width="100px" src="https://mjml.io/assets/img/logo-small.png"></mj-image>
        <mj-divider border-color="#F45E43"></mj-divider>
        <mj-text font-size="20px" color="#F45E43" font-family="helvetica">Hello World</mj-text>
      </mj-column>
    </mj-section>
  </mj-body>
</mjml>
```


---

###### Citation


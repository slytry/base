---
aliases: null
date created: 2022-03-19 11:20
date updated:
---

Позволяет вставлять куски mjml. Делать шаблонизацию

```
<!-- header.mjml -->
<mj-section>
  <mj-column>
    <mj-text>This is a header</mj-text>
  </mj-column>
</mj-section>
```

Внутри `mj-body` можно вставлять куски кода

```
<!-- main.mjml -->
<mjml>
  <mj-body>
    <mj-include path="./header.mjml" />
  </mj-body>
</mjml>
```


### Вставка css
Можно вставлят сторонний css. Он будет добавлен так же, как он был бы написал в `mj-style`. То есть окажется в  `<head> => <style>`

Надо указать атрибут `type="css"`. Можно вставить этот css inline, надо указать дополнительный атрибут `css-inline="inline"`

```
<!-- main.mjml -->
  <mj-include path="./styles.css" type="css" />
  <mj-include path="./inline-styles.css" type="css" css-inline="inline" />
```

### Вставка HTML
Можно вставлять html файлы. Они будут вставленны так же как бы их вставил тэг `mj-raw`
Атрибут - `type="html"`.


---

###### Citation


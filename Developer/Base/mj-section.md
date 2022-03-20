---
aliases: null
date created: 2022-03-19 13:11
date updated:
---

Структурный компонент. По умаолчанию имеет 600px  ширину, но с помощью `full-width="full-width"`   измениться на 100%

Можно менять порядок вложеных стобцов 

![[Pasted image 20220319132214.png]]

Так как фреймвор mobile first сначало располагаем как будет на мобилке, а этим свойством меняет отображение на desktop'е

В outlook  background-images вдет себя по особенному:
Если размер изображение не указан - свойство no-repeat будет проигнорированно. Если размер задан один атрибутов в проентах, то высота будет  посчитана автоматически. В outlook изображение никогда не будет переполнять родителя, и оно будет не обрезано а уменьшено



```html
<mjml>
  <mj-body>
    <mj-section full-width="full-width" background-color="red">
      <!-- Your columns go here -->
    </mj-section>
  </mj-body>
</mjml>
```

---

###### Citation

[Полный список дифолтных настроек (дока)](https://documentation.mjml.io/#mj-section)

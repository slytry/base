---
tags: 
aliases: 
---
##### Вместо `text-align`, для выравнивания текста лучше использовать `flexbox`
- В некоторых языках, которые пишутся справа налево или вертикально, свойства `left` и `right` могут работать некорректно
- В случае с `justify` проблемы могут возникнуть с языками, где есть орграфы
- Также он может доставить неудобства [людям с дислексией](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align#Accessibility_concerns).
### Text align
```css
/* Keyword values */
text-align: start;
text-align: end;
text-align: left;
text-align: right;
text-align: center;
text-align: justify;
text-align: justify-all;
text-align: match-parent;
```

---
###### Citation
[text-align](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align#accessibility_concerns)
Date: 2021-11-23T15:00

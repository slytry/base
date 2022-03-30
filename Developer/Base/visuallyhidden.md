---
tags: atomCSS
aliases: скрыть спрятать hide 
date created: 2022-03-29 13:05
date modified: Tuesday, March 29th 2022, 1:06:38 pm
title: visuallyhidden
---

# visuallyhidden

```css
.visuallyhidden:not(:focus):not(:active) {
  position: absolute;

  width: 1px;
  height: 1px;
  margin: -1px;
  border: 0;
  padding: 0;

  white-space: nowrap;

  clip-path: inset(100%);
  clip: rect(0 0 0 0);
  overflow: hidden;
}
```

---

###### Citation

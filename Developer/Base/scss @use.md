---
aliases: null
date created: 2022-02-17 09:37
date updated:
---
# @use
Позволяет использовать подгружать scss модули.

Например модуль с кодом. Нижнее подчеркивание (unerscore) означает что это файл не должен будет скомпилироваться в отдельный файл. Он всегда будет использоваться как часть другого.

```scss
//_mixins.scss

@mixin clickZone($sizeZone: 10px) {
  position: relative;

  &::before {
    position: absolute;
    top: ($sizeZone * -1);
    right: ($sizeZone * -1);
    bottom: ($sizeZone * -1);
    left: ($sizeZone * -1);

    content: '';
    cursor: pointer;
  }
}


```

Чтобы использовать этот модуль с миксином надо к нему обратиться. Это можно сделать несколькими способаими
**Способ 1**
Можно обратиться по имени модуля. Это просто имя конечного файла. В данном случае mixins

```scss
//common.scss
@use './modules/mixins' 

.elem {
@include mixins.clickZone(15px)
}

```

**Способ 2** и 3
Можно подключить сразу все и обращаться только по имена миксина, но это не рекомендуется так как может возникнуть конфликт имен.
Или задать собственное имя модулю

```scss
//common.scss
@use './modules/mixins' as *;

.elem {
@include clickZone(15px)
}


//common.scss
@use './modules/mixins' as m

.elem {
@include m.clickZone(15px)
}



```


---

###### Citation


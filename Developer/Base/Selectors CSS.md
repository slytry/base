---
tags: 
aliases: 
---
# Special selectors
| Селектор          | к Кому                              |
| ----------------- | ----------------------------------- |
| `:not(:last-child)` | Ко всем элементам кроме последнего  |
| `:nth-child($)  `   | К элументу по очереди под номером $ |
|                   |                                     |

# Selectors
Структура правила CSS

```css
селектор {
  свойство: значение;
  свойство: значение;
}
```

Селектором может быть отдельный тег и тогда все **теги** автоматически пробретут свойства правила, но можно создать класс и руками приписывать его только в нужный тегах.

У одного элемента может быть бесконечное количество классов. Перечисляются они все в атрибуте **class** через пробел.


| Syntax | Definition   | Features                                                                                                                                                           |
| ------ | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `#`    | id           | Unique name for element                                                                                                                                            |
| `.`    | class        | Name for unlimited amount of element                                                                                                                               |
| `:`    | Pseudo-class | State for &lta&gt: link, visited, hover, focus, active <br> The active state occurs when the user first clicks on a link <br> Focus when we use Tab for navigation |
|        |              |                                                                                                                                                                    |



---

###### Related %% ссылки на другие заметки%%
###### Citation %% ссылка на источник%%
 Head First HTML and CSS Elisabeth Robson Eric Freeman

Date: 07-06-2021 07:12%% дата создания заметки%%


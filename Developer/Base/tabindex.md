---
tags: 
aliases: 
---
`tabindex` — универсальный атрибут. Принимает цифры от 1 и до ... устанавливает порядок получения фокуса при переходе между элементами с помощью клавиши Tab. *Максимальное значение не должно превышать 32767.*
В реальной жизни лучше не менять порядок. 
Если добавить не интерактивному элементу значение 0, то на него станет возможно перейти через tab. (по умолчанию только у интерактивных элементов есть такая возможность)
Значение -1 позволяет сфокусировать через скрипт или мышкой, но через таб не позволяет. Можно поставить туда фокус мышкой и уйти табом,  но обратно вернуться не получится.


---
###### Citation
Date: 2021-11-28T11:37

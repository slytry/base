---
tags: 
aliases: DOM
---
## Object model
DOM — document object model. Представления элементов HTML как объекты в JS, которые он может изменять. Все на странице является объектом. Невидимые знаки переноса строки или пробела, коментарии и др. также являеются частью DOM и будут видны в JS. Каждый объект в DOM  можно назвать узлом (node), тэги HTML можно называть еще и элементами.

DOM  не единственная объектная модель. Есть CSSOM — предосталяет функционал для изменения CSS свойств. Но в проектах редко использутся, обычно просто меняют готовые классы.

Есть BOM (Browser Object Model) — модель для работы со всей остальной средой кроме документа. В частности для браузера, но можно .  Например, функции `alert/confirm/prompt` - это часть BOM.
Некоторые объекты BOM:
 -  `navigator.userAgent` – about the current browser
  -  `navigator.platform` – about the platform (can help to differ between Windows/Linux/Mac etc).
 - `llocation.href` — shows current URL

---
###### Related 
---
###### Citation
Date: 19:24 19:24

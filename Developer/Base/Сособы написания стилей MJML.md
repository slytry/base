---
aliases: null
date created: 2022-03-19 13:47
date updated:
---

? Не понятна поддержка scss. Скорей всего ее нет. Но можно самому ее сделат при необходимости

1. Писать инлайн в компонентах стили нельзя
2. Каждый компонент mjml имеет набор атрибутов для стилизации
3. В mj-attribute можно переопределять дефолтные стили и создавать кастомные классы
4. В антибуте css-class писать селектор и стилизовать внутри mj-style. Можно смотреть на сгенерированный html и писать более сложные селекторы.  
5. Можно писать стили в отдельном файле и добавлять их через mj-include
---

###### Citation


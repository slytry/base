---
tags: 
aliases: 
date created: Thursday, March 17th 2022, 9:36:45 am
date modified: Monday, May 16th 2022, 11:52:35 am
---

# EditorConfig

### Что это

Файл настройки среды разработки. Редакторы кода(IDE) принимают эти настройки.
Файлик кофигурации распростроняется между разрабтчиками и так достигается одинаковость кода.

Некоторые программы понимают такой файл нативно, а для некоторых нужнен плагин. Список с поддержкой смотреть на оф сайте

### Правила

editorconfig поддерживает минимайльный набор правил, представленый внизу

некоторые среды разработки могут поддерживать больше свойст, но там где они не поддерживаются они будут просто проигнорированный
правила можно настравивать под конкретные разширения файлов

```editorconfig

// Все базово поддерживаемые свойства

root = true //говорит что файлы буду искаться в дирректории файла и нижу

[*]
charset = utf-8
indent_style = tab
indent_size = 4
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true`

[{*.json,*.yml,*.toml}]
indent_size = 2




```

**Поддержка свойст в VS code**

Эти свйоства поддерживает расширение для VS code

```editorconfig

indent_style`
indent_size`
tab_width`
end_of_line` (on save)
insert_final_newline` (on save)
trim_trailing_whitespace` (on save)

```

---

###### Citation

[EditorConfig Site](https://editorconfig.org)

[Памятка про .editorconfig](http://glivera-team.github.io/tips/2016/02/08/editorconfig.html)

[Расширения для VS code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)

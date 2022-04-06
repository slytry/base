---
aliases: 
tags: 
date created: Wednesday, April 6th 2022, 12:11:02 pm
date modified: Wednesday, April 6th 2022, 12:13:35 pm
title: git bisect
---

# git bisect

Поволяет пропускать не важные коммиты

- Изменение форматирован (adding/removing spaces/empty lines, indentation)
- пропустил запятую
- удаление комментарий

Коммиты без изменения логики можно игнорировать

```
git bisect skip $(git rev-list --grep irrelevant <good place> HEAD)
```

---

###### Citation

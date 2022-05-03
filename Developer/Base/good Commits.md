---
aliases: 
tags: 
date created: Thursday, April 21st 2022, 8:53:05 pm
date modified: Thursday, April 21st 2022, 10:36:38 pm
---

# Почему надо использовать?

---

- Упростит людям участие в проектах, позволив им изучить более структурированную историю коммитов

---

- Можно создавать changelog/release notes автоматически

---

- наличие типов заставляет думать об атомарности коммитов

---

- автоматическое определение семантического повышения версии

---

Структура

```js
<type>(<optional scope>): <subject>
empty separator line
<optional body>
empty separator line
<optional footer>
```

---

# Types

---

- API relevant changes
	- `feat` Commits, that adds a new feature
	- `fix` Commits, that fixes a bug

---

- `refactor` Commits, that rewrite/restructure your code, however does not change any behaviour
	- `perf` Commits are special `refactor` commits, that improve performance

---

- `style` Commits, that do not affect the meaning (white-space, formatting, missing semi-colons, etc)

---
- `test` Commits, that add missing tests or correcting existing tests

---
- `docs` Commits, that affect documentation only

---
- `build` Commits, that affect build components like build tool, ci pipeline, dependencies, project version, …

---

- `ops`/`ci` Commits, that affect operational components like infrastructure, deployment, backup, recovery, …

---

# ?

- `chore` Miscellaneous commits e.g. modifying `.gitignore`

---

После типов вставить
![[Pasted image 20220421205200.png]]

---

# Scope

---

1.



---
tags: 
aliases: null
date created: 2022-03-09 10:28
date modified: Thursday, March 31st 2022, 3:54:40 pm

title: path aliases next js
---

# path aliases next js

В файле `tsconfig.json` и`jsconfig.json` можно настраивать пути

По умолчание next понимает опции `paths` и `baseUrl`.

### Опция baseUrl

Такая настройка позволит обращаться из корня проекта

```json
{
  "compilerOptions": {
    "baseUrl": "."
  }
}
```

```json

{
  "compilerOptions": {
    "baseUrl": "./",
    "paths": {
      "@/*": ["./src/*"]
    },
    "allowJs": true
  }
}
```

### Опция paths

Можно настриивать более сложные пути

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/components/*": ["components/*"]
    }
  }
}
```

---

###### Citation

 <https://nextjs.org/docs/advanced-features/module-path-aliases>

---
aliases: 
tags: 
date created: Thursday, July 28th 2022, 11:09:45 am
date modified: Thursday, July 28th 2022, 11:28:51 am
---

# Models

## Литеральный тип

*see  [source](https://mobx-state-tree.js.org/overview/types#:~:text=types.literal(value))*

```js


const Person = types.model({
    name: types.string,
    gender: types.union(types.literal('male'), types.literal('female'))
})
```

---

###### References

- [Types overview](https://mobx-state-tree.js.org/overview/types)

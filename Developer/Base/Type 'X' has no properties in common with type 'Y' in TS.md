---
aliases: 
tags: 
date created: Wednesday, July 20th 2022, 10:47:26 am
date modified: Wednesday, July 20th 2022, 10:49:01 am
---

# Type 'X' has no properties in common with type 'Y' in TS

Ошибка «Type 'X' has no properties in common with type 'Y' in TS» возникает, когда мы пытаемся присвоить что-либо слабому типу ([weak type detection](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-4.html#weak-type-detection)),  и ни одно свойство не пересекается свойства не пересекаются. Чтобы устранить ошибку, объявите любые перекрывающиеся свойства, если они существуют, или используйте утверждение типа (type assertion).

---

###### References

- [Type 'X' has no properties in common with type 'Y' in TS](https://bobbyhadz.com/blog/typescript-type-has-no-properties-in-common-with-type)

---
aliases: 
tags: 
date created: Friday, May 20th 2022, 2:01:16 pm
date modified: Friday, May 20th 2022, 2:23:04 pm
---

# Зачем нужный Generic

## Определение

**Дженерик** - параметризованный тип, позволяющий обявлять параметры типа, являющийся временной заменой конкретный мнолотных типов (констант), опредление которых будет выполнено в момент исползования.

Дженерики нужны для возможности переиспользования типов.
Если есть  несколко интерфейсов отличающихся одним типом (как ниже)

```ts
interface UserState {
loading: boolean;
error: Error | null;
data: User;
}

interface MessageState {
loading: boolean;
error: Error | null;
data: Message;
}

```

Удобно создать джинерик, что бы не повторяться (DRY)


---

###### References

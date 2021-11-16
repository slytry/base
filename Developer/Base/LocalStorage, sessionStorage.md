---
tags: 
aliases: 
---
### Храненние данный до 4мб в браузере.

Объекты веб-хранилища localStorage и sessionStorage позволяют сохранять пары ключ / значение в браузере.
- Данные распровстроаняются на все страницы из одного источника
- sessionStorage сохраняется при перезагрузке страницы. Используется реже, так как имеет ряд ограничений.
- localStorage сохраняется при перезагрузке брвузера, всего компа
- Данный храняться в строках. Все другие типы будет приведены.
- На изменения состояни хранилища можно повесить обработчик. (Есть услоовия когда он может не запуститсья.)
- Можно записать целый объект, но только через JSON.stringify

**Методы и свойства:**
-   `setItem(key, value)` – store key/value pair.
-   `getItem(key)` – get the value by key.
-   `removeItem(key)` – remove the key with its value.
-   `clear()` – delete everything.
-   `key(index)` – get the key on a given position.
-   `length` – the number of stored items.
-   Use `Object.keys` to get all keys.

---
###### Citation
https://tproger.ru/articles/localstorage/
https://javascript.info/localstorage
http://dev-test.nemikor.com/web-storage/support-test/
Date: 2021-11-14T08:16

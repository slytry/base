---
tags: 
aliases: 
---

1.  Чтобы удалить модуль1 **без** изменения package.json:
    
    `npm uninstall module1`
    
2.  Чтобы удалить module1 **с** изменением package.json и удалить его из зависимостей в package.json:
    
    `npm uninstall --save module1`
    

Примечание: чтобы упростить вышеупомянутые команды, вы можете использовать **-S** вместо **--save** , а также использовать **remove** , **rm** , **r** , **un** , **unlink** вместо **uninstall**

---
###### Citation
Date: 2021-12-24T09:34

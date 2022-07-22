---
tags: 
aliases: null
date created: 2022-03-01 18:05
date updated:
date modified: Friday, July 22nd 2022, 2:01:27 pm
---

# useLayoutEffect

Имеет тонкое отличие от useEffect во времени срабатывания эффекта.
В редких случаях нам надо чтобы эффект применился еще до отрисовки экрана и тогда нужен useLayoutEffect. Например что бы не было мерцание кого-то цвета (если мы меняем цвет).

Этот процесс бокирует отрисовку до выяснения обстоятельств.

Можно использовать для ожидания пользовательского ввода

![[Pasted image 20220301180747.png]]

---

###### Citation

- [Когда использовать](https://stackoverflow.com/questions/57005663/when-to-use-useimperativehandle-uselayouteffect-and-usedebugvalue)

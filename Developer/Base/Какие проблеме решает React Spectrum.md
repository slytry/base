---
aliases: 
tags: 
date created: Wednesday, July 20th 2022, 7:11:14 pm
date modified: Wednesday, July 20th 2022, 8:39:14 pm
---

# Какие проблеме решает React Spectrum

Компаниям или большим проекта нужны собственные ui-kit'ы. Каждый раз приходиться реализовывать все компоненты с нуля.
Хороший компонент обладает полная поддержкой:  доступности, интернационализацию, клавиатуры, мыши и сенсорного взаимодействия и другие фичи. Даже с наличием современных библиотек отображения это все еще чрезвычайно с ложная задача.

Так же нужно держать в голове что компонент может быть использован в веб,  react-native или любой другой платформе.

Хотя каждая дизайн-система уникальна, между компонентами зачастую больше общего, чем различий. Существуют даже спецификации, описывающие, как многие из наиболее распространенных компонентов должны вести себя с точки зрения семантики доступности и взаимодействия с клавиатурой ([accessibility semantics](https://www.w3.org/TR/wai-aria-1.2/) and [keyboard interactions](https://www.w3.org/TR/wai-aria-practices-1.2/)). Основное различие между дизайн-системами заключается в стилевом оформлении.

Это открывает возможность совместного использования большей части поведения и логики компонентов между дизайн-системами и платформами.

 Таким образом библитека разделена на несколько логических блоков. –  [[Аритектура ui-kit здорового человека|читать дальше]]

---

###### References

> Текст сверху взят из вступления с разделу [архитектуры](https://react-spectrum.adobe.com/react-aria/why.html). Есть продолжение – [Why React Aria?](https://react-spectrum.adobe.com/react-aria/why.html)

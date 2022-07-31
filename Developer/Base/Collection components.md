---
aliases: 
tags: 
date created: Thursday, July 21st 2022, 10:03:55 am
date modified: Thursday, July 21st 2022, 10:04:03 am
---

# Collection components

Многие компоненты отображают внутри наборы элементов. Например:  lists, menus, selects, tables, trees, and grids. Такие коллекции обычно должны уметь навигироваться с клавиатуры и у многих есть какая-то форма отбора. Так же коллекции могут иметь асинхронную загрузку,  обновляться со временем или иметь ??виртуальный скролл??

Существует множество способов разработки API для таких компонентов: JSX children, a list of option objects, or a datasource object. Выбор и другие состояния, такие как отключено, могут быть переданы каждому элементу или в качестве реквизита верхнего уровня. Каждый из способов имеет различные компромиссы. На этой странице описывается, как мы это делаем в React Spectrum, и подробно рассматриваются некоторые из этих компромиссов.

## Design goals

Наша основная цель заключалась в том, чтобы предоставить согласованный API для многих типов компонентов коллекций, который был бы прост в освоении, эффективен для больших коллекций и расширяем для расширенных функций. Вот некоторые из вариантов использования, которые мы рассмотрели:

-  Static data
-  Dynamic data
-  Async loading
-  Sections/groups of data from a single source
-  Sections from different sources
-  Single and multiple selection (controlled and uncontrolled)
-  Controlled and uncontrolled expanded states for components like trees and accordions
-  Marking items as selected, expanded, disabled, etc. prior to loading them from a server
-  Drag and drop of items
-  Virtualization for large collections
-  Infinite scrolling to load more items on demand

---

###### References

-[Collection components](https://react-spectrum.adobe.com/react-stately/collections.html)

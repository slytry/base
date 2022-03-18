---
aliases: null
date created: 2022-03-05 10:13
date updated:
---

SOLID - акроним для 5-ти основных принципов объектно ориентированного программирования 
-   Single responsibility — принцип единственной ответственности
-   Open-closed — принцип открытости / закрытости
-   Liskov substitution — принцип подстановки Барбары Лисков
-   Interface segregation — принцип разделения интерфейса
-   Dependency inversion — принцип инверсии зависимостей

### Single responsibility (SPR)
1 класс = 1 задача
1 сущность = 1 задача (Functional Programming)

Это принцип про декомпозицию

Не должно быть классов или компонентов которые одновременно и логируют что-то и отправляют данные
Когда наша сущность разрастается мы получаем много связанного кода.  Если что-то сломается, она потянет за собой и другое
Ухудшается читабельность такого кода
Банально когда много разрабочик правят один файл, в git бывает много кофилктов

Пример делаения классов:
1. Есть Основной класс
2. Делаем класс для работы с БД, называем Repository
3. Если нам нужно отправлять запросы HttpSender
4. Если нам надо логирование, делаем класс Logger, если вывод Printer

И если приходить задача поправить что-то мы не копаемя в одном огромном классе, а сразу идем в нежный класс (файл)

Так же данное деление позволило отделить модель данных в Основном классе, а поведение (контроллер) держим отдельно

### Open-closed (OCP)
Программные сущности должны бить открыты для расширения, но закрыты для изменения

Изменять работающий, существуеющий код плохо. Он протестирован, работает, и не ясно что будет если его изменить. 

Если код меняет, то необходимо выполнять регрессионное тестирование - убеждаться что старый функционал все еще работает.

Изменения не возможно полностью отменить (как баги фиксить?), просто по возможности стоит этого избегать

### Liskov substitution (LSP)
Ф-и, сущьносити, которые использует родительский тип, должны точно также работать и с дочерними классами. 
Наследаемый класс должнен дополнять, а не заменять функционал родительского класса 

Нельзя просто так взять и дочернего класса уничтожить сущность которая есть у родительского. Если возникает такая нужда, значит была ошибка проектирования


### Interface segregation (ISP)

Программные сущьности не должны зависеть от методом, которые они не используют.
Нельзя засталять колиента реализовывать интерфейс, которым он не пользуется

Этот принцип перекликается с первым и третим.

**Ошибка построения**

![[Pasted image 20220305111352.png]]

Тут мы сделали интерфейс который подошел для реализации первого класса, но в дальнейшем оказалось что другие классы не нуждуются в некоторых методах. 


**Как надо строить архитектуру**

![[Pasted image 20220305111334.png]]

Правильно будет разбить интерфес и добавлять его только куда нужно


В данном принцепе избавляемся от сущьностей которые не используеются => получаем более предсказуемую работу и код становиться менее связанным. Не связанные код намного легче поддерживать

### Dependency inversion (DIP)

 Модули верхнего уровня не должны зависеть от модулей нижнего. Нам недолжно требовать переписывать родитеельский компонент, если в дочернем что-то поменялось. Это достигается с помощью прослоек которые заботяться о согласовании
 
 Зависимость должна строиться на абстракциях, а не на что-то конкретное. 

Как например мы используем axios, и не вожно какие методы от использует внутри ( на сервенен это XMLHTTP, а на клиенте это Fetch)
 

---

###### Citation

- [SOLID ПРИНЦИПЫ простым языком (много примеров)](https://www.youtube.com/watch?v=TxZwqVTaCmA&list=PLZTsCOAKJJ_YjEHsB4HJQ9GnB7I_g3n1l&index=1&t=3s&ab_channel=UlbiTV)
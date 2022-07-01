---
aliases: 
tags: 
date created: Friday, July 1st 2022, 5:21:40 pm
date modified: Friday, July 1st 2022, 5:25:53 pm
---

# Утилиты

### Выбирает случайный элемент из массива:

```js
export const sampleOne = (arr) => {
  return arr[Math.floor(Math.random() * arr.length)];
};
```

### Перемещает курсор пользователя в текстовом вводе

```js
export function moveCursorWithinInput(input, position) {
  if (input.setSelectionRange) {
    input.focus();
    input.setSelectionRange(position, position);
  } else if (input.createTextRange) {
    var range = input.createTextRange();
    range.collapse(true);
    range.moveEnd('character', position);
    range.moveStart('character', position);
    range.select();
  }
}
```

### И эта утилита получает расстояние между двумя точками на декартовой плоскости (что на удивление часто встречается в проектах с нетривиальной анимацией):

```js
export const getDistanceBetweenPoints = (p1, p2) => {
  const deltaX = Math.abs(p2.x - p1.x);
  const deltaY = Math.abs(p2.y - p1.y);
  return Math.sqrt(deltaX ** 2 + deltaY ** 2);
};
```

---

###### References

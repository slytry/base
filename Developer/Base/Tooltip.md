---
aliases: 
tags: 
date created: Thursday, July 21st 2022, 10:16:29 am
date modified: Thursday, July 21st 2022, 11:11:32 am
---

# Tooltip

## Необходимые хуки

- [[useTooltipTrigger , useTooltip]] - react-aria
- [[useTooltipTriggerState]] - react-stately

useTooltipTrigger и useTooltip отвечает за:

- Управление фокусом с клавиатуры и кросс-браузерная нормализация
- Управление наведением и кросс-браузерная нормализация
- Поддержка маркировки для программ чтения с экрана (aria-describedby)
- Предоставляется в виде всплывающей подсказки вспомогательным технологиям через ARIA
- Соответствует собственному поведению всплывающей подсказки с задержкой при наведении на первую всплывающую подсказку и без задержки для последующих всплывающих подсказок.

Состояние всплывающей подсказки управляется хуком useTooltipTriggerState. Объект состояния должен передаваться как опция в useTooltipTrigger и useTooltip.

## Tooltip |[Tooltip](https://react-spectrum.adobe.com/react-spectrum/Tooltip.html)

Сигнатура

```tsx
<TooltipTrigger>
  <ActionButton aria-label="Edit Name"><Edit /></ActionButton>
  <Tooltip>Change Name</Tooltip>
</TooltipTrigger>
```

TooltipTrigger принимает ровно двух дочерних элементов: элемент, запускающий отображение всплывающей подсказки, и саму всплывающую подсказку. Элемент триггера должен быть первым дочерним элементом, переданным в TooltipTrigger.

### TooltipTrigger

### ActionButton

### Tooltip

---

###### References

- [Tooltip](https://react-spectrum.adobe.com/react-spectrum/Tooltip.html) – пример для вдохновения React Spectrum

---
aliases: null
date created: 2022-03-01 16:34
date updated:
---

Мощная бибилиотека для работы с датой

Пример форматирования даты с бэка. 28-12-2021 в 28 декабря 2021

```jsx
import { parseISO, format } from 'date-fns'
import { format } from 'date-fns';
import { ru } from 'date-fns/locale';

export default function Date({ dateString }) {
  const date = parseISO(dateString)
  return <time 
	 dateTime={dateString}>{format(date, 'dd MMMM yyyy', { locale: ru })}
  </time>
}
```


---

###### Citation
https://www.npmjs.com/package/date-fns

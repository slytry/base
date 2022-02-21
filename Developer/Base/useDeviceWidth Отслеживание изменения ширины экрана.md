---
aliases: null
date created: 2022-02-18 13:35
date updated:
---

Для обработчика событий надо всегда задавать удаление слушателя при размонтировании

Вторым параметром передан пустой массив, значит обработчик навеситься только один раз


```js
import { useEffect, useState } from 'react';

export const useDeviceWidth = (initialWidth = 0) => {
  const [deviceWidth, setDeviceWidth] = useState(initialWidth);

  // Ресайз страницы
  useEffect(() => {
    const resizeListener = () => {
      setDeviceWidth(window.innerWidth);
    };

    resizeListener();
    window.addEventListener('resize', resizeListener);
    return () => {
      window.removeEventListener('resize', resizeListener);
    };
  }, []);

  return deviceWidth;
};

```

Использование:

```js
 const deviceWidth = useDeviceWidth();

  useEffect(() => {
    if (deviceWidth > 767) {
      //логика
      };

      window.addEventListener('scroll', handler);

      return () => {
        window.removeEventListener('scroll', handler);
      };
    }
  }, [deviceWidth]);
```

После изменения ширины экрана компонент будет размонтироваться и заного монтироваться. Так при ширинах экрана меньше 767 обработчик не будет повешен


---

###### Citation


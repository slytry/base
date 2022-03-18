---
aliases: null
date created: 2022-02-24 15:22
date updated:
---

Расширение для тэга img. Имеет много уже встроенной оптимизации

- Делает webp и меняет сам разрешение под экраны
- Предотваращает скачки интерфеса
- Ленивая загрузка и может блюрить при загрузке

### Использование
Чтобы использовать надо импортировать
```jsx
import Image from 'next/image'
```

**Если фото локальное**
Сначало надо импортировать само фото. Форматы:  `.jpg`, `.png` или `.webp`

```jsx
import profilePic from '../public/me.png'
```

Next сам глянет размеры изображения чтобы не было сдвига при загрузке

```js
 <Image
        src={profilePic}
        alt="Picture of the author"
        // width={500} automatically provided
        // height={500} automatically provided
        // blurDataURL="data:..." automatically provided
        // placeholder="blur" // Optional blur-up while loading
      />
```

placeholder blur работает сразу

**Если с удаленного источника**
Для этого в src должно быть строка URL. Это может быть как абсолютные так и относительны путь. И в таком случае надо будет задать в ручную высоту и ширину. И задать [`blurDataURL`](https://nextjs.org/docs/api-reference/next/image#blurdataurl) 

Что бы для удаленных изображений работали все автоматические оптимизации Image надо указывать абсолютный путь.  И домены с которых будет запрашивать данные надо указать к конфигурации (ради безопасности)

```js
module.exports = {
  images: {
    domains: ['example.com', 'example2.com'],
  },
}
```

placeholder blur не работает сам по себе. Для стороних изображений надо самому указывать фон для placeholder в своействе  [`blurDataURL`](https://nextjs.org/docs/api-reference/next/image#blurdataurl). Это может автоматический генератор фонов в кодровке base64 [Plaiceholder](https://github.com/joe-bell/plaiceholder) или [generate a solid color Data URL](https://png-pixel.com/)


### Генератор url строк 
Опционально можно запрашивать изображения разных разреений и форматом и качеств. Но тогда отключиться встроенная оптимизация Image

### Priority

Самому тяжелому изображению на странице надо поставить атрибут priority
```jsx
 <Image
        src="/me.png"
        alt="Picture of the author"
        width={500}
        height={500}
        priority
      />
```

Это ускорить загрузку

### Атрибуты

| Антибут        | Значения                                                                                         | Описание                                                                                                   |
| -------------- | ------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------- |
| objectFit      | [object-fit CSS property](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)           | Определяет, как изображение будет помещаться в родительский контейнер при использовании layout="fill".     |
| objectPosition | [object-position CSS property](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position) | Определяет, как изображение позиционируется внутри родительского элемента при использовании layout="fill". |
|                |                                                                                                  |                                                                                                            |



###

---

###### Citation


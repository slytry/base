---
aliases: 
tags: 
date created: Thursday, June 16th 2022, 1:24:18 pm
date modified: Tuesday, July 5th 2022, 9:09:54 pm
---

# CSS shapes

## Стрелки

Стрелка из двух частей с загругленными краями

```scss
.ArrowButton__shape {
	$width: 8px;
	$height: 1.5px;
	$shiftX: $width/2;

	display: block;

	width: 100%;
	height: 100%;

	&::after,
	&::before {
		display: block;
		position: absolute;
		top: 50%;
		left: 50%;
		background-color: $c-dark;
		width: $width;
		height: $height;
		content: '';
	}

	&::before {
		transform: rotate(45deg) translateX(-$shiftX);
		border-radius: 10px 6px 6px 10px;
	}

	&::after {
		transform: rotate(-45deg) translateX(-$shiftX);
		border-radius: 10px 6px 6px 10px;
	}
}
```

---

###### References

- [The Shapes of CSS](https://css-tricks.com/the-shapes-of-css/)
- [60 CSS Arrows](https://freefrontend.com/css-arrows/#simple-arrows)
- Генератор облачнокошка [CSS ARROW PLEASE!](https://cssarrowplease.com/)

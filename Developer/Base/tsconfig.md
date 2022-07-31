---
aliases: 
tags: 
date created: Friday, July 29th 2022, 5:38:21 pm
date modified: Friday, July 29th 2022, 5:48:39 pm
---

# tsconfig

## Обозначения

- `!` - если это правило включить на проекте не сразу, а где то в середине - случаться пиздец. Такие правила заставляют типизировать

## Из проекта Vertical (NextJs)

```json
{
	"compilerOptions": {
		"baseUrl": ".",
		"target": "es5",
		"lib": ["dom", "dom.iterable", "esnext"],
		"typeRoots": ["node_modules/@types", "typings"],
		"allowJs": true, // - можно делать обычные js файлы
		"skipLibCheck": true,
		"strict": false,
		"forceConsistentCasingInFileNames": true,
		"noEmit": true,
		"esModuleInterop": true,
		"module": "esnext",
		"moduleResolution": "node",
		"resolveJsonModule": true,
		"isolatedModules": true,
		"jsx": "preserve",
		"experimentalDecorators": true,
		"allowSyntheticDefaultImports": true,
		"incremental": true,
		"strictFunctionTypes": true,
		"strictNullChecks": true, // - проверяет каждый объект на возможность быть пустым и если да заставляет писать проверку
		"noImplicitAny": true, // - проверяет все не явные any. Хорошее правило само по себе, но надо
		"noImplicitReturns": true,
		"noImplicitThis": true
	},
	"exclude": ["node_modules"],
	"include": ["next-env.d.ts", "**/*.ts", "**/*.tsx"]
}

```

---

###### References

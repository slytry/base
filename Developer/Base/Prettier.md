---
aliases: 
tags: 
date created: Wednesday, May 11th 2022, 12:57:50 pm
date modified: Friday, May 13th 2022, 4:59:30 pm
---

# Prettier

### Зачем?

- Репы только с eslint исключение из правил, в основном используется оба инструмента. Наверно они знают что делают
	- prettier + eslint **[:](https://github.com/use-platform/use-platform "Follow link")** [use-platform,](https://github.com/use-platform/use-platform "Follow link")  [yargs](https://github.com/yargs/yargs "Follow link")**,** [lerna,](https://github.com/lerna/lerna "Follow link")  [angular](https://github.com/angular/angular "Follow link"), [react,](https://github.com/ui-router/react "Follow link")  [react-router](https://github.com/remix-run/react-router "Follow link")
	- Только eslint: [massive-js,](https://gitlab.com/dmfay/massive-js "Follow link")  [unleash](https://github.com/Netflix/unleash "Follow link")
- Приятно использовать лучшие инструменты  
	eslint хоть и может исправлять автоматически синтаксические ошибки, но это не его основная задача. В eslint более 300-т правил и только 100 могут автоматически исправится  
	prettier с другой стороны специализированный интрумент. Даже некоторые пересекающиеся правила работают лучше в prettier. Например максимальная длинна строки.  
	Нашел вот такой коммит [chore: Turn off eslint's max-len in favor of prettier's printWidth](https://github.com/lerna/lerna/commit/9697b17ef83e316bcd40c733d04a894deaab2c9a "Follow link")

- !! eslint не умеет форматировать ничего кроме js. Если не будет prettier значит будет отдельная утилита для каждого языка, притом и работать они будут также, а то и хуже 
	- Поддержка prettier:
		- JavaScript (including experimental features)
		- [JSX](https://facebook.github.io/jsx/ "Follow link")
		- [Angular](https://angular.io/ "Follow link")
		- [Vue](https://vuejs.org/ "Follow link")
		- [Flow](https://flow.org/ "Follow link")
		- [TypeScript](https://www.typescriptlang.org/ "Follow link")
		- CSS, [Less](http://lesscss.org/ "Follow link"), and [SCSS](https://sass-lang.com/ "Follow link")
		- [HTML](https://en.wikipedia.org/wiki/HTML "Follow link")
		- [Ember/Handlebars](https://handlebarsjs.com/ "Follow link")
		- [JSON](https://json.org/ "Follow link")
		- [GraphQL](https://graphql.org/ "Follow link")
		- [Markdown](https://commonmark.org/ "Follow link"), including [GFM](https://github.github.com/gfm/ "Follow link") and [MDX](https://mdxjs.com/ "Follow link")
		- [YAML](https://yaml.org/ "Follow link")

### Правила

Можно посмотреть готовые конфиги
- [lerna](https://github.com/lerna/lerna)
- [use-platform](https://github.com/use-platform/use-platform)
- [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier)

### Конфиг


```
{
	"trailingComma": "es5",
	"arrowParens": "always",
	"endOfLine": "lf",
	"printWidth": 100,
	"semi": true,
	"singleQuote": true,
	"tabWidth": 4,
	"useTabs": true,
	"prettier.jsxSingleQuote": true,
	"prettier.jsxBracketSameLine": true
	
	// "@trivago/prettier-plugin-sort-imports" - плагин для сортировки импортов

	"importOrder": ["^[./]"],
	"importOrderSeparation": true,
	"importOrderSortSpecifiers": true
}

```

---

###### References

### Сортировка CSS свойств
-	https://github.com/tujoworker/prettier-plugin-rational-order
-	https://www.npmjs.com/package/prettier-plugin-css-order
---
tags: 
aliases: svse
date created: 2022-03-18 15:40
date modified: Wednesday, July 6th 2022, 8:37:42 pm

title: Настройки Расширения VS code
---

# Расширения VS code

#### ecsstractor

```json
{
	"ecsstractor_port.add_comment": false,
	"ecsstractor_port.modifier_separator": "--",
}
```

#### Path Intellisense

```json
{	
  "typescript.suggest.paths": false,
  "javascript.suggest.paths": false,
  //Элиасы для более простого регулярного выржения при сборке gulp
  "path-intellisense.mappings": {
    "/": "${workspaceFolder}",
    "@img": "${workspaceFolder}/src/assets/images",
    "@svg": "${workspaceFolder}/src/assets/images/svg",
    "@scss": "${workspaceFolder}/src/scss",
    "@script": "${workspaceFolder}/src/script"
  },
}
```

#### bemHelper

```json
{
	  "bemHelper.classNameCase": "any",
}
```

#### prettier

https://prettier.io/docs/en/options.html

```json
{
	"prettier.jsxBracketSameLine": true,
	"prettier.jsxSingleQuote": true,
	"prettier.singleQuote": true,
	"prettier.tabWidth": 2,
	"prettier.useTabs": true,
	"prettier.printWidth": 90,
	"prettier.trailingComma": "es5",
	"prettier.bracketSameLine": true,
	
}
```

#### Рассылки

Надо скачать расширение MJML

```json
{	
	 "[mjml]": { "editor.defaultFormatter": "mjmlio.vscode-mjml" },
}
```

---

###### References

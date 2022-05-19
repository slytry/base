---
tags: 
aliases: null
date created: 2022-03-14 19:02
date modified: Wednesday, May 18th 2022, 9:56:01 pm
date modified: Wednesday, May 18th 2022, 9:56:01 pm
---

## Eslintrc file

Конфиг основан  [этой](https://indepth.dev/posts/1282/setting-up-efficient-workflows-with-eslint-prettier-and-typescript) статье и доплнительными плюшками:
- некоторые правала взятых с шаблона виталика
- eslint для nextjs взят из [доки](https://nextjs.org/docs/basic-features/eslint#:~:text=Migrating%20Existing%20Config)
- установлен [плагин](https://nextjs.org/docs/basic-features/eslint#:~:text=Migrating%20Existing%20Config) для притиера, отменяет некоторые правили дл яизбежания конфликтов

### main part

```json
{
	"env": {
		"browser": true,
		"es2021": true
	},
	"extends": [
		"plugin:react/recommended",
		"plugin:@typescript-eslint/recommended",
		"airbnb",
		"next",
		"prettier"
	],
	"parser": "@typescript-eslint/parser",
	"parserOptions": {
		"ecmaFeatures": {
			"jsx": true
		},
		"ecmaVersion": "latest",
		"sourceType": "module"
	},
	"plugins": ["react", "react-hooks", "@typescript-eslint"],
	"settings": {
		"import/resolver": {
			"typescript": {}
		}
	},

```

### rules part

```json
"rules": {
		"react-hooks/rules-of-hooks": "error",
		"react-hooks/exhaustive-deps": "warn",
		"no-shadow": "off",
		"@typescript-eslint/no-shadow": ["error"],
		"no-unused-vars": "off",
		"jsx-a11y/anchor-is-valid": "off",
		"react/react-in-jsx-scope": "off",
		"react/jsx-props-no-spreading": "off",
		"react/jsx-filename-extension": [
			"warn",
			{
				"extensions": [".tsx"]
			}
		],
		"react/forbid-prop-types": "off",
		"import/no-unresolved": "off",
		"import/extensions": [
			"error",
			"ignorePackages",
			{
				"ts": "never",
				"tsx": "never"
			}
		],
		"import/prefer-default-export": "off",
		"prefer-promise-reject-errors": "off",
		"react/no-arrow-function-lifecycle": "off",
		"react/no-invalid-html-attribute": "off",
		"react/no-unused-class-component-methods": "off",
		"react/prop-types": "off",
		"react/require-default-props": [
			"error",
			{
				"ignoreFunctionalComponents": true
			}
		],
	  	"react/function-component-definition": [
		  //Меняет все стрелочные ф-и на декларэйшин (причина в типизации, но пока я не умею)
		  "warn",
		    {	
			  "namedComponents": "arrow-function",
			  "unnamedComponents": "arrow-function"
		 	}
   		 ],
		"@typescript-eslint/no-namespace": "off",
		"@typescript-eslint/no-unused-vars": "error",
		"no-use-before-define": "off",
		"@typescript-eslint/no-use-before-define": ["error"],
		"@typescript-eslint/no-explicit-any": "error",
		"@typescript-eslint/explicit-function-return-type": [
			"error",
			{
				"allowExpressions": true
			}
		]
	}
}

```

## Packaje.json

```json
{
  "devDependencies": {
	"prettier": "2.6.2"
	"eslint": "^8.15.0",
    "eslint-config-next": "^12.1.6",
	"eslint-config-prettier": "^8.5.0",
	"eslint-import-resolver-typescript": "^2.7.1",
	  
	  // устанавливается автоматически при установке airbnb и выбора ts через npx eslint --init
	"eslint-config-airbnb": "^19.0.4",
	"@typescript-eslint/eslint-plugin": "^5.25.0",
	"@typescript-eslint/parser": "^5.25.0",
	"eslint-plugin-import": "^2.26.0",
	"eslint-plugin-jsx-a11y": "^6.5.1", 
	"eslint-plugin-react": "^7.29.4",
	"eslint-plugin-react-hooks": "^4.5.0",
  }
}

```

## .prettierrc

```json
{
	"trailingComma": "es5",
	"arrowParens": "always",
	"endOfLine": "lf",
	"printWidth": 100,
	"semi": true,
	"singleQuote": true,
	"tabWidth": 4,
	"useTabs": true,
	"overrides": [
		{
			"files": "*.md",
			"options": {
				"useTabs": false,
				"tabWidth": 2
			}
		}
	]
}

```

## .prettierignore +  .prettierignore

```
# folders
node_modules
dist
storybook-static
.next
public

# files
**/*.test.js
/**/*.d.ts
*.svg
package-lock.json
```

## настройка vscode

```json
{
	"files.exclude": {
		"**/.DS_Store": true,
		"**/.git": false,
		"**/node_modules": false

		// Cкроются все файлы не учавствующие в разработке (поставить ',' сверху)
		// "**/.DS_Store": true,
		// "**/.git": true,
		// "**/node_modules": true,
		// "**/docker": true,
		// "**/.prettierignore": true,
		// "**/.prettierrc": true,
		// "**/.eslintignore": true,
		// "**/.eslintrc.json": true,
		// "**/tsconfig.json": true,
		// "**/.babelrc": true,
		// "**/next-env.d.ts": true,
		// "**/.next": true,
		// "**/.vscode": true,
		// "**/docs": true,
		// "**/.gitignore": true
	},
	"search.exclude": {
		"**/node_modules": true
	},

	"editor.formatOnPaste": true,
	"editor.formatOnSave": true,
	"editor.defaultFormatter": "esbenp.prettier-vscode",
	"editor.codeActionsOnSave": {
		"source.fixAll.eslint": true,
		"source.fixAll.format": true
	},

	"eslint.workingDirectories": ["./src"],
	"prettier.configPath": "./src/.prettierrc",
	"eslint.alwaysShowStatus": true,

	"[jsonc]": {
		"editor.defaultFormatter": "esbenp.prettier-vscode"
	},
	"[javascript]": {
		"editor.defaultFormatter": "esbenp.prettier-vscode"
	},
	"[scss]": {
		"editor.defaultFormatter": "esbenp.prettier-vscode"
	},
	"[html]": {
		"editor.defaultFormatter": "esbenp.prettier-vscode"
	},
	"[typescriptreact]": {
		"editor.defaultFormatter": "esbenp.prettier-vscode"
	},
	"[markdown]": {
		"editor.defaultFormatter": "esbenp.prettier-vscode"
	}
}

```



---

###### Citation
Articles
- [Setting up efficient workflows with ESLint, Prettier and TypeScript](https://indepth.dev/posts/1282/setting-up-efficient-workflows-with-eslint-prettier-and-typescript)
- [Setting ESLint on a React Typescript project (2022)](https://andrebnassis.medium.com/setting-eslint-on-a-react-typescript-project-2021-1190a43ffba)


Examples
- [storybook repo](https://github.com/storybookjs/storybook) - переписывают правила только для определенных языков



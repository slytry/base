---
aliases: null
date created: 2022-03-16 21:27
date updated:
---

### Базовые нстройки 
```json
{
  //ОБЩИЕ
  "editor.fontSize": 16,
  "editor.fontFamily": "Fira Code",
  "editor.fontLigatures": true,
  "workbench.colorTheme": "Panda Syntax",
  "workbench.iconTheme": "vscode-icons",
  "editor.wordWrap": "wordWrapColumn",
  "editor.wordWrapColumn": 110,
  "files.autoSave": "onFocusChange",
  "editor.tabSize": 2,
  "editor.detectIndentation": false,
  "workbench.startupEditor": "none",

  //Открывает вместе с настройками файл с дефолтными настройками
  "workbench.settings.useSplitJSON": true,

  //Отключение сообщения о новых версиях
  "vsicons.dontShowNewVersionMessage": true,

  //Атоматическая чистка пустых строк и пробеллов
  "files.insertFinalNewline": true,
  "files.trimFinalNewlines": true,
  "files.trimTrailingWhitespace": true,
  "[markdown]": {
    "files.trimTrailingWhitespace": false
  },

  // Убираем алерты с предупреждениями при удалении и перетаскивании файлов и директорий:
  "explorer.confirmDelete": false,
  "explorer.confirmDragAndDrop": false,

  //Зум через колесико и ctr
  "editor.mouseWheelZoom": true,

  // Оканчание строки lf
  "files.eol": "\n",

  //Встроенный Intellisense не показывает именна
  "javascript.suggest.names": false,

  //Bash по умолчанию
  "terminal.integrated.defaultProfile.windows": "Git Bash",

  //ДАЛОЙ НЕНУЖНЫЕ РАСШИРЕНИЯ
  //Auto renaming HTML tags
  "editor.linkedEditing": true,
  "javascript.autoClosingTags": true,
  "typescript.autoClosingTags": true,

  //Auto import modules JS
  "javascript.suggest.autoImports": true, //включение подсказок (работает по умолчанию)
  "typescript.suggest.autoImports": true,
  "javascript.updateImportsOnFileMove.enabled": "always", //Автоматическая замена путей (по умолчанию будет спрашивать)
  "typescript.updateImportsOnFileMove.enabled": "always",

  //Bracket pair coloring
  "editor.bracketPairColorization.enabled": true,

  //Indentation guides colorization (Indent Rainbow)
  "editor.guides.bracketPairs": true,
  "editor.guides.highlightActiveIndentation": true,
  "editor.guides.bracketPairsHorizontal": "active",

  //ЛИНТЕРЫ
  //Действия по схранению
  "editor.codeActionsOnSave": {
    // удаляет неиспользуемые операторы import и расположит сверху импорты с глобальными
    "source.organizeImports": true,
    //Включаем ESlint на сохранение
    "source.fixAll.eslint": true
  },

  //Настройка дефолтных форматеров
  "[html]": {
    "editor.defaultFormatter": "vscode.html-language-features"
  },
  "[css]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[scss]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[json]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[jsonc]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  //дефолтный форматер для JS
  "[javascript]": {
    "editor.defaultFormatter": "dbaeumer.vscode-eslint"
  },
  "[javascriptreact]": {
    "editor.defaultFormatter": "dbaeumer.vscode-eslint"
  },
  "[typescript]": {
    "editor.defaultFormatter": "dbaeumer.vscode-eslint"
  },
  "[typescriptreact]": {
    "editor.defaultFormatter": "dbaeumer.vscode-eslint"
  },

  //Prettier
  //Одинарные ковычки
  "prettier.singleQuote": true,

  //ESLint
  //Отключаем дефольтный линтер
  "javascript.validate.enable": false,
  "typescript.validate.enable": false,
  //Закрепляет еслинт в трей
  "eslint.alwaysShowStatus": true,
  //Фключает форматирование, после этого eslint появлятеся в списке форматеров
  "eslint.format.enable": true,
  //Задаем языки для ESlint
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    "typescript",
    "typescriptreact"
  ],

  //РАСШИРЕНИЯ
  //БЕМ хелпер, ругался на названия классов
  "bemHelper.classNameCase": "any",

  //Path Intellisense
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
  "terminal.integrated.cursorStyle": "line",
  "liveServer.settings.donotShowInfoMsg": true,
  "security.workspace.trust.untrustedFiles": "open",
  "ecsstractor_port.add_comment": false,
  "ecsstractor_port.modifier_separator": "--",
  "editor.formatOnSave": true,
  "reactSnippets.settings.importReactOnTop": false,
  "window.zoomLevel": 1,
  "breadcrumbs.enabled": false,
  "editor.renderWhitespace": "none",
  "editor.minimap.enabled": false,
  "editor.suggestSelection": "recentlyUsed",
  "editor.lineNumbers": "off",
  "workbench.sideBar.location": "right",
  "git.confirmSync": false,

  //Курсор
  "editor.cursorBlinking": "expand",
  "editor.cursorStyle": "line",
  "editor.cursorWidth": 2,
  "editor.cursorSmoothCaretAnimation": true
}
```


---

###### Citation


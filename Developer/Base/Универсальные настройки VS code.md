---
aliases: null
date created: 2022-03-18 15:44
date updated:
---

#### Универсальные

##### Оступы

```json
{
     //Отключение пробелов при табе, чтобы были сами табы
  "editor.insertSpaces": false,

	 //Размер отступа
  "editor.tabSize": 2,
	
	 //Отключение автоматического подстройка отступов. Чтобы везде были табы
  "editor.detectIndentation": false,
}
```


#####  Вешний вид

```json
{
	//Отколючаем хлебные крошки
  "breadcrumbs.enabled": false,
	
	//Плавный скролл
  "editor.smoothScrolling": true,
	
	//Перенос строк
  "editor.wordWrap": "wordWrapColumn",
  "editor.wordWrapColumn": 110,
	
	//Скрытие акстивита бара
  "workbench.activityBar.visible": false,

	//Отображение нечитаемых символов (всех кроме одиночных пробелов)
  "editor.renderWhitespace": "boundary",
	
	 //Отображение миникарты
  "editor.minimap.enabled": false,

	 //Возможность скрытия кусков кода
  "editor.folding": false,

     //Точки остановки кода
  "editor.glyphMargin": false,
	
	 //Курсор
  "editor.cursorBlinking": "expand",
  "editor.cursorStyle": "line",
  "editor.cursorWidth": 2,
  "editor.cursorSmoothCaretAnimation": true,

	//Положение сайд бара
  "workbench.sideBar.location": "right",
	
	//Скрытие пустых папок
	"explorer.compactFolders": false,
	
}
```

##### Поведение

```json
{
	//Проверка доверие к файлам
  "security.workspace.trust.enabled": false,
  "security.workspace.trust.untrustedFiles": "open",
	//Всякие подсказки при когд анет открытых файлов
	"workbench.tips.enabled": false,
	
	//Подсказка в новом файле
	"workbench.editor.untitled.hint": "hidden",
	
	//Первое окно при открытии
  "workbench.startupEditor": "none",
	
	// Убираем алерты с предупреждениями при удалении и перетаскивании файлов и директорий:
  "explorer.confirmDelete": false,
  "explorer.confirmDragAndDrop": false,
	
  "terminal.integrated.cursorStyle": "line",
  "terminal.integrated.enableMultiLinePasteWarning": false,
  "[jsonc]": {

    "editor.defaultFormatter": "vscode.json-language-features"

  }
}
```

##### Доработка

```json
{
	//Открывает вместе с настройками файл с дефолтными настройками
  "workbench.settings.useSplitJSON": true,
	
	//Отображение контрольных символов
  "editor.renderControlCharacters": true,

	// Оканчание строки lf
  "files.eol": "\n",
	
	//Оставляем одну строку в конце
  "files.insertFinalNewline": true,
	
	//Удаляем лишнии пробелы
  "files.trimFinalNewlines": true,
  "files.trimTrailingWhitespace": true,
	
	//Не удаляем для markdown
  "[markdown]": {
    "files.trimTrailingWhitespace": false
  },
	
		//Зум через колесико и ctr
  "editor.mouseWheelZoom": true,

	 //Auto renaming HTML tags
  "editor.linkedEditing": true,
  "javascript.autoClosingTags": true,
  "typescript.autoClosingTags": true,
	
	//Bracket pair coloring
  "editor.bracketPairColorization.enabled": true,
	
	//Indentation guides colorization (Indent Rainbow)
  "editor.guides.bracketPairs": true,
  "editor.guides.highlightActiveIndentation": true,
  "editor.guides.bracketPairsHorizontal": "active",
	
	//Сохранение по смене фокуса
  "files.autoSave": "onFocusChange",
  "editor.formatOnSave": true,

   // ActionsOnSave
  "editor.codeActionsOnSave": {
	"source.organizeImports": true,
  },
	
	//Добавить подчеркивание в разделители
  "editor.wordSeparators": "`~!@#$%^&*()_-=+[{]}\\|;:'\",.<>/?",
	
	//Автоматическое удаление лишний символов
 "editor.unusualLineTerminators": "auto",
	
}
```

##### Git

```json
{
	// Автоматическая проверка репо на новые коммиты
 "git.autofetch": true,
	//Интервал запросов
	"git.autofetchPeriod": 60,
	
	//Не задают глупых вопросов при синхе
	 "git.confirmSync": true,
	
	//Позволяет закомитить при наличии не застедженых файлов
	"git.enableSmartCommit": true,
	
	//Ребээйз вместо мерджа
	 "git.rebaseWhenSync": true,
	
} 
```



---

###### Citation


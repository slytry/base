---
tags: 
aliases: null
date created: 2022-02-18 14:25
date modified: Wednesday, July 6th 2022, 8:42:47 pm
date modified: Wednesday, July 6th 2022, 8:42:47 pm
---

# Snippets VS code

### JS

```json
{
"Redux Toolkit Configure Store": {
    "prefix": "rts",
    "body": [
      "import { configureStore } from '@reduxjs/toolkit';",
      "$0",
      "import ${1:reducer} from '${2:location}';",
      "$0",
      "export default configureStore({",
      "  ${3:reducerName}: ${1:reducer},",
      "});"
    ],
    "description": "Creates Redux Toolkit Configure Store"
  },
  "Redux Toolkit Create Slice": {
    "prefix": "rtcs",
    "body": [
      "import { createSlice } from '@reduxjs/toolkit';",
      "$0",
      "const initialState = {${1}};",
      "$0",
      "export const ${2:sliceName} = createSlice({",
      "  name: '${3:name}',",
      "  initialState,",
      "  reducers: {",
      "    ${4:reducerName}: (state, action) => {",
      "      ${5}",
      "    },",
      "  },",
      "});",
      "$0",
      "export const { ${4:reducerName} } = ${2:sliceName}.actions;",
      "$0",
      "export default ${2:sliceName}.reducer;"
    ],
    "description": "Creates Redux Toolkit Create Slice"
  },
  "Redux Toolkit Create Reducer": {
    "prefix": "rtcr",
    "body": [
      "import { createAction, createReducer } from '@reduxjs/toolkit';",
      "$0",
      "const ${1:name} = createAction('${2:action}/${3:type}');",
      "$0",
      "const initialState = {${4}};",
      "$0",
      "const ${5:reducerName} = createReducer(initialState, builder => {",
      "  builder",
      "    .addCase(${1:name}, (state, action) => {",
      "      ${6}",
      "    });",
      "});"
    ],
    "description": "Creates Redux Toolkit Create Reducer"
  },
  "Redux Toolkit Create Action": {
    "prefix": "rtca",
    "body": [
      "import { createAction } from '@reduxjs/toolkit';",
      "$0",
      "const ${1:name} = createAction('${2:action}/${3:type}');"
    ],
    "description": "Creates Redux Toolkit Create Action"
  }
}

```

- [JavaScript (ES6) code snippets](https://marketplace.visualstudio.com/items?itemName=xabikos.JavaScriptSnippets)

### React

```json
{
 "cnClass": {
    "prefix": "cx",
    "body": ["{cx('$1')}"],
    "description": "classnames"
  },

  "cnBind": {
    "prefix": "cb",
    "body": [
      "import cnBind from 'classnames/bind';\nimport style from '$1';\n\nconst cx = cnBind.bind(style);"
    ],
    "description": "classnames"
  },

  "classProp": {
    "prefix": "cl",
    "body": ["className={cx('$1')}"],
    "description": "classnames"
  },

  "reactFCoWithPropTypes": {
    "key": "reactFunctionalComponentWithPropTypes",
    "prefix": "rr",
    "body": [
      "import cnBind from 'classnames/bind';",
      "import PropTypes from 'prop-types';",
      "import style from '${1:style}';",
      "",
      "const cx = cnBind.bind(style);",
      "",
      "function ${2:${TM_FILENAME_BASE}}({ className }) {",
      "  return (",
      "    <div className={cx('', className)}>${3: Component}</div>",
      "  );",
      "}",
      "",
      "${2:${TM_FILENAME_BASE}}.propTypes = {",
      "  className: PropTypes.string,",
      "};",
      "",
      "${2:${TM_FILENAME_BASE}}.defaultProps = {",
      "  className: '',",
      "};",
      "",
      "export { ${2:${TM_FILENAME_BASE}} };",
      ""
    ],
    "description": "Creates a React Functional Component with ES7 module system with PropTypes",
    "scope": "typescript,typescriptreact,javascript,javascriptreact"
  }
}


```

[React Hooks Snippets](https://marketplace.visualstudio.com/items?itemName=AlDuncanson.react-hooks-snippets)

[vscode-react-javascript-snippets](https://github.com/dsznajder/vscode-react-javascript-snippets)

### Emmet

[Emmet Cheat Sheet](https://docs.emmet.io/cheat-sheet/)

[VS Code ES7+ React/Redux/React-Native/JS snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)

### Next

[Next.js snippets](https://marketplace.visualstudio.com/items?itemName=PulkitGangwar.nextjs-snippets)

### SCSS

```json
{
  "breakpoint-up": {
    "prefix": "media-up",
    "body": ["@include media-breakpoint-up('$1') {", "\t$2", "}"],
    "description": "mixin media query min-width"
  },
  "breakpoint-down": {
    "prefix": "media-down",
    "body": ["@include media-breakpoint-up('$1') {", "\t$2", "}"],
    "description": "mixin media query max-width"
  },
  "7md7": {
    "prefix": "7md7",
    "body": ["@media (max-width: 767px) {", "\t$2", "}"],
    "description": "mixin media query max-width"
  },
  "8md8": {
    "prefix": "8md8",
    "body": ["@media (max-width: 1023px) {", "\t$2", "}"],
    "description": "mixin media query max-width"
  },
  "use": {
    "prefix": "us",
    "body": ["@use '../../../styles/abstract/' as *;"],
    "description": "at use"
  }
}


```

---

###### Citation

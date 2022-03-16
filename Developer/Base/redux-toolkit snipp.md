---
aliases: null
date created: 2022-03-12 21:42
date updated:
---
## Redux Toolkit

### Create Action

##### `rtca`

```javascript
import { createAction } from '@reduxjs/toolkit';

const name = createAction('action/type');
```

### Create Reducer

##### `rtcr`

```javascript
import { createAction, createReducer } from '@reduxjs/toolkit';

const name = createAction('action/type');

const initialState = {};

const reducerName = createReducer(initialState, builder => {
  builder.addCase(name, (state, action) => {
    // ...
  });
});
```

### Create Slice

##### `rtcs`

```javascript
import { createSlice } from '@reduxjs/toolkit';

const initialState = {};

export const sliceName = createSlice({
  name: 'name',
  initialState,
  reducers: {
    name: (state, action) => {
      // ...
    },
  },
});

export const { name } = sliceName.actions;

export default sliceName.reducer;
```

### Configure Store

##### `rts`

```javascript
import { configureStore } from '@reduxjs/toolkit';

import reducer from 'location';

export default configureStore({
  reducerName: reducer,
});
```
---

###### Citation

https://marketplace.visualstudio.com/items?itemName=lzrnic.javascript-vscode-extension
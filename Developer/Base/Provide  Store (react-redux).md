---
aliases: 
tags: 
date created: Thursday, March 31st 2022, 3:56:00 pm
date modified: Thursday, March 31st 2022, 4:54:03 pm
title: Provide the Redux Store to React
---

# Provide the Redux Store to React

```js
import React from 'react'  
import ReactDOM from 'react-dom'  
import './index.css'  
import App from './App'  
import { store } from './app/store'  
import { Provider } from 'react-redux'  
  
ReactDOM.render(  
<Provider store={store}>  
<App />  
</Provider>,  
document.getElementById('root')  
)
```

---

###### Citation

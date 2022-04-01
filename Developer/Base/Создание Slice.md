---
aliases: 
tags: 
date created: Thursday, March 31st 2022, 4:56:26 pm
date modified: Friday, April 1st 2022, 9:45:45 am
title: Создание Slice
---

# Создание Slice

Можно писать мутирующую логику, по под капотом используется библиотека Immer, она заботится об иммутабельности за нас


```js
import { createSlice } from '@reduxjs/toolkit'  
  
const initialState = {  
value: 0,  
}  
  
export const counterSlice = createSlice({  
name: 'counter',  
initialState,  
reducers: {  
increment: (state) => {  
// Redux Toolkit allows us to write "mutating" logic in reducers. It  
// doesn't actually mutate the state because it uses the Immer library,  
// which detects changes to a "draft state" and produces a brand new  
// immutable state based off those changes  
state.value += 1  
},  
decrement: (state) => {  
state.value -= 1  
},  
incrementByAmount: (state, action) => {  
state.value += action.payload  
},  
},  
})  
  
// Action creators are generated for each case reducer function  
export const { increment, decrement, incrementByAmount } = counterSlice.actions  
  
export default counterSlice.reducer

```

---

###### Citation

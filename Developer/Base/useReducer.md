---
aliases: null
date created: 2022-01-28 16:17
date updated: 2022-01-28 16:17
---

А `useReducer` позволяет вам управлять локальным состоянием сложных компонентов с помощью редьюсера:

```js
const [state, dispatch] = useReducer(reducer, initialState, init)	

```

### reducer
Редьюсер - ф-я, хранит логику по изменение данных. Обычно реализовывается с помощью switch. Принимает в аргументы сами данные и объект события action. switch проверяет поле action.type (строка с название) и выполняет какую-то логику по изменение данных.

Помимо type, можно передавать payload - это новое значение

```jsx
function reducer(state, action) {
switch (action.type) {
	case 'plus':
		ruturn {...state, count: state.count + 1};
	case 'minus':
		ruturn {...state, count: state.count - 1};
	case 'setName	':
		ruturn { count: 0, name: action.payload};
	default:
		return state;
		
		}

}


```

### initialState

Может быть задан явно. Если начальное значение приходит из пропсов то его можно обработать в init.

### init
ф-и которая помогает преобразовать данные для initialState. Может использованться для сброса с начальному состоянию. Но можно и вообще не исопльзовать

### dispatch

В вызов dispatch передаем ему action. По тиму экшина reducer реашет какая операцая должнна быть выполнена





---

###### Citation

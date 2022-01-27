---
aliases: null
date created: 2022-01-23 16:39
date updated:
---

Для Function Declaration хостинг работает. Можно использовать до объявления,
>Никогда не исползовать в блоках  if/else

Для Function Expression хостинг не работает

### Вопросы интервью по хостингу ф-й

#### Question 1
```js
var a = 1;
function b() { 
	a = 10;  return;
	function a() {}}
b();
console.log(a);
```

Ответ: 1. Так получилось из за того что внутри ф-и `b` появилась своя `a`. Эта `а` ф-я и она всплывет на вверх и теперь есть локальная `a`. Значит `a = 10;` не меняет глобальную `а`, меняет только внутреннюю.
#### Question 2
```js
function foo(){    
	function bar() {       
		return 3;    
	}    
	return bar();    
	function bar() {       
		return 8;    
	}
}
alert(foo());
```
Ответ 8. Обе ф-и bar но та, что возвращает 8 будет второй, ниже в коде.

#### Question 3
```js
function parent() {    
	var hoisted = "I'm a variable";    
	function hoisted() {        
		return "I'm a function";   
	}    
	return hoisted(); 
}

console.log(parent());

```

Ответ. **“TypeError: hoisted is not a function”**
Сложная задача. При переменной и ф-и в одним именем, выбирается ф-я. Подъем пеерменной просто игнорируются. В даном случае не поднятая переменная просто переопределяет поднятую ф-ю. 
Хостинг переменных происходит с undefined, а ф-и поднимаются вместе с определением. 

#### Question 4
```js
alert(foo());
function foo() {  
	var bar = function() { return 3;  };  
	return bar();  
	var bar = function() { return 8; };
}
```
Ответ 3. Такие ф-и не хостятся.

#### Question 5
```js
var myVar = 'foo';
(function() {  
	console.log('Original value was: ' + myVar); 
	var myVar = 'bar';  
	console.log('New value is: ' + myVar);
})();

```
Ответ “Original value was: undefined”, “New value is: bar”

---

###### Citation


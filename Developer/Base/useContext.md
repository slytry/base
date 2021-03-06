---
tags: 
aliases: null
date created: 2022-01-28 16:16
date updated:
date modified: Monday, June 27th 2022, 9:06:23 pm
---

# useContext

Решает проблему передачи пропсов от самомго верхнего компонента к самому нижнему, когда промежуточные компоненты значение и не используют.

Этот хук работает в связке в `<MyContext.Provider`. Он просто позволяет импортировать уже созданный контекст в определенный компонент

```js
const value = useContext(MyContext);
```

### Полный цикл

Пример работы с use контекст на примере темы

##### Создаем контекст

Создаем контекст

```
const ThemeContext = React.createContext();
```

Создаем значение

```js
const [theme] = useState('white')
```

##### Создаем провайдета

Провойдет оборачивает другие компоненты. Все дерево компоненто внутри будет иметь доступ к значение контекста. В значении передаем тему.

```jsx
return (

 <ThemeContext.Provider value={theme}>
      <Toolbar />
 </ThemeContext.Provider>

)
```

##### Принимаем значение

Внутри любого вложенного компонента можно использовать хук

```jsx

 const theme = useContext(ThemeContext);

```

---

###### Citation


---
aliases: null
date created: 2022-02-15 13:24
date updated:
---
Если два файла формата md.
Установлена библиотека gray-matter для работы  [YAML](https://github.com/nodeca/js-yaml) front-matter заголовками. В этих файлах есть data и title.


```js
import fs from 'fs'// В `fs` модуль позволяет взаимодействовать с файловой системой способом, смоделированным на основе стандартных функций POSIX.
import path from 'path' // Модуль предоставляет множество очень полезных функций для доступа и взаимодействия с файловой системой.
import matter from 'gray-matter'
import process from 'process'


const postsDirectory = path.join(process.cwd(), 'posts') // Объект process предоставляет информацию о текущем процессе Node.js и управляет им. Хотя он доступен как глобальный, рекомендуется явно обращаться к нему через require или import:

export function getSortedPostsData() {
  // Get file names under /posts
  const fileNames = fs.readdirSync(postsDirectory)
  
  const allPostsData = fileNames.map(fileName => {
    // Remove ".md" from file name to get id
    const id = fileName.replace(/\.md$/, '')

    // Read markdown file as string
    const fullPath = path.join(postsDirectory, fileName)
    const fileContents = fs.readFileSync(fullPath, 'utf8')

    // Use gray-matter to parse the post metadata section
    const matterResult = matter(fileContents)

    // Combine the data with the id
    return {
      id,
      ...matterResult.data
    }
  })
  // Sort posts by date
  return allPostsData.sort(({ date: a }, { date: b }) => {
    if (a < b) {
      return 1
    } else if (a > b) {
      return -1
    } else {
      return 0
    }
  })
}
```

---

###### Citation


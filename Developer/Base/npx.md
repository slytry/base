---
tags: 
aliases: null
date created: 2022-03-17 10:08
date modified: Monday, March 28th 2022, 9:33:17 am
title: npx
---

# npx

`npx` позволяет запускать пакеты `Node.js`, не устанавливая его и не добавляя зависимости в ваш проект

### 1. Запустить сервер

Например, у вас есть статический веб-сайт, и вам нужно поднять сервер на `localhost`.

```clike
npx http-server .
```

Сам пакет доступен [здесь](https://github.com/http-party/http-server).

### 2. Создать .gitignore файл

Например, мы создаём новый `Node.js` проект и хотим создать `.gitignore` для этой технологии.

```clike
npx gitignore node
```

Доступны и другие варианты, посмотрите [документацию пакета](https://github.com/msfeldstein/gitignore).

### 3. Подождать, пока определённый порт будет открыт

Например, вам нужно написать цепочку команд, вы хотите, чтобы сначала полностью поднялся `Docker` контейнер, а потом выполнилась команда.

```clike
npx wait-port 9000
```

Эта команда выполнится только тогда, когда что-то откроет порт `9000`.

Сам пакет доступен [здесь](https://github.com/dwmkerr/wait-port).

### 4. Освободить порт

Например, вы не можете стартануть сервер, потому что что-то уже занимает порт. Вам не важно, что это, вы хотите просто убить этот процесс.

```clike
npx kill-port 9000
```

Сам пакет доступен [здесь](https://github.com/tiaanduplessis/kill-port).

### 5. Сделать package.json красивым

Эта команда отсортирует содержимое вашего `package.json`. Зависимости будут размещены в алфавитном порядке и даже больше!

```clike
npx sort-package-json
```

Сам пакет доступен [здесь](https://github.com/keithamus/sort-package-json).

### 6. Управляем обновлением npm-зависимостей

Представьте, что вам нужно работать с когда-то заброшенным `Node.js` проектом. Его не трогали уже 6 месяцев, куча зависимостей устарела. Первым делом хорошо бы их обновить. Все зависимости обновлять небезопасно, что-то может сломаться, а тестов мало. Давайте обновим только те, где новые версии содержат минорные изменения.

```clike
npx npm-check-updates --target minor -u
```

Это только малая часть того, что может пакет [npm-check-updates](https://github.com/raineorshine/npm-check-updates).

### 7. Быстрый цифровой дождь из Матрицы

```clike
npx matrix-rain
```

[Сам пакеt](https://github.com/nojvek/matrix-rain)

---

###### Citation

- [Представляем npx: утилиту для запуска npm-пакетов](https://medium.com/devschacht/introducing-npx-an-npm-package-runner-a72a658cd9e6)

https://nodejs.dev/learn/the-npx-nodejs-package-runner - запустить нода ноду определенной версии

[awesome-npx](https://github.com/junosuarez/awesome-npx)

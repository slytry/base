---
tags: 
aliases: 
---
GULP - система для написания произвольных задач
### Гайды
- [[Установка gulp]]
- [[Потоки Vinyl FS]]
- [[Сборка стилей gulp]]
### Плагины
##### Общие
- [gulp-if](https://www.npmjs.com/package/gulp-if) добавляем условия чтобы делать сборки без карты 
- [gulp-debug]() дебагер
- [run-sequence](https://www.npmjs.com/package/run-sequence) Последовательный запуск плагинов 
- [del](https://www.npmjs.com/package/del) удаление файлов
- [gulp-concat](https://www.npmjs.com/package/gulp-concat) для конкатинации ("склеивания" файлов вместе) 
- [gulp-notify](https://learn.javascript.ru/screencast/gulp#gulp-errors) помогает отлавливать ошибки, присылает уведомление
- [gulp-plumber](https://learn.javascript.ru/screencast/gulp#gulp-errors) вешает обработчик ошибки на все потоки
- [combiner](https://learn.javascript.ru/screencast/gulp#gulp-errors) вешает обработчик ошибки на все потоки  другой способ

##### Производительность и отслеживание
- [gulp-newer]() убирает лишнее копирование не изменившихся файлов
- [gulp-remember]() кэширует проходящие сквозь файлы. Нужно когда мы следим за файлами и пересобираем только изменившиеся через since, но дальше используем конкат, очевидно что склеится должны старые файлы тоже
- [gulp-cached]() исключает одинаковые файлы. Если мы удалили файл, а потом вернули через ctr+z, его не увидит сборщик. (обычно используется since last run)
- [gulp-cache]() кэширует результат обработки на диск
- [browserSync](https://learn.javascript.ru/screencast/gulp#gulp-browsersync) обновляет браузер

##### Изображения
- Оптимизация изображений [gulp-imagemin](https://www.npmjs.com/package/gulp-imagemin)
- Конвертация изображений в формате webp [gulp-webp](https://www.npmjs.com/package/gulp-webp)
- Переименование файлов [gulp-rename](https://www.npmjs.com/package/gulp-rename)
- Шаблонизация HTML [gulp-posthtml](https://www.npmjs.com/package/gulp-posthtml)  и [posthtml-include](https://www.npmjs.com/package/posthtml-include)
- Сборка SVG-спрайтов [gulp-svgstore](https://www.npmjs.com/package/gulp-svgstore)


---
###### Citation
- [Насnройка GULP + Babel](https://only-to-top.ru/blog/tools/2019-10-20-gulp-babel.html)
-  [Web app generator](https://github.com/yeoman/generator-webapp)
- [Глубокая настройка watch](https://learn.javascript.ru/screencast/gulp#gulp-watch-perf)
Date: 2021-11-18T15:58

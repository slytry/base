---
tags: 
aliases: 
---
Плагины
- Препроцессор [Gulp-sass](https://www.npmjs.com/package/gulp-sass), [sass]()
- Чтобы в DevTools было понятно, из какого файла взялись стили [gulp-sourcemaps](https://www.npmjs.com/package/gulp-sourcemaps)
- Чтобы scss-файлы можно было импортировать не по одному, а целыми директориями [gulp-sass-bulk-importer](https://www.npmjs.com/package/gulp-sass-bulk-importer)
- Для автоматической расстановки префиксов [gulp-autoprefixer](https://www.npmjs.com/package/gulp-autoprefixer)
- Минификация, очистки лишнего CSS [gulp-csso](https://www.npmjs.com/package/gulp-csso) ([CSS Minification Benchmark](http://goalsmashers.github.io/css-minification-benchmark/))



Установка:
```
npm i --save-dev gulp-sass gulp-sass-bulk-importer gulp-autoprefixer gulp-csso gulp-concat gulp-sourcemaps
```

Конфигурация 
```js
'use strict';

const gulp = require('gulp'),
	gulpIf = require('gulp-if'),
	del = require('del'),
	sass = require('gulp-sass')(require('sass')),
	maps = require('gulp-sourcemaps'),
	csso = require('gulp-csso');

	const isDevelopment = !process.env.NODE_ENV || process.env.NODE_ENV == 'development';

gulp.task('scss', function () {
	return gulp.src('src/scss/*.scss')
	.pipe(gulpIf(isDevelopment, maps.init()))
	.pipe(sass())
	.pipe(gulpIf(isDevelopment, maps.write()))
	.pipe(gulp.dest('public/css'));
});

gulp.task('clean', function () {
 return del('public');
});

gulp.task('assets', function () {
 return gulp.src('src/assets/**') 
 .pipe(gulp.dest('public'));
});



gulp.task('build', gulp.series('clean', gulp.parallel('scss', 'assets')));
```


---
###### Citation

Date: 2021-12-22T10:19

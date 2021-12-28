---
tags: 
aliases: 
---
app - глобальная переменная

Другой подход. Во всех видео до этого использовался gulp для отслеживания изменений, и потом запускался browser-sync.stream(). stream это что-то от ноды. Теперь же сам плагин следит. Оказывается он так может, и внутри у него все тот же chokidar
```js
import browserSync from 'browser-sync';

const server = (done) => {
  browserSync.create().init({
    server: {
      baseDir: app.config.dist.root,
    },
    files: [
      `${app.config.dist.html}/`,
      `${app.config.dist.root}/*.*`,
      `${app.config.dist.css}/`,
      `${app.config.dist.js}/`,
      {
        match: [`${app.config.dist.images}/**/*`],
        fn() {
          this.reload();
        },
      },
    ],
    open: false,
    notify: false,
  });
  done();
};

export default server;

```

Простое удаление
```js 
import del from 'del';

const clean = () => del(app.config.dist.root);

export default clean;

```
---
###### Citation
Date: 2021-12-28T23:56

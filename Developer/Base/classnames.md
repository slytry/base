---
aliases: null
date created: 2022-02-18 09:31
date updated:
---

При использовании модульного css  удобно забиндить объект с классами

```js
var classNames = require('classnames/bind');

var styles = {
  foo: 'abc',
  bar: 'def',
  baz: 'xyz'
};

var cx = classNames.bind(styles);

var className = cx('foo', ['bar'], { baz: true }); // => "abc def xyz"
```

---

###### Citation
https://ru.hexlet.io/courses/js-react/lessons/classnames/theory_unit
<https://www.npmjs.com/package/classnames>
---
aliases: 
tags: 
date created: Thursday, May 19th 2022, 9:35:47 am
date modified: Friday, May 20th 2022, 10:01:15 pm
---

# Добавить шрифты Storybook
```
	config.resolve.roots = [path.resolve(__dirname, '../public')];
		config.module.rules.push({
			test: /\.(woff2)$/i,
			type: 'asset/resource',
		});
```

---

###### References

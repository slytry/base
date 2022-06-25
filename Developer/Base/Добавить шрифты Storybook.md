---
aliases: 
tags: 
date created: Thursday, May 19th 2022, 9:35:47 am
date modified: Monday, June 20th 2022, 11:51:52 am
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

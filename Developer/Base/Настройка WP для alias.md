---
tags: 
aliases: null
date created: 2022-03-09 11:36
date updated:
date modified: Thursday, March 17th 2022, 9:36:45 am
---

# Настройка WP для alias

jsconfig

```js
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/components/*": ["components/*"],
      "@/hooks/*": ["hooks/*"],
      "@/lib/*": ["lib/*"],
      "@/styles/*": ["styles/*"]
    }
  }
}

```

Только такой webpack

```js
const path = require('path');

webpackFinal: async (config, { configType }) => {
config.resolve.alias = {
      ...config.resolve?.alias,
      '@': path.resolve(__dirname, '../'),
      '@/components': path.resolve(__dirname, '../components/'),
      '@/hooks': path.resolve(__dirname, '../hooks/'),
      '@/lib': path.resolve(__dirname, '../lib/'),
      '@/styles': path.resolve(__dirname, '../styles/'),
    };
	
	return config
}


```

---

###### Citation

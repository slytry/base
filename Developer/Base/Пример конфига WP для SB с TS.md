---
aliases: 
tags: 
date created: Saturday, June 18th 2022, 11:07:55 am
date modified: Saturday, June 18th 2022, 11:09:19 am
---

# Пример конфига WP для SB с TS

```js
const TsconfigPathsPlugin = require('tsconfig-paths-webpack-plugin');
const path = require('path');

module.exports = {
	stories: ['../components/**/*.stories.@(js|jsx|ts|tsx)'],
	addons: [
		'@storybook/addon-links',
		'@storybook/addon-essentials',
		'@storybook/addon-interactions',
	],
	framework: '@storybook/react',
	core: {
		builder: '@storybook/builder-webpack5',
	},
	webpackFinal: async (config) => {
		config.resolve.roots = [path.resolve(__dirname, '../public')];

		config.resolve.plugins = [
			...(config.resolve.plugins || []),
			new TsconfigPathsPlugin({
				extensions: config.resolve.extensions,
			}),
		];
		config.module.rules.push({
			test: /\.scss$/i,
			use: [
				'style-loader',
				'css-loader',
				{
					loader: 'sass-loader',
					options: {
						sassOptions: {
							includePaths: [path.join(__dirname, '../styles/')],
						},
					},
				},
			],
			include: path.resolve(__dirname, '../'),
		});
		config.module.rules.push({
			test: /\.(woff2)$/i,
			type: 'asset/resource',
		});

		return config;
	},
};

```

---

###### References

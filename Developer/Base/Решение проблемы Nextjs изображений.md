---
aliases: null
date created: 2022-03-03 15:43
date updated:
---

Because Storybook runs these components in isolation of Next.js framework-integrations, we need to configure it in two important ways:

1.  Serve the Next.js `public` directory in Storybook
2.  Add the `unoptimized` prop to Next.js Image component in all stories

### 1. Serve the public directory in Storybook

The `sb init` script creates two Storybook scripts in our `package.json`. Update both of them to serve the `public`directory (where Next.js images are kept). The CLI option we use for this is `-s`. or `--static-dir`.

```diff
// package.json

"scripts": {
-    "storybook": "start-storybook -p 6006",
-    "build-storybook": "build-storybook"
+    "storybook": "start-storybook -p 6006 -s ./public",
+    "build-storybook": "build-storybook -s public"
}
```

Find more CLI options in our [CLI options doc](https://storybook.js.org/docs/react/api/cli-options). And learn more about [Serving Static Files via Storybook](https://storybook.js.org/docs/react/configure/images-and-assets#serving-static-files-via-storybook).

### 2. Use the unoptimized prop for Next.js Images in Storybook

Everywhere that the Next.js Image component is used, images are served from a `/_next`-prefixed path. We want to utilize Next Image's prop APIs and attributes, but we don't want to require that the Next.js dev server be running. We can do exactly this with the `unoptimized` prop. But how do we do this in Storybook but not Next.js 🤔

With a bit of module trickery, we can de-optimize Next.js Image only in stories.

```jsx
// .storybook/preview.js
import * as NextImage from "next/image";

const OriginalNextImage = NextImage.default;

Object.defineProperty(NextImage, "default", {
  configurable: true,
  value: (props) => <OriginalNextImage {...props} unoptimized />,
});
```

This snippet of configuration modifies how Storybook evaluates the `next/image` module. Anywhere that Next.js Image's default export is used, the `unoptimized` prop is applied.

Restart your server and check out the Vercel SVG at the bottom. We're back in business!

For more information on this technique, read _How to Use the Next.js Image Component in Storybook_ — a fantastic post by [Jonas Schumacher](https://dev.to/jonasmerlin).

---

###### Citation


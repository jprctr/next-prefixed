<div align="center">
  <img width="200" height="200"
    src="https://seeklogo.com/images/N/next-js-logo-7929BCD36F-seeklogo.com.png">
  <h1>next-prefixed</h1>
  <p>Prefix next links and images. Useful when serving from basePath.</p>
</div>

## Installation

```sh
yarn add next-prefixed
```

### Usage

`next-prefixed` exports components for rendering prefixed links and images. It also exports a function to prefix any url.

To set the prefix for the URLs, set the `assetPrefix` in your `next.config.js`.

```js
const debug = process.env.NODE_ENV !== 'production';
const assetPrefix = debug ? '' : '/your_prefix/';

module.exports = withPlugins([withCSS, withMDX, withBlog], {
  pageExtensions: ['js', 'mdx'],
  assetPrefix,
  publicRuntimeConfig: {
    assetPrefix
  }
});
```

#### prefixURL

```js
import { prefixURL } from 'next-prefixed';

prefixURL('/blog'); // => my_prefix/blog
```

#### Image

Passes all props to HTML `img` tag.

```js
import { Image } from 'next-prefixed';

const Example = () => <Image src="pony.png" alt="Valiant Horse" />;
```

#### Link

Passes all props to next.js `Link` component.

```js
import { Link } from 'next-prefixed';

const Example = () => <Link to="/blog" />;
```

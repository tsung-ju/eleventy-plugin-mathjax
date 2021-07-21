# eleventy-plugin-mathjax

Eleventy plugin for server-side MathJax rendering.

## Installation

```sh
npm install eleventy-plugin-mathjax
```

```js
const mathjaxPlugin = require("eleventy-plugin-mathjax");

module.exports = function (eleventyConfig) {
  eleventyConfig.addPlugin(mathjaxPlugin);
};
```

### Options

Optionally pass in an options object as the second argument to addPlugin to further customize this plugin pack.

For example, to use the CommonHTML output format instead of SVG:

```js
eleventyConfig.addPlugin(mathjaxPlugin, {
  output: "chtml",
  chtml: {
    fontURL:
      "https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2",
  },
});
```

#### output

Output format for math equations. Supports `"svg"` and `"chtml"`. Defaults to `"svg"`.

#### tex

Options for MathJaX's TeX input processor.

Defaults to:

```js
{
  packages: /* all packages */,
  inlineMath: [
    ["$", "$"],
    ["\\(", "\\)"],
  ],
}
```

See [here](https://docs.mathjax.org/en/latest/options/input/tex.html) for full options.

#### svg

Options for MathJaX's SVG output processor.

Defaults to:

```js
{
  fontCache: "global",
}
```

See [here](https://docs.mathjax.org/en/latest/options/output/svg.html) for full options.

#### chtml

Options for MathJaX's CommonHTML output processor. Defaults to `{}`.

See [here](https://docs.mathjax.org/en/latest/options/output/chtml.html) for full options.

#### adaptor

Options for MathJaX's lite DOM adaptor. Useful for passing size hints to MathJaX, e.g. `{ fontSize: 18 }`. Defaults to `{}`.

See [here](https://github.com/mathjax/MathJax-src/blob/master/ts/adaptors/liteAdaptor.ts) for full options.

# postcss-plugin-color-functions

[PostCSS](https://github.com/postcss/postcss) plugin to implement commonly used color functions, including ant-design's colorPalette function and SASS/compass color functions.

Inspired, and modified from, [postcss-color-function](https://github.com/postcss/postcss-color-function),[postcss-sass-color-functions](https://github.com/adam-h/postcss-sass-color-functions).

## Installation

```bash
npm install postcss-plugin-color-functions
```

## Usage

```js
// dependencies
var fs = require("fs")
var postcss = require("postcss")
var sassColorFunctions = require("postcss-plugin-color-functions")

// css to be processed
var css = fs.readFileSync("input.css", "utf8")

// process css
var output = postcss()
  .use(sassColorFunctions())
  .process(css)
  .css
```

Using this `input.css`:

```css
body {
  background-color: mix(#255073, #3c749e, 25%);
  color: colorPalette(#00a854, 5);
}

```

you will get:

```css
body {
  background-color: rgb(54, 107, 147);
  color: #3dbd7d;
}
```

Checkout [tests.js](tests.js) for examples.

## Currently Supported functions

- `colorPalette(color, index)`
- `mix(one, two, weight)`
- `rgba(color, alpha)`
- `darken(color, amount)`
- `lighten(color, amount)`
- `tint(color, amount)`
- `shade(color, amount)`

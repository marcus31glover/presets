# Typescript preset for Storybook

One-line Typescript w/ docgen configuration for storybook.

## Basic usage

```
yarn add -D @storybook/preset-typescript react-docgen-typescript-loader ts-loader
```

Then add the following to `.storybook/presets.js`:

```js
module.exports = ["@storybook/preset-typescript"];
```

## Advanced usage

You can pass configurations into the Typescript or Docgen loaders using the `tsLoaderOptions`, `tsDocgenLoaderOptions`, and `include` options in `.storybook/presets.js`, e.g.:

```js
const path = require("path");

module.exports = [
  {
    name: "@storybook/preset-typescript",
    options: {
      tsDocgenLoaderOptions: {
        tsconfigPath: path.resolve(__dirname, "../tsconfig.json")
      },
      include: [path.resolve(__dirname, "../src")]
    }
  }
];
```

You also can enable Typescript transpilation on [manager](https://storybook.js.org/docs/addons/writing-addons/) side, by setting the `transpileManager` option to `true`, e.g.:

```js
const path = require("path");

module.exports = [
  {
    name: "@storybook/preset-typescript",
    options: {
      transpileManager: true
    }
  }
];

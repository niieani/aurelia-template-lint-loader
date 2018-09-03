# Aurelia Template Lint Loader for Webpack 2

[![Greenkeeper badge](https://badges.greenkeeper.io/niieani/aurelia-template-lint-webpack-loader.svg)](https://greenkeeper.io/)

## Usage

Apply the aurelia-template-lint-webpack-loader in your webpack configuration, enforcing the rule as `'pre'`:

``` javascript
module.exports = {
  module: {
    rules: [{
      test: /\.html$/i,
      enforce: 'pre',
      include: [
        // where your aurelia templates are contained:
        path.resolve('src')
      ],
      use: [{
        loader: 'aurelia-template-lint-webpack-loader',
        options: {
          // you can pass an configuration class
          // config reference https://github.com/MeirionHughes/aurelia-template-lint#config
          configuration: options && options.config,

          // aurelia errors are displayed by default as warnings
          // set emitErrors to true to display them as errors
          emitErrors: false,

          // aurelia does not type check by default
          // if you want to do type checking set
          // typeChecking to true and provide
          // the right fileGlobs
          // reference https://github.com/MeirionHughes/aurelia-template-lint#static-type-checking
          // these settings can also be passed with configuration above
          typeChecking: true,
          reflectionOpts: {
            sourceFileGlob: './**/*.ts',
            typingsFileGlob: './**/*.d.ts',
          }
        }
      }]
    }]
  }
}

```
## More options and configuration
Behind the scenes, the loader is using the following linter https://github.com/MeirionHughes/aurelia-template-lint

## Installation

``` shell
npm install aurelia-template-lint-loader --save-dev
```

## License

This is a Webpack 2 + TypeScript fork of https://github.com/w3tecch/aurelia-template-lint-loader.

MIT (http://www.opensource.org/licenses/mit-license.php)


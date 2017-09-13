<div align="center">
  <a href="https://github.com/webpack/webpack">
    <img width="200" height="200" src="https://webpack.js.org/assets/icon-square-big.svg">
  </a><a href="https://github.com/WeltN24/react-web-component"><img alt="React Web Component Logo" src="https://raw.githubusercontent.com/WeltN24/react-web-component-style-loader/master/docs/images/react-web-component-logo.png" height="200">
  </a>
</div>

# React Web Component Style Loader

Adds CSS to web components created by [react-web-component](https://github.com/WeltN24/react-web-component) by injecting a <code>&lt;style&gt;</code> tag to the web component

* [What is it, how does it work and when to use it](#what-is-it-how-does-it-work-and-when-to-use-it)
* [Installation](#installation)
* [Basic Usage](#basic-usage)
* [Maintainers](#maintainers)

## What is it, how does it work and when to use it

`react-web-component-style-loader` is a companion to [react-web-component](https://github.com/WeltN24/react-web-component). When creating a web component we face the issue that we need to attach all styles to the shadow dom of the component rather than _somewhere on the page_ while still being able to use state of the art tooling (webpack) and write modular CSS across multiple files. 

This is where this loader comes in. It will gather all CSS you use in your webpack project and store it internally, accessible to `react-web-component`. When you use this project and `react-web-component`, `react-web-component` will know where to find the CSS and write it to the shadow dom of the web component you created with it.

In essence `react-web-component-style-loader` is a fork of [style-loader](https://github.com/webpack-contrib/style-loader) and their README can be used for detailed usage and further information. A little more technical explanation of how this loader works: The original style loader loads the CSS from your project, creates `style` nodes and appends them to your website. The only real difference in this loader is that it writes the `style` nodes to an array in our JavaScript and `react-web-component` will find them and append them to the web component. It is that easy. 

## Installation

```
yarn add react-web-component-style-loader --dev
```

## Basic Usage

It's recommended to combine `react-web-component-style-loader` with the [`css-loader`](https://github.com/webpack/css-loader)

**component.js**
```js
import './file.css'
```

**webpack.config.js**
```js
{
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [
          { loader: "react-web-component-style-loader" },
          { loader: "css-loader" }
        ]
      }
    ]
  }
}
```

## Maintainers

<table>
  <tbody>
    <tr>
      <td align="center">
        <a href="https://github.com/LukasBombach">
          <img width="150" height="150" src="https://github.com/LukasBombach.png?v=3&s=150">
          </br>
          Lukas Bombach
        </a>
      </td>
    </tr>
  <tbody>
</table>
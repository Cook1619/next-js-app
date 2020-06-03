---
title: "Styling in React"
date: "2020-06-03"
---

#Here a few different ways to style in React


Inline Styles
```jsx
import React from "react";
import ReactDOM from "react-dom";

ReactDOM.render(
  <div>
    <h1 style={{ color: 'blue'}}>Hello World</h1>
  </div>,
  document.getElementById("root")
);
```

From a CSS File
be sure to import your css file from whereever its located in your project
```jsx
import React from "react";
import ReactDOM from "react-dom";
import './main.css'

ReactDOM.render(
  <div>
    <h1 className="heading">Hello World</h1>
  </div>,
  document.getElementById("root")
);
```
```css
.heading {
    color: red;
    font-size: 20px
}
```
You can create objects which you can style like normal CSS to omit the double brackets
```jsx
import React from "react";
import ReactDOM from "react-dom";

//This needs to be treated with camel casing for keys and strings values
const headingStyle = {
  color: 'red',
  fontSize: '20px'
}

ReactDOM.render(
  <div>
    <h1 className={headingStyle}>Hello World</h1>
  </div>,
  document.getElementById("root")
```

To use SCSS you need to intall a couple dependencies and configure your webpack file something like this
```js
const path = require('path');

module.exports = {
  entry: './src/app.js',
  output: {
    path: path.join(__dirname, 'public'),
    filename: 'bundle.js'
  },
  module: {
    rules: [{
      loader: 'babel-loader',
      test: /\.js$/,
      exclude: /node_modules/
    }, {
      test: /\.s?css$/,
      use: [
        'style-loader',
        'css-loader',
        'sass-loader'
      ]
    }]
  },
  devtool: 'cheap-module-eval-source-map',
  devServer: {
    contentBase: path.join(__dirname, 'public')
  }
};
```

Dependencies are css-loader, node-sass, sass-loader, style-loader
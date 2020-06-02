---
title: "React Basics"
date: "2020-06-1"
---

# So React is known as a single page application along with the other popular frontend
# libraries/frameworks, and thats because a single html document will get server to the 
# browser. This is what that document might look like.
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>JSX</title>
    <link rel="stylesheet" href="styles.css" />
  </head>

  <body>
    <div id="root"></div>
    <script src="../src/index.js" type="text/javascript"></script>
  </body>
</html>

```
## The important line in here is the div with the id of root

# In a index.js file typically located in a src directory you will need to do a few things
## Import React and ReactDOM, ReactDOM will have a render method which is the entry point into the app
## This functions first arguement can be thought of as what to show? The second would be where to show it?
## The third is optionally which is a callback to tells us when the render function has completed
```js
import React from 'react';
imoport ReactDOM from 'react-dom';

ReactDom.render(<h1>Hello World</h1>, document.getElementById('root'));
```
## Now that h1 would normally be a component, but this is just an example. Also this isn't HTML
## this is JSX and will actually get compiled down to this
```js
ReactDom.render(React.createElement("h1", null, "Hello World"), document.getElementById('root'));
```
### So it creates the h1 element, the second argument would be for an id or className if it had one
### and the third is the text in the element
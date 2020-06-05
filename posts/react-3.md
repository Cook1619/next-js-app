---
title: "Props in React"
date: "2020-06-05"
---

# Passing data to children components via props in react

### This is our main index.js file which imports our App component and
### tells react where to put our single page application
```js
import React from "react";
import ReactDOM from "react-dom";
import App from "./components/App";

ReactDOM.render(<App />, document.getElementById("root"));
```

### This is our App component, can be thought of as our parent component
### name, email, and phone are all being pass as an object to the Card component
```jsx
import React from "react";
import Card from './Card';

function App() {
  return (
    <div>
      <h1 className="heading">My Contacts</h1>
      <Card name="Tim" email="tim@gmail.com" number="677-333-2343">
      <Card name="Christy" email="christy@gmail.com" number="677-344-2343">
      <Card name="Jimbobb" email="tim@gmail.com" number="677-399-2343">
    </div>
  );
}

export default App;
```
### The Card component then takes in the argument props which is the object from above
### You can call this anything but props in the convention
```jsx
import React from 'react';

const Card = (props) => {
  const { name, img, phone, email } = props
  return (
    <div>
    <div className="card">
      <div className="top">
        <h2 className="name">{ name }</h2>
      </div>
      <div className="bottom">
        <p className="info">{ number }</p>
        <p className="info">{ email }</p>
      </div>
    </div>
  </div>
  )
}

export default Card;
```
### Now you can access the props you passed in from the App component via props
#### props.name, props.number, props.email
#### I destructured before the return method so I can just write name, number, email

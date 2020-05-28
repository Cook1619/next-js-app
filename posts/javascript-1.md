---
title: "Javascript OOP Concepts"
date: "2020-05-27"
---

# Object - an object contains key value pairs also called properties. It can also have functions within and object and their called methods. Let's take a simple example of a car. Every car has a color, a type, horsepower. Every care also performs actions like drive, and honking a horn. A simple object like this would look like this
```js
const car = 
{
    color: 'red',
    type: 'sedan',
    horsepower: 125
    drive() {
        return 'car is moving';
    },
    honk() {
        return 'honk honk'
    }
}
```
# Every Object is javascript inherits from at least one object, that is called the prototype
# You can also define objects using a constructor function. The convention of doing this is using a capital letter like this:
```js
    function Person(gender, age, height){
        this.gender = gender;
        this.age = age;
        this.height = height;
    }
```
# The new way to do is creating a class, which is just syntactic sugar
```js
class Person(){
    constructor(gender, age, height){
        //we can obmit the this keyword 
        gender
        age
        height
    }
}
```
# Then creating an instance of that car like this
```js
const matt = new Person('male', 33, 72)
```
# From the classes or constructor function you can create new instances, this process is called instantiation and the object instance is instantiated from the class
# We can create a Developer class which has the same properties as a person. This is known as inheritance, it can also have some properties that just the class Developer has.
```js
class Developer extends Person {
    constructor(gender, age, height){
        super(gender, age, height)// super is called to inherit the properties of the person class to pass them to the developer class
    }
}
```
---
title: "Typescript Objects"
date: "2020-05-28"
---

# When using typescript on an object, it actually infers the type of values for us

```js
const person 
{
    name: 'Matt',
    age 33
}
```
# Now there is nothing special about this object but 'under the hood'
# this is what typescript is doing for us
```ts
const person: 
{
    name: string;
    age: number
} = 
{
    name: 'Matt',
    age: 33
}
```
# When we create an object in typescript it is infering the the datatypes
# being used upon creation of the object
# We also get an error underline if we try to access a value on an object
# which doesn't exist
```ts
//this would reset in an error right away, and when you compile your TS file
console.log(person.nickname)
```
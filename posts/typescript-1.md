---
title: "Typescript Basics"
date: "2020-05-26"
---

Learning the basics with typescript

```typescript
{
  //Its better to typecheck as function parameters as oppposed to doing it when declaring the variables
  function add(num1: number, num2: number) {
    return num1 + num2;
  }
  const number1 = 3;
  const number2 = 6;

  const result = add(number1, number2);
  console.log(result);
}
```

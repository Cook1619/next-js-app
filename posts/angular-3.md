---
title: "Angular Databinding"
date: "2020-05-29"
---

# What is data binding in angular?
## It's simply the communication between your component (typescript code)
## and your template(what the user sees)

# There are a couple different way to make use of databinding
## Property Binding
```html
    [property]="data"
```
## Event Binding, such as binding to a click event
```ts
    ('click')="expression"
```
## Two way binding with ngModel
```ts
    [(ngModel)] = "dataBeingBound(user)"
```

# Deeper dive on string interpolation, anything between {{}} is
# referred to as string interpolation
## At the end of the day only variables an items that return strings,
## or can easily be coverted to a string can be passed in this curly brackets
## Examples are strings, numbers, methods that return strings

```ts
import { Component } from '@angular/core';

//This component decorator tells typescript what to do with this class,
//Think of it as configuration for the class
@Component({
    //the html tag you want to use it as, must be unique
    selector: 'app',
    templateUrl: './app.component.html'
})

export class AppComponent {
    customerId: number = 1;
    customerStatus: string = 'paid'
    getCustomerStatus(){
        return this.customerStatus
    }
}
```
```html
<p>{{ 'Customer'}} with ID {{ customerId }} is {{ getCustomerStatus() }}</p>
```
## In the above example this is a simple template communicating with a component
## String interpolation is hapenning via a string be evaluated, a variable,
## and a method, which returns a number, which gets converted to a string

# Another key feature with Angular is propery binding
## Below I will show a very simple example of getting this done
```html
<button [disabled]="!allowNewCustomer">Add Customer</button>

```
```ts
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent implements OnInit {
  allowNewCustomer = false

  constructor() {
    setTimeout(() => {
      this.allowNewCustomer = true;
    }, 2000)
   }

  ngOnInit(): void {
  }
}
```
## Now the importants parts here the [disabled], we are not binding the 
## html attribute disabled. We are then binding the disabled attribute
## to the variable in our component allNewCustomer. So if that variable is 
## true it will disable the button, thats why we put a bang ! infront of the
## variable to flip it.
## We are then using a setTimeout to mock something happening.

# Another way to handle property binding in a contrived example from the 
# components data above

```html
<p [innerText] = "allowNewCustomer"></p>
```
## This will work because booleans can be cast as strings as well.
### In this example false will be displayed, then true after 2 seconds.

# Event binding
## the click event is one of the most used, so lets see it in action

```ts
@Component({
    //the html tag you want to use it as, must be unique
    selector: 'app',
    templateUrl: './app.component.html'
})

export class AppComponent {
    customerId: number = 1;
    customerStatus: string = 'paid'
    customerCreationStatus = 'Customer has not been created'
    getCustomerStatus(){
        return this.customerStatus
    }
    onCreateCustomer(){
        this.customerCreationStatus = 'Customer was created'
    }
}
```
```html
<button [disabled]="!allowNewCustomer" (click)="onCreateCustomer()">Add Customer</button>
<p>{{ customerCreationStatus }}</p>
```
## Now we are initially setting the value of the string to not creation
## We then creation a method which changes the value of that string to created
## Then in the template we add a click event handler which calls the method
## onCreateCustomer which will flip the value of the string

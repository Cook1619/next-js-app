---
title: "Angular Components"
date: "2020-05-26"
---

## The command to create Angular components via cli is

```
{
    ng generate component componentName
    //shorthand
    ng g c componentName
}
```

## How to nest components, here is our child components html template and component files

```html
<p>Server component</p>
```

```typescript
import { Component } from "@angular/core";

//This component decorator tells typescript what to do with this class,
//Think of it as configuration for the class
@Component({
  //the html tag you want to use it as, must be unique
  selector: "app-server",
  templateUrl: "./server.component.html",
})
export class ServerComponent {}
```

## Then in our parent component we have our html file and component file

```html
<app-server></app-server>
<app-server></app-server>
<app-server></app-server>
```

```typescript
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-servers",
  templateUrl: "./servers.component.html",
  styleUrls: ["./servers.component.css"],
})
export class ServersComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

## Then our app components template, component file, the module is the same as the starting cli module

```html
<h1>App Component</h1>
<app-servers></app-servers>
```

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  
}

```

## This code will render a heading with the paragraph tag Server Component three times, because that how many times we decided to render is here:

```html
<app-server></app-server>
<app-server></app-server>
<app-server></app-server>
```

---
title: "Angular Basics"
date: "2020-05-26"
---

## How and why Angular Applications are called SPAS (single page applications)

## Starting with the index.html file in the src folder you will see code like this, this is the file that is served

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>AngularPlayground</title>
    <base href="/" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link rel="icon" type="image/x-icon" href="favicon.ico" />
  </head>
  <body>
    <app-root></app-root>
  </body>
</html>
```

## app-root is the important element here, it is one component that the CLI created for us.

## This is our app.component.ts, here we see our app-root element component being created

```typescript
{
  import { Component } from "@angular/core";

  @Component({
    selector: "app-root",
    templateUrl: "./app.component.html",
    styleUrls: ["./app.component.css"],
  })
  export class AppComponent {}
}
```

## The very first file that runs in an Angular project is the main.ts file. This runs all the scripts angular needs to run, plus it bootstraps your app.module.

```typescript
import { enableProdMode } from "@angular/core";
import { platformBrowserDynamic } from "@angular/platform-browser-dynamic";

import { AppModule } from "./app/app.module";
import { environment } from "./environments/environment";

if (environment.production) {
  enableProdMode();
}

platformBrowserDynamic()
  .bootstrapModule(AppModule)
  .catch((err) => console.error(err));
```

## How does angular know about this component file? This is the job for modules in angular

```typescript
import { BrowserModule } from "@angular/platform-browser";
import { NgModule } from "@angular/core";

import { AppComponent } from "./app.component";
import { ServerComponent } from "./server/server.component";
import { ServersComponent } from "./servers/servers.component";

@NgModule({
  declarations: [AppComponent, ServerComponent, ServersComponent],
  imports: [BrowserModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

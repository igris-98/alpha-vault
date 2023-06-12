[[NgModule]]
[NgModule Vs JavaScript Module](https://angular.io/guide/architecture-modules#ngmodules-and-javascript-modules)
- NgModule system is different from, and unrelated to, the JavaScript Module system for managing collection of JavaScript objects.
- These are complementary module systems that you can use together to write your application.
- In JavaScript each _file_ is a module and all objects defined in the file belong to that module. The module declares some objects to be public by marking them with the `export` key word. Other JavaScript modules use _import statements_ to access public objects from other modules.

EX :

```typescript
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';

export class AppModule { }
```
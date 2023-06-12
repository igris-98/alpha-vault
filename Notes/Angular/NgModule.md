[[ANGULAR]]
#angular/NgModule #intoduction 
# Introduction :
- Angular Applications are **MODULAR**.
- Angular has its own modularity system called [**NgModule**](https://angular.io/guide/architecture-modules).
- NgModules are container for a [[COHESIVE]] block of a code dedicated to an application domain, a workflow, or a closely related set of capabilities.
- They can contain [[COMPONENT]], [[SERVICE]] provider and other code files whose scope is define by containing NgModule.
-  They can **import** functionality that is exported from other NgModules, and export selected functionality for use by other NgModules.

#NOTE 
### Every Angular application has at least one NgModule class, the root module, which is conventionally named AppModule and reside in a file name [[app.module.ts]]. You launch your application by *bootstrapping* the NgModule.


 #angular/NgModule #metadata 
# [NgModule metadata](https://angular.io/guide/architecture-modules#ngmodule-metadata) : 
- NgModule is defined by a class [[DECORATOR]] with @[NgModule()](https://angular.io/api/core/NgModule).
- NgModule decorator is a function that takes a single [[METADATA(A)]] object, whose properties describe the module.
- The most Important properties are as follows. 
	- **declarations** : The [[COMPONENT]], [[DIRECTIVE]],  and [[PIPE]] that belongs to this NgModule.
	- **exports** : The subset of declaration that should be visible and usable in the component template of other NgModules.
	- **imports** : Other modules whose exported classes are needed by component template declared in this NgModule.
	- **providers** : Creators of services that this NgModule contributes to the *global collection of services*. they accessible in all parts of the application. (You can also specify providers at the component level.)
	- bootstrap : The main application view, called the _root component_, which hosts all other application views. Only the _root NgModule_ should set the `bootstrap` property.

```javascript
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
@NgModule({
  imports:      [ BrowserModule ],
  providers:    [ Logger ],
  declarations: [ AppComponent, YourComponent, YourPipe, YourDirective ],
  exports:      [ AppComponent ],
  bootstrap:    [ AppComponent ]
})
export class AppModule { }
```

#angular/NgModule #JavascriptModule
# [[NgModule Vs JavaScript Module]]

#angular/NgModule #angular/library
# [[ANGULAR LIBRARY]] 

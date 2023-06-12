[[ANGULAR]]
#angular/decorator
# [Decorator](https://angular.io/guide/glossary#decorator--decoration) :
- A function that modifies a class or property definition.
- A decorator is also referenced as an _annotation_.
- TypeScript adds support for decorators.
- Angular defines decorators that attach metadata to classes or properties so that it knows what those classes or properties mean and how they should work.

#angular/decorator/class 
## [Class Decorator](https://angular.io/guide/glossary#class-decorator) : 
- A decorator that appears immediately before a class definition, which declare the class to be if the give type and provides metadata suitable to the type.
	- @Component()
	- @NgModule()
	- @Directive()
	- @Pipe()
	- @Injective()

#angular/decorator/class-field 
## [Class field Decorator](https://angular.io/guide/glossary#class-field-decorator) : 
- A decorator statement immediately before a field/property in a class definition that declares the type of field.
	- @Input()
	- @Output()
	- @ViewChild()
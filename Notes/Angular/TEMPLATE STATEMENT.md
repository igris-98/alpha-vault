[[TEMPLATE]]

#angular/template/statement

# [Template Statement](https://angular.io/guide/template-statements#template-statements) :
- Template statements are methods or properties that you can use in your HTML to respond to **user events**.
- With template statements, your application can engage users through actions such as displaying dynamic content or submitting forms.
- template statement/declaration appears in quotation marks to the right of the symbol `=` as in `(event)="statement"`.
- Like [[TEMPLATE EXPRESSION]], template statements use a language that looks like JavaScript. In addition, the template statements parser specifically supports both basic assignment (`=`) and chaining expressions with semicolons (`;`).
- Template statements are used for EVENT BINDING.

## [Statement Context](https://angular.io/guide/template-statements#statement-context) :
- Statements have a context —a particular part of the application to which the statement belongs.
- Statements can refer only to what's in the statement context, which is typically the component instance.
	-  For example, `deleteHero()` of `(click)="deleteHero()"` is a method of the component in the following snippet.
	```html
	<button type="button" (click)="deleteHero()">Delete hero</button>
	```
- The statement context may also refer to properties of the template's own context.
	- In the following example, the component's event handling method, `onSave()` takes the template's own `$event` object as an argument. On the next two lines, the `deleteHero()` method takes a [[TEMPLATE VARIABLE#[Template Input Variable](https://angular.io/guide/template-reference-variables template-input-variable) ]], `hero`, and `onSubmit()` takes a [[TEMPLATE VARIABLE#[Template Reference Variable](https://angular.io/guide/template-reference-variables understanding-template-variables)]], `#heroForm`.
	```html
	<button type="button" (click)="onSave($event)">Save</button>
	<button type="button" *ngFor="let hero of heroes" (click)="deleteHero(hero)">{{hero.name}}</button>
	<form #heroForm (ngSubmit)="onSubmit(heroForm)"> ... </form>
	```

#NOTE 
### Template context names take precedence over component context names.
###  However, the parser for template statements differs from the parser for template expressions.
### Template statements/declarations cannot see anything in the global namespace. They cannot see `window` or `document`. They can't call `console.log` or  `Math.max`.
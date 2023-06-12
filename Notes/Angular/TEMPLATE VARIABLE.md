[[TEMPLATE]]

#angular/template/variable/reference 
# [Template Reference Variable](https://angular.io/guide/template-reference-variables#understanding-template-variables) :
- It help you use data from one part of a template in another part of the template. Use template variables to perform tasks such as respond to user input or finely tune your application's forms.
- A template reference variable can refer to the following :
	- A DOM element within a template.
	- a directive or component.
	- a [TemplateRef](https://angular.io/api/core/TemplateRef) from an [ng-template](https://angular.io/api/core/ng-template)
	- a [web component](https://developer.mozilla.org/en-US/docs/Web/Web_Components "MDN: Web Components")

## Syntax : 
- In the template, you can use # or (ref- prefix) to declare a template reference variable.
```html
<input #phone placeholder="phone number" />
<!-- OR -->
<input ref-phone placeholder="phone number" />

<!-- lots of other elements -->

<!-- phone refers to the input element; pass its `value` to an event handler -->
<button type="button" (click)="callPhone(phone.value)">Call</button>
```

## [How Angular assigns values to template variables](https://angular.io/guide/template-reference-variables#how-angular-assigns-values-to-template-variables "Link to this heading") :
- Angular assigns a template variable a value based on where you declare the variable:
	- If you declare the variable on a component, the variable refers to the component instance.
	- If you declare the variable on a standard HTML tag, the variable refers to the element.
	- If you declare the variable on an `[<ng-template>](https://angular.io/api/core/ng-template)` element, the variable refers to a `[TemplateRef](https://angular.io/api/core/TemplateRef)` instance which represents the template. For more information on `[<ng-template>](https://angular.io/api/core/ng-template)`, see [How Angular uses the asterisk, `*`, syntax](https://angular.io/guide/structural-directives#asterisk) in [Structural directives](https://angular.io/guide/structural-directives).


## [Variable specifying a name](https://angular.io/guide/template-reference-variables#variable-specifying-a-name "Link to this heading") :
- If the variable specifies a name on the right-hand side, such as `#var`="[ngModel](https://angular.io/api/forms/NgModel)"`, the variable refers to the directive or component on the element with a matching `exportAs` name.

## [Template variable scope](https://angular.io/guide/template-reference-variables#template-variable-scope) : 
-  Template variables are scoped to the template that declares them.
-  Such as [`*ngIf`](https://angular.io/api/common/NgIf) and [`*ngFor`](https://angular.io/api/common/NgFor), or [`<ng-template>`](https://angular.io/api/core/ng-template) declarations create a new nested template scope.
- You cannot access template variables within one of these structural directives from outside of its boundaries.
#NOTE 
### The scope of a template reference variable is the entire template.
### Define a variable only once in the template so the runtime value remains predictable.


### [Accessing in a nested template](https://angular.io/guide/template-reference-variables#accessing-in-a-nested-template)

# [Template Input Variable](https://angular.io/guide/template-reference-variables#template-input-variable) :
- A _template input variable_ is a variable with a value that is set when an instance of that template is created. See [Structural Directive].
- The `let` keyword declares a template input variable that you can reference within template.

Example : 
```html
<div
  *ngFor="let hero of heroes; let i=index; let odd=odd; trackBy: trackById"
  [class.odd]="odd">
  ({{i}}) {{hero.name}}
</div>

<ng-template ngFor let-hero [ngForOf]="heroes"
  let-i="index" let-odd="odd" [ngForTrackBy]="trackById">
  <div [class.odd]="odd">
    ({{i}}) {{hero.name}}
  </div>
</ng-template>
```
 The input variables in this example are `hero`, `i`, and `odd`. The parser translates `let hero`, `let i`, and `let odd` into variables named `let-hero`, `let-i`, and `let-odd`. The `let-i` and `let-odd` variables become `let i=index` and `let odd=odd`. Angular sets `i` and `odd` to the current value of the context's `index` and `odd` properties.

The parser applies PascalCase to all directives and prefixes them with the directive's attribute name, such as ngFor. For example, the `[ngFor](https://angular.io/api/common/NgFor)` input properties, `of` and `trackBy`, map to `[ngForOf](https://angular.io/api/common/NgForOf)` and `ngForTrackBy`.

As the `[NgFor](https://angular.io/api/common/NgFor)` directive loops through the list, it sets and resets properties of its own context object. These properties can include, but aren't limited to, `index`, `odd`, and a special property named `$implicit`.

Angular sets `let-hero` to the value of the context's `$implicit` property, which `[NgFor](https://angular.io/api/common/NgFor)` has initialized with the hero for the current iteration.
[[TEMPLATE]]

#angular/template/expression
# [Template Expression](https://docs.angular.lat/guide/interpolation#template-expressions) :
- [alternative link](https://angular.io/guide/understanding-template-expr-overview)
- A template **expression** produces a value and appears within the double curly braces, `{{ }}`.
- Angular executes the expression and assigns it to a property of a binding target; the target could be an HTML element, a component, or a directive.
- In the property binding ([[BINDING#Property Binding]]), a template expression appears in quotes to the right of the  `=` symbol as in `[property]="expression"`.
-  Many JavaScript expressions are legal template expressions, with a few exceptions.
- You can't use JavaScript expressions that have or promote side effects, including:
	- Assignments ( `=`, `+=`, `-=`, `...`)
	- Operators such as `new`, `typeof`, `instanceof`, etc.
	- Chaining expressions with `;` or `,`
	- The increment and decrement operators `++` and `--`
	- Some of the ES2015+ operators
	- No support for the bitwise operators such as `|` and `&`
 - Template Expression are used for DATA BINDING.

## [Template Expression Guidelines](https://docs.angular.lat/guide/interpolation#expression-guidelines) :
### Simplicity
- Although it's possible to write complex template expressions, it's a better practice to avoid them.
- A property name or method call should be the norm, but an occasional Boolean negation, `!`, is OK. Otherwise, confine application and business logic to the component, where it is easier to develop and test.
### Quick execution
- Angular executes template expressions after every change detection cycle.
- Change detection cycles are triggered by many asynchronous activities such as promise resolutions, HTTP results, timer events, key presses and mouse movements.
- Expressions should finish quickly or the user experience may drag, especially on slower devices. Consider caching values ​​when their computation is expensive.
### No visible side effects
- A template expression should not change any application state other than the value of the target property.
- This rule is essential to Angular's "unidirectional data flow" policy. You should never worry that reading a component value might change some other displayed value. The view should be stable throughout a single rendering pass.
## [template expression operators](https://docs.angular.lat/guide/template-expression-operators) : Such as `|` ,  `?.` and `!`



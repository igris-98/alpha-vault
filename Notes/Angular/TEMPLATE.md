[[ANGULAR]]

#angular/template
# [Template](https://angular.io/guide/template-overview#understanding-templates)  OR [Template Syntax](https://angular.io/guide/template-syntax#template-syntax) :
- In Angular, a template is a blueprint for a fragment of user interface(UI).
- Templates are written in [[HTML]]. 
- Angular extends the HTML syntax in your templates with additional functionality to build many Angular's feature. Such as 
	- [[TEMPLATE EXPRESSION]]
	- [[TEMPLATE STATEMENT]]
	- [[TEMPLATE VARIABLE]]
	- It can use data-binding ([[BINDING#Data Binding]]), to coordinate the application and DOM data.
	- [[INTERPOLATION]]
	- [[PIPE]] to transform data before it is displayed.
	- [[DIRECTIVE]] to apply application logic to what gets displayed.

#angular/template #NOTE 
### When you generate an Angular application with the Angular CLI, the `app.component.html` file is the default template containing placeholder HTML.

### An Angular template is a fragment of the UI, it does not include elements such as `<html>`, `<body>` and `<base>`.

### To eliminate the risk of script injection attacks, Angular does not support the `<script>` element in templates. Angular ignores the `<script>` tag and outputs a warning to the browser console.

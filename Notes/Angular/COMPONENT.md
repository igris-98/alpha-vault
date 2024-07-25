[[ANGULAR]]
 #angular/component
# [Component](https://angular.io/guide/component-overview) :
- Component controls a patch of screen called a [view](https://angular.io/guide/glossary#view).
- Component are the main building block for Angular Application.
- Each component consists of :
	- HTML [[TEMPLATE]]  that declares what renders on the page.
	- A TypeScript Class that defines behavior (the interaction of HTML template) and *rendered DOM Structure*.
	- A CSS selector that defines how the component is used in a template
	- Optionally, CSS styles applied to the template that describes its appearance.

#angular/component #metadata 
# [Component metadata](https://angular.io/guide/architecture-components#component-metadata): 
- The @[Component](https://angular.io/api/core/Component) decorator identifies the class *immediately below* it as a component class, and specifies its [[METADATA(A)]].
- most useful properties are as follow:
	- **selector** : A **CSS selector** that tells Angular to create and insert an instance of this component wherever it finds the corresponding tag in template HTML.
	- **templateUrl** : The module-relative address of this component's HTML template.  This template defines the component's *HOST VIEW*.
	- **providers** : An array of [providers](https://angular.io/guide/glossary#provider) for services that the component requires.
	- **styleUrls** : One or more relative paths or absolute URLs for files containing CSS stylesheets to use in this component.
 
```typescript
@Component({
  selector:    'app-hero-list',
  templateUrl: './hero-list.component.html',
  providers:  [ HeroService ],
  styleUrls: ['./hero-list.component.css']
})
export class HeroListComponent implements OnInit {
  /* . . . */
}
```
- To use this component, you write the following in a [[TEMPLATE]] : 
```html
<app-hero-list></app-hero-list>
```

# [[Create a component using Angular CLI]]
# [[Notes/Angular/Component Lifecycle]]

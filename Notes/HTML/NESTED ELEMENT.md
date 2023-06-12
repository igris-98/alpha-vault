[[ELEMENT]]

#html/element/nested
# [Nesting elements](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started#nesting_elements) :
- Elements can be placed within other elements. This is called _nesting_.
- There are two ways to do nesting : Right Way and Wrong way
- Right Way :  In the example below, we opened the `p` element first, then opened the `strong` element. For proper nesting, we should close the `strong` element first, before closing the `p`.
	```html
	<p>My cat is <strong>very</strong> grumpy.</p>
	```
- Wrong Way :  In the example below, the browser has to guess your intent. This kind of guessing can resulting in unexpected results.
	```html
	<p>My cat is <strong>very grumpy.</p></strong>
	```

## The *tags have to open and close in a way that they are inside or outside one another*.
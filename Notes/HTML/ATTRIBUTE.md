[[HTML]] [[ELEMENT]]

#html/attribute
# [Attribute]() :
- Attributes contain extra information about the element that won't appear in the content.
- An Attribute should have : 
	- A space between it and the element name. (For an element with more than one attribute, the attributes should be separated by spaces too.)
	- The attribute name, followed by an equal sign.
	- An attribute value, wrapped with opening and closing quote marks.

![paragraph tag with 'class="editor-note"' attribute emphasized](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started/grumpy-cat-attribute-small.png)


## [Boolean attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started#boolean_attributes) : 
- Sometimes you will see attributes written without values. This is entirely acceptable. These are called Boolean attributes. 
- Boolean attributes can only have one value, which is generally the same as the attribute name.
	```html
	<input type="text" disabled="disabled" />
	OR
	<input type="text" disabled />
	```
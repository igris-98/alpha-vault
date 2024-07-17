# CSS stands for Cascading Style Sheets
## References : CSS in Depth Book and MDN Docs

# Definition :
- CSS is used to style and lay out web pages.
- CSS is a declarative language that controls how webpages look in the browser.
- CSS is one of the three core Web Technologies, along with HTML and JavaScript.
- CSS is a rule-based language.
- CSS was proposed in 1994 and first implemented by IE3 in 1996.

# Terminology :

1. Declaration - declaration is made up of a property and value;
```css
color: black;
```


2. Declaration Block - a group of declaration inside curly braces is called declaration block. A declaration block is preceded by a selector (here body)
```css
{
	color: black;
}
```
3. Ruleset - Together, the selector and declaration block are called a ruleset. A ruleset also called rule.

```css
body {
	color: black;
	font-size: 10px;
}
```


# Cascade : 
- cascade is mechanism that control which rule/ruleset applies when there is a conflict.
- cascade is set of rules which determines how conflicts are resolved.
- cascade is fundamental part of how the language(CSS) works.

## Three Rules to resolve the conflicts
1. Stylesheet Origin - Where the styles(rulesets) come from. Author(yours) styles are applied in conjunction with Browser's(USER Agent) Styles.
2. Selector SPECIFICITY - Which selectors take precedence over which.
3. Source Order - Order in which styles(ruleset) are declared in the stylesheet.

### These rules allow browser to behave predictably when resolving any ambiguity in the CSS.

### Understanding Stylesheet Origin
- There are different types or origin of stylesheet.
	1. Author : Yours Styles are called author styles.
	2. User Agent: The Browser's default styles are called User Agent Styles.
- User Agent styles have ***lower priority*** then Author, so your styles override them.

#### Important Declaration
- There's an Exception to the style origin rules: declaration that are marked as ***important***.
- A declaration can be marked as important by adding ***!important*** to the end of the declaration, before the semicolon.

```css
color: red !important;
```

### Understanding Specificity is Essential
- If conflicting declaration can't be resolved based on their origin, the browser next tries to resolve them by looking at their **specificity**.
- The Browser evaluates specificity in two parts.
	1. INLINE STYLES : styles applied in inline in HTML.
	3. SELECTOR SPECIFICITY : styles applied using a selector.
 
#### Inline Styles :
- If you use an HTML **style** attribute to apply styles, the declaration are applied only to that element.
- These are ""SCOPED"" declaration, which override any declaration applied from your stylesheet or `<style>` tag.
- Inline styles have no selector because they are applied directly to the element they target.

#NOTE 
##### To Override inline declaration in your stylesheet , you'll need to add an important to the declaration, shifting it into a **higher-priority origin**. It's  preferable to do this from within the stylesheet. Because if the inline styles are marked up important, then nothing can override them.

##### An important note about importance If you’re creating a JavaScript module for distribution (such as an NPM package), I strongly urge you not to apply styles inline via JavaScript if it can be avoided. If you do, you’re forcing developers using your package to either accept your styles exactly or use !important for every property they want to change. Instead, include a stylesheet in your package. If your component needs to make style changes dynamically, it’s almost always preferable to use JavaScript to add and remove classes to the elements. Then users can use your stylesheet, and they have the option to edit it however they like without battling specificity.


#### Selector Specificity : Different type of selectors also have different specificities 
-  ID selector has a higher specificity
- Class selector has a lower specificity that ID
- Tag(type) selector has a lowest specificity
- If a selector has more IDs, it wins
- If that result in TIE, the selector with the most classes wins.
- If that result in TIE, the selector with the most tag names wins.
```css
html body header h1 {
	color: blue; /* 4 Tags */
}
body header.page-header h1 {
	color: yellow; /* 3 tags and 1 class */
}
.page-header .title {
	color: green; /* 2 classes */
}
#page-title {
	color: red; /* 1 ID */
}
```

##### Pseudo-class selectors and attributes selector each have same specificity as a class selector. A universal selector and combinators have no effect on specificity.


### Understanding Source Order :
- If the Origin and Specificity are the same, then the declaration that appears later in the stylesheet takes precedence.

#### Link Styles and Source order : (IMP)
- Selectors for styling links should go in certain order.
```css
a:link {
	color: blue;
	text-decoration: none;
}
a:visited {
	color: purple;
}
a:hover {
	text-decoration: underline; 
}
a:active {
	color: red;
}
```
- The cascade is the reason this above order matters: given the same specificity, later styles override earlier styles.
- Helpful mnemonics to remember this order is LoVe/HAte - link, visited, hover, active
- NOTE : if you break this order you may get unexpected results.

#### Cascade Values : 
- The Browser follows these three steps - origin , specificity, source order to resolve the declaration conflicts. A declaration that **wins** the cascade is called a **Cascade Value**.
- A value for a particular property applied to an element as a result of the cascade.
- If a property is never specified for an element, it has no cascaded value for that property.


## Two Rule of thumb :
1. Don't use IDs in your selector.
2. Don't use !important.

## conflicts example :
When two or more rules target the same element on your page, the rules may provide conflicting declarations (different values of the same property) . Rules with conflicting declarations can appear one after the other, or they can be scattered throughout your stylesheets.

```html
<!DOCTYPE html>
<html>
	<head>
		<link href="style.css" rel="stylsheet" />
	</head>
	<body>
		<header class="page-header">
			<!-- Page Title -->
			<h1 id="page-title" class="title"> Cascadin Rule </h1>
			<nav>
				<ul>
					<li><a href="/"> Home</a></li>
				</ul>
			</nav>
		</header>
	</body>
</html>
```

```css
h1 {
	color: black;   /* Tag Selector */
}
#page-title {
	color: blue;   /* ID Selector */
}
.title {
	color: yellow;   /* class Selector */
}
```



# Inheritance :
- If an element has no cascade values for a given element. it may inherit one from an ancestor element. this concept is known as inheritance.
- Not all properties are inherited. By Default, only certain one are.
	- Primarily Properties pertaining to text :
		- color
		- font , font-family, font-size, font-weight, font-variant, font-style
		- line-height
		- letter-spacing
		- text-align, text-indent, text-transform
		- white-space
		- word-spacing
	- list properties : 
		- list-style, list-style-type, list-style-position, list-style-image
	- table border properties :
		- border-collapse, border-spacing
		- NOTE: these control border behavior of tables, not the more commonly used properties for specifying borders for non-table elements.



# Special Values : (inherit and initial)
- There are two special values that you can apply to any property to help manipulate the cascade : **inherit** and **initial**.

## Using Inherit :
- Sometimes you'll want inheritance to take place when a cascaded value is preventing it. To do this, you can use **inherit** keyword.
- You can override another value with this, and it will cause the element to inherit that value from its parent.

## Using Initial:
- Sometimes you'll find you have styles applied to an element that you want to undo. To do this, you can use **initial** keyword.
- Every CSS property has an initial or default value. It's like hard-rest of that value.
- NOTE : the initial keyword isn't supported in any version on IE and Opera.
- It's Important to note that **auto** is not the default value of all properties (like: width: auto).



# Shorthand properties :
- Shorthand properties are properties that let you set the values of several other properties at one time.
- like - font, background, border, margin, padding etc.
## Beware shorthand silently overriding other styles :
- Most **shorthand properties** let you omit certain values and only specify the bits you're concerned with. It's important to know that omitted values will be **set implicitly** to their **initial** values. This can silently override styles you specify elsewhere.
## understanding the order of shorthand values :
- Shorthand properties try to be lenient when it comes to the order of the values you specify.
- padding and margin - TOP RIGHT BOTTOM LEFT (TRouBLe/clockwise order begging at the top).
- background-position , text-shadow and box-shadow : H(Right/Left) V(Top/Bottom)



#CSS/default-values
# Defaults values :
- display : inline;
- width : auto;
- color : black;
- For most browser, the default font-size value is 16px. Technically, it’s the keyword value medium that calculates to 16 px. 


#css/root-element
# Root Element(:root) :
- The root node is the ancestor of all other elements in the document. It has a special pseudo-class selector (:root) that you can use to target it. **This is equivalent to using the type selector html with the specificity of a class rather than a tag.**
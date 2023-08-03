[[HTML]]

# HTML LISTS : 
Lists in HTML are used to present information in an organized and structured manner. HTML provides three main types of lists:

1. Ordered Lists (`<ol>`): Ordered lists are used when the order or sequence of the list items is important. The list items are automatically numbered by the browser. The `<ol>` element is used to define an ordered list, and each list item is represented by the `<li>` (list item) element. Here's an example of an ordered list:

```html
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```

The above code will be displayed in the browser as:

1. First item
2. Second item
3. Third item

2. Unordered Lists (`<ul>`): Unordered lists are used when the order of the list items is not significant, and they are typically represented by bullet points. The `<ul>` element is used to define an unordered list, and each list item is represented by the `<li>` element. Here's an example:

```html
<ul>
  <li>Red</li>
  <li>Green</li>
  <li>Blue</li>
</ul>
```

The above code will be displayed in the browser as:

- Red
- Green
- Blue

3. Definition Lists (`<dl>`): Definition lists are used when you want to present a list of terms along with their definitions or descriptions. The `<dl>` element is used to define a definition list. Each term is represented by the `<dt>` (definition term) element, and its corresponding definition or description is represented by the `<dd>` (definition description) element. Here's an example:

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

The above code will be displayed in the browser as:

HTML
HyperText Markup Language

CSS
Cascading Style Sheets

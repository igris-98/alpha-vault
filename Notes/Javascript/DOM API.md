#dom
# DOM : 
- DOM stands for Document Model Object.
- It is a programming interface for web documents, which represents the structure of an HTML or XML document as a tree-like model.
- The DOM allows us to use JavaScript to access HTML elements and styles in order to manipulate them.
- DOM Is not part of JavaScript, but it and it's method are actually part of the [[WEB APIS]].
- Using JavaScript and DOM we can: 
	- Access and modify the content of HTML elements.
	- Add, remove, or modify HTML elements and attributes.
	- Attach event handlers to respond to user actions, such as clicks or keypresses.
	- Dynamically change the style and layout of elements.
	- Traverse the DOM tree to navigate between elements and their relationships.
 - When a web page is loaded in a browser, the browser creates a DOM representation of the page. Each element in the HTML document becomes a node in the DOM tree, and these nodes can be accessed and manipulated using JavaScript. The DOM provides a set of objects, properties, and methods that allow developers to interact with and modify the DOM tree.

## `document` object in JS :
- `document` object is a special object in JS which serves as an entry point into the DOM.
```javascript
console.log(document);
```
- the first child of the document is usually the `<HTML>` Element which is the root element in all HTML Document. It's also called document element in the DOM.
```javascript
cosnt rootElement = document.documentElement;
```



## Access Html elements in the JS :
- To access an HTML element in the DOM using JavaScript, you can use various methods depending on the specific element you want to target. Here are a few common approaches:

#dom/access-element/getElementById
### **getElementById():** 
- If the element you want to access has a unique ID attribute, you can use the `getElementById()` method. This method retrieves the element with the specified ID from the document.
``` javascript
const element = document.getElementById('elementId');
```

#dom/access-element/getElementsByClassName
### **getElementsByClassName()**
- If the element you want to access has a specific class name, you can use the `getElementsByClassName()` method. This method returns a collection of elements that have the specified class.
``` javascript
const elements = document.getElementsByClassName('className');
```

#dom/access-element/getElementsByTagName
### **getElementsByTagName()**
- If you want to access elements based on their tag name, you can use the `getElementsByTagName()` method. This method returns a collection of elements with the specified tag.
``` javascript
const elements = document.getElementsByClassName('className');
```

#dom/access-element/querySelector
### **querySelector()**
- The `querySelector()` method allows you to select elements using CSS selectors. It returns the first element that matches the specified selector.
``` javascript
const element = document.querySelector('selector');
```

#dom/access-element/querySelectorAll
### **querySelectorAll()**
- The `querySelectorAll()` method allows you to select elements using CSS selectors. It returns the a collection of all matching element of the specified selector.
``` javascript
const element = document.querySelectorAll('selector');
```
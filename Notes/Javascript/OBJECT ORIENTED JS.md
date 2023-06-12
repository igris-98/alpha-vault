
# OBJECT : 
- An object is a data type that represents a collection of related data and functionality.
- It is a fundamental concept in JavaScript, and almost everything in JavaScript is an object or can be treated as an object.
- An object in JavaScript is defined as an unordered collection of **key-value** pairs, where the keys are **strings** (or symbols in ES6+) and the values can be any JavaScript data type, including other objects.

# Object Literal Syntax :  
- Objects can be created using the object literal syntax, which uses curly braces  `{}`:

```javascript
const person = {
  name: 'John',
  age: 30,
  isStudent: false,
  sayHello: function() {
    console.log('Hello!');
  }
};
```


# Accessing properties of Objects :
In JavaScript, there are two common ways to access properties of an object: dot notation and bracket notation.

1. Dot Notation:
   You can use dot notation to access properties of an object by specifying the object name followed by a dot (`.`) and the property name:

   ```javascript
   const person = {
     name: 'John',
     age: 30
   };

   console.log(person.name);  // Output: John
   console.log(person.age);   // Output: 30
   ```

	In the above example, `person.name` retrieves the value of the `name` property, and `person.age` retrieves the value of the `age` property.

2. Bracket Notation:
	- Bracket notation allows you to access object properties by using square brackets `[]` and providing the property name as a string or an expression:

	   ```javascript
	   const person = {
	     name: 'John',
	     age: 30
	   };
	
	   console.log(person['name']);  // Output: John
	   console.log(person['age']);   // Output: 30
	   ```

   - **The property name inside the brackets is treated as a string**. It allows you to access properties with special characters or dynamically compute the property name based on a variable or expression:

	   ```javascript
	   const propertyName = 'age';
	   console.log(person[propertyName]);  // Output: 30
	
	   const dynamicPropertyName = 'na' + 'me';
	   console.log(person[dynamicPropertyName]);  // Output: John
	   ```

Both dot notation and bracket notation are commonly used, but bracket notation is more versatile because it allows for dynamic property access.


# Methods :
Methods are functions that are defined as properties of an object. They allow objects to have behavior or perform actions.

```javascript
const person = {
  name: 'John',
  age: 30,
  methodName: function() {
    console.log('Hello!');
  }
};
person.methodName();  // Output: Hello! - Dot Notation
person['methodName']();  // Output: Hello! - Bracket Notation
```
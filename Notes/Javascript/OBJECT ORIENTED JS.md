[[JAVASCRIPT]]
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



# Destructuring Objects : 
In JavaScript, object destructuring allows you to extract properties from an object and assign them to variables. Destructuring can be performed on nested objects to access properties at different levels of depth.

```javascript
const person = {
  name: 'John',
  age: 30,
  address: {
    street: '123 Main St',
    city: 'New York',
    country: 'USA'
  }
};

const { name, age, address: { street, city, country } } = person;

console.log(name);      // Output: John
console.log(age);       // Output: 30
console.log(street);    // Output: 123 Main St
console.log(city);      // Output: New York
console.log(country);   // Output: USA


// renaming the keys name

const {name: firstName} = person
console.log(firstName);


//default value 
const { address = {}} = [person]

//both at same time 
const { name: fullName = 'Unknown' } = person;

//mutating variables
const a = 111;
const b = 222;
const obj = {a =12, b=13};
({a,b}) = obj; // without paranthese it's treated as a block which produce an error.

```


# Object Keys , Values and Entries(): 
In JavaScript, you can use three different methods to work with objects and their properties: `Object.keys()`, `Object.values()`, and `Object.entries()`. These methods allow you to extract information about an object's keys, values, or key-value pairs. Here's an explanation of each method:

1. `Object.keys()`:
   The `Object.keys()` method returns an array containing the keys of an object. It extracts only the enumerable property names of the object. Here's an example:

   ```javascript
   const obj = { a: 1, b: 2, c: 3 };
   const keys = Object.keys(obj);

   console.log(keys);  // Output: ["a", "b", "c"]
   ```

   In the above example, `Object.keys(obj)` retrieves the keys of the `obj` object and returns them as an array `["a", "b", "c"]`.

2. `Object.values()`:
   The `Object.values()` method returns an array containing the values of an object. It extracts only the enumerable property values of the object. Here's an example:

   ```javascript
   const obj = { a: 1, b: 2, c: 3 };
   const values = Object.values(obj);

   console.log(values);  // Output: [1, 2, 3]
   ```

   In this example, `Object.values(obj)` retrieves the values of the `obj` object and returns them as an array `[1, 2, 3]`.

3. `Object.entries()`:
   The `Object.entries()` method returns an array of arrays, where each inner array contains a key-value pair from the object. It extracts both the enumerable property names and their corresponding values. Here's an example:

   ```javascript
   const obj = { a: 1, b: 2, c: 3 };
   const entries = Object.entries(obj);

   console.log(entries);
   // Output: [["a", 1], ["b", 2], ["c", 3]]
   ```

   
[[JAVASCRIPT]]
#javascript/this
# this :
- Special keyword that is created for every execution context.
- It's refer to the context in which a function is called.
- It's determined dynamically at runtime, based on how a function is invoked.
- The behavior of `this` can be a bit complex and can differ depending on whether the function is a regular function, an arrow function, a method, or a constructor function.

Let's explore the different scenarios in which the `this` keyword is used:

1. Global scope:
   When `this` is used in the global scope (outside of any function), it refers to the global object, which is `window` in a web browser or `global` in Node.js.

2. Function context:
    However, if the function is called without any context (e.g., `myFunction()`), `this` typically defaults to the global object (`window` in a browser or `global` in Node.js), except in strict mode where it remains `undefined`.

3. Method context:
   When a function is defined as a method of an object, `this` refers to the object on which the method is being called. For example:
   ```javascript
   const obj = {
     name: 'John',
     sayHello: function() {
       console.log('Hello, ' + this.name + '!');
     }
   };
   obj.sayHello(); // Output: Hello, John!
   ```

4. Event handlers:
   When a function is used as an event handler, such as with `addEventListener`, `this` refers to the element that triggered the event.

5. Constructor functions:
   When a function is used as a constructor with the `new` keyword, `this` refers to the newly created object. Constructor functions are used to create multiple objects with the same structure.
   ```javascript
   function Person(name) {
     this.name = name;
   }
   const person1 = new Person('Alice');
   console.log(person1.name); // Output: Alice
   ```

6. Arrow functions:
   Arrow functions behave differently from regular functions when it comes to `this`. They do not have their own `this` binding and instead retain the `this` value from the surrounding context in which they are defined.
   ```javascript
   const obj = {
     name: 'John',
     sayHello: function() {
       const innerFunc = () => {
         console.log('Hello, ' + this.name + '!');
       };
       innerFunc();
     }
   };
   obj.sayHello(); // Output: Hello, John!
   ```

**It's important to note that the value of `this` is determined at runtime and not at the time of function definition.** It can be influenced by how a function is called, using call/apply/bind methods, or by using arrow functions to preserve the outer `this` context.

Understanding the context in which a function is called and how `this` behaves is crucial for correctly utilizing the `this` keyword in JavaScript code.



# Example : 
```javascript
console.log(this); // this -> window object in web or global in nodejs

function hiDeclaration() {
	console.log(this); // this -> undefined (strict mode) / otherwise window object
}

const hiExpression = function() {
	console.log(this); // this -> undefined (strict mode) / otherwise window object
}

const hiArrow = () => {
	console.log(this); // this -> window object because it's surrounding this is window 
}

hiDeclaration();
hiExpression();
hiArrow();

james = {
	firstName : "James",
	hiMethod : function() {
		console.log(this)
		
		// solutions of below function for this
		//solution 1
		const self = this // also known as self or that
		const fuctionInMethod = function() {
			console.log(this);
			console.log(self.firstName);
		}
		functionInMethod(); // regular function call so this would be undefined or window object
		// solution 2
		const arrowFunInMethod = () => {
			console.log(this.firstName); // this -> james object because arrow function has lexical this.
		}
		arrowFunInMethod();
	},
	hiMethodArrow : () => console.log(this),
}

james.hiMethod() // this -> james object
james.hiMethodArrow()// this -> window object


const malinda = {
	firstName : "Malinda"
}

malinda.hiMethod = james.hiMethod
malinda.hiMethod() // this -> malinda object

const simpleFunction = james.hiMethod
simpleFunction(); // this -> undefined (strict mode) or window object
```
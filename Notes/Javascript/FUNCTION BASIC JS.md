[[JAVASCRIPT]]

The fundamental building of real world javascript applications are functions.

In simplest form, function is a piece of code that we can reuse over and over again in our code.

In JavaScript, a function is a block of reusable code that performs a specific task or calculates a value. Functions are used to organize and structure code, promote reusability, and make the code easier to understand and maintain.

A function in JavaScript consists of the following components:

1. **Function keyword:** Functions in JavaScript are defined using the `function` keyword.

2. **Function name:** A name that identifies the function and can be used to invoke the function later.

3. **Parameters (optional):** Parameters are variables listed inside parentheses in the function definition. They represent the inputs that the function can accept.

4. **Function body:** The block of code enclosed within curly braces `{}` is called the function body. It contains the statements that define what the function does.

5. **Return statement (optional):** A function can optionally return a value using the `return` statement. This statement specifies the value that the function will produce as its result. If there is no return statement, the function returns `undefined` by default.

Here's a simple example of a JavaScript function that adds two numbers:

```javascript
function addNumbers(a, b) {
  return a + b;
}
```

In this example, the function is named `addNumbers`, and it takes two parameters `a` and `b`. The function body consists of a single statement that adds `a` and `b` together and returns the result.

Functions can be invoked or called by using the function name followed by parentheses, and passing arguments (values) for the parameters if required. For example:

```javascript
let result = addNumbers(5, 3);
console.log(result); // Output: 8
```

In this case, the `addNumbers` function is called with arguments `5` and `3`, and the returned value `8` is stored in the `result` variable and then printed to the console.


## Function Defining Syntax :
```javascript
function functionName(parameter1, parameter2, ...) {
  // Function body: statements to be executed
  // You can use the parameters within the function body
  return value; // Optional - specifies the value to be returned
}
```

## Function Calling Syntax :
Function calling, also known as invoking a function, refers to the process of executing a function and running its code. When a function is called, the program flow jumps to the function's body, executes the statements inside it, and then returns to the point where the function was called.

The syntax for calling a function in JavaScript is as follows:

```javascript
functionName(argument1, argument2, ...);
```

To call a function, you use the function name followed by parentheses `()`. Inside the parentheses, you can provide the necessary arguments or values that the function expects, separated by commas. If the function does not require any arguments, the parentheses can be empty.

Here's an example of a function call:

```javascript
function greet(name) {
  console.log("Hello, " + name + "!");
}

greet("John"); // Output: Hello, John!
```

In this example, the `greet` function is defined with a single parameter `name`. To call the function, we provide the argument `"John"` inside the parentheses. The function is then executed, and it logs `"Hello, John!"` to the console.

It's important to note that when calling a function, you should ensure that the function is defined or declared before its invocation. JavaScript code is executed sequentially, and functions need to be defined before they are called. Otherwise, you may encounter a runtime error indicating that the function is not defined.

Functions can be called multiple times with different arguments, allowing for code reuse and performing specific tasks with varying inputs. Each function call can have different argument values, and the function's code will be executed in the order in which the calls occur.

```javascript
function add(a, b) {
  return a + b;
}

console.log(add(2, 3)); // Output: 5
console.log(add(5, 7)); // Output: 12
console.log(add(10, -3)); // Output: 7
```

In this example, the `add` function is called multiple times with different arguments, and the returned values are printed to the console. The function calculates the sum of two numbers and returns the result.

Function calling is a fundamental aspect of JavaScript programming, allowing you to execute the logic and functionality defined within functions at various points in your code.

# Function Declaration and Function Expression 
In JavaScript, there are two main ways to define a function: function declaration and function expression. The main difference between them lies in how they are created and hoisted within the code.

1. **Function Declaration:**
   ```javascript
   function functionName(parameters) {
     // Function body
   }
   ```
   Function declarations are defined using the `function` keyword, followed by the function name and a set of parentheses containing any parameters. The function body is enclosed in curly braces. Function declarations are hoisted, which means they are moved to the top of their containing scope during the JavaScript parsing phase. As a result, you can call the function before its actual declaration in the code.

   Example:
   ```javascript
   sayHello("John");

   function sayHello(name) {
     console.log("Hello, " + name);
   }
   ```
   In this example, the `sayHello` function is declared using a function declaration. It is then called before its actual declaration. Since function declarations are hoisted, the code will run without any errors and print "Hello, John" to the console.

2. **Function Expression:**
   ```javascript
   var functionName = function(parameters) {
     // Function body
   };
   ```
   Function expressions involve assigning a function to a variable. The `function` keyword is used to define an anonymous function (a function without a name), which is then assigned to the variable. Function expressions are not hoisted and must be defined before they are called.

   Example:
   ```javascript
   sayHello("John"); // Error: sayHello is not a function

   var sayHello = function(name) {
     console.log("Hello, " + name);
   };
   ```
   In this example, the `sayHello` function is defined using a function expression. When trying to call the function before its definition, an error will occur because the variable `sayHello` is assigned the function expression after the function call. Moving the function expression above the function call will fix the error.

Function expressions provide more flexibility because they allow functions to be assigned dynamically to variables, passed as arguments to other functions, or returned as values from other functions. They are commonly used in scenarios such as callback functions or creating immediately invoked function expressions (IIFE).

Both function declarations and function expressions serve the same purpose of defining functions, but the choice between them depends on the specific requirements and design of your code.

# IIFE :
	IIFE stands for Immediately Invoked Function Expression. It is a JavaScript design pattern that involves creating and immediately executing a function expression.

Here's an example of an IIFE:

```javascript
(function() {
  // Function body
})();
```

In this pattern, an anonymous function is defined within parentheses and followed by an additional pair of parentheses `()`. This syntax immediately invokes the function.

The primary purpose of using an IIFE is to create a new scope and prevent the pollution of the global scope. When variables and functions are declared within an IIFE, they are encapsulated within its scope and do not interfere with other variables and functions outside of it.

Benefits and use cases of IIFEs:

1. **Encapsulation:** IIFEs provide a way to encapsulate code and prevent variable and function name clashes with other parts of the codebase. Variables declared within an IIFE are not accessible outside of it, which helps maintain a clean and modular code structure.

2. **Avoiding global scope pollution:** By wrapping code within an IIFE, you can avoid polluting the global scope with numerous variables and functions. This reduces the risk of naming conflicts and unintended interactions between different parts of your code.

3. **Module pattern:** IIFEs are often used in conjunction with the module pattern to create modules with private and public members. By defining variables and functions within the IIFE, you can create private members that are only accessible within the module, and expose selected members as public interfaces.

   ```javascript
   var myModule = (function() {
     var privateVariable = "This is private";

     function privateFunction() {
       console.log("This is a private function");
     }

     function publicFunction() {
       console.log("This is a public function");
     }

     return {
       publicFunction: publicFunction
     };
   })();

   myModule.publicFunction(); // Output: "This is a public function"
   ```

   In this example, the IIFE encapsulates the module code and exposes the `publicFunction` as the public interface of the module. The `privateVariable` and `privateFunction` are not accessible outside of the IIFE, providing data privacy and encapsulation.

IIFEs are commonly used in older JavaScript codebases and were particularly useful before the introduction of block-scoped variables with `let` and `const` in ES6. However, with modern JavaScript modules (`import` and `export`), IIFEs are less frequently used for encapsulation and module management. Nevertheless, they still find use in specific scenarios where a self-contained and immediately executed function is required.

# Callback Function :
A callback function is a function that is passed as an argument to another function and is invoked or called at a later point in time. The primary purpose of a callback function is to allow asynchronous and event-driven programming in JavaScript.

In JavaScript, functions are first-class objects, which means they can be assigned to variables, passed as arguments to other functions, and returned as values from other functions. This characteristic enables the use of callback functions.

Here's an example to illustrate the concept of callback functions:

```javascript
function fetchData(url, callback) {
  // Simulating an asynchronous operation
  setTimeout(function() {
    // Simulated data retrieval
    var data = { id: 1, name: "John Doe" };
    // Callback function invocation
    callback(data);
  }, 2000);
}

function processData(data) {
  console.log("Processing data: ", data);
}

fetchData("https://example.com/api/data", processData);
```

In this example, the `fetchData` function is defined to simulate an asynchronous operation, such as fetching data from an API. It takes two parameters: `url` and `callback`. After a simulated delay of 2000 milliseconds (2 seconds), it invokes the callback function, passing the retrieved `data` as an argument.

The `processData` function is defined separately and serves as the callback function in this case. It simply logs the received `data` to the console.

When calling the `fetchData` function, the `processData` function is passed as an argument. It acts as a callback function that will be executed once the data is retrieved, allowing us to process the data asynchronously.

Callbacks are commonly used in scenarios where the completion of an asynchronous operation triggers further actions. Examples include handling AJAX requests, reading files, event handling, or working with timers. By using callbacks, you can specify what should happen once an asynchronous operation completes, enabling non-blocking behavior and maintaining the responsiveness of the program.



# Arrow Function :
Arrow functions, also known as fat arrow functions, are a concise syntax for defining functions in JavaScript. They were introduced in ES6 (ECMAScript 2015) as a shorter and more expressive way to write functions.

The syntax for an arrow function is as follows:

```javascript
(parameters) => {
  // Function body
  return expression; // Optional
}
```

Here are some key features of arrow functions:

1. **Shorter syntax:** Arrow functions provide a more concise syntax compared to traditional function expressions, making the code more compact and easier to read.

2. **Implicit return:** If the function body consists of a single expression, the curly braces `{}` can be omitted, and the result of the expression will be implicitly returned. This allows for shorter function definitions.

3. **Lexical `this` binding:** Arrow functions do not have their own `this` value. Instead, they inherit the `this` value from the surrounding context (lexical scoping). This behavior helps to avoid confusion with the `this` keyword and provides a simpler way to access the enclosing scope.

Here are some examples to illustrate the usage of arrow functions:

```javascript
// Traditional function expression
var sum = function(a, b) {
  return a + b;
};

// Arrow function
var sum = (a, b) => a + b;

console.log(sum(5, 3)); // Output: 8

// Traditional function expression
var square = function(x) {
  return x * x;
};

// Arrow function
var square = x => x * x;

console.log(square(4)); // Output: 16

// Arrow function with implicit return
var greet = name => `Hello, ${name}!`;

console.log(greet("John")); // Output: "Hello, John!"
```

Arrow functions are commonly used in the following scenarios:

1. **Shorter function expressions:** When you need to define simple functions with concise bodies, arrow functions provide a more compact and readable syntax. They help reduce the boilerplate code associated with traditional function expressions.

2. **Avoiding `this` binding issues:** Arrow functions inherit the `this` value from the enclosing scope, which is particularly useful when working with callbacks or event handlers. It eliminates the need for explicit `bind`, `call`, or `apply` methods to preserve the correct `this` context.

3. **Array methods and functional programming:** Arrow functions are often used with array methods such as `map`, `filter`, and `reduce`, where concise function definitions are commonly needed. They facilitate a more expressive and functional programming style.

```javascript
var numbers = [1, 2, 3, 4, 5];

var doubled = numbers.map(num => num * 2);
console.log(doubled); // Output: [2, 4, 6, 8, 10]

var evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]
```

Arrow functions offer a more compact and expressive way to write functions in JavaScript. However, it's important to note that they have some differences in behavior compared to traditional functions, especially with regard to the `this` binding. Therefore, it's important to consider the context and usage requirements when deciding whether to use arrow functions.

#NOTE 
## For Best Practice never use arrow function as a method.
## Arrow Function are Excellent for simple one-liner functions. 
## Always Declare all your function first and use them only after the declaration. This apply to all type of function, even function declaration which are hoisted.
## Function are blocked scope (only in strict mode). Otherwise Function are function scope. (starting in ES6)

# Function Anatomy : 
- TODO :use the javascript pdf image here.




# Four way in which function can be Called :

```javascript
// method : this = Object that is calling the method.
// simple function caliing : this = undefined (only in strict mode otherwise to global object window (in the browser)).
// arrow function : this = this of surrounding function (lexical this). Dont's get its own this. [this -> where it's born or created.]
// Event Listener : this = DOM element that the handler is attached to.

'use strict';
console.log(this); // window object

function calcAgeDeclaration() {
	console.log(arguments); // arguments array [1,2]
	console.log(this) // undefined
}
const calcAgeExpression = function (){
	console.log(arguments); // arguments array  [3,4]
	console.log(this); // undefined
}

const calcAgeArrow  = () => {
	console.log(arguments); // Reference Error - not defined
	console.log(this); // window object
}

const jonas = {
	firstName : "Jonas",
	calcAgeMethod : function (){
		console.log(arguments); // arguments array
		console.log(this); // jonas object
	}, 
	calcAgeArrowMethod: () => {
		console.log(arguments); // Reference Error - not defined
		console.log(this); // window object because it's in object literal not in an block scope. so lexical this would be global this.
	}
}

const malinda = {
	firstName : "Malinda"
}
malinda.calcAgeMethod = jonas.calcAgeMethod;
malinda.calcAgeMethod() // console this -> malinds object

const simpleFunction = jonas.clacAgeMethod;
simpoleFuntion(); // console this -> undefined

calcAgeDeclaration(1,2);
calcAgeExpression(3,5);
calcAgeArrow(6,7);
jonas.calcAgeMethod();
jonas.calcAgeArrowMethod();
```

- this keyword never pointed to the function in which we are using it.
- this keyword never pointed to the variable environment of the function.


# First-Class Function : 
In JavaScript, functions are considered first-class objects, which means they have the same capabilities and characteristics as any other object in the language. Here are some key points to understand about functions being first-class objects:

1. **Functions can be assigned to variables:** Like any other data type in JavaScript, functions can be assigned to variables. You can create a function and assign it to a variable just like you would assign a string, number, or object.

```javascript
const greet = function(name) {
  console.log("Hello, " + name + "!");
};

greet("John"); // Output: Hello, John!
```

In this example, the function `greet` is assigned to the variable `greet`. The variable `greet` now references the function and can be called as if it were the original function.

2. **Functions can be passed as arguments to other functions:** Functions can be passed as arguments to other functions. This is a powerful feature in JavaScript that allows for higher-order functions and functional programming patterns.

```javascript
function greet(name) {
  console.log("Hello, " + name + "!");
}

function greetAndLog(callback, name) {
  console.log("Before greeting...");
  callback(name);
  console.log("After greeting...");
}

greetAndLog(greet, "John");
```

In this example, the `greet` function is passed as an argument to the `greetAndLog` function. The `greetAndLog` function calls the callback function (in this case, `greet`) with the provided name.

3. **Functions can be returned from other functions:** Functions can also be returned as values from other functions. This allows for the creation of higher-order functions that generate or customize behavior based on the returned function.

```javascript
function createGreeter() {
  return function(name) {
    console.log("Hello, " + name + "!");
  };
}

const greet = createGreeter();
greet("John"); // Output: Hello, John!
```

In this example, the `createGreeter` function returns an inner function that performs the greeting. The returned function is assigned to the `greet` variable, and it can be invoked just like any other function.

4. **Functions can have properties and methods:** Since functions are objects, you can assign properties and methods to them. This allows you to augment functions with additional data or behavior.

```javascript
function greet(name) {
  console.log("Hello, " + name + "!");
}

greet.message = "Welcome!";

console.log(greet.message); // Output: Welcome!
```

In this example, the `greet` function is given a `message` property, which can be accessed just like any other object property.

The fact that functions are treated as first-class objects in JavaScript enables powerful programming techniques such as passing functions as arguments, returning functions, and dynamically creating functions. This flexibility contributes to the expressive and functional nature of JavaScript as a language.``


# Function Default Parameter: 
```javascript
const bookings = []
// #NOTE 
// parameter must be in order to work the price parameter expression.
const createBooking = function(flightNum, numPassengers = 1, price = 199 * numPassengers) {
	booking = {
		flightNum,
		numPassengers,
		price
	}
	console.log(booking);
	bookings.push(booking);
}
createBooking("ABC123"); // flightNum = ABC123 , numPassengers = 1 , price = 199
createBooking("ABC123", 3); // flightNum = ABC123, numPassengers = 3 , price = 597
createBooking("ABC123", 10, 2999); // flightNum = ABC123, numPassengers = 10 , price = 2999
createBooking("ABC123", undefined, 2999); // flightNum = ABC123, numPassengers = 1 , price = 2999
createBooking("ABC123", null, 2999); // flightNum = ABC123, numPassengers = null , price = 2999
```

# First Class v/s Higher-Order Functions :
First-Class Functions:
First-class functions refer to the capability of a programming language to treat functions as first-class citizens. In a language with first-class functions, functions can be assigned to variables, passed as arguments to other functions, returned from functions, and stored in data structures. Essentially, functions are treated like any other data type. JavaScript is an example of a language that supports first-class functions.

Higher-Order Functions:
A higher-order function is a function that can take one or more functions as arguments or can return a function as its result. In other words, it operates on functions, either by accepting them as arguments or by returning them. Higher-order functions are a concept that builds on the idea of first-class functions.

Here's an example to illustrate the difference between first-class functions and higher-order functions:

```javascript
// First-class functions
function sayHello(name) {
  console.log("Hello, " + name + "!");
}

const greet = sayHello; // Assigning a function to a variable
greet("John"); // Calling the function through the variable

// Higher-order function
function higherOrderFunction(callback) {
  console.log("Inside the higher-order function");
  callback("Sarah"); // Calling the callback function passed as an argument
}

higherOrderFunction(sayHello); // Passing a function as an argument
```

In this example, `sayHello` is a function that prints a greeting to the console. It is assigned to the variable `greet` and called through the variable. This demonstrates the first-class nature of functions in JavaScript.

The `higherOrderFunction` is a higher-order function that takes a callback function as an argument. It logs a message and then invokes the callback function, passing it the name "Sarah." The `sayHello` function is passed as an argument to the `higherOrderFunction`, showcasing the concept of a higher-order function.

To summarize, first-class functions refer to the ability to treat functions as values, while higher-order functions are functions that operate on other functions by either accepting them as arguments or returning them. First-class functions provide the foundation for higher-order functions.



# Call and Apply Method : 
In JavaScript, the `call()` and `apply()` methods are used to invoke a function and specify the value of `this` inside the function, along with passing arguments to the function. They allow you to explicitly set the `this` value and provide arguments to a function, even if the function is not defined as a method of an object. Here's how they work:

1. **`call()` method:**
The `call()` method is used to invoke a function with a specified `this` value and individual arguments passed directly as comma-separated values. The syntax for the `call()` method is as follows:

```javascript
functionName.call(thisValue, arg1, arg2, ...);
```

- `functionName`: The function to be invoked.
- `thisValue`: The value to be used as the `this` value inside the function.
- `arg1`, `arg2`, ...: The arguments to be passed to the function individually.

Here's an example to illustrate the usage of the `call()` method:

```javascript
function greet() {
  console.log("Hello, " + this.name + "!");
}

const person = {
  name: "John"
};

greet.call(person); // Output: Hello, John!
```

In this example, the `greet()` function is defined without any explicit object association. The `call()` method is then used to invoke the `greet()` function with `person` as the `this` value. The function is called in the context of the `person` object, and it accesses the `name` property of `person`.

2. **`apply()` method:**
The `apply()` method is similar to `call()`, but it accepts an array-like object or an actual array as the second argument to pass arguments to the function. The syntax for the `apply()` method is as follows:

```javascript
functionName.apply(thisValue, [arg1, arg2, ...]);
```

- `functionName`: The function to be invoked.
- `thisValue`: The value to be used as the `this` value inside the function.
- `[arg1, arg2, ...]`: An array-like object or an array containing the arguments to be passed to the function.

Here's an example to illustrate the usage of the `apply()` method:

```javascript
function greet() {
  console.log("Hello, " + this.name + "!");
}

const person = {
  name: "John"
};

const args = ["arg1", "arg2"];

greet.apply(person, args); // Output: Hello, John!
```

In this example, the `greet()` function is called using the `apply()` method. The `person` object is passed as the `this` value, and an array `args` is provided as the second argument. The elements of the array are passed as individual arguments to the `greet()` function.

Both `call()` and `apply()` methods provide a way to control the `this` value inside a function and pass arguments to it. The main difference between them is how the arguments are passed: `call()` accepts individual arguments, while `apply()` accepts an array-like object or an array of arguments. These methods are commonly used in situations where you need to invoke a function with a specific `this` value or pass arguments dynamically.


# Bind Method :
The `bind()` method in JavaScript is used to create a new function that has a specified `this` value, along with pre-defined arguments. Unlike `call()` and `apply()`, `bind()` does not immediately invoke the function. Instead, it returns a new function with the bound `this` value and arguments, which can be invoked later. Here's how it works:

The syntax for the `bind()` method is as follows:

```javascript
functionName.bind(thisValue, arg1, arg2, ...);
```

- `functionName`: The function to be bound.
- `thisValue`: The value to be used as the `this` value inside the function when the bound function is invoked.
- `arg1`, `arg2`, ...: Optional arguments that are pre-defined for the bound function.

Here's an example to illustrate the usage of the `bind()` method:

```javascript
function greet() {
  console.log("Hello, " + this.name + "!");
}

const person = {
  name: "John"
};

const boundGreet = greet.bind(person);

boundGreet(); // Output: Hello, John!
```

In this example, the `greet()` function is bound to the `person` object using the `bind()` method. The `bind()` method returns a new function `boundGreet` with the `this` value set to `person`. When `boundGreet()` is invoked, it logs "Hello, John!" to the console.

Additionally, you can also pre-define arguments while using `bind()`. Here's an example:

```javascript
function multiply(a, b) {
  return a * b;
}

const multiplyByTwo = multiply.bind(null, 2);

console.log(multiplyByTwo(5)); // Output: 10
```

In this example, the `multiply()` function is bound to a `null` `this` value, and the first argument is pre-defined as `2`. The `bind()` method creates a new function `multiplyByTwo`, which multiplies any given number by `2`. When `multiplyByTwo(5)` is called, it returns `10`.

The `bind()` method is particularly useful when you want to create a new function with a specific `this` value that can be invoked later or passed as a callback function. It allows you to control the `this` value and pre-define arguments before invoking the function.
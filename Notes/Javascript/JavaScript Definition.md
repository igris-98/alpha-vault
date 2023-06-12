- JS is a HIGH-LEVEL, OBJECT-ORIENTED, MULTI-PARADIGM Programming Language.
	- High-Level : We don't have to worry about complex stuff like memory management etc.
	- Object-Oriented : Based on Object, for storing most kind of data.
	- Programming Language : Instruct computer do things.
	- Multi-Paradigm : We can use different styles of programming.

# DEFINING and Declaring variable :
In JavaScript, declaring and defining a variable are two distinct actions that involve working with variables.

1. Declaring a Variable:
Declaring a variable is the process of introducing a variable to the JavaScript runtime environment. It involves specifying the variable's name using the `var`, `let`, or `const` keyword, followed by an optional initialization (assignment) of a value.

Example of variable declaration:
```javascript
var x; // Variable declaration of 'x'
let y; // Variable declaration of 'y'
const z; // Variable declaration of 'z'
```

In the above example, variables `x`, `y`, and `z` are declared using the `var`, `let`, and `const` keywords, respectively. At this stage, the variables are considered to be declared but not defined or assigned a value. The variables exist in memory, but their values are `undefined`.

2. Defining (Initializing) a Variable:
Defining (initializing) a variable is the process of assigning a value to a declared variable. It sets the initial value of the variable, allowing it to hold a specific data value.

Example of variable definition (initialization):
```javascript
var x = 5; // Variable 'x' is defined with the value 5
let y = "Hello"; // Variable 'y' is defined with the value "Hello"
const z = true; // Variable 'z' is defined with the value true
```

In the above example, the variables `x`, `y`, and `z` are defined (initialized) by assigning them values (`5`, `"Hello"`, and `true`, respectively). The assignment operation sets the value of the variable, making it defined and ready for use.

It's important to note that when declaring variables using `var` or `let`, you can declare them without immediately defining (initializing) a value. In such cases, the variables will be automatically initialized with the value `undefined` until they are explicitly defined with a value later in the code.

Example of declaring variables without immediate definition:
```javascript
var x; // Variable 'x' is declared (initialized with 'undefined')
let y; // Variable 'y' is declared (initialized with 'undefined')
```

To summarize, declaring a variable in JavaScript is the act of introducing it to the runtime environment, while defining (initializing) a variable involves assigning a specific value to the declared variable. Both declaring and defining variables are essential steps in working with data and storing values in JavaScript programs.
In JavaScript, operators are symbols or keywords used to perform operations on variables and values. They allow you to manipulate and combine values, make comparisons, assign values, and perform various other operations. JavaScript supports several types of operators:
1.  Arithmetic Operators
2.  Assignment Operators
3.  Comparison Operators
4.  Logical Operators
5.  String Operators
6.  Bitwise Operators
7.  Ternary Operator
8.  typeof Operator
9.  In Operator
10.  instanceof Operator
11.  Unary Operators
12.  Comma Operator
13.  Delete Operator
14.  Spread Operator


1. Arithmetic Operators: These operators perform mathematical calculations.

- Addition: `+`
- Subtraction: `-`
- Multiplication: `*`
- Division: `/`
- Modulus (remainder): `%`
- Increment: `++`
- Decrement: `--`

Example:
```javascript
var x = 5;
var y = 2;

var sum = x + y; // 7
var difference = x - y; // 3
var product = x * y; // 10
var quotient = x / y; // 2.5
var remainder = x % y; // 1
```

2. Assignment Operators: These operators assign values to variables.

- Assignment: `=`
- Addition assignment: `+=`
- Subtraction assignment: `-=`
- Multiplication assignment: `*=`
- Division assignment: `/=`
- Modulus assignment: `%=`

Example:
```javascript
var x = 5;
x += 3; // equivalent to x = x + 3, x becomes 8
```

3. Comparison Operators: These operators compare values and return a boolean result (`true` or `false`).

- Equal to: `==`
- Not equal to: `!=`
- Strict equal to: `===`
- Strict not equal to: `!==`
- Greater than: `>`
- Less than: `<`
- Greater than or equal to: `>=`
- Less than or equal to: `<=`

Example:
```javascript
var x = 5;
var y = 3;

console.log(x > y); // true
console.log(x === y); // false
```

4. Logical Operators: These operators perform logical operations and return a boolean result.

- Logical AND: `&&`  (need more clarification add image or logic of each logic gate for all three)
- Logical OR: `||`
- Logical NOT: `!`
- [[SHORT CIRCUITING]]

Example:
```javascript
var x = 5;
var y = 3;
var z = 7;

console.log((x > y) && (z > y)); // true
console.log((x > y) || (z < y)); // true
console.log(!(x > y)); // false
```

5. String Operators: JavaScript allows string concatenation using the `+` operator.

Example:
```javascript
var firstName = "John";
var lastName = "Doe";

var fullName = firstName + " " + lastName; // "John Doe"
```

6. Bitwise Operators: These operators perform operations at the binary level, manipulating individual bits of numeric values.

- Bitwise AND: `&`
- Bitwise OR: `|`
- Bitwise XOR: `^`
- Bitwise NOT: `~`
- Left shift: `<<`
- Right shift: `>>`
- Zero-fill right shift: `>>>`

Example:
```javascript
var x = 5; // Binary: 0101
var y = 3; // Binary: 0011

var bitwiseAnd = x & y; // Binary: 0001 (Decimal: 1)
var bitwiseOr = x | y; // Binary: 0111 (Decimal: 7)
var bitwiseXor = x ^ y; // Binary: 0110 (Decimal: 6)
var bitwiseNot = ~x; // Binary: 1010 (Decimal: -6)
var leftShift = x << 1; // Binary: 1010 (Decimal: 10)
var rightShift = x >> 1; // Binary: 0010 (Decimal: 2)
```

7. Ternary Operator: Also known as the conditional operator, it provides a concise way to write conditional statements.

Syntax: `condition ? expression1(when true): expression2(when false)`

Example:
```javascript
var age = 18;
var message = (age >= 18) ? "You are an adult" : "You are a minor";
console.log(message); // "You are an adult"
```

8. typeof Operator: This operator returns a string indicating the data type of a value.

Example:
```javascript
var x = 5;
var y = "Hello";

console.log(typeof x); // "number"
console.log(typeof y); // "string"
```

9. In Operator: This operator checks if a property exists in an object.

Example:
```javascript
var person = { name: "John", age: 25 };

console.log("name" in person); // true
console.log("gender" in person); // false
```

10. instanceof Operator: This operator checks if an object is an instance of a particular class or constructor.

Example:
```javascript
function Rectangle(width, height) {
  this.width = width;
  this.height = height;
}

var rect = new Rectangle(5, 3);

console.log(rect instanceof Rectangle); // true
console.log(rect instanceof Object); // true
```

11. Unary Operators: These operators perform operations on a single operand.

- Unary plus: `+`
- Unary negation: `-`
- Increment: `++`
- Decrement: `--`
- Logical NOT: `!`
- typeof: `typeof`

Example:
```javascript
var x = 5;

console.log(+x); // 5 (unary plus)
console.log(-x); // -5 (unary negation)
console.log(++x); // 6 (increment)
console.log(--x); // 5 (decrement)
console.log(!true); // false (logical NOT)
console.log(typeof x); // "number" (typeof)
```

12. Comma Operator: This operator allows you to evaluate multiple expressions, separating them with a comma. The value of the entire expression is the value of the last expression.

Example:
```javascript
var x = (1 + 2, 3 + 4); // x = 7, as 3 + 4 is the last expression
```

13. Delete Operator: This operator deletes a property from an object or an element from an array.

Example:
```javascript
var person = { name: "John", age: 25 };
delete person.age; // Deletes the "age" property from the object
console.log(person); // { name: "John" }

var numbers = [1, 2, 3, 4, 5];
delete numbers[2]; // Deletes the element at index 2
console.log(numbers); // [1, 2, <empty>, 4, 5]
```

14. Spread Operator: Introduced in ES6, this operator allows you to expand elements of an array or object.
	- It's work on all [[ITERABLES]] 
	- We can only use it when building an array or we pass value into a function.
#NOTE
### Since ES 2018, the spread operator actually also work on objects even though object are not iterables.
 

Example:
```javascript
var arr = [1, 2, 3];
var arr2 = [4,5,6];
var newArr = [...arr, 4, 5]; // [1, 2, 3, 4, 5]

var obj = { x: 1, y: 2 };
var newObj = { ...obj, z: 3 }; // { x: 1, y: 2, z: 3 }

//shallow copy 
const newShallowArray = [...arr];
const newObj = { ...obj};

// join arrays
const joinArray = [...arr, ...arr1];

// passing value into function
const str = "JAMES";
consol.log(...str); // log is a function
```

15. rest pattern :
	The rest pattern is a feature in JavaScript that allows you to extract multiple elements from an array or object and assign them to a single variable. It is denoted by the ellipsis (`...`) syntax and is typically used in function parameters or array destructuring assignments.

	```javascript
	const numbers = [1, 2, 3, 4, 5];
	
	const [first, second, ...rest] = numbers;
	
	console.log(first);  // Output: 1
	console.log(second); // Output: 2
	console.log(rest);   // Output: [3, 4, 5]
	```
	
	```javascript
	function sum(...numbers) {
	  let total = 0;
	  for (let number of numbers) {
	    total += number;
	  }
	  return total;
	}
	
	console.log(sum(1, 2, 3, 4, 5)); // Output: 15
	```
	
	The rest pattern is a handy feature that simplifies working with arrays or function parameters when the number of elements or arguments is variable or unknown. It provides a concise way to handle multiple elements or arguments as a group.



# Operator Precedence :
Certainly! Here is a list of JavaScript operators grouped by their precedence levels, from highest to lowest. Operators within the same level have equal precedence.

1. Grouping:
   - `( )`

2. Member Access:
   - `.` (dot notation)
   - `[]` (bracket notation)

3. Computed Member Access:
   - `obj[prop]`

4. Function Call, Object Creation:
   - `()` (function call)
   - `new`

5. Increment/Decrement:
   - `++` (post-increment)
   - `--` (post-decrement)

6. Logical NOT, Bitwise NOT, Unary Plus, Unary Negation:
   - `!` (logical NOT)
   - `~` (bitwise NOT)
   - `+` (unary plus)
   - `-` (unary negation)

7. Exponentiation:
   - `**`

8. Multiplication, Division, Modulus:
   - `*` (multiplication)
   - `/` (division)
   - `%` (modulus)

9. Addition, Subtraction:
   - `+` (addition)
   - `-` (subtraction)

10. Bitwise Shift:
    - `<<` (left shift)
    - `>>` (right shift)
    - `>>>` (zero-fill right shift)

11. Relational and Comparison:
    - `<` (less than)
    - `>` (greater than)
    - `<=` (less than or equal to)
    - `>=` (greater than or equal to)
    - `in`
    - `instanceof`

12. Equality:
    - `==` (loose equality)
    - `!=` (loose inequality)
    - `===` (strict equality)
    - `!==` (strict inequality)

13. Bitwise AND:
    - `&`

14. Bitwise XOR:
    - `^`

15. Bitwise OR:
    - `|`

16. Logical AND:
    - `&&`

17. Logical OR:
    - `||`

18. Conditional (Ternary) Operator:
    - `? :`

19. Assignment:
    - `=` (assignment)
    - `+=` (addition assignment)
    - `-=` (subtraction assignment)
    - `*=` (multiplication assignment)
    - `/=` (division assignment)
    - `%=` (modulus assignment)
    - `<<=` (left shift assignment)
    - `>>=` (right shift assignment)
    - `>>>=` (zero-fill right shift assignment)
    - `&=` (bitwise AND assignment)
    - `^=` (bitwise XOR assignment)
    - `|=` (bitwise OR assignment)
    - `**=` (exponentiation assignment)

It's important to note that operator precedence determines the order in which operators are evaluated in an expression. Parentheses can be used to override the default precedence and explicitly specify the evaluation order.

Understanding operator precedence helps ensure that expressions are evaluated correctly, particularly when multiple operators are used together.
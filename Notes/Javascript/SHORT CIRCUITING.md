[[JAVASCRIPT]]

Short-circuiting is a behavior in JavaScript (and many other programming languages) where logical operators, such as the `&&` (logical AND) and `||` (logical OR), don't evaluate the second operand if the outcome can be determined by the first operand alone. This behavior can be useful for conditional statements and can help optimize code execution.

Here's how short-circuiting works with logical operators in JavaScript:

1. Logical AND (`&&`) Short-Circuiting:
When using the logical AND operator (`&&`), if the first operand evaluates to a falsy value (e.g., `false`, `0`, `null`, `undefined`, `NaN`, or an empty string), the second operand is not evaluated because it's not necessary to determine the overall result. In this case, the expression returns the falsy value of the first operand. If the first operand is truthy, the second operand is evaluated, and the expression returns the value of the second operand.

Example:

```javascript
var result = false && someFunction();  // The second operand is not evaluated because the first operand is false
console.log(result);  // Output: false
console.log( 0 && "JAMES");  // Output: 0
console.log( 7 && "JAMES");  // Output: JAMES
console.log("Hello" && 23 && null && 'jonas');  // Output: null

```

2. Logical OR (`||`) Short-Circuiting:
When using the logical OR operator (`||`), if the first operand evaluates to a truthy value, the second operand is not evaluated because it's not necessary to determine the overall result. In this case, the expression returns the truthy value of the first operand. If the first operand is falsy, the second operand is evaluated, and the expression returns the value of the second operand.

Example:

```javascript
var result = true || someFunction();  // The second operand is not evaluated because the first operand is true
console.log(result);  // Output: true
console.log(3 || "JONAS"); // Output : 3
console.log('' || "JONAS"); // Output : JONAS
console.log(true || "JONAS"); // Output : true
console.log(undefined || null); // Output : null
console.log(undefined || 0 || '' || 'Hello' || 23 || null); // Output : Hello


const numGuest = 0;
const totalGuest = numGuest || 10; // output always be 10;

```

Short-circuiting can be leveraged for conditional execution or to avoid potential errors when accessing properties or invoking functions based on certain conditions. For example, it's common to use short-circuiting to provide default values for variables:

```javascript
var name = username || "Guest";
```

In the above example, if the `username` variable is truthy, its value will be assigned to `name`. However, if `username` is falsy (e.g., `null`, `undefined`, or an empty string), the `"Guest"` string will be assigned to `name` as a default value.

Short-circuiting is a useful feature that can help write concise and efficient code by avoiding unnecessary evaluations when the outcome is already determined by the first operand.


# Nullish Coalescing Operator (??) :
```javascript
// #NOTE 
// solution for above problem is 
// nullish values which null and undefined
const numGuest1=0;
const totalGuest1 = numGuest ?? 10; // output will be 0;
```
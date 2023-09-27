[[JAVASCRIPT]]

In JavaScript, conditional statements are used to control the flow of a program based on certain conditions. They allow you to execute different blocks of code depending on whether a given condition evaluates to `true` or `false`. JavaScript provides several types of conditional statements:

1. `if` statement:
The `if` statement allows you to execute a block of code if a specified condition is true.

Syntax:
```javascript
if (condition) {
  // code to be executed if the condition is true
}
```

Example:
```javascript
var num = 5;

if (num > 0) {
  console.log("The number is positive.");
}
```

2. `if...else` statement:
The `if...else` statement allows you to execute one block of code if a condition is true and another block of code if the condition is false.

Syntax:
```javascript
if (condition) {
  // code to be executed if the condition is true
} else {
  // code to be executed if the condition is false
}
```

Example:
```javascript
var num = 5;

if (num > 0) {
  console.log("The number is positive.");
} else {
  console.log("The number is non-positive.");
}
```

3. `if...else if...else` statement:
The `if...else if...else` statement allows you to test multiple conditions and execute different blocks of code based on the first condition that evaluates to true. You can have multiple `else if` blocks, and the `else` block is optional.

Syntax:
```javascript
if (condition1) {
  // code to be executed if condition1 is true
} else if (condition2) {
  // code to be executed if condition2 is true
} else {
  // code to be executed if all conditions are false
}
```

Example:
```javascript
var num = 0;

if (num > 0) {
  console.log("The number is positive.");
} else if (num < 0) {
  console.log("The number is negative.");
} else {
  console.log("The number is zero.");
}
```

4. `switch` statement:
The `switch` statement allows you to select one of many code blocks to be executed based on the value of an expression. It provides a convenient way to handle multiple cases without writing multiple `if...else if` statements.

Syntax:
```javascript
switch (expression) {
  case value1:
    // code to be executed if expression matches value1
    break;
  case value2:
    // code to be executed if expression matches value2
    break;
  default:
    // code to be executed if expression doesn't match any value
}
```

Example:
```javascript
var day = "Monday";

switch (day) {
  case "Monday":
    console.log("It's Monday.");
    break;
  case "Tuesday":
    console.log("It's Tuesday.");
    break;
  default:
    console.log("It's another day.");
}
```

Conditional statements are fundamental in JavaScript programming as they allow you to make decisions and control the execution flow based on specific conditions. They are commonly used for tasks such as input validation, handling user interactions, and implementing different behaviors based on different scenarios.



## why use break in switch statement : 
In JavaScript's `switch` statement, the `break` statement is used to terminate the execution of a code block associated with a particular case. When a `break` statement is encountered, the program exits the `switch` statement, preventing the execution of subsequent case blocks.

The reason we use `break` in a `switch` statement is to ensure that only the code block corresponding to the matched case is executed, and subsequent case blocks are skipped. Without the `break` statement, the program would continue executing the code in the following case blocks, regardless of whether the conditions are met. This behavior is known as "fall-through."

Consider the following example:

```javascript
var day = "Tuesday";

switch (day) {
  case "Monday":
    console.log("It's Monday.");
    break;
  case "Tuesday":
    console.log("It's Tuesday.");
    // missing break statement
  case "Wednesday":
    console.log("It's Wednesday.");
    break;
  default:
    console.log("It's another day.");
}
```

In this case, if `day` is `"Tuesday"`, without the `break` statement after the `"Tuesday"` case, the program would execute the code block for `"Tuesday"`, but then it would also execute the code block for `"Wednesday"`. This fall-through behavior is not always desired and can lead to unexpected results.

By including the `break` statement after each case block, the program will only execute the code corresponding to the matching case and then exit the `switch` statement. This ensures that only one code block is executed based on the matching condition.

Here's the modified example with `break` statements:

```javascript
var day = "Tuesday";

switch (day) {
  case "Monday":
    console.log("It's Monday.");
    break;
  case "Tuesday":
    console.log("It's Tuesday.");
    break;
  case "Wednesday":
    console.log("It's Wednesday.");
    break;
  default:
    console.log("It's another day.");
}
```

In this case, if `day` is `"Tuesday"`, only the code block for `"Tuesday"` will be executed, and the program will exit the `switch` statement after executing that code block.

Using the `break` statement appropriately in a `switch` statement helps ensure that the program behaves as intended and executes the desired code block based on the matching case.
[[JAVASCRIPT]]

In JavaScript, a loop statement is used to repeatedly execute a block of code until a specific condition is met. It allows you to automate repetitive tasks and iterate over collections of data. There are three main types of loop statements in JavaScript: the `for` loop, the `while` loop, and the `do...while` loop. Let's explore each of them in depth:

1. **The `for` loop**: The `for` loop is commonly used when you know the exact number of iterations you want to perform. It consists of three parts: the initialization, the condition, and the iteration statement.

   ```javascript
   for (initialization; condition; iteration) {
     // code to be executed
   }
   ```

   - Initialization: It is executed once before the loop starts and is typically used to initialize a counter variable.
   - Condition: It is evaluated before each iteration. If the condition is true, the loop continues; otherwise, it exits.
   - Iteration: It is executed at the end of each iteration and is used to update the counter variable.

   Example: Printing numbers from 1 to 5 using a `for` loop.

   ```javascript
   for (let i = 1; i <= 5; i++) {
     console.log(i);
   }
   ```

2. **The `while` loop**: The `while` loop is used when you don't know the exact number of iterations in advance. It continues iterating as long as the specified condition remains true.

   ```javascript
   while (condition) {
     // code to be executed
   }
   ```

   - Condition: It is evaluated before each iteration. If the condition is true, the loop continues; otherwise, it exits.

   Example: Printing numbers from 1 to 5 using a `while` loop.

   ```javascript
   let i = 1;
   while (i <= 5) {
     console.log(i);
     i++;
   }
   ```

3. **The `do...while` loop**: The `do...while` loop is similar to the `while` loop, but it guarantees that the code block is executed at least once before checking the condition. It continues iterating as long as the specified condition remains true.

   ```javascript
   do {
     // code to be executed
   } while (condition);
   ```

   - Condition: It is evaluated after each iteration. If the condition is true, the loop continues; otherwise, it exits.

   Example: Printing numbers from 1 to 5 using a `do...while` loop.

   ```javascript
   let i = 1;
   do {
     console.log(i);
     i++;
   } while (i <= 5);
   ```

It's important to ensure that loop conditions eventually become false; otherwise, you can end up in an infinite loop, causing your program to hang or crash. To control the flow within a loop, you can use statements like `break` to exit the loop prematurely or `continue` to skip the current iteration and proceed to the next one.

These loop statements provide powerful tools for iterating over data structures, processing arrays, and performing repetitive tasks in JavaScript.





## FOR-IN and FOR-OF :
The `for-in` and `for-of` loops in JavaScript are used to iterate over elements in different types of collections, such as objects and arrays. While they may appear similar, they have distinct use cases:

1. **`for-in` loop**: The `for-in` loop is primarily used for iterating over the properties of an object. It loops through all enumerable properties of an object, including properties inherited from its prototype chain. It is not recommended to use `for-in` with arrays, as it can produce unexpected results.

   ```javascript
   for (variable in object) {
     // code to be executed
   }
   ```

   - Variable: It represents a different property name (key) on each iteration.
   - Object: It is the object whose properties you want to iterate over.

   Example: Iterating over the properties of an object using a `for-in` loop.

   ```javascript
   const person = {
     name: 'John',
     age: 30,
     occupation: 'Developer'
   };

   for (let prop in person) {
     console.log(prop + ': ' + person[prop]);
   }
   ```

   Output:
   ```
   name: John
   age: 30
   occupation: Developer
   ```

   Note: It's important to use `hasOwnProperty()` method within the loop to check if the property belongs directly to the object and not its prototype chain.

2. **`for-of` loop**: The `for-of` loop is used to iterate over iterable objects such as arrays, strings, maps, sets, and other collection objects. It provides an easier and more concise way to iterate through the values of an iterable object compared to other loop constructs.

   ```javascript
   for (variable of iterable) {
     // code to be executed
   }
   ```

   - Variable: It represents a different value on each iteration.
   - Iterable: It is an object that can be iterated over, such as an array or a string.

   Example: Iterating over the elements of an array using a `for-of` loop.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];

   for (let num of numbers) {
     console.log(num);
   }
   ```

   Output:
   ```
   1
   2
   3
   4
   5
   ```

   Note: The `for-of` loop iterates over the values, not the indices, of an iterable object. If you need to access the indices, you can use the `entries()` method of an array to get both the index and value.

Overall, the `for-in` loop is suitable for iterating over object properties, while the `for-of` loop is more appropriate for iterating over iterable collections like arrays and strings.



### for-of with array entries() :
Certainly! Here's an example that demonstrates the usage of the `entries()` method in JavaScript:

```javascript
const fruits = ['apple', 'banana', 'cherry'];

for (let [index, fruit] of fruits.entries()) {
  console.log(`Index: ${index}, Fruit: ${fruit}`);
}
```

Output:
```
Index: 0, Fruit: apple
Index: 1, Fruit: banana
Index: 2, Fruit: cherry
```

In this example, the `entries()` method is called on the `fruits` array. It returns an iterator object that provides both the index and value of each element in the array as an array `[index, value]`. 

The `for-of` loop is then used to iterate over the iterator object. On each iteration, the array destructuring assignment is used to assign the index to the `index` variable and the value to the `fruit` variable. The corresponding values are then printed using `console.log()`.

As a result, you get the output that displays the index and value of each fruit in the `fruits` array.



# Break and Continue :
Both `continue` and `break` are control flow statements used within loops in JavaScript to alter the normal flow of execution.

1. **`continue` statement**: The `continue` statement is used to skip the rest of the current iteration within a loop and proceed to the next iteration. When encountered, it stops the execution of the current iteration's code block and moves to the next iteration.
	Example:
	```javascript
	for (let i = 1; i <= 5; i++) {
	  if (i === 3) {
	    continue; // Skip the iteration when i equals 3
	  }
	  console.log(i);
	} 
	// Output 
	// 1 2 4 5
	```
 
2. **`break` statement**: The `break` statement is used to terminate the execution of a loop prematurely. When encountered, it immediately exits the loop, regardless of whether the loop's condition has been met or not.
	Example:
	```javascript
	for (let i = 1; i <= 5; i++) {
	  if (i === 3) {
	    break; // Exit the loop when i equals 3
	  }
	  console.log(i);
	}
	// Output 
	// 1 2

	```
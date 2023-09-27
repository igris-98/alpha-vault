[[JAVASCRIPT]]

The `typeof` operator is a built-in operator in JavaScript that allows you to determine the data type of a given value or expression. It returns a string representing the type of the operand. Here are some examples:

1. Example: Checking the type of a number
   ```javascript
   let num = 42;
   console.log(typeof num);  // Output: "number"
   ```

2. Example: Checking the type of a string
   ```javascript
   let str = "Hello, world!";
   console.log(typeof str);  // Output: "string"
   ```

3. Example: Checking the type of a boolean
   ```javascript
   let bool = true;
   console.log(typeof bool);  // Output: "boolean"
   ```

4. Example: Checking the type of an array
   ```javascript
   let arr = [1, 2, 3];
   console.log(typeof arr);  // Output: "object"
   ```

5. Example: Checking the type of an object
   ```javascript
   let obj = { name: "John", age: 25 };
   console.log(typeof obj);  // Output: "object"
   ```

6. Example: Checking the type of a function
   ```javascript
   let func = function() {
     console.log("Hello!");
   };
   console.log(typeof func);  // Output: "function"
   ```

7. Example: Checking the type of `null`
   ```javascript
   let nullValue = null;
   console.log(typeof nullValue);  // Output: "object"
   ```
   It's important to note that the `typeof` operator returns "object" for `null`, which is considered a language quirk and not an accurate representation of its type.

8. Example: Checking the type of `undefined`
   ```javascript
   let undefinedValue;
   console.log(typeof undefinedValue);  // Output: "undefined"
   ```

The `typeof` operator is useful for performing type checks and conditionally executing code based on the data type of a value or variable. However, it's important to keep in mind that `typeof` has some limitations, particularly with regard to distinguishing between different types of objects. In such cases, you may need to use additional techniques like `instanceof` or other methods for more precise type checking.
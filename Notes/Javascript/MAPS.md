In JavaScript, "maps" refer to the `Map` object, which is a built-in data structure introduced in ECMAScript 2015 (ES6). **A `Map` is used to store key-value pairs, where the keys and values can be of any type.** It provides an efficient way to store and retrieve data based on the keys.

MAPs are also Iterables.

Here's a basic example of creating and using a `Map` in JavaScript:

```javascript
// Creating a new Map
const myMap = new Map();

// alterantive to create new map
const question = new Map([
	['question', 'what is the best programming language.'],
	[1, 'C'],
	[2, 'Python'],
	[3, 'JavaScript'],
	['correct', 3],
	[true, "Correct"],
	[false, "Incorrect"]
])
console.log(question);

// Adding key-value pairs to the Map
myMap.set("key1", "value1");
myMap.set(2, "value2").set(true, "value3");

// Retrieving values from the Map
console.log(myMap.get("key1")); // Output: "value1"
console.log(myMap.get("key2")); // Output: "value2"

// Checking if a key exists in the Map
console.log(myMap.has("key3")); // Output: true
console.log(myMap.has("key4")); // Output: false

// Removing a key-value pair from the Map
myMap.delete(2);

// Iterating over the Map
myMap.forEach((value, key) => {
  console.log(`${key} => ${value}`);
});

// Clearing the Map
myMap.clear();

// objects as keys
// 1. array
myMap.set([1,2], "test");
myMap.get([1,2]); // undefined because they both are not same. in the heap they both have their separate refernces.

const arr = [1,2];
myMap.set(arr, "test");
myMap.get(arr);  // test becasue it's the same reference in the heap

```

Some important characteristics of `Map` are:

- Keys can be any type, including objects or functions.
- Each key can only appear once in the `Map`. Adding a key-value pair with an existing key will overwrite the previous value.
- The order of the key-value pairs is maintained based on the insertion order.
- The `Map` object provides several methods for working with the data, such as `set()`, `get()`, `has()`, `delete()`, `forEach()`, `size`, and more.

`Map` is commonly used when you need to associate values with unique keys and perform efficient lookups based on those keys. It provides a flexible and powerful alternative to using plain objects as dictionaries in JavaScript.


# MAPS METHODS :
Certainly! Here are some of the commonly used methods of the `Map` object in JavaScript:

1. `set(key, value)`: Adds a key-value pair to the `Map`. If the key already exists, the previous value is overwritten.
   ```javascript
   const myMap = new Map();
   myMap.set("key1", "value1");
   ```

2. `get(key)`: Retrieves the value associated with the specified key from the `Map`.
   ```javascript
   console.log(myMap.get("key1")); // Output: "value1"
   ```

3. `has(key)`: Checks if a key exists in the `Map` and returns a boolean indicating the result.
   ```javascript
   console.log(myMap.has("key1")); // Output: true
   ```

4. `delete(key)`: Removes the key-value pair associated with the specified key from the `Map`.
   ```javascript
   myMap.delete("key1");
   ```

5. `forEach(callbackFn)`: Executes a provided function once for each key-value pair in the `Map`, in insertion order.
   ```javascript
   myMap.forEach((value, key) => {
     console.log(`${key} => ${value}`);
   });
   ```

6. `clear()`: Removes all key-value pairs from the `Map`.
   ```javascript
   myMap.clear();
   ```

7. `size`: Returns the number of key-value pairs in the `Map`.
   ```javascript
   console.log(myMap.size); // Output: 0
   ```

These are just a few of the methods available on the `Map` object. You can explore the full range of methods and their details in the JavaScript documentation for `Map`: [Map - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)


#NOTE 
- The Big Difference in MAPs and Objects is , In Objects key are **always string**. But in Maps we can have any type of key.
#javascript/array 

# Array : 
- An array is a data structure used to store multiple values in a single variable.
- Arrays are especially useful when you need to work with a collection of related values.
- Arrays are zero-indexed, which means that the first element in an array is accessed using the index 0, the second element is accessed using the index 1, and so on. 
- You can access or modify individual elements in an array using their respective indices.
- Array are specialized form of Objects.
- Array are reference type.

```javascript
const numbers = [1,2,3,4];
const alphabets = new Array('a', 'b', 'c');

console.log(numbers.length); // array length

console.log(numbers[0]); // access using index 
console.log(alphabets);
console.log(typeof alphabets); // object
console.log(Array.isArray(alphabets)) // true - Introduced in ES5 
```


# Destructuring an Array :
- Destructuring an array in JavaScript allows you to extract values from an array and assign them to variables in a concise and convenient way.
- It provides a shorthand syntax for extracting elements from an array without the need for accessing them individually by their indices.

Example 1:
```javascript
const numbers = [1, 2, 3, 4, 5];

const [first, second, ...rest] = numbers;
const [, , third] = numbers;

console.log(first);  // Output: 1
console.log(second); // Output: 2
console.log(third); // Output: 2
console.log(rest);   // Output: [3, 4, 5]
```

Example 2:
```javascript
const nestedArray = [1, [2, 3], 4, 5];

const [a, [b, c], d, e , f=9] = nestedArray;

console.log(a); // Output: 1
console.log(b); // Output: 2
console.log(c); // Output: 3
console.log(d); // Output: 4
console.log(e); // Output: 5
console.log(f); // Output: 9 //default value assign at the time of destructuring

```

# Array Built-In methods : 

JavaScript provides a variety of built-in methods that you can use to manipulate arrays. Here are some commonly used methods:

1. `push()`: Adds one or more elements to the end of an array and returns the new length of the array.
```javascript
let fruits = ['apple', 'banana'];
fruits.push('orange', 'grape');
console.log(fruits); // Output: ['apple', 'banana', 'orange', 'grape']
```

2. `pop()`: Removes the last element from an array and returns that element.
```javascript
let fruits = ['apple', 'banana', 'orange'];
let removedFruit = fruits.pop();
console.log(fruits);         // Output: ['apple', 'banana']
console.log(removedFruit);   // Output: 'orange'
```

3. `concat()`: Combines two or more arrays and returns a new array.
```javascript
let fruits = ['apple', 'banana'];
let additionalFruits = ['orange', 'grape'];
let allFruits = fruits.concat(additionalFruits);
console.log(allFruits); // Output: ['apple', 'banana', 'orange', 'grape']
```

4. `join()`: Joins all elements of an array into a string, optionally using a specified separator.
```javascript
let fruits = ['apple', 'banana', 'orange'];
let fruitString = fruits.join(', ');
console.log(fruitString); // Output: 'apple, banana, orange'
```

5. `slice()`: Returns a **shallow copy** of a portion of an array as a new array, without modifying the original array.
```javascript
let fruits = ['apple', 'banana', 'orange', 'grape'];
let slicedFruits = fruits.slice(1, 3);
console.log(slicedFruits); // Output: ['banana', 'orange']
```

6. `indexOf()`: Returns the first index at which a given element is found in the array, or -1 if not found.
```javascript
let fruits = ['apple', 'banana', 'orange'];
let index = fruits.indexOf('banana');
console.log(index); // Output: 1
```

7. `splice()`: Changes the content of an array by removing, replacing, or adding elements in place.
```javascript
let fruits = ['apple', 'banana', 'orange', 'grape'];
fruits.splice(2, 1, 'mango', 'cherry');
console.log(fruits); // Output: ['apple', 'banana', 'mango', 'cherry', 'grape']
```

8. `shift()`: Removes the first element from an array and returns that element. It also shifts all subsequent elements to a lower index.
```javascript
let fruits = ['apple', 'banana', 'orange'];
let shiftedFruit = fruits.shift();
console.log(fruits);       // Output: ['banana', 'orange']
console.log(shiftedFruit); // Output: 'apple'
```

9. `unshift()`: Adds one or more elements to the beginning of an array and returns the new length of the array. It also shifts existing elements to higher indices.
```javascript
let fruits = ['apple', 'banana'];
fruits.unshift('orange', 'grape');
console.log(fruits); // Output: ['orange', 'grape', 'apple', 'banana']
```

10. `reverse()`: Reverses the order of elements in an array in place, modifying the original array.
```javascript
let fruits = ['apple', 'banana', 'orange'];
fruits.reverse();
console.log(fruits); // Output: ['orange', 'banana', 'apple']
```

11. `sort()`: Sorts the elements of an array in place, either using the default lexicographic (dictionary) order or a custom comparison function.
```javascript
let fruits = ['banana', 'orange', 'apple'];
fruits.sort();
console.log(fruits); // Output: ['apple', 'banana', 'orange']
```

12. `forEach()`: Calls a provided function once for each element in an array, in ascending order.
```javascript
let fruits = ['apple', 'banana', 'orange'];
fruits.forEach((fruit, index) => {
  console.log(fruit, index);
});
// Output:
// 'apple' 0
// 'banana' 1
// 'orange' 2
```

13. `map()`: Creates a new array by calling a provided function on every element in the array.
```javascript
let numbers = [1, 2, 3];
let squaredNumbers = numbers.map(num => num ** 2);
console.log(squaredNumbers); // Output: [1, 4, 9]
```

14. `filter()`: Creates a new array with all elements that pass a test implemented by a provided function.
```javascript
let numbers = [1, 2, 3, 4, 5];
let evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]
```

15. `entries()` : The `entries()` method is a built-in method available for arrays in JavaScript. It returns a new Array Iterator object that contains key-value pairs for each index and corresponding element in the array. The key-value pairs are represented as arrays, where the first element is the index, and the second element is the corresponding element value.

	```javascript
	const fruits = ['apple', 'banana', 'orange'];
	
	const entriesIterator = fruits.entries();
	
	console.log(entriesIterator.next().value); // Output: [0, 'apple']
	console.log(entriesIterator.next().value); // Output: [1, 'banana']
	console.log(entriesIterator.next().value); // Output: [2, 'orange']
	```
		
	The `entries()` method is often used in conjunction with looping constructs like `for...of` or `Array.from()` to iterate over the key-value pairs in the array:
	
	```javascript
	const fruits = ['apple', 'banana', 'orange'];
	
	for (let [index, fruit] of fruits.entries()) {
	  console.log(`Index: ${index}, Fruit: ${fruit}`);
	}
	// Output:
	// Index: 0, Fruit: apple
	// Index: 1, Fruit: banana
	// Index: 2, Fruit: orange
	```
	
// TODO reduce(),includes()
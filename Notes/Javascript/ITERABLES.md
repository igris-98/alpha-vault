In JavaScript, an iterable is an object that can be iterated over using the `for...of` loop or other mechanisms that support iteration. Iterables are a general concept in JavaScript that allow you to loop or iterate through their elements in a sequential manner.

An iterable must implement the iterable protocol, which involves providing an iterator. The iterator is an object that defines a `next()` method, which returns an object with two properties: `value` (the current element in the iteration) and `done` (a boolean value indicating whether the iteration is complete or not).

Common built-in iterables in JavaScript include arrays, strings, maps, sets, and certain collection-like objects. For example, you can use the `for...of` loop to iterate over an array:

```javascript
let numbers = [1, 2, 3];

for (let num of numbers) {
  console.log(num);
}
// Output:
// 1
// 2
// 3
```

In this example, the array `numbers` is an iterable, and the `for...of` loop iterates over each element in the array.

Strings are also iterable, allowing you to iterate over their individual characters:

```javascript
let greeting = "Hello";

for (let char of greeting) {
  console.log(char);
}
// Output:
// "H"
// "e"
// "l"
// "l"
// "o"
```

You can also create your own custom iterables by implementing the iterable protocol. To make an object iterable, you need to define the `Symbol.iterator` method that returns an iterator object.

Here's an example of a custom iterable object:

```javascript
let myIterable = {
  data: [1, 2, 3],
  [Symbol.iterator]() {
    let index = 0;
    let data = this.data;

    return {
      next() {
        if (index < data.length) {
          return { value: data[index++], done: false };
        } else {
          return { value: undefined, done: true };
        }
      }
    };
  }
};

for (let item of myIterable) {
  console.log(item);
}
// Output:
// 1
// 2
// 3
```

In this example, the `myIterable` object is made iterable by implementing the `Symbol.iterator` method, which returns an iterator object with a `next()` method.

Overall, iterables provide a consistent and convenient way to iterate over various types of objects in JavaScript, making it easier to work with collections of data in a loop.
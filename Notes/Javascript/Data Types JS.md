- Every Value in JS is either **OBJECT (NON-PRIMITIVE OR REFERENCE TYPE)** Or **PRIMITIVE**.

# PRIMITIVE DATA TYPE
- Primitive data types are simple and immutable, meaning their value cannot be changed once they created.
- It's stored in the execution contexts in which they are declared.(call stack or stack);
- When you assign a primitive value to a variable, the variable directly holds that value.
- There are total 7 primitive data types which are as follow :
	1.  Number : Floating Point Numbers . It's user for Decimal & Integers.
		```javascript
		let age = 23;
		const rate = 123.50;
		```
	2.  String : Sequence of characters. it's used for text.
		```javascript
		const name = "Hello";
		```
	3. Boolean : Logical Type that can only be **true** and **false**. it's used for taking decisions.
		 ```javascript
		let isOpen = false; 
		```
	4. Undefined: Value taken by a variable that is not yet defined (empty value).
		```javascript
		let games;
		```
	5. Null : Also means intentionally **empty value**. 
		```javascript
		let myNull = null;
		```
	6. Symbol(ES2015) : Value that is unique and cannot be changed
		```javascript
		let sym = Symbol("foo");
		```
	7. BigInt(ES2020) : Larger integers than the Number type can hold

# NON-PRIMITIVE DATA TYPE
- Non-primitive data types are complex and mutable, meaning their values can be changed even after they are created.
- These are typically stored and accessed by reference. The variable holds a reference to the memory location where the actual value is stored.
- When you assign non-primitive value to variable, the variable holds a reference to that value.
- when you assign non-primitive value to another variable or pass it as function argument, the reference is copied, not the actual value.
- **Object** and **Array** are example of non-primitive data type.

# JAVASCRIPT has dynamic typing. Data types are determined automatically.
# Value has type, NOT Variable.


example of primitive and non-primitive:
- argument passing
- comparing
- value assignment

example 1 : passing primitive Values
```javascript
function valuePass(a) {
	console.log(a, "IN"); // 10
	a = 20;
	console.log(a, "IN"); // 20
}
let a = 10;
console.log(a, "OUT"); // 10
valuePass(a);
console.log(a, "OUT"); // 10
```

example 2 : passing non-primitive values
```javascript
function referencePass(a) {
	console.log(a, "IN"); // [1,2,3]
	a.push(4);
	console.log(a, "IN"); // [1,2,3,4]
	a = [5,6,7]
	console.log(a, "IN"); // [5,6,7]
	a.push(8);
	console.log(a); // [5,6,7,8]
	// local variable `a` is reference to the global variable `a` until it's not assign to any new value.
}
let a = [1,2,3];
console.log(a, "OUT"); // [1,2,3] 
referencePass(a);
console.log(a, "OUT"); // [1,2,3,4]
```

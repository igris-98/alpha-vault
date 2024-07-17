# Generalize Recursion:
```js
// this psuedo code can be convert into any language easily.
function fun(param){
	if(_base_condition_){
		// 1. Calling Phase -> Ascending Phase // statements;
		// 2. Recursive Call
		fun(param - 1); // any arithmetic operation with recursive call are also operate in Returning Phase. like : fun(param - 1) * 2;
		// 3. Returning Phase -> Descending Phase
	}
}
```

#NOTE/DSA/Recursion/General
- Descending phase only available in recursion not in loops.
- Recursive Function utilize the stack.
- Recursive Function are memory consuming.
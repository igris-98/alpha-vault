[[JAVASCRIPT]]

- Strict mode is a special mode that we can activate in javascript.
- Which make easier for us to write a secure JS code.

- To activate strict mode use below string. it has to be the very **first statement in the script**.
	```javascript
	'use strict';

	// 1. can't declare variables without var,let,const
	c = 1; // ReferenceError: c is not defined 

	// 2. can't use reversed keywords as identifiers(variable's name)
	const private = 1; // SyntaxError: Unexpected strict mode reserved word

	// 2. can't use reversed keywords as identifiers(variable's name)
	const private = 1; // SyntaxError: Unexpected strict mode reserved word
	
	// 3. this keyword not pointing to window object
	console.log(this); // undefined
	```

#NOTE
- If we have any code before this above string then strict mode will not be activated.
- We actually can also activate strict mode, only for a specific function and a specific block. but it's not have any significant advantage so Always use it at beginning of each script.
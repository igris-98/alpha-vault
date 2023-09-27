[[JAVASCRIPT]]
# Variable Naming :
- JavaScript variable names are case-sensitive. Lowercase and uppercase letters are distinct.
	```javascript
	var DogName = 'Scooby-Doo';
	var dogName = 'Droopy';
	var DOGNAME = 'Odie';
	console.log(DogName); // "Scooby-Doo"
	console.log(dogName); // "Droopy"
	console.log(DOGNAME); // "Odie"
	```
 - The **most recommended** way to declare JavaScript variables is with **camel case** variable names.
	```javascript
	// bad // all lowercase without word separation
	var dogname = 'Droopy'; 
	// bad 
	// snake_case but not recommened for js variable name. 
	// It may be used for object key's name.
	var dog_name = 'Droopy'; 
	// bad // all UPPERCASE without word separation
	var DOGNAME = ‘Droopy’; 
	// bad // used for global constant 
	var DOG_NAME = 'Droopy'; 
	// good
	var dogName = 'Droopy';
	``` 
- The names of variables should be self-explanatory and describe the stored value.
	```javascript
	// bad // what do you mean by d?
	var d = 'Scooby-Doo';
	// bad // it's ambiguity who's name -> person name, dog name, car name so on.
	var name = 'Scooby-Doo';
	// good // it's more declarative and means
	var dogName = 'Scooby-Doo';
	```

# Boolean Variable Naming : 
- When it comes to **Boolean** variables, we should use **is** or **has** as prefixes. 
	```javascript
	// bad
	var bark = false;
	// bad
	var ideal = true;
	// bad
	var owner = true;
	// good
	var isBark = false;
	// good
	var areIdeal = true;
	// good
	var hasOwner = true;
	```

# Function and Method Naming :
- The **camel case** approach is the recommended way to declare function names.
	```javascript
	// bad // same as variable name -> it's ambiguity
	function name(dogName, ownerName) { 
	  return '${dogName} ${ownerName}';
	}
	
	// good
	function getName(dogName, ownerName) { 
	  return '${dogName} ${ownerName}';
	}
	```


# Class and Component Naming :
- we have to use **Pascal case** for class names.
- JavaScript components are widely used in front-end frameworks like React and Angular.
```javascript
class DogCartoon { 
  constructor(dogName, ownerName) { 
    this.dogName = dogName; 
    this.ownerName = ownerName; 
  }
}

var cartoon = new DogCartoon('Scooby-Doo', 'Shaggy');
```

# Private Variable and Method Naming :
- Leading Underscore(`_`) is used for private variable and functions.
	```javascript
	class DogCartoon { 
	  constructor(dogName, ownerName) { 
	    this.dogName = dogName; 
	    this.ownerName = ownerName; 
	    this.name = _toonName(dogName, ownerName); 
	  } 
	  _toonName(dogName, ownerName) { 
	    return `${dogName} ${ownerName}`; 
	  } 
	}
	
	var cartoon = new DodCartoon('Scooby-Doo', 'Shaggy'); 
	
	// good
	var name = cartoon.name;
	console.log(name);
	// "Scooby-Doo Shaggy" 
	
	// bad
	name =cartoon._toonName(cartoon.dogName, cartoon.ownerName);
	console.log(name);
	// "Scooby-Doo Shaggy"
	```

# Global Variable Naming :
- It is recommended to use **camel case** for **mutable** global variables and **uppercase** for **immutable** global variables.
In JavaScript, scope refers to the accessibility and visibility of variables, functions, and objects in a particular part of your code during runtime. Understanding scope is crucial for managing variable lifetimes, avoiding naming conflicts, and creating modular and maintainable code. To explain scope, let's break it down into three related concepts: scope, lexical environment, and scope chain.

1. Scope:
   - Scope defines the region or context in which variables and functions are declared and can be accessed.
   - JavaScript has function scope and block scope. Variables declared with `var` keyword have function scope, while variables declared with `let` and `const` have block scope.
   - Variables defined within a particular scope are accessible within that scope and any nested inner scopes, but not outside of them.
   - Example:
     ```javascript
     function outer() {
       var x = 10;  // Function scope variable

       function inner() {
         console.log(x);  // Accessible within the inner scope
       }

       inner();
     }

     outer();  // Output: 10
     console.log(x);  // Error: x is not defined (outside the scope)
     ```

2. Lexical Environment:
   - A lexical environment is an internal JavaScript data structure that holds identifier-variable mappings.
   - It consists of two main components: an environment record (which stores variables and functions) and a reference to the outer environment (lexical parent).
   - Each time a function is invoked or a block is executed, a new lexical environment is created, forming a hierarchy of nested environments.
   - Example:
     ```javascript
     function outer() {
       var x = 10;

       function inner() {
         var y = 20;
         console.log(x + y);
       }

       inner();
     }

     outer();  // Output: 30
     ```
     In the above example, `inner` has access to variables defined in its own environment (such as `y`) as well as variables from the outer environment (such as `x`).

3. Scope Chain:
   - The scope chain is a mechanism that allows inner functions to access variables and functions from their outer (parent) scopes.
   - It is formed by linking the lexical environments together, creating a chain-like structure.
   - When a variable is accessed, JavaScript first searches for it in the current lexical environment. If it's not found, it looks up the scope chain until it either finds the variable or reaches the global scope.
   - Example:
     ```javascript
     var x = 10;

     function outer() {
       var y = 20;

       function inner() {
         var z = 30;
         console.log(x + y + z);
       }

       inner();
     }

     outer();  // Output: 60
     ```
     In the above example, `inner` can access `x`, `y`, and `z` by traversing the scope chain, even though those variables are not directly defined within its own scope.

#NOTE 
- Scope Chain is all about the order in which functions ae written in the code.
- What's really important to note here is that the scope chain has nothing to do with the order in which function were called.

Understanding scope, lexical environment, and scope chain is crucial for understanding variable access, closures, and how JavaScript manages the lifetime and visibility of variables and functions within your code.
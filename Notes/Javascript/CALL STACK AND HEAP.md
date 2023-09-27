[[JAVASCRIPT]]
In JavaScript, the stack, heap, and call stack are all important concepts related to the execution context of a program.

1. **Stack**: The stack is a region of memory that is used for storing primitive values and function call information. It operates in a Last-In-First-Out (LIFO) manner. Each time a function is called, a new frame is created on top of the stack, known as a "stack frame" or "activation record." The stack frame contains the function's local variables, parameters, and the return address. When a function completes its execution, its stack frame is removed from the stack, and the control returns to the previous stack frame.

2. **Heap**: The heap is another region of memory used for storing dynamically allocated objects and non-primitive data types. Objects created using the `new` keyword, arrays, and other non-primitive values are allocated in the heap. The heap is not managed in a specific order like the stack. Instead, it uses a more complex memory allocation and deallocation mechanism called "garbage collection" to automatically manage memory and free up space when objects are no longer needed.

3. **Call Stack**: The call stack is a data structure that keeps track of the execution context of a program. It keeps a record of the active function calls and their order of execution. Each time a function is called, a new frame is pushed onto the call stack, and when a function completes, its frame is popped off the stack. The call stack allows the program to keep track of which function is currently being executed and the point where the program should return after completing a function.

When a JavaScript program starts executing, an initial stack frame is created for the global context. As functions are called, additional stack frames are created and pushed onto the call stack. The call stack helps maintain the order of execution and tracks the point where a function should return once its execution is complete. The stack frames contain information about local variables, function parameters, and the return addresses.

It's important to note that the size of the stack is typically limited, and exceeding its capacity can result in a "stack overflow" error. This can happen if there is excessive recursion or if a function's call stack becomes too deep due to nested function calls. Proper management of the stack and heap is crucial to ensure efficient memory usage and avoid runtime errors.



# STRING POOL : (not in JS)
In JavaScript, strings are stored as primitive values. They are stored in the stack memory when assigned to variables or used as function arguments or return values. Each string value is stored in its own memory location in the stack.

However, JavaScript does not have a built-in concept of a "string pool" like some other programming languages, such as Java. In languages with a string pool, strings with the same value are stored in a shared memory area called the string pool. This optimization allows multiple variables to reference the same string object, reducing memory usage.

In JavaScript, when you create multiple strings with the same value, each string is stored as a separate primitive value in memory. There is no automatic sharing of string objects.

For example:
```javascript
let str1 = "Hello";
let str2 = "Hello";
```
In this case, `str1` and `str2` are separate string variables with the same value, but they are stored as distinct string objects in memory.

However, it's important to note that JavaScript engines may implement internal optimizations behind the scenes. In some cases, when a string is created using the same value multiple times, the engine may choose to internally optimize the memory usage. These optimizations may involve techniques like interning or caching commonly used strings, but these details are specific to the engine's implementation and are not part of the JavaScript language specification.

In summary, JavaScript does not have a dedicated string pool concept, but JavaScript engines may employ their own optimizations for string handling and memory usage.
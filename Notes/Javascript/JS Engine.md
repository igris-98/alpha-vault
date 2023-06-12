JS Engine : It is a computer program that executes javascript code.

It's component and how it works:

JS engine always contains a call stack and a heap.

- The call stack is where our code is executed using execution contexts.

- Heap is an unstructured memory pool which stores all the objects that our application needs.

Compilation and Interpretation :

Each computer's processor only understand the one's and zero's. So every single program needs to be converted into the machine code and this happen using compilation and interpretation.

In Compilation, the entire source code is converted into the machine code at once and then written  in a portable file that can executed on any computer.

In Interpretation, there is an interpreter which runs through the source code and executes it line by line ( at the same time).The source code still needs to be converted into machine code but it happens right before it's executed.

The interpreted languages are much more slower than the compiled languages.

The modern javascript engine are now use a mix between compilation and interpretation which called just-in-time compilation (JIT Compilation). This approach compiles the entire code in machine code at once and then executes it right away.


# JS ENGINE THEORY
A JavaScript engine is a computer program or interpreter that executes JavaScript code. It is responsible for parsing, interpreting, and executing JavaScript programs or scripts. JavaScript engines are typically found in web browsers to run JavaScript code embedded in web pages, but they can also be standalone engines used in server-side environments or command-line tools.

JavaScript engines perform several important tasks to execute JavaScript code effectively:

1. Lexical Analysis and Parsing:
   - The engine first performs lexical analysis, which involves breaking down the source code into a sequence of tokens.
   - Then, it parses the tokens to create an abstract syntax tree (AST), which represents the structure of the code.

2. Compilation and Optimization:
   - Once the AST is created, the engine compiles it into an internal format that can be executed more efficiently.
   - The engine may apply various optimization techniques, such as just-in-time (JIT) compilation, to optimize the execution speed of the code.

3. Execution:
   - After the code is compiled and optimized, the engine executes the code by traversing the AST and performing the required operations.
   - It evaluates expressions, assigns values to variables, executes control flow statements (such as conditionals and loops), and invokes functions.

4. Memory Management:
   - JavaScript engines handle memory management for objects and variables created during code execution.
   - They allocate memory for objects on the heap and deallocate memory for objects that are no longer needed, using garbage collection algorithms.

Popular JavaScript engines used in web browsers include:

- V8 (used in Chrome and Node.js)
- SpiderMonkey (used in Firefox)
- JavaScriptCore (used in Safari)
- Chakra (used in older versions of Microsoft Edge)
- Blink (a fork of V8 used in newer versions of Microsoft Edge)

Each JavaScript engine may have its own unique features, optimization strategies, and performance characteristics. They constantly evolve and improve to provide faster execution and better compatibility with the JavaScript language specifications.
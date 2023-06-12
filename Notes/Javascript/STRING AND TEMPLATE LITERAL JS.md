In JavaScript, a string is a sequence of characters enclosed in single quotes (`'`) or double quotes (`"`). Strings are used to represent and manipulate textual data in JavaScript. Here's an example of a string:

```javascript
var greeting = "Hello, world!";
```

Template literals, introduced in ECMAScript 6 (ES6), provide an enhanced way to work with strings in JavaScript. They are enclosed in backticks (```) and allow you to include placeholders `${expression}` within the string, which will be replaced with the evaluated value of the expression. Template literals also support multiline strings without the need for explicit line breaks.

Here's an example of a template literal:

```javascript
var name = "John";
var age = 25;

var message = `My name is ${name} and I am ${age} years old.`;
```

In the example above, the `${name}` and `${age}` are placeholders within the template literal. During the evaluation, the expressions `name` and `age` will be substituted with their corresponding values, resulting in the string `"My name is John and I am 25 years old."`.

Template literals offer several advantages over traditional string concatenation:

1. Variable Substitution: You can easily embed variables within the string using `${expression}` syntax. This provides a cleaner and more readable way to incorporate variables into strings.

2. Expression Evaluation: The expressions within `${}` are evaluated, allowing you to include dynamic values or perform computations directly within the template literal.

3. Multiline Strings: Template literals support multiline strings without the need for explicit line breaks or string concatenation. You can include line breaks and indentation within the template literal, making it more convenient for writing and maintaining multiline strings.

Here's an example of a multiline template literal:

```javascript
var message = `
  This is a multiline string.
  It spans across multiple lines.
  No explicit line breaks needed.
`;
```

In this case, the resulting `message` string will preserve the line breaks and indentation specified within the template literal.

Template literals provide a more flexible and expressive way to work with strings in JavaScript, especially when dealing with dynamic content and multiline text. They are widely used in modern JavaScript development for improved string manipulation and formatting.
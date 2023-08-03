#css/function
# CSS Functions:
- CSS functions are built-in functions that allow you to perform calculations, transformations, and manipulations on values within CSS properties. They provide a way to dynamically modify or generate values based on certain criteria.

#css/function/calc
## calc() :
The calc() function lets you do basic arithmetic with two or more values. This is particularly useful for combining values that are measured in different units. This function supports addition (+), subtraction (-), multiplication (`*`) and division (/). The addition and subtraction operators must be surrounded by whitespace, so I suggest getting in the habit of always adding a space before and after each operator.

```css
:root { font-size: calc(0.5em + 1vw); }
```
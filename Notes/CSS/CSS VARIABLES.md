#css/variables
# CSS Variables :
CSS variables, also known as CSS custom properties, are a feature introduced in CSS3 that allow you to define reusable values and store them for later use. They provide a way to create variables in CSS, similar to variables in programming languages, and enable you to centralize and control the values used throughout your stylesheets. Here's how CSS variables work:

1. **Variable Declaration**:
   CSS variables are declared using the `--` prefix followed by a custom name and assigned a value. The variable declaration is typically placed in a selector that establishes the scope of the variable.

   ```css
   :root {
     --primary-color: #ff0000;
     --font-size: 16px;
   }
   ```

   In the example above, `--primary-color` and `--font-size` are the variable names, and `#ff0000` and `16px` are the corresponding values.

2. **Variable Usage**:
   Once declared, CSS variables can be referenced and used in any property value by using the `var()` function.

   ```css
   .my-element {
     color: var(--primary-color);
     font-size: var(--font-size);
   }
   ```

   In the example above, the `--primary-color` and `--font-size` variables are used to define the color and font-size of the `.my-element` class, respectively.

3. **Value Inheritance**:
   CSS variables can also inherit values from other variables. This means you can define a variable based on the value of another variable.

   ```css
   :root {
     --primary-color: #ff0000;
     --secondary-color: var(--primary-color);
   }
   ```

   In this case, the `--secondary-color` variable inherits the value of `--primary-color`.

4. **Dynamic Updates**:
   CSS variables can be dynamically updated using JavaScript. By modifying the value of a CSS variable using JavaScript, you can change the appearance of multiple elements simultaneously.

   ```javascript
   document.documentElement.style.setProperty('--primary-color', '#00ff00');
   ```

   The above code updates the value of the `--primary-color` variable to `#00ff00`.

CSS variables provide greater flexibility and maintainability in your stylesheets. They allow you to define and reuse values in a centralized manner, making it easier to update and customize your styles.
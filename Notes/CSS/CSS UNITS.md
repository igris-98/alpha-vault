#css/units
# CSS Units : 
In CSS, units are used to express measurements for various properties such as length, size, spacing, and time. CSS offers several types of units, categorized as follows:

#css/units/absolute
1. **Absolute Units**:
   - **px**: Pixels are the most common absolute unit. They represent a fixed length on the screen and are not affected by scaling factors. For example, `10px` specifies a length of 10 pixels.
   - **in**: Inches represent physical inches. For example, `1in` corresponds to one physical inch on a printed page.
   - **cm**: Centimeters represent physical centimeters. For example, `2cm` corresponds to two centimeters on a printed page.
   - **mm**: Millimeters represent physical millimeters. For example, `5mm` corresponds to five millimeters on a printed page.
   - **pt**: Points represent a unit commonly used in print media. One point is equal to 1/72nd of an inch.
   - **pc**: Picas represent a unit commonly used in print media. One pica is equal to 12 points.

#css/units/relative
2. **Relative Units**:
   - **em**: 
	   - The `em` unit is relative to the **font-size** of the element itself or its parent element. 
	   - For example, `2em` means the element's size will be twice the **font-size** of its parent or itself.
	   - font-size of ems are derived from the **inherited** font size.
	   - ems can be convenient when setting properties like padding, height, width, or border-radius because these will scale evenly with the element if it inherits different font sizes, or if the user changes the font settings.
   - **rem**: 
	   - The `rem` unit is similar to `em` but relative to the root element's font-size. It ensures consistent sizing across the entire document.
	   - Use `rem` for font-size.
   - **%**: 
	   - The percentage unit is relative to a specific value. For example, `50%` represents half of the parent element's size or a specified value.
   
   #CSS/computed-value
   - **Computed Values** : In CSS, Values declared using relative units are evaluated by the browser to an absolute value, called the computed value. 

#css/units/viewport
3. **Viewport-Percentage Units**:
   - **vw**: 
	   - Represents a percentage of the viewport's width. For example, `50vw` is equal to 50% of the viewport's width.
	   - 1/100th of the viewport width.
   - **vh**: 
	   - Represents a percentage of the viewport's height. For example, `50vh` is equal to 50% of the viewport's height.
	   - 1/100th of the viewport height.
   - **vmin**: Represents a percentage of the smaller dimension (width or height) of the viewport.
   - **vmax**: Represents a percentage of the larger dimension (width or height) of the viewport.

4. **Other Units**:
   - **fr**: Represents a fraction of the available space in a CSS Grid or Flexbox container.
   - **ch**: Represents the width of the "0" (zero) character in the element's font.
   - **ex**: Represents the height of the lowercase "x" character in the element's font.

These are the main types of units in CSS. Each unit serves a specific purpose and provides flexibility when defining sizes and measurements in web design. Choosing the appropriate unit depends on the context and the desired visual or responsive behavior you want to achieve.


#NOTE #css/tips/units
- When in doubt, use rems for font size, pixels for borders, and ems for most other properties.


#css/units/unitless
## Unitless Numbers :
In CSS, unitless values refer to numeric values that are used without any specific unit of measurement. They are used in certain properties where the unit is implied or not applicable. Here are some examples:

1. **line-height**: The `line-height` property determines the height of a line of text. It can be specified as a unitless value, representing a multiplier or a ratio of the font-size of the element. For example, `line-height: 1.5` means the line height will be 1.5 times the font-size.

2. **font-weight**: The `font-weight` property sets the boldness of the text. It can be specified with unitless values such as `normal` or `bold`. Additionally, numeric values like `400` and `700` are commonly used to define different levels of boldness.

3. **opacity**: The `opacity` property controls the transparency of an element. It accepts a unitless value ranging from `0` (completely transparent) to `1` (fully opaque). For example, `opacity: 0.5` makes an element 50% transparent.

4. **flex**: In CSS Flexbox layout, the `flex` property is used to specify the flexibility of a flex item. The value can be a unitless number representing the flex grow factor, flex shrink factor, and flex basis. For example, `flex: 1` assigns equal flex grow, shrink, and basis values to the item.

5. **z-index**: The `z-index` property determines the stacking order of positioned elements. It is usually specified as a unitless integer value. Higher values appear on top of lower values in the stacking order.

#NOTE 
## A unitless 0 can only be used for length values and percentages, such as in paddings, borders, and widths. It can’t be used for angular values, such as degrees or time-based values like seconds.

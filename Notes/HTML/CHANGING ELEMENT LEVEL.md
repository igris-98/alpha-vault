[[BLOCK VS INLINE ELEMENT]]

# Changing element level :
-  You can change the _visual presentation_ of an element using the CSS [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property. For example, by changing the value of `display` from `"inline"` to `"block"`, you can tell the browser to render the inline element in a block box rather than an inline box, and vice versa. However, doing this will not change the _category_ and the _content model_ of the element. For example, even if the `display` of the `span` element is changed to `"block"`, it still would not allow to nest a `div` element inside it.


#NOTE/HTML/ELEMENT-LEVEL
#### The terms _block_ and _inline_, as used in this article, should not be confused with [the types of CSS boxes](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model#block_and_inline_boxes) that have the same names. While the names correlate by default, changing the CSS display type doesn't change the category of the element, and doesn't affect which elements it can contain and which elements it can be contained in. One reason HTML5 dropped these terms was to prevent this rather common confusion.
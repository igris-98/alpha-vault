[[HTML TEXT FUNDAMENTALS]]

#html/paragraph
# Paragraph :
- In HTML, each paragraph has to be wrapped in a [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) element, like so:
```html
<p>I am a paragraph, oh yes I am.</p>
```
- Paragraphs are block-level elements([[BLOCK VS INLINE ELEMENT), and notably will automatically close if another block-level element is parsed before the closing `</p>` tag.
[[HTML]]

# [Anatomy of html document](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started#anatomy_of_an_html_document) :

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```

- `<!DOCUMENT html>` : (in HTML5)
	- It is a declaration that tell web browser which version of HTML is being used in the web page.
	- it ensures that the web page is rendered correctly and consistently across different devices and browsers by specifying the version of HTML being used.
- `<html></html>` : 
	- This element wraps all content on the page.
	- It is also knows as root element.
- `<head></head>` : 
	- The [head](https://developer.mozilla.org/en-US/docs/Glossary/Head) of an HTML document is the part that is not displayed in the web browser when the page is loaded.
	-  It contains information such as the page [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title), links to [[CSS]], links to custom favicons, and other metadata.
- `<meta>` :
	- This element represents [[METADATA(H)]] that cannot be represented by other HTML meta-related elements, like [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base), [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link), [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script), [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) or [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title).
- `<title></title>` : 
	-  This sets the title of the page, which is the title that appears in the browser tab the page is loaded in. 
	- The page title is also used to describe the page when it is bookmarked.
- `<body></body>` :
	- This contains _all_ the content that displays on the page, including text, images, videos, games, playable audio tracks, or whatever else.
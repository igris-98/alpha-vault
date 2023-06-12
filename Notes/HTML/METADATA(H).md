[[ANATOMY OF HTML DOCUMENT]]

#html/metadata

# [Metadata](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#metadata_the_meta_element) :
 -  HTML has an "official" way of adding metadata to a document — the [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element.
 - There are a lot of different types of `<meta>` elements that can be included in your page's `<head>`. 

## Specifying your document's character coding :
```html
	<meta charset="utf-8"/>
```

## Active learning: Experiment with character encoding :
```html
<meta name="author" content="Chris Mills" />
<meta
  name="description"
  content="The MDN Web Docs Learning Area aims to provide
complete beginners to the Web with all they need to know to get
started with developing web sites and applications." />
```
- Specifying an author is beneficial in many ways: it is useful to be able to understand who wrote the page, if you have any questions about the content and you would like to contact them. Some content management systems have facilities to automatically extract page author information and make it available for such purposes.
- Specifying a description that includes keywords relating to the content of your page is useful as it has the potential to make your page appear higher in relevant searches performed in search engines([[SEO]]).

#NOTE
### **Note:** In Google, you will see some relevant subpages of MDN Web Docs listed below the main homepage link — these are called sitelinks, and are configurable in [Google's webmaster tools](https://search.google.com/search-console/about?hl=en) — a way to make your site's search results better in the Google search engine.

## Adding custom icons to your site :
```html
<link rel="icon" href="favicon.ico" type="image/x-icon" />
```

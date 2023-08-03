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
- There are lots of other icon types to consider these days as well. For example, you'll find this in the source code of the MDN Web Docs homepage:
```html
<!-- third-generation iPad with high-resolution Retina display: -->
<link
  rel="apple-touch-icon-precomposed"
  sizes="144x144"
  href="https://developer.mozilla.org/static/img/favicon144.png" />
<!-- iPhone with high-resolution Retina display: -->
<link
  rel="apple-touch-icon-precomposed"
  sizes="114x114"
  href="https://developer.mozilla.org/static/img/favicon114.png" />
<!-- first- and second-generation iPad: -->
<link
  rel="apple-touch-icon-precomposed"
  sizes="72x72"
  href="https://developer.mozilla.org/static/img/favicon72.png" />
<!-- non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->
<link
  rel="apple-touch-icon-precomposed"
  href="https://developer.mozilla.org/static/img/favicon57.png" />
<!-- basic favicon -->
<link
  rel="icon"
  href="https://developer.mozilla.org/static/img/favicon32.png" />
```

# [Open Graph Data](https://ogp.me/) : 
- [Open Graph Data](https://ogp.me/) is a metadata protocol that Facebook invented to provide richer metadata for websites.
```html
<meta
  property="og:image"
  content="https://developer.mozilla.org/mdn-social-share.png" />
<meta
  property="og:description"
  content="The Mozilla Developer Network (MDN) provides
information about Open Web technologies including HTML, CSS, and APIs for both websites
and HTML Apps." />
<meta property="og:title" content="Mozilla Developer Network" />
```

# [Twitter Cards](https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/abouts-cards) :
- Twitter also has its own similar proprietary metadata called Twitter Cards, which has a similar effect when the site's URL is displayed on twitter.com.
```html
<meta name="twitter:title" content="Mozilla Developer Network" />
```
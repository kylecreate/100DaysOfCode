---
tags:
  - WebDev
---
Adding more meta data into the content of the webpage.
* [Metadata in HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML)

[Adding an Author and Description to the Metadata - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#adding_an_author_and_description)
- `name` specifies the type of meta element it is; what type of information it contains.
- `content` specifies the actual meta content.
It’s important to define the author of the page and provide a good description of that webpage to be able to be seen in search engines *(should the page be uploaded to a server in the future.)*.

[Adding custom image icons to your site - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#adding_custom_icons_to_your_site)
To further enrich your site design, you can add references to custom icons in your metadata, and these will be displayed in certain contexts. The most commonly used of these is the **favicon** (short for "favorites icon", referring to its use in the "favorites" or "bookmarks" lists in browsers).
* The image created for this should be 16px x 16px.

[Applying CSS/JavaScript to HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#applying_css_and_javascript_to_html)
Just about all websites you'll use in the modern day will employ CSS to make them look cool, and JavaScript to power interactive functionality, such as video players, maps, games, and more. These are most commonly applied to a web page using the `<link>` element and the `<script>` element, respectively.
* Example
	* `<link rel="stylesheet" href="my-css-file.css"/>` - To link a CSS file
	* `<script src="my-js-file.js"></script>` - To link a JavaScript file
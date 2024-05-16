---
tags:
  - WebDev
---
Going to be learning about adding links to an HTML page

Links that are in the head element aren’t the links that he’s referring to. He’s referring to links to outside of the “server” that go to another part of the web.

[Anchor Tag - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)
* This element (or _anchor_ element), with its `href` attribute, creates a hyperlink to web pages, files, email addresses, locations in the same page, or anything else a URL can address.
	* Example: `<a href="https://example.com">Website</a>`

[Absolute Reference w/ Anchor Tag - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#linking_to_an_absolute_url)
* Full address to the webpage that we’re going to
	* Example: `<a href="https://example.com">Website</a>`

[Relative Reference w/ Anchor Tag - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#linking_to_relative_urls)
* Linking to another page on the current website
	* Example: `<a href="//example.com">Scheme-relative URL</a>`

[Internal Reference w/ Anchor Tag - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#linking_to_an_element_on_the_same_page)
* Linking to either another section or heading of the page that you’re currently on.
	* Example: `<p><a ref="#Section-Down">Jump to a section below</a></p>`

[Section Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)
* This element represents a generic standalone section of a document, which doesn't have a more specific semantic element to represent it. Sections should always have a heading, with very few exceptions.
	* Example: `<section></section>`

[Nav(Navigation) Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav)
* This element represents a section of a page whose purpose is to provide navigation links, either within the current document or to other documents. Common examples of navigation sections are menus, tables of contents, and indexes.
```HTML file:navigation-example fold
<nav>
  <ol>
    <li><a href="#">Bikes</a></li>
    <li><a href="#">BMX</a></li>
  </ol>
</nav>
```

[Download Link - MDN](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/download)
* This property is a string indicating that the linked resource is intended to be downloaded rather than displayed in the browser.
	* Example: `<li>Download an <a href="html5.png" download>HTML5 Favicon</a></li>`

[Email Link - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#href)
* *Not advised since the search webpage spiders will grab them*
* Example: `<li>Contact me at <a href="mailto:email@email.com">my email address</a></li>`

[Phone Number Link - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#href)
* Example: `<li>Dial <a href="tel:+1233335555">my phone number</a></li>`

[Target Attribute for links - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#target)
* Where to display the linked URL, as the name for a _browsing context_ (a tab, window, or `<iframe>`). The following keywords have special meanings for where to load the URL.
	* Refer to list in the link

Having a `/` in the `href` link will link back to the root of the website no matter what.
* Example: `<a href="/">Back to Home</a>`

Link naming conventions and what you don’t want to do
1. Avoid printing the full web address to the page, don’t add the URL to the text of the link
2. Avoid “links to” phrase, we all know it’s a link
	* IE: *“This links to info…”* – Not needed
3. Keep link text short to the exact topic. No need for sentences!
4. Avoid having links that say *“click here”*. It provides no meaning to you or the user using the web page. Possibly confusing to others and yourself.
	* **Keep it Short!**
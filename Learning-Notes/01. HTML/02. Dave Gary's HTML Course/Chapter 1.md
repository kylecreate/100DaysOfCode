---
tags:
  - WebDev
---
### What is HTML?
[HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML)
HTML: An acronym for **Hypertext Markup Language** which is the most basic building block of the web and defines the meaning and structure of web content.
* “Hypertext” refers to links that connect web pages to one another.
	* This can be within one website or another website somewhere else.
* HTML uses “markup” to annotate text, images, and other content for display on a web browser.
### Programs Needed (and suggested)
1. Google Chrome
	1. Dark New Tab extension for new tabs, since dark mode is good
	2. uBlock Origin - to remove ads *(not suggested in video, but something that should always be done)*
2. Visual Studio Code (or Codium)
	1. Prettier extension *(for formatting code)*
	2. VSCode-icons *(to show icons next to files)*
	3. GitHub Theme
	4. Live Server *(to view webpages in real time)*

*Showing how to navigate through VSCode and open the first lesson folder*

Always keep the `index.html` clean of any spaces or and lower case.
* Windows won’t complain about it, but when a web server reads it, it could cause some sort of problem.
* Can also use hyphens or dashes

### <u>Our First HTML Elements</u>
[HTML Root Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)
Creating our first HTML element is the `<html></html>` element
* Every page starts with this tag, and everything else for an HTML pages goes between it.
* After using the W3C Validator service *(mentioned below)*, we need to add a `lang` attribute so that the webpage knows what language we’re using and so will the internet (should we upload the file to a web server)

After creating the HTML root element, the page then has **two main areas**
1. An area that contains data on the page but cannot be seen by the user but is considered to be metadata about the page
	* `<head></head>` element - Metadata about the page goes here; **can’t be seen by users**
	* [HTML Head Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head)
2. This is the part of the webpage that everyone sees in their browser
	* `<body></body>` element - Where the rest of the HTML elements go that can be seen by everyone
	* [HTML Body Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)

Inside on the head elements of the page, we can insert the title element.
* `<title>texthere</title>` element - This element will show the title in the browser’s tab and show the text that’s been provided for it.
* [HTML Title Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)

Inside of the body element, we input a `<h1>` element
* The `<h1>` element (or heading element) is the biggest heading element you can have on a page. You should only have 1 `<h1>` per page. These are like titles kind of like what your page is about.
	* [HTML Heading Elements - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)
	* The other heading elements (2-6) can be on a webpage multiple times. The lower the number, the smaller the text.

Adding some CSS to the page to make it easier to read for our eyes *(this is optional, but also not recommended in the future. Will learn about that later on)*
* [HTML Style Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style)
* This will act as a stylesheet until you create a separate file the CSS for the site/application being created.
* Per the example from the video, here’s what everything does…
	* Calling `html` will call for the whole document to use the same font-size for everything (including headers) to 22px tall.
	* Calling `body` will call for the body of the document to use the background color of the webpage to `#333` and the color of the text to whitesmoke.

When using the Live Server extension, the webpage being used is an IP address **which only YOU can see** and no one else.
* Creates your own local server, which is called a Dev Environment
* The server can be stopped by clicking on the same spot as starting the server

To tell if our HTML files have any errors or problems in them, we can use the [W3C Markup Validation Service](https://validator.w3.org/)
* W3C stands for **World Wide Web Consortium**
1. According to the Validator, we needed to add the charset metadata tag
	* [Character Encoding (charset) - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#specifying_your_documents_character_encoding)
	* This element specifies the document's character encoding — the character set that the document is permitted to use. `utf-8` is a universal character set that includes pretty much any character from any human language.
2. Need to add `<!DOCTYPE html>` at the beginning of every HTML file
	* [Doctype - MDN](https://developer.mozilla.org/en-US/docs/Glossary/Doctype)
	* The sole purpose is to prevent a browser from switching into so-called ["quirks mode"](https://developer.mozilla.org/en-US/docs/Web/HTML/Quirks_Mode_and_Standards_Mode) when rendering a document; that is, the "`<!DOCTYPE html>`" doctype ensures that the browser makes a best-effort attempt at following the relevant specifications, rather than using a different rendering mode that is incompatible with some specifications.
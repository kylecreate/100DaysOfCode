---
tags:
  - WebDev
---
HTML achieves document organization with semantics. Going to improve our code with semantic HTML.

What we have already added over the lessons that have been watched.
* Adding a hierarchy of headers (only 1 `h1` per page, title for the whole page)
* Writing semantic HTML helps us quickly read and see the different sections of a webpage.
	* Added a `nav` element to the page which is a semantic element
	* Added an `hr` element to help make line brakes in the page for different sections/topics.
* <u>Semantic</u> - The use of HTML tags that convey the meaning—or semantics—of the content contained within them.
* A list is also semantic HTML
* There can be more than one `nav` element in a page, could also be in the footer which is commonly done.
	* Important that they’re labeled for assistive technology to know what `nav` does what.

[Header Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header)
* Can be more than one header element per page, however it needs to follow the header hierarchy.
	* This element represents introductory content, typically a group of introductory or navigational aids. It may contain some heading elements but also a logo, a search form, an author name, and other elements.

[Main Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main)
* There can only be one main element per page, which would make sense by definition.
	* This element represents the dominant content of the `<body>` of a document. The main content area consists of content that is directly related to or expands upon the central topic of a document, or the central functionality of an application.

[Footer Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer)
* Just like the header element, there can be more than one footer per page.
	* This element represents a footer for its nearest ancestor sectioning content or sectioning root element. A `<footer>` typically contains information about the author of the section, copyright data or links to related documents.

[Aside Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside)
* This element represents a portion of a document whose content is only indirectly related to the document's main content. Asides are frequently presented as sidebars or call-out boxes.

[Details Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details)
* Similar to a toggle button on Obsidian/Notion
	* This element creates a disclosure widget in which information is visible only when the widget is toggled into an "open" state. A summary or label must be provided using the `<summary>` element.

[Summary Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary)
* Used with the Details Element
	* This element specifies a summary, caption, or legend for a `<details>` element's disclosure box. Clicking the `<summary>` element toggles the state of the parent `<details>` element open and closed.

[Mark Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/mark)
* Used like a highlighter on paper and can be changed with CSS
	* This element represents text which is **marked** or **highlighted** for reference or notation purposes due to the marked passage's relevance in the enclosing context.

[Time Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time)
* This element represents a specific period in time. It may include the `datetime` attribute to translate dates into machine-readable format, allowing for better search engine results or custom features such as reminders, and is also good for web accessibility for screen readers and other devices.

There is no semantic meaning to a `div` element. Think of `div` as a section without the semantic meaning. Just stands for divider and has no meaning. Just a block element.
* Avoid using `div` and `span` until you understand how to use semantic elements.

There’s a debate about whether or not to use `article` or `section` is the proper choice.
* An `article` has a clear topic/subject
* A `section` is more generic

Downloaded a [Chrome Extension called HTML Outliner](https://chromewebstore.google.com/detail/html5-outliner/afoibpobokebhgfnknfndkgemglggomo) which will show the outline of the page that you’re on to see how it looks.
* The `aside` and `nav` are untitled on the page we’ve created which is fine for now.
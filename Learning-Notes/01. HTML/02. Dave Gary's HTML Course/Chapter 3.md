---
tags:
  - WebDev
---
Much of the text content on a webpage will contain heading and paragraph elements.

Headings have a hierarchy to them, which means that `<h1>` should only be on a page once.
* `<h2> - <h6>` can be on the page multiple times, known as subtopics
* We can change the size of all the heads and paragraphs to be the same size (pixel wise) using CSS, which will be talked about in the future.

An element that doesn’t really provide any semantic meaning, but visually helps us on the page is the `<hr>` element.
* [HR Element aka The Thematic Break - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/hr)
	* This element represents a thematic break between paragraph-level elements: for example, a change of scene in a story, or a shift of topic within a section.
	* Shows a long line going across the webpage, can be changed with CSS if needed

White Space Collapsing
* [How is White Space handled by HTML, CSS, and the DOM - MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Whitespace)
	* <u>Whitespace</u> is any string of text composed only of spaces, tabs or line breaks (to be precise, CRLF sequences, carriage returns or line feeds).
	* In the case of HTML, whitespace is largely ignored — whitespace in between words is treated as a single character, and whitespace at the start and end of elements and outside elements is ignored. Take the following minimal example:

Line Brakes
* [Line Breaks (using br) - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br)
	* This element produces a line break in text (carriage-return). It is useful for writing a poem or an address, where the division of lines is significant.

Block level elements vs. Inline elements
* [Block Level Content in HTML - MDN](https://developer.mozilla.org/en-US/docs/Glossary/Block-level_content)
	* In a block layout, boxes are laid out one after the other, vertically, beginning at the top of a containing block. Each box's left outer edge touches the left edge of the containing block. A block-level element always starts on a new line.
* [Inline Element Content in HTML - MDN](https://developer.mozilla.org/en-US/docs/Glossary/Inline-level_content)
	* In inline layout, a mixed stream of text, replaced elements, and other inline boxes are laid out by fragmenting them into a stack of line boxes. Within each line box, inline-level boxes are aligned to each other vertically or horizontally, depending on the writing mode. Typically, they are aligned by the baselines of their text. This can be changed with CSS.

[Emphasis Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em)
* Inline level element
	* This element marks text that has stress emphasis. The `<em>` element can be nested, with each level of nesting indicating a greater degree of emphasis.
		* Example: `This paragraph has <em>random</em> text.`

[Strong Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong)
* Inline level element
	* This element indicates that its contents have strong importance, seriousness, or urgency. Browsers typically render the contents in bold type.
		* Example: `This paragraph has <strong>random text</strong>.`

HTML entities
* [HTML Entities - MDN](https://developer.mozilla.org/en-US/docs/Glossary/Entity)
	* An HTML **entity** is a piece of text ("string") that begins with an ampersand (`&`) and ends with a semicolon (`;`). HTML entities are frequently used to display reserved characters (which would otherwise be interpreted as HTML code), and invisible characters (like non-breaking spaces).
		* Example: `&amp; - Will show & in HTML`

Abbreviation Element
* [The Abbreviation element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/abbr)
* Not available to screen readers or other assisted technology
	* This element represents an abbreviation or acronym.
		* Example: `<abbr title="Kansas">KS</abbr>` - When hovered over with the mouse, you should see Kansas appear in a small box.

Address Element
* [The Contact Address Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address)
	* This element indicates that the enclosed HTML provides contact information for a person or people, or for an organization.
		* The text that’s inserted into this element will be italicized.
		* Example: `<address>1234 Main Street USA</address>`
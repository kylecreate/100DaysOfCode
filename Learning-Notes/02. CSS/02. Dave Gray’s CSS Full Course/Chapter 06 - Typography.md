---
tags:
  - WebDev
---
Typography is the way that text is arranged and presented.
*Goes over the useage of the HTML elements being used for this chapter*

[Text Decoration Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration)
* This property sets the appearance of decorative lines on text.
	* Example: `text-decoration: green underline;`

[Text Transform Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)
* This property specifies how to capitalize an element's text.
	* Uppercase, capitalize, lowercase, or no changes with text
	* Example: `text-transform: lowercase;`

[Text Align Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
* This property sets the horizontal alignment of the inline-level content inside a block element or table-cell box.
* Real life example would be a paper written for school or a academic paper.
	* Example: `text-align: right;`

[Text Indent Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent)
* This property sets the length of empty space (indentation) that is put before lines of text in a block.
* Real life example of this would be to indent left at the start of a paragraph.
* *Good to use the em unit*
	* Example: `text-indent: 2em;`

[Line Height Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)
* This property sets the height of a line box.
* Real life example of this would be doing a book report that needs to be spaced 1.5 times than normal when typing it out on a computer.
* *A good readability is 1.5*
	* Example: `line-height: 1.5;`

[Letter Spacing Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)
* This property sets the horizontal spacing behavior between text characters.
* Real life example of this would be a quote from someone famous that’s being shown somewhere for importance.
* *Don’t use too often*
	* Example: `letter-spacing: 1px;`

[Word Spacing Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/word-spacing)
* This property sets the length of space between words and between tags.
* Real life example of this would be a quote from someone famous that’s being shown somewhere for importance.
* *Don’t use too often*
	* Example: `word-spacing: 1rem;`

[Font Weight Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)
* This property sets the weight (or boldness) of the font. The weights available depend on which font is currently set.
* Real life example would be when you’re trying to make something known or a header for a section of text.
	* Example: `font-weight: bold;`

[Font Style Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)
* This property sets whether a font should be styled with a normal, italic, or oblique face from its font-family.
* Real life example of this would be when you’re doing vocabulary for school and you need to underline the words that need to be defined.
	* Example: `font-style: italic;`

[Font Family Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)
* This property specifies a prioritized list of one or more font family names and/or generic family names for the selected element.
* Real life example of this is using Times New Romans when writing a paper for school since the teacher said it was the only font that you’re allowed to use.
	* Example: `font-family: 'Open-Sans', sans-serif;`

[Adding a external font from Google Fonts](https://fonts.google.com/)
* Adding the import tag makes it easier and less of a mess when adding the text that is wanted for the webpage/application.
* Either for the body, paragraph, heading, or the * (HTML wildcard), you can set the font-family to be whatever was chosen along with 1-2 backups should Google Fonts be down for some reason.
```CSS file:adding-a-google-font fold
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

p {
	font-family: 'Roboto', sans-serif;
}
```

[Web Safe Fonts](https://www.cssfontstack.com/)

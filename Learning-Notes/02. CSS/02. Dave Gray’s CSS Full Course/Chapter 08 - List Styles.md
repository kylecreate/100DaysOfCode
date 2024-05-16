---
tags:
  - WebDev
---
*Goes over the way that the HTML and CSS file are laid out.*

[List Style Type Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
* This property sets the marker (such as a disc, character, or custom counter style) of a list item element.
	* Example #1: `list-style-type: disc;` - changes the squares to dots
	* Example #2: `list-style-type: space-counter;` - changes to different space emojis

[Start Attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol#start)
* An integer to start counting from for the list items.
	* Example: `<ol start="3"></ol>` - the list will start with 3 and go on

[Reverse Attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol#reversed)
* This Boolean attribute specifies that the list's items are in reverse order. Items will be numbered from high to low.
	* Example: `<ol start="3" reversed></ol>` - the list will start with 3 and go down to 0

[List Style Position Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-position)
* This property sets the position of the `::marker` relative to a list item.
	* Example: `list-style-position: inside;` - will set the list to be inside of the list

If you set the color of the `ul`/`ol`, it will change the text and the bullet points/numbers/letters to the color that was provided.

[List Style Image Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-image)
* This property sets an image to be used as the list item marker.
	* Example: `list-style-img: url('../images/checkmark.png');` - adds a checkmark image next to each item

Shorthand Example of the List Style Property
* This includes type, position, and image
* `list-style: square url('../images/checkmark.png') inside;`

[:nth-child() Pseudo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child)
* This class matches elements based on the indexes of the elements in the child list of their parents. In other words, the `:nth-child()` selector selects child elements according to their position among all the sibling elements within a parent element.
	* Example: `li:nth-child(2);` - selects the 2nd list item in a unordered/ordered list

[::marker Pseudo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker)
* This class selects the marker box of a list item, which typically contains a bullet or number.
	* Example: `li::marker { content: '+'; font-size: 1.2em; }` - Added a plus sign in a slightly larger font for the bullet points.
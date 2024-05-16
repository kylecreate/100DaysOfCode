---
tags:
  - WebDev
---
*Goes over what’s in the HTML and CSS files*

The display property in CSS relates back to something that we learned in the HTML course which includes block level elements vs inline level elements. The paragraph elements in the current HTML file before changing anything is an inline block level element.

[Display Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
* This property sets whether an element is treated as a block or inline box and the layout used for its children, such as flow layout, grid or flex.
* Examples are below…

[Display Block - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/display#block)
* The element generates a block box, generating line breaks both before and after the element when in the normal flow.
	* Example: `display: block;`

[Display Inline - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/display#inline)
* The element generates one or more inline boxes that do not generate line breaks before or after themselves. In normal flow, the next element will be on the same line if there is space.
	* Example: `display: inline;`

[Display Flex - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/display#flex)
* *Going to be covered in the future*
* The element behaves like a block-level element and lays out its content according to the flexbox model.

[Display None - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/display#display_none)
* Using a `display` value of `none` on an element will remove it from the accessibility tree. This will cause the element and all its descendant elements to no longer be announced by screen reading technology or be shown on the page at all.

[Display Property Example from MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/display#examples)
* In the example linked, there is two block-level container elements, each one with three inline children. Below that, there is a select menu that allows you to apply different `display` values to the containers, allowing you to compare and contrast how the different values affect the element's layout, and that of their children.
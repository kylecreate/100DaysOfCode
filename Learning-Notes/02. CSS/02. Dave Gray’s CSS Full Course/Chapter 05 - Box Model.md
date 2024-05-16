---
tags:
  - WebDev
---
*Removing most of the current CSS rules that were created except for the h1 rule to view the box model of it.*

Using the Developer Tools in Google Chrome and viewing the H1 tag, we see…
* The color blue is the <u>content</u> inside of the box
* The color green for the <u>padding</u> around the content being shown/used.
* The color yellow for the <u>border</u> that is around the padding
* The color orange for the <u>margin</u> that is around everything else creating the box.

[The CSS Box Model - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)
* Everything in CSS has a box around it and understanding those boxes is key to being able to create more complex layouts within CSS and to align items with other items.
	* [Examples of different display types - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model#examples_of_different_display_types)
* The CSS box model as a whole applies to block boxes and defines how the different parts of a box — margin, border, padding, and content — work together to create a box that you can see on a page. Inline boxes use just _some_ of the behavior defined in the box model.
	* <u>Content Box</u>: The area where the content created is displayed.
		* Used with properties such as `width` and `height`.
	* <u>Padding Box</u>: The padding sits around the content as white space.
		* Used with the `padding` property.
	* <u>Border Box</u>: The border box wraps the content and any padding.
		* Used with the `border` property.
	* <u>Margin Box</u>: The margin is the outermost layer, wrapping the content, padding, and border as whitespace between this box and other elements.
		* Used with the `margin` property.
* Refer to the Google Chrome developer tools in the Computed tab to see what the box model looks like for certain content.

[Box-Sizing Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)
* The `box-sizing` CSS property sets how the total width and height of an element is calculated. Also best used with CSS Reset.
	* Example: `box-sizing: border-box;`

[Margin Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
* The `margin` CSS shorthand property sets the margin area on all four sides of an element.
* Adding auto to this element selects a suitable margin to use.
	* Example: This value can be used to center an element.
		* `margin: 1em auto;`

[Padding Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)
* The `padding` CSS shorthand property sets the padding area on all four sides of an element at once.
* An element's padding area is the space between its content and its border.
	* Example: `padding: 1em;`

[Border Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/border)
* The `border` shorthand CSS property sets an element's border.
	* Example: `border: 2px dashed red;`

[Outline Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/outline)
* The `outline` CSS shorthand property sets most of the outline properties in a single declaration.
	* Example: `outline: 2px double black;`


---
tags:
  - WebDev
---
*Goes over the HTML and CSS file, explaining what everything does and talks about if you want to change the font back to Roboto*

Image elements are not block level elements, they’re actually inline elements

[Background-Image - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image)
* This property sets one or more background images on an element.
	* Example: `background-img: url('../imgs/img-name-here.png');`

[Background-Repeat - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat)
* This property sets how background images are repeated. A background image can be repeated along the horizontal and vertical axes, or not repeated at all.
	* Example: `background-repeat: repeat-x;`

[Background-Size - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size)
* This property sets the size of the element's background image. The image can be left to its natural size, stretched, or constrained to fit the available space.
	* Example: `background-size: cover;`

[Text-Shadow - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow)
* This property adds shadows to text. It accepts a comma-separated list of shadows to be applied to the text and any of its `decorations`. Each shadow is described by some combination of X and Y offsets from the element, blur radius, and color.
	* Example: `text-shadow: 1px 1px 5px red;`

[Background-Position - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position)
* This property sets the initial position for each background image. The position is relative to the position layer set by `background-origin`.
	* Example: `background-position: top right;`

[Linear-Gradient Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient)
* This function creates an image consisting of a progressive transition between two or more colors along a straight line. Its result is an object of the `<gradient>` data type, which is a special kind of `<image>`.
	* Example: `background: linear-gradient(to right, red, blue, green);`

[Background Shorthand - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/background)
* This shorthand property sets all background style properties at once, such as color, image, origin and size, or repeat method. Component properties not set in the `background` shorthand property value declaration are set to their default values.
	* Example: `background: center / contain no-repeat url("../../media/examples/firefox-logo.svg"), #eee 35% url("../../media/examples/lizard.png");`

[Background-Clip - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/background-clip)
* This property sets whether an element's background extends underneath its border box, padding box, or content box.
* Should use [canIuse](https://caniuse.com/) to see what I can use on a website depending on if something is compatible or not.
	* Example: `background-clip: text; -webkit-background-clip: text;`
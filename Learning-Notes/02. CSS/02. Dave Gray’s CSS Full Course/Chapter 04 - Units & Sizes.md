---
tags:
  - WebDev
---
CSS units determine the size of everything in your page. Going to cover the most common CSS units.

[CSS Values and Units - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)
* Most commonly used is pixels (px) as far as absolute units
	* Which is equivalent to 1/96th of 1in

[Font Size Selector - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)
* This property sets the size of the font. Changing the font size also updates the sizes of the font size-relative `<length>` units, such as `em`, `ex`, and so forth.
* Default font-size on any page is 16px *(not including the header elements)*
	* Example: `font-size: 12px;`

[Pixels (px) - MDN](https://developer.mozilla.org/en-US/docs/Glossary/Pixel)
* A pixel is the smallest building block of a graphical display like a computer screen.
	* Example #1: `font-size: 12px;`
	* Example #2: Desktop resolution: 1920px x 1080px

[Percentage (%) - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#percentages)
* This represents a percentage value. It is often used to define a size as relative to an element's parent object.
* Normally wouldn’t do this for a font-size. Would be good for something like height and width or the sizing of different elements.
	* Example: `width: 30%; margin-right: 60%;`

[REM Unit - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#numbers_lengths_and_percentages)
* Font size of the root element.
	* Example: `font-size: 1rem;`
	* REM stands for Root EM
	* 1rem = 16px | 2rem = 32px

[EM Unit - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#numbers_lengths_and_percentages)
* Font size of the parent, in the case of typographical properties like `font-size`, and font size of the element itself, in the case of other properties like `width`.
	* Example: `font-size: 2em;`
	* Could also be used for the padding selector *(will be talked about in the future)*

[CH Unit - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#numbers_lengths_and_percentages)
* The advance measure (width) of the glyph "0" of the element's font.
	* This comes from print and a magazine layout to have a certain width depending on the character size.
	* Example: `width: 40ch;`

[VW Unit - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#numbers_lengths_and_percentages)
* 1% of the viewport's width.
	* Example: `width: 50vw;`

[VH Unit - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#numbers_lengths_and_percentages)
* 1% of the viewport's height.
	* Example: `width: 50vh;`

CSS Reset
* A reset stylesheet is a collection of CSS rules used to clear the browser's default formatting of HTML elements, removing potential inconsistencies between different browsers. It also prevents developers from unknowingly relying on the browser default styling and force them to be explicit about the styling they want to apply on the page.
```CSS file:CSS-Reset-Example fold
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
```
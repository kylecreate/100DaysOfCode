---
tags:
  - WebDev
---
*Goes over the HTML and CSS files with what’s currently on the page*

[Position Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
* This property sets how an element is positioned in a document. The `top`, `right`, `bottom`, and `left` properties determine the final location of positioned elements.
	* Example: `position: absolute;`

[Position Static - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/position#static)
* The element is positioned according to the normal flow of the document. The `top`, `right`, `bottom`, `left`, and `z-index` properties have _no effect_. **This is the default value**.
	* Example: `position: static;`

[Position Absolute - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/position#absolute)
* The element is removed from the normal document flow, and no space is created for the element in the page layout. The element is positioned relative to its closest positioned ancestor (if any) or to the initial containing block. Its **final position is determined by the values of `top`, `right`, `bottom`, and `left`**.
	* Example: `position: absolute;`

[Position Relative - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/position#relative)
* The element is positioned according to the normal flow of the document, and then offset _relative to itself_ based on the values of `top`, `right`, `bottom`, and `left`. The offset does not affect the position of any other elements; thus, the space given for the element in the page layout is the same as if position were `static`.
	* Example: `position: relative;`

[Position Fixed - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/position#fixed)
* The element is removed from the normal document flow, and no space is created for the element in the page layout. The element is positioned relative to its initial containing block, which is the viewport in the case of visual media. Its **final position is determined by the values of `top`, `right`, `bottom`, and `left`.**
	* Example: `position: fixed;`

[Position Sticky - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/position#sticky)
* The element is positioned according to the normal flow of the document, and then offset relative to its _nearest scrolling ancestor_ and containing block (nearest block-level ancestor), including table-related elements, based on the values of `top`, `right`, `bottom`, and `left`. The offset does not affect the position of any other elements.
	* Example: `position: sticky;`

[Z-Index - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index)
* This property sets the z-order of a positioned element and its descendants or flex and grid items. Overlapping elements with a larger z-index cover those with a smaller one.
	* Example: `z-index: 1;`

For taking something off of the page for only a screen reader or some sort of accessibility helper, you can set the `left` attribute to -10000px. This way, a normal user can’t see/read it, but the screen reader will still be able to see it.
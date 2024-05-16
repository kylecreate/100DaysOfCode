---
tags:
  - WebDev
---
*Goes over the HTML and CSS file before starting on flexbox*

**`Divs` are block elements**

[Display Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
* This property sets whether an element is treated as a block or inline box and the layout used for its children, such as flow layout, grid or flex.
	* Example: `display: block;`

[Display Flex Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/display#flex)
* The element behaves like a block-level element and lays out its content according to the flexbox model.
	* Example: `display: flex;`

[Align Items Flex-Start - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items#flex-start)
* Used in flex layout only, aligns the flex items flush against the flex container's main-start or cross-start side.
	* Example: `align-items: flex-start;`

[Align Items Flex-End - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items#flex-end)
* Used in flex layout only, aligns the flex items flush against the flex container's main-end or cross-end side.
	* Example: `align-items: flex-end;`

[Gap - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/gap)
* This property sets the gaps (gutters) between rows and columns.
	* Example: `gap: 10%;`

[Space-Around - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content#space-around)
* The items are evenly distributed within the alignment container along the main axis. The spacing between each pair of adjacent items is the same. The empty space before the first and after the last item equals half of the space between each pair of adjacent items.
	* Example: `justify-content: space-around;`

[Space-Between - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content#space-between)
* The items are evenly distributed within the alignment container along the main axis. The spacing between each pair of adjacent items is the same. The first item is flush with the main-start edge, and the last item is flush with the main-end edge.
	* Example: `justify-content: space-between;`

[Space-Evenly - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content#space-evenly)
* The items are evenly distributed within the alignment container along the main axis. The spacing between each pair of adjacent items, the main-start edge and the first item, and the main-end edge and the last item, are all exactly the same.
	* Example: `justify-content: space-evenly;`

[Align Items - Flex-Start - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items#flex-start)
* Used in flex layout only, aligns the flex items flush against the flex container's main-start or cross-start side.
	* Example: `align-items: flex-start;`

[Align-Items - Flex-End - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items#flex-end)
* Used in flex layout only, aligns the flex items flush against the flex container's main-end or cross-end side.
	* Example: `align-items: flex-end;`

[Flex Direction Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction)
* property sets how flex items are placed in the flex container defining the main axis and the direction (normal or reversed).
* `flex-direction: row;`
	* The flex container's main-axis is defined to be the same as the text direction. The **main-start** and **main-end** points are the same as the content direction.
* `flex-direction: row-reverse;`
	* Behaves the same as `row` but the **main-start** and **main-end** points are opposite to the content direction.
* `flex-direction: column;`
	* The flex container's main-axis is the same as the block-axis. The **main-start** and **main-end** points are the same as the **before** and **after** points of the writing-mode.
* `flex-direction: column-reverse;`
	* Behaves the same as `column` but the **main-start** and **main-end** are opposite to the content direction.

[Flex-Wrap Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap)
* This property sets whether flex items are forced onto one line or can wrap onto multiple lines. If wrapping is allowed, it sets the direction that lines are stacked.
* `flex-wrap: nowrap;`
	* The flex items are laid out in a single line which may cause the flex container to overflow. The **cross-start** is either equivalent to **start** or **before** depending on the `flex-direction` value. This is the default value.
* `flex-wrap: wrap;`
	* The flex items break into multiple lines. The **cross-start** is either equivalent to **start** or **before** depending `flex-direction` value and the **cross-end** is the opposite of the specified **cross-start**.
* `flex-wrap: wrap-reverse;`
	* Behaves the same as `wrap` but **cross-start** and **cross-end** are permuted.

[Flex-Flow Shorthand - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow)
* The shorthand property specifies the direction of a flex container, as well as its wrapping behavior.
	* Example: `flex-flow: row-reverse nowrap;`

[Align-Content Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content)
* property sets the distribution of space between and around content items along a flexbox's cross-axis or a grid's block axis.
	* Example: `align-content: space-between;`

[Flex-Basis Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis)
* *Similar to using min-width*
* This property sets the initial main size of a flex item. It sets the size of the content box unless otherwise set with `box-sizing`.
	* Example: `flex-basis: 200px;`

[Flex-Grow Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow)
* This property sets the flex grow factor, which specifies how much of the flex container's remaining space should be assigned to the flex item's main size.
	* Example: `flex-grow: 2;`

[Flex-Shrink Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink)
* This property sets the flex shrink factor of a flex item. If the size of all flex items is larger than the flex container, items shrink to fit according to `flex-shrink`.
	* Example: `flex-shrink: 2;`

[Flex Shorthand - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)
* This shorthand property sets how a flex _item_ will grow or shrink to fit the space available in its flex container.
	* Example: `flex: 1 1 100px;`

[Order Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/order)
* This property sets the order to lay out an item in a flex or grid container. Items in a container are sorted by ascending `order` value and then by their source code order. Items not given an explicit `order` value are assigned the default value of `0`.
	* Example: `order: -1;`

Best way to get practice with CSS Flexbox is by playing [Flexbox Froggy](https://flexboxfroggy.com/)
* There’s 24 challenges that can help you think about the different properties while using CSS Flexbox
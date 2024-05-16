---
tags:
  - WebDev
---
*Going over the code from the mini-project and talking about the pseudo selectors/elements that were used.*

Pseudo selectors include both classes and elements. What’s the difference between the two?
* <u>Pseudo Class</u> is a selector that selects elements that are in a specific state. These use a single colon.
* A <u>Pseudo Element</u> is similar to a class, but they act like you’ve added a new HTML element into your document. They also use 2 colons instead of one like the class selector does.

[Pseudo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* This is a keyword added to a selector that specifies a special state of the selected element(s). For example, the pseudo-class `:hover` can be used to select a button when a user's pointer hovers over the button and this selected button can then be styled.
* Refer to example in link

[Pseudo Element - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* This is a keyword added to a selector that lets you style a specific part of the selected element(s).
* Refer to example in link

[Descendent Selector - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator)
* This is typically represented by a single space (" ") character — combines two selectors such that elements matched by the second selector are selected if they have an ancestor (parent, parent's parent, parent's parent's parent, etc.) element matching the first selector. Selectors that utilize a descendant combinator are called _descendant selectors_.
	* Example: `selector1, selector2 {-CSS RULE HERE-};`

[is() Pseudo Selector - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:is)
* This function takes a selector list as its argument, and selects any element that can be selected by one of the selectors in that list. This is useful for writing large selectors in a more compact form.
	* Example: `:is(ol, ul) {-CSS RULE HERE-};`

[Any-Link Pseudo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:any-link)
* This selector represents an element that acts as the source anchor of a hyperlink, independent of whether it has been visited. In other words, it matches every `<a>` or `<area>` element that has an `href` attribute. Thus, it matches all elements that match `:link` or `:visited`.
	* Example: `a:any-link {-CSS RULE HERE-};`

[:where Pseudo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:where)
* This function takes a selector list as its argument, and selects any element that can be selected by one of the selectors in that list.
	* Refer to the example in the link

[:target Pseudo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)
* This pseudo class represents a unique element (the _target element_) with an `id` matching the URL's fragment.
	* Refer to the example in the link

[:not Pseudo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:not)
* This pseudo class represents elements that do not match a list of selectors. Since it prevents specific items from being selected, it is known as the _negation pseudo-class_.
	* Refer to the example in the link

[:nth-child - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child)
* This matches elements based on the indexes of the elements in the child list of their parents. In other words, the `:nth-child()` selector selects child elements according to their position among all the sibling elements within a parent element.
	* Refer to the example in the link

[::after Pseudo Element - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)
* This element that is the last child of the selected element. It is often used to add cosmetic content to an element with the `content` property. It is inline by default.
	* Refer to the example in the link

[::before Pseudo Element - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)
* This element that is the first child of the selected element. It is often used to add cosmetic content to an element with the `content` property. It is inline by default.
	* Refer to the example in the link

[::first-letter Pseudo Element - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter)
* This applies styles to the first letter of the first line of a block container, but only when not preceded by other content (such as images or inline tables).
	* Refer to the example in the link
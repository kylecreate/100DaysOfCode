---
tags:
  - WebDev
---
*Goes over the HTML and CSS file with what is added and laid out*

Styling our link is an extension of the typography chapter since it’s still text. We can apply what we learned to our links. They also have their own default styles given.

If the link hasn’t been visited before, it’s a blue color. If the link has been visited before, then it becomes purple. When we hover over the link, it cursor changes to a pointer cursor. The last style that’s a default is when clicking on a link and not actually clicking it, the link then becomes red, when means the link is active.

[Text Decoration Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration)
* This property sets the appearance of decorative lines on text.
* Real world example would be giving x amount of words an underline in some text.
	* Example: `text-decoration: none;`

[Cursor Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor)
* This property sets the mouse cursor, if any, to show when the mouse pointer is over an element.
* Real would example of this would be giving the user the option to not being allowed to click on a link with a red circle and a line through it.
	* Example: `cursor: not-allowed;`

[Psuedo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* A keyword added to a selector that specifies a special state of the selected element(s).
	* Examples are below

[:visted Pseudo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited)
* This applies once the link has been visited by the user
	* Example: `a:visited{ color: yellow; }`

[:hover Pseudo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover)
* This matches when the user interacts with an element with a pointing device, but does not necessarily activate it.
	* Example: `a:hover{ color: red; }`

[:active Pseudo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:active)
* This represents an element (such as a button) that is being activated by the user. Usually when you click on a button or some text and drag down, you can see the effect.
	* Example: `a:active{ color: green; }`

[:focus Pseudo Class - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus)
* This represents an element (such as a form input) that has received focus. This is best seen when tabbing through the website/application for links and form boxes.
	* Example: `a:focus { color: black; }`

If wanting to use similar colors for the links and visited links, you can switch to HSL/HSLA colors to give it a darker/lighter color to give it a difference of being visited or not. You can also use the opacity property to give it a % darker/lighter.
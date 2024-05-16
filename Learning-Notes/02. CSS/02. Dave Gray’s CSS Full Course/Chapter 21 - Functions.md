---
tags:
  - WebDev
---
Going to learn CSS Functions

*Goes over the HTML and CSS file which is similar to the previous chapters, except this has a heading and paragraph elements.*

[List of all the CSS functions (*includes that those not covered*) - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Functions)

[Min Function - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/min)
* This function lets you set the smallest (most negative) value from a list of comma-separated expressions as the value of a CSS property value. The `min()` function can be used anywhere a `<length>`, `<frequency>`, `<angle>`, `<time>`, `<percentage>`, `<number>`, or `<integer>` is allowed.
* *Provide only one absolute value and then provide `vh`. No need to provide a percentage since it won’t look right.*
	* Example: `width: min(20vw, 200px);`

[Max Function - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/max)
* This function lets you set the smallest (most positive) value from a list of comma-separated expressions as the value of a CSS property value. The `max()` function can be used anywhere a `<length>`, `<frequency>`, `<angle>`, `<time>`, `<percentage>`, `<number>`, or `<integer>` is allowed.
	* Example: `width: max(20vw, 200px);`

[Clamp Function - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp)
* This function clamps a middle value within a range of values between a defined minimum bound and a maximum bound. The function takes three parameters: a minimum value, a preferred value, and a maximum allowed value.
	* Example: `font-size: clamp(1rem, 2.5vw, 2rem);`

[Calc Function - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/calc)
* This function lets you perform calculations when specifying CSS property values. It can be used with `<length>`, `<frequency>`, `<angle>`, `<time>`, `<percentage>`, `<number>`, or `<integer>` values.
	* Example: `width: calc(100% - 30px);`

[Filter Functions - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/filter)
* This property applies graphical effects like blur or color shift to an element. Filters are commonly used to adjust the rendering of images, backgrounds, and borders.
	* Example: `filter: blur(10px);`
	* *More examples provided on the linked page*

[Attribute Function - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/attr)
* This function is used to retrieve the value of an attribute of the selected element and use it in the stylesheet. It can also be used on pseudo-elements, in which case the value of the attribute on the pseudo-element's originating element is returned.
	* *Examples provided on the linked page*

[MinMax Function - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/minmax)
* This function defines a size range greater than or equal to _min_ and less than or equal to _max_. It is used with CSS Grids.
	* Example: `grid-template-columns: minmax(20px, auto) 1fr 1fr;`

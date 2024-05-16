---
tags:
  - WebDev
---
CSS variables are very useful. Imagine a large project and we have a hex color code that has been used multiple times in the CSS file. The boss says that we need to change the color in every instance of the code which would be a hassle. Instead, we can use CSS variables to be able to change it in one place.

*Goes over the HTML and CSS file from a previous chapter that is going to be used to learn about CSS Variables*

[:root Pseudo Class Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:root)
* This pseudo class matches the root element of a tree representing the document. In HTML, `:root` represents the `<html>` element and is identical to the selector `html`, except that its specificity is higher.
	* Review example provided in the link

[Var Function - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/var)
* This can be used to insert the value of a custom property (sometimes called a "CSS variable") instead of any part of a value of another property.
	* Example: `border-color: var(--BORDER-COLOR);`

[Adding a Dark Mode - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)
* This is used to detect if a user has requested light or dark color themes. A user indicates their preference through an operating system setting (e.g. light or dark mode) or a user agent setting.
	* Example: `@media (perfers-color-scheme: dark) { /* CSS RULES HERE */ }`
	* Refer to the example also in the Ch20 files
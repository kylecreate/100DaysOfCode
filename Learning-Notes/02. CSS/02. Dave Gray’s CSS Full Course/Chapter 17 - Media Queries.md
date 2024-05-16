---
tags:
  - WebDev
---
Media queries allow you to modify your site based on specific characteristics and parameters of your site. Most often, you look at the browser’s viewport width which is how the browser will tell what device and size your screen is based on the width.

*Goes over the HTML and CSS files*

There’s a meta tag that enables responsive design in the HTML file
`<meta name="viewport" content="width=device-width, initial-scale=1.0">`
* Necessary for responsive design and always will be in the Emmet Abbreviation

Syntax of a media query; how we write it out
```CSS file:media-query fold
@media <media type> and (condition: breakpoint) {
	/* CSS Rules here */
}
```

[Media Query - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)
* The at-rule can be used to apply part of a style sheet based on the result of one or more media queries. With it, you specify a media query and a block of CSS to apply to the document if and only if the media query matches the device on which the content is being used.
	* Refer to the example on the page linked
* *Easier to start with the smallest screen and then work your way to the largest screen when using this.*

 Vanilla CSS Media Queries Breakpoints![![Technical Stuff/Learning Notes/Mastering Front End Dev/CSS/Dave Gray’s CSS Full Course/#^Table]]
[Bootstrap](https://getbootstrap.com/) Media Queries Breakpoints
![![Technical Stuff/Learning Notes/Mastering Front End Dev/CSS/Dave Gray’s CSS Full Course/#^Table1]]
[Tailwind CSS](https://tailwindcss.com/) Media Queries Breakpoints
![![Technical Stuff/Learning Notes/Mastering Front End Dev/CSS/Dave Gray’s CSS Full Course/#^Table2]]
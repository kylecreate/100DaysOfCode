---
tags:
  - WebDev
---
*Goes over the structure of the HTML that’s been created for us*

1. [Element Selectors - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors#type_class_and_id_selectors)
	* Can only be used once
		* In the example below, we’re selecting the body to have the font-size of 22px.
```CSS file:element-selector-example fold
body {
	font-size: 22px;
}
```

2. [Class Selectors - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors#type_class_and_id_selectors)
	* Can be used more than once and are more specific than the Element Selectors
	* Similar to the normal element selector, but instead of choosing a certain part of the HTML page, you’re choosing a class that’s been created using `class="someclassname"` in an HTML element.
		* In the example below, we’re selecting the highlight class and transforming the letters in this element to become uppercase and have a background color of gold to make it look light it’s highlighted on paper.
```CSS file:class-selector-example fold
.highlight {
	text-transform: uppercase;
	background-color: gold;
}
```

3. [ID Selector - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors#type_class_and_id_selectors)
	* *Should use <u>class selectors</u> more often than ID selectors*
	* Similar to the previous 2 selectors, this will do the same thing but an ID that’s been created using `id="someidhere"` in an HTML element
		* In the example, we’re changing the element that has the unique id selector to have a text color of blue.
```CSS file:ID-selector-example fold
#unique {
	color: blue;
}
```

4. Group Selectors
	* This selector will have more than one element in this creating a group that will effect everything mentioned.
		* In this example, we’re selecting headings 1, 2, and 3 to change the color of the text to red.
```CSS file:group-selector-example fold
h1, h2, h3 {
	color: red;
}
```

5. [Universal Selector - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors)
	* This selector will select all of the elements of the webpage.
		* In the example,  this will change all of the text no matter what it is to the color green.
```CSS file:universal-selector-example fold
* {
	color: green;
}
```

CSS works from the top down meaning it’s a waterfall-style language. Things can be overridden depending on where they’re placed in the document.
* In the example, because purple is mentioned first, the text should be purple. However, since red is below it the text will become red.
	* *This could happen with a file that has 100’s or 1000’s of lines of code. Can be avoided by using the inspect element function on the web browser to see what styles are being used with the different elements.*
		* Right click the page → Inspect
```CSS file:waterfall-example fold
p {
	color: purple;
}

/* Overridden from purple to red */
p {
	color: red;
}
```

[Inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/Inheritance)
* In CSS, this will control what happens when no value is specified for a property on an element

Keeping your code DRY can be very good; learned in the HTML course
* DON’T REPEAT YOURSELF!

[Specificity Calculator - CSS](https://specificity.keegan.st/)
* Helpful to see what will work depending on the usage of elements
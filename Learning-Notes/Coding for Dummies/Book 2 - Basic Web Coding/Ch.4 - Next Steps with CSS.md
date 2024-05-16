---
tags:
  - ReadingNotes
  - WebDev
---
> "Design is not just what it looks like and feels like. Design is how it works.”
> — Steve Jobs

- So far, the CSS rules learned in the previous chapters applied to the entire web page, but now they get more specific.
- Getting more specific in stylings elements such as lists, tables, forms, and part of a webpage.
- Then, learning about how professional web developers use CSS and the box model to control, down to the pixel, the positioning of elements on the page.

## Styling (More) Elements on your Page
- Going to learn common ways to style lists and tables
### Styling Lists
- Two most common tasks when styling a list include the following…
    1. **Changing the marker used to create a list**
        - Unordered Lists: Using a solid disc, empty circle, or square bullet point
        - Ordered Lists: Using roman numerals or case letters
    2. **Specifying an image to use as the bullet point**
        - Instead of using the mentioned above methods, you can use small images as a bullet point instead.

**REMEMBER**: CSS selectors using properties and rules modify HTML elements by the same name.
CSS properties and values apply to a CSS selector and modify an HTML element.
- Changing the marker in an unordered list using `list-style-type` .
- Changing the marker in an ordered list to uppercase Roman numerals using `list-style-type` .
- Setting a custom marker to an icon using `list-style-image` .

### Common CSS Properties and Values for Styling Lists

|                       Property Name |                                         Possible Values |                                                                                                                                                                                                                    Description |
|:------------------------------------|:--------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `list-style-type`  (unordered list) |                                 disc circle square none |                                                                                                                  Sets the markers used to create list items in an unordered list to disc (●), circle (ο), square (■), or none. |
|   `list-style-type`  (ordered list) | decimal upper-roman lower-roman upper-alpha lower-alpha | Sets the markers used to create list items in an ordered list to decimal (1, 2, 3), uppercase Roman numerals (I, II, III), lowercase Roman numerals (i, ii, iii), uppercase letters (A, B, C), or lowercase letters (a, b, c). |
|                  `list-style-image` |                                              url("URL") |                                                                                                                 When URL is replaced with the image link, the property sets an image as the marker used to create a list item. |

**TIP**: If the custom image for your marker is larger than the text, your text may not align vertically with the marker.
- A fix for this is by using `font-size` , `margin` , and `list-style-type: none`

### Designing tables
- By default, the width of these tables expands to fit content inside the table, content in individual cells is left-aligned, and no borders are displayed.
- Three common tasks CSS can perform for tables include the following…
    1. Setting the width of a table, table row, or individual table cell with the `width` property.
    2. Aligning text within the table with the `text-align`  property.
    3. Displaying borders within the table with the `border`  property

### Common CSS Properties and Values for Styling Tables
| Property Name |           Possible Values |                                                                                                                                                                                                                                                               Description |
|:--------------|:--------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       `width` |            pixels (#px) % |                                                                                                                                                         Width of the table measured either in pixels on-screen or as a percentage of the browser window or container tag. |
|  `text-align` | left right center justify |                                                                                                    Position of text relative to the table according to the value of the attribute. For example, `text-align="center"` positions the text in the center of the table cell. |
|      `border` |         width style color | Defines three properties in one `border-width`, `border-style`, and `border-color`. The values must be specified in this order: Width (pixel), style (none, dotted, dashed, solid), and color (name, hexadecimal code, RBG value). For example, `border: 1px solid red;`. |

**TIP**: The HTML tag `<caption>` and the CSS property `border-collapse` further style the preceding table.

## Selecting Elements to Style
- Depending on the content, you may want to center only the text in the header row, but left-align text in subsequent rows. There's two ways to do this…
    1. Styling specific HTML elements based on position to other elements.
    2. Naming HTML elements and styling elements only by name.
- When styling specific elements, it is helpful to visualize the HTML code as a family tree with parents, children, and siblings.
    - The HTML tree is called the DOM (Document Object Model) — *will learn more about this in JavaScript!*

### Child Selector
- From the example on page 108 (*fig 4-4 to 4-6*), a child selector is created by first listing the parent selector, then a greater-than sign (>), and finally the child selector.
```CSS fold
p > a {
	color: red;
	text-decoration: none;
}
```

### Descendant Selector
A descendant selector is created by first listing the parent selector, a space, and finally the descendant selector you want to target.
- From the example in fig 4-8 or (*page 111*)
```CSS fold
ul a {
	color: blue;
	text-decoration: line-through;
}
```

### Naming HTML Elements
- You name your code by using either the `id` or `class` attribute and then style your code by referring to the `id` or `class` selector.
    - The `\`i`d\` attribute can name any HTML element, and it is always placed in the opening HTML tag.
        - After you define the attribute in the HTML file, you refer to the HTML element in your CSS by writing a hashtag (#) followed by the attribute value.
    - Use the class attribute to style multiple elements on your web page.
        - After you define the attribute in the HTML file, you refer to the HTML element by writing a period (.) followed by the attribute value.
```CSS fold
/* ID Selector Class */
#jurassic {
	color: red;
	background-color: yellow;
}

/* Class Selector Class */
.tech {
	color: red;
	text-decoration: none;
}
```

## Aligning and Laying Out Your Elements
- CSS not only allows control over the formatting of HTML elements, it also allows control over the placement of these elements on the page, known as *page layout*.
- HTML table page layouts were tedious to create and required that developers write a great deal of code to ensure consistency across browsers. Now, we have CSS to handle how things look.
### Organizing data on the page
- Review figure 4-9 on page 114 and view some of the basic ways we can structure the page and the content on it.

**TIP**: Always ask yourself how your intended layout will appear on desktop, tablet, and mobile devices.
  - Examples of websites with horizontal layouts
      1. [MDN Documents](https://developer.mozilla.org/en-US/docs/Learn/HTML) on HTML/CSS/JavaScript
  - Examples of websites with vertical navigation layouts
      1. [eBay.com](https://www.ebay.com/)
**TIP**: Don’t spend too much time worrying about which layout to pick. You can always pick one, observe whether the visitors can navigate your website quickly and easily and change the layout if necessary.
### Shaping the div
- These elements are grouped together using rectangular containers created with an opening and closing `div` tag, and all of the layouts can be created with these `div` tags.
    - The `div` tag doesn't render anything on the screen, but serves as a container for content of any type.
- In the following example, as shown in Figure 4-13 (*page 116*), HTML code is used to create two containers using  tags, the id attribute names each div, and CSS sizes and colors the div.

### Understanding the box model
- CSS creates a box around each and every single element on the page, even text.
- These boxes may not always be visible, but comprise four parts…
    1. *Content*: HTML tag that is rendered inside of the browser.
    2. *Padding*: Optional spacing between content and the border.
    3. *Border*: Marks the edge of the padding and varies in width and visibility.
    4. *Margin*: Transparent optional spacing surrounding the border.
- The padding, border, and margin are CSS properties, and the value is usually expressed in pixels, em, or rem.
```CSS fold
div {
	height: 100px;
	width: 100px;
	border: 1px solid black;
	padding: 10px;
	margin: 10px;
}
```
### Positioning the boxes
- After understanding how to group elements using HTML and how CSS views elements, the final piece is to position the elements on a page.

### Select CSS Properties and Values for Page Layouts
| Property Name |      Possible Values |                                                                                                                      Description |
|:--------------|:---------------------|:---------------------------------------------------------------------------------------------------------------------------------|
|     \`float\` |      left right none | Sends an element to the `left` or `right` of the container it is in. The none value specifies that the element should not float. |
|     \`clear\` | left right both none |                                                       Specifies on which side of an element not to have other floating elements. |

- If the `width` of an element is specified, the \`float\` property allows elements that would normally appear on separate lines to appear next to each other, such as navigation toolbars and a main content window.
- Breaking down the HTML/CSS example from figure 4-16 (*page 120 - 122*)
    - The CSS is embedded between the opening and closing `<style>` tags, and the HTML is between the opening and closing `<body>` tags.
    - Between the opening and closing `<body>` tags, using `<div>` tags, the page is divided into four parts with header, navigation bar, content, and footer.
    - The navigation menu is created with an unordered list, which is left-aligned, with no marker.
    - CSS styles size and color and align each `<div>` tag.
    - CSS properties, `float` and `clear`, are used to place the left navigation layout to the left, and the footer below the other elements.

---
tags:
  - learning-notes
  - code-for-dummies-book-2
  - CSS
obsidianUIMode: preview
---
> “Create your own style . . . let it be unique for yourself and yet identifiable
> for others.” — Anna Wintour

Websites you browse today are different, and they have a more polished look and feel.
  - Twenty years ago you might have browsed the Internet with a dial-up modem, but today you likely use a very fast Internet connection and a more powerful computer.
First, you’ll learn basic CSS structure and then the CSS rules to style your content.
Finally, you’ll see how to apply these rules to your websites.

## What Does CSS Do?
CSS styles HTML elements with greater control than HTML does.
- An example of this is going to Facebook and removing the styling that currently exists. Without it, everything would be aligned left and the images would be bigger than they should be.

CSS can style almost any HTML tag that creates a visible element on the page, such as…
- Text size, color, style, typeface, and alignment
- Link color and style
- Image size and alignment
- List bullet style and indentation
- Table size, shading, borders, and alignment

**REMEMBER**: CSS Styles and positions the HTML elements that appear on a webpage. However, the use of `<head>`  isn't visible and styled using CSS.

There are 3 reasons as to why creating a separate language to handle styling was considered. That's because…
1. **History**: CSS emerged four years after HTML as an experimental solution to gauge interest in additional styling effects. Initially uncertain of its utility, CSS gained limited support from major browsers. Consequently, it was developed independently from HTML, enabling developers to construct websites solely with HTML.
2. **Code Management**: CSS initially overlapped with HTML, causing cluttered code. For example, setting font types in HTML required repetitive attributes for each paragraph, complicating styling tasks. CSS simplified this by universalizing style application after a single specification. This separation eased coding and content processing by search engines.
3. **Accessibility**: Web browsers aren’t the only place where web pages are used. In addition to traditional web browsers, web pages may also be used by screen readers for the blind, text-to-speech applications, smart speakers, and much more. Different kinds of devices require different types of styling. By separating style (CSS) from structure (HTML) web pages become much more flexible and the content of the web page can be used more easily by more people.

## CSS Structure
CSS follows a certain set of rules that websites will be displayed in the same way no matter the browser/computer used.
**TIP**: Every web browser will interpret CSS rules to style your HTML, though you should be sure to download, install, and use the latest version of Chrome, Safari, Firefox, Edge, or Opera for the best experience.

Basic syntax of CSS
```CSS fold
selector {
	property: value;
}
```

- **Selector**: The HTML element you want to style
- **Property**: The feature of the HTML element you want to style. For example, font typeface, image height, or color
- **Value**: The options for the property that the CSS rule sets.
    - Example: If `color` were the property, the value would be \`red\`

The next example shows modifying a specific HTML element
```CSS fold
h1 {
	font-family: cursive;
}
```

The CSS selector targets and styles the HTML element with the same name (in this case, `h1` tags).

**REMEMBER**: CSS uses a colon instead of the equals sign (=) to set values of CSS properties
### My property has value
The combination of property and value together is called a *declaration*,
and a group of properties and values is called a *declaration block.*
```CSS fold
h1 {
	font-size: 15px;
	color: blue;
}
```

In the example above, CSS styles the `h1` element, changing the `font-size `property to 15px, and the `color` property to blue.

### Hacking the CSS on your favorite website(s)
Follow the steps to change some CSS rules in the wild.
1. Using Chrome/Firefox, navigate to your favorite news site that has many headlines.
2. Place the mouse pointer over a headline and right click. From the menu that appears, select inspect.
3. Click the Styles tab on the right side of the window that opened to see the CSS rules being applied to the HTML elements
4. Change the color of the headline chosen using CSS.
## Common CSS Tasks and Selectors
Although CSS includes over 150 properties and many values for each property, on modern websites, a handful of CSS properties and values do the majority of the work.
Other common tasks performed with CSS include..
- Changing font size, style, font family, and decoration
- Customizing links including color, background color, and link state
- Adding background images and formatting foreground images.

### Font gymnastics: Size, color, style, family, and decoration
CSS lets you control text in many HTML element.
### Common CSS Properties and Values for Styling Text
| Property Name   | Possible Values             | Description                                                                                                                                                                                                                                                 |
| :-------------- | :-------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| font-size       | pixels (#px) % em (#em)     | Specifies the size of text measured either in pixels as a percentage of the containing element’s font size or with an `em` value, which is calculated by desired pixel value divided by containing element font size in pixels. Example:` font-size: 16px`; |
| color           | name hex code rgb value     | Changes the color of the text specified using names (color: blue;), hexadecimal code (color: `#0000FF`;), or RGB (red, green, and blue) value (color: rgb(0,0,255);).                                                                                       |
| font-style      | normal italic               | Sets font to appear in italics (or not).                                                                                                                                                                                                                    |
| font-weight     | normal bold                 | Sets font to appear as bold (or not).                                                                                                                                                                                                                       |
| font-family     | font name                   | Sets the font typeface. Example: \`font-family: serif;\`                                                                                                                                                                                                    |
| text-decoration | none underline line-through | Sets font to have an underline or strikethrough (or not).                                                                                                                                                                                                   |
### Setting the font-size
You can set the size of the font you’re using with CSS’s font-size property.
There's a few options for setting the font size, the most common one is pixels.
- One disadvantage of using pixels to size your font occurs when users who prefer a large font size for readability have changed their browser settings to a default font size value that’s larger than the one you specify on your site. You can also use percentages or rems.
```CSS fold
p {
	font-size: 16px; /* Option #1 */
	font-size: 150%; /* Option #2 */
	font-size: 2rem; /* Option #3 - Reccommended */
}
```

### Setting the color
The color property can set the color in one of three ways.
1. **Name**: CSS supports referencing 147 colors by name, including common ones like black, blue, and red, as well as unusual ones like burlywood, lemon chiffon, and thistle. Notably, a shade called `rebeccapurple` was added to honor Rebecca Meyer, daughter of CSS standards author Eric Meyer, who passed away from brain cancer at age six in 2014. All major browsers now support this color.
2. **Hex Code**: Colors can be defined using red, green, and blue components. With hexadecimal code, over 16 million colors can be referenced. For instance, in "#FF0000", "FF" represents red, "00" represents green, and another "00" represents blue.
3. **RGB Value**: RGB values, like hex codes, specify the red, green, and blue components for over 16 million colors, providing a decimal equivalent to
hexadecimal values.

**TIP**: There's no need to try and remember hex codes or RGB values. Instead, you can use an online color picker.
Example of all three ways to change color
```CSS fold
p {
	color: red;
}

h1 {
	color: #FF0000;
}

li {
	color: rgb(255, 0, 0);
}
```

### Setting to font-style and font-weight
The `font-style` property can set text to italics
The `font-weight` property can set text to bold
- Each property has a default of normal if not used.
```CSS fold
p {
	font-style: italics;
	font-weight: bold;
}
```

### Setting the font-family
The font-family property sets the typeface used for certain text.
It's usually set equal to one or more fonts that are separated by commas.
- Depending on the visitor's computer, the font may change or be different from someone elses.

There's two types of values for font-family..
1. Font name: Specific font names such as Times New Roman, Arial, and Courier.
2. Generic Font Family: Modern browsers usually define one installed font for each generic font family. These five generic font families include..
    - **Serif** (Times New Roman, Palantino)
    - **Sans-Serif** (Helvetica, Verdana)
    - **Monospace** (Courier, Andale Mono)
    - **Cursive** (Comic Sans, Florence)
    - **Fantasy** (Impact, Oldtown)

It's best to define two or three specific fonts followed by a generic font family as a fallback in case the fonts you specify aren’t installed, such as…
```CSS fold
p {
	font-family: "Times New Roman", Times, serif;
}
```

### Setting the text decoration
The text-decoration property sets any font underlining or strikethrough.
```CSS fold
h1 {
	text-decoration: underline;
}

p {
	text-decoration: line-through;
}
```

### Customizing links
In general, browsers display links as blue underlined text.
Some websites don’t underline links; others retain the underlining but style links in colors other than blue; and so on.

**REMEMBER**: The anchor element is used to create links. The text between the open and closing tag is the link description. Lastly, the URL set in the `href` attribute is the address that the browser will visit when clicked.

The anchor tag has 4 states…
1. `link` : A link that a user hasn't clicked or visited yet
2. `visited` : A link that a user has clicked or visited
3. `hover` : A link that the user hovers with the mouse cursor over the link without cliking.
4. `active` : A link the user has begun to click on but hasn't yet released the mouse button.


### Common CSS Properties and Values for Styling Links
| **Property Name** |     **Possible Values** | **Description**                                                                                                             |
| :---------------- | :---------------------- | :-------------------------------------------------------------------------------------------------------------------------- |
|             color | name hex code rgb value | Link color specified using names (color: blue;), hexadecimal code (color: `#0000FF`;), or RGB value (color: rgb(0,0,255);). |
|   text-decoration |          none underline | Sets link to have an underline (or not).                                                                                    |

```CSS fold
a:link {
	color: rgb(6,69,173);
	text-decoration: none;
}

a:visited {
	color: rgb(11,0,128)
}

a:hover {
	text-decoration: underline
}

a:active {
	color: rgb(250,167,0)
}
```
The various link states are known as pseudo-class selectors.
- These add a keyword to CSS selectors that allow you to style a special state of the selected element.


## Adding background images and styling foreground images
You can use CSS to add background images behind HTML elements. Most commonly, the background-image property is used to add background images to individual HTML elements such as `div`, `table`, and `p`, or (when applied to the `body` element) to entire web pages.

### Setting the background-image
The `background-image` property can set the background image for the entire web page or a specific element.
```CSS fold
body {
	background-image: url("http://upload.wikimedia.org/wikipedia/commons/e/e5/Chrysler_Building_Midtown_Manhattan_New_York_City_1932.jpg");
}
```

### CSS Properties and Values for Background Images
|     **Property Name** |                       **Possible Values** |                                                                                                                                                                                                                                                                                                                                           **Description** |
|:----------------------|:------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      background-image |                                url("URL") |                                                                                                                                                                                                                                                                                           Adds a background image from the image link specified at `URL`. |
|       background-size | auto contain cover width, height (#px, %) |      Sets background size according to the value: `auto` (default value) displays the image as originally sized. `contain` scales the image’s width and height so that it fits inside element. `cover` scales the image so element background isn’t visible. Background size can also be set by specifying width and height in pixels or as a percentage. |
|   background-position |                keywords position (#px, %) | Positions the background in element using keywords or exact position. Keywords comprise horizontal keywords (`left, right, center`) and vertical keywords (`top, center, and bottom`). The placement of the background can also be exactly defined using pixels or a percentage to describe the horizontal and vertical position relative to the element. |
|     background-repeat |        repeat repeat-x repeat-y no-repeat |                                                                                                                                                                   Sets the background image to *tile*, or repeat, as follows.. horizontally (`repeat-x`) vertically (`repeat-y`) horizontally and vertically (`repeat`) don’t repeat at all (`no-repeat`) |
| background-attachment |                              scroll fixed |                                                                                                                                                                                                                                                                Sets the background to scroll with other content (`scroll`), or to remain fixed (`fixed`). |


### Setting the background-size
By specifying exact dimensions using pixels or percentages, the `background-size` property can scale background images to be smaller or larger, as needed.
The background-size property has 3 dimensions that are commonly used..
1. `auto`: This value maintains the original dimensions of an image.
2. `cover`: This value scales an image so all dimensions are greater than or equal to the size of the container or HTML element.
3. `contain`: This value scales an image so all dimensions are less than or equal to the size of the container or HTML element.
    - *Refer to figure 3-7 to see an example of all 3*

### Setting the background-position
The `background-position` property sets the initial position of the background image.
You change the default position by specifying a pair of keywords
or position values, as follows…
1. **Keywords**: The first keyword (`left, center, right`) represents the horizontal position, and the second keyword (`top, center, bottom`) represents the vertical position.
2. **Position**: The first position value represents the horizontal position, and the second value represents the vertical. Each value is defined using pixels or percentages, representing the distance from the top-left of the browser or the specified element.
    - For example, `background-position: center;` center is equal to `background-position: 50% 50%;`.

### Setting the background-repeat
The background-repeat property sets the direction the background will tile as follows..
1. `repeat`: This value (the default) repeats the background image both horizontally and vertically.
2. `repeat-x`: This value repeats the background image only horizontally.
3. `repeat-y`: This repeats the background image only vertically.
4. `no-repeat`: This value prevents the background from repeating at all.

### Setting the background-attachment
The `background-attachment` property sets the background image to move (*or not*) when the user scrolls through content on the page.
1. `scroll`: The background image moves when the user scrolls.
2. `fixed`: The background image doesn’t move when the user scrolls.
```CSS fold
body {
	background-image: "URLHERE.COM/IMG"
	background-size: cover;
	background-position: center center;
	background-repeat: no-repeat;
	background-attachment: fixed;
}
```

## Getting Stylish
Although you aren’t likely to remember every property and value, with practice, the property and value names will come to you naturally.
The next step is to actually incorporate CSS into your web page and try your hand at styling HTML elements.

### Adding CSS your your HTML
There are three ways to apply CSS to a website to style HTML..
1. **Inline CSS**: Inline CSS refers to the practice of embedding CSS code directly within the HTML elements of a web page, using the "style" attribute. This allows for styling individual elements without the need for a separate CSS file. Inline CSS takes precedence over external and internal CSS styles, making it useful for overriding styles on specific elements. However, it can make the HTML code less readable and harder to maintain, especially in large projects.
2. **Embedded CSS**: Embedded CSS, *also known as internal CSS*, involves placing CSS code directly within the HTML document, typically within the tags in the section. It allows for styling multiple elements or classes within the same HTML file, offering more organization and maintainability compared to inline CSS.
3. Separate Style Sheets⭐: Separate style sheets, also known as external CSS, involve storing CSS code in separate `.cs`s files linked to HTML documents using tags in the section. They offer organized and maintainable styling across multiple pages, promoting separation of concerns and faster loading times through browser caching.
```CSS fold
h1 {
	color: red;
}
```

```HTML fold
<head>
	<link href="styles.css" type="text/css" rel="stylesheet">
</head>
```
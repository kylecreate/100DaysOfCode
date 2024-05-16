---
tags:
  - ReadingNotes
  - WebDev
---
>“A chain is no stronger than its weakest link, and life is after all a chain.” – William James

HTML, or *Hypertext Markup Language*, is used in every single web page you browse on the Internet. It’s the very first language to learn when learning about frontend web development.

Ch.1 of Book 2 will cover the basics and structure of using HTML to make it appear in the browser. Then, you can create your own and first HTML page using what was learned in the chapter.

## What Does HTML Do?
* HTML is the language used to give structure to a website and was originally designed for creating documents like letters, books, or scientific papers.
	* Now, these examples could be made using something like Microsoft Word/WordPad, Notepad, or Apple Pages.
* Markup language documents, like HTML documents, are just plain text files.
	* Documents created with a word processor aren’t possible to see using a browser as they include unseen formatting commands.

## Understanding HTML Structure
* HTML follows a few rules to ensure that a website always displays in the same way no matter which browser or computer is used.
	* You can use any browser to display your HTML file, it’s recommended that you use Chrome or Firefox since they’re both updated frequently, generally fast, and support the rendering of the widest variety of HTML tags.

### Identifying elements
* Basic building blocks of HTML are called elements which give meaning and structure to web pages. The browser will see them if the following conditions exist.
	1. The element has a name that’s a letter, word, or phrase with meaning.
		* IE: `h1`
	2. The element’s name is enclosed with a left and right angle bracket, which is why it’s called a tag.
		* IE: `<h1>`
	3. An opening tag is usually followed by a closing tag. Although, some tags don’t need a closing tag, which will be covered later on.
		* IE: `<h1> </h1>`
* When all the conditions are met, web browsers will display the text between the opening and closing tags using some predefined style, or the browser will take some other action based on the content of the element.
```HTML file:elements-example fold
<h1>This is a big heading with all 3 conditions</h1> ✔
h1 this is text without the < and > sign surronding the tag /h1 ✘
<rockstar>This is text with a tag that has no meaning to the browser.</rockstar> ✘
This is regular text ✘
```

* The browser applies a header effect to the `h1` tag because…
	1. that tag/element exists within HTML
	2. The element is surrounded by the opening and closing angle brackets
	3. The opening tag (`<h1>`) is followed by the closing tag (`</h1>`)
* The browser will never display the actual text of a tag in a properly formatted HTML element.
* The last 3 lines display as plain text because they’re each missing one or more of the conditions mentioned.
	* Line 2: There’s no opening or closing brackets for the h1 tag
	* Line 3: The rockstar tag doesn’t exist
	* Line 4: The text is just plain text
* Over 100 elements exist, there’s no need to memorize them all.

### Featuring your best attribute
* Attributes provide additional ways to modify the behavior of an element or specify additional information.
```HTML file:attribute-example fold
<h1 title="United States of America">USA</h1>
<h1 hidden>New York City</h1>
<h1 title="United States of America" lang="en">USA</h1>
```

* The *title* attribute provides a tooltip of information about the element when the mouse hovers over the text displaying “USA”.
* The *hidden* attribute indicates that the element is not relevant, so the browser doesn’t render it.
	* This is often used to hide form fields from users so they can’t edit them.
* It’s possible to use more than one attribute at a time in a single HTML tag.
* The `lang` attribute is set to `"en"` to specify that the content of the element is in the English language.
* Keep the following rules in mind when using attributes…
	1. Always include the attribute in the opening HTML tag
	2. Multiple attributes can modify a single element.
	3. If an attribute has a value, then use the equal sign and enclose that value in quote marks.

### Standing head, title, and body above the rest
* HTML files are structured in a specific way so browsers can correctly interpret the file’s information.
* Every file has 5 elements, four of which won’t appear on the page
	1. `<!DOCTYPE html>` - This should appear first in the HTML file and only once. This will let the browser know which version of HTML you’re using.
	2. `<html>` - This represents the *root* or the beginning of an HTML document. This is followed before the opening head tag and after the closing head tag.
	3. `<head>` - This contains other elements that specify general information about the page, including the title of the webpage.
	4. `<title>` - This defines the title of the webpage in the browser’s title tab or page tab.
	5. `<body>` - This contains the main content of an HTML document such as text, images, and other content listed.
```HTML file:HTML-structure fold
<!DOCTYPE html>
<html>
<head>
	<title>Page Title Here</title>
</head>
<body>
	<h1>This is a title</h1>
	<p>This is a paragraph of text</p>
</body>
</html>
```

===TIP===: Using spaces to indent and separate your tags is highly recommended. It helps you and others read and understand your code.

#### History of HTML
* HTML was created by [[Sir Tim Berners-Lee]] in 1990 while working at [[CERN]]. Originally designed as a simple markup language for sharing research documents among scientists, it has since evolved into the standard language for creating web pages on the World Wide Web, undergoing various versions and updates over the years to accommodate the growing complexity and demands of web development.

## Getting Familiar with Common HTML Tasks and Elements
* The browser can interpret over a hundred HTML elements, but most websites use just a few elements to do most of the work within the browser.
* Using an example from the NY Times *(fig 1-5, page 53)*, there’s 4 elements on the page that are seen.
	1. <u>Headlines</u>: Headlines are displayed in bold and have a larger font size than the surrounding text.
	2. <u>Paragraphs</u>: Each story is organized into paragraphs with whitespace dividing each paragraph.
	3. <u>Hyperlinks</u>: The site’s homepage and article pages have links to other stores, and links to share the story on social media like Facebook and Twitter.
	4. <u>Images</u>: Writers place images throughout the story, but also look for site images like icons and logos.

### Writing headlines
* Using headlines can describe a section of your page, HTML has six levels of these.
	* `h1` is used for the most important headings and **should only be used once!**
	* `h2` is used for subheadings
	* `h3 to h6` are used for less important headings
		* Headings should always have a closing tag!

### Organizing text in paragraphs
* To display text in paragraphs, you can use the `p` element. They start with an opening and end with a closing tag.
```HTML file:Paragraph-Example fold
<p>Armstrong: Okay. I'm going to step off the LM now.</p>
<p>Armstrong: That's one small step for man; one giant leap for mankind.</p>
<p>Yes, the surface is fine and powdery. I can kick it up loosely
with my toe. It does adhere in fine layers, like powdered
charcoal, to the sole and sides of my boots.</p>
```
* *View fig 1-7 on page 55 for an example of this*

### Linking to your (heart’s) content
* Hyperlinks are one of HTML’s most valuable features. You can allow readers/users to access the sources you’re linking with one click. They have two parts.
	1. <u>Link Destinations</u>: The web page the browser visits once the link is clicked.
	2. <u>Link Description</u>: The words used to describe the link.
```HTML file:Hyperlink-example fold
<a href="http://www.amazon.com">Amazon Link</a>
<a href="http://www.google.com">Google Link</a>
<a href="http://www.youtube.com">YouTube Link</a>
```
* *View fig 1-8 on page 56 for an example of this*
* When rendering hyperlinks, the browser, by default, will underline the link and color the link blue. You can change these colors and behaviors with CSS (*will be talked about later on*).

### Adding images
* Images spruce up otherwise plain HTML text pages, you can include your own or someone else’s – if given permission.
	* Use a site like [Imgur](https://imgur.com/) to upload photos if needed
```HTML file:Adding-Images fold
<img src="http://upload.wikimedia.org/wikipedia/commons/5/55/Grace_Hopper.jpg"/>
<img src="http://upload.wikimedia.org/wikipedia/commons/b/bd/Bill_Gates.jpg"/>
```
* *View fig 1-9 on page 57 for an example of this*
* ===TIP===: The image tag is self-closing, which means a separate `</img>` closing image tag is not used.

## Styling Me Pretty
* HTML has basic capabilities to style content, and later chapters will show you how to use CSS to style and position your content down to the last pixel.

### Highlighting with bold, italics, underline, and strikethrough
* HTML allows for basic text styling using the following elements…
	1. `strong` marks important text, which will be shown as bold
	2. `em` makes emphasized text, which will be shown as italicized
	3. `u` marks text as underlined
	4. `del` marks deleted text, which will display as a strikethrough
```HTML file:Styling-HTML fold
Grace Hopper, <strong> a US Navy rear admiral </strong>, popularized the term "debugging."
Bill Gates co-founded a company called <em>Microsoft</em>.
Stuart Russell and Peter Norvig wrote a book called <u>Artificial Intelligence: A Modern Approach</u>.
Mark Zuckerberg created a website called <del>Nosebook</del> Facebook.
Steve Jobs co-founded a company called <del><em>Peach</em></del> <em>Apple</em>
```
* *View fig 1-10 on page 59 for an example of this*

### Raising and lowering text with super and subscript
* Reference works like [Wikipedia](https://www.wikipedia.org/) and technical papers often use superscript for footnotes and subscript for chemical names.
	1. `sup` for text marked as superscript
		* When using the superscript element to mark footnotes, use an `<a>` anchor tag to link directly to the footnote so the reader can view the footnote easily.
	2. `sub` for text marked as subscript
```HTML file:Sizing-text fold
<p>The University of Pennsylvania announced to the public the first electronic general-purpose computer, named ENIAC, on February 14, 1946.<sup>1</sup></p>
<p>The Centers for Disease Control and Prevention recommends drinking several glasses of H<sub>2</sub>0 per day.</p>
```
* *View fig 1-11 on page 59 for an example of this*

## Building Your First Website Using HTML
* *Refer to the instructions on page 61 to build your very first website*
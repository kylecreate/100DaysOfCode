---
tags:
  - WebDev
---
## What is CSS?
CSS stands for <u>Cascading Style Sheets</u> which is a stylesheet language used to describe the presentation of a document written in HTML or XML. This language describes how elements should be rendered on a screen or other media for users to see.
* We will be working with CSS using HTML
* CSS is among the core languages of the **open web** and is standardized across Web browsers.
* [CSS - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS)

HTML is considered the foundation and structure of a website.
* Like a new building or a new house being built
HTML also provides meaning and we can convey that meaning with structure.
* The structure of a home, the wood and foundation of a home
HTML first… then CSS
* You build the house/building first, and then you can decorate it.
CSS describes how elements should appear
* Which is what makes the house/building look better once its finished
### Tools Needed while using this course (suggested)
1. Google Chrome
2. Using an IDE (Integrated Developer Environment) - VSCode
	1. Add the Live Server extension from Ritwick Dey

*Goes over creating a folder for the lessons being used for the course*

There are 3 different ways we can apply CSS to our document…
1. [External Style Sheet - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link)
	* Best way and commonly used for modern websites
	* This uses the `<link>` element in the head of an HTML page
	* Specifies the relationship between the current document and an external resources, such as this.
2. [Internal Style Sheet - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style)
	* Not used at all, avoid using this if you can
	* Depending on if this is placed above or below the external sheet, it could be over-written or not.
	* It does contain CSS, but in the head of the document using the `<style></style>` tag.
3. [Inline Style Sheet - MDN](https://developer.mozilla.org/en-US/docs/Glossary/Inline-level_content)
	* Not used at all, avoid using this if you can
	* Similar to the internal style sheet but used inside of the body tag with each HTML element.
	* Creates more of a mess than using the External Style Sheet (mentioned above).

[Anatomy of a CSS Ruleset - MDN](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics#anatomy_of_a_css_ruleset)
```CSS file:CSS-rule-set-example fold
p {
	color: red;
}
```
1. The red `p` in the example is considered the Selector
	* The selector is an HTML name at the start of the ruleset which is to be defined later on in the line.
2. The  yellow `color` text in the example is considered the Property
	* The property value has many different options to choose from the style something on the webpage.
3. The pink `red` text in the example is the Property Value
	* This property chooses one of the many possible appearances given for a property
4. So, what does this rule set do for the text?
	* The selector being targeted is the Paragraph element and we want to change the text color to red.

If you do put in color using UK English, it won’t be wrong but it just won’t work since CSS is Americanized.
* Example: Using `colour` instead of `color`

To make sure our CSS file has any errors, you can use the [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)
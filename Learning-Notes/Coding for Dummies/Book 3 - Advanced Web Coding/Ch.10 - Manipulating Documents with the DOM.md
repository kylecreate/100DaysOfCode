---
tags:
  - ReadingNotes
  - WebDev
---
> *"No object is mysterious. The mystery is your eye"*
> -- Elisabeth Bowen

Understanding the DOM (Document Object Model) is key to being able to manipulate text or HTML on a web page. You can create animations, update data without needing to refresh the page, move objects around in a browser, and more.

# <u>Understanding the DOM</u>
The <u>Document Object Model</u> (DOM) is the interface for JavaScript to talk to and work with HTML documents inside of browser windows. It can be visualized as an inverted tree with each part branching off to a certain part.
A DOM tree is made up of individual components, called *nodes*.
* The main node (from where everything comes from) is called the *document node*.
* The node under the document node is the *root element node*.
* The *root node* is created by the `<html>` element
	* After this node, every element/attribute/content in the document is represented by a node in the tree that comes from another node in the tree.
**Document Node**: The entire HTML document is represented in this node.
**Element Nodes**: The HTML elements.
**Attribute Nodes**: The attributes associated with elements.
**Text Nodes**: The text content of elements
**Comment Nodes**: The HTML comments in a document

[[DOM Model - Ex.1.canvas|DOM Model - Ex.1]]

# <u>Understanding Node Relationships</u>
DOM trees resemble family trees in the hierarchical relationship between nodes. To describe relationships between nodes in a tree, take their names from familial relationships.
* Every node (except for the root node) has one *parent*.
* Each node may have any number of *children*.
* Nodes with the same parent are considered *siblings*.
The DOM allows you to access distinct elements in a node list using an index number when you have elements that are the same type.
* IE: Refer to the first paragraph element as `p[0]` and the second element as `p[1]`.

**<span style="color: yellow">WARNING</span>**: Although a node list may look like an array, it’s not. You can loop through the contents of a node list, but you can’t use an array method on a node lists.

In the example below, the 3 `<p>` elements are all children of the `<div>` element and because they have the same parent, they're considered siblings.
* The comments are also considered children of the `<section>` element as well. The last comment before the closing `<section>` tag is considered the *last child* of the section.
```HTML file:child-sibiling-ex-1 fold
<section> <!-- proud parent of 3 p elements, child of body -->
	<p>First</p>
	<!-- 1st child of section element, sibling of 2 p elements -->
	<p>Second</p>
	<!-- 2nd p child of section element, sibling of 2 p elements -->
	<p>Third</p>
	<!-- 3rd p child of section element, sibling of 2 p elements -->
</section>
```

Understanding the relationships between document nodes, you can use the DOM tree to find any element you're looking for within a document.
In the next example below, the HTML has a script that outputs all the child nodes of the `<section>` element.
* This shows what the output would look like in a browser.
	* The first child node is a text node in the `<section>`.
```HTML file:HTML/JS-display-nodes fold
<section> <!-- proud parent of 3 p elements, child of body -->
	<p>First</p> <!-- 1st child of section element, sibling of 2 p elements -->
	<p>Second</p> <!-- 2nd p child of section element, sibling of 2 p elements -->
	<p>Third</p> <!-- 3rd p child of section element, sibling of 2 p elements -->
</section>

<h1>Nodes in the section element</h1>

<script>
	let myNodelist = document.body.childNodes[1].childNodes;
	for (let i = 0; i < myNodelist.length; i++) {
		document.write(myNodelist[i] + '<br>');
}
</script>
```

The HTML DOM provides keywords for navigating the different nodes using their positions relative to their siblings/parents.
* `firstChild`: References the first child of a node.
* `lastChild`: References the last child of the node.
* `nextSibling`: References the next node with the same parent node.
* `previousSibling`: References the previous node with the same parent node.

In the next example, the HTML and JavaScript shows how you can use the properties mentioned above to traverse the DOM.
*  All the spacing must be removed between the elements within the `<nav>` element for the `firstChild` and `lastChild` properties to access the correct elements that we want to select and style.
	* The first and last links in the navigation bar are bolded while the rest aren't.
* The method used in the example is almost never used as it's prone to making mistakes and difficult to interpret/use.
```HTML file:firstChild-&-lastChild fold
<head>
	<title>Iguanas Are No Fun</title>
	<script>
		function boldFirstAndLastNav() {
			document.body.childNodes[1].firstChild.style.fontWeight = 'bold';
			document.body.childNodes[1].lastChild.style.fontWeight = 'bold';
		}
	</script>
</head>

<body>
	<nav>
		<a href="home.html">Home</a> |
		<a href="why.html">Why Are Iguanas No Fun?</a> |
		<a href="what.html">What Can Be Done?</a> |
		<a href="contact.html">Contact Us</a>
	</nav>
	<p>Iguanas are no fun to be around. Use the links above to learn more.</p>

	<script>
		boldFirstAndLastNav();
	</script>
</body>
```

# <u>Using the Document Object's Properties and Methods</u>
The `Document` object provides properties and methods for working with HTML documents.

#### Document Object's Properties Table

| Property          | Use                                                                                                                                                                                 |
| :---------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `anchors`         | Gets a list of all anchors (`<a>` elements with name attributes) in the document.                                                                                                   |
| `baseURI`         | Gets the base URI of the document.                                                                                                                                                  |
| `body`            | Gets the `<body>` or `<frameset>` node of the document body.                                                                                                                        |
| `cookie`          | Gets or sets the name/value pairs of cookies in the document.                                                                                                                       |
| `doctype`         | Gets the Document Type Declaration associated with the document.                                                                                                                    |
| `documentElement` | Gets the element that is the root of the document (for example, the `<html>` element of an HTML document).                                                                          |
| `documentMode`    | Gets the mode used by the browser to render the document.                                                                                                                           |
| `documentURI`     | Gets or sets the location of the document.                                                                                                                                          |
| `domain`          | Gets the domain name of the server that loaded the document                                                                                                                         |
| `embeds`          | Gets a list of all `<embed>` elements in the document.                                                                                                                              |
| `forms`           | Gets a collection of all `<form>` elements in the document.                                                                                                                         |
| `head`            | Gets the `<head>` element in the document.                                                                                                                                          |
| `images`          | Gets a list of all `<img>` elements in the document.                                                                                                                                |
| `implementation`  | Gets the `DOMImplementation` object that handles the document.                                                                                                                      |
| `lastModified`    | Gets the date and time the current document was last modified.                                                                                                                      |
| `links`           | Gets a collection of all `<area>` and `<a>` elements in the document that contain the `href` attribute.                                                                             |
| `readyState`      | Gets the loading status of the document. Returns `loading` while the document is loading, `interactive` when it has finished parsing, and `complete` when it has completed loading. |
| `referrer`        | Gets the URL of the page that the current document was linked from.                                                                                                                 |
| `scripts`         | Gets a list of `<scripts>` elements in the document.                                                                                                                                |
| `title`           | Gets or sets the title of the document.                                                                                                                                             |
| `URL`             | Gets the full URL of the document.                                                                                                                                                  |
#### Document Object's Methods

| Method                     | Use                                                                                                          |
| :------------------------- | :----------------------------------------------------------------------------------------------------------- |
| `addEventListener()`       | Assigns an event handler to the document.                                                                    |
| `adoptNode()`              | Adopts a node from an external document.                                                                     |
| `close()`                  | Finishes the output writing stream of the document that was previously opened with `document.open()`.        |
| `createAttribute()`        | Creates an attribute node.                                                                                   |
| `createComment()`          | Creates a comment node.                                                                                      |
| `createDocumentFragment()` | Creates an empty document fragment.                                                                          |
| `createElement()`          | Creates an element node.                                                                                     |
| `createTextNode()`         | Creates a text node.                                                                                         |
| `getElementById()`         | Gets the element that has the specified ID attribute.                                                        |
| `getElementsByClassName()` | Gets all elements with the specified class name.                                                             |
| `getElementsByName()`      | Gets all elements with the specified name.                                                                   |
| `getElementsByTagName()`   | Gets all elements with the specified tag name.                                                               |
| `importNode()`             | Copies and imports a node from an external document.                                                         |
| `normalize()`              | Clears the empty text nodes and joins adjacent nodes.                                                        |
| `open()`                   | Opens a document for writing.                                                                                |
| `querySelector()`          | Gets the first element that matches the specified group of selector(s) in the document.                      |
| `querySelectorAll()`       | Gets a list of all the elements that match the specified selector(s) in the document.                        |
| `removeEventListener()`    | Clears an event handler that had been added using the `.addEventListener()` method from the document.        |
| `renameNode()`             | Renames an existing node.                                                                                    |
| `write()`                  | Writes JavaScript code or HTML expressions to a document.                                                    |
| `writeIn()`                | Writes JavaScript code or HTML expressions to a document and adds a new line character after each statement. |

# <u>Using the Element Object's Properties and Methods</u>
The `Element` object provides properties and methods for working with HTML elements within a document.

#### Element Object's Properties

| Method                   | Use                                                                                                           |
| :----------------------- | :------------------------------------------------------------------------------------------------------------ |
| `accessKey`              | Gets or sets the accesskey attribute of the element.                                                          |
| `attributes`             | Gets a collection of all the element’s attributes registered to the specified node (returns a `NameNodeMap`). |
| `childElementCount`      | Gets the number of child elements in the specified node.                                                      |
| `childNodes`             | Gets a list of the element’s child nodes.                                                                     |
| `children`               | Gets a list of the element’s child elements.                                                                  |
| `classList`              | Gets the class name(s) of the element.                                                                        |
| `className`              | Gets or sets the value of the class attribute of the element                                                  |
| `clientHeight`           | Gets the inner height of an element, including padding                                                        |
| `clientLeft`             | Gets the left border width of the element.                                                                    |
| `clientTop`              | Gets the top border width of the element.                                                                     |
| `clientWidth`            | Gets the width of the element, including padding.                                                             |
| `contentEditable`        | Gets or sets whether the element is editable.                                                                 |
| `dir`                    | Gets or sets the value of the `dir` attribute of the element.                                                 |
| `firstChild`             | Gets the first child node of the element.                                                                     |
| `firstElementChild`      | Gets the first child element of the element.                                                                  |
| `id`                     | Gets or sets the value of the id attribute of the element.                                                    |
| `innerHTML`              | Gets or sets the content of the element.                                                                      |
| `isContentEditable`      | Returns `true` if the content of an element is editable; returns `false` if it is not editable.               |
| `lang`                   | Gets or sets the base language of the elements attribute.                                                     |
| `lastChild`              | Gets the last child node of the element.                                                                      |
| `lastElementChild`       | Gets the last child element of the element.                                                                   |
| `namespaceURI`           | Gets the namespace URI for the first node in the element.                                                     |
| `nextSibling`            | Gets the next node at the same node level.                                                                    |
| `nextElementSibling`     | Gets the next element at the same node level.                                                                 |
| `nodeName`               | Gets the current node’s name.                                                                                 |
| `nodeType`               | Gets the current node’s type.                                                                                 |
| `nodeValue`              | Gets or sets the value of the node.                                                                           |
| `offsetHeight`           | Gets the height of the element, including vertical padding, borders, and scrollbar.                           |
| `offsetWidth`            | Gets the width of the element, including horizontal padding, borders, and scrollbar.                          |
| `offsetLeft`             | Gets the horizontal offset position of the element.                                                           |
| `offsetParent`           | Gets the offset container of the element.                                                                     |
| `offsetTop`              | Gets the vertical offset position of the element.                                                             |
| `ownerDocument`          | Gets the root element (document node) for an element.                                                         |
| `parentNode`             | Gets the parent node of the element.                                                                          |
| `parentElement`          | Gets the parent element node of the element.                                                                  |
| `previousSibling`        | Gets the previous node at the same node tree level.                                                           |
| `previousElementSibling` | Gets the previous element node at the same node tree level.                                                   |
| `scrollHeight`           | Gets the entire height of the element, including padding.                                                     |
| `scrollLeft`             | Gets or sets the number of pixels the element’s content is scrolled horizontally.                             |
| `scrollTop`              | Gets or sets the number of pixels the element’s content is scrolled vertically.                               |
| `scrollWidth`            | Gets the entire width of the element, including padding.                                                      |
| `style`                  | Gets or sets the value of the `style` attribute of the element.                                               |
| `tabIndex`               | Gets or sets the value of the tabindex attribute of the element.                                              |
| `tagName`                | Gets the tag name of the element.                                                                             |
| `textContent`            | Gets or sets the textual content of the node and its descendants.                                             |
| `title`                  | Gets or sets the value of the title attribute of the element.                                                 |
| `length`                 | Gets the number of nodes in the `NodeList`.                                                                   |
#### Element Object's Methods

| Method                      | Use                                                                                   |
| :-------------------------- | :------------------------------------------------------------------------------------ |
| `addEventLIstener()`        | Registers an event handler to the element.                                            |
| `appendChild()`             | Inserts a new child node to the element (as a last child node).                       |
| `blur()`                    | Eliminates focus from the element.                                                    |
| `click()`                   | Replicates a mouse-click on the element.                                              |
| `cloneNode()`               | Clones the element.                                                                   |
| `compareDocumentPosition()` | Compares the document position of two elements.                                       |
| `contains()`                | Yields `true` if the node is a descendant of a node; otherwise, yields `false`.       |
| `focus()`                   | Gives focus to the element.                                                           |
| `getAttribute()`            | Gets the specified attribute value of the element node.                               |
| `getAttributeNode()`        | Gets the specified attribute node.                                                    |
| `getElementsByClassName()`  | Gets a collection of all child elements with the stated class name.                   |
| `getElementsByTagName()`    | Gets a collection of all the child elements with the stated tag name.                 |
| `getFeature()`              | Gets an object that implements the APIs of the stated feature.                        |
| `hasAttribute()`            | Yields `true` if the element has the stated attribute; otherwise, yields `false`.     |
| `hasAttributes()`           | Yields `true` if the element has any attributes; otherwise, yields `false`.           |
| `hasChildNodes()`           | Yields `true` if the element has any child nodes; otherwise, yields `false`.          |
| `insertBefore()`            | Enters a new child node before the stated existing node.                              |
| `isDefaultNamespace()`      | Yields `true` if the stated `namespaceURI` is the default; otherwise, yields `false`. |
| `isEqualNode()`             | Evaluates to see whether two elements are equal.                                      |
| `isSameNode()`              | Evaluates to see whether two elements are the same node.                              |
| `isSupported()`             | Yields `true` if the stated feature is supported on the element.                      |
| `normalize()`               | Joins the specified nodes with their adjacent nodes and removes any empty text nodes. |
| `querySelector()`           | Gets the first child element that matches the stated CSS selector(s) of the element.  |
| `querySelectorAll()`        | Gets all the child elements that match the stated CSS selector(s) of the element.     |
| `removeAttribute()`         | Takes the stated attribute out of the element.                                        |
| `removeAttributeNode()`     | Takes the stated attribute node out of the element and retrieves the removed node.    |
| `removeChild()`             | Removes the stated child node.                                                        |
| `replaceChild()`            | Replaces the specified child node with another.                                       |
| `removeEventListener()`     | Removes the specified event handler.                                                  |
| `setAttribute()`            | Changes or sets the stated attribute to the specified value.                          |
| `setAttributeNode()`        | Changes or sets the stated attribute node.                                            |
| `toString()`                | Changes an element to a string.                                                       |
| `item()`                    | Gets the node at the stated index in the `NodeList`.                                  |

# <u>Working with the Contents of Elements</u>
You can display node types and node values by using the HTML DOM and set property values of elements within the DOM using the `element` object.  The new values are then reflected in real time within the HTML document.
* This was referred to as Web 2.0.

## innerHTML
The most important property of an element that you can modify through the DOM is the `innerHTML` property.
* This property of an element contains everything between the beginning and ending tag of the element.
```HTML file:innerHTML-example fold
<p>This is some text.</p>

<script>
	let getTheInner = document.body.firstChild.innerHTML;
	document.write (getTheInner);
	document.body.firstChild.innerHTML = "Hi there!";
</script>
```

In the example above, to retrieve and display the value of the `innerHTML` property, you can use the first 2 lines in the script tag.
The value that will be output by the write method, is the paragraph tag at above the script tag.
The result of the script code will contain a `<p>` element on the page with the sentence of "Hi there!" while the original HTML document remains unchanged but the webpage reflects the changes because of the JavaScript DOM changes.

## Setting attributes
To set the value of an HTML attribute, you can use the `setAttribute()` method:
* The result of using this statement is the first child element of the body element will be given a new attribute tag named `class` and a value of `myclass`.
```JS file:attribute-example fold
document.body.firstChild.innerHTML.setAttribute("class", "myclass");
```

# <u>Getting Elements by ID, Tag Name, or Class</u>
The `getElementBy` methods provide easy access to any element or groups of elements in a document without relying on parent/child relationships of nodes. The most used include...
* `getElementById`
* `getElementByTagName`
* `getElementByClassName`

## `getElementById`
This is the most widely used method for selecting elements and is essential to modern web development. With this, you're able to find and work with any element simply by referencing a unique `id` attribute.
The example below enables you to keep all your JavaScript together in your document or to modularize your code. By using this method, you can work with any element, anywhere in your document as long as you know the id.
```HTML file:getElementById-example fold
<head>
	<title>Using getElementById</title>

	<script>
		function calculateMPG(miles, gallons) {
		document.getElementById('displayMiles').innerHTML = parseInt(miles);
		document.getElementById('displayGallons').innerHTML = parseInt(gallons);
		document.getElementById('displayMPG').innerHTML = miles / gallons;
	}
	</script>
</head>

<body>
	<p>You drove <span id="displayMiles">___</span> miles.</p>
	<p>You used <span id="displayGallons">___</span> gallons of gas.</p>
	<p>Your MPG is <span id="displayMPG">___</span>.
		<script>
		let milesDriven = prompt('Enter miles driven');
		let gallonsGas = prompt('Enter the gallons of gas used');
		calculateMPG(milesDriven, gallonsGas);
		</script>
	</p>
</body>
```

## `getElementsByTagName`
This method returns a node list of all the elements with the specified tag name.
In the example below, the method is used to select all `h1` elements and change their `innerHTML` properties to sequential numbers.
```HTML file:getElementsByTagName-example fold
<head>
	<title>Using getElementsByTagName</title>
	<script>
		function numberElements(tagName) {
		let getTags = document.getElementsByTagName(tagName);
		for (let i = 0; i < getTags.length; i++) {
			getTags[i].innerHTML = i + 1;
		}
	}
</script>
</head>

<body>
	<h1>this text will go away</h1>
	<h1>this will get overwritten</h1>
	<h1>JavaScript will erase this</h1>
		<script>
			numberElements('h1');
		</script>
</body>
```

## `getElementsByClassName`
This method works similarly as the `getElementsByTagName`, but it uses the values of the class attribute to select elements.
In the example below, we select elements with the class `error` and then change their value of their `innerHTML` property.
* The result of the example in a web browser and entering a wrong answer will tell you that the answer is right/wrong depending on what answer you give.
```HTML file:getElementsByClassName-example fold
<head>
	<title>Using getElementsByClassName</title>
	<script>
	function checkMath(result) {
		let userMath = document.getElementById('answer1').value;
		let errors = document.getElementsByClassName('error');
		if (parseInt(userMath) != parseInt(result)) {
			errors[0].innerHTML = 'That's wrong. You entered ' + userMath + '. The answer is ' + result;
		} else {
			errors[0].innerHTML = 'Correct!';
		}
	}
</script>
</head>

<body>
	<label for="number1">4+1 = </label>
	<input type="text" id="answer1" value=""/>
	<button id="submit" onclick="checkMath(4+1);">Check your math!</button>
	<h1 class="error"></h1>
</body>
```

# <u>Using the Attribute Object's Property</u>
The Attribute object provides properties for working with attributes within the HTML elements.

#### Attribute Object's Properties

| Property    | Use                                                                           |
| :---------- | :---------------------------------------------------------------------------- |
| `isId`      | Yields `true` if the attribute is an id; otherwise, yields `false`.           |
| `name`      | Gets the name of the attribute.                                               |
| `value`     | Gets or sets the value of the attribute.                                      |
| `specified` | Yields `true` if the attribute has been specified; otherwise, yields `false`. |
# <u>Creating and Appending Elements</u>
To create a new element in an HTML document using the DOM, use `document.createElement()` method. When used, a new beginning and end tag of the type specified will be created.
In the example below, you can use this method to dynamically create a list in an HTML document from an array.
```HTML file:document.createElement()-example fold
<head>
	<title>Generating a list</title>
</head>

<body>
	<h1>Here are some types of balls</h1>
	<ul id="ballList"></ul>
		<script>
		let typeOfBall = ['basket', 'base', 'soccer', 'foot', 'hand'];
		for (let i = 0; i < typeOfBall.length; i++) {
			let listElement = document.createElement('li');
			listElement.innerHTML = typeOfBall[i];
			document.getElementById('ballList').appendChild(listElement);
	}
</script>
</body>
```

# <u>Removing Elements</u>
The HTML DOM has a number of oddities and tends to make some things more difficult than they should be for professional JavaScript programmers.
A big fault with the DOM is that it doesn’t provide a way to directly remove an element from a document.
* Instead of doing that, you have to tell the DOM to find the parent of the element you're looking for to remove and then tell the parent to remove its child.
In the example below, when you run this in a browser the `onclick` event calls the `removeFirstParagraph()` function. The first thing the function does is select the element that you
actually want to remove, the element with the id `"firstparagraph"`. Then, the script selects the parent node of the first paragraph and uses the `removeChild()` method to remove the first paragraph from the webpage.
```HTML file:removing-elements fold
<head>
	<title>Remove an element</title>
	<script>
		function removeFirstParagraph() {
			let firstPara = document.getElementById('firstparagraph');
			firstPara.parentNode.removeChild(firstPara);
	}
</script>
</head>

<body>
	<div id="gibberish">
		<p id="firstparagraph">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum molestie pulvinar ante, a volutpat est sodales et. Ut gravida justo ac leo euismod, et tempus magna posuere. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Integer non mi iaculis, facilisis risus et, vestibulum lorem. Sed quam ex, placerat nec tristique id, mattis fringilla ligula. Maecenas a pretium justo. Suspendisse sit amet nibh consectetur, tristique tellus quis, congue arcu. Etiam pellentesque dictum elit eget semper. Phasellus orci neque, semper ac tortor ac, laoreet ultricies enim.</p>
	</div>
	<button onclick="removeFirstParagraph();">That's Gibberish!</button>
</body>
```
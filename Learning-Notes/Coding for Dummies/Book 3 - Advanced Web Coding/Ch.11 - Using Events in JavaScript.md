---
tags:
    - learning-notes
    - code-for-dummies
    - JavaScript
obsidianUIMode: preview
---
> "And now, the sequence of events in no particular order."
> -- Dan Rather

Web pages can display more than just static displays of text and graphics. JavaScript provides the interactivity and ability to perform useful work including responding to events within the browser.

## Knowing Your Events
Events are things that happen within the web browser. This includes when the page is loading, when a user clicks on a key of the keyboard, clicking the mouse on an element, moving the mouse, and more. They all happen in time within the browser.

Within the HTML DOM (Document Object Model), JavaScript is given the ability to respond to events within the browser. They can be divided into groups based on the HTML elements or browser objects that its applied to.

### Events Supported by all HTML Elements

| Event        | Occurs when...                                                                                        |
| ------------ | ----------------------------------------------------------------------------------------------------- |
| `abort`      | The loading of a file is aborted.                                                                     |
| `change`     | An `elements` value has changed since losing and regaining focus.                                     |
| `click`      | A mouse has been clicked on an element.                                                               |
| `dbclick`    | A mouse has been clicked twice on an element.                                                         |
| `input`      | The value of an `<input>` or `<textarea>` element is changed.                                         |
| `keydown`    | A key is pressed down.                                                                                |
| `keyup`      | A key is released after being pressed.                                                                |
| `mousedown`  | A mouse button has been pressed down on an element.                                                   |
| `mouseenter` | A mouse pointer is moved onto the element that has the<br>listener attached.                          |
| `mouseleave` | A mouse pointer is moved off of the element that has the<br>listener attached.                        |
| `mousemove`  | A mouse pointer is moved over an element.                                                             |
| `mouseout`   | A mouse pointer is moved off the element or one of its children that has<br>the listener attached.    |
| `mouseover`  | A mouse pointer is moved onto the element or one of its children that<br>the listener is attached to. |
| `mouseup`    | A mouse button is released over an element.                                                           |
| `mousewheel` | A wheel button of a mouse is rotated.                                                                 |
| `reset`      | A form is reset.                                                                                      |
| `select`     | Text has been selected.                                                                               |
| `submit`     | A form is submitted.                                                                                  |
Other types of events are supported by every element other than the `body` and `frameset` elements.

In addition to the events mentioned above, there's many other specifications that can happen. An example of this being the File API has a series of events related to file loading. The HTML5 Media specification contains events related to audio and video playback. There's a lot of things that can happen within the browser.

### Events Supported by event element except `<body>` and `<frameset>`

| Event    | Occurs when...                                       |
| -------- | ---------------------------------------------------- |
| `blur`   | An element has gone out of focus.                    |
| `error`  | A file failed to load.                               |
| `focus`  | An element has come into focus.                      |
| `load`   | A file and its attached files have finished loading. |
| `resize` | The document has been resized.                       |
| `scroll` | The document or an element has been scrolled.        |
### Events Supported by the Window Object

| Event          | Occurs when...                                                                   |
| -------------- | -------------------------------------------------------------------------------- |
| `afterprint`   | The document print preview has been closed or the document has started printing. |
| `beforeprint`  | The document print preview is open or the document is about to be printed.       |
| `beforeunload` | The window, the document, and its included files are about to be unloaded.       |
| `hashchange`   | The part of the URL after the number sign (#) changes.                           |
| `pagehide`     | The browser leaves a page in the browser history.                                |
| `pageshow`     | The browser goes to a page in the session history.                               |
| `popstate`     | The active session history item changes.                                         |
| `unload`       | The document or included file is being unloaded.                                 |
For more events, visit [MDN Events](https://developer.mozilla.org/en-US/docs/Web/Events)

## Handling Events
When JavaScript reacts to something in response, this is called *event handling*.

Browsers have implemented several ways for JavaScript programs to handle events over the years. The landscape of JavaScript events has been one of incompatibilities between browsers.

JavaScript today is getting to the point where old code/techniques that were once used can soon be discarded. They're still widely used today.

### Using inline event handlers
This system for handling events was introduced within the first versions of JavaScript and relies on special event handler attributes within HTML that includes the `onclick` handler.

These inline event handlers are formed by adding the prefix of `on` to the event. When the specified event occurs on the page, JavaScript will perform that action/event. An example coded below is a popup alert when a link is clicked.
```HTML file:inlineMethod-EventHandler fold
<a href="home.html" onclick="alert('Go Home!');">Click here to go home</a>
```

If you put the above example in an HTML document and click the link, a popup window will appear with `Go Home!`. After dismissing the alert window, the link proceeds with the default event and follows the `href` attribute link.

In a lot of cases, you may not want the default action to work within an element. What if you just wanted the alert window to pop up and then do nothing else?

Programmers in the past have come up with different methods to prevent default actions from happening within the web page/code. One is to make the default action something that is inconsequential. An example of this is by changing the value of the `href` attribute to a `#` so the link will point to itself.
```HTML file:betterInlineMethod.html fold
<a href="#" onclick="alert('Go Home!');">Click Here</a>
```

A better method than written above is by telling the event handler to return a `false` Boolean which tells the action to not run.
```html file:betterInlineMethodV2.html fold
<a href="homepage.html" onclick="alert('Go Home!');return false">Click Here</a>
```

Another way to prevent the default action is to use `void` which was learned back in Ch.5

### Event handling using element properties
A big problem with older and inline techniques of assigning events to elements is that it breaks an important rule of programming. That rule being keeping presentation separate from functionality. Mixing event handlers and HTML tags makes the web page more difficult to maintain, debug, and understand.

When v3 of Netscape was introduced, a new event model was added to allow programmers to attach elements as properties. An example of this is coded below.
```HTML file:eventsToElements.html fold
<html>
	<head>
		<title>Counting App</title>
		<script>
		// Wait until the window is loaded before registering the onclick event
		window.onload = initalizer;
		// Create a global counting variable
		var theCount = 0;

			// Registers the onclick event
			function initalizer() {
				document.getElementById('incrementButton').onclick = increaseCount;
			}
			// Increments theCount and displays the result
			function increaseCount() {
				theCount++;
				document.getElementById('currentCount').innerHTML = theCount;
			}
		</script>
	</head>
	<body>
		<h1>Click the button to count</h1>
		<p>Current Number: <span id="currentCount">0</span></p>
		<button id="incrementButton">Increase Count</button>
	</body>
</html>
```
Something to note about the above code is that the function names that are assigned to the event handler don't have parentheses after them. The whole function is assigned to the event handler and is saying "run this when the event happens" rather than using a usual function call. If you do add parentheses after the function name, when executed, the result will be assigned to the `onclick` event which isn't what you want.

### Event handling using `addEventListener`
The two previous methods are commonly used and are supported by ever browser. There's a more modern and flexible way to handle events which is recommended which is to use the `addEventListener()` method.

This method listens for events on any DOM node and triggers certain actions based on the events that happened. When the function is specified as an action for an event, the event will run and usually receives a single argument. This is conventionally named `e` for event.

There's several benefits of using this method, which include...
1. You can apply more than one event listener to an element.
2. It works on any node within the HTML DOM tree, not just its elements.
3. It gives you more control over when it's activated.

The code below has the same counting function as above, but it adds a second event handler to the button that increases the number each time it's clicked.
```HTML file:addEventListener.html fold
<html>
	<head>
		<title>Counting App</title>
		<script>
			window.addEventListener('load', registerEvents, false);
			var theCount = 0;
		function registerEvents(e) {
			document
				.getElementById('incrementButton')
				.addEventListener('click', increaseCount, false);
			document
				.getElementById('incrementButton')
				.addEventListener('click', changeSize, false);
		};


		function increaseCount(e) {
			theCount++;
			document.getElementById('currentCount').innerHTML = theCount;
		};

		function changeSize(e) {
			document.getElementById('currentCount').style.fontSize = theCount;
		};
		</script>
	</head>
	<body>
		<h1>Click the button to count</h1>
		<p>Current Number: <span id="currentCount">0</span>
		<button id="incrementButton">Increase Count</button>
	</body>
</html>
```
From the example above...
* The `addEventListener` method is implemented using three arguments
	1. The first argument is the event type. The method wants the name of the event to be used without the `on` prefix.
	2. The second argument is the function call for when the event happens. It's important to not use parentheses in order for the function to be assigned to the handler.
	3. The third argument which is the Boolean value (`true` or `false`) indicates the order in which the event handlers execute when the element within an event has a parent element associated with that event.

When elements are nested, it's good to know which one will happen first!

Another example is knowing why the order in which event handlers execute is important. The `h1` elements in this next example have click events as well as the text within the header.
```HTML file:eventBubbling.html fold
<html>
	<head>
		<title>Event Capturing vs. Event Bubbling</title>
		<style>
			#theText {
				font-size: 18px;
			}
			h1 {
				border: 1px solid #000;
				background-color: #dadada;
			}
			#capEvent,
			#bubEvent {
				background-color: #666;
			}
		</style>
		<script>
			window.addEventListener('load', registerEvents false);

			function registerEvents(e) {
				document
					.getElementById('capTitle')
					.addEventListener('click', makeTiny, true);
				document
					.getElementById('capEvent')
					.addEventListener('click', makeHuge, true);
				document
					.getElementById('bubTitle')
					.addEventListener('click', makeTiny, false);
				document
					.getElementById('bubEvent')
					.addEventListener('click', makeHuge, false);
			}

			function makeHuge(e) {
				console.log('Making the text huge');
				document.getElementById('theText').style.fontSize = 80px;
			}

			function makeTiny(e) {
				console.log('Making the text tiny');
				document.getElementById('theText').style.fontSize = 10px;
			}
		</script>
	</head>
	<body>
		<h1 id="capTitle">Event <span id="capEvent">capturing </span></h1>
		<h1 id="bubTitle">Event <span id="bubEvent">bubbling </span></h1>
		<p id="theText">Hello, Events!</p>
	</body>
</html>
```
From the example above, when the word *capturing* is clicked, the event registered to the larger container files first and then the event registered to the word capturing.
When you click on *bubbling*, the event registered to that span fires first followed by the event on the parent element.

## Stopping propagation
Adding to bubbling and capturing, you can handle nested events in a third and final way by doing a single event and then stopping the event using the `stopPropagation` method.

<strong><span style="color: yellow">TIP 💡</span></strong>: If you don't need an event propagation in your script, then it's good to turn that off because all the bubbling and capturing uses your system resources and can make a website/program slower.

The example code below shows how to turn off event propagation
```JS file:eventPropagationOff.js fold
function load(e) {
	if (!e) var e = window.event

	e.cancelBubble = true;

	if (e.stopPropagation) e.stopPropagation()
		document
			.getElementById('capTitle')
			.addEventListener('click', makeTiny, true);
		document
			.getElementById('capEvent')
			.addEventListener('click', makeHuge, true);
		document
			.getElementById('bubTitle')
			.addEventListener('click', makeTiny, false);
		document
			.getElementById('bubEvent')
			.addEventListener('click', makeHuge, false);
}
```
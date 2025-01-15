---
tags:
    - learning-notes
    - code-for-dummies
    - JavaScript
obsidianUIMode: preview
---
> "In making theories, always keep a window open so that you can throw one out if necessary."
> -- Bela Lugosi

The Browser Object Model (BOM) allows JavaScript to interact with the functionality of the web browser itself. Using this model, you can create and resize windows, display alert messages, and change the current page being displayed within the browser.

Within this chapter, you'll discover what can be done within the browser window and how its used to write better JavaScript programs.

## Understanding the Browser Environment
Web browsers are complicated pieces of software that, when they work will, they operate seamlessly and use their functions into a smooth browsing experience. Every now and then they may have a hiccup or crash. To understand why this may happen and to have better use of browsers, it's good to know the many different parts of the web browser and how they can interactive with each other.

### The user interface
The part of the browser that you interact with when typing in a URL, clicking the home button, creating/using a bookmark, or changing the settings of the browser is called the user interface (UI).

For example, the Chrome browser consists of the web browser's menus, window frames, toolbars, and buttons that are outside of the main content window where web pages are loaded and displayed.

### Loader
The *loader* is the part of the browser that communicates with web servers and downloads web pages, scripts, CSS, graphics, and all the components that are associated with that web page. Often, loading is part of the display of the webpage that creates the longest possible wait time for a user.

The first part of a webpage that must be downloaded is the HTML page. This contains links, embedded scripts, and styles that need to be processed to display the page.

If and when you open Chrome's Developer Tools (or Firefox's) network tab, it should display a graphical view of everything that happens during the loading of a webpage. This also includes a timeline of showing how long the loading of each part of the webpage takes.

Once the HTML document has finished downloading, browsers will open several connections to the server to download other parts of the web page that are needed as quickly as possible. The parts of a webpage that are linked from the HTML document are loaded in the order of which tyey appear in the code.
* Example: A script that is linked in the `head` element of the HTML page will be loaded before one that's linked at the bottom of the page.

<strong><span style="color: yellow">REMEMBER ❗</span></strong>: The load order of resources if critical for a pages efficiency and speed to be displayed to the user. For the webpage to be displayed correctly, the CSS styles that apply to that page need to be loaded and parsed. The CSS should always be loaded in the `head` element at the top of the web page.

JavaScript sometimes affects the display of a webpage as well, but more often the functionality. When a script will accept the display of a web page, it should be loaded after the CSS in the head of the document. Script that aren't as critical to the webpage should be linked at the end of the body element right before the `</body>` tag. This way, you won't create a blocking scenario where the browser waits for scripts to load before displaying anything to the user.

### HTML parsing
After a webpage is downloading, the HTML parsing component of the browser works to create a model called the Document Object Model (DOM). This is going to be covered in the next chapter. It's like a map of your webpage which is used to manipulate and access different pages of the page.

After the HTML is finished parsing, the browser then begins download the other components of the web page that are needed.

### CSS parsing
Once the CSS for the web page is completely download, the browser will then parse the styles and figure out which ones to apply to the document. This is a complex process involving multiple passes over a document to apply each style correctly and consider how the styles impact each other.

### JavaScript parsing
The next step in the loading process is parsing the JavaScript. This parser compiles and runs every script that the web page contains in order in which it appears within the document. If your code adds or remove elements, text, or styles within the HTML DOM, the browser will update the HTML and/or CSS rendering accordingly.

### Layout and rendering
Lastly, once all the web page's resources have been loaded and parsed, the browser then determines how to display the page and displays it. Unless there's a script that you've included to be executed at the end, the layout and rendering of scripts will occur in the order they're included in the document.

<strong><span style="color: yellow">TIP 💡</span></strong>: It's better to display the web page to the user as quick as possible, even if the page isn't fully functional when it first appears. Modern websites frequently use this strategy (known as deferred loading) to improve the performance of their pages. If you've ever opened a webpage and had to wait a moment before you can use a form or interactive element, then you've seen that in action.

## Investigation the BOM (Browser Object Model)
Programmers using JavaScript can find out information about a user's web browser and control aspects of the user's experience through an API called the Browser's Object Model (BOM).

There's no standard for this model. Different browsers use it in many different ways. But, there are some generally accepted standard for how JavaScript should interact with a web browser.

### The Navigator object
This object provide JavaScript with access to information about the user's web browser. The object takes its name from the first web browser to implement it, Netscape Navigator. This object isn't built into JavaScript, but rather a feature of web browsers that is accessible using JavaScript. Most web browsers have adopted the same terminology to refer to the highest level browser object.

The navigator object accesses helpful information such as...
* The name of the web browser
* The version of the web browser
* The physical location of the computer the browser is running on (if the user allows access to geolocation data to the browser)
* The language of the browser
* The type of computer the browser is running on

#### The Properties of the Navigator Object Table

| Property        | Use                                                   |
| --------------- | ----------------------------------------------------- |
| `appCodeName`   | Gets the code name of the browser.                    |
| `appName`       | Gets the name of the browser.                         |
| `appVersion`    | Gets the browser version information.                 |
| `cookieEnabled` | Tells whether cookies are enabled in the browser.     |
| `geolocation`   | Locates the user's physical location.                 |
| `language`      | Gets the language of the browser.                     |
| `onLine`        | Identifies whether the browser is online.             |
| `platform`      | Gets the platform the browser was compiled for.       |
| `product`       | Gets the browser engine name of the browser.          |
| `userAgent`     | Gets the user-agent the browser sends to web servers. |
To get the properties of the `Navigator` object, you use the same syntax that's used to get the properties of any object using dot or bracket notations.
* The example below will display the current properties and values of the `navigator` object within the browser.
```HTML file:navigatorExample.html fold
<html>
	<head>
		<style>
			.columns {
				column-count: 6;
			}
		</style>
	</head>
	<body>
	<div class="columns">
		<script>
			for (var prop in navigator) {
				document.write(prop + ': ' + navigator[prop] + '<br>');
			}
		</script>
	</div>
	</body>
</html>
```
If/when you run the code above, the output will be interesting. The values for `appName` and `userAgent` properties are wrong.
The misleading values are something from the days when programmers used the properties of the `Navigator` object to see if a user was using a certain browser that only supported certain features.

With new/current browsers such as Chrome and Firefox, they adopted the Netscape browser `appName` value in order to make sure they were compatible with websites that needed certain features.

<strong><span style="color: yellow">WARNING ⚠</span></strong>: Browser detection isn't recommended today as there's better ways to detect support for functionality by looking at the `appName` property within the `Navigator` object. A common way to detect features is by examining the DOM for objects that are associated with the feature that you want to use. An example of this would be finding out if the HTML `audio` element works with the browser or not.
```JS file:audio-check-JS fold
let test_audio = document.createElement('audio');

if (test_audio.play) {
	console.log('Browser supports HTML5 audio');
} else {
	console.log("Browser doesn't support HTML5 audio");
}
```

### The Window Object
The main area of the browser is called the *window*. This is where the HTML and other resources are loaded into. Each tab within the web browser is represented by the JavaScript `window` object. Some of it's most common uses are...
* Opening a new location in the browser window
* Finding the size of a browser window
* Returning to a previously open page (*back button functionality*)

### Opening a web page with the `window.location` property
Getting the value from the `window.location` property will return the URL of the current page the user is on. Setting a value of the property will load that webpage in the window.

#### The Window Object's Properties Table

| Property        | Use                                                                                                                 |
| --------------- | ------------------------------------------------------------------------------------------------------------------- |
| `closed`        | A Boolean value indicating whether a window has been closed or not.                                                 |
| `defaultStatus` | Gets or sets the default text in the status bar of a window.                                                        |
| `document`      | Refers to the `document` object for the window                                                                      |
| `frameElement`  | Gets the element, such as `<iframe>` or `<object>`, that the window<br>is embedded in.                              |
| `frames`        | Lists all the subframes in the current window.                                                                      |
| `history`       | Gets the user’s browser history for the current window.                                                             |
| `innerHeight`   | Gets the inner height of the window.                                                                                |
| `innerWidth`    | Gets the inner width of the window.                                                                                 |
| `length`        | Gets the number of frames in the window.                                                                            |
| `location`      | Gets the Location object for the window.                                                                            |
| `name`          | Gets or sets the name of the window.                                                                                |
| `navigator`     | Gets the `Navigator` object for the window.                                                                         |
| `opener`        | Gets the `Window` object that created the current window.                                                           |
| `outerHeight`   | Gets the outer height of the window, including scrollbars and toolbars.                                             |
| `pageXOffset`   | Gets the number of pixels that have been scrolled horizontally in<br>the window.                                    |
| `pageYOffset`   | Gets the number of pixels that have been scrolled vertically in<br>the window.                                      |
| `parent`        | Refers to the parent of the current window.                                                                         |
| `screen`        | Refers to the `Screen` object of the window.                                                                        |
| `screenLeft`    | Gets the horizontal pixel distance from the left side of the main<br>screen to the left side of the current window. |
| `screenTop`     | Gets the vertical pixel distance from the top of the window relative<br>to the top of the screen.                   |
| `screenX`       | Gets the horizontal coordinate relative to the screen.                                                              |
| `screenY`       | Gets the vertical coordinate relative to the screen.                                                                |
| `self`          | Refers to the current window.                                                                                       |
| `top`           | Refers to the topmost browser window.                                                                               |
Below is an example of a script for loading a webpage within the browser window using the `window.location` property.
```HTML file:loadWithin.html fold
<html>
	<head>
		<script>
			function loadNewPage(url) {
				window.location = url;
			}
		</script>
	</head>
	<body>
		<script>
			let newUrl = prompt('
				Please enter a web page address!');
			loadNewPage(newURL);
		</script>
	</body>
</html>
```

### Determining the size of a browser window
When designing a website or web application that works and functions on different types of devices using responsive design, knowing the size of the browser is very important.

The `window.innerWidth` and `window.innerHeight` properties give this information in pixels for the current browser window.

<strong><span style="color: yellow">TECHNICAL 🤓</span></strong>: Using CSS to determine the size of the browser is also possible and very commonly used. There's differences in how CSS and JavaScript treat scrollbars that influence which you decide to use.

Running the example below, if the browser window is below 500px, a message will be displayed. If the browser window is above 500px, then a different message will be displayed.
```HTML file:sizeOfWindow.html fold
<html>
	<head>
		<title>Adapting to the window.innerWidth</title>
	</head>
	<body>
		<script>
			let currentWidth = window.innerWidth;

			if (currentWidth > 500) {
				document.write('<h1>Your window is big.</h1>');
			} else {
				document.write('<h1>Your window is small.</h1>');
			}
		</script>
	</body>
</html>
```
You can test the code above by following these steps...
1. In the web browser of your choice, open an HTML document containing the code from above.
2. Drag the lower right corner of the browser to make the window as narrow as possible.
3. Click your browser's refresh button to reload the page.

### Creating a Back button using location and history
The `history` property of the `window` object is a read-only reference to the history object. This stores information about the pages the user has accessed in the current window. The most common use of this object is to enable buttons that return the user to a previously viewed page. An example of this is coded below.
```html file:backButton.html fold
<html>
	<head>
		<title>Creating a Back Button</title>
		<script>
			function takeMeBack() {
				window.location(history.go(-1));
			}
			function getHistoryLength() {
				var 1 = window.history.length;
				return 1;
			}
		</script>
	</head>
	<body>
		<script>
			var historyLength = getHistoryLength();
			document.write("<p>Welcome! The number of pages you've visited in this window is: " + historyLength + ".</p>);
		</script>
		<br/>
		<a href="javascript.void(0);" onclick="takeMeBack();">Go back</a>
	</body>
</html>
```
To use the code above, follow these steps...
1. Open a new browser window and visit any page you'd like.
2. While in that same window, open an HTML document containing the code from above.
3. Click the `Go back` link.

## Using the Window object's methods
The `window` object also has some useful methods that programmers should know how to use including its properties. Here's a table of these methods.

| Method            | Use                                                                                                |
| ----------------- | -------------------------------------------------------------------------------------------------- |
| `alert()`         | Displays an alert box with a message and an OK button.                                             |
| `atob()`          | Decodes a base-64 encoded string.                                                                  |
| `blur()`          | Causes the current window to lose focus.                                                           |
| `clearInterval()` | Cancels the timer set using `setInterval()`.                                                       |
| `clearTimeout()`  | Cancels the timer set using `setTimeout()`.                                                        |
| `close()`         | Closes the current window or notification.                                                         |
| `confirm()`       | Displays a dialog box with an optional message and two<br>buttons; OK and Cancel.                  |
| `createPopup()`   | Creates a popup window.                                                                            |
| `focus()`         | Sets the current window into focus.                                                                |
| `moveBy()`        | Moves the current window by a specified amount.                                                    |
| `moveTo()`        | Relocates a window to a specified position.                                                        |
| `open()`          | Opens a new window.                                                                                |
| `print()`         | Prints the contents of the current window.                                                         |
| `prompt()`        | Displays a dialog box prompting the user for input.                                                |
| `resizeBy()`      | Resizes the window by a specified number of pixels.                                                |
| `resizeTo()`      | Resizes a window to a specified height and width.                                                  |
| `scrollBy()`      | Scrolls the document by a specified amount.                                                        |
| `scrollTo()`      | Scrolls the document to a specific set of coordinates.                                             |
| `setInterval()`   | Calls a function or executes an expression repeatedly at<br>specified intervals (in milliseconds). |
| `setTimeout()`    | Calls a function or executes an expression after a specified<br>interval (in milliseconds).        |
| `stop()`          | Stops the current window from loading.                                                             |
<strong><span style="color: yellow">REMEMBER ❗</span></strong>: A method is another name for a function that's contained within an object.
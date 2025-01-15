---
tags:
    - learning-notes
    - code-for-dummies
    - JavaScript
obsidianUIMode: preview
---
> "The Secret of getting ahead is getting started."
> -- Mark Twain

Simple JavaScript programming isn't difficult to understand. Within this chapter, you're going to setup your computer/laptop for writing JavaScript code and writing your first JavaScript program to understand the basic syntax.

# Setting Up Your Development Environment
It's important to have all your tools setup before starting to write your first program. Before starting (*if you haven't done so already...*) is to download some development tools.
If there are preferred tools you prefer using than the ones that are recommended, that's fine. You're allowed. Still be sure to read this section of the book to learn and understand the most popular JavaScript tools and then make your own decisions of what you'd like to do.

<strong><span style="color: yellow">REMEMBER ❗</span></strong>: Should you not want to download tools, you can use Codesandbox.io.

After installing these tools, you'll learn some tricks for how to get the most out of each.

## Downloading and installing Google Chrome
*SIDE NOTE: Use Firefox instead...*

All browsers run JavaScript very fast and correctly. Some of the instructions provided will be specific to Google Chrome because it offers excellent tools for making a JavaScript programmer's job easier and it's widely used.
To download Google Chrome, follow these steps...
1. Go to the [Google Chrome website](https://www.google.com/chrome/)
2. Click on `Download Chrome` along with the appropriate version for the OS you're using.
3. Open the downloaded file and follow the instructions provided to install Google Chrome.

## Downloading and installing a code editor
A *source code editor* (aka code editor), is a text editor with added functionality to help write and edit programming code for any language available. In this section, we're going to learn about Visual Studio Code (VS Code).

<strong><span style="color: yellow">TIP 💡</span></strong>: There's many code editors to choose from. If you already have a favorite, then use that since you're comfortable with it. It's your personal choice as to what you want to use. If that doesn't fit your style, then check out the table below.

VS Code is popular among programmers as it provides a simple user interface and many plugins for handling advanced programming tasks.

| Code Editor Name | Website                                                                     | Compatible with...  |
| ---------------- | --------------------------------------------------------------------------- | ------------------- |
| Brackets         | [brackets.io](https://brackets.io/)                                         | Mac, Windows, Linux |
| Sublime Text     | [sublimetext.com](https://www.sublimetext.com/)                             | Mac, Windows, Linux |
| Nova             | [nova.app](https://nova.app/)                                               | Mac only            |
| Notepad++        | [notepad-plus-plus.org](https://notepad-plus-plus.org/)                     | Windows only        |
| TextMate         | [macromates.com](https://macromates.com/)                                   | Mac only            |
| BBEdit           | [barebones.com/products/bbedit](https://www.barebones.com/products/bbedit/) | Mac only            |
| EMacs            | [gnu.org/software/emacs](https://www.gnu.org/software/emacs/)               | Mac, Windows, Linux |
| TextPad          | [textpad.com](https://textpad.com/home)                                     | Windows only        |
| vim              | [vim.org](https://www.vim.org/)                                             | Mac, Windows, Linux |
| Netbeans         | [netbeans.org](https://netbeans.apache.org/front/main/index.html)           | Mac, Windows, Linux |
*Atom code editor was discontinued in 2022*

To install VS Code, follow these steps...
1. Go to [code.visualstudio.com](https://code.visualstudio.com/) and choose the appropriate version for your OS.
2. Open the downloaded file and follow the instructions to install VS Code to your OS.

### Getting started with VS Code
When you first open the VS Code program, you'll have the option to choose a color theme. You can skip this for now or choose what you'd like to have. Next, click on the `Get Started` link in the upper left corner to get to the `Get Started` screen.

If you've used this program before, you'll be given the option to choose to open a recent project from the `Get Started` page. If not, then click on `New File` .

To get started with your first VS Code project, follow these steps...
1. Click `New File` from the Get Started screen.
2. Click the Explorer icon (the magnifying glass) in the left toolbar. The explorer pane will open on the left and will tell you that you haven't opened a folder yet.
3. Click `Open Folder` and find the folder (*or create one*) on your computer to where you'd like to save the JavaScript files that you create over time.
4. Save your untitled file in your new folder name it `myFirstProgram.html`.

### Choosing a syntax color scheme
VS Code syntax colors are based on the type of code that you're writing and the file extension you've created. Input the following HTML and JavaScript code in the file you've just created in VS Code to see the color scheme.

<strong><span style="color: yellow">WARNING ⚠</span></strong>: As you're soon to find out, JavaScript is finicky. Make sure to capitalize and spell everything correctly or your code won't work properly.
```HTML file:HTML-with-JS fold
<!DOCTYPE html>
<html>

<head>
	<title>Hello, HTML!</title>
	<script>
		function countToTen() {
			let count = 0;
			while (count < 10) {
				count++;
				document.getElementById("theCount").innerHTML += count + "<br>";
			}
		}
	</script>
</head>
<body onload="countToTen();">
	<h1>Let's Count to 10 with JavaScript!</h1>
	<p id="theCount"></p>
</body>
</html>
```

To try out the code that's been typed up, follow these steps...
1. Save the file by choosing File -> Save
2. Open your Chrome browser and press CTRL + O (*the open file window appears*)
3. Navigate to the file on your computer that you wrote the code in and select it.
4. Click the Open button (*the file should open in the browser*).

<strong><span style="color: yellow">TECHNICAL 🤓</span></strong>: You can save your file by doing Command + S (*on MAC*) or CTRL + S (*on Windows*).

## Reading JavaScript Code
Before getting started with writing JavaScript programs, you need to be aware of a few rules within JavaScript.
* **JavaScript is case-sensitive**: Mistakes in the capitalization of words are probably the most common error that those who are new to programming make. They're also a difficult bug to track down as well. In JavaScript, the words `pants` and `Pants` are completely different.
* **JavaScript doesn't care about whitespace**: Whitespace includes spaces, tabs, and line breaks or any character that doesn't have visual representation. When writing JavaScript, it doesn't matter if you use one, two, or three spaces, a tab, or a line break within the code. The one exception is when you're writing out text that you want to print to the screen. In that case, the whitespace will show up in the end result. For whitespace within code, it makes it easier for you and others to read the code.
* **Watch out for reserved words**: JavaScript contains a list of words that have special meanings to the language. The words are mentioned in the next chapter, but be aware of words such as `function`, `while`, `break`, and `with`.
* **JavaScript likes semicolons**: JavaScript is made up of statements that are similar to sentences in the English language and are considered the fundamental building blocks of JavaScript programs. Statements in JavaScript end with a semicolon.
<strong><span style="color: yellow">WARNING ⚠</span></strong>: If you don't have a semicolon at the end of a statement, JavaScript will put one there for you. If you didn't want one there, it may lead to some unexpected results.

## Running JavaScript in the Browser Window
Although seen in other environments, the most common place to see JavaScript in the wild is in web browsers. Controlling the inputs, outputs, manipulating web pages, common browser events, and more is what the language was born to do!

To run JavaScript inside of a browser, there's 3 options...
1. Put it directly in an HTML event attribute.
2. Put it between the opening and closing script tags.
3. Put it in a separate document and include it in your HTML document.

Many times, you may use a combination of all 3 techniques within a single web page. Knowing when to use each is important and a skill that you'll learn over time with practice.

### Using JavaScript in an HTML event attribute
HTML has several special attributes designed for triggering JavaScript code when something happens within a web browser or when the user does something. An example of that can be seen below.
```HTML file:html-on-click-event fold
<button id="bigButton" onClick="alert('Hello World!');">Click Here</button>
```

In the case above, when the user clicks on the button, a popup will appear within the browser with the words "Hello World!".

There's over 70 different event attributes within HTML. The table below shows the most commonly used.

| Attribute     | Description                                                                         |
| ------------- | ----------------------------------------------------------------------------------- |
| `onload`      | Runs the script after the page finishes loading.                                    |
| `onfocus`     | Runs the script when the element gets focus (when a textbox is active)              |
| `onblur`      | Runs the script when the element loses focus (when the user clicks a new text box ) |
| `onchange`    | Runs the script when text has been submitted                                        |
| `onselect`    | Runs the script when text has been submitted                                        |
| `onsubmit`    | Runs the script when a form has been submitted                                      |
| `onkeydown`   | Runs the script when a user is pressing a key                                       |
| `onkeypress`  | Runs the script when a user presses a key                                           |
| `onkeyup`     | Runs the script when a user releases a key                                          |
| `onclick`     | Runs the script when a user mouse clicks an element                                 |
| `ondrag`      | Runs the script when an element is dragged                                          |
| `ondrop`      | Runs the script when a dragged element is being dropped                             |
| `onmouseover` | Runs the script when a user moves a mouse pointer over an element                   |
<strong><span style="color: yellow">WARNING ⚠</span></strong>: Although easy to use, using event attributes in HTML is considered less-than-ideal to use by many programmers. You'll learn about that later in the book because they're widely used and easy to learn. Just be aware that there are better ways to write code that responds to events than to use event attributes. This will be brought up in chapter 11.

## Using JavaScript in a script element
The HTML script element allows you to embed JavaScript right into an HTML document. These are usually placed within the `head` element and is a requirement. Today, the script element is often used within the `head` element and the body of web pages.
```HTML file:script-format-HTML fold
<script>
	(insert JavaScript code here)
</script>
```

As seen in an example earlier, this is another example of a HTML document with a script tag containing JavaScript. But, the script tag is at the bottom of the body element.
```HTML file:Script-at-bot fold
<!DOCTYPE html>
<html>
<head>
	<title>Hello, HTML!</title>
</head>
<body>
	<h1>Let's Count to 10 with JavaScript!</h1>
	<p id="theCount"></p>
	<script>
		let count = 0;
		while (count < 10) {
			count++;
			document.getElementById("theCount").innerHTML += count + "<br>";
		}
	</script>
</body>
</html>
```

If you create a new file within VS Code and then open it in a web browser, you'll notice that it does the same thing as the example from earlier in the notes.

### Script placement and JavaScript execution
Web browsers usually load and execute scripts as they're loaded in and gets read from the top down. Sometimes you'll wait to see the browser is done loading the content before the script runs on the page. We accomplished this earlier with the `onload` event attribute in the body element. Another way to delay the execution of JavaScript code is to place the code to be executed at the end of the code.

### Limitations of JavaScript in `<script>` elements
Much more commonly used and accepted than the inline scripting, embedding the JavaScript into a script element has many limitations.
The biggest is that scripts embedded in this way can be used only within the webpage of where they are location. You'd have to copy and paste the `<script>` element into every page where it exists. This wouldn't be a good idea for a website with 100+ or more pages which can be a nightmare to fix in the future.

### When to use JavaScript in `<script>` elements
The method of embedding JavaScript like this does have its uses from time to time. For something small as calling other bits of JavaScript that may never change, then it's acceptable so you don't have to make so many requests to the web server.
SPAs (Single Page Apps) only contain a single HTML webpage and a great chance to use this option since there's only 1 page and 1 place to use the code.
As a rule of doing this, try to minimize the amount of JavaScript code that you embed into the HTML document. It'll be easier maintenance and better organization for the code/project you're working on.

## Including external JavaScript Files
The third and most popular way to add JavaScript to a HTML document is by using the `src` attribute within the `<script>` element.
Using this attribute with the `<script>` element works similarly to the tag having code between the tags. The JavaScript code is loaded into the HTML file through a different file.
```HTML file:script-JS fold
<script src="myScript.js"></script>
```

In the use case from above, you'd have a separate file named `myScript.js` which would be contained in the same folder as the HTML file is in. The benefits of using this way are...
1. Keeps your HTML files neat and less cluttered.
2. Makes life easier because you modify the JavaScript code in one place when you need to make changes or fix a bug.

### Creating a `.js` file
Creating an external JavaScript file is like creating another file in your project. Follow these steps.
1. Is VS Code (*or whatever code editor you're using*), choose File -> New File
2. Copy your code between the `<script>` and `</script>` tag that was created earlier.
3. Save that file as `countToTen.js` in the same folder as your HTML file
4. In the HTML file, modify the `<script>` tag by adding a `src` attribute, which should now look like this...
```HTML file:myFirstProgram.html fold
<!DOCTYPE html>
<html>
	<head>
		<title>Hello, HTML</title>
		<script src="countToTen.js"></script>
	</head>
	<body onload="countToTen();">
		<h1>Let's Count to 10 with JavaScript!</h1>
		<p id="theCount"></p>
	</body>
</html>
```
```JS file:countToTen.js fold
function countToTen() {
	let count = 0;
	while (count < 10) {
		count++;
		document.getElementByUd("theCount").innerHTML += count + "<br>";
	}
}
```

After saving both of the files created, you should see both of them on the Code Explorer pane within VS Code (*or whatever code editor you're using*).

### Keeping your `.js` files organized
External JavaScript files can sometimes get large in size. It's a good idea to break them up into smaller files organized by the type of functions they contain for your project.
* If one file contains scripts related to login capabilities for users while another file contains blogging capabilities.
For smaller projects/programs, it's ok to have just one JavaScript file which is usually named `app.js`, `main.js`, or `scripts.js`.

Consider the following steps to create a `.js` folder inside of your project.
1. Click the New Folder icon at the top of the code explorer pane.
2. A blank text area should appear within the explorer. You can enter `.js` into the folder name field and press enter.
3. A new folder called `js` should appear in the sidebar.
4. Click and drag the `countToTen.js` file in the explorer and place it into the `js` folder.
5. Open `myFirstProgram.js` and change the `script` element to reflect the new location of the file by typing this out...
```HTML file:newJSLocation fold
<script src="js/countToTen.js"></script>
```

As you open the `myFirstProgram.html` in your browser (or refreshing the browser after you've made the changes), it should like exactly like it did before you moved the files around and added the `js` folder.

## Using the JavaScript Developer Console
Sometimes, it's nice to run JavaScript commands without creating a new HTML and/or JavaScript file. You can use the browser's JavaScript Console within Google Chrome/Mozilla Firefox.
* To access the console, go to the upper right menu of the browser with the 3 dots/lines. From there, look for more tools and then Browser's Console.
	* Another and faster way to open this is by hitting `F12` within the browser. This will open the console.
<strong><span style="color: yellow">TECHNICAL 🤓</span></strong>: The JavaScript console is considered the best friend of a JavaScript developer. Allowing you to test and run JavaScript code quickly, it also shows error within your code file that are reported and tell you where to look for them.

After opening the console, you can input commands into it. As soon as you press `Enter`, you'll see the code you create with a response from the browser.
```JS file:usingTheConsoleFromBrowser fold
1080/33 // 32.727272
40 + 2  // 42
40 * 34 // 1360
100 % 3 // 1
34++    // 35
34--    // 33
```

## Commenting Your Code
As you learn more about JavaScript commands and start to write larger programs over time, it's helpful to often leave little reminders of what you're thinking about or what something does. These are referred to as "comments".

<strong><span style="color: yellow">REMEMBER ❗</span></strong>: The JavaScript engine will completely ignore comments are they're just for people. This is a good time to explain something, clarify something, or describe what you're thinking. Also, a good time to leave reminders about what you might want to do to the code in the future.

Even if you think your code is self-explanatory at the time you're writing it, you may want to make a comment so down the road in the future you may need to modify it.

There's two ways to make something a comment within JavaScript
1. Single-line comments
2. Multi-line comments

### Single-line comments
Single-line comments start with `//`. Everything after the slashes and until the end of that line will be ignored by JavaScript. They don't need to start at the beginning of the line. It's quite common to see it being used on the same line as code.
```JS file:single-line-comment-JS fold
pizzas = pizza + 1 // add 1 more pizza
```

### Multi-line comments
Multi-line comments start with `/*` and tell the engine to ignore everything until it sees `*/`. This is useful for more extensive documentation of code.
```JS file:multi-line-comment-JS fold
/* The countToTen function does the following things:
	* Initializes a variable called count
	* Starts a loop by checking the value of count to make sure it's less than 10
	* Adds 1 to the value of count
	* Appends the current value of count, followed by a line break, to the paragraph with id="count"
	* Starts the loop over
*/
```

### Using comments to prevent code execution
Other than being useful for documenting code, it's also helpful for isolating pieces of code to find problems/bugs. An example being if you wanted to see what the `countToTen` function would do if you remove the part of the code that increments the value of `count`, you could comment that line out with a single-line comment.
```JS file:real-life-example-single-comment fold
function countToTen() {
	let count = 0;
	while (count < 10) {
		// count++;
		document.getElementById("theCount").innerHTML += count + "<br>";
	}
}
```

When you run the program above, the line of `count++` won't run anymore and the program will print out 0's forever; until you close the browser window.

<strong><span style="color: yellow">WARNING ⚠</span></strong>: What you've created with the above code is called an *infinite loop*. If you run the modified version of this program, it won't do any harm to the computer itself. However, it'll take the CPU for a ride of spinning in circles until you shut down the browser itself.
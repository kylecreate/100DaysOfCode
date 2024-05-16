---
tags:
  - WebDev
---
## Section Intro

It's now time to finally build our first project with a visual user interface. Going to be building 3 different projects to learn the basics of DOM. With this section, we're going to learn how to make JavaScript interact with web pages.

---

## Section Roadmap

Complete everything!

---
## Project #1: Guess My Number

This is the first of the 3 projects that are going to be built.
The project that's going to be built is a "Guess My Number" game as he shows a demo of the final product.
```JS file:using-DOM-to-get-message
console.log(document.querySelector('.message').textContent);
// Start guessing...
```

---
## What's the DOM and DOM Manipulation?

In this section, we're going to use JavaScript to interact with the web page for the very first time. The technical and coding term for this is called <u>DOM Manipulation</u>.
With the code from the last section, we already selected an element from a page. This means we sort of interacted with the DOM already. But, now we're going to learn what the DOM is and how it works.

### What is the DOM?
[DOM - MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) - This connects web pages to scripts or programming languages by representing the structure of a document—such as the HTML representing a web page—in memory.

<u>DOM (Document Object Model)</u>: Structured representation of HTML documents that allows JavaScript to access HTML elements and styles to manipulate them.
* Changing text, HTML attributes, and CSS styles
* Basically a connection point between HTML documents and JavaScript code.
* This DOM is automatically created as soon as the webpage loads and stored in a tree structure.
	* [Example of the tree structure](http://web.simmons.edu/~grabiner/comm244/weekfour/document-tree.html)

### The DOM Tree Structure
[[HTML DOM Tree Structure.canvas|HTML DOM Tree Structure Canvas]]

1. The DOM starts with the <u>document object</u> **that is always** at the very top of the tree.
	* We have access to this object that is a entry point into the DOM (`document.querySelector()`).
	* [querySelector Method - MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector) - This method returns the first `Element` within the document that matches the specified selector, or group of selectors. If no matches are found, `null` is returned.
1. The first child element of Document is usually the HTML element because it's the root element in all of HTML documents. (IE: The entire code of the HTML from the example above.)
2. HTML usually has two child elements that are under the Document, the `<head>` and `<body>` elements.
	* They're siblings in our DOM since they're next to each other in the tree structure.
3. Going deeper into the tree, we keep adding more and more children. Inside of head and body, you have more child elements (`<title>` and `<section>`). The 2 sections that are apart of the HTML even have children themselves (`paragraph` and `img`).
	* The first paragraph goes even deeper because it has a child element of a link.
The DOM tree structure has more than just element nodes. It also has nodes for all the text, comments, and others. This is because that whatever is in the HTML document has to be in the DOM. The DOM is a complete representation of the HTML document that can be manipulated in different ways.

### DOM `!==` JavaScript
Many people believe that all the methods and properties for the DOM are part of JavaScript. It's not true at all.
* JavaScript is a dialect of the ECMAScript specification.
* We've only really used the JavaScript language itself until this section where we will also use JavaScript in the browser.
"If the DOM is not apart of the JavaScript language, then how does this all work?"
* The DOM and DOM Methods are part of the Web APIs, which are like libraries that browsers implement and can access from our JavaScript code.
	* <u>API</u> stands for Application Programming Interface
	* Also written in JavaScript
	* Automatically available for us to use for free.
	* We don't have to import anything
	* There's an official DOM specification that browser's implement which is how they work the same in all browsers.
	* Besides the DOM, there's more web APIs that we can use (*going to learn more about that in the future*).
		* Timers
		* Fetch API
		* and more!
---
## Selecting and Manipulating Elements

Now that you have a better understanding of what DOM and DOM manipulation are, we're now going to select and manipulate more elements.
[textContent Property - MDN](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent) - This property of the `Node` interface represents the text content of the node and its descendants.

```JS file:adding-in-numbers-ourselves fold
document.querySelector('.number').textContent = 13; // Value in correct number
document.querySelector('.score').textContent = 10; // Value is score box

document.querySelector('.guess').value = 23; // Value in textbox
console.log(document.querySelector('.guess').value); // Logging above number
```

---
## Handling Click Events

With our code, we're going to make the web application we're creating do something when click on the `check` button. This will be the first time that our code reacts to something for the first time with the DOM.
We need to use an event listener which is when something happens on the page, IE: mouse click, key press, or others.
With the event listener in our code, we can wait for a certain event to happen and then have it react to whatever is happening with something else.
```JS file:making-sure-guess-is-number fold
document.querySelector('.check').addEventListener('click', function() {
	const guess = Number(document.querySelector('.guess').value);
	console.log(guess, typeof guess);

	if (!guess) {
		document.querySelector('.message').textContent = '🚫 No Number!';
	}
});
```

[addEventListener Event Target - MDN](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) - This method of the `EventTarget` interface sets up a function that will be called whenever the specified event is delivered to the target.

---
## Implementing the Game Logic

Going to continue building out the game and implement the game logic itself (*the way how the game works when someone guesses a number correctly/incorrectly*).
* Refer to the old code in the `guess my number` folder
---
## Manipulating CSS Styles

You can manipulate CSS styles within the DOM using what we've learned with manipulating HTML. However, you use the same ways of classes and IDs when trying to change them.
* If a CSS property has a hyphen in it, then it won't have one when trying to find it with the DOM. Everything is camel cased and must be in a string when trying to change something.
```JS file:CSS-to-JS fold
document.querySelector('body').style.backgroundColor = '#60b347';
```

---
## Coding Challenge #1

With this coding challenge, we need to implement the game functionality which is a challenge he's giving us.
* Before starting, we need to fix and hide the secret number so it's not shown on the page when playing the game. We move that line of code to the function where the player has won the game so the question mark comes back.

### Instructions
Implement a game rest functionality, so that the player can make a new guess! Here is how:

1. Select the element with the 'again' class and attach a click event handler.
2. In the handler function, restore initial values of the score and `secretNumber` variable.
3. Restore the initial conditions of the message, number, score, and guess input field.
4. Also, restore the original background color (#222) and number width (15rem).
```JS file:solution fold
document.querySelector('.again').addEventListener('click', function() {
    score = 20;
    secretNumber = Math.trunc(Math.random() * 20 + 1);

    document.querySelector('.message').textContent = 'Start guessing...';
    document.querySelector('.score').textContent = score;
    document.querySelector('.number').textContent = '?';
    document.querySelector('.guess').value = '';

    document.querySelector('body').style.backgroundColor = '#222';
    document.querySelector('.number').style.width = '15rem';
});
```

---
## Implementing Highscores

Now, we're going to implement the last missing functionality which is the highscore part of the game.
```JS file:highscore-check fold
let highScore = 0;

if (score > highScore) {
	highScore = score;
	document.querySelector('.highscore').textContent = highScore;
}
```

---
## Refactoring our Code: The DRY Principle

It's important to not have duplicate code in your program because whenever we have duplicated code, when we want to change a functionality about something then we need to change it in multiple instances. Try to avoid that as best as you can. You can start with duplicate code when first writing it, but then it's best to clean it up in the future. You can use something called Refactoring (or restructuring) the code to remove duplicate code and improve the code.
* An example of this is the checking of whether the player's guess was too high or too low. The only thing that needs to he changed out is the string that tells the player if their guess was high or low depending on the random number chosen by the program.

#### Explanation of how the code works
*(Rubber Duck Theory!)*
At the top of the code we have three variables which include `secretNumber`, score and high score.
* The secret number variable includes `math.trunk` and `math.random` being multiplied by 20 and adding 1 to get a random number between 1 and 20.
* The score is set to 20 and high score is set to zero
We then have a function of display message which will display a message using the document query selector to insert a message into the HTML document.
Then, we make another document query selector in the check CSS class to add an event listener with a function of guessing the random number to then tell what that type of guess is and what the guess is.
* If the guess has no number or input in the field, then the document query selector will produce text content that says `🚫 No Number!` .
If the number chosen is the correct number guessed, then background color will change, the number box width will change in size, and the secret number will be revealed to the player.
* To check the high score we see if the current score is greater than the previous highest score which will be shown on the web page.
If the guess is not the secret number but is also greater than one than the display message function will run to either show that the secret number is either too high or too low and decreasing that score by one by showing your new score. If you get the number wrong after `x` amount of guesses, then you will get a message saying you `💥 You lost the game!` and the score is equal to zero.
The last thing is the clicking on the `again` button which is a query selector and add event listener function with the start of a score of 20, and the secret number being changed back to a random number. The display message function will bring back the `start guessing...` text on the web page and the score will be set to 0, where the number is that we need to guess and the value in the box is set to an empty string, the body and the number styling will be set to how it was before you started the game.

---
## Project #2: Modal Window

In this project, we will be creating a webpage that had 3 buttons we can click on. Each button will have a window popup with some text that we can keep open or close. Once we hit the ESC key, outside the box, or the X on the window, the window will go away.
* He goes over how the HTML and CSS work and what the code looks like

When trying to use the `querySelector` property on a CSS property that is used more than once, it will only show the first one. Instead, we should use `querySelectorAll`. This will create a `nodeList` which is similar to an array, but it's not an array.

---
## Working with Classes

Going to learn how to manipulate classes with JavaScript.
The first thing we have to do, is react to a click on each of the buttons even though nothing happens.

[add() method - MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/add):  This method of the `DOMTokenList` interface adds the given tokens to the list, omitting any that are already present.
* For a CSS class, you don't need to add the `.` to the CSS class
* `modal.classList.add('hidden')`
[remove() method - MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/remove): This method of the `DOMTokenList` interface removes the specified _tokens_ from the list.
* Similarly to the add method, you don't need to add the `.` to the CSS class
* `modal.classList.remove('hidden');`
---
## Handing an "ESC" Keypress Event

Now, we're going to learn how to handle keypress events.
In the previous lesson, we can close the 'X' button or outside of the box. We can also do keypress events, in this case using the "ESC" key.

[Keydown Event - MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/keydown_event): The **`keydown`** event is fired when a key is pressed.
* `eventTarget.addEventListener("keydown", (event))`
[Keyup Event - MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/keyup_event): The **`keyup`** event is fired when a key is released.
* `eventTarget.addEventListener("keyup", (event))`
[Keydown Event - MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/keydown_event): The **`keydown`** event is fired when a key is pressed. This is similar to `keypress`
* `eventTarget.addEventListener("keydown", (event))`
[Keyboard Event - MDN](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent): This objects describe a user interaction with the keyboard; each event describes a single interaction between the user and a key (or combination of a key with modifier keys) on the keyboard.

---
## Project #3: Pig Game

With this project, it's going to be the most exciting one because we're going to take everything we learned from the first two projects to create a very fun game called "The Pig Game". This will be a practice project where we reinforce the skills we learned up until now.
* Reinforcing knowledge is the most important thing you can do.

[[Pig Game Flowchart.canvas|Pig Game Flowchart]]
* A representation of everything that can happen in the application
	* <span style="color: yellow">Yellow</span> represents the actions that the users/players can take and then see what happens after the chosen options
* Can also use [Draw.io](https://www.drawio.com/) to create what he made

*Goes over how the actual game works and what the HTML/CSS/JS code looks like as it's also hosted on the web*

We select the score elements and the dice element on the webpage, create a hidden class in CSS to hide anything, and then change the scores to 0 at the beginning of the game and hide the dice before starting the game.

---
## Rolling the Dice

We will actually start implementing the game's functionality and start with working on rolling the dice.
* Creating a flowchart for a project like this (or even a website) makes a big problem have a lot of small problems that are easier to work through. All the squares on the flowchart are sub-problems that are needed to be worked on.
* Divide the big problem into smaller problems that will be easy to implement.

---
## Switching the Active Player

We're going to be concerned in this video with switching from one active player to another whenever either player rolls a dice of 1. If the player doesn't roll a 1, it gets added to their score until they hold.
We need to keep track of who is the current player (active player as the dice was rolled).
* Whenever the button is clicked

---
## Holding Current Score

We're going to implement the feature of holding their current score.
Looking at the flow chart, when the user/player holds their score, it adds to their current score. If the score is greater than or equal to 100, then that player wins. If not, the player will be switched.

---
## Resetting the Game

We're going to implement the functionality of resetting the game at any time when the "New Game" button has been clicked to reset everything (scores and current scores).
* Resetting the conditions of the game
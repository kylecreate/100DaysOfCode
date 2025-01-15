---
tags:
    - learning-notes
    - code-for-dummies
    - JavaScript
obsidianUIMode: preview
---
> "O, call back yesterday, bid time return"
> -- Earl of Salisbury, Richard II

Callbacks and closures are two of the most useful and used techniques within JavaScript. With this chapter, you'll learn about how and way to pass functions as arguments to other functions within your code.

## What are Callbacks?
<strong><span style="color: yellow">REMEMBER ❗</span></strong>: JavaScript functions are objects and is the key to understanding many advanced topics, including callback functions.

Functions can be assigned to variables, be passed as arguments to other functions, and created within and returned from functions.

### Passing functions as arguments
Callback functions are a technique that's possible because of the fact that functions are objects.

Function objects contain a string with the code of a function. When calling a function by naming the function followed by `()`, you're telling the function to execute that code. Without them, the code won't execute.

An example coded below of a callback function using the `addEventListener` method...
```JS file:callbackFunction1.js fold
document.addEventListener('click', doSomething, false);
```
The method above takes an event (`click`) and a `function` object (`doSomething`) as arguments. The function doesn't execute right away. But, the `addEventListener` method will execute when the event occurs.

### Writing functions with callbacks
Coded below is an example function `doMath` that accepts a callback function as an argument.
```JS file:doMath1.js fold
function doMath(number1, number2, callback) {
	let result = callback(number1, number2);
	document.write('The result is: ' + result);
}
```
The above code is a generic function for returning the result of any math operation using two numeric values. The callback function that's been passed is specifying what actual operations will be done.

The call of the `doMath` function, pass two numbers, and then function as the third argument is coded below.
```JS file:doMath2.js fold
doMath(5, 2, function(number1, number2) {
	let calculation = number1 * number2 / 6;
	return calculation;
});
```

The coded example below is a webpage that contains the `doMath` function and then invokes it a few times with different callback functions.
```HTML file:differentFunctions.html fold
<html>
	<head>
		<title>Introducing the doMath function</title>
		<script>
			function doMath(number1, number2, callback) {
				let result = callback(number1, number2);
				document.getElementById('theResult').innerHTML +=
				'The result is: ' + result + `<br>`;
			}

			document.addEventListener(
				`DOMContentLoaded`,
				function () {
					doMath(5, 2, function (number1, number2) {
						let calculation = number1 * number2;
						return calculation;
					});

					doMath(10, 3, function (number1, number2) {
						let calculation = number1 / number2;
						return calculation;
					});

					doMath(81, 9, function (number1, number2) {
						let calculation = number1 % number2;
						return calculation;
					});
				},
				false
			);
		</script>
	</head>
	<body>
		<h1>Do the Math</h1>
		<div id="theResult"></div>
	</body>
</html>
```

### Using named callback functions
From the examples above, the callback functions were all written as anonymous functions. It's possible to define named functions and then pass the name of a function as a callback function.

<strong><span style="color: yellow">REMEMBER ❗</span></strong>: Anonymous functions are functions that you can create without giving them names!

Using named functions as callbacks reduces the visual code clutter. A coded example below shows how to use a named function as a callback. There's also two improvements to the code.
1. A test was added to the `doMath` function to make sure the `callback` argument is a function.
2. The code prints the callback function before displaying the result.
```HTML file:differentFunctions-v2.html fold
<html>
	<head>
		<title>Introducing the doMath function</title>
		<script>
			function doMath(number1, number2, callback) {
				if (typeof callback === 'function') {
					let result = callback (number1, number2);
					document.getElementById('theResult').innerHTML +=
						callback.toString() +
						'<br><br>The result is: ' +
						result +
						'<br><br>';
				}
			}

			function multiplyThem(number1, number2) {
				let calculation = number1 * number2;
				return calculation;
			}

			function divideThem(number1, number2) {
				let calculation = number1 / number2;
				return calculation;
			}

			function modThem(number1, number2) {
				let calculation = number1 % number2;
				return calculation;
			}

			document.addEventListener(
				`DOMContentLoaded`,
				function () {
					doMath(5, 2, multiplyThem);
					doMath(10, 3, divideThem);
					doMath(81, 9, modThem);
				},
				false
			);
		</script>
	</head>
	<body>
		<h1>Do the Math</h1>
		<div id="theResult"></div>
	</body>
</html>
```

Using named functions for callbacks gives two advantages over anonymous functions
1. Makes your code easier to read and less cluttered
2. Named functions are multipurpose and can be used on their own or as a separate callback.

## Understanding Closures
A *closure* is the local variable for a function being kept alive after the function has been returned.

The coded example below has an inner function defined without an outer function. When that outer function returns a reference to the inner function, it's returned reference can still access the local data from the other function. The `greetVisitor` function returns a function that is created within it called `sayWelcome`. The return statement doesn't using `()` because you don't want to return that value, but code the actual function.
```JS file:functionUsingFunction.js fold
function greetVisitor(phrase) {
	let welcome = phrase + '. Great to see you!';
	let sayWelcome = function() {
		alert(welcome);
	};
	return sayWelcome;
}

let personalGreeting = greetVisitor('Hola Amiga');
personGreeting(); // alerts "Hola Amiga. Great to see you!"
```

The useful thing about the coded example above, is that is uses the `greetVisitor` function to make a new function called `personalGreeting`. This can still access the variables from within the original function.

Usually when a function has finished executing, the local variables are inaccessible. But, by returning a function reference (in this case, `sayWelcome`), the `greetVisitor` function's internal data becomes accessible to everything outside.

<strong><span style="color: yellow">TIP 💡</span></strong>: The key to understanding closures are to understand variable scopes within JavaScript and to know the different between executing a function and function referencing. By assigning the return value of the `greetVisitor` function to the `personalGreeting` function, the program stores the code of `sayWelcome` function. This can be tested by using a `toString` method.
```JS file:toStringMethod.js fold
personalGreeting.toString();
```

In the next example below, a new closure is created using a different argument from the `greetVisitor` function. Even though calling that function changes the value of the `welcome` variable, the result of calling that first function remains the same.
```HTML file:secretReferences.html fold
<html>
	<head>
		<title>Using Closures</title>
		<script>
			function greetVisitor(phrase) {
			let welcome = phrase + ". Great to see you!<br><br>"; // Local variable
			let sayWelcome = function() {
			document.getElementById("greeting").innerHTML += welcome;
			}

		return sayWelcome;
		}

		// Wait until document is loaded
		document.addEventListener('DOMContentLoaded', function() {

		// Make a function
		let personalGreeting = greetVisitor("Hola Amiga");

		// Make another function
		let anotherGreeting = greetVisitor("Howdy, Friend");

		// Look at code of the first function
		document.getElementById("greeting").innerHTML +=
		"personalGreeting.toString() <br>" + personalGreeting.toString() + "<br>";
		// Run first function
		personalGreeting(); // alerts "Hola Amiga. Great to see you!"

		// Look at code of 2nd function
		document.getElementById("greeting").innerHTML +=
		"anotherGreeting.toString() <br>" + anotherGreeting.toString() + "<br>";

		// Run 2nd function
		anotherGreeting(); // alerts "Howdy, Friend. Great to see you!"

		// Check first function
		personalGreeting(); // alerts "Hola Amiga. Great to see you!"

		// finish addEventListener method
		}, false);
		</script>
	</head>
	<body>
		<p id="greeting"</p>
	</body>
</html>
```

<strong><span style="color: yellow">TIP 💡</span></strong>: Closures are not hard to understand after understanding concepts and have a need for them. If you still don't feel comfortable with them, that's fine. Once you understand them, they can be quite useful and make you a better programmer.

## Using Closures
A closure is like keeping a copy of local variables of a function as when they were created.

Within programming, closures are frequently used to eliminate the duplication of effort within a program or by holding values that need to be reused.

Another use for them is to create customized versions of functions for certain use cases.

<strong><span style="color: yellow">TECHNICAL 🤓</span></strong>: When a function's purpose is to create other functions, it's known as a *function factory*.

In the last coded example below, closures are being used to create functions with error messages specific to different problems that could occur. All error messages get created by using the same function.

```HTML file:functionCreatingFunctions.html fold
<html>
	<head>
	<title>function factory</title>
	<script>
		function createMessageAlert(theMessage){
			return function() {
				alert (theMessage);
			}
		}

		let badEmailError = createMessageAlert("Unknown email address!");
		let wrongPasswordError = createMessageAlert("That's not your password!");

		window.addEventListener('load', loader, false);
		function loader(){
		document.login.yourEmail.addEventListener('change',badEmailError);
document.login.yourPassword.addEventListener('change',wrongPasswordError);
		}
		</script>
	</head>
	<body>
		<form name="login" id="loginform">
			<p>
				<label>Enter Your Email Address:
					<input type="text" name="yourEmail">
				</label>
			</p>
			<p>
				<label>Enter Your Password:
					<input type="text" name="yourPassword">
				</label>
		</p>
		<button>Submit</button>
	</body>
</html
```

The key to understanding the above example is by using the function factory...
```JS file:functionFactory.js fold
function createMessageAlert(theMessage) {
	return function() {
		alert(theMessage);
	}
}
```

To use the function factory, you need to assign the return value to a variable
```JS file:returnValueVariable.js fold
let badEmailError = createMessageAlert("Unknown email address!");
```

The next statement creates a closure that can be used anywhere else in the program by running `badEmailError` as a function in the coded example's event handler.
```JS file:badEmailErrorStatement.js fold
document.login.yourEmail.addEventListener('change', badEmailError);
```
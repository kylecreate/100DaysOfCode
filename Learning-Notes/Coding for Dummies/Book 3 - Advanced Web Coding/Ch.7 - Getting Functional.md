---
tags:
  - ReadingNotes
  - WebDev
---
> *"I write as a function. Without it I would fall ill and die. It’s much a part of one*
*as the liver or intestine, and just about as glamorous."*
> -- Charles Bukowski

Functions help reduce code repetition by turning frequently used bits of code into reusable parts. Within the chapter, you'll learn to write some functions and use them to make certain tasks easy and fun.

# <u>Understanding the Function of Functions</u>
<u>Functions</u> are mini programs within your programs and serve to handle tasks within your main program that might need to be required multiple times within different parts of the program. They're a fundamental part of programming in JavaScript have a lot of rules/powers. No need to memorize each one, that will come with time.
```JS file:easy-example-function fold
function addZ(aString) {
	aString += "z";
	return aString;
}
addZ("I have JavaScript skill");
// "I have JavaScript skillz"
```

# <u>Using Function Terminology</u>
There's a number of words that programmers use that are important to understand when referring to functions.

## Defining a Function
When a function appears, it doesn't run automatically. It's just been created and made for use later on, called *defining a function*.
**<span style="color: yellow">REMEMBER</span>**: You only need to define a function once in a program or on a web page.
```JS file:defining-a-function fold
function myFunction(){
};
```

## Function Head
The *function head* is the part of the function definition that includes the function keyword, the function name, and the parentheses.
```JS file:function-head fold
function myFunction();
```

## Function Body
The body of a function (aka *function body*) is made up of the statements between the curly braces of the function.
```JS file:function-body fold
{
	// function body
}
```

## Calling a Function
When you use a function, it’s called *calling* the function which causes the statements in the function to be executed.
```JS file:calling-function
myFunction();
```

## Defining parameters and passing arguements
Names that you give to pieces of data that are provided to a function when it’s called are called *parameters*. The values that you provide to functions are called *arguments*. When a function is called with arguments inside of the parentheses, it's referred to as *passing* the arguments into the function.
```JS file:parameters-and-arguments
// Defining a parameter
function myFunction(parameters) {

// Calling a function
myFunction(myArgument);
```

## Returning a value
Functions can also send back values when they've completed running. When a function does send back something, it's called *returning a value* which is used with the `return` keyword.
```JS file:returning-a-value fold
return myValue;
```

# <u>The Benefits of Using Functions</u>
With the below examples, it works great and does exactly what a function is supposed to do using a `for...in` loop.
```JS file:adding-numbers-function-example fold
let myNumbers = [2,4,2,7];
let total = 0;
for (oneNumber in myNumbers){
	total = total + myNumbers[oneNumber];
}
document.write(total);

// Above example turning into a function and then uses that function to find the sums of the elements in several different arrays.
function addNumbers(numbersToAdd) {
	let sum = 0;
	for (oneNumber in numbersToAdd) {
		sum = sum + numbersToAdd[oneNumber];
	}
	return sum;
}

let myNumbers = [2,4,2,7];
let myNumbers2 = [3333,222,111];
let myNumbers3 = [777,555,777,555];
let sum1 = addNumbers(myNumbers);
let sum2 = addNumbers(myNumbers2);
let sum3 = addNumbers(myNumbers3);
document.write(sum1 + "<br>");
document.write(sum2 + "<br>");
document.write(sum3 + "<br>");
```

### Documenting JavaScript with JSDoc
It’s a good practice to always document your JavaScript code using a standard system. The most widely used is JavaScript documentation system (or JSDoc).
* A simple markup language that can be inserted inside of JavaScript files.
```JS file:example-of-JSDoc fold
/**
 * Solves equations of the form a * x = b
 * @example &lt;caption>Example usage of method1.&lt;/caption>
 * // returns 2
 * globalNS.method1(5, 10);
 * @returns {Number} Returns the value of x for the equation.
 */
```
By commenting your functions using this format, you not only make your programs much easier to
read, you also can use these comments to automatically generate documentation for your programs. Read more at [JSDoc.app](https://jsdoc.app/)

Most popular tags of JSDoc

| **JSDoc Tag**  | **Explanation**                                                                         |
| :------------- | :-------------------------------------------------------------------------------------- |
| `@author`      | Programmer’s name.                                                                      |
| `@constructor` | Indicates that a function is a constructor.                                             |
| `@deprecated`  | Indicates the method is deprecated.                                                     |
| `@exeception`  | Describes an exception thrown by a method; synonymous with `@throws`.                   |
| `@exports`     | Specifies a member that is exported by the module                                       |
| `@param`       | Describes a method parameter.                                                           |
| `@private`     | Indicates a member is private.                                                          |
| `@return`      | Describes a return value. Synonymous with `@returns`.                                   |
| `@returns`     | Describes a return value. Synonymous with `@return`.                                    |
| `@see`         | Records an association to another object.                                               |
| `@this`        | Specifies the types of the object to which the keyword `this` refers within a function. |
| `@throws`      | Describes an exception thrown by a method.                                              |
| `@version`     | Indicates the version number of a library                                               |
Functions are a great time, work, and space saver while a usual function may take longer than writing JavaScript code outside of a function. It's better to be organized and save yourself some headaches.

# <u>Writing Functions</u>
A function declaration consists of the following items...
1. Function keyword
2. Name of the function
3. Parentheses (*can contain more than one parameter*)
4. Pair of curly brackets containing statements
Sometimes, a function’s purpose could be to write a single message to web page. For example, writing out the current date in the browser window.
```JS file:writing-the-date-example
function getTheDate() {
	let rightNow = new Date();
	document.write(rightNow.toDateString());
}
// Returns undefined which is a value til you see the webpage change to the date
```

# <u>Returning Values</u>
From the example above, we created a function that just prints the string to the browser window. After the `document.write` executes, there aren't any more statements to run which will exit the function and program.
Most functions return a value (not including `undefined`) after the work is done. This allows you to use the value for the rest of the program. Below is an example of a function that returns a value printed to the console.
```JS file:returning-value-from-function fold
function getHello() {
	return "Hello!";
}
let helloText = getHello();
console.log(helloText);
```
The `return` in the statement is generally the last statement written in a function, when that executes, the function exits and stops running. A `return` statement can send any kind of JS value outside of the function or return the value of a variable, expression, array, object, or another function.
An example of a function that returns the result of a expression
```JS file:result-of-expression fold
function getCircumference(){
	let radius = 12;
	return 2 * Math.PI * radius;
}
console.log (getCircumference());
// 75.39822368615503
```

# <u>Passing and Using Arguments</u>
For functions to be able to do the same thing with a different input, they need a way for programmers to give them an input.

**<span style="color: yellow">REMEMBER</span>**: The difference between parameters and arguments can be confusing, how it works...
* Parameters are the names you specify in the **function definition**.
* Arguments are the **values you pass** to the function. They take on the names of the parameters when they are passed.
```JS file:example-of-two-parameters fold
function myTacos(meat, produce) {
...
}

// Arguments
myTacos("beef", "onions");
```

When you call the function in the above example, you include data (*arguments*) in the places where the function definition has parameters. The values passed to the function will become the values the local variables inside of the function and will be given the names of the function’s parameters.
An example of the `myTacos` function to print out the values of the two arguments to the console...
```JS file:arguments-inside-function-example fold
function myTacos(meat,produce){
	console.log(meat); // writes "beef"
	console.log(produce); // writes "onions"
}
myTacos("beef","onions");
```

**<span style="color: yellow">TECHNICAL</span>**: You can specify up to 255 parameters in a function definition. However, it's highly unusual and not practical to do that many. If you find that you need a lot of parameters, you should think about whether there’s a better way to do it.

## Passing arguments by value
If you use a variable with one of the primitive data types to pass your argument, the argument passes *by value*.
* The new variable that was created inside the function is totally separate from the variable used to pass the argument, and no matter what happens after that value gets into the function, the variable outside of the function won’t change.
In the example below, you'll see several variables were created, given values, and passed into a function. The parameters of the function have the same names as the variables used to pass the arguments. Even though the values of the variables created inside the function get changed, the values of the original variables will remain the same.
```JS file:arguments-passed-by-value-example fold
function addToMyNumbers(number1,number2){
	number1++;
	number2++;
	console.log("number 1: " + number1); //3
	console.log("number 2: " + number2); // 12
}
let number1 = 3;
let number2 = 12;
addToMyNumbers(number1,number2); // pass the arguments
console.log("original number1: " + number1); // 4
console.log("original number2: " + number2); // 13
```

## Passing arguments by reference
JavaScript objects are passed by reference as primitive variables are passed to functions by values. Meaning that when you pass an object as an argument to a function, any changes to that object within the function created will also change the value outside of that function.

## Calling a function without all the arguments
You don’t always need to call a function with the same number of parameters as are listed in the function definition. A function definition contains three parameters, but if you call it with only two, that third parameter will create a variable with a value of `undefined` in the function.

## Setting default parameter values
If you want arguments to be set to something other than `undefined`, then you can set default values. A way to do that is to test the arguments inside of the function created with the set default values if the data type of the argument is undefined.
In the below example, the function created takes one parameter. Inside that function, a test is done to check if the argument is `undefined` or not. If so, it will be set to a default value. Included is an example from pre-ES6 and ES6.
```JS file:default-argument-values fold
// Before ES6
function welcome(yourName){
	if (typeof yourName === 'undefined'){
		yourName = "friend";
}

// With ES6
function welcome(yourName = "friend") {
	document.write("Hello," + yourName);
}
```

## Calling a function with more arguments than parameters
If you call a function with more arguments than the number of parameters, local variables won’t be created for the additional arguments because the created function has no way of knowing what to call them. To retrieve the values of arguments that don't have a matching parameter, you can use the `arguments` object.

## Getting into arguments with the `arguments` object
If/When you don’t know how many arguments will be passed into a function, use the `arguments` object which is built in to functions by JavaScript to retrieve all of the arguments to make use of them.
This object contains an array of all the arguments passed to the created function and looping into the array (using the `for` loop or `for...in` loop).
The example below uses the `argument` object to write a welcome message to someone with two middle names and someone with one middle name.
```JS file:arguments-object-example
function flexibleWelcome() {
	let welcome = 'Welcome,';
	for (i = 0; i < arguments.length; i++) {
		welcome = welcome + arguments[i] + '';
	}
	return welcome;
}
document.write(
	flexibleWelcome('John', 'Jacob', 'Jingleheimer', 'Schmidt') + '<br>');
document.write(
	flexibleWelcome('Christopher', 'James', 'Minnick') + '<br>');
```

# <u>Understanding Function Scope</u>
Variables that are created inside a function by passing arguments are only available within that function is called a *function scope*.
* Variables that are created inside of a function are destroyed when the function exits.
* If the variable that is created inside of a function without `var`, `let`, or `const`, it becomes a global variable and can be changed/accessed anywhere in the program.
<span style="color: yellow">WARNING</span>: Accidentally creating a global variable <u>is the source</u> of many JavaScript bugs and errors. It’s <u>recommended that you always properly scope variables</u> and **NEVER** create a global variable unless it’s absolutely necessary.

# <u>Creating Anonymous Functions</u>
The function name part of the function head isn’t required, you can create them without names. *Anonymous functions* can be assigned to variables when they are created, which gives the same capabilities as using a name within the function head.
```JS file:anon-function fold
let doTheThing = function(thingToDo) {
	document.write("I will do this thing: " + thingToDo);
}
```

## The differences between anonymous and named functions
There are differences between creating a named function and assigning an anonymous function to a variable.
1. An <u>anonymous function</u> assigned to a variable only exists and can only be called after the program executes the assignment.
2. Between <u>named functions</u> and <u>anonymous functions</u> assigned to variables is that you can change the value of a variable and assign a different function to it at any point.

## Arrow Functions
Another way to write anonymous functions is as *arrow functions*.
* Arrow functions get their name from the combination of symbols used to write them
	* Instead of writing out `function`, you use `=>` (also known as a 'fat arrow') between the parameter list and function body.
	* They're always anonymous function and can be passed as arguments to other functions or assigned to other variables.
	* They're more compact than using the `function` keyword
```JS file:arrow-function-example
let square = (num) => {
	return num * num;
}
```

Arrow functions have special rules and shortcuts that can make them even more compact than the example from above.
* If a function only has one parameter, you don’t need to use the parentheses around the parameter list.
* If a function doesn’t do anything but return data, you don’t need to include the `return` keyword.
* If you don’t include the `return` keyword in the function, you also don’t include the curly brackets around the function body.
```JS file:rewriting-above-example
let square = num => num * num;
```

# <u>Doing it again with Recursion</u>
You can call functions from outside of the function or from within other functions or from within itself which is called *recursion*.
* You can use <u>recursions</u> in many of the same cases where you would use a loop, except that it repeats the statements within a function.
```JS file:flawed-recursion-function fold
function squareItUp(startingNumber) {
	var square = startingNumber * startingNumber;
	console.log(square);
	squareItUp(square);
}
// This function NEVER ends...
```

Running the above function will probably crash your browser, if not your computer. No damage will be done to either, but just make sure it doesn't happen.
You can improve the function from above by using what’s called a *base case*.
* The condition under which a recursive function’s job is done and it should halt. **Every recursive function must have a base case!**
```JS file:a-working-recursive-function fold
function squareItUp(startingNumber) {
	square = startingNumber * startingNumber;

	if (square > 1000000) {
		console.log(square);
	} else {
		squareItUp(square);
	}
}
```

There's still a problem with the above example. What would happen if someone passed either a 0 or -1? It would create an infinite loop. With that, we need to create a termination condition to make sure that the argument isn't less than or equal to 1.
```JS fixed-recursive-function fold
function squareItUp(startingNumber) {
	// Termination conditions, invalid input
	if (typeof startingNumber != 'number' || startingNumber - Number <= 1) {
		return -1; // exit the function
	}
	square = startingNumber * startingNumber;
	// Base condition
	if (square > 1000000) {
		console.log(square); // Print the final value
	} else {
	// If the base condition isn't met, do it again.
	squareItUp(square);
	}
}
```

# <u>Functions within Functions</u>
Functions can actually be declared within functions. The below example demonstrates how this
technique works and affects the scope of variables created within the created functions.
```JS file:function-within-function fold
function turnIntoAMartian(myName) {
	function recallName(myName) {
		let martianName = myName + ' Martian';
	}
	recallName(myName);
	console.log(martianName);
}

turnIntoAMartian("Glenn"); // martianName is not defined
```

The above example shows how nesting a function within a function creates another layer of scope. However, variables created in the inner function aren’t directly accessible to the containing function. A return statement is needed to get their values, which is shown in the below example.
```JS file:returning-values-from-function fold
function turnIntoAMartian(myName) {
	function recallName(myName) {
		let martianName = myName + ' Martian';
		return martianName;
	}
	let martianName = recallName(myName);
	console.log(martianName);
}

turnIntoAMartian("Glenn"); // "Glenn Martian"
```
---
tags:
  - ReadingNotes
  - WebDev
---
> "It's not hard to make decisions when you know what your values are."
> — Roy Disney

There comes a time (*many times, actually*) in a program where you need a choice to be made or where you need to alter the straight-ahead logic of a program to repeat statements multiple times with different values.
## Branching Out
*Looping* and *branching statements* are called control statements because they control the order in which JavaScript statements are run.
- You can use* branching statements* to create different paths for the execution of JavaScript code depending on the conditional logic.
- *Loops* are the simplest way to group JavaScript statements
together in a program.

The logic of a JavaScript program often comes to a point where a choice must be made that will make all the difference.
### `if…else` Statements
The `if` and `else` statements work together to evaluate a logical expressions and run different statements based on the result.
- `if` statements are often used by themselves.
- `else` statements must always be used in conjunction with an `if` statement.
```JS fold
// Basic if statement
if (condition) {
	...
}
```

The condition mentioned is any expression that evaluates to a Boolean (true or false) value.
- If the result is *true*, the statement between the brackets is executed.
- If the result is *false*, the statement between the brackets will just be skipped.

The `else` statement comes in when you want to do something should the condition evaluate to *false*.
```JS fold
let age = 19;
if (age < 21) {
	document.write ("You are under the legal drinking age in the U.S.");
} else {
	document.write("What'll it be?");
}
```

Other programming languages have a combination keyword statement called the `elseif` statement, which can be used multiple times in an `if…else` statement until a true value occurs. JavaScript doesn't have the `elseif` keyword.
- You can get a similar functionality out of it by using if and else together with a space between them.
```JS fold
if (time < 12) {
	document.write ("Good Morning!");
} else if (time < 17) {
	document.write ("Good Afternoon!");
} else if (time < 20) {
	document.write ("Good Evening!");
} else {
	document.write ("Good Night!");
}
```

### Switch Statements
The switch statement chooses between different statements to execute based on the possible values of a single expression.
In English, we would say…
- "In the case that we are expecting six guests, order three pizzas. In the case that we are expecting 12 guests, order six pizzas. In the case that we’re expecting more than 20 guests, freak out.”

What a switch statement looks like…
```JS fold
switch (expression) {
	case value1:
		// Statements Here
		break;
	case value2:
		// Statements here
		break;
	case value3:
		// Statements here
		break;
	default:
		// Statements here
	break;
}
```

- The break statement comes after the statements associated with each case. This will tell the switch statement to stop and exit the statement as it's been completed.
    - Without the break, the statement would run to the next clause even if the expression meets the conditions of the case.

**WARNING**: Forgetting a *break* statement within a switch can cause big problems, so be sure to always use it.
If no match is found in any of the *case* clauses, the *switch* statement will look for a *default* clause and execute the statement it contains.
**TECHNICAL**: The exception to the rule that you should always use a *break* statement between *case* clauses is the *default* clause.
- The *default* clause is the last statement in your *switch* (*which it should be*), you can safely omit the break after it because the program will break out of the switch after the last statement anyway.
```JS fold
let languagePreference = "Spanish";
switch (languagePreference) {
	case "English":
		console.log("Hello!");
		break;
	case "Spanish":
		console.log("Hola!");
		break;
	case "German":
		console.log("Guten Tag!");
		break;
	case "French":
		console.log("Bon Jour!");
		break;
	default:
		console.log("I'm sorry, I don't speak " + languagePreference + "!");
```

## Here We Go: Loop De Loop
Loops execute the same statement multiple times, there's different types of loops.
- `for`
- `for…in`
- `do…while`
- `while`
### `for` loops
The *for* statement creates a loop using three expressions:
1. **Initialization**: The initial value of a variable, typically a counter.
2. **Condition**: A Boolean expression to be evaluated with each iteration of the loop.
3. Final Expression: An expression to be evaluated after each loop iteration.

It's not required to use all 3 expressions in a `for` loop, but they're always included.
```JS fold
for (let x = 1; x < 10; x++) {
	console.log(x);
}
```

How the above example works…
1. A new variable (in this case *x*), is initiated with the value of `1`.
2. A test is performed to determine whether x is less than 10.
*(If so, the statement inside of the loop are executed. If not, the value of `x` is incremented using the operator `++`.)*
3. The test is done again to determine whether `x` is less than 10.*
(If so, the statements inside the loop are executed*)
4. The test repeats until the condition expression no longer evaluates to `true`.

### Looping through an array
You can use `for` loops to list the contents of an array by testing the value of the counter against the value of the *length *property of the array.
- A reminder that arrays are zero-indexed (meaning they start from 0 instead of 1)
```JS fold
let areaCodes = ["770", "404", "718", "202", "901", "305", "312", "313", "215", "803"];

for (x = 0; x < areaCodes.length - 1; x++) {
	document.write("Different Area Code: " + areaCodes[x] + "<br>");
}
```

### `for…in` Loops
The `for…in` statements loop through the properties in an object. You can also use a `for…in` statement to loop through the values of an array.
- It doesn’t care about the order of properties or elements that it’s looping through.
- You’re better off using a standard for loop to loop through array elements.

Web browsers have a set of built-in objects that programmers can use to control the function of the browser. The most basic of these is the *Document* object.
You can also use a `for…in` loop to output the values that are in the properties of the object, rather than just the property name.
```JS fold
for (var prop in document) {
	document.write(prop + '<br>');
}

for (var prop in document) {
	document.write(prop + ': ' + document[prop] + '<br>');
}
```

### `while` Loops
The `while` statement creates a loop that runs as long as a condition evaluates to true.
```JS fold
let guessedWord = prompt('What word am I thinking of?');
while (guessedWord != 'sandwich') {
// as long as the guessed word is not sandwich
	guessedWord = prompt("No. That's not it. Try again.");
}
alert("Congratulations! That's exactly right!"); // do this after exiting the loop
```

### `do…while` Loops
This *loop* works in much the same way as the while loop, except that it puts the statements before the expression to test against.
```JS fold
let i = 0;
	do {
		i++;
		document.write(i + '<br>');
	} while (i < 10);
}
```

### Break and Continue Statements
You can use `break` and `continue` to interrupt the execution of a loop.
- The *break* statement was shown earlier in the context of a *switch* statement, where it serves to break out of the switch after a successful match.

In a loop, *break* does much the same thing. It causes the program to immediately exit the loop, no matter the conditions.
```JS fold
let guessedWord = prompt('What word am I thinking of?');
while (guessedWord != 'sandwich') {
	if (guessedWord == '') {
		break;
	} // exit the loop right away if user doesn't enter a value
	guessedWord = prompt("No. That's not it. Try again.");
}
alert("Congratulations! That's exactly right!");
```

The *continue statement* in the example causes the current iteration of the loop to stop and tells the program to start up again with the next iteration of the loop, skipping the statements that come after the *continue* statement.
```JS fold
for (let i = 0; i <= 20; i++){
	if (i%2 != 0){
		continue;
	}
	document.write (i + " is an even number.<br>");
}
```

When used in this way, *continue* can replace the functionality of an *else statement*.

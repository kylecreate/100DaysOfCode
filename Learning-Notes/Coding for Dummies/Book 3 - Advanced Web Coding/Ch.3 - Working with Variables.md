---
tags:
    - learning-notes
    - code-for-dummies
    - JavaScript
obsidianUIMode: preview
---
> “Beauty is variable, ugliness is constant.”
> — Douglas Horton (1981 - 1968)

In this chapter, we're going to learn how to create variables, fill them with values, use functions to find out what type of data is in your variables, convert between different data types, and manipulate the data in your variables.

## Understanding Variables
Variables are representative names in a program.
- Similar to how `x` may stand for some value in algebra, or `x` marks the spot to where a treasure may be. They're used to represent something else.

Think about variables as containers that contain data. You can give them names and later recall them to change the data in a variable by using its name that was given.
Without variables, every computer program would have only one purpose.
- *An example of a one-line program that doesn't use a single variable*
```JS fold
alert(3 + 7); // Pops up 10
```

The purpose of the alert is to add together the numbers `3` and `7` and to print out the result in a browser popup window.
While using variables, you can make a general purpose program that can add together any two numbers and print out the result, for example…
```JS fold
let firstNumber = 3;
let secondNumber = 7;
let total = Number(firstNumber) +
			Number(secondNumber);
alert (total); // Pops up 10
```

Another example of taking it a step further for adding two completely random numbers (*Need to create a separate `index.html` and `script.js` file to make this run properly.*)
```JS fold
let firstNumber = prompt("Enter the first number");
let secondNumber = prompt("Enter the second number");
let total = Number(firstNumber) + Number(secondNumber);
alert (total); //Adds two numbers together that are chosen
```

## Initializing Variables
*Initializing a variable* is used to describe the process of first creating a variable in a program and then giving it an initial value.
Variables can be initialized in three ways…
1. Using the `var` keyword - *(Not used at all since ES6/ES2015*)
    - `var myName;`
    - A variable created using the `var` keyword will have an initial value of undefined unless you give it a value when you create it, such as…
        - `var myName = "Chris";`
    - You can also not use `var` as a keyword, and just leave it out.
    - When creating a variable without the `var` keyword, it becomes a global variable* (see next section)* which should be avoided*.*
2. Using the `let` keyword - (*Used frequently since ES6/ES2015*)
    - `let myName = "Chris";`
    - Similar to the `var` keyword, if you create a variable without assigning a value, it will have a default value of `undefined` .
3. Using the `const` keyword - (*Used frequently since ES6/ES2015*)
    - This keyword creates a constant that when created, it can't be assigned a new value.
    - They're great for making sure the program you're creating won't change something that shouldn't be changed (IE: the value of PI or something in a recipe).

**TECHNICAL**: The quotes around the value in the previous examples are indicating that the value should be treated as text rather than a number, a JavaScript keyword, or some other variable.
### When is Equal not Equal?
With the English language, it's common and correct to read a statement containing a `=` as `"var myName equals Chris"` , which isn't correct.
Using the following example…
- `var myName = 'Chris';`
The character that acts as a equal sign between the variable and value may look like an equal sign and is produced that way. However, this is called an **assignment operator**.
- The assignment operator sets the thing to the left of it equal to the thing to the right.
    - `var myName = 'Chris';`
- "Equals" compares the value on the left to the right and determines whether or not they're equal to each other (*JavaScript writes that as `===`  which will be covered in the future*).

## Understanding Global and Local Scope

How and where you declare a variable determines how and where the program you're creating can make use of that variable, which is called variable scope.
There are 3 types of variable scopes…
1. Global Scoped Variables: These can be used anywhere inside of a program.
2. Function Scoped Variables: These are variables that you can create using the `var` keyword inside a protected program called a function.
3. Block Scoped Variables: These are variables that can be created using either the `let` or `const` keyword. They can be used within the "block" when initialized. A black of code in JavaScript is created using the left and right curly bracket `{ }` .

**TIP**: Using block scoped variables is much preferable to using function scoped variables because it's limiting the scope of variables and reduces the change that you may overwrite the value of a variable inside another with a similar name.
You should always avoid creating a global scoped variable as it can create problems with your web application/webpage. It's better to use `let` or `const` .
## Naming Variables
Varaible names can have the following characters in them…
- Upper or Lower case letters
- Underscores (`_`)
- Dollar signs ($)

Although you can use an underscore or dollar sign to start a variable, **it’s best to begin with a letter**. Otherwise, your code will look hard to read since you're just starting out.
### Guidelines for creating good Variable Names
1. Do not use names that are too short! Simple one letter names or nonsensical names are not a good option when naming variables.
2. Use multiword names to be as precise as possible.
3. In multiword names, always put adjectives to the left, as in `let greenPython;`.

There are two ways to join words to create a name: camelCase and under\_score.
- Example of camelCase: `userFirstName`
- Example of underscore: `user\_FirstName`

Some words cannot be used as variable names as there's a list of words that JavaScript already has.
- [Reserved Keywords in JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#reserved_words) - MDN

**WARNING**: Always remember that JavaScript is case-sensitive. A variable named `myname` is not the same variable as `Myname` or `myName`.
A longer name that accurately represents the variable is more useful than a shorter name that is vague.

## Creating Constants Using the `const` Keyword
Occasionally, the program your working on may have a need for variables that can’t be changed. For example…
```JS fold
const heightOfTheEmpireStateBuilding = 1454;
const speedOfLight = 299792458;
const numberOfProblems = 99;
const meanNumberofBooksReadIn2022 = 12;
```

Once you create a constant, its value cannot be changed during its lifetime (*which lasts as long as the script is running*).

## Working with Data Types
A variable’s data type is the kind of data the variable can hold and what operations can be done with the value of the variable.
- The number '10' used in a sentence is different from the number '10' being used in a math equation.

JavaScript is what’s called a loosely typed language.
- Loosely Typed: You don’t even need to tell JavaScript, (*or even know*), whether a variable you’re creating will hold a word, a paragraph, a number, or a different type of data. Also, it doesn’t distinguish between words and numbers.

There's 7 basic types of data
### **Number**
- Stored as 64-bit
- Floating point value
- Numbers can range from 5e-324 (*that’s -5 followed by 324 zeros*) to 1.7976931348623157e+308 (*move the decimal 308 spots*)
- When determining a number variable, you can compile it from the following elements
    - `var` , `let` ,`const` keyword
    - Name you gave the variable
    - The assignment opperator
    - A number (or equation that resolves to a number)
    - A semicolon

- JavaScript includes a built-in Number function for converting values to numbers.
- You can use the `parseInt` function to tell JavaScript to consider only the nonfractional part of the number (the integer), discarding everything after the decimal point.
- You can use `parseFloat` to specifically tell JavaScript to treat a number as a float.
- **WARNING**: Number variables must be declared without quotation marks. "10" *(string)* is not the same as 10 *(number)*.
    - "12" (the string) + 12 (the number), result is `"1212"`
```JS fold
// Number Type Examples
let numberOfDucks = 4;
var populationOfSpan = 47200000;
const howManyTacos = 8;

// Number Function Examples
Number("42") // returns 42
Number("eggs") // returns NaN - Not a Number
Number(true) // returns 1
Number(false) // returns 0

// parseInt Example
parseInt(100.33); // returns 100

// parseFloat Examples
parseFloat("10"); // returns 10
parseFloat(100.00); // returns 100.00
parseFloat("10"); // returns 10
```
### bigInt Data Type
This data type doesn't have an upper limit. If you have a large number than the maximum safe integer (007199254740991), then use bigInt.
- Just add a *n* to the end of a number
```JS fold
let reallyBigNumber = 9007199254740992n;
```
### String Data Type
Strings can be made up of any characters
- Letters
- Numbers
- Punctuation (*commas and periods*)
- Special characters that can be written using the backslash followed by a character

Some characters, such as quotes, have special meaning in JavaScript or require a special combination of characters.
**JavaScript Special Characters**

| Code | Inputs          |
| :--- | :-------------- |
| ''   | Single Quote    |
| ""   | Double Quote    |
| \    | Backslash       |
| \n   | New Line        |
| \r   | Carriage Return |
| \t   | Tab             |
| \b   | Backspace       |
| \f   | Form Feed       |

You create a string variable by enclosing it in single or double quotes
```JS fold
let myString = "Hi, I'm a string.";
```

You can use single or double quotes, as long as the beginning and ending quotes surrounding the string match up.
**WARNING**: If you create a string and surround it with one type of quote, you can’t use that type of quote inside the string, or the JavaScript parser will think you mean to end the string and will generate an error.
### String Functions
JavaScript includes many helpful functions for working with and converting strings.
```JS fold
// charAt produces the character at a specified position
let watzThisString = 'JavaScript is Fun!';
console.log(watzThisString.charAt(3));
// return a

// concat combines one or more strings together
let watzThisString = 'JavaScript is Fun!';
console.log(watzThisString.concat(' We love JavaScript!'));
// return JavaScript is Fun! We love JavaScript!

// indexOf searchs and returns the position of the char mentioned
let watzThisString = 'JavaScript is Fun!';
console.log (watzThisString.indexOf('Fun');
// returns 14

// split splits the string into an array of substrings
let watzThisString = 'JavaScript is Fun!';
console.log (watzThisString.split('F'));
// returns ["JavaScript is ", "un!"]

// substr extracts a portion of a string beginning through a specified length
let watzThisString = 'JavaScript is Fun!';
console.log (watzThisString.substr(2,5));
// returns vaScr

// substring extracts characters within a string
let watzThisString = 'JavaScript is Fun!';
console.log (watzThisString.substring(2,5));
// returns vaS

// toLowerCase converts the string into lowercase letters
let watzThisString = 'JavaScript is Fun!';
console.log (watzThisString.toLowerCase());
// returns javascript is fun!

// toUpperCase converts the string into uppercase letters
let watzThisString = 'JavaScript is Fun!';
console.log (watzThisString.toUpperCase());
// returns JAVASCRIPT IS FUN!
```

### Boolean Data Type
Boolean variables store one of two possible values: either `true` or `false`.
**TECH STUFF**: The term *Boolean* is named after George Boole (1815–1864), who created an algebraic system of logic.
Boolean variables are often used for storing the results of comparisons.
```JS fold
let isItGreater = Boolean (3 > 20);
alert (isItGreater); // returns false

let areTheySame = Boolean ("tiger" === "Tiger");
alert (areTheySame); // returns false
```

The result of converting a value in JavaScript into a Boolean value using the
Boolean function depends on the value:
- False Values
    - NaN - *(Not a Number*)
    - Undefined
    - 0 *(number zero)*
    - -0
    - "" - *(empty string)*
    - `false`
- True Values
    - 74
    - "Eva"
    - "10"
    - "NaN" - *(Not a Number*)

**REMEMBER**: The number character "0" is not the same as the numeric value 0 (zero).
Boolean values are primarily used with conditional expressions. The example creates a variable and then tests the value using a if/then statement *(which will be learned about later)*
```JS fold
let b = true;
if (b == true) {
	alert ("It is true!");
	} else {
	alert ("It is false.");
}
```

**TIP**: Boolean values are written without quotes around them
- `let myVar = true`
- `let myVar = "true"` *(creates a string*)

### NaN Data Type
NaN *(or Not a Number)* is the result that you get when you try to do math with a string, or when a calculation fails or can’t be done.
- Example: An attempt to perform mathematical operations using strings that can’t be converted to numbers will produce NaN.

### Undefined Data Type
Even if you create a variable in JavaScript and don’t specifically give it a value it's considered `undefined`
### Symbol Data Type
This data type is used to create unique identifiers in JavaScript.
Even if two symbols appear to be identical and have the same name, JavaScript guarantees that they’ll be unique.
- A test to see what happens
```JS fold
let id1 = Symbol("id");
let id2 = Symbol("id");
alert(id1 === id2);
// Alert window with the boolean of False will be displayed
```
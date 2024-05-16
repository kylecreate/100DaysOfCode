---
tags:
  - WebDev
---
## Section Intro

In this section, we'll be learning the very basics of the JavaScript language.
- Variables
- Data Types
- Operators
- If..else statements
- More!
Need to focus first on the language fundamentals before creating pretty UI
---
## Hello World!

Going to write our first line of code in the Chrome/Firefox developer console/tools.
*Shows how to open and get the the console in Chrome and Firefox*
The developer console tool allows us to write and test JS code, which is useful for seeing if the code has any errors or to test something else.
You can hit the up or down arrow to see a previous command that's been used before.
```JS fold
//Creates a pop up in the browser that says Hello World!
alert("Hello World!");

// If JS is amazing, then create an alert with the following sentence
let js = 'amazing';
if (js === 'amazing') alert('JavaScript is Fun!');

// Nothing happens since JS is now considered boring
js = 'boring'
if (js === 'amazing') alert('JavaScript is Fun!');

// Can also do simple math problems
40+8+23-10
61
```
 ---
## A Brief introduction to JavaScript
### What is JavaScript?
JavaScript is a high-level, object-oriented, multi-paradigm programming language. 🤯
- Programming Language: A tool that allows us to write code to instruct the computer to do something.
- High-level Language: We don't have to think of complex stuff such as the computer memory that we don't have to worry about. *Makes it easier to write and learn how to use.*
- Object-Oriented: The language is mostly based on the concept of objects for storing most kinds of data.
- Multi-paradigm: So flexible and versatile, you can use all sorts of programming styles to structure the code.

### The Role of JavaScript in Web Development
- HTML, CSS, and JavaScript are the 3 core technologies of the web today. They work together to create dynamic and beautiful websites or applications.
    - HTML is responsible for the content of the web page or application. *(Text, images, buttons, and content)*
        - Nouns: `<p></p>` - *means "paragraph"*
    - CSS is responsible for the presentation or styling of that content. (*Styling and laying out elements on a page*)
        - Adjectives: `p {color: red};` - means to make the paragraph text red
    - JavaScript allows programmers to add dynamic and interactive effects to their web pages or applications. Can also use it to manipulate the content, load data from servers, or build entire applications in the browser.
        - Verbs: `p.hide();` - means *"hide the paragraph"*

### Examples of Dynamic Effects / Web Application
*Showing an example of a profile page being opened from Twitter*
- Rotating loading spinners on the profile and sidebar where information usually is.
- After the content is loaded, the spinners go away and the content is shown on the website/web application.
- Showing the tweet box when you click on the "Tweet" button, and hides it when you click outside of it
- Shows user information when hovering over a profile
    - Going to learn how to do these things in a project in the future.

### There is nothing you can't do with JavaScript (well, almost…)
- JavaScript allows us to add dynamic effects and entire web applications in the browser.
- Some modern JavaScript libraries/frameworks like ReactJS, AngularJS, or VueJS
    - Tools that make writing large scale applications and web page easier.
    - 100% based on JavaScript, they could go away but JavaScript won't ever go away.
        - Library of choice might not be as popular as it is today.
        - Learning JavaScript properly and well is the best investment that you can make in your career now.
    - These are considered frontend applications* - this course*
- You can also use JavaScript on a web server using NodeJS
    - Doesn't need any browser
    - Allows us to create backend applications that interact with databases.
    - These are considered backend applications
- You can also use JavaScript to build native mobile/desktop applications
    - Using React Native, Ionic Framework, or Electron

### JavaScript Releases/Versions *(more about this later…)*
… → ES5 → **ES6/ES2015** → ES7/ES2016 → ES8/ES2017 → ES9/ES2018 → ES10/ES2019 → ES11/ES2020 → …
- ES6/ES2015 was the largest update to the JavaScript language EVER
    - ES stands for ECMAScript
- After ES2015, there's a yearly update of JavaScript which is known as Modern JavaScript.
    - Learn Modern JavaScript from the beginning, but without forgetting the older parts.
---
## Linking a JavaScript File

*Going to learn how to write code in a JavaScript file and then run that code in the browser.*
*Make sure to download and extract the starter code somewhere for the course that was mentioned at the beginning of the course.*
We always need a HTML document so that way our JavaScript can be attached to it.

There's a script tag in HTML that can be used to write JavaScript, *however this isn't used at all!*
```JS fold
<script>
	let js = 'amazing';
	if (js === 'amazing') alert('JavaScript is FUN!');

	40 + 8 + 23 - 10; <!-- Doesn't show in browser -->
	console.log(40 + 8 + 23 - 10); <!-- Shows in browser -->
</script>

<script src="script.js"></script> <!-- Linking to a JS file -->

```

Why doesn't the math problem in the JS/HTML code not show up in the browser's console?
- The console is an environment to execute small pieces of code and show the results immediately.

To access the console from our code, we need to add `console.log();`  to our code with something inside the parentheses to be seen.
The advantage of having an inline script of JavaScript, is to not have another file to load along side the HTML file. However, it's not good for separating the HTML content with the JavaScript content.
Make sure the JavaScript file is linked properly and spelled properly when adding it to a page. Also, make sure there's no errors inside of the JavaScript code.
 ---
## Values and Variables

A value is basically a piece of data, the most fundamental unit that we have in programming. Also considered the smallest unit of information that is in JavaScript.
- `'Kyle'`  is a value

We can store values into variables to be able to reuse them over and over again.
Values are also numbers
Imagine a variable being a box, a box can hold some object, such as a book. Then, you can write on the box a label to describe what is in the box. Next, we can find the object later when we need it by using that label.
- Box called first name, and in the box is the value of "Kyle".
- If we want to use the value, then we just use the label (or variable name)

When JavaScript see's `console.log(itemhere);` , then it will log to the console the item that is mentioned. This can also have multiple items inside of it be mentioned.
- Without variables in JavaScript, you'd have to change out the value by hand everywhere that you need to change it.

All errors will be mentioned in the console should something happen to your code.
### Conventions and Rules for Naming Variables
[Camel Case](https://developer.mozilla.org/en-US/docs/Glossary/Camel_case) - A way of writing phrases without spaces, where the first letter of each word is capitalized, except for the first letter of the entire compound word, which may be either upper or lower case. They can only contain letters, numbers, underscores, or dollar signs
  - Can't write `3years` , an *illegal* variable name because it starts with a number
  - Can't write `someone&something` , another *illegal* variable name because you can't use the `&` symbol in a variable name. Can use `something\_someone` .
  - Can't use a word that JavaScript has been declared a reserved keyword, *such as `new` and `function`*
  - You can use `name` , but in some cases it can create some problems since it's also a reserved keyword in JavaScript. Don't call your variables just name.
  - Don't start a variable name with an uppercase letter, always start with a lowercase letter. Only use when doing *OOP (mentioned later in the course)*.
  - Variables that are all in uppercase are reserved for constants we know that **will never change**, such as the number of PI.
  - Make sure variable names are descriptive to write clean code. It should be easy to understand what value the variable is holding.
```JS fold
// Examples from the video that have been written down in VS Code
console.log("Kyle");
console.log(23);
console.log(40 + 8 + 23 - 10); // Values are the numbers

let firstName = "John"; // Declaring a variable, will be stored in memory
console.log(firstName);
console.log(firstName);
console.log(firstName);

let PI = 3.1415; // Never will change

let myFirstJob = 'Programmer'; // Descriptive and a lot better
let myCurrentJob = 'Teacher';
let job1 = 'programmer'; // Not descriptive, what even are they???
let job2 = 'teacher';
console.log(myFirstJob);
```
### Practice Assignment
Instructions
1. Declare variables called `country`, `continent` and `population` and assign their values according to your own country (population in millions).
2. Log their values to the console.

```JS file:solution fold
// Solution
let currentCountry = 'USA';
let currentContinent = 'North America';
let currentPop = 333.3;

console.log(currentCountry, currentContinent, currentPop);
```

---
## Practice Assignments

There's practice assignments that have been provided for after each section [on this website](https://codingheroes.io/assignments/values-and-variables.html). Go there after each section to hopefully retain from what's been taught.

---
## Data Types

In every programming language, values can have different types depending on the type of data we want them to hold. There's more than strings and numbers.
### Objects and Primitives
- Every value is either an object or a primitive value
    - A value is only a primitive when it's not an object

```JS fold
// Example of an Object in JavaScript
let me = {
	name: 'Kyle';
}

// Example of a Primitive Value in JavaScript
let firstName = 'Kyle';
let age = 28;
```
### The 7 Primitive Data Types
*Data types 1 → 3 are the most data types that we will deal with the most.*
1. **Number**: Floating point numbers, used for decimals and integers. In other programming languages, you will find different data types for integers and decimals.
    - `let age = 23;`
2. **String**: Sequence of characters used for text. Always put them in double or single quotes. *JavaScript will confuse it with a variable name.*
    - `let firstName = 'Kyle'`
3. **Boolean**: Logical type that can only take and be true or false, used for taking decisions.
    - `let fullAge = true;`
4. **Undefined**: Value taken by a variable that is not yet defined ('empty value'). *Simply a variable that we declared without assigning a value*.
    - `let children;`
5. **Null**: Also means 'empty value'. *Don't worry about the details, but it exists*.
6. **Symbol**: Introduced in ES6/ES2015, its a value that is unique and cannot be changed. (*Not useful at the moment, but will be talked about by the end of the course*).
7. **BigInt**: Introduced in ES11/ES2020, this is for larger integers that the Number type can't hold.

JavaScript has a feature called Dynamic Typing. We do ***not*** have to manually define the data type of the value stored in a variable. Instead, data types are determined **automatically**.
- In other programming languages, **you do** have to do that.
- In JavaScript, the value has a type and not the variable.

*Goes over code commenting and how it works and why it's used*

[typeOf Operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof) - This operator returns a string indicating the type of the operand's value.

Examples shown in VS Code
```JS fold
let javascriptIsFun = true;
console.log(javascriptIsFun); // Should return true

console.log(typeof true); //typeOf Operator being used
console.log(typeof javascriptIsFun);
console.log(typeof 23);
console.log(typeof 'Kyle');

// Dynamic typing
javascriptIsFun = 'YES!';
console.log(typeof javascriptIsFun);

// Undefined
let year;
console.log(year);
console.log(typeof year);

year = 1991;
console.log(typeof year);

// Error that exists in the typeof error
// JS says null is an object, but it's a bug and never corrected
console.log(typeof null);
```
### Practice Assignment
Instructions
1. Declare a variable called `isIsland` and set its value according to your country. The variable should hold a Boolean value. Also declare a variable `language`, but don't assign it any value yet.
2. Log the types of `isIsland`, `population`, `country` and `language` to the console.
```JS file:solution fold
let isIsland = false;
let language;

console.log(typeof isIsland);
console.log(typeof population);
console.log(typeof country);
console.log(typeof language);
```
 ---
## Let, Const, and VAR

`let` and `const` were introduced in ES6/ES2015 (*considered part of modern JavaScript*).
- `var` is the old way of declaring variables.

We use `let` keyword to declare variables that can change later.
When we need to mutate (*or change*) a variable, we use the `let` keyword.
- Declaring an empty year variable, and then declaring it to be 1991 later on in the code.

We use the `const` keyword to declare variables that are not supposed to change at any point in the future.
- If trying to re-assign, an error will be shown in the browser's console.
- **Can't declare an empty `const` variable*** - shows an error in the browser's console*

Should I use `let` or `const` to declare a new variable?
- For clean code, use `const` by default and use `let` if the variable needs to change sometime in the future.
    - For something like a birth year, use const because a birth year of a person can never be changed.
    - For something like an age number, use let since that is able to change every year. However, you should use const as well because it's a good practice to have as little changes as possible. Can create bugs in the future if not careful enough.

Using the `var` keyword should be avoided at all costs. However, it should still be learned and talked about due to legacy reasons, being used in old code bases, or even while watching an old tutorial.
- The old way of defining variables prior to ES6/ES2015
- It works the same as `let`

You can still name a variable without using `let` , `const` , and `var` . However, it's a terrible idea because it doesn't create a variable in the scope. JavaScript will just create it in the global object. *(No need to understand this for now, will be taught later on)*.
```JS fold
let age = 30;
age = 31;

const birthYear = 1991;
birthYear = 1990;

var job = 'programmer';
job = 'teacher';

// Don't do this...
lastName = 'namegoeshere';
console.log(lastName);
```
### Practice Assignment
Instructions
1. Set the value of `language` to the language spoken where you live (some countries have multiple languages, but just choose one).
2. Think about which variables should be `const` variables (which values will never change, and which might change?). Then, change these variables to `const`.
3. Try to change one of the changed variables now, and observe what happens.
```JS file:solution fold
let language = 'English';
console.log(language); // Provides no errors, English is logged to the console

const stateName = 'Florida';
stateName = 'Georgia'; // Provides an error when shown in the console
```
 ---
## Basic Operators

An **operator** allows us to transform values or combine multiple values and do all kinds of work with values.
- Mathematical operators
- Comparison operators
- Logical operators
- Assignment operators
- and more operators!

Mathematical Operators
- You can do addition, subtraction, multiplication, division, and many more
- You can add a `+` sign to combine two or more strings together

Comparison Operators
- `<`, `>`, `<=`, `=>`
```JS fold
// Math Operators
const now = 2037;
const ageKyle = now - 1995;
const ageSarah = now - 2018;
console.log(ageKyle, ageSarah); // 42 and 19

console.log(ageKyle * 2, ageKyle / 10, 2 ** 3); // 84, 4.2, and 8
// 2 ** 3 means 2 to the power of 3 = 2 * 2 * 2

// Concatinating strings together
const firstName = 'Kyle';
const lastName = 'Namehere';
console.log(firstName + ' ' + lastName); // Kyle Namehere

// Assignment operators
let x = 10 + 5; // 15
x += 10; //x = x + 10 = 25
x *= 4; // x = x * 4 = 100
x++; // x = x + 1 = 101
x--; // x = x - 1 = 100
console.log(x);

// Comparision Operators | >, <, >=, <=
console.log(ageKyle > ageSarah); // True
console.log(ageSarah >= 18); // True
const isFullAge = ageSarah >= 18;
// The same as doing the first console log
console.log(now - 1991 > now - 2019); // True
```
### Practice Assignment
Instructions
1. If your country split in half, and each half would contain half the population, then how many people would live in each half?
2. Increase the population of your country by 1 and log the result to the console.
3. Finland has a population of 6 million. Does your country have more people than Finland?
4. The average population of a country is 33 million people. Does you country have less people than the average country?
5. Based on the variables you created, create a new variable `description` which contains a string with this format: `'Portugal is in Europe, and its 11 million people speak portuguese'`.
```JS file:solution fold
let currentPop = 333.3;
let country = 'USA';
let continent = 'North America';
let language = 'English';
console.log(currentPop / 2);

currentPop++;

console.log(currentPop);
console.log(currentPop > 6);
console.log(currentPop < 33);

const description1 =
    country +
        ' is in ' +
    continent +
        ', and its ' +
    currentPop +
        ' million people speak ' +
    language +
		'.';
console.log(description1);
// [USA] is in [North America], and its [334.3] million people speak [English][.]
```
 ---
## Operator Precedence

[JavaScript Order Precedence Table](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_precedence#table) - MDN
- *No need to understand the numbers on the left side, no one does. No need to worry about it*

Going to be talking about the precedence of different operators.
*"Why is the subtraction in the code executed before the comparison operator?"*
`console.log(now - 1991 > now - 2018);`
JavaScript has a well defined order of operator precedence, the order in which operators are executed.
You can also declare 2 values at once
- `let x, y;`
```JS fold
const now = 2037;
const ageKyle = now - 1995;
const ageSarah = now - 2018;

console.log(now - 1991 > now - 2018);
// Two calculations are done before the gt

console.log(25 - 10 - 5);
let x, y;
x = y = 25 - 10 - 5; // x = y = 10, x = 10
console.log(x, y);

const averageAge = ageKyle + ageSarah // 2;
console.log(ageKyle, ageSarah, averageAge);
```
 ---
## A Note about Challenges

Don't skip the challenges in the course, as they're important to learning in the course overall.

---
## Coding Exercise #1: Challenge #1

Instructions
Mark and John are trying to compare their BMI (Body Mass Index), which is calculated using the formula: `BMI = mass / (height \* height)` (mass in kg and height in meters).
Your task is to write some code to help them:
1. Store Mark's and John's mass and height in variables called `massMark`, `heightMark`, `massJohn` and `heightJohn`.
2. Calculate both their BMIs using the formula, and store the results in two variables called `BMIMark` and `BMIJohn`.
3. Log the value of `BMIMark` and `BMIJohn` to the console.
4. **BONUS**: Create a boolean variable `markHigherBMI` containing information about whether Mark has a higher BMI than John. Log it to the console too

**TEST DATA #1:** Marks weighs 78 kg and is 1.69 m tall. John weighs 92 kg and is 1.95 m tall.
**TEST DATA #2:** Marks weights 95 kg and is 1.88 m tall. John weights 85 kg and is 1.76 m tall.
**👋 OPTIONAL: You can watch my solution in video format in the next lecture
**IMPORTANT:** The `\*\*` operator is not supported in this editor. Please make sure to use exactly this formula `mass / (height \* height)`, and not this one `mass / (height \*\* 2)`.
```JS file:solution fold
const massMark = 78;
const heightMark = 1.69;
const massJohn = 92;
const heightJohn = 1.95;

const BMIMark = massMark / (heightMark * heightMark);
const BMIJohn = massJohn / (heightJohn * heightJohn);
const markHigherBMI = BMIMark > BMIJohn;

console.log(BMIMark, BMIJohn, markHigherBMI);
// 27.309968138370508 24.194608809993426 true
```
 ---
## Strings and Template Literals

Strings are a very important part of programming. Going to be learning about how to combing strings using Template Literals.
[Template Literals - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) - Literals delimited with backtick ( `\``) characters, allowing for [multi-line strings](), [string interpolation]() with embedded expressions, and special constructs called [tagged templates]().
Many developers started using backtick characters for all their strings because then you don't have to think about which quotation marks you should use. It's much easier than going back to switch it out.
```JS fold
const firstName = 'Kyle';
const job = 'Frontend Web Developer';
const birthYear = 1995;
const year = 2024;

// Before ES6
const kyle = "I'm " + firstName + ', a ' + (year - birthYear) + ' years old ' + job + '!';
console.log(kyle);
// I'm Kyle, a 29 years old Frontend Web Developer!

// With ES6
const kyleNew = `I'm ${firstName}, a ${year - birthYear} years old ${job}!`;
console.log(kyleNew);
// I'm Kyle, a 29 years old Frontend Web Developer!

console.log(`Just a regular string...`);
// Just a regular string...

// Multiline string before ES6/ES2015
console.log('String with \n\
multiple \n\
lines');

// Multiline string with ES6/ES2015
console.log(`Strings with
multiple
lines`);
```
### Practice Assignment
Instructions
1. Recreate the `description` variable from the last assignment, this time using the template literal syntax.
```JS file:solution fold
let currentPop = 333.3;
let continent = 'North America';
let country = 'USA';
let language = 'English';

const currLocation = `The ${country} is in ${continent}, and its ${currentPop} million people speak ${language}.`
console.log(currLocation);
// The USA is in North America, and its 333.3 million people speak English.
```
 ---
## Taking Decisions: `if/else` Statements

[If/Else Statement - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
Going to make coding even more fun as we make it look a lot more real with `if/else` statements by seeing if someone is of age to get their driver's license.
This statement executes a statement if a specified condition is `truthy`. If the condition is `falsy`, another statement in the optional `else` clause will be executed.
[Control Structure/Flow - (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Control_flow): The order in which the computer executes statements in a script.
```JS fold
const age = 15;

if (age >= 18) {
    console.log('Sarah can start driving license 🚘'); // Older than or is 18
} else {
    const yearsLeft = 18 - age; // Younger than 18
    console.log(`Sarah is too young. Wait another ${yearsLeft} year(s).`);
}

const birthYear = 1999;

let century;
if (birthYear <= 2000) {
    century = 20; // If born before 2000
} else {
    century = 21; // If born after 2000
}
console.log(century);
```
### Practice Assignment
Instructions
1. If your country's population is greater than 33 million, log a string like this to the console: `"Portugal's population is 22 million below average"` (the 22 is the average of 33 minus the country's population).
2. After checking the result, change the population temporarily to 13 and then to 130. See the different results, and set the population back to original.
```JS file:solution fold
let currentPop = 333.3; // Change to 13 to get the else statement
let country = 'USA';

if (currentPop > 33) {
    console.log(`${country}'s population is above average!`);
} else {
    console.log(`${country}'s population is ${33 - currentPop} million below average`);
}
```
 ---
## Coding Exercise #2: Challenge #2

Instructions
Use the BMI example from **Challenge #1**, and the code you already wrote, and improve it:
1. Print a nice output to the console, telling the user who has the higher BMI. The message can be either:
    `"Mark's BMI is higher than John's!"` or `"John's BMI is higher than Mark's!"`.
2. Modify the outputs above to use template literals to include the BMI values in the outputs.
Example: `"Mark's BMI (28.3) is higher than John's (23.9)!"` or `"John's BMI (29.1) is higher than Mark's (27)!"`.

**Note:** Don't round the BMI values. Leave them as they are.

**👋 OPTIONAL: You can watch my solution in video format in the next lecture

**IMPORTANT:** The `\*\*` operator is not supported in this editor. Please make sure to use exactly this formula `mass / (height \* height)`, and not this one `mass / (height \*\* 2)`.
```JS file:solution fold
// Depending on the below numbers, it can change the result
const massMark = 95;
const heightMark = 1.88;
const massJohn = 85;
const heightJohn = 1.76;

const BMIMark = massMark / (heightMark * heightMark);
const BMIJohn = massJohn / (heightJohn * heightJohn);
console.log(BMIMark, BMIJohn);

if (BMIMark > BMIJohn) {
    console.log(`Mark's BMI (${BMIMark}) is higher than John's (${BMIJohn})!`);
} else {
    console.log(`John's BMI (${BMIJohn}) is higher than Mark's (${BMIMark})!`);
}
```
 ---
## Type Conversion and Coercion

Types are one of the fundamental aspects in programming. Converting between types is something that's done in every programming language.
- Example: Converting a string to a number or a number into a Boolean.

[Type Conversion - MDN](https://developer.mozilla.org/en-US/docs/Glossary/Type_Conversion): The transfer of data from one data type to another.
[Type Coercion - MDN](https://developer.mozilla.org/en-US/docs/Glossary/Type_coercion): The automatic or implicit conversion of values from one data type to another behind the scenes *(such as strings to numbers).*
```JS fold
// Type Conversion
const inputYear = '1991';
console.log(Number(inputYear));
console.log(Number(inputYear) + 18); // 2009

console.log(Number('Kyle')); // NaN, because string
console.log(typeof NaN); // Number(but an invalid number)

console.log(String(23), 23); // String of 23 vs 23 the number

// Type Corecion
console.log('I am ' + 23 + ' years old'); // Number -> String
console.log('23' - '10' - 3); // 10, String -> Number
console.log('23' + '10' + 3); // 23103
console.log('23' * '2'); // 46, String -> Number

// Fun Game #1
let n = '1' + 1; // 11 the string
n = n - 1; // 11 string -> 11 number - 1
console.log(n); // 10

// Fun Game #2 & #3
2 + 3 + 4 + '5' // "95" -- 2 + 3 = 5 + 4 = 9 + '5' = "95"
'10' - '4' - '3' - 2 + '5' // "15" -- 6 - 3 = 3 - 2 = 1 + '5' = "15"
```
### Practice Assignment
Instructions
1. Predict the result of these 5 operations without executing them…
```JS fold
console.log('9' - '5'); // -> ?
console.log('19' - '13' + '17'); // -> ?
console.log('19' - '13' + 17); // -> ?
console.log('123' < 57); // -> ?
console.log(5 + 6 + '4' + 9 - 4 - 2); // -> ?
```
2. Execute the operations to check if you were right.

```JS file:solution fold
console.log('9' - '5'); // -> 4
console.log('19' - '13' + '17'); // -> 617 (string)
console.log('19' - '13' + 17); // -> 23
console.log('123' < 57); // -> False
console.log(5 + 6 + '4' + 9 - 4 - 2); // -> 1143
```
 ---
## Truthy and Falsy Values

[Falsy Values - MDN](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
A **falsy** (sometimes written **falsey**) value is a value that is considered false.
- There's 5 falsy values
    1. 0
    2. ''  - (*empty string*)
    3. undefined
    4. null
    5. NaN - (*Not a Number*)

[Truthy Values - MDN](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
A **truthy** value is a value that is considered `true` when encountered in a Boolean context.
- This includes all values that are not apart of the falsy values.
```JS fold
console.log(Boolean(0));         // False
console.log(Boolean(undefined)); // False
console.log(Boolean(''));        // False - Empty string
console.log(Boolean('Kyle'));    // True - Filled String, not empty
console.log(Boolean({}));        // True - Object

// Money is 0, meaning false so the 2nd statement runs
// Money is 100, meaning first statement will run
const money = 100;
if (money) {
    console.log("Don't spend it all! 💵");
} else {
    console.log('You should get a job! 💼');
}

// Why is height undefined in this?
// let height;
let height = 0; // A bug because 0 is a number but undefined
if(height) {
    console.log('Yay! Height is defined!');
} else {
    console.log('Height is undefined');
}
// Undefined is a falsly value since height isn't defined
```
 ---
## Equality Operators: `==` vs. `===`

If we want to check if two values are actually equal or not using the `==` or `===` .
[Equality (= =) - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality) - This operator checks whether its two operands are equal (*using true or false values*), returning a Boolean result. This does type coercion.
- `'18' == 18` - "true"

[Strict Equality (= = =) - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality) - This operator checks whether its two operands are equal (*using true or false values*), returning a Boolean result. It doesn't perform type coercion and only returns true when both values are the same.
- `'18' === 18` - "false"

As a general rule, avoid the loose equality operator (`==`) as much as you can when comparing values. Always default to use the strict equality (`===`) operator.
[Strict Inequality `(!==)` - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_inequality): This operator checks whether its two operands are not equal, returning a Boolean result. **Use this one and not the loose equality!**
- `!==23`

[Inequality (!=) - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Inequality): This operator checks whether its two operands are not equal, returning a Boolean result.
- `!=23`
```JS fold
const age = '18';
if (age === 18) console.log('You just became an adult! 🧓🏻 (strict)');
if (age == 18) console.log('You just became an adult! 🧓🏻 (loose)');

// Getting a value from any webpage
const favorite = Number(prompt("What's your favorite number?")); // Asks for favorite number
console.log(favorite); // Shows user's response in the console
console.log(typeof favorite);

if (favorite === 23) {
    console.log('Cool! 23 is an amazing number!');
} else if (favorite === 7) {
    console.log('7 is also a cool number...');
} else if (favorite === 9){
    console.log('9 is also a cool number...');
} else {
    console.log('Number is not 23, 7, or 9');
}

if(favorite !== 23) console.log('Why not 23?!');
```
### Practice Assignments
Instructions
1. Declare a variable `numNeighbours` based on a prompt input like this:
```JS fold
prompt('How many neighbour countries does your contry have?');
```
2. If there is only 1 neighbor, log to the console 'Only 1 border!' (use loose equality `==` for now).
3. Use an `else-if` block to log 'More than 1 border' in case `numNeighbours` is greater than 1.
4. Use an `else` block to log 'No borders' (this block will be executed when `numNeighbours` is 0 or any other value).
5. Test the code with different values of `numNeighbours`, including 1 and 0.
6. Change `==` to `===`, and test the code again, with the same values of `numNeighbours`. Notice what happens when there is exactly 1 border! Why is this happening?
7. Finally, convert `numNeighbours` to a number, and watch what happens now when you input 1.
8. Reflect on why we should use the `===` operator and type conversion in this situation.
```JS file:solution fold
const numNeighbors = Number(prompt('How many neighbour countries does your country have?'));

if (numNeighbors === 1) {
	console.log('Only 1 border!');
} else if {
	console.log('More than 1 border!');
} else {
	console.log('No border...');
}
```

---
## Boolean Logic

When learning about if/else statements, comparison and equality operators, and Boolean values, we also need to learn about logic. About Boolean Logic.
Boolean Logic is a branch of computer science which uses true and false values to solve complex logical problems. It uses several logical operators to combine true and false values, *(like math operators*).
Boolean Logic is not specific to JavaScript or any programming language.
### Basic Boolean Logic: The And, Or, & Not Operators
An example of two Boolean Variables that can either be true or false…
1. Sarah has a driver's license
2. Sarah has good vision

### Using A and B: "Sarah has a driver's license ***AND*** good vision"
- Going to use a truth table for the possible 2 values
| **AND** | **TRUE** | **FALSE** |
|:--------|:---------|:----------|
|    TRUE |     <span style="color: green">TRUE</span> |      TRUE |
|   FALSE |     TRUE |     FALSE |

- If A (*at the top*) and B (*on the side*) are true, the result would be true.
    - True when **ALL** are true (*no matter how many variables are being used*).

### Using A or B: "Sarah has a driver's license OR good vision
| **AND** | **TRUE** | **FALSE** |
|:--------|:---------|:----------|
|    TRUE |     TRUE |      TRUE |
|   FALSE |     TRUE |     FALSE |

- Even if one of the variables is false, then the operation is true
    - True when **ONE** is true

### Using NOT A, NOT B
- This inverts true/false values
- Acts on only one Boolean value

### An Example
If someone's age = 16…
Our two Boolean variables that we're using…
1. Age is greater than or equal to 20 years old - **FALSE**
2. Age is less than 30 years old - **TRUE**

Using operators!
| **AND** | **TRUE** | **FALSE** |
|:--------|:---------|:----------|
|    TRUE |     TRUE |      TRUE |
|   FALSE |     TRUE |     FALSE |

| **AND** | **TRUE** | **FALSE** |
|:--------|:---------|:----------|
|    TRUE |     TRUE |     FALSE |
|   FALSE |    FALSE |     FALSE |

- !A (not A) is false - **TRUE**
- A is false and B is true - **FALSE**
- A is false or B is true - **TRUE**
- !A (not A) is true and B is true - **TRUE**
- A is false and !B (not B) is false - **FALSE**
 ---

## Logical Operations

[<u>Logical AND (&&) - MDN</u>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND): This operator for a set of Boolean operands will be `true` if and only if all the operands are `true`. Otherwise it will be `false`.
```JS file:Logical-AND-Example fold
const a = 3;
const b = -2;

console.log(a > 0 && b > 0); // A is greater than 0 AND b is greather than 0
// Output is FALSE
```

[<u>Logical OR (\|\|) - MDN</u>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR): This operator for a set of operands is true if and only if one or more of its operands is true.
```JS file:Logical-OR-Example fold
const a = 3;
const b = -2;

console.log(a > 0 || b > 0); // A is greater than 0 OR B is greater than 0
// Output is TRUE
```

[<u>Logical NOT (!) - MDN</u>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_NOT): This operator takes truth to falsity and vice versa.
```JS file:Logical-NOT-Example fold
const a = 3;
const b = -2;

console.log(!(a > 0 || b > 0)); // NOT A is greater 0 OR NOT B is greater than 0
// Output is FALSE

const hasDriversLicense = true; // Variable A
const hasGoodVision = true; // Varaible B

console.log(hasDriversLicense && hasGoodVision);
console.log(hasDriversLicense || hasGoodVision);
console.log(!hasDriversLicense);

const isTired = false; // Variable C
console.log(hasDriversLicense && hasGoodVision && isTired);

if(hasDriversLicense && hasGoodVision && !isTired) {
    console.log('Sarah is able to drive! 🚗'); // Current Output!
} else {
    console.log('Someone else should drive... ❌');
}
```
### Practice Assignment
Instructions
1. Comment out the previous code so the prompt doesn't get in the way.
2. Let's say Sarah is looking for a new country to live in. She wants to live in a country that speaks English, has less than 50 million people and is not an island.
3. Write an `if `statement to help Sarah figure out if your country is right for her. You will need to write a condition that accounts for all of Sarah's criteria. Take your time with this, and check part of the solution if necessary.
4. If yours is the right country, log a strings like this `'You should live in Portugal :)'`. If not, log `'Portugal does not meet your criteria :('`.
5. Probably your country does not meet all the criteria. So go back and temporarily change some variables in order to make the condition true (unless you live in Canada :D).
```JS file:solution fold
let language = 'English';
let country = 'USA';
let currentPop = 333.3;
let isIsland = false;

if (language === language && currentPop < 50 && !isIsland) {
	console.log('You should live in ${country}');
} else {
	console.log(`${country} does not meet your criteria.`);
}
```
 ---
## Coding Exercise 3: Challenge #3

Instructions
There are two gymnastics teams: Dolphins and Koalas. They compete against each other 3 times. The winner with the highest average score wins a trophy!
**Your tasks:**
1. Calculate the average score for each team, using the test data included below. The average score for Dolphins should be assigned to the `scoreDolphins` variable, and the average score of Koalas should be assigned to the `scoreKoalas` variable.
2. Compare the team's average scores to determine the winner of the competition, and print to the console:
`"Dolphins win the trophy"` if Dolphins win, or
`"Koalas win the trophy"` if Koalas win, or
`"Both win the trophy"` if their average scores are equal.
**TEST DATA:** Dolphins scored 96, 108, and 89. Koalas scored 88, 91, and 110.
**👋 OPTIONAL: You can watch my solution in video format in the next lecture

```JS file:solution fold
const scoreDolphins = (97 + 112 + 80) / 3;
const scoreKoalas = (109 + 95 + 50) / 3;
console.log(scoreDolphins, scoreKoalas);

if (scoreDolphins > scoreKoalas && scoreDolphins >= 100) {
    console.log('Dolphins win the trophy! 🏆');
} else if (scoreDolphins < scoreKoalas && scoreKoalas >= 100) {
    console.log('Koalas win the trophy! 🏆');
} else if (scoreDolphins === scoreKoalas && scoreDolphins >= 100 && scoreKoalas >= 100) {
    console.log('Both win the trophy! 🏆🏆');
} else {
    console.log('No one wins the trophy... 😭');
}
```
 ---
## The Switch Statement

The switch statement is alternative of writing a complicated if/else statement when all you want to do is compare one value with multiple different options.
[<u>Switch Statement - MDN</u>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch): This statement evaluates an expression, matching the expression's value against a series of `case` clauses, and executes statements after the first `case` clause with a matching value, until a `break` statement is encountered.
```JS file:switch-statement-example fold
const day = 'Monday';

switch (day) {
    case 'Monday': // day === 'Monday'
        console.log('Plan course structure');
        console.log('Go to coding meetup');
        break; // Without this, it continues to execute | Tell it to stop
    case 'Tuesday': // day === 'Tuesday'
        console.log('Prepare theory videos');
        break;
    case 'Wednesday': // day === 'Wednesday'
    case 'Thursday': // day === 'Thursday'
        console.log('Write code examples');
        break;
    case 'Friday': // day === 'Friday'
        console.log('Record videos');
        break;
    case 'Satruday': // day === 'Saturday'
    case 'Sunday': // day === 'Sunday'
        console.log('Enjoy the weekend!');
        break;
    default:
        console.log('Not a valid day... 📅');
}

// Using the If/Else Statement
// Repetitive code vs. the switch statement
if (day === 'Monday') {
    console.log('Plan course structure');
    console.log('Go to coding meetup');
} else if (day === 'Tuesday') {
    console.log('Prepare theory videos');
} else if (day === 'Wednesday' || day === 'Thursday') {
    console.log('Write code examples');
} else if (day === 'Friday') {
    console.log('Record videos');
} else if (day === 'Saturday' || day === 'Sunday') {
    console.log('Enjoy the weekend!');
} else {
    console.log('Not a valid day... 📅');
}
```
### Practice Assignment
Instructions
1. Use a `switch` statement to log the following string for the given `language`:
	- Chinese or mandarin: `'MOST number of native speakers!'`;
	- Spanish: `'2nd place in number of native speakers'`;
	- English: `'3rd place'`;
	- Hindi: `'Number 4'`;
	- Arabic: `'5th most spoken language'`;
	- For all other simply log `'Great language too :D'`.

```JS file:solution fold
let language = 'English';

switch (language) {
    case 'Chinese':
    case 'Mandarin':
        console.log('Chinese and Mandarin have the MOST number of Native Speakers');
        break;
    case 'Spanish':
        console.log('2nd place in number of Native Speakers');
        break;
    case 'English':
        console.log('3rd Place in number of Native Speakers');
        break;
    case 'Hindi':
        console.log('4th Place in number of Native Speakers');
        break;
    case 'Arabic':
        console.log('5th place in number of Native Speakers');
        break;
    default:
        console.log('Great language too!');
}
```
 ---
## Statements and Expressions

Going to learn about the theoretical concept between Statements and Expressions in JavaScript.
Expression: A piece of code that produces a value.
- Example: `3 + 4` , `1991` , `true && false && !false`

Statement: A bigger piece of code that is executed and doesn't produce a value on itself. You can compare this with normal spoken language in a sentence. We write our whole program as a sequence of actions which are considered statements.
- When something ends with a semicolon (;), that is a statement (*kind of like a complete sentence*).
```JS file:Statement-Example fold
// Example
// It declares the variable and performs the action, but doesn't produce a value
// The string is an expression, (might be confusing)
if (23 > 10) {
	const str = '23 is bigger';
}
```
 ---
## The Conditional (Ternary) Operator

We learned about the switch statement and if/else statement. Now, we're going to learn about the conditional ternary operator.
[Ternary Operator - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_operator): This operator is the only JavaScript operator that takes three operands: a condition followed by a question mark (`?`), then an expression to execute if the condition is truthy followed by a colon (`:`), and finally the expression to execute if the condition is falsy. The operator is frequently used as an alternative to the `if..else` statement.
```JS fold
// If/Else Statement Example
let drink2;
if (age >= 18) {
    drink2 = 'wine 🍷';
} else {
    drink2 = 'water 💧';
}
console.log(drink2);

// Using the Ternary Operator Examples
const age = 23;
age >= 18 ? console.log('I like to drink wine 🍷') : console.log('I like to drink water 💧');

const age = 23;
const drink = age >= 18 ? 'wine 🍷' : 'water 💧';
console.log(drink);

console.log(`I like to drink ${age >= 18 ? 'wine 🍷' : 'water 💧'}`);
// I like to drink wine 🍷
```
### Practice Assignment
Instructions
1. If your country's population is greater than 33 million, use the ternary operator to log a string like this to the console: `"Portugal's population is above average"`. Otherwise, simply log `"Portugal's population is below average"`. Notice how only one word change between these two sentences!
2. After checking the result, change the population temporarily to 13 and then to 130. See the different results, and set the population back to original.
```JS file:solution fold
let country = 'USA';
let population = 333.3;

console.log(`${country}'s population is ${population > 33 ? 'above' : 'below'} average`);
// USA's population is above average
```
 ---
## Coding Exercise 4: Challenge #4

Instructions
Steven needs a very simple tip calculator for whenever he goes to eat in a restaurant. In his country, it's usual to tip 15% if the bill value is between 50 and 300. If the value is different, the tip is 20%.
**Your tasks:**
1. Calculate the tip, depending on the bill value. Create a variable called `tip` for this. It's not allowed to use an `if...else` statement (if it's easier for you, you can start with an `if...else` statement, and then try to convert it to a ternary operator).
2. Print a string to the console containing the `bill` value, the `tip`, and the final value ( `bill + tip`).

Example: `The bill was 275, the tip was 41.25, and the total value 316.25`.
**Note:** Use the values of the `bill` and `tip` variables to construct this string. Don't hard-code them 🙂
**TEST DATA:** Test with different `bill` values: 275, 40, and 430
**HINT:** To calculate 20% of a value, simply multiply it by 20/100 = 0.2
**HINT 2:** Value X is between 50 and 300, if it's `>= 50 && <= 300` 😉
**👋 OPTIONAL: You can watch my solution in video format in the next lecture

```JS file:solution fold
const bill = 275;
const tip = bill <= 300 && bill >= 50 ? bill * 0.15 : bill * 0.2;
console.log(`The bill was ${bill}, the tip was ${tip}, and the total value ${bill + tip}.`);
// The bill was 275, the tip was 41.25, and the total value 316.25.
```
 ---
## JavaScript Releases: ES5, ES6+, and ESNext

Now that we're familiar with the fundamentals of the JavaScript language, we can talk about JavaScript releases/versions before moving on. This was briefly talked about in the intro video, but now we're going into more depth about how releases work and how we can use this as its important for developers. We need to understand what's going on.

### A Brief History of JavaScript
**1995**: Brendan Eich was hired by Netscape Browser to create a programming language. He **creates the very first version of JavaScript in just 10 days**. It was called Mocha, but already had many fundamental features of modern JavaScript.
**1996**
- Mocha changes its name to LiveScript and then to JavaScript in order to attract Java Developers at the time. However, **JavaScript has almost nothing to do with Java**.
- Microsoft launches Internet Explorer, **copying JavaScript from Netscape** and calling it JScript *for legal reasons*.
**1997**: With a need to standardize the language, ECMA releases ECMAScript 1 (ES1), the first **official standard for JavaScript** (*ECMAScript is the standard, JavaScript is the language in practice.*)
**2009**: ES5/ES2009 (ECMAScript 5) is released with lots of great new features.
**2015**
- ES6/ES2015 (ECMAScript 6) is was released in June which was **the biggest update to the language EVER!**
- ECMAScript changes to an **annual release cycle** in order to ship less features per update.
2016 → ∞: Release of ES2016 / ES2017 / ES2018 / ES2019 / ES2020 / ES2021 / … / ES2089

### Backward Compatibility: Don't Break the Web!
If you took JavaScript code that was written back in 1997 and put it in a modern browser with a modern JavaScript engine, it would still work today. It can still understand old code from back then as well.
```JS fold
// ES1 Code
function add(n) {
	var x = 5 + add.arguments[0];
	return x;
}

// ES2089 Code (wouldn't work at all since it and we can't see in the future)
c int add n <=> int 5 + n;
```
It works this way because of the fundamental principle of JavaScript, **DON'T BREAK THE WEB!**
- Old features are **never removed**
- Not really new versions, just incremental updates/releases
- Websites keep working **forever**!
### How can we use Modern JavaScript today?
During Development: Simply use the latest version of Google Chrome/Mozilla Firefox
During Production: Use Babel to transpile and polyfill your code (*converting back to ES5 to ensure browser compatibility for all users*).

ES5: Fully supported in all browsers today and ready to be used (*from IE9 from 2011*)
ES6/ES2015 → ES2020: ES6+ is well supported on all modern browsers and doesn't have support for older browsers. You can use **most** features in production with transpiling and polyfilling.
To be up to date with what's compatible in a browser, you can view the [ES6 Compatibility Table](https://compat-table.github.io/compat-table/es6/)
ES2021 → ∞: ESNext: Future versions of the language (new feature proposals that reach Stage 4);
- Can already use some features in production with transpiling and polyfilling.

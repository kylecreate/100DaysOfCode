---
tags:
  - WebDev
---
In this section, we're going to continue learning important JavaScript fundamentals such as Functions, Objects, Arrays, and Loops. After completing the section, you'll have the skills to begin writing your own small programs using JavaScript.

---
## Activating Strict Mode

[Strict Mode - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
Before continuing to learn JavaScript in this new section, we should first activate "strict mode".
Strict Mode is a special mode that we can activate in JavaScript which makes it easier to write secure code.
- This needs to be the **very first line of code** in the script, otherwise it will not work.
- Best used at the beginning of each script you create in the future
    - Helps with creating accidental errors in your code
        1. Strict mode forbids from doing certain things
        2. Will create visible errors in the developer console in certain situations (*without it, it would fail silently*)

Another thing when using strict mode, is that it introduces a short list of variable names that are reserved for features that might be added to the language in the future.
```JS fold
`use strict`; // Enables strict mode for the entire script

let hasDriversLicense = false;
const passTest = true;

// if (passTest) hasDriverLicense = true; // Wrong spelling error
if (hasDriversLicense) console.log('I can drive!');

const interface = 'Audio'; // Reserving of the word 'interface'
const private = 534; // Reserving of the word 'private'
const if = 23; // Reserving of the word 'if'
```
 ---
## Functions

[Functions - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
The fundamental building block of real world JavaScript applications are functions. They're one of the most essential concepts in the language.
A function is a piece of code that we can re-use over and over again, like a variable but for whole chunks of code. It can hold one or more lines of code.
- The code that is inside the curly braces of the function is called the function buddy which will be executed when you run the function.

* When we write functions, we also pass data into a function and additionally it can also return data that can be used for something else in the program.
* Within the function, we specify parameters. These are like variables that are specific to the function that has them.
* Without executing the function code, the code will never run making it useless and never be processed which only happens when you call the function.
* Not all functions need to return something or accept parameters (*like the `fruitprocessor`*).
* Functions allow us to write more maintainable and create reusable chunks of code instead of re-writing it multiple times. You will know when you use functions when writing code for programs in the future.
- Keep your code **DRY** (Don't Repeat Yourself)
```JS fold
function logger() {
    console.log('My name is Kyle'); // This just logs to the console, but doesn't print til later
}

// Invoking/Running/Calling the function -- executing/using the function
logger(); // Doesn't produce a value, no variable used

function fruitProcessor(apples, oranges) {
    const juice = `Juice with ${apples} apples and ${oranges} oranges`;
    return juice; // The result of the function
}

const appleJuice = fruitProcessor(5, 0); // The numbers used are called arguments -- USE THIS
console.log(fruitProcessor(5, 0)); // Didn't capture value into variable -- NOT THIS

const appleOrangeJuice = fruitProcessor(2, 4);
console.log(appleOrangeJuice);
```
### Practice Assignment
Instructions
1. Write a function called `describeCountry` which takes three parameters: `country`, `population` and `capitalCity`. Based on this input, the function returns a string with this format: `'Finland has 6 million people and its capital city is Helsinki'`.
2. Call this function 3 times, with input data for 3 different countries. Store the returned values in 3 different variables, and log them to the console.

```JS file:solution fold
function describeCountry(country, population, capitalCity) {
    return `${country} has ${population} million people and its capital city is ${capitalCity}.`;
}

const descUnitedStates = describeCountry('United States', 333.3, `Washington, DC`);
console.log(descUnitedStates)
const descCanada = describeCountry('Canada', 40.7, `Ottawa`);
console.log(descCanada)
const descMexico = describeCountry('Mexico', 130, `Mexico City`);
console.log(descMexico);
```
 ---
## Functions Declarations vs. Expressions

In JavaScript, there's different types of ways of writing a function. Each type of function works in a slightly different way, but are similar to each other.
Functions are not a type, but instead are values which can be stored in a variable.
[Function Declarations - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_declarations): This statement consists of the function keyword and then is followed by the name of the function, a list of parameters to the function (*using parentheses and commas for multiple parameters*), and curly braces to define the function.
- This was shown in the last section.
- Can be called in the code before the function is mentioned.

[Function Expressions - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_expressions): This statement can be anonymous, meaning that it doesn't have to have a name.
- This cannot be called in the code before the function is mentioned, an error will throw because of a process called hoisting (*more about that in the future*).

Which one of these should I use when I write my own functions?
- Often times, it depends on the preference on the developer. He prefers to use expressions which forces him to use a nice structure where he has to define the structures first at the top before calling them. You can use either one, it doesn't matter. You just need to know about both. Don't just pick one and forget about the other one.
```JS fold
// Function Declaration
function calcAge1(birthYear) {
    return 2037 - birthYear;
}
const age1 = calcAge1(1991);

// Function Expression
const calcAge2 = function (birthYear) {
    return 2037 - birthYear;
}
const age2 = calcAge2(1991);

console.log(age1, age2); // 46 46
```
### Practice Assignment
Instructions
1. The world population is 7900 million people. Create a function declaration called `percentageOfWorld1` which receives a `population` value, and returns the percentage of the world population that the given population represents. For example, China has 1441 million people, so it's about 18.2% of the world population.
2. To calculate the percentage, divide the given `population` value by 7900 and then multiply by 100.
3. Call `percentageOfWorld1` for 3 populations of countries of your choice, store the results into variables, and log them to the console.
4. Create a function expression which does the exact same thing, called `percentageOfWolrd2`, and also call it with 3 country populations (can be the same populations).

```JS file:solution fold
function percentageOfWorld1(population) {
    return (population / 7900) * 100;
};

const percentageOfWorld2 = function (population) {
    return (population / 7900) * 100;
};

const percPortugal1 = percentageOfWorld1(10);
console.log(percPortugal1); // 0.12658227848101267
const percChina1 = percentageOfWorld1(1441);
console.log(percChina1); // 18.240506329113924
const percUSA1 = percentageOfWorld1(332);
console.log(percUSA1); // 4.2025316455696204
```
 ---
## Arrow Functions

After learning about Function Declarations and Expressions, there's actually a 3rd one that was released back in ES6/ES2015 called Arrow Functions.
[Arrow Functions - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions): This is a compact alternative to a traditional function expression, with some semantic differences and deliberate limitations in usage…
- Shorter and faster to write than the previous 2 that we've learned.
    - We don't need the curly braces to define the code block
    - The return happens implicitly without having to write the `return` keyword
1. They don't have their own bindings to `this` , `arguments` , or `super` and should not be used as methods.
2. They can't be used as constructors, using the `new` keyword will throw a error.
3. They can't use `yield` within their body and can't be created as a generator function.

What type of function should I use? Should I use arrow for everything since they're easy to write, declaration, or expression?
- No, but it's complicated. There's many different things about all 3, but it depends on the usage. This will go over in a topic in the future.
```JS fold
const calcAge3 = birthYear => 2037 - birthYear;
const age3 = calcAge3(1991);
console.log(age3); // 46

const yearsUntilRetirement = (birthYear, firstName) => {
    const age = 2037 - birthYear;
    const retirement = 65 - age;
    return `${firstName} retires in ${retirement} years.`;
}
console.log(yearsUntilRetirement(1991, 'Kyle')); // Kyle retires in 19 years.
console.log(yearsUntilRetirement(1980, 'Bob')); // Bob retires in 8 years.
```
### Practice Assignment
Instructions
1. Recreate the last assignment, but this time create an arrow function called `percentageOfWorld3`.
```JS file:solution fold
const percentageOfWorld3 = population => (population / 7900) * 100;

const percPortugal3 = percentageOfWorld3(10);
console.log(percPortugal3) // 0.12658227848101267
const percChina3 = percentageOfWorld3(1441);
console.log(percChina3) // 18.240506329113924
const percUSA3 = percentageOfWorld3(332);
console.log(percUSA3) // 4.2025316455696204
```
 ---
## Functions Calling Other Functions

Going to be learning about taking a function and putting them inside another function. This is something that's done all the time in JavaScript, but beginners tend to struggle with this.
```JS fold
// Follow the numbers to understand how it works from the bottom up
function cutFruitPieces(fruit) {
    return fruit * 4;
}

function fruitProcessor(apples, oranges) {
    const applePieces = cutFruitPieces(apples);
    const orangePieces = cutFruitPieces(oranges);

    const juice = `Juice with ${applePieces} piece of apple and ${orangePieces} piece of orange`;
    return juice;
}

console.log(fruitProcessor(2,3));
// "Juice with 8 pieces of apple and 12 pieces of orange"
```
### Practice Assignment
Instructions
1. Create a function called `describePopulation`. Use the function type you like the most. This function takes in two arguments: `country` and `population`, and returns a strings like this: `'China has 1441 million people, which is about 18.2% of the world'`.
2. To calculate the percentage, `describePopulation` calls the `percentageOfWorld1` you created earlier.
3. Call `describePopulation` with data for 3 countries of your choice.

```JS file:solution fold
function percentageOfWorld1(population) {
    return (population / 7900) * 100;
};

const describePopulation = function(country, population) {
    const percentage = percentageOfWorld1(population);

    const description = `${country} has ${population} million people, which is about ${percentage}% of the world.`;
    console.log(description);
    };

describePopulation('Portugal', 10);
describePopulation('China', 1441);
describePopulation('USA', 332);
```
 ---
## Reviewing Functions

To finish learning about functions, we're going to review everything important that's been learned so far to understand functions before moving on.
The `return` element/statement in a function will stop the action of the code even if there's a `console.log` or something else below it.
Review the different functions that were mentioned above and how they work.
```JS fold
const calcAge = function(birthYear) {
    return 2037 - birthYear;
}

const yearsUntilRetirement = function (birthYear, firstName) {
    const age = calcAge(birthYear);
    const retirement = 65 - age;

    if(retirement > 0) {
        console.log(`${firstName} retires in ${retirement} years.`);
        return retirement;
    } else {
        console.log(`${firstName} has already retired! 🥳`);
        return -1;
    }
}

console.log(yearsUntilRetirement(1991, 'Kyle'));
console.log(yearsUntilRetirement(1950, 'Mike'));
// "Kyle retires in 19 years."
// "Mike has already retired! 🥳"
```
 ---
## Coding Exercise #5: Challenge #1
Instructions

Back to the two gymnastics teams, the Dolphins and the Koalas! There is a new gymnastics discipline, which works differently.
Each team competes 3 times, and then the average of the 3 scores is calculated (so one average score per team).
A team **only** wins if it has at least **double** the average score of the other team. Otherwise, no team wins!
**Your tasks:**
1. Create an arrow function `calcAverage` to calculate the average of 3 scores. This function should have three parameters and return a single number (the average score).
2. Create two new variables — `scoreDolphins` and `scoreKoalas`, and assign the value returned from the `calcAverage` function to them (you will need to call this function, and pass scores as arguments).
3. Create a function `checkWinner` that takes the average score of each team as parameters ( `avgDolphins` and `avgKoalas`), and then logs the winner to the console, together with the victory points, according to the rule above. Example: `Koalas win (30 vs. 13)` (use *avgDolphins* and *avgKoalas* instead of hard-coded values).
4. Use the `checkWinner` function to determine the winner for both **DATA 1** and **DATA 2**.
5. Ignore draws this time. Instead, log `No team wins...` to the console if there is no winner.

**TEST DATA 1**: Dolphins scored 44, 23, and 71. Koalas scored 65, 54, and 49.
**TEST DATA 2**: Dolphins scored 85, 54, and 41. Koalas scored 23, 34, and 27.
**👋 OPTIONAL: You can watch my solution in video format in the next lecture

```JS file:solution fold
const calcAverage = (a, b, c) => (a + b + c) / 3;
console.log(calcAverage(3, 4, 5));

const scoreDolphins = calcAverage(44, 23, 71);
const scoreKoalas = calcAverage(65, 54, 49);
console.log(scoreDolphins, scoreKoalas);

const checkWinner = function(avgDolphins, avgKoalas) {
    if (avgDolphins >= 2 * avgKoalas) {
        console.log(`Dolphins win the trophy! 🏆 (${avgDolphins} vs. ${avgKoalas})`);
    } else if (avgKoalas >= 2 * avgDolphins) {
        console.log(`Koalas win the trophy! 🏆 (${avgKoalas} vs. ${avgDolphins})`);
    } else {
        console.log('No team wins... ☹️');
    }
}

checkWinner(scoreDolphins, scoreKoalas);
checkWinner(576, 111);
```
 ---
## Introduction to Arrays

Going to be learning about the first data structure, which is arrays.
[Arrays - MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays)
Array: This object is a type of global object that is used to store data. They consist of an ordered collection or list containing zero or more data types.
- Like a big container and then we can reference them when needed.
- They're 0 based, meaning they start from 0 and on.
- JavaScript accepts a expression and not a statement inside of the square brackets.
- Only primitive are not changeable, but arrays aren't a primitive value. We can always mutate/change the array because of the way arrays work with memory (*Will go over in a future section*). You're unable to replace the entire array.
```JS fold
// Instead of doing this for objects...
const friend1 = 'Michael';
const friend2 = 'Steven';
const friend3 = 'Peter';

// Create an array instead | Literal syntax w/ square brackets
const friends = ['Michael', 'Steven', 'Peter'];
console.log(friends);

// Creating an array function
const years = new Array(1991, 1984, 2008, 2020);

// Logging the first element of the friends array
console.log(friends[0]); // Michael
console.log(friends[2]); // Peter

// Finding how many objects are in an array
console.log(friends.length); // 3 -- not 0 based
console.log(friends[friends.length - 1]); // Peter, 3 - 1 = 2(pos. 2)

// Adding/Removing elements to the friends array
friends[2] = 'Jay'; // Removing Peter and adding Jay to array
console.log(friends);

// Arrays holding different values at the same time
const firstName = 'Kyle';
const kyle = [firstName, 'LastName', 2037 - 1995, 'Student', friends];
console.log(kyle);

// Short Array Exercise
const calcAge = function (birthYear) {
    return 2037 - birthYear;
}

const years2 = [1990, 1967, 2002, 2010, 2018];
const age1 = calcAge(years2[0]);
const age2 = calcAge(years2[1]);
const age3 = calcAge(years2[years2.length - 1]);
console.log(age1, age2, age3); // 40, 70, 19 not in array

const ages = [calcAge(years2[0]), calcAge(years2[1]), calcAge(years2[years2.length - 1])];
console.log(ages); // 40, 70, 19 in a array
```
### Practice Assignment
Instructions
1. Create an array containing 4 population values of 4 countries of your choice. You may use the values you have been using previously. Store this array into a variable called `populations`.
2. Log to the console whether the array has 4 elements or not ( `true` or `false`).
3. Create an array called `percentages` containing the percentages of the world population for these 4 population values. Use the function `percentageOfWorld1` that you created earlier to compute the 4 percentage values.
```JS file:solution fold
function percentageOfWorld1(population) {
    return (population / 7900) * 100;
};

const populations = [10, 1441, 332, 83];
console.log(populations.length === 4);

const percentages = [
    percentageOfWorld1(populations[0]),
    percentageOfWorld1(populations[1]),
    percentageOfWorld1(populations[2]),
    percentageOfWorld1(populations[3])
];

console.log(percentages);
// [0.12658227848101267, 18.240506329113924, 4.2025316455696204, 1.0506329113924051]
```
 ---
## Basic Array Operations (Methods)

JavaScript has some built in functions that we can apply directly on arrays called methods. You can think of them as operations.
[Array Push Method - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push): This method of an array instances adds the specified elements to the end of an array and returns the new length of the array.
- Can mutate the original array

[Array Unshift Method - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift): This method of [Array]() instances adds the specified elements to the beginning of an array and returns the new length of the array.
[Array Pop Method - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop): This metho[d of Array]() instances removes the **last **element from an array and returns that element. This method changes the length of the array.
[Array Shift Method - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift): This metho[d of Array]() instances removes the **first **element from an array and returns that removed element. This method changes the length of the array.
[Array indexOf Method - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf): This method of Array instances returns the first index at which a given element can be found in the array, or *-1* if it is not present.
[Array Includes Method - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes): This method of Array instances determines whether an array includes a certain value among its entries, returning *true* or *false* as appropriate
```JS fold
const friends = ['Michael', 'Steven', 'Peter'];

// Push Method/Function - Adds elements to array
const newLength = friends.push('Jay'); // Adds Jay to the array
console.log(friends);
console.log(newLength);

// Unshift method/function - Adding elements to the beginning of the array
friends.unshift('John'); // Adds John to the beginning
console.log(friends);

// Pop Method/Function - Removing elements in a array
friends.pop();
console.log(friends); // Removes Jay from the array

// Shift Method/Function - Removes the first element in array
friends.shift();
console.log(friends); // Removes John from beginning

// indexOf Method/Function - Where it is in the function
console.log(friends.indexOf('Steven')); // 1
console.log(friends.indexOf('Bob')); // -1

// Includes Method/Function - ES6 method (uses strict equality)
console.log(friends.includes('Steven')); // true, in the array
console.log(friends.includes('Bob')); // false, not in the array

// If an array includes...
if (friends.includes('Peter')) {
    console.log('You have a friend called Peter!'); // True, this runs
}
```
### Practice Assignment
Instructions
1. Create an array containing all the neighboring countries of a country of your choice. Choose a country which has at least 2 or 3 neighbors. Store the array into a variable called `neighbors`.
2. At some point, a new country called 'Utopia' is created in the neighborhood of your selected country, so add it to the end of the `neighbors` array.
3. Unfortunately, after some time the new country is dissolved, so remove it from the end of the array.
4. If the `neighbors` array does not include the country 'Germany', log to the console: `'Probably not a central European country :D'`.
5. Change the name of one of your neighboring countries. To do that, find the index of the country in the `neighbors` array, and then use that index to change the array at that index position. For example, you can search for 'Sweden' in the array, and then replace it with 'Republic of Sweden'.

```JS file:solution fold
const neighbors = ['Norway', 'Sweden', 'Russia'];

neighbors.push('Utopia');
console.log(neighbors);

neighbors.pop();
console.log(neighbors);

if (!neighbors.includes('Germany')) {
  console.log('Probably not a central European country :D');
}

neighbors[neighbors.indexOf('Sweden')] = 'Republic of Sweden;';
console.log(neighbors);
```
 ---
## Coding Exercise #6: Challenge #2

Instructions

Steven wants you to improve his tip calculator, using the same rules as before — tip 15% of the bill if the bill value is between 50 and 300, and if the value is different, the tip is 20%.
**Your tasks:**
1. Write a function `calcTip` that takes any bill value as an input and returns the corresponding tip, calculated based on the rules above (you can check out the code from the first tip calculator challenge if you need to). Use the function type you like the most. Test the function using a bill value of 100.
2. And now let's use arrays! So, create an array called `bills` containing the test data below.
3. Create an array called `tips` containing the tip value for each bill, calculated from the function you created before.
4. **BONUS**: Create an array `totals` containing the total values, so the `bill + tip`.

**TEST DATA**: 125, 555, and 44.
**👋 OPTIONAL: You can watch my solution in video format in the next lecture

```JS file:solution fold
const calcTip = function(bill) {
    return bill >= 50 && bill <= 300 ? bill * 0.15 : bill * 0.2;
}

const bills = [125, 555, 44];
const tips = [calcTip(bills[0]), calcTip(bills[1]), calcTip(bills[2])];
const totals = [bills[0] + tips[0], bills[1] + tips[1], bills[2] + tips[2]];
console.log(bills, tips, totals);
```
 ---
## Introduction to Objects

[Objects - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object): Objects are used to store various keyed collections (or pairs) and more complex entities. Objects can be created using the `Object()` constructor or the object initializer / literal syntax.
Now we're going to learn about another JavaScript data structure called Objects.
Up until now, we've been using arrays as a data structure to store multiple related values within the same variable.
- In an array, you have no way of giving the different elements a name to know what is what. You can only use their order number in the array to know what is what.

Using the curly bracket for an object is called the `Literal Syntax` of an object. **This is most commonly used**.
We should use arrays for more ordered data and objects for more unstructured data that we want to name and retrieve from that object.
The order of properties doesn't matter, as when you use `console.log` , the log will have everything in alphabetical order.
```JS fold
// Example of an Array vs. Object
const kyleArray = [
    'Kyle',
    'LastName',
    2037 - 1995,
    'Student/Learner',
    ['Michael', 'Peter', 'Steven'],
];

const kyleObject = {
    firstName: 'Kyle',
    lastName: 'LastName',
    age: 2037 - 1995,
    job: 'Student/Learner',
    friends: ['Michael', 'Peter', 'Steven'],
};
```
### Practice Assignment
Instructions
1. Create an object called `myCountry` for a country of your choice, containing properties `country`, `capital`, `language`, `population` and `neighbours` (an array like we used in previous assignments).

```JS file:solution fold
const myCountry = {
	country: 'USA',
	countryCapital: 'Washington DC',
	state: 'Florida',
	stateCapital: 'Tallahassee',
	language: ['English', 'Spanish', 'Haitian'],
	population: 22.24,
	neighbors: ['Georgia', 'Alabama', 'The Bahamas'],
};
```
 ---
## Dot vs. Bracket Notation in Objects

Going to learn how to retrieve data and also how to change data in objects using dot and bracket notation.
When should we use the dot notation and when should we use the bracket notation?
- When using something like the very last example below, then you need to use the bracket notation.
- Any other case, use the dot notation which looks cleaner and is easier to use.

Undefined is what we get when we try to access a property that doesn't exist (*refer to below*)
```JS fold
const kyleObject = {
    firstName: 'Kyle',
    lastName: 'LastName',
    age: 2037 - 1995,
    job: 'Student/Learner',
    friends: ['Michael', 'Peter', 'Steven'],
};

/* The dot is an operator that will go to the object and get what we mentioned
Have to use the real property name and not something made up */
console.log(kyleObject.lastName);

// The bracket does the same thing, but you can put any expression you want.
console.log(kyleObject['lastName']);

// Will execute the + op and then go to the object and get the names
const nameKey = 'Name';
console.log(kyleObject['first' + nameKey]);
console.log(kyleObject['last' + nameKey]);

// Getting info from UI prompt in browser
const interestedIn = prompt('What do you want to know about Kyle? Choose between firstName, lastName, age, job, and friends.');
// console.log(kyleObject.interestedIn); // Doesn't work
console.log(kyleObject[interestedIn]); // Returns job


// Getting info from UI
const interestedIn = prompt('What do you want to know about Kyle? Choose between firstName, lastName, age, job, and friends.');
// console.log(kyleObject.interestedIn); // Doesn't work

// If the user doesn't choose the correct object
if (kyleObject[interestedIn]) {
    console.log(kyleObject[interestedIn]); // Returns job
} else {
    console.log('Wrong request! Choose between firstName, lastName, age, job, and friends.');
}

// Adding new properties to an object
kyleObject.location = 'Florida';
kyleObject['twitter'] = '@kylecreate';
console.log(kyleObject);

// Challenge
// "[Kyle] has [3] friends, and his best friend is called [Michael]"
console.log(`${kyleObject.firstName} has ${kyleObject.friends.length} friends, and his best friend is called ${kyleObject.friends[0]}.`);
```
### Practice Assignment
Instructions
1. Using the object from the [previous assignment](https://codingheroes.io/assignments/introduction-to-objects), log a string like this to the console: 'Finland has 6 million Finnish-speaking people, 3 neighboring countries and a capital called Helsinki'.
2. Increase the country's population by two million using dot notation, and then decrease it by two million using bracket notation.

```JS file:solution fold
const myCountry = {
	country: 'USA',
	countryCapital: 'Washington, DC',
	state: 'Florida',
	stateCapital: 'Tallahassee',
	language: ['English', 'Spanish', 'Haitian'],
	population: 22.24,
	neighbors: ['Georgia', 'Alabama', 'The Bahamas'],
};

console.log(`${myCountry.country} has ${myCountry.population} million ${myCountry.language}-speaking people, ${myCountry.neighbors.length} neighbouring countries and a capital called ${myCountry.countryCapital}.`);

myCountry.population += 2;
console.log(myCountry.population);

myCountry['population'] -= 2;
console.log(myCountry.population);
```
 ---
## Object Methods

Going to keep exploring objects and going to learn more about object methods.
Any function that is attached to an object is called a method.
- Think of functions being values, method is a property that can hold a function value.

Remember that we used methods on arrays in a previous section that are similar to how we can manipulate objects.
```JS fold
const kyleObject = {
    firstName: 'Kyle',
    lastName: 'LastName',
    birthYear: 1995,
    job: 'Student/Learner',
    friends: ['Michael', 'Peter', 'Steven'],
    hasDriversLicense: true,

    /* calcAge: function (birthYear) {
		return 2037 - birthYear;
     }

     calcAge: function () {
		// console.log(this);
		return 2037 - this.birthYear;
    } */

    calcAge: function() {
        this.age = 2037 - this.birthYear;
        return this.age;
    },

    getSummary: function() {
        return `${this.firstName} is a ${this.calcAge()}-years old ${kyleObject.job}, and he has ${this.hasDriversLicense ? 'a' : 'no'} driver's license.`
    }
};

// Accessing the calcAge property from the object
console.log(kyleObject.calcAge());

console.log(kyleObject.age);
console.log(kyleObject.age);
console.log(kyleObject.age);

/* Challenge
"[Kyle] is a [42]-year old [student/learner], and he has [a/no] driver's license. (Refer to above function)" */
console.log(kyleObject.getSummary());
```
### Practice Assignment
Instructions
1. Add a method called `describe` to the `myCountry` object. This method will log a string to the console, similar to the string logged in the [previous assignment](https://codingheroes.io/assignments/dot-vs-bracket-notation), but this time using the 'this' keyword.
2. Call the `describe` method.
3. Add a method called `checkIsland` to the `myCountry` object. This method will set a new property on the object, called `isIsland`. `isIsland` will be `true` if there are no neighboring countries, and `false` if there are. Use the ternary operator to set the property.

```JS file:solution fold
const myCountry = {
	country: 'USA',
	countryCapital: 'Washington DC',
	state: 'Florida',
	stateCapital: 'Tallahassee',
	language: ['English', 'Spanish', 'Haitian'],
	population: 22.24,
	neighbors: ['Georgia', 'Alabama', 'The Bahamas'],
    describe: function() {
        console.log(`${this.country} has ${this.population} million ${this.language}-speaking people, ${this.neighbors.length} neighboring countries and a capital called ${this.capital}.`);
    },
    checkIsland: function() {
        this.isIsland = this.neighbors.length === 0 ? true : false;
    }
};

myCountry.describe();
myCountry.checkIsland();

console.log(myCountry);
```
 ---
## Coding Exercise #7: Challenge #3

Instructions

Let's go back to Mark and John comparing their BMIs! This time, let's use objects to implement the calculations! Remember: `BMI = mass / (height \* height)` (mass in kg and height in meters).

**Your tasks:**
1. For each of them, create an object with properties for their full name, mass, and height (Mark Miller and John Smith). Name these objects as `mark` and `john`, and their properties exactly as `fullName`, `mass` and `height`.
2. Create a `calcBMI` method on each object to calculate the BMI (the same method on both objects). Assign the BMI value to a property called `bmi` (lowercase), and also return it from the method.
3. Log to the console who has the higher BMI, together with the full name and the respective BMI. Example: `"John Smith's BMI (28.3) is higher than Mark Miller's (23.9)!"`.

**TEST DATA:** Marks weighs 78 kg and is 1.69 m tall. John weighs 92 kg and is 1.95 m tall.
**👋 OPTIONAL: You can watch my solution in video format in the next lecture
**IMPORTANT:** The `\*\*` operator is not supported in this editor. Please make sure to use exactly this formula `mass / (height \* height)`, and not this one `mass / (height \*\* 2)`

```JS file:solution fold
const mark = {
    fullName: 'Mark Miller',
    mass: 78,
    height: 1.69,
    calcBMI: function () {
        this.bmi = this.mass / (this.height * this.height);
        return this.bmi;
    }
};

const john = {
    fullName: 'John Smith',
    mass: 92,
    height: 1.95,
    calcBMI: function () {
        this.bmi = this.mass / (this.height * this.height);
        return this.bmi;
    }
};

mark.calcBMI();
john.calcBMI();

if (mark.bmi > john.bmi) {
    console.log(`${mark.fullName}'s BMI (${mark.bmi}) is higher than ${john.fullName}'s (${john.bmi}).`)
} else if (john.bmi > mark.bmi) {
    console.log(`${john.fullName}'s BMI (${john.bmi}) is higher than ${mark.fullName}'s (${mark.bmi}.`)
};
```
 ---
## Iteration: The `for` Loop

[for Loop - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for_statement): This loop repeats until a specified condition evaluates to false
When talking about the if/else statement, he mentions that it's a control structure and that there are more control structures in JavaScript. One of the other control structures are loops, which is the last major subject in this section.
Loops are a fundamental aspect of every programming language because they allow us to automate repetitive tasks that we need to perform over and over.
- Using the analogy of a gym where you might lift weights where you do 10 reps of a certain exercise.

```JS fold
console.log('Lifting weights Rep #1 💪🏻'); // 10 times over

// For loops keeps running while condition is true
for (let rep = 1; rep <= 30; rep++) {
    console.log(`Lifting weights rep #${rep} 💪🏻`); // Prints out this line 10 times
}
```
### Practice Assignment
Instructions
1. There are elections in your country! in a small town, there are only 50 voters. Use a `for` loop to simulate the 50 people voting, by logging a string like this to the console (for numbers 1 to 50): `'Voter number 1 is currently voting'`.

```JS file:solution fold
for (let voter = 1; voter <= 50; voter++) {
	console.log(`Voter number #${voter} is currently voting`);
}
```
 ---
## Looping Arrays, Breaking, and Continuing

Going to explore more features of the `for` loop and also create a more useful example.
One of the most used loops is to loop through arrays.
[Continue Statement - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue): This statement terminates execution of the statements in the current iteration of the current or labeled loop, and continues execution of the loop with the next iteration.
[Break Statement - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break): This statement terminates the current loop or `[switch]()` statement and transfers program control to the statement following the terminated statement.
```JS fold
// Example #1
const kyleArray = [
    'Kyle',
    'LastName',
    2037 - 1995,
    'Student/Learner',
    ['Michael', 'Peter', 'Steven'],
    true
];

const types = []; // Empty object

for (let i = 0; i < kyleArray.length; i++) {
    // Reading from kyleArray
    console.log(kyleArray[i], typeof kyleArray[i]);

    // Filling types array
    // types[i] = typeof kyleArray[i];

    // Adding items to the array using push
    types.push(typeof kyleArray[i]);
}

console.log(types);

// Example #2: Calculating ages using loops
const years = [1991, 2007, 1969, 2020];
const ages = [];

for (let i = 0; i < years.length; i++) {
    ages.push(2037 - years[i]);
}
console.log(ages); //46, 30, 68, 17

// Continue & Break Statement
console.log('--- ONLY STRINGS ---');
for (let i = 0; i < kyleArray.length; i++) {
    if (typeof kyleArray[i] !== 'string') continue; // Only logging strings

    console.log(kyleArray[i], typeof kyleArray[i]);
}

console.log('--- BREAK WITH NUMBER ---');
for (let i = 0; i < kyleArray.length; i++) {
    if (typeof kyleArray[i] === 'number') break; // Breaking after a number is found

    console.log(kyleArray[i], typeof kyleArray[i]);
}
```
### Practice Assignment

Instructions
1. Let's bring back the `populations` array from a [previous assignment](https://codingheroes.io/assignments/introduction-to-arrays).
2. Use a `for` loop to compute an array called `percentages2` containing the percentages of the world population for the 4 population values. Use the function `percentageWOrld1` that you created earlier.
3. Confirm that `percentages2` contains exactly the same values as the `percentages` array that we created manually in the [previous assignment](https://codingheroes.io/assignments/introduction-to-arrays), and reflect on how much better this solution is.

```JS file:solution fold
function percentageOfWorld1(population) {
    return (population / 7900) * 100;
};

const populations = [10, 1441, 332, 83];
const percentages2 = [];

for (let i = 0; i < populations.length; i++) {
	const perc = percentageOfWorld1(populations[i]);
	percentages2.push(perc);
}

console.log(percentages2);
// [0.12658227848101267, 18.240506329113924, 4.2025316455696204, 1.0506329113924051]
```
 ---
## Looping Backwards and Loops in Loops

In this section, we're going to do two interesting things
1. Loop over an array backwards
2. Create a loop inside of a loop

Probably won't be doing this all the time, but it's good to know how to do this should you ever need to know.
```JS fold
// Looping Backwards
const kyleArray = [
    'Kyle',
    'LastName',
    2037 - 1995,
    'Student/Learner',
    ['Michael', 'Peter', 'Steven']
];

for (let i = kyleArray.length - 1; i >= 0; i--) {
    console.log(i, kyleArray[i]);
}

// Loop inside of a Loop
for (let exercise = 1; exercise <= 4; exercise++) {
    console.log(`-------- Starting exercise ${exercise} 🏋🏻‍♂️`);

    for (let rep = 1; rep < 6; rep++) {
        console.log(`Lifting weights repetition $${rep} 💪🏻`);
    }
}
```
### Practice Assignment
Instructions
1. Store this array of arrays into a variable called `listOfNeighbors`:
```JS fold
[['Canada', 'Mexico'], ['Spain'], ['Norway', 'Sweden', 'Russia']];
```
2. Log only the neighboring countries to the console, one by one, not the entire arrays. Log a string like `'Neighbour: Canada'` for each country.
3. You will need a loop inside a loop for this. This is actually a bit tricky, so don't worry if it's too difficult for you! But you can still try to figure this out anyway 😉

```JS file:solution fold
const listOfNeighbors = [['Canada', 'Mexico'], ['Spain'], ['Norway', 'Sweden', 'Russia']];

for (let i = 0; i < listOfNeighbors.length; i++)
	for (let y = 0; y < listOfNeighrs[i].length; y++)
		console.log(`Neighbor: ${listOfNeighbors[i][y]}`);
```
 ---
## The `while` Loop

After learning about the `for` loop, there's another type of loop called the `while` loop.
- [While Loop - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while): This statement creates a loop that executes a specified statement as long as the test condition evaluates to true.
- Can be used in more situations than the `for` loop.
```JS fold
// For Loop
for (let rep = 1; rep <= 10; rep++) {
    console.log(`Lifting weights repetition ${rep} 💪🏻`);
}

// While Loop, more versitile than the for loop
let rep = 1;
while (rep <= 10) {
    console.log(`Lifting weights repetition ${rep} 💪🏻`);
    rep++;
}

// Roll dice til we roll a 6
let dice = Math.trunc(Math.random() * 6) + 1;

while (dice !== 6) {
    console.log(`You rolled a ${dice}`);
    dice = Math.trunc(Math.random() * 6) + 1;
    if (dice === 6) console.log('Loop is about to end...');
}

```
### Practice Assignment
Instructions
1. Recreate the challenge from the lecture [Looping Arrays, Breaking and Continuing](https://codingheroes.io/assignments/looping-backwards-and-loops-in-loops), but this time using a `while` loop (call the array `percentages3`).
2. Reflect on what solution you like better for this task: the `for` loop or the `while` loop?

```JS file:solution fold
function percentageOfWorld1(population) {
    return (population / 7900) * 100;
};
const percentages3 = [];

let i = 0;
while (i < populations.length) {
	const perc = percentageOfWorld1(populations[i]);
	percentages3.push(perc);
	i++;
}

console.log(percentages3);
```
 ---
## Coding Exercise #8: Challenge #4

Instructions
Let's improve Steven's tip calculator even more, this time using loops!

**Your tasks:**
1. Create an array called `bills` containing all 10 test bill values.
2. Create empty arrays for the tips and the totals ( `tips` and `totals`)
3. Use the `calcTip` function we wrote before (included in the starter code) to calculate tips and total values ( `bill + tip`) for every bill value in the `bills` array. Use a for loop to perform the 10 calculations!

**TEST DATA:** 22, 295, 176, 440, 37, 105, 10, 1100, 86, and 52.
**BONUS:**
Write a function `calcAverage` which takes an array called `arr` as an argument. This function calculates the average of all numbers in the given array. This is a **DIFFICULT** challenge (we haven't done this before)! Here is how to solve it if you feel like it:
1. First, you will need to add up all values in the array. To do the addition, start by creating a variable `sum` that starts at 0. Then loop over the array using a for loop. In each iteration, add the current value to the `sum` variable. This way, by the end of the loop, you have all values added together.
2. To calculate the average, divide the `sum` you calculated before by the length of the array (because that's the number of elements).
3. Call the function with the `totals` array.

**👋 OPTIONAL: You can watch my solution in video format in the next lecture

```JS file:solution fold
const calcTip = function (bill) {
    return bill >= 50 && bill <= 300 ? bill * 0.15 : bill * 0.2;
}

const bills = [22, 295, 176, 440, 37, 105, 10, 1100, 86, 52];
const tips = [];
const totals = [];

for (let i = 0; i < bills.length; i++) {
    const tip = calcTip(bills[i]);
    tips.push(tip);
    totals.push(tip + bills[i]);
}

console.log(bills, tips, totals);

// Bonus Challenge
const calcAverage = function(arr) {
    let sum = 0;
    for (let i = 0; i < arr.length; i++) {
        // sum = sum + arr[i];
        sum+= arr[i];
    }
    return sum / arr.length;
}
console.log(calcAverage([2, 3, 7])); // 12 / 3 = 4
console.log(calcAverage(totals)); // 275.19
console.log(calcAverage(tips)); // 42.89
```
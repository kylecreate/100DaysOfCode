---
tags:
  - WebDev
---
## Section Intro

We will continue learning about basic JavaScript features and syntax but with a focus on more modern JavaScript. We're going to dive deeper into built in data structures like Objects, Maps, and Arrays and Modern ES6+ operators like destructuring and chaining and how to work with Strings. All this together will give a solid foundation for the upcoming sections and projects.

---
## Section Roadmap

Make sure to watch everything even though you don't have to.

---
## Destructuring Arrays

We're going to start the section by learning about array destructuring.
* Destructuring is an ES6 (ES2015) feature and its a way of unpacking values from an array or object into separate variables. Basically to break down a large data structures into smaller data structures like a variable. For arrays, we use destructuring to retrieve elements from an array and store them into variables in a very easy way.
[Destructuring Assignment - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

```JS file:destructuring-arrays-examples fold
/*
== Basic Destructuring ==
You can extract values from an array and assign them to variables in a single, concise statement.
*/
const fruits = ['apple', 'banana', 'cherry'];
const [first, second, third] = fruits;
console.log(first); // Output: apple
console.log(second); // Output: banana
console.log(third); // Output: cherry

/*
== Skipping Values ==
You can skip over any values in the array that you do not need.
*/
const numbers = [1, 2, 3, 4, 5];
const [first, , third] = numbers;
console.log(first); // Output: 1
console.log(third); // Output: 3

/*
== Default Values ==
If the array is shorter than the list of variables, you can assign default values to avoid `undefined`.
*/
const colors = ['red'];
const [primary, secondary = 'blue'] = colors;
console.log(primary); // Output: red
console.log(secondary); // Output: blue

/*
== Rest Pattern ==
You can use the rest pattern (`...`) to capture the remaining items in an array.
*/
const letters = ['a', 'b', 'c', 'd'];
const [first, ...rest] = letters;
console.log(first); // Output: a
console.log(rest); // Output: ['b', 'c', 'd']

/*
== Nested Destructuring ==
Destructuring can also be nested to extract values from nested arrays.
*/
const nestedArray = [1, [2, 3], 4];
const [one, [two, three], four] = nestedArray;
console.log(one); // Output: 1
console.log(two); // Output: 2
console.log(three); // Output: 3
console.log(four); // Output: 4
```
#### Practice Assignments
```JS file:practice-assignments-1 fold
/*
Q1: Destructure the `books` array into two variables called `firstBook` and `secondBook`.
*/
const [firstBook, secondBook] = books;

/*
Q2: Destructure the `books` array into a variable called `thirdBook`. You must skip the first two books.
*/
const [, , thirdBook] = books;

/*
Q3: Below is the nested `ratings` array that contains two other arrays. Destructure the nested `ratings` arrays into two variables called `rating` and `ratingsCount`. In the result of your destructuring, the `ratings` variable should store a number 4.19, and the `ratingsCount` variable should store a number 144584.
const ratings = [['rating', 4.19], ['ratingsCount', 144584]];
*/
const [[, rating], [, ratingsCount]] = ratings;

/*
Q4: Below is the `ratingStars` array. Destructure it into three variables called `fiveStarRatings`, `oneStarRatings` and `threeStarRatings`. Assign the `threeStarRatings` variable with a default value of 0.
const ratingStars = [63405, 1808];
*/
const [fiveStarRatings, oneStarRatings, threeStarRatings = 0] = ratingStars;
```

---
## Practice Assignments

Provides the link to practice assignments that are for each/most of the videos in this section.

---
## Destructuring Objects

We talked about destructuring arrays, but we can also destructure objects which was also apart of the ES6 (ES2015) update.
[Destructuring Assignment - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

```JS file:destructuring-objects-examples fold
/*
== Basic Syntax ==
The basic syntax for object destructuring is to enclose the variables to be extracted in curly braces `{}`.
*/
const person = { name: 'John', age: 30, city: 'New York' };
const { name, age, city } = person;
console.log(name); // John
console.log(age);  // 30
console.log(city); // New York

/*
== Default Values ==
You can assign default values to variables in case the property does not exist in the object.
*/
const person = { name: 'John', age: 30 };
const { name, age, city = 'Unknown' } = person;
console.log(city); // Unknown

/*
== Renaming Variables ==
Variables can be renamed by using a colon `:` and providing the new name.
*/
const person = { name: 'John', age: 30 };
const { name: fullName, age: years } = person;
console.log(fullName); // John
console.log(years);    // 30

/*
== Nested Object Destructuring ==
You can destructure nested objects by repeating the destructuring pattern.
*/
const person = {
  name: 'John',
  address: {
    city: 'New York',
    zip: '10001'
  }
};
const { name, address: { city, zip } } = person;
console.log(city); // New York
console.log(zip);  // 10001

/*
== Destructuring Function Patterns ==
Object destructuring can also be used in function parameters to extract properties from objects passed as arguments.
*/
function greet({ name, age }) {
  return `Hello, my name is ${name} and I am ${age} years old.`;
}
const person = { name: 'John', age: 30 };
console.log(greet(person)); // Hello, my name is John and I am 30 years old.

/*
== Combining with Rest Operator ==
The rest operator `...` can be used to collect the remaining properties into a new object.
*/
const person = { name: 'John', age: 30, city: 'New York' };
const { name, ...rest } = person;
console.log(name);  // John
console.log(rest);  // { age: 30, city: 'New York' }
```
#### Practice Assignments
```JS file:practice-assignments-2 fold
/* Q1: Destructure the first book object from the `books` array into variables called `title`, `author` and `ISBN` */
const {title, author, ISBN} = books[0];

/* Q2: Each book object has the `keywords` property. Destructure the first book object from the `books` array into a variable called `tags`. The `tags` variable should be assigned with the value of the `keywords` property. */
const {keywords: tags} = books[0];

/* Q3: The seventh book from the `books` array is missing the `programmingLanguage` property. Destructure the seventh book object (`books[6]`) into variables called `language` and `programmingLanguage`. Assign the `programmingLanguage` variable with a default value of 'unknown'. */
const {language, programmingLanguage = 'unknown'} = books[6];

/* Q4: Below are two variables called `bookTitle` and `bookAuthor`. Reassign them with the values of the `title` and `author` properties of the first book object from the `books` array. */
let bookTitle = 'unknown';
let bookAuthor = 'unknown';

({title: bookTitle, author: bookAuthor} = books[0]);

/* Q5: Each book object has a deeply nested `rating` property as illustrated below:
{
	title: 'Algorithms',
	...
	thirdParty: {
		goodreads: {
			rating: 4.41, // <- HERE
			ratingsCount: 1733,
			reviewsCount: 63,
			fiveStarRatingCount: 976,
			oneStarRatingCount: 13
		}
	}
}
Destructure the first book object from the `books` array into a variable called `bookRating`. In the result of your destructuring, the `bookRating` variable should be assigned with the value of the `book[0].thirdParty.goodreads.rating` property.
Please do most of the work on the left side of the assignment operator: `const ... = books[0];` */
const {thirdParty: {goodreads: {rating: bookRating}}} = books[0];

/* Q6: Write a function called `printBookInfo` that has three parameters called `title`, `author` and `year`. This function should work for a single object passed as an argument, and it should log to the console information about the book in this format: `"${title} by ${author}, ${year}"`.
If `year` is undefined (was not passed), it should be assigned with a default value of `'year unknown'`. */
printBookInfo({ title: 'Algorithms', author: 'Robert Sedgewick', year: '2011'});

function printBookInfo({title, author, year = 'year unknown'}) {
	console.log(`${title} by ${author}, ${year});
};
```

---
## The Spread Operator `(...)`

We're going to talk about the amazing spread operator and use it to basically expand an array to all it's element. Basically unpacking the elements at once.
The spread operator in JavaScript is a powerful and versatile feature that allows for the expansion of iterable elements (like arrays, strings, or objects (as of ES2018)) into individual elements.
* The spread operator is represented by three dots (`...`).
* It allows you to spread out elements of an iterable (like an array or object) into individual elements.
[Spread Syntax - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

Some key points
* **Shallow Copy**: The spread operator creates a shallow copy of the array or object. If the original contains nested objects, the nested objects are still referenced.
* **Order Matters**: When combining objects, the order of spreading matters. Properties from the later object can overwrite earlier ones.
```JS file:spread-operator-examples fold
/* Copying an array */
const fruits = ['apple', 'banana', 'orange'];
const moreFruits = [...fruits];
console.log(moreFruits); // ['apple', 'banana', 'orange']

/* Combining Arrays */
const fruits = ['apple', 'banana'];
const vegetables = ['carrot', 'lettuce'];
const food = [...fruits, ...vegetables];
console.log(food); // ['apple', 'banana', 'carrot', 'lettuce']

/* Copying and merging objects */
const person = { name: 'Alice', age: 25 };
const job = { title: 'Developer', company: 'XYZ' };
const personWithJob = { ...person, ...job };
console.log(personWithJob); // { name: 'Alice', age: 25, title: 'Developer', company: 'XYZ' }

/* REAL LIFE EXAMPLE
Imagine you are working on a web application that displays a list of products. You want to create a new array that includes all the existing products and some new ones fetched from an API.
*/
const existingProducts = [
  { id: 1, name: 'Laptop' },
  { id: 2, name: 'Phone' }
];

// Assume this is the new data fetched from an API
const newProducts = [
  { id: 3, name: 'Tablet' },
  { id: 4, name: 'Smartwatch' }
];

const updatedProductList = [...existingProducts, ...newProducts];
console.log(updatedProductList);
/* Output:
[
   { id: 1, name: 'Laptop' },
   { id: 2, name: 'Phone' },
   { id: 3, name: 'Tablet' },
   { id: 4, name: 'Smartwatch' }
] */
```

#### Practice Assignments
```JS file:practice-assignments-3 fold
/* Q1: ach book object has the `author` property, which stores an array of strings (author names) if there are multiple authors, or a single string (author name) if there is just one author.

Declare an array called `bookAuthors`, and fill it with authors of the first two books from the `books` array. The `bookAuthors` array should have just one level (no nested arrays). */
const bookAuthors = [...books[0].author, ...books[1].author];

/* Q2: Write a function called `spellWord` that accepts a single string as an argument. This function should log to the console each letter of the argument separated by a space. */
spellWord('JavaScript');

function spellWord(word) {
	console.log(...word);
}

// "J a v a S c r i p t"
```

---
## Rest Pattern and Parameters

We're going to move on and talk about the rest pattern and rest parameters.
The rest pattern and parameters in JavaScript are powerful tools that allow you to handle function arguments and array elements more flexibly.
[Rest Parameter - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)
[Destructuring Assignments - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

**Rest Parameters**: This allows you to represent an indefinite number of arguments as an array. This is useful when you don't know how many arguments will be passed to a function.
To declare a rest parameter, you use three dots (`...`) followed by the name of the array that will contain the rest of the arguments.
```JS file:beginner-example fold
function sum(...numbers) {
  return numbers.reduce((acc, curr) => acc + curr, 0);
};

console.log(sum(1, 2, 3)); // 6
console.log(sum(1, 2, 3, 4, 5)); // 15
/* In this example, the sum function can take any number of arguments, which are all stored in the numbers array.
```
### Rest Pattern in Destructuring
The rest pattern can also be used in destructuring assignments to collect the "rest" of the elements in an array or properties in an object.
```JS file:rest-pattern-examples fold
/* Array Destructuring */
const [first, second, ...rest] = [1, 2, 3, 4, 5];
console.log(first); // 1
console.log(second); // 2
console.log(rest); // [3, 4, 5]

/* Object Destructuring */
const { a, b, ...rest } = { a: 1, b: 2, c: 3, d: 4 };
console.log(a); // 1
console.log(b); // 2
console.log(rest); // { c: 3, d: 4 }
```
### Real-Life Example
Imagine you're building a function to handle a variety of user inputs for an e-commerce site. Users can apply filters such as category, price range, brand, and so on. Using rest parameters, you can create a flexible function to handle this.
* In this real-life scenario, the `applyFilters` function uses rest parameters to handle an arbitrary number of filter conditions and constructs the final query dynamically.
```JS file:real-example-of-rest-pattern fold
function applyFilters(baseQuery, ...filters) {
  filters.forEach(filter => {
    baseQuery = `${baseQuery} AND ${filter}`;
  });
  return baseQuery;
};

const baseQuery = "SELECT * FROM products WHERE available = true";
const finalQuery = applyFilters(baseQuery, "category = 'Electronics'", "price < 100", "brand = 'Acme'");
console.log(finalQuery);
// SELECT * FROM products WHERE available = true AND category = 'Electronics' AND price < 100 AND brand = 'Acme'
```
#### Practice Assignments
```JS file:practice-assignments-4 fold
/* Q1: Destructure the `keywords` property (array) of the first book from the `books` array into variables called `mainKeyword` and `rest`. The first keyword should be assigned to `mainKeyword`, and the rest of the keywords should be assigned to the `rest` variable (it should be an array). */
const [mainKeywod, ...rest] = books[0].keywords;

/* Q2: Destructure the second book from the `books` array into a variable called `bookPublisher`. The `bookPublisher` variable should be assigned with the value of the `publisher` property of the book object. Assign the rest of the properties to the `restOfTheBook` variable. */
const {publisher: bookPublisher, ...restOfTheBook} = books[1];

/* Q3: Write a function called `printBookAuthorsCount` that has two parameters called `title` and `authors`. The `authors` parameter should accept any number of arguments. This function should log to the console a string formatted like that: `"The book "${title}" has ${authors.length} authors"`. */
printBookAuthorsCount('Algorithms', 'Robert Sedgewick', 'Kevin Wayne');

function printBookAuthorsCount(title, ...authors) {
	console.log(`The book "${title}" has ${authors.length} authors.`);
}
// The book "Algorithms" has 2 authors.
```

---
## Short Circuiting (&& and ||)

We're going back to using two logical operators that we already used before, but we didn't use their full potential yet and how we can use them for something called short circuiting.
[Logical OR (||) - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR)
[Logical AND (&& - MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND)

**Short circuiting** in JavaScript refers to the behavior of logical operators `&&` (AND) and `||` (OR) in which they do not evaluate the second operand if the first operand is sufficient to determine the outcome of the operation.
#### Logical AND (&&)
* **Syntax**: `expression1 && expression2`
* **Explanation**: if `expression1` is falsy, `expression2` is not evaluated and `expression1` is returned. If `expression1` is truthy, `expression2` is evaluated and returned.

<u>Truthy Values</u> include: `true`, non-zero numbers, non-empty strings, objects, and arrays.
<u>Falsy Values</u> include: `false`, `0`, `""` (empty string), `null`, `undefined`, and `NaN`(Not a Number)
```JS file:logical-AND-circuiting-example fold
console.log(false && true);  // false
console.log(true && 'Hello');  // 'Hello'
console.log(null && 'world');  // null
console.log(1 && 0);  // 0
```
#### Logical OR (||)
* **Syntax**: `expression1 || expression2`
* **Explanation**: If `expression1` is truthy, `expression2` is not evaluated and `expression1` is returned. If `expression1` is falsy, `expression2` is evaluated and returned.

```JS file:logical-OR-circuting-example fold
console.log(true || false);  // true
console.log(false || 'Hello');  // 'Hello'
console.log(null || 'world');  // 'world'
console.log(0 || 42);  // 42
```
#### Real Life Example
Suppose you're building a web application where a user can provide their email address. You want to display a default email address if the user hasn't provided one.
* In the example, `getEmailFromUser()` is called. If that returns a falsy value (IE: `null`, `undefined`, or an empty string), the default email of `default@example.com` is used instead.
```JS file:real-life-circuting-example fold
/* Without short citcuting */
let userEmail = getEmailFromUser();
if (!userEmail) {
  userEmail = 'default@example.com';
}
console.log(userEmail);

/* With short circuting */
let userEmail = getEmailFromUser() || 'default@example.com';
console.log(userEmail);
```
#### Practice Assignments
```JS file:practice-assignment-5 fold
/* Q1: Some of the book objects have the `programmingLanguage` property, which specifies what programming language is used in the book, for example

{
	title: 'Algorithms',
	author: ['Robert Sedgewick', 'Kevin Wayne'],
	...
	programmingLanguage: 'Java', (HERE)
};

Write a function called `hasExamplesInJava` that takes a book object from the `books` array as an argument. This function should return `true` if the book uses Java, or a string 'no data available' if it uses other language or no programming language at all. */

function hasExamplesInJava(book) {
	return book.programmingLanguage === 'Java' || 'no data available';
}

/* Q2: Some of the book objects have the `onlineContent` property, which is either `true` or `false`. Loop over the `books` array, and for the books that provide online content, log to the console a string in this format: `"${title}" provides online content`. Use short-circuiting.
 {
	 title: 'Opreating System Concepts',
	 // ... removed for clarity
	 onlineContent: false, (HERE)
 }, */

for (let i = 0; i < books.length; i++) {
	books[i].onlineContent && console.log(`"${books[i].title}" provides online content`);
}
```

---
## The Nullish Coalescing Operator (??)

We're going to learn about the new operator with the funny name of 'Nullish Coalescing Operator'.

[Nullish coalescing operator (??) - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing)
The Nullish Coalescing Operator (`??`) in JavaScript is a logical operator that returns its right-hand operand when its left-hand operand is `null` or `undefined`, and otherwise returns its left-hand operand. It is useful for providing default values in cases where a variable may be `null` or `undefined`. This new feature was introduced in ES2020 (ES11).
```JS file:basic-syntax-example fold
let result = leftOperand ?? rightOperand;
```
* **leftOperand**: The value to check against `null` or `undefined`.
* **rightOperand**: The value to return if `leftOperand` is either `null` or `undefined`.
	* `??` only checks for `null` or `undefined`, unlike the OR operator (`||`) which checks for any falsy value (e.g., `0`, `""`, `false`, `NaN`).
	* It is particularly useful in cases where you want to allow falsy values other than `null` or `undefined`.
#### Basic Usage
In the below example, since `user` is `undefined`, `currentUser` will be assigned to the value of "Guest".
```JS file:basic-nullish-coalescing-usage fold
let user;
let defaultUser = "Guest";

let currentUser = user ?? defaultUser;
console.log(currentUser); // "Guest"
```
#### Differentiating from OR Operator (||)
In the below example, `count` is `0`, which is a falsy value. Using `??`, `result` will be `0` because `0` is not `null` or `undefined`. Using `||`, `result` will be `10` because `0` is falsy.
```JS file:differentiating-from-OR-operator-example fold
let count = 0;
let defaultCount = 10;

let result = count ?? defaultCount;
console.log(result); // 0

result = count || defaultCount;
console.log(result); // 10
```
#### Combining with Optional Chaining
In this example, `??` is used with optional chaining (`?.`) to safely access nested object properties and provide a default value if the property doesn't exist.
```JS file:optional-chaining fold
let user = {
	profile: {
		name: "John";
	}
};

let userName = user.profile?.name ?? "Anonymous";
console.log(userName); // "John"

let user2 = {};
let userName2 = user2.profile?.name ?? "Anonymous";
console.log(userName2); // "Anonymous"
```
#### Real Life Example
Imagine a configuration object for a web application that might not have all the settings defined. In the example, `??` ensures that `timeout` defaults to `3000` and `debugMode` defaults to `false` if they're not provided in the configuration.
```JS file:real-example fold
const config = {
	title: "My Application";
	timeout: null;
	debug: undefined;
};

const appTitle = config.title ?? "Default App";
const timeout = config.timeout ?? 3000; // Default to 3000ms if null/undefined
const debugMode = config.debug ?? false; // Default to false if undefined

console.log(appTitle); // "My Application"
console.log(timeout); // 3000
console.log(debugMode); // False
```
#### Practice Assignments
```JS file:practice-assignment-6 fold
/* Q1: There are objects in the `books` array that don't have the `onlineContent` property at all. Loop over the `books` array, and log a string to the console in this format: `"${title}" provides no data about its online content`. */
for (let i = 0; i < books.length; i++) {
	books[i].onlineContent ?? console.log(`"${books[i].title} provides no data about its online content"`);
}
```

----
## Logical Assignment Operators

Even more modern than the Nullish Coalescing Operator that was just talked about in the previous lecture, are 3 new logical assignment operators that were introduced in ES2021(ES12).
[Logical AND Assignment (&&=) - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND_assignment)
[Logical OR Assignment (||=) - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR_assignment)
[Logical Nullish Assignment (??=)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_nullish_assignment)
[ES2021 Features - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR_assignment#logical_assignment_operators)

Logical Assignment Operators in JavaScript combine logical operations with assignment operations. These operators allow you to perform a logical operation on a variable and assign the result back to that variable in a concise way. The three logical assignment operators are...
* `&&=`
* `||=`
* `??=`
#### Logical AND Assignment (`&&=`)
This operator only assigns a value if the land-hand side is truthy.
```JS file:Logical-AND-examples fold
// Basic Syntax
x &&= y;

// The above is similair to
if (x) {
	x = y;
}

// Example
let a = true;
let b = false;

a &&= 42; // a is 42 because it was true
b &&= 42; // b remains false because b was false
```
#### Logical OR Assignment (`||=`)
This operator assigns a value only if the left-hand-side is falsy.
```JS file:Logical-OR-examples
// Basic Syntax
x ||= y;

// The above is similair to
if (!x) {
	x = y;
}

// Example
let a = false;
let b = null;
let c = 0;

a ||= 42; // a is now 42 because it was false
b ||= 42; // b is now 42 because it was null
c ||= 42; // c is now 42 because it was 0 (falsy)
```
#### Nullish Coalescing Assignment (`??=`)
This operator assigns a value only if the left-hand side is `null` or `undefined`.
```JS file:Nullish-coalescing-examples fold
// Basic Syntax
 x ??= y;

// The above is similair to
if (x === null || x === undefined) {
	x = y;
}

// Example
let a = null;
let b = undefined;
let c = '';

a ??= 42; // a is now 42 because it was null
b ??= 42; // b is now 42 because it was undefined
c ??= 42; // c remaind '' because it wasn't null/undefined
```
#### Real life example
Consider a scenario where you need to set default values for configuration options that might be missing or `null`.
```JS file:real-life-example fold
let config = {
	host: null;
	port: 8080;
	timeout: undefined;
};

config.host ??= 'localhost'; // Sets host to 'localhost' because it was null
config.port ||= 3000; // Port remains 8080 because it was already truthy
config.timeout ??= 5000; // Sets timeout to 5000 because it was undefined

console.log(config); // { host: 'localhost', port: 8080, timeout: 5000 }
```
#### Practice Assignments
```JS file:practice-assignments-7
/* Q1: Some of the book objects from the `books` array are missing the `edition` property. Loop over the `books` array, and assign this property with a number 1 (if it doesn't already exist). Use logical assignment operators. */
for (let i = 0; i < books.length; i++) {
	books[i].edition ||= 1;
}

/* Q2: Some of the book objects from the `books` array have the `highlighted` property, which by default is set to true. Iterate over the `books` array, and if the `thirdParty.goodreads.rating` property is less than `4.2`, reassign it with false.
Use the `&&=` operator (tip: you may also need the `!` operator) */
for (let i = 0; i < books.length; i++) {
	books[i].highlighted &&= !(books[i].thirdParty.goodreads.rating < 4.2)
}
```

----
## Coding Challenge #1

It's time for a break from learning so we can apply everything we've learned so far so we can do our first coding challenge of the section. We're going to build a football (soccer) betting application.
* Instructions
	Your tasks:
	1. Create one player array for each team (variables 'players1' and 'players2')
	2. The first player in any player array is the goalkeeper and the others are field players. For Bayern Munich (team 1) create one variable ('gk') with the goalkeeper's name, and one array ('fieldPlayers') with all the remaining 10 field players
	3. Create an array 'allPlayers' containing all players of both teams (22 players)
	4. During the game, Bayern Munich (team 1) used 3 substitute players. So create a new array ('players1Final') containing all the original team1 players plus 'Thiago', 'Coutinho' and 'Perisic'
	5. Based on the game.odds object, create one variable for each odd (called 'team1', 'draw' and 'team2')
	6. Write a function ('printGoals') that receives an arbitrary number of player names (not an array) and prints each of them to the console, along with the number of goals that were scored in total (number of player names passed in)
	7. The team with the lower odd is more likely to win. Print to the console which team is more likely to win, without using an if/else statement or the ternary operator.

	Test data for 6.: First, use players 'Davies', 'Muller', 'Lewandowski' and 'Kimmich'. Then, call the function again with players from game.scored
```JS file:solution-challenge-1 fold
// 1.
const [players1, players2] = game.players;
console.log(players1, players2);

// 2.
const [gk, ...fieldPlayers] = players1;
console.log(gk, fieldPlayers);

// 3.
const allPlayers = [...players1, ...players2];
console.log(allPlayers);

// 4.
const players1Final = [...players1, 'Thiago', 'Coutinho', 'Periscic'];
console.log(players1Final);

// 5.
const {odds: {team1, x:draw, team2}} = game;
console.log(team1, draw, team2);

// 6.
const printGoals = function(...players) {
	console.log(`${players.length} goals were scored`);
}
printGoals('Davies', 'Muller', 'Lewandowski', 'Kimmich');
printGoals('Davies', 'Muller');
printGoals(...game.scored);

// 7.
team1 < team2 && console.log('Team 1 is more likely to win');
team1 > team2 && console.log('Team 2 is more likely to win');
```

---
## Looping Arrays: the `for-of`Loop

We're going to talk about a new way of looping over arrays that was introduced in ES6 (ES2015).
[for...of Loop - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)

A `for` loop is a control flow statement that allows code to be executed repeatedly based on a given boolean condition. The loop has three main components:
1. **Initialization**: This sets the starting point of the loop.
2. **Condition**: This is evaluated before each iteration. If true, the loop continues. If false, the loop stops.
3. **Increment/Decrement**: This updates the loop variable after each iteration.
```JS file:for-loop-examples fold
// Basic Syntax
for (initalization; condition; increment) {
	// CODE TO EXECUTE
}

/* Looping through an array
When looping through arrays, you typically want to access each element. Here's how you can do it using a `for` loop */
let fruits = ["apple", "banana", "cherry", "date"];

for (let i = 0; i < fruits.length; i++) {
	console.log(fruits[i]); // Lists out all the fruits seperately
}

// Adding the numbers in an array using a for..loop
let numbers = [10, 20, 30, 40, 50];
let sum = 0;

for (let i = 0; i < numbers.length; i++) {
	sum += numbers[i];
}

console.log('Sum:', sum); // Sum: 150
```
#### Real Life Example
Imagine you have an array of order amounts for an e-commerce application, and you want to calculate the total sales for the day.
```JS file:real-life-example
let orders = [23.45, 35.50, 100.99, 49.99, 19.80];
let totalSales = 0;

for (let i = 0; i < orders.length; i++) {
  totalSales += orders[i];
}

console.log('Total Sales for the Day: $', totalSales.toFixed(2));
// Total Sales for the Day: $ 229.73
```
#### Practice Assignments
```JS file:practice-assignment-8 fold
/* Q1: Use the for-of loop to loop over the `books` array and sum the pages of all books. Use the `pageSum` variable below, and the `pages` property of the book objects.
let pageSum = 0; */
let pageSum = 0;

for (let book of books) {
	pageSum += book.pages;
};

/* Q2: Below is the `allAuthors` variable which stores an empty array. Use the for-of loop to fill `allAuthors` with the authors of each book from the `books` array.

Remember that each book object has the `author` property, which can be a string (if there is only a single author) or an array (if there are multiple authors). You may need to use the `typeof` operator. You can also use multiple loops if needed. The `allAuthors` array should have just one level (no nested arrays).

const allAuthors = []; */
for (const book of books) {
	if (typeof book.author === 'string') {
		allAuthors.push(book.author)
	} else {
		for (const author of book.author) {
			allAuthors.push(author);
		}
	}
}

/* Q3: Use the for-of loop together with Array's `entries()` method to log each author from `allAuthors` to the console together with its index. Make the index start from 1, instead of 0. */
for (const [index, author] of allAuthors.entires()) {
	console.log(`${index + 1}. ${author}`);
}
```

----
## Enhanced Object Literals

Maybe you've noticed that we've been talking about ES6 features and more modern features. We're going to continue with that with learning about Enhanced Object Literals.

<u>Enhanced Object Literals</u> are a set of features from ES6 (ECMAScript 2015) that make it easier and more concise to create and manipulate objects in JavaScript. These features include shorthand property names, method definitions, computed property names, and more!
[Object.assign() Method - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)
[Object Initializer - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer)
[Enhanced Object Literals - WebDevSimplified](https://blog.webdevsimplified.com/2021-02/javascript-enhanced-object-literals/)

1. Shorthand Property Names
	* When creating objects, if the property name is the same as the variable name, you can omit the value.
```JS file:shorthand-property-example fold
const name = "John";
const age = 30;

// ES5
const personES5 = { name: name, age: age };

// ES6
const personES6 = {name, age};

console.log(personES6); // { name: "John", age: 30 }
```

2. Shorthand Method Names
	* Methods can be defined in a more concise way.
```JS file:shorthand-method-example fold
// ES5
const personES5 = {
	name: 'John';
	sayHello: function() {
		console.log('Hello');
	}
};

// ES6
const personES6 = {
	name: 'John',
	sayHello() {
		console.log('Hello');
	}
};

personES6.sayHello(); // Hello
```

3. Computed Property Names
	* Allows you to use expressions as property names within object literals.
```JS file:computed-property-example fold
const propName = 'age';

// ES5
var personES5 = {};
personES5[propName] = 30;

// ES6
const personES6 = {
	[propName]: 30
};

console.log(personES6); // { age: 30 }
```

4. `Object.assign()` Method
	* Although not part of object literals per se, it's useful to merge objects.
```JS file:object-assign-example fold
const obj1 = { a:1 };
const obj2 = { b:2 };
const merged = Object.assign({}, obj1, obj2);

console.log(merged); // { a: 1, b: 2 }
```

Real Life Example
Imagine you're developing an application where you need to handle user data. Enhanced object literals can simplify this process. For instance, if you have user data coming from a form, you can easily create an object to represent this data.
```JS file:real-life-example fold
function createUser(firstName, lastName, email) {
	return {
		firstName,
		lastName,
		email,
		fullName() {
			return `${this.firstName} ${this.lastName}`;
		},
	isActive: true
	};
}

const user = createUser('Jane', 'Doe', 'jane.doe@example.com');
console.log(user.fullName()); // Jane Doe
console.log(user); // { firstName: 'Jane', lastName: 'Doe', email: 'jane.doe@example.com', fullName: [Function: fullName], isActive: true}
```
#### Practice Assignments
```JS file:practice-assignments-9 fold
/* Q1: Below is the `bookData` array that contains other arrays. Each inner array consists of the property name (first element), and the value (second element). For example, in `['title', 'Computer Networking: A Top-Down Approach']`, `'title'` is the property name, and `'Computer Networking: A Top-Down Approach'` is meant to be the value assigned to that property name.

Using computed properties, fill the `newBook` object with the properties and values from the `bookData` array. The first one is done already.*/
const bookData [
	['title', 'Computer Networking: A Top-Down Approach'],
	['author', ['James F. Kurose', 'Keith W. Ross']],
	['publisher', 'Addision Wesley'],
];

// Do the rest
const newBook = {
	[bookData[0][0]: bookData[0][1]]
	// ...
};

// Answer //
const newBook = {
	[bookData[0][0]: bookData[0][1]],
	[bookData[1][0]: bookData[1][1]],
	[bookData[2][0]: bookData[2][1]]
};

/* Q2: Below is the `pages` variable. Add it as a property of the `newBook2` object. Use the shorter way. */
const pages = 880;

const newBook2 = {
	title: 'The C Programming Language',
	author: ['Brian W. Kernighan', 'Dennis M. Ritchie'],
	// ...
}

// Answer //
const newBook2 = {
	title: 'The C Programming Language',
	author: ['Brian W. Kernighan', 'Dennis M. Ritchie'],
	pages
};
```

----
## Optional Chaining (`?.`)

We're going to learn about an even new feature of objects and also of a race which is called optional chaining.

Optional chaining is a valuable addition to JavaScript in ES2020 that allows you to simplify the process of accessing nested properties and methods, especially in situations where the data structure might be unpredictable. This feature improves code readability and helps avoid runtime errors related to `null` or `undefined` references.
[Optional Chaining - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining)

1. Basic Syntax
	* **Safety**: Prevents errors when accessing properties or methods on `undefined` or `null` objects.
	* **Short-circuiting**: Stops evaluating the chain as soon as it encounters a `null` or `undefined` value.
	* **Readability**: Simplifies code, making it cleaner and more readable by reducing the need for multiple `if` statements or the `&&` operator.
```JS file:basic-syntax-examples fold
object?.property
object?.[expression]
object.method?.()

let user = {
	profile: {
		name: 'Alice',
		address: {
			city: 'Wonderland'
		}
	}
};

console.log(user?.profile?.name); // Alice
console.log(user?.profile?.address?.city); // Wonderland
console.log(user?.profile?.address?.zipcode); // Undefined
console.log(user?.profile?.age); // Undefined
console.log(user?.job?.title); // Undefined
```

2. Accessing Array Elements
	* The following example demonstrates how to safely access elements within an array using optional chaining.
```JS file:accessing-arrays-example fold
let users = [
	{ name: 'Alice' },
	{ name: 'Bob' }
];

console.log(users?.[0]?.name); // Alice
console.log(users?.[1]?.name); // Undefined
```

3. Calling Methods
	* The example below shows how to use optional chaining to safely call methods that might not exist on an object.
```JS file:calling-methods-example
let user = {
	greet: function() {
		return 'Hello';
	}
};

console.log(user.greet?.()); // Hello
console.log(user.sayBye?.()); // Undefined
```

4. With Functions
	* The example highlights the use of optional chaining when dealing with functions that might be called on potentially `null` or `undefined` objects.
```JS file:with-functions-example fold
let user = {
	name: 'Alice';
	getName: function() {
		return this.name;
	}
}

console.log(user.getName?.()); // Alice
let anotherUser = null;
console.log(anotherUser?.getName?.()); // Undefined
```

Real Life Example
Consider a web application that fetches user data from an API. The data structure can be unpredictable, and some properties might be missing. Optional chaining can be used to handle these uncertainties gracefully.
```JS file:real-example fold
// Simulating user data from an API
let apiResponse = {
  user: {
    name: 'Alice',
    contact: {
      email: 'alice@example.com'
    }
  }
};

// Accessing nested properties safely
let userEmail = apiResponse?.user?.contact?.email;
console.log(userEmail); // alice@example.com

// When a property is missing
let userPhone = apiResponse?.user?.contact?.phone;
console.log(userPhone); // undefined

// w/o optional chaining, (this would require multiple checks)
if (apiResponse && apiResponse.user && apiResponse.user.contact) {
  console.log(apiResponse.user.contact.email); // alice@example.com
}
```
#### Practice Assignment
```JS file:practice-assignment-10 fold
/* Q1: Write a function called `getFirstKeyword` that takes the book object as an argument. This function should return the first keyword from the book's `keywords` property (array) or undefined (if the `keywords` property doesn't exist). It shouldn't throw an error. Use optional chaining for that. */
function getFirstKeyword(book) {
	return book.keywords?.[0];
}
```

----
## Looping Objects: Object Keys, Values, and Entries

We learned about the `for...of` loop to loop over arrays which is an iterable. We can also loop over objects, but in an indirect way.
[Object.keys() Method - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)
[Object.values() Method - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values)
[Object.entries() Method - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries)

In JavaScript, objects are collections of key-value pairs. Looping over these pairs is a common task, and JavaScript provides several methods to do so. The main methods are:
* `Object.keys(obj)`
* `Object.values(obj)`
* `Object.entries(obj)`
#### `Object.keys(obj)`
* This method returns an array of the object's keys
```JS file:keys-method-example fold
const user = { name: 'Alice', age: 25, city: 'Wonderland' };
const keys = Object.keys(user);
console.log(keys); // Output: ['name', 'age', 'city']
```
#### `Object.values(obj)`
* This method returns an array of the object's values.
```JS file:values-method-example
const user = { name: 'Alice', age: 25, city: 'Wonderland' };
const values = Object.values(user);
console.log(values); // Output: ['Alice', 25, 'Wonderland']
```
#### `Object.entries(obj)`
* This method returns an array of the object's key-value pairs in the form of arrays.
```JS file:entries-method-example fold
const user = { name: 'Alice', age: 25, city: 'Wonderland' };
const entries = Object.entries(user);
console.log(entries); // Output: [['name', 'Alice], ['age': 25], ['city', 'Wonderland']]
```
#### Looping through Objects
To loop through these arrays, you can use various loop constructs such as `forEach`, `for...of`, or even a simple `for` loop.
1. Using `for...of` with `object.keys`
```JS file:for-of-keys-example fold
const user = { name: 'Alice', age: 25, city: 'Wonderland' };
for (let key of Object.keys(user)) {
	console.log(key); // Output: 'name', 'age', 'city'
}
```
2. Using `for...of` with `object.values`
```JS file:for-of-values-example fold
const user = { name: 'Alice', age: 25, city: 'Wonderland' };
for (let value of Object.values(user)) {
	console.log(value); // Output: 'Alice', 25, 'Wonderland'
}
```
3. Using `for...of` with `object.entries`
```JS file:for-of-entires-example fold
const user = { name: 'Alice', age: 25, city: 'Wonderland' };
for (let [key, value] of Object.entries(user)) {
	console.log(`${key}: ${value}`); // Output: 'name', 'Alice], ['age': 25], ['city', 'Wonderland'
}
```
#### Real Life Example
Consider a scenario where you have a user profile object, and you want to display the user information in a readable format.
* From the example, we loop through the `userProfile` object using `Object.entries` to create a nicely formatted output for each key-value pair, with the key being capitalized.
```JS file:real-life-example fold
const userProfile = {
  username: 'johndoe',
  email: 'john.doe@example.com',
  age: 30,
  country: 'USA'
};

function displayUserInfo(user) {
  console.log('User Information:');
  for (let [key, value] of Object.entries(user)) {
    console.log(`${key.charAt(0).toUpperCase() + key.slice(1)}: ${value}`);
  }
}

displayUserInfo(userProfile);
/* Outputs
User Information:
Username: johndoe
Email: john.doe@example.com
Age: 30
Country: USA */
```
#### Practice Assignments
```JS file:practice-assignment-11 fold
/* Q1: Below is the `entries` variable that stores an empty array. Use the for-of loop together with the `Object.keys()` method to loop over the `thirdParty.goodreads` property (array) of the first book object from the `books` array. For each key, push a new array that contains that key to the `entries` array.

In the end, the `entries` array should be filled with arrays containing keys:
[['rating'], ['ratingsCount'], ['reviewsCount'], ['fiveStarRatingCount'], ['oneStarRatingCount']] */
const entries = [];

for (const key of Object.keys(books[0].thirdParty.goodreads)) {
	entries.push([key]);
}

/* Q2: Use the for-of loop together with the `Object.values()` method and Array's entries() method to loop over `thirdParty.goodreads` property of the first book from the `books` array.

Push each value to the appropriate inner array in the `entries` array (use `index` from `entries()`). */
for (const [index, value] of Object.values(books[0].thirdParty.goodreads).entries()) {
	entries[index].push([value]);
}

/* Q3: Use the `Object.entries()` method on the `thirdParty.goodreads` property of the first book from the `books` array. Assign the returned value to the variable called `entries2`. */
const entries2 = Object.entires(books[0].thirdParty.goodreads);

/* Q4: Log the `entries` and `entries2` variables to the console, and compare them. They should look the same. */
console.log(entries);
console.log(entries2);
```

----
## Coding Challenge #2

Let's challenge ourselves with the second coding challenge where we continue with the football betting application. It's difficult which is on purpose.
* Instructions
	Your tasks:
	1. Loop over the `game.scored` array and print each player name to the console, along with the goal number (Example: "Goal 1: Lewandowski")
	2. Use a loop to calculate the average odd and log it to the console (We already studied how to calculate averages, you can go check if you don't remember)
	3. Print the 3 odds to the console, but in a nice formatted way, exactly like this:
		* Odd of victory Bayern Munich: 1.33
		* Odd of draw: 3.25
		* Odd of victory Borrussia Dortmund: 6.5
		Get the team names directly from the game object, **don't hardcode them** (except for "draw"). Hint: Note how the odds and the game objects have the same property name 😉
	4. Bonus: Create an object called 'scorers' which contains the names of the players who scored as properties, and the number of goals as the value. In this game, it will look like this: (*doesn't go over this in the video because it would take too long*)
		`{`
			`Gnarby: 1,`
			`Hummels: 1,`
			`Lewandowski: 2`
		`}`
```JS file:coding-challenge-solution fold
// 1.
for (const [i, player] of game.scored.entries())
  console.log(`Goal ${i + 1}: ${player}`);

// 2.
const odds = Object.values(game.odds)
let average = 0;
for (const odd of odds)
  average += odd;
average /= odds.length;
console.log(average);

// 3.
for (const [team, odd] of Object.entries(game.odds)) {
  const teamStr = team === 'x' ? 'draw' : `victory ${game[team]}`;
  console.log(`Odd of ${teamStr} ${odd}`);
}
```

----
## Sets

[Sets - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)
In the past, JavaScript has always had very little built-in data structures, we only had objects and arrays. However, in ES6 (ES2015), two more data structures were introduced;  one of them being `set` is a built-in object in JavaScript introduced in ES6 that allows you to store unique values of any type, whether primitive values or object references.
#### Key Characteristics of Sets
- **Unique Values**: Each value in a `Set` must be unique; duplicate values are automatically removed.
- **Insertion Order**: The values in a `Set` are ordered by their insertion order.
- **No Index Access**: Unlike arrays, `Set` elements are not accessible by index.
- **Iterability**: Sets are iterable, which means you can use them in loops and other functions that operate on iterables.
#### Common Methods and Properties of Sets
- **add(value)**: Adds a new element with the given value to the `Set`.
- **delete(value)**: Removes the specified value from the `Set`.
- **has(value)**: Returns a boolean indicating whether the `Set` contains the specified value.
- **clear()**: Removes all elements from the `Set`.
- **size**: Returns the number of values in the `Set`.
```JS file:sets-examples fold
// Creating a Set
const mySet = new Set();

// Adding values
mySet.add(1);
mySet.add(5);
mySet.add(5); // Duplicate value, will be ignored
mySet.add('hello');
mySet.add({ name: 'John' });

// Checking values
console.log(mySet.has(1)); // true
console.log(mySet.has(99)); // false

// Size of the set
console.log(mySet.size); // 4

// Deleting values from a set
mySet.delete(5);
console.log(mySet.has(5)); // false

// Iterating over a Set
for (let item of mySet) {
    console.log(item);
};

// Clearing a Set
mySet.clear();
console.log(mySet.size); // 0
```
#### Real Life Example
Suppose you're developing a web application and want to ensure that a user can "like" a post only once. You can use a `Set` to keep track of the users who have liked the post.
```JS file:real-life-example fold
class Post {
    constructor() {
        this.likes = new Set();
    }

    like(user) {
        this.likes.add(user);
    }

    unlike(user) {
        this.likes.delete(user);
    }

    getLikes() {
        return this.likes.size;
    }

    hasLiked(user) {
        return this.likes.has(user);
    }
};

const post = new Post();
post.like('User1');
post.like('User2');
post.like('User1'); // User1 tries to like again

console.log(post.getLikes()); // 2
console.log(post.hasLiked('User1')); // true

post.unlike('User1');
console.log(post.getLikes()); // 1
```
#### Practice Assignments
```JS file:practice-assignments-12 fold
/* Q1: Below is the `allKeywords` variable, which stores an empty array. Loop over the `books` array, and fill the `allKeywords` array with the keywords coming from the `keywords` property of each book object. The `allKeywords` array should have just one level (no nested arrays).

Use whatever loop and methods you want. You can also use the spread syntax. In the end, the `allKeywords` array should look more or less like this: `['computer science', 'programming', 'algorithms', 'data structures', ...]`.

const allKeywords = []; */
for (const book of books) {
	allKeywords.push(...book.keywords);
}

/* Q2: The `allKeyword` array contains duplicates. Remove them by creating a Set out of that array. Assign the newly created set to the `uniqueKeywords` variable. */
const uniqueKeywords = new Set(allKeywords);

/* Q3: Add two more keywords to the `uniqueKeywords` set, for example, 'coding' and 'science'. */
uniqueKeywords.add('coding');
uniqueKeywords.add('science');

/* Q4: Delete 'business' from the `uniqueKeywords` set. */
uniqueKeywords.delete('business');

/* Q5: Create an array out of the `uniqueKeywords` set, and assign it to the `uniqueKeywordsArr` variable. */
const uniqueKeywordsArr = [...uniqueKeywords];

/* Q6: Delete all items from the `uniqueKeywords` set. */
uniqueKeywords.clear();
```

----
## Maps: Fundamentals

We learned about sets and now it's time to learn about maps. They're a lot more useful than sets.

[Map - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)
[Map and Set - JavaScript.info](https://javascript.info/map-set)

A `Map` is the collection of key-value pairs where both keys and values can be of any data type. It provides an alternative to using plain objects for storing keyed collections. This feature was released in ES6 (ES2015).

The key features of a Map are...
1. **Ordered Collection**: Maps maintain the order of their elements, meaning you can iterate over items in the order they were inserted.
2. **Flexible Keys**: Unlike objects, where keys must be strings or symbols, Map keys can be of any type, including functions, objects, or any primitive.
3. **Size Property**: Maps have a size property that returns the number of key-value pairs in the Map.
4. **Methods**: Maps come with useful methods like `set`, `get`, `has`, `delete`, `clear`, and `forEach`.
```JS file:creating-using-maps-examples fold
// Creating new Map
let map = new Map();

// Adding key-value pairs to a map
map.set('name', 'John');
map.set(1, 'one');
map.set(true, 'boolean');

// Getting values from maps
console.log(map.get('name')); // John
console.log(map.get(1)); // one

// Checking for existence inside of map (true/false)
console.log(map.has('name')); // true

// Size of the map (number of items in a map)
console.log(map.size); // 3

// Deleting a key-value pair
map.delete('name');
console.log(map.has('name')); // false

// Clearing the map
map.clear();
console.log(map.size); // 0
```
#### Real Life Example
Consider a scenario where you're building a user management system, and want to keep track of user details using their unique user IDs.
```JS file:real-life-example
let users = new Map();

// Adding users
users.set(1, { name: 'Alice', age: 28 });
users.set(2, { name: 'Bob', age: 34 });
users.set(3, { name: 'Charlie', age: 25 });

// Retrieving user by ID
let user = users.get(1);
console.log(user); // { name: 'Alice', age: 28 }

// Checking if a user exists in the map
console.log(users.has(3)); // true
```
#### Practice Assignments
```JS file:practice-assignments-13 fold
/* Q1: Create a new book, but this time, as a Map. Assign it to the `bookMap` variable. Use this array as initial data:
[['title', 'Clean Code'], ['author', 'Robert C. Martin']] */
const bookMap = new Map([['title', 'Clean Code'], ['author', 'Robert C. Martin']]);

/* Q2: Set a new key in `bookMap` called `pages`, and assign it with a number 464. */
bookMap.set('pages', 464);

/* Q3: Get the `title` and `author` values from `bookMap`, and log to the console a string formatted like that: `"${title} by ${author}"`. */
console.log(`"${bookMap.get('title')}" by ${bookMap.get('author')}`);

/* Q4: Get the size of `bookMap`, and log it to the console. */
console.log(bookMap.size);

/* Q5: Check if `bookMap` has the `author` key. and if so, log `"The author of the book is known"` to the console. */
if (bookMap.has('author')) console.log('The author is known');
```

---
## Maps: Iteration

We're going to continue learning about maps with iterations.

[Map - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)
[Map and Set - JavaScript.info](https://javascript.info/map-set)

**Maps** in JavaScript are collections of key-value pairs where both keys and values can be of any type. Maps maintain the insertion order of elements, and each key in a Map is unique.

Their key methods and properties
1. **new Map()**: Creates a new Map object.
2. **set(key, value)**: Adds a new key-value pair.
3. **get(key)**: Retrieves the value for a given key.
4. **has(key)**: Checks if a key exists.
5. **delete(key)**: Removes a key-value pair by key.
6. **clear()**: Removes all key-value pairs.
7. **size**: Returns the number of key-value pairs.
Map Iteration Methods
1. **map.keys()**: Returns an iterator for the keys.
2. **map.values()**: Returns an iterator for the values.
3. **map.entries()**: Returns an iterator for the key-value pairs.
4. **forEach(callback)**: Executes a provided function once for each key-value pair.
```JS file:basic-iteration-map-examples fold
// Create a new Map
let map = new Map();

// Set key-value pairs
map.set('name', 'John');
map.set('age', 30);
map.set('isStudent', true);

// Iterate over map keys
for (let key of map.keys()) {
    console.log(key); // Output: name, age
}

// Iterate over map values
for (let value of map.values()) {
    console.log(value); // Output: John, 30
}

// Iterate over key-value pairs
for (let [key, value] of map.entries()) {
    console.log(`${key}: ${value}`); // Output: name: John, age: 30
}

// Using forEach to iterate over the map
map.forEach((value, key) => {
    console.log(`${key}: ${value}`); // Output: name: John, age: 30
});
```
#### Real Life Example
Imagine you're building a web application where you need to manage user permissions. You can use a Map to associate each user with their permissions. *(Similar to example fundamentals lecture)*
```JS file:real-life-example fold
// Create a Map to store user permissions
let userPermissions = new Map();

// Set user permissions
userPermissions.set('alice', ['read', 'write']);
userPermissions.set('bob', ['read']);
userPermissions.set('charlie', ['read', 'write', 'delete']);

// Check if a user exists
console.log(userPermissions.has('alice')); // Output: true

// Get permissions for a user
console.log(userPermissions.get('charlie')); // Output: ['read', 'write', 'delete']

// Update permissions for a user
userPermissions.set('bob', ['read', 'write']);

// Iterate over user permissions
userPermissions.forEach((permissions, user) => {
    console.log(`${user}: ${permissions.join(', ')}`);
    // Output:
    // alice: read, write
    // bob: read, write
    // charlie: read, write, delete
});
```
#### Practice Assignments
```JS file:practice-assignment-14 fold
/* Q1: Convert the first book object from the `books` array into a Map, and assign it to a `firstBookMap` variable. */
const firstBookMap = new Map(Object.entries(books[0]));

/* Q2: Use the for-of loop to iterate over `firstBookMap`, and log to the console keys that have numbers as values. */
for (const [key, value] of firstBookMap) {
	if (typeof value === 'number') console.log(key);
}
```

----
## Summary: Which Data Structure to Use?

[[Video 120 - Summary - Which Data Structure to Use]]

---
## Coding Challenge #3

* Instructions
	Let's continue with our football betting app! This time, we have a map called `gameEvents` (see below) with a log of the events that happened during the game. The values are the events themselves, and the keys are the minutes in which each event happened (a football game has 90 minutes plus some extra time).

	<u>Your tasks:</u>
	1. Create an array 'events' of the different game events that happened (no duplicates)
	2. After the game has finished, is was found that the yellow card from minute 64 was unfair. So remove this event from the game events log.
	3. Compute and log the following string to the console: "An event happened, on average, every 9 minutes" (keep in mind that a game has 90 minutes)
	4. Loop over `gameEvents` and log each element to the console, marking whether it's in the first half or second half (after 45 min) of the game, like this:
	`[FIRST HALF] 17:
	`⚽ GOAL
```JS file:solution fold
// 1.
const events = [...new Set (gameEvents.values())];
console.log(events);

// 2.
gameEvents.delete(64);

// 3.
console.log(`An event happened, on averagem every ${90 / gameEvents.size } minutes`);
const time = [...gameEvents.keys()].pop();
console.log(time);
console.log(`An event happened, on averagem every ${time / gameEvents.size } minutes`);

// 4.
for (const [minute, event] of gameEvents) {
  const half = minute <= 45 ? 'FIRST' : 'SECOND';
  console.log(`[${half} HALF] ${minute}: ${event}`);
};
```

---
## Working with Strings - Part. 1

Over the next few lectures, we're going to go over how to work with strings and a couple of useful string methods.
```JS file:working-with-strings-pt.1-example fold
const airline = 'TAP Air Portugal';
const plane = 'A320';

console.log(plane[0]); // A
console.log(plane[1]); // 3
console.log(plane[2]); // 2
console.log('B737'[0]); // B
console.log(airline.length); // 16
console.log('B737'.length); // 4

console.log(airline.indexOf('r')); // 6
console.log(airline.lastIndexOf('r')); // 10
console.log(airline.indexOf('Portugal')); // 8
console.log(airline.indexOf('portugal')); // -1 (can't be found)

console.log(airline.slice(4)); // "Air Portugal"
console.log(airline.slice(4, 7)); // "Air"

console.log(airline.slice(0, airline.indexOf(' '))); // TAP
console.log(airline.slice(airline.lastIndexOf(' ') + 1)); // Portugal

console.log(airline.slice(-2)); // al
console.log(airline.slice(1, -1)); // AP Air Portuga

// Writing a function to see if middle seat or not
const checkMiddleSeat = function (seat) {
  // B and E are middle seats
  const s = seat.slice(-1);
  if (s === 'B' || s === 'E')
    console.log('You got the middle seat 🤮');
  else console.log('You got lucky! 🍀');
};

checkMiddleSeat('11B'); // Middle Seat 🤮
checkMiddleSeat('23C'); // Lucky Seat 🍀
checkMiddleSeat('3E'); // Middle Seat 🤮
```
#### Practice Assignments

---
## Working with Strings Pt.2

We're going to continue with some simple string methods
```JS file:working-with-strings-pt.2-example fold
const airline = 'TAP Air Portugal';

console.log(airline.toLowerCase()); // tap air portugal
console.log(airline.toUpperCase()); // TAP AIR PORTUGAL

// Fix capitalization in a name
const passenger = 'jOnAS'; // Jonas
const passengerLower = passenger.toLowerCase();
const passengerCorrect = passengerLower[0].toUpperCase() + passengerLower.slice(1);
console.log(passengerCorrect); // Jonas

// Check user input email (comparing emails)
const email = 'hello@jonas.io';
const loginEmail = '   Hello@Jonas.Io  \n';
// const lowerEmail = loginEmail.toLowerCase();
// const trimmedEmail = lowerEmail.trim();

const normalizedEmail = loginEmail.toLowerCase().trim();
console.log(normalizedEmail); // hello@jonas.io
console.log(email === normalizedEmail); // True

// Replacing
const priceGB = '288,97£';
const priceUS = priceGB.replace('£', '$').replace(',', '.');
console.log(priceUS); // 288.97$

const announcement = 'All passengers come to boarding door 23. Boarding door 23!';
// console.log(announcement.replace('door', 'gate')); // First mention
// console.log(announcement.replaceAll('door', 'gate')); // Both changed
console.log(announcement.replace('/door/g', 'gate')); // /g is globaly changed

// Booleans (includes, starts with, and ends with)
const plane = 'Airbus A320neo';
console.log(plane.includes('A320')); // True
console.log(plane.includes('Boeing')); // False
console.log(plane.startsWith('Air')); // True
console.log(plane.startsWith('A')); // True
if (plane.startsWith('Airbus') && plane.endsWith('neo')); // True

// Practice Exercise (check if baggage is allowed on plane)
const checkBaggage = function (items) {
  const baggage = items.toLowerCase();
  if (baggage.includes('knife') || baggage.includes('gun')) {
    console.log('You are NOT allowed on board');
  } else {
    console.log('Welcome aboard!');
  }
};

checkBaggage('I have a laptop, some Food, and a pocket Knife.'); // NO
checkBaggage('Socks abd camera'); // YES
checkBaggage('Got some snacks and a gun for protection'); // NO
```
#### Practice Assignments


---
## Working with Strings Pt.3

This is the 3rd and final part of working with strings
```JS file:working-with-strings-pt.3-example fold
// Split and Join
console.log('a+very+nice+string'.split('+')); // Split in array
console.log('Jonas LastName'.split(' ')); // Split in array

const [firstName, lastName] = 'Jonas LastName'.split(' ');
const newName = ['Mr.', firstName, lastName.toUpperCase()].join(' ');
console.log(newName); // Mr. Jonas LASTNAME

const capitalizeName = function (name) {
  const names = name.split(' ');
  const namesUpper = [];
  for (const n of names) {
    // namesUpper.push(n[0].toUpperCase() + n.slice(1));
    namesUpper.push(n.replace(n[0], n[0].toUpperCase())); // Similair to above
  }
  console.log(namesUpper.join(' '));
};

capitalizeName('jessica ann smith davis'); // Jessica Ann Smith Davis
capitalizeName('john smith'); // John Smith
capitalizeName('jane doe'); // Jane Doe

// Padding a string (giving a string a deseired length)
const message = 'Go to gate 23!';
console.log('Kyle'.padStart(25, '+')); // +++++++++++++++++++++Kyle
console.log(message.padStart(25, '+').padEnd(30, '+')); // +++++++++++Go to gate 23!+++++

const maskCreditCard = function (number) {
  const str = number + '';
  const last = str.slice(-4);
  return last.padStart(str.length, '*');
}

console.log(maskCreditCard(12345678)); // ****5678
console.log(maskCreditCard(43656457457435)); // **********7435
console.log(maskCreditCard('3335457665234')); // *********5234

// Repeat method
const message2 = 'Bad weather... All departures delayed... ';
console.log(message2.repeat(5)); // Repeats above 5 times

const planesInLine = function(n) {
  console.log(`There are ${n} planes in line ${'✈ '.repeat(n)}`);
}

planesInLine(5); // There are 5 planes in line ✈ ✈ ✈ ✈ ✈
planesInLine(3); // There are 3 planes in line ✈ ✈ ✈
planesInLine(12); // There are 12 planes in line ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈ ✈
```
#### Practice Assignments


---
## Coding Challenge #4

* Instructions
	Write a program that receives a list of variable names written in `underscore_case` and convert them to camelCase.
	The input will come from a text area inserted into the DOM (see code below to insert the elements), and conversion will happen when the button is pressed.

	Test data (pasted to text area, including spaces):
	* `underscore_case`
	* `first_name`
	* `Some_Variable`
	* `calculate_AGE`
	* `delayed_departure`

	Should produce this output (5 separate console.log outputs):
		underscoreCase ✅
		firstName ✅✅
		someVariable ✅✅✅
		calculateAge ✅✅✅✅
		delayedDeparture ✅✅✅✅✅

	Hints:
	* Remember which character defines a new line in the textarea 😉
	* The solution only needs to work for a variable made out of 2 words, like a_b
	* Start without worrying about the ✅. Tackle that only after you have the variable name conversion working 😉
	* This challenge is difficult on purpose, so start watching the solution in case you're stuck. Then pause and continue!

	**Afterwards, test with your own test data!**
```JS file:challenge-4-solution fold
document.body.append(document.createElement('textarea'));
document.body.append(document.createElement('button'));

document.querySelector('button').addEventListener('click', function () {
  const text = document.querySelector('textarea').value;
  const rows = text.split('\n');
 
  for (const [i, row] of rows.entries()) {
    const [first, second] = row.toLowerCase().trim().split('_');
    const output = `${first}${second.replace(second[0], second[0].toUpperCase())}`
    console.log(`${output.padEnd(20)}${'✅'.repeat(i + 1)}`);
  };
});
```

----
## String Methods Practice

Over the last couple of videos, we learned how to work with strings and work on a few challenges. We're going to solve one more challenge and do 1 more exercise.
```JS file:string-methods-practice fold
const flights = '_Delayed_Departure;fao93766109;txl2133758440;11:25+_Arrival;bru0943384722;fao93766109;11:45+_Delayed_Arrival;hel7439299980;fao93766109;12:05+_Departure;fao93766109;lis2323639855;12:30';

const getCode = str => str.slice(0,3).toUpperCase();

for (const flight of flights.split('+')) {
  const [type, from, to, time] = (flight.split(';'));
  const output = `${type.startsWith('_Delayed') ? '🔴' : ''}${type.replaceAll('_', ' ')} from ${getCode(from)} to ${getCode(to)} (${time.replace(':', 'h')})`.padStart(36);
  console.log(output);
}
```
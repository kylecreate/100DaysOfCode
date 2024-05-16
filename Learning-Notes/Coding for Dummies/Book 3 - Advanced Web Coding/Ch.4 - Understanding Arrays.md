---
tags:
  - WebDev
  - ReadingNotes
---
> *"I am large. I contain multitudes."*
> *- Walt Whitman*

Arrays are a fundamental part of any programming language. We discover what they are, how to use them, and what makes JavaScript arrays distinct from arrays in other programming languages.

# <u>Making a List</u>
In earlier chapters of the book involve working with variables that are standalone pieces of data.
```JS file:example fold
const myName = "Chris";
let firstNumber = "3";
var howManyTacos = 8;
```

There may be times when programming in JavaScript (or even another language) where you want to store related data of some sort under a single name. Consider these kinds of lists.
* A list of favorite artists
* A program that selects and displays different quotes from a list of quotes each time the program is run
* A holiday mailing card list
* A list of your top music albums from the past year
* A list of all your family/friends' birthdays
* A shopping list
* A to-do list
* A list of New Year's resolutions
If you're using single-value variables, then you'd need to create and keep track of every variable and item to do any of the above tasks.
* While it could work short-term, you’d quickly run into difficulties.
JavaScript supports the creation of variables containing multiple values known as <u>arrays</u>.

[<u>Array - MDN</u>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) - storing a collection of multiple items under a single variable name, and has members for performing common array operations.
* String values
* Numbers
* Boolean values
* Objects
* Functions
* Arrays, and more!

# <u>Array Fundamentals</u>
Arrays consists of array elements, which are made up of the array name and then an index number that is contained in square brackets.
* An individual value within the array is called an <u>array element</u> which use numbers (index numbers) to access the elements.
```JS file:array-index-numbers fold
myArray[0] = "yellow balloon";
myArray[1] = "red balloon";
myArray[2] = "blue balloon";
myArray[3] = "pink balloon";
```

In the above example, the element with the index number of 0 has a value of "yellow
balloon" and index 3 has a value of "pink balloon".
* By assigning index numbers in arrays, JavaScript gives you the ability to make a single variable name hold a nearly unlimited list of values.

**<span style="color: yellow">TECHNICAL:</span>** There's actually a limit to the number of elements that you can have in an array, which is 4,294,967,295 elements.

Arrays have a few other rules and special properties that you need to be familiar with as you work with them.
1. They're zero-indexed
2. They can store any type of data

## Arrays are zero-indexed
Because JavaScript isn't a person and doesn't have fingers or toes, the first element in an array has the index number of 0.
* Example: `myArray[3]` is the 4th element in this array.
Zero-based numbering is a frequent cause of bugs and confusion to those new to
programming in general, however you will become used to it once you get a better understanding of it.

## **Arrays can store any type of data**
Each element in an array can store any of the data types as well as other arrays, functions, and objects.
You can also store elements that contain different types of data, together, within one array.
```JS file:different-types-of-data-array fold
item[0] = "apple";
item[1] = 4 + 8;
item[2] = 3;
item[4] = item[2] * item[1]; //28
```

# <u>Creating Arrays</u>
You can create arrays in two different ways using...
1. `new` keyword
2. Array literal notation

## Using the `new` keyword method
Using the `new` keyword to create an array uses the `new Array` method to create an array.
```JS file:new-keyword fold
let catNames = new Array("Larry", "Fuzzball", "Mr. Furly");
```

<u><span style="color: yellow">WARNING</span>:</u> This is a perfectly acceptable way to create an array, however many experts recommend against using this method. This is because what happens when you forget to include it? It will change how the program you're creating works.

## <u>Array Literal</u>
A simpler and safer way to create arrays is to use what is called the "array literal method of notation".
```JS file:array-literal-method-of-notation fold
let dogNames = ["Shaggy", "Tennessee", "Dr. Spock"];
```

The use of square brackets and no special keywords in an array means that you’re less likely to leave something out.

# <u>Populating Arrays</u>
You can add values to an array when its first created, or you can simply create an array and then add elements to in the future. Adding elements to an array works the same as creating/modifying a variable, except you have to specify the index number of the element.
```JS file:populating-an-empty-array fold
let peopleList = [];
peopleList[0] = "Chris Minnick";
peopleList[1] = "Eva Holland";
peopleList[3] = "Abraham Lincoln";
```

You don't have to add elements sequentially as you can create a new element out of sequence. Creating an element like the one in the example below creates blank elements for all of the indexes in between 2 and 99. When using the `.length` property to see how long the list is, it returns 100. Even if you've created 4 elements, JavaScript will say the length is 100 because it's based on the highest numbered index rather than the number of elements in the array that you've created.
```JS file:out-of-sequence-array fold
peopleList[99] = "Tina Turner";
peopleList.length; // returns 100
```

# <u>Understanding Multidimensional Arrays</u>
An array that contains an array is called a <u>multidimensional array</u>. You simply add more sets of square brackets to a variable name. They can be difficult to visualize when you first start working with them, but you should be able to get the hang of it.

You can also visualize multidimensional arrays as hierarchal lists or outlines, for example; listing out everything visually and then coding it out.
1. Country
	1. Johnny Cash: Live at Folsom Prison
	2. Patsy Cline: Sentimentally Yours
	3. Hank Williams: I’m Blue Inside
2. Rock
	1. T-Rex: Slider
	2. Nirvana: Nevermind
	3. Lou Reed: Transformer
3. Punk
	1. Flipper: Generic
	2. The Dead Milkmen: Big Lizard in my Backyard
	3. Patti Smith: Easter
```JS file:best-albums-by-genre fold
let bestAlbumsByGenre = []
bestAlbumsByGenre[0] = "Country";
bestAlbumsByGenre[0][0] = "Johnny Cash: Live at Folsom Prison"
bestAlbumsByGenre[0][1] = "Patsy Cline: Sentimentally Yours";
bestAlbumsByGenre[0][2] = "Hank Williams: I'm Blue Inside";
bestAlbumsByGenre[1] = "Rock";
bestAlbumsByGenre[1][0] = "T-Rex: Slider";
bestAlbumsByGenre[1][1] = "Nirvana: Nevermind";
bestAlbumsByGenre[1][2] = "Lou Reed: Tranformer";
bestAlbumsByGenre[2] = "Punk";
bestAlbumsByGenre[2][0] = "Flipper: Generic";
bestAlbumsByGenre[2][1] = "The Dead Milkmen: Big Lizard in my Backyard";
bestAlbumsByGenre[2][2] = "Patti Smith :Easter";
```

# <u>Accessing Array Elements</u>
You can access the elements of an array in the same way that you set them, using the square brackets and index number. For example...
```JS file:accessing-arrays fold
bestAlbumsByGenre[0][1]; // Patsy Cline: Sentimentally Yours
```

## Looping through arrays
There are easier ways to work with all of the elements in an array with the most common being called *loops (covered in B3 Ch.6)* and functions.
## Array Properties
You can access certain data about an array by accessing array properties using dot notation. Type the name of the array, followed by a period, followed by the property you want to access.

| Property      | Return Value                                                            |
| :------------ | :---------------------------------------------------------------------- |
| `prototype`   | Allows the addition of properties and methods to an `Array` object      |
| `constructor` | A reference to the function that created the `Array` object’s prototype |
| `length`      | Either returns or sets the number of elements in an array               |
The most commonly used array property is `length`. Its purpose is to provide the number of elements in an array, either defined or undefined.
```JS file:array-length-property
let myArray = [];
myArray[2000] = "surprise!";
myArray.length; // returns 2001

myArray.length; // returns 2001
myArray.length = 10;
myArray.length; // returns 10
```

## Array Methods
Array methods provide handy ways to manipulate and work with arrays. Below is a list of commonly used methods with their descriptions/values of what they can produce.

| Method        | Return Value                                                                                                            |
| :------------ | :---------------------------------------------------------------------------------------------------------------------- |
| `concat`      | A new array made up of the current array, joined with other array(s) and/or value(s).                                   |
| `every`       | `true` if every element in the given array satisfies the provided testing function.                                     |
| `filter`      | A new array with all of the elements of a current array that test true by the given function.                           |
| `forEach`     | Completes the function once for each element in the array.                                                              |
| `indexOf`     | The first occurrence of the specified value within the array. Returns `-1` if the value is not found.                   |
| `join`        | Joins all the elements of an array into a string.                                                                       |
| `lastIndexOf` | The last occurrence of the specified value within the array. Returns `-1` if value is not found.                        |
| `map`         | A new array with the result of a provided function on every element in the array.                                       |
| `pop`         | Removes the last element in an array.                                                                                   |
| `push`        | Adds new items to the end of an array.                                                                                  |
| `reduce`      | Reduces two values of an array to a single value by applying a function to them (from left to right).                   |
| `reduceRight` | Reduces two values of an array to a single value by applying a function to them<br>simultaneously (from right to left). |
| `reverse`     | Reverses the order of elements in an array                                                                              |
| `shift`       | Removes the first element from an array and returns that element, resulting in a<br>change in length of an array.       |
| `slice`       | Selects a portion of an array and returns it as a new array.                                                            |
| `some`        | Returns `true` if one or more elements satisfy the provided testing function.                                           |
| `sort`        | Returns an array after the elements in an array are sorted (default sort order is alphabetical and ascending).          |
| `splice`      | Returns a new array comprised of elements that were added or removed from a<br>given array.                             |
| `toString`    | Converts an array to a string.                                                                                          |
| `unshift`     | Returns a new array with a new length by the addition of one or more elements.                                          |
## Using array methods
The syntax for using an array methods differs depending on the particular method you are trying to use. Using dot notation, you can access the functionality of every array method the same way you access properties.
```HTML file:JS-array-methods-in-action fold
<body>
	<script>
		let animals = ['tiger', 'bear'];
		let fruit = ['cantaloupe', 'orange'];
		let dishes = ['plate', 'bowl', 'cup'];
		let fruitsAndAnimals = fruit.concat(animals);
		document.write(fruitsAndAnimals + '<br>');
		let whereIsTheTiger = animals.indexOf('tiger');
		document.write('The tiger has an index number of: ' + whereIsTheTiger + '<br>');
	</script>
</body>
```
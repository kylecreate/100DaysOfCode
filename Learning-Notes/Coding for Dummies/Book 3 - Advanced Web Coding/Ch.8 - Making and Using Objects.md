---
tags:
    - learning-notes
    - code-for-dummies
    - JavaScript
obsidianUIMode: preview
---
> “We cannot do anything with an object that has no name.”
> — Maurice Blanchot, “Literature and the Right To Death”

Going to be learning about why, how, and what is so special about giving our programs objects to use.
## Object of My Desire
In addition to the seven primitive data types, JavaScript also has another data type called *objects* which contain data and functionality in reusable components.
A better way to understand how objects work in JavaScript, it's good to compare these with physical, real-life things, such as a guitar.
- Has 6 strings
- Black and white
- Electric
- Solid body

The thing you can do with (or that can be done) to a guitar…
- Strum the strings
- Tighten the strings
- Loosen the strings
- Increase the volume
- Decrease the volume
- Adjust the tone

If the example guitar were a JavaScript object and not a real-life object, the thing that it does would be *methods* and the things that make it up (like the strings and body type of it) would be considered its *properties*.
- Both methods and properties are written the same way as name-value pairs with a colon separating the two. When a property has a *function* as the value, it's known as a *method*.

An example of what the guitar's properties would look like as a JavaScript object…
```JS fold
let guitar = {
	bodyColor: "Black",
	scratchPlateColor: "White",
	numberOfStrings: 6,
	brand: "Yamaha",
	bodyType: "Solid",
	strum: function() {...},
	tune: function() {...}
};
```

## Creating Objects
There's 4 ways to create a JavaScript object…
1. Writing an object literal
2. Using the object constructor method
3. Using the `object.create` method
4. Using the `class` keyword

Whichever one is used depends on the circumstances on the project.
### Defining objects with object literals
The object literal method of creating objects starts with a standard variable definition, using the `var`, `let`, or `const` keyword, followed by the assignment operator. The right side of the statement will have curly braces with commas separating the name and value pairs.
```JS fold
const person = {eyes: 2, feet: 2, hands: 2, eyeColor: "blue"};
```

When creating your object and you're unsure of the properties that you will be using, you can add them at a later time.
```JS fold
const person = {};
person.eyes = 2;
person.hair = "brown";
```

Another thing about objects is that similar to arrays, they can contain multiple different data types as the values of properties.
**TECHNICAL**: The not-so-well-kept secret to really understanding JavaScript is in knowing that arrays and functions are types of objects and that the number, string, and Boolean primitive data types can also be used as objects. Objects and arrays are often initialized using the `const` keyword

### Defining objects with a constructor function
The second way to define an object is by using a constructor function. The method uses the *new* keyword to create an object from a function.
```JS fold
function Person(name, age){
	this.name = name;
	this.age = age;
}
const mom = new Person("NameHerem", 55);
```

This function can be used to create multiple objects from the same template.
Each object using the *person* function from the example will have a property called `name` and `age`.

### Making objects with class
A class is a template used for objects which was introduced in ES2015/ES6. They're similar to constructor functions, but you can use it to write a class.
```JS fold
class Person {
	constructor(name, age) {
		this.name = name;
		this.age = age;
	}
}
const neighbor = new Person('Murray', 6);
```

An interesting things about using classes is that you can create new classes
that are based on other classes.
```JS fold
const Teacher extends Person {
	constructor(name,age,subject) {
		super(name,age);
		this.subject = subject;
	}
}
const myTeacher = newTeacher('Jill', 39, 'art');
```
Creating a new object based on the `teacher` class, use the new keyword and pass the tree arguments inside of that. Inside of the constructor function, the class uses the *super* function to call the `person` class and run that function with the arguments provided to the `Teacher` function.

### Using `Object.create`
This method of making objects take an existing object as the parameter and returns a new object with the object that it was created from as a prototype.
```JS fold
const cat = {
	sound: 'meow';
	sleep: function () {
		console.log('The cat is asleep...');
	},
};
const sparky = object.create(cat);
sparky.name = 'Sparky';
sparky.age = 10;
```

## Retrieving and Setting Object Properties
After you create an object and define its properties, you’ll want to be able to retrieve and change those properties. There's two ways to do this…
1. Dot Notation
2. Square Brackets Notation
### Using dot notation
With dot notation, the name of an object is followed by a period (*or dot*), followed by the name of the property that you want to get or set.
- If the property doesn't exist already, the statement will create it. If it already does exist, then it will update it with a new value.
```JS fold
person.firstName = "Glenn";
```

To retrieve the value of a property, you would use the exact same syntax, but you would move the object and property names (called the *property accessor*) into a different position in the statement.
```JS fold
let fullName = person.firstName + person.lastName;
```

**TIP**: Dot notation is generally faster to type and easier to read. It’s an easier way to set and retrieve object property values.

### Using Square Bracket Notation
Square bracket notation uses square brackets after the object name in order to get and set property values.
```JS fold
person["firstName"] = "Iggy";
```

Square bracket notation has a couple of capabilities that dot notation doesn’t. The main case being that you can use variables inside of a square bracket notation for cases where you don't know the name of the property you want when writing your program.
```JS fold
let personProperty = "firstName";
person[personProperty] = "Iggy";
```

An example of an object called chair that loops through each of the properties and asks for a user to input values for each one.
```JS fold
let myChair = {
	cushionMaterial: '',
	numberOfLegs: '',
	legHeight: '',
};

function configureChair() {
	let userValue;
	for (const property in myChair) {
		if (myChair.hasOwnProperty(property)) {
			userValue = prompt('Enter a value for ' + property); myChair[property] = userValue;
		}
	}
}
function writeChairReceipt() {
	document.write(
		'<h2>Your chair will have the following configuration:</h2>'
	);
	for (const property in myChair) {
		if (myChair.hasOwnProperty(property)) {document.write(property + ': ' + myChair[property] + '<br>');
		}
	}
}
configureChair();
writeChairReceipt();
```

## Deleting Properties
You can delete properties from objects by using the *delete* operator.
```JS fold
const myObject = {
	var1 : "the value",
	var2 : "another value",
	var3 : "yet another"
};

// delete var2 from myObject
delete myObject.var2;

// try to write the value of var2
document.write(myObject.var2); // result is an error
```

## Working with Methods
Methods are properties with functions for their values that you define a method the same way that you define any function with the only difference being that a method is assigned to a property or object.
```JS fold
const sandwich = {
	meat: '',
	cheese: '',
	bread: '',
	condiment: '',
	makeSandwich: function (meat, cheese, bread, condiment) {
		this.meat = meat;
		this.cheese = cheese;
		this.bread = bread;
		this.condiment = condiment;
		let mySandwich = `${sandwich.bread}, ${sandwich.meat}, ${sandwich.cheese}, ${sandwich.condiment}`; // ES2015
	return mySandwich;
	},
};
```

**TECHNICAL**: JavaScript has a newer way of creating strings that incorporate variables than the method shown in the preceding example called *template literals* which was released in ES6/ES2015. You can re-write the above code in the following example.
### Using `this`
The `this` keyword is a shorthand for referencing the containing object of a method. It becomes useful when you have a function that may apply to multiple different objects.

## An Object-Oriented Way to Become Wealthy: Inheritance
When creating objects, you’re not just limited to creating specific objects, such as a guitar, car, cat, or a sandwich. The real beauty of objects is that you can use them to create types of objects, from which other objects can be created.
```JS fold
const person = new Object();
person.eyes = 2;
person.ears = 2;
person.arms = 2;
person.hands = 2;
person.feet = 2;
person.legs = 2;
person.species = "Homo sapien";
```

Now that we have specific properties for the `person` object, you can technically create a specific person such as Willie Nelson or others that are people. You can modify an object using the `prototype` property from the `Object` .
```JS fold
function Person() {
	this.eyes = 2;
	this.ears = 2;
	this.arms = 2;
	this.hands = 2;
	this.feet = 2;
	this.legs = 2;
	person.species = "Homo sapien";
}

const willieNelson = new Person();
const johnnyCash = new Person();
const pastyCline = new Person();

// A person might need more properties!
Person.prototype.knees = 2;
Person.prototype.toes = 10;
Person.prototype.elbows = 2;

// Checking the values of existing objects for new properties
document.write (pastyCline.toes); // 10
```
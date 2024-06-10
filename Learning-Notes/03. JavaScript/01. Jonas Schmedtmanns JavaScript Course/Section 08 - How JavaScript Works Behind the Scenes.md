---
tags:
  - WebDev
---
## Section Intro

In this section, we'll go behind the scenes of JavaScript and learn how the language actually works. Throughout the section, we're going to use the basic JavaScript knowledge we've learned from the first few sections and learn how exactly everything works under the hood. This is very important to know because it will allow you to understand other's code and make your code better. It will also make you confident and a better developer.
Knowing how JavaScript works will set you apart from other Jr. developers.
Don't be scared of theory!

---
## Section Roadmap

Everything is important to watch in this section. The optional videos are Hoisting and TDZ in Practice and the `this` keyword in practice. *I'll be watching them...*

---
## <u>An High-Level Overview of JavaScript</u>

As an intro to the theory section, we're going to start with a high-level overview of the language to get an understanding of most of the things to master in the language.

### What is JavaScript: <u>Revisited</u>
<u>JavaScript</u>: A high-level, object-oriented, multi-paradigm programming language.
* This is correct, but it's just the tip of the surface. What about the definition below?
<u>JavaScript v2</u>: A <u>high-level, prototype-based object oriented, multi-paradigm, interpreted or just-in-time compiled, dynamic single threaded, garbage-collected</u> programming language with <u>first-class functions</u> and a non-blocking <u>event loop concurrency model</u>.
* An unreadable sentence for fun!
* Everything underlined is what we're going to be learning about.
* This is the big picture before getting started and to introduce some topics that are good to know.
### Deconstructing the definition from above
<u>High Level</u>
* Every computer need some sort of hardware resources like memory (RAM) and a CPU.
	* There's low level languages (*like C*), where you have to manage the resources manually
	* There's high level languages (*like JS and Python*), the developer doesn't have to worry since everything happens manually.
		* High level language is easy to learn and use, but programs won't run as fast or optimized as C programs.
<u>Garbage-collected</u>
* An algorithm inside of the JavaScript language engine which automatically removes unused objects from the computer's memory to not clog it up.
	* Like a janitor who cleans from time to time.
<u>Interpreted or just-in-time compiled</u>
* A computers processor only understands 0's and 1's known as machine code which isn't practical to write as humans, which is why we write what we can understand. (*More about this in the future...*)
	* When writing JavaScript code, it then converts it to machine code which we don't have to compile like other languages. It happens inside of the engine.
<u>Multi-paradigm</u>
* A *paradigm* is an approach and mindset of structuring code, which will direct your coding style and technique in a project that uses a certain paradigm. (*More about this in the future...*)
* Some popular paradigms are... (JavaScript does all 3 and we can do whatever we want to use)
	1. Procedural programming (What we've been doing so far)
	2. Object-oriented programming (*OOP*)
	3. Functional programming (*FP*)
* You can also classify paradigms as <u>imperative</u> or <u>declarative</u>.
<u>Prototype-based object-oriented</u>
* Almost everything in JavaScript is an object except for primitive values (strings, numbers, `bigInt`, Boolean, undefined, symbols, and null).
* Wondering how you can create an array and then use the push method?
	* Prototypal inheritance: We create arrays from an array blueprint like a template or prototype. They then inherent the methods from the prototype to use them.
<u>First-class functions</u>
* In a language with **first-class functions**, functions are simply <u>treated as variables</u>. We can pass them into other functions and return them from other functions.
	* Extremely powerful which allows us to use some powerful techniques and also allows for functional programming (one of the paradigms). We've used this already without knowing about it (closing the modal from a previous section).
<u>Dynamic</u>:
* Dynamic in terms of dynamically typed
	* We don't assign data types to variables and only becomes known when JavaScript executes a function.
	* The type of variables can easily be changed as we reassign variables (what dynamically typed means)
		* In languages like C, Java, and Ruby, you have to mainly assign types to variables. This then prevents bugs from happening which is why others think that JavaScript should do the same. But, if you'd like to do that, then you can use TypeScript.
<u>Single-threaded and Non-blocking event loop</u>:
* Concurrency model: How the JavaScript engine handles multiple tasks happening at the same time.
	* Why do we need that?
		* JavaScript runs in one single thread so it can only do one thing at a time. We need a way of handling multiple things at the same time.
		* In computing, a thread is like a set of instructions that is executed in the computer's CPU which is where our code is executed in the machine's processor.
	* What if there's a long-running task?
		* This sounds like it would block the single thread as we want non-blocking behavior.
	* But, how do we achieve that? (Oversimplification that we will come back to in the future)
		* By using an **event loop** which takes long running tasks, executes them in the "background", and then puts them back in the main thread once everything is finished.
---
## <u>The JavaScript Engine and Runtime</u>

[[Video 90 - JS Engine and Runtime]]
### What is a JavaScript Engine?
The JavaScript engine is a computer program that executes JavaScript code. There's a lot of steps in doing that, which is what the engine does.
* The most well known engine used is Google's V8 engine which powers <u>Google Chrome</u> and <u>NodeJS</u>.
	* All the other browsers have other engines that they use
		* Safari: JavaScriptCore
		* Firefox: SpiderMonkey
		* Edge: Chakra
* What's most important is to understand its components and how it works.
	* Any JavaScript engine always contains a `callstack` and a heap
		* The `callstack` is where our code is executed using executed context
		* The heap is an unstructured memory pool which stores all the objects our application needs.
### Computer Science Sidenote: Compilation vs. Interpretation
Mentioned in the previous section, the computer's processor only understand 0's and 1's, therefore every computer program needs to be converted into machine code.

<u>Compilation</u>: The entire code is converted into machine code at once, and then written to a portable binary file that can be executed by a computer.
* Source Code → Step 1: Compilation → **Portable File**: Machine Code → Step 2: Execution → Program runs
	* *Step 2 can happen way after compilation!*

<u>Interpretation</u>: Interpreter runs through the source code and executes it line by line. (JavaScript isn't this anymore)
* Source Code → Step 1: Execution Line by Line → Program running
	* The source code still needs to be converted into machine code, but it happens before its executed and not ahead of time.

<u>Just-in-time (JIT) Compilation</u>: Entire code is converted into machine code at once, and then executed immediately. (What modern JavaScript is now)
* Source Code → Step 1: Compilation → Machine Code → Step 2: Execution → Program runs
	* The portable file is instead turned into machine code and execution of it happens immediately.
### Modern Just-in-time Compilation of JavaScript
*~~"JavaScript is an interpreted language"~~*
A piece of JavaScript code enters the engine
* Step 1: Parsing the code (read the code) into a data structure called AST (Abstract Syntax Tree)
	* Splits each line of code into pieces that are meaningful to the language (`const` or `function` keywords) and saves all the pieces into the tree in a structured way. It also checks if there's any syntax error. It will later be turned into machine code. The AST has **nothing to do** with the DOM tree and not related in any way.
* Step 2: Compilation which takes the generated AST and compiles it into machine code. (Just-in-time compilation)
	* The code is being optimized are re-compiled during the already running program execution which can be done multiple times. The un-optimized code is swept away for the new optimized code without stopping the execution.
* Step 3: The machine code then gets executed right away. (Happens in the Call Stack)
All three of these happens in some special threads inside the engine that we can't access from the code. Completely separate from the main thread.
[[Visual example of Just-In-Time Compilation of JavaScript.canvas|Visual example of Just-In-Time Compilation of JavaScript]]
### The Bigger Picture: JavaScript Runtime
We're going to look at what a JavaScript Runtime is and in particular the most common one which is the browser. By doing this, we can get the bigger picture of how all the pieces fit together when using JavaScript.
* We can compare the above sentences to an container that includes all the things that we need to use (in this case, inside the browser).
* The heart of any JavaScript Runtime is a JavaScript Engine (the one we've been talking about).
	* Without an engine, there is no runtime or JavaScript at all. The engine is not enough.
* Because the engine is not enough, in order to work properly we also need access to the Web APIs (everything related to the DOM, Timers, `FetchAPI`, and more).
	* Web APIs are functionalities that are provided to the engine accessible using the global `window` object. These aren't part of the JavaScript language itself, but the runtime.
* A typical JavaScript runtime also includes a "Callback Queue" which is a data structure that includes all the callback functions that are ready to be executed.
	* We attach event handler functions to DOM elements like a button to react to certain events, also known as <u>Callback Functions</u>. As the event happens (such as a click), the callback function will be called.
---
## <u>Execution Contexts and The Call Stack</u>

[[Video 91 - Execution Contexts and The Call Stack]]
In this lecture, we're going to answer the question of how JavaScript code is executed. We already know it happens in the call stack in the JavaScript Engine, but let's dig deeper!
### What is an Execution Context?
From using the example above (The Bigger Picture: JavaScript Runtime), our code has just finished compiling.
1. The code is now ready to be executed.
2. The **global execution context** (for top-level code) is created. [[Top-Level Code Example.canvas|Top-Level Code Example]]
	* Top-level code <u>is not</u> inside any function. Only the code outside of functions will be executed when they are called.
3. <u>Execution Context</u> is an abstract concept and is defined as an environment in which a piece of JavaScript is executed. It stores all the necessary information for some code to be executed (local variables or arguments passed into a function).
	* Imagine ordering a pizza from a take out place. The pizza comes in a box and some other stuff is necessary to eat the pizza (utensils and a receipt).
		* The pizza is the JavaScript code to be executed
		* The box is the pizza "execution context"
		* Eating the pizza happens inside the box which is then the environment for eating pizza and also contains utensils and a receipt to eat the pizza (or execute the code).
	* In any JavaScript project no matter how large it is, there's <u>only ONE global execution context</u> (EC): Default context created for code that is not inside any function (top-level).
4. The code is the executed inside a global execution. It's the computer's CPU processing the code it received.
5. Execution of functions and waiting for callbacks start.
	* **One execution context <u>per function</u>** for each function call, a new execution context is created.
	* All together make the <u>call stack</u>.
		* An example of this is a click event callback
### Execution Context in Detail
#### What's inside execution context?
1. Variable Environment
	* `let`, `const`, `var` declarations are stored
	* Functions are stored
	* `arguments` object
2. Scope chain (*going to learn about later in the section*)
	* Consists of references to variables that are located outside of the current function.
	* To keep track of this, it's stored in each execution context.
3. Each context also gets a variable called `this` keyword (*going to learn about later in the section*)
All 3 of the above mentioned are generated during the "creation phase", right before execution.
Something to keep in mind is that execution context belonging to arrow functions do not get their own arguments keyword or the `this` keyword.
* Instead, they can use the `arguments` object and the `this` keyword from their closest regular function parent.

Going to try and simulate the creation phase for the following code example. We will get 1 global execution context and 1 for each function.
```JS
const name = 'Jonas';

const first = () => {
	let a = 1;
	const b = second(7, 9);
	a = a + b;
	return a;
};

function second (x, y) {
	var c = 2;
	return c;
}

const x = first();
```
Global (contains all the code of the function, x is unknown because it's the first function that is unknown as you need to run the `first()` function)
* Name declaration: `name = 'Jonas'`
* first = `<function>`
* second = `<function>`
* x = `<unknown>`
`first()` (the `b` variable requires the function to run in order to get the number)
* a = 1
* b = `<unknown>`
`second()`
* c = `2`
* arguments = `[7, 9]` - an array of passed arguments that is available in all "regular" functions and not arrow functions.
### The Call Stack
Remember that the Call Stack together with the memory heap makes up the JavaScript engine itself. But, what is the Call Stack?
* The Call Stack is a "place" where execution contexts get stacked on top of each other to keep track of where we are in the execution.
	* The execution context that is on the top of the stack is the one that's currently running. When it's finished running, the execution will go back to the previous execution.
		* This is similar to having boxes stacked on top of each other and then removing the box on top to a new one.
---
## <u>Scope and The Scope Chain</u>

Going to continue learning about the behind the scenes of JavaScript. The next video/section will be a coding lecture.
### Scoping and Scope in JavaScript: Concepts
We learned in the last lecture that each execution context has a variable environment, a scope chain, and a `this` keyword. Let's learn what the scope and scope chain are, why they're so important, and how they work.

**Scoping**: How our program's variables are <u>organized</u> and <u>accessed</u> by the JavaScript Engine. "*Where do variables live?*" or "*Where can we access a certain variable, and where not?*";
**Lexical Scoping**: Scoping is controlled by <u>placement</u> of functions and blocks in the program's code.
* A function written inside another function has access to the variables of the parent function.
* Influenced by where we write our functions and code blocks.
**Scope**: The space or environment in which a certain variable is **declared** (*variable environment in case of functions*). There is <u>global</u> scope, <u>function</u> scope, and <u>block</u> scope;
* "What's the difference between scope and variable environment?" For the case of functions, it's the same thing.
**Scope of a Variable**: The entire region of our code where a certain variable can be <u>accessed</u>.

You should know about the subtle differences such as Scope not being the same as Scope of a Variable.
### The 3 Types of Scope in JavaScript
<u>Global Scope</u>
```JS file:global-scope-example
const me = 'Jonas';
const job = 'Teacher';
const year = 1989;
```
* Outside of **any** function block
* Variables declared in global scope are **accessible** everywhere.

<u>Function Scope</u>
```JS file:function-scope-example
function calcAge(birthYear) {
	const now = 2037;
	const age = now - birthYear;
	return age;
}

console.log(now); // ReferenceError
```
* Variables are accessible <u>only inside the function and not outside</u> the function.
* Also called "*local scope*."

<u>Block Scope (ES6/ES2015 feature)</u>
```JS file:block-scope-example
if (year >= 1981 && year <= 1996) {
	const millenial = true;
	const food = 'Avocado Toast';
} // Example if block, for loop block, etc..

console.log(millenial); // Reference Error
```
* Variables are <u>accessible only inside</u> the block (*block scoped*).
* **HOWEVER**, this only applies to `let` and `const` variables.
* Functions are <u>also block scoped</u> (*only in strict mode, which should be using!*).

## The Scope Chain
[[Video 92 - Scope and The Scope Chain]]
## Scope Chain vs. Call Stack
He gets a lot of questions about the differences between Scope Chain and Call Stack. This is where he'll answer those questions and how they're all related to one another.
[[Video 92 - Scope and The Scope Chain]]
## Summary
Even though this was a long lecture with a lot to take in, this is the summary of the video.
* Scoping asks the question "*Where do variables live?*" or "*Where can we access a certain variable, and where not?*"
* There are 3 types of scope in JavaScript: the Global Scope, scopes defined by functions, and scopes defined by blocks.
* Only `let` and `const` variables are block-scoped. Variables declared with `var` end up in the closest function scope.
* In JavaScript, we have lexical scoping, so the rules of where we can access variables are based on exactly where in the code functions and blocks are written.
* Every scope always has access to all the variables from all its outer scopes, which is called the scope chain.
* When a variable is not in the current scope, the engine looks up in the scope chain until it finds the variable it's looking for, called variable lookup.
* The scope chain is a one-way street: a scope will never, ever have access to the variables of an inner scope.
* The scope chain in a certain scope is equal to adding together all the variable environments of all the parent scopes.
* The scope chain has nothing to do with the order in which functions were called. It does not affect the scope chain at all.
---
## Scoping in Practice

Now it's time to see scoping in practice while working on a semi-complex example to make sure that you understand the concept.
*Goes over the file structure and then starts coding out the example.*
Refer to 08-behind-the-scenes `script.js` file lines 6 → 43 for what the code looks like.

---
## Variable Environment: Hoisting and The TDZ

This next topic is going to be a misunderstood topic that's in JavaScript called <u>hoisting</u>.
### Hoisting in JavaScript
[[Video 94 - Variable Environment - Hoisting and The TDZ]]

---
## Hoisting and TDZ in Practice

It didn't seem like it when learning about hoisting, but it's a fairly straight forward process by going through different scenarios with variables.
Refer to 08-behind-the-scenes `script.js` file lines 48 → 89 for what the code looks like.

---
## The `this` Keyword

The `this` keyword is an important concept to understand in JavaScript. Many beginners find it difficult to understand, but don't worry because it's not that hard if you understand how the `this` keyword works.
[[Video 96 - The this Keyword]]

---
## The `this` Keyword in Practice

We're going to see the rules of how the `this` keyword is defined in action.
Refer to 08-behind-the-scenes `script.js` file lines 94 → 125 for what the code looks like.

---
## Regular Functions vs. Arrow Functions

We're going to talk about the pitfalls of regular functions and arrow functions. This way, we can learn when we should avoid and use each of them.
Refer to 08-behind-the-scenes `script.js` file lines 130 → 175 for what the code looks like.

An arrow function doesn't get its own keyword, but it gets it from its surroundings.
As best practice, never use an arrow function as a method even if you're not using the `this` keyword in a particular method. If you have the rule of never using the arrow function as a method, then you don't have to think about which type of function to use and can prevent different mistakes from happening in the first place.

---
## Primitives vs. Objects (Primitive vs. Reference Types)

As we move towards the end of the section, we need to learn about the big difference between the way primitive types and objects are stored in memory. This is a practical aspect and <u>causes a lot of confusion with beginners</u>.
Refer to 08-behind-the-scenes `script.js` file lines 181 → 195 for what the code looks like.
[[Video 99 - Primitive vs. Objects (Primitive vs. Reference Types)]]

---
## Primitives vs. Objects in Practice

We're going to create a similar example from the last video so we can see it in practice.
Refer to 08-behind-the-scenes `script.js` file lines 202 → 238 for what the code looks like.
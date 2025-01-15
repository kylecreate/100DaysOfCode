---
tags:
    - learning-notes
    - code-for-dummies
    - JavaScript
obsidianUIMode: preview
---
> "Hello Operator. Can you give me number 9?"
> — The White Stripes

JavaScript operators, expressions, and statements are the basic building blocks of programs which help manipulate and change values, perform math, compare two or more values, and more.
### Express Yourself
An *expression* is a piece of code that resolves to a value and can either assign a value to a variable or can have a value.
Below are examples of valid expressions.
```JS fold
1 + 1;
a = 1;
```

They can be short and simple or complicated depending on their need.
The `1` in the example above is called *operands*.
### Hello, Operator
The engines that make expressions do their work are called *operators* which operate on data to produce different results using the `+` and `=` symbols.
###  Operator Precedence
A single expression often will and can contain several operators depending on how complicated it needs to be.
- Depending on the order that the expressions is calculated, you can get one of the three results.
```JS fold
a = 1 + 2 * 3 / 4;
// a = 1.75
// a = 2.5 -- actual answer
// a = 2.25
```

Operator precedence is the order in which operators in an expression are evaluated.
- Operators are divided into groups of different levels of precedence, numbered from 0 to 19.

**TECHNICAL**: The operator with the lowest number is said to have the highest precedence.
When an expression contains two or more operators that have the same precedence, they are evaluated according to their associativity which determines the operators are evaluated from `left to right` or `right to left`.

### Using parentheses
The operator with the highest precedence in an expression is **parentheses**.
With a similar example above, the multi operator expression can be fully clarified in the following ways.
[Operator Precedence Table - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_precedence#table)
```JS fold
a = (1 + 2) * (3 / 4); // result: 2.25
a = (1 + (2 * 3)) / 4; // result: 1.75
a = ((1 + 2) * 3) / 4; // result: 2.25 -- actual statement
a = 1 + ((2 * 3) / 4); // result: 2.5
```
## Types of Operators
There's several types of operators that are used in JavaScript.
### Assignment Operators
This operator assigns the value of the operand on the right to the operand on the left.
After this expression runs, the variable `a` will have a value of `5` . Also, you can chain assignment operators together to assign the same value to multiple variables.
```JS fold
a = 5;
a = b = c = 5;

let b = 1;
let a = b += c = 5; // 6
```
### Comparison Operators
These operators test for equality or difference between operands and return a true or false value.

JavaScript Comparison Operators Table

| **Operator** |          **Description** |       **Example** |
|:-------------|:-------------------------|:------------------|
|           == |                 Equality |  3 === "3" (true) |
|           != |               Inequality |    3 != 3 (false) |
|          === |          Strict Equality | 3 === "3" (false) |
|          !== |        Strict Inequality |  3 !== "3" (true) |
|            > |             Greater Than |      7 > 1 (true) |
|           >= | Greater than or equal to |     7 >= 7 (true) |
|            < |                Less Than |     7 < 10 (true) |
|           <= |    Less than or equal to |     2 <= 2 (true) |

### Arithmetic Operators
These operators perform mathematical operations on operands and return the result.

**JavaScript Arithmetic Operators Table**

| **Operator** | **Description** |              **Example** |
|:-------------|:----------------|:-------------------------|
|            + |        Addition |                a = 1 + 1 |
|            - |     Subtraction |               a = 10 - 1 |
|           \* |  Multiplication |               a = 2 \* 2 |
|            / |        Division |                a = 8 / 2 |
|            % |         Modulus |                a = 5 % 2 |
|           ++ |       Increment |      a = ++b a = b++ a++ |
|          - - |       Decrement | a = - -b a = b - - a - - |

### String Operator
This operator performs operations using two strings. When used with strings, the `+` operator becomes the concentration operator to join the two or more string together.
```JS fold
let greeting = "Hello, " + firstName + ". I'm " + " " + mood + " to see you.";
```

### Bitwise Operators
These operators are signed 32-bit binary representations of numbers in twos complement format.
- Binary numbers are strings of 1s or 0s, with the position of the digit determining the value of a 1 in that position.

*Signed integers* means that both negative and positive whole numbers can be represented in this form.
To change a number from positive to negative, just flip all the bits and add 1.
```JS fold
00000000000000000000000000000001 // 1
00000000000000000000000000000101 // 5
11111111111111111111111111111011 // -5
```

**TECHNICAL**: Bitwise operators convert numbers to these 32-bit binary numbers and then convert them back to what we would consider normal numbers after the operation has been done.

**JavaScript Bitwise Operators Table**

|                 **Operator** | **Usage** |                                                                                                                   **Description** |
|:-----------------------------|:----------|:----------------------------------------------------------------------------------------------------------------------------------|
|                  Bitwise AND |     a & b |                                        Returns a 1 in each bit position for which the corresponding bits of both operands are 1s. |
|                   Bitwise OR |    a \| b |                              Returns a 1 in each bit position for which the corresponding bits of either or both operands are 1s. |
|                  Bitwise XOR |     a ^ b |                         Returns a 1 in each bit position for which the corresponding bits of either but not both operands are 1s. |
|                  Bitwise NOT |        ~a |                                                                                                  Inverts the bits of its operand. |
|                   Left Shift |    a << b |                                 Shifts `a` in binary representation `b` (<32) bits to the left, shifting in zeros from the right. |
| Sign-propagating right shift |    a >> b |                                     Shifts `a` in binary representation `b` (<32) bits to the right, discarding bits shifted off. |
|        Zero-fill right shift |   a >>> b | Shifts `a` in binary representation `b` (<32) bits to the right, discarding bits shifted off and shifting in zeros from the left. |


### Logical Operators
The terms `truthy` and `falsy` in JavaScript refer to the value that’s returned when you evaluate something as a **Boolean**. The following values are considered falsy values
- `false`
- 0
- -0
- '' - (`empty string`)
- `null`
- `undefined`
- NaN - (`Not a Number`)

Everything else evaluates to a Boolean `true` value, and is then considered `truthy` .
```JS fold
Boolean(0) // returns false
Boolean("0") // returns true
Boolean(1+1) //returns true
```

**JavaScript Logical Operators Table**

| **Operator** | Meaning |                                                                                                    Description |
|:-------------|:--------|:---------------------------------------------------------------------------------------------------------------|
|           && |     And |                                     Returns the first falsy operand. Otherwise, it returns the second operand. |
|         \|\| |      Or |                           Returns the first operand if it is `true`. Otherwise, it returns the second operand. |
|            ! |     Not | Takes only one operand. Returns `false` if its operand can be converted to `true`. Otherwise, it returns false |

**TECHNICAL**: You can also use the `OR` operator to set a default value for variables. In the following expression, the value of `myVar` will be set to the value of `x` unless `x` evaluates to a `false` value. Otherwise, it will be
set to the default value of `0` .
```JS fold
let myVar = x || 0;
```

### Conditional Operator
The conditional operator (also known as the *ternary operator*) uses three operands. This evaluates a logical expression and then returns a value based on whether that expression is true or false. It's the only operator that requires three operands.
```JS fold
let isItBiggerThanTen = (value > 10) ? "greater than 10" : "not greater than 10";
```

### Comma Operator
The *comma operator* evaluates two operands and returns the value of the second one. This is most often used to perform multiple assignments or other operations within loops and can serve as a shorthand for initializing variables.
```JS fold
let a = 10, b = 0;
```

### `delete` Operator
The `delete` operator removes a property from an object or an element from an array. The length of the array will stay the same when using it, the value will just become `undefined`.
```JS fold
let animals = ["dog","cat","bird","octopus"];
console.log (animals[3]); // returns "octopus"
delete animals[3];
console.log (animals[3]); // returns "undefined"
```

### `in` Operator
This operator returns `true` if the value exists in an array or an object.
```JS fold
let animals = ["dog","cat","bird","octopus"];
if (3 in animals) {
	console.log ("it's in there");
}
```
### `instanceOf` Operator
This operator returns `true` if the object specified is the type of object that has been specified.
```JS fold
let myString = new String();
if (myString instanceof String) {
	console.log("yup, it's a string!");
}
```

### `new` Operator
This operator creates an instance of an object.
```JS fold
let today = new Date();
let bird = new Pet();
let daisy = new Flower();
```

### `this` Operator
The operator refers to the current object. It’s frequently used for retrieving
properties within an object.
*(talked about more in detail in Chapter 8)*
### `typeof` Operator
This operator returns a string containing the type of the operand.
```JS fold
let businessName = "Harry's Watch Repair";
console.log(typeof businessName); // returns "string"
```

### `void` Operator
This operator evaluates an expression and then returns `undefined`. You will often see this used in HTML documents when a link is needed but you want to override the link's default behavior using JavaScript.
```HTML fold
<a href="javascript:void(0);">
	This is a link, but it won't do anything
</a>
```

## Combining Operators
You can combine assignment operators with the other operators as a shorthand method of assigning the result of an expression to a variable.
```JS fold
a = a + 10; // Regular
a += 10; // Shorthand
```


**Combining the Assignment Operators and Other Operators Table**

|                              Name | Shorthand |    Standard |
|:----------------------------------|:----------|:------------|
|                        Assignment |     x = y |       x = y |
|               Addition Assignment |    x += y |   x = x + y |
|            Subtraction Assignment |    x -= y |   x = x - y |
|         Multiplication Assignment |   x \*= y |  x = x \* y |
|               Division Assignment |    x /= y |   x = x / y |
|              Remainder Assignment |    x %= y |   x = x % y |
|             Left Shift Assignment |   x <<= y |  x = x << y |
|            Right Shift Assignment |    x >> y |  x = x >> y |
| Unassigned Right Shift Assignment |  x >>>= y | x = x <<< y |
|            Bitwise AND Assignment |    x &= y |   x = x & y |
|            Bitwise XOR Assignment |    x ^= y |   x = x ^ y |
|             Bitwise OR Assignment |   x \|= y |  x = x \| y |


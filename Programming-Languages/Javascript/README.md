# JavaScript

## Table of Contents

1. [Online Resources](#online-resources)
2. [Basics](#basics)

## Online Resources

### Written Tutorials

- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [W3Schools](https://www.w3schools.com/js/)
- [JavaScript.info](https://javascript.info/)
- [freeCodeCamp](https://www.freecodecamp.org/learn/)
- [Codecademy](https://www.codecademy.com/learn/introduction-to-javascript)
- [Eloquent JavaScript](https://eloquentjavascript.net/)
- [JavaScript for Cats](http://jsforcats.com/)

### Video Tutorials

- [freeCodeCamp](https://www.youtube.com/watch?v=PkZNo7MFNFg)
- [Traversy Media](https://www.youtube.com/watch?v=hdI2bqOjy3c)
- [Codecademy](https://www.youtube.com/watch?v=hdI2bqOjy3c)
- [The Net Ninja](https://www.youtube.com/watch?v=hdI2bqOjy3c)
- [Academind](https://www.youtube.com/watch?v=hdI2bqOjy3c)

### Courses

- [Coursera - HTML, CSS, and Javascript for Web Developers](https://www.coursera.org/learn/html-css-javascript-for-web-developers)
- [Udemy - The Complete JavaScript Course 2020: Build Real Projects!](https://www.udemy.com/course/the-complete-javascript-course/)
- [Udemy - JavaScript: Understanding the Weird Parts](https://www.udemy.com/course/understand-javascript/)
- [Udemy - JavaScript: The Advanced Concepts](https://www.udemy.com/course/advanced-javascript-concepts/)
- [Udemy - JavaScript: Understanding the Weird Parts](https://www.udemy.com/course/understand-javascript/)

## Basics

### What is JavaScript?

JavaScript is a high-level, interpreted programming language that conforms to the ECMAScript specification. It is a versatile language used for web development, server-side development, mobile app development, and game development.

### JavaScript Syntax

JavaScript syntax is similar to other programming languages like C, C++, and Java. Here is a simple example of a JavaScript function:

```javascript
function greet(name) {
  return "Hello, " + name + "!";
}

console.log(greet("World"));
```

In this example, the `greet` function takes a `name` parameter and returns a greeting message.

### JavaScript Variables

JavaScript variables are containers for storing data values. You can declare a variable using the `var`, `let`, or `const` keyword. Here is an example:

```javascript
var x = 5;
let y = 10;
const PI = 3.14;
```

In this example, `x` is declared using the `var` keyword, `y` is declared using the `let` keyword, and `PI` is declared using the `const` keyword.

### JavaScript Data Types

JavaScript has several data types, including:

- Number
- String
- Boolean
- Object
- Array
- Function
- Null

Here is an example of declaring variables with different data types:

```javascript
var num = 10;
var str = "Hello, World!";
var bool = true;
var obj = { key: "value" };
var arr = [1, 2, 3];
var func = function () {
  return "Hello!";
};
var n = null;
```

### JavaScript Operators

JavaScript supports several operators, including:

- Arithmetic operators (+, -, \*, /, %)
- Assignment operators (=, +=, -=, \*=, /=)
- Comparison operators (==, ===, !=, !==, >, <, >=, <=)
- Logical operators (&&, ||, !)
- Bitwise operators (&, |, ^, ~, <<, >>, >>>)
- Conditional (ternary) operator (condition ? expr1 : expr2)

Here is an example of using arithmetic operators:

```javascript
var x = 10;
var y = 5;
var sum = x + y;
var difference = x - y;
var product = x * y;
var quotient = x / y;
var remainder = x % y;
```

In this example, `sum` contains the sum of `x` and `y`, `difference` contains the difference, `product` contains the product, `quotient` contains the quotient, and `remainder` contains the remainder.

### JavaScript Functions

JavaScript functions are blocks of code that perform a specific task. You can define a function using the `function` keyword. Here is an example:

```javascript
function greet(name) {
  return "Hello, " + name + "!";
}

console.log(greet("World"));
```

In this example, the `greet` function takes a `name` parameter and returns a greeting message.

### JavaScript Objects

JavaScript objects are containers for named values called properties. You can define an object using curly braces `{}`. Here is an example:

```javascript
var person = {
  name: "John Doe",
  age: 30,
  email: "johndoe@gmail.com",
};
```

In this example, `person` is an object with `name`, `age`, and `email` properties.

### JavaScript Arrays

JavaScript arrays are used to store multiple values in a single variable. You can define an array using square brackets `[]`. Here is an example:

```javascript
var fruits = ["Apple", "Banana", "Orange"];
```

In this example, `fruits` is an array containing three elements.

### JavaScript Loops

JavaScript loops are used to execute a block of code multiple times. There are several types of loops in JavaScript, including `for`, `while`, and `do...while`. Here is an example of a `for` loop:

```javascript
for (var i = 0; i < 5; i++) {
  console.log(i);
}
```

In this example, the loop will print the numbers 0 to 4 to the console.

### JavaScript Conditional Statements

JavaScript conditional statements are used to perform different actions based on different conditions. There are several types of conditional statements in JavaScript, including `if`, `else if`, and `else`. Here is an example:

```javascript
var x = 10;
if (x > 5) {
  console.log("x is greater than 5");
} else {
  console.log("x is less than or equal to 5");
}
```

In this example, the code will print `x is greater than 5` to the console if `x` is greater than 5, and `x is less than or equal to 5` otherwise.

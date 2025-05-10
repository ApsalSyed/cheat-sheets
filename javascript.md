# JavaScript Cheat Sheet

## Table of Contents

- [Basics](#basics)
- [Variables](#variables)
- [Data Types](#data-types)
- [Operators](#operators)
- [Control Flow](#control-flow)
- [Functions](#functions)
- [Arrays](#arrays)
- [Objects](#objects)
- [ES6+ Features](#es6-features)
- [DOM Manipulation](#dom-manipulation)
- [Async JavaScript](#async-javascript)
- [Error Handling](#error-handling)
- [Modules](#modules)
- [Regular Expressions](#regular-expressions)
- [Best Practices](#best-practices)

## Basics

### Comments

```javascript
// Single line comment

/* Multi-line
   comment */
```

### Console Output

```javascript
console.log("Hello World"); // Basic logging
console.error("Error!"); // Error output
console.warn("Warning"); // Warning output
console.table(object); // Display object as table
console.time("label"); // Start timer
console.timeEnd("label"); // End timer and output time
```

## Variables

### Declaration

```javascript
var variableName;       // Function scope, hoisted (older)
let variableName;       // Block scope (recommended)
const CONSTANT_NAME;    // Block scope, cannot be reassigned (recommended)
```

### Naming Conventions

- camelCase for variables and functions
- PascalCase for classes and constructors
- UPPER_SNAKE_CASE for constants

## Data Types

### Primitive Types

```javascript
// String
const name = "John";
const greeting = `Hello, ${name}`; // Template literal

// Number
const integer = 42;
const float = 3.14;
const infinity = Infinity;
const notANumber = NaN;

// Boolean
const isTrue = true;
const isFalse = false;

// Undefined
let undefinedVar;

// Null
const nullValue = null;

// Symbol (ES6)
const uniqueKey = Symbol("description");

// BigInt (ES2020)
const bigNumber = 9007199254740991n;
```

### Type Checking

```javascript
typeof "string"; // "string"
typeof 42; // "number"
typeof true; // "boolean"
typeof undefined; // "undefined"
typeof null; // "object" (quirk in JavaScript)
typeof Symbol(); // "symbol"
typeof 42n; // "bigint"
typeof {}; // "object"
typeof []; // "object" (use Array.isArray() for arrays)
typeof function () {}; // "function"

// Better type checking
Array.isArray([]); // true
value === null; // Check for null
Number.isNaN(NaN); // Check for NaN
```

## Operators

### Arithmetic

```javascript
a + b; // Addition
a - b; // Subtraction
a * b; // Multiplication
a / b; // Division
a % b; // Modulo (remainder)
a ** b; // Exponentiation (ES2016)
++a; // Increment (pre)
a++; // Increment (post)
--a; // Decrement (pre)
a--; // Decrement (post)
```

### Assignment

```javascript
a = b; // Assignment
a += b; // a = a + b
a -= b; // a = a - b
a *= b; // a = a * b
a /= b; // a = a / b
a %= b; // a = a % b
a **= b; // a = a ** b
a ??= b; // a = a ?? b (nullish coalescing assignment)
a &&= b; // Logical AND assignment
a ||= b; // Logical OR assignment
```

### Comparison

```javascript
a == b; // Equal (value)
a === b; // Strict equal (value and type)
a != b; // Not equal (value)
a !== b; // Strict not equal (value and type)
a > b; // Greater than
a >= b; // Greater than or equal
a < b; // Less than
a <= b; // Less than or equal
```

### Logical

```javascript
a && b; // Logical AND
a || b; // Logical OR
!a; // Logical NOT
a ?? b; // Nullish coalescing (returns b if a is null/undefined)
```

### Other Operators

```javascript
condition ? ifTrue : ifFalse; // Ternary operator
delete object.property; // Delete property
typeof x; // Get type
void expression; // Evaluates expression and returns undefined
a instanceof Constructor; // Check if object is instance of constructor
a in object; // Check if property exists in object
```

## Control Flow

### Conditional Statements

```javascript
// If, else if, else
if (condition) {
  // code
} else if (anotherCondition) {
  // code
} else {
  // code
}

// Switch
switch (expression) {
  case value1:
    // code
    break;
  case value2:
    // code
    break;
  default:
  // default code
}
```

### Loops

```javascript
// For loop
for (let i = 0; i < 10; i++) {
  // code
}

// For...in (iterates over object properties)
for (const key in object) {
  if (object.hasOwnProperty(key)) {
    // code
  }
}

// For...of (iterates over iterable values, ES6)
for (const value of iterable) {
  // code
}

// While loop
while (condition) {
  // code
}

// Do-while loop
do {
  // code
} while (condition);

// Break and continue
for (let i = 0; i < 10; i++) {
  if (i === 3) continue; // Skip this iteration
  if (i === 8) break; // Exit loop
  // code
}
```

## Functions

### Function Declaration

```javascript
// Named function
function add(a, b) {
  return a + b;
}

// Function expression
const subtract = function (a, b) {
  return a - b;
};

// Arrow function (ES6)
const multiply = (a, b) => a * b;

// Arrow function with block body
const divide = (a, b) => {
  if (b === 0) throw new Error("Division by zero");
  return a / b;
};

// Immediately Invoked Function Expression (IIFE)
(function () {
  // code
})();

// With parameters and return value
((a, b) => a + b)(2, 3); // Returns 5
```

### Parameters

```javascript
// Default parameters (ES6)
function greet(name = "Guest") {
  return `Hello, ${name}!`;
}

// Rest parameters (ES6)
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

// Parameter destructuring (ES6)
function processUser({ name, age }) {
  console.log(`Name: ${name}, Age: ${age}`);
}
```

### Advanced Function Concepts

```javascript
// Closures
function createCounter() {
  let count = 0;
  return function () {
    return ++count;
  };
}
const counter = createCounter();
counter(); // 1
counter(); // 2

// Function methods
function greet() {
  console.log(`Hello, ${this.name}!`);
}
greet.call({ name: "John" }); // Set 'this' and call
greet.apply({ name: "John" }, []); // Set 'this' and call with args array
const boundGreet = greet.bind({ name: "John" }); // Set 'this' and return new function
boundGreet(); // "Hello, John!"
```

## Arrays

### Creation and Access

```javascript
// Array creation
const arr1 = [1, 2, 3];
const arr2 = new Array(1, 2, 3);
const arr3 = Array.of(1, 2, 3);
const arr4 = Array.from("123"); // Creates [1, 2, 3]

// Accessing elements
const first = arr1[0]; // First element
const last = arr1[arr1.length - 1]; // Last element
```

### Array Methods

```javascript
// Adding and removing elements
array.push(item); // Add to end
array.pop(); // Remove from end
array.unshift(item); // Add to beginning
array.shift(); // Remove from beginning
array.splice(start, deleteCount, ...items); // Add/remove at position

// Finding elements
array.indexOf(item); // Find index
array.lastIndexOf(item); // Find last index
array.includes(item); // Check if exists
array.find(callback); // Find first matching element
array.findIndex(callback); // Find first matching index

// Iteration methods
array.forEach(callback); // Iterate
array.map(callback); // Transform
array.filter(callback); // Filter
array.reduce(callback, initial); // Reduce to single value
array.reduceRight(callback, initial); // Right-to-left reduce
array.every(callback); // Test if all pass
array.some(callback); // Test if any pass

// Other useful methods
array.slice(start, end); // Extract portion
array.concat(array2); // Combine arrays
array.join(separator); // Join to string
array.sort(compareFunction); // Sort
array.reverse(); // Reverse
array.flat(depth); // Flatten nested arrays
array.flatMap(callback); // Map and flatten
```

## Objects

### Object Creation

```javascript
// Object literal
const user = {
  name: "John",
  age: 30,
  "likes coding": true, // Property with space
};

// Constructor
function User(name, age) {
  this.name = name;
  this.age = age;
}
const user2 = new User("Jane", 25);

// Object.create()
const user3 = Object.create(prototypeObject);

// Class syntax (ES6)
class User {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}
```

### Accessing Properties

```javascript
// Dot notation
user.name;

// Bracket notation
user["name"];
user["likes coding"];

// Destructuring (ES6)
const { name, age } = user;
```

### Object Methods

```javascript
// Object keys, values, entries
Object.keys(obj); // Array of keys
Object.values(obj); // Array of values
Object.entries(obj); // Array of [key, value] pairs

// Object manipulation
Object.assign(target, ...sources); // Copy properties
Object.freeze(obj); // Make immutable
Object.seal(obj); // Prevent adding/deleting props
Object.create(proto); // Create with prototype

// Property descriptors
Object.defineProperty(obj, prop, descriptor);
Object.getOwnPropertyDescriptor(obj, prop);
```

## ES6+ Features

### Template Literals

```javascript
const name = "John";
const greeting = `Hello, ${name}!
This supports multi-line strings.`;
```

### Destructuring

```javascript
// Array destructuring
const [first, second, ...rest] = [1, 2, 3, 4, 5];

// Object destructuring
const { name, age, job = "Developer" } = person;

// Function parameter destructuring
function process({ name, age }) {
  // code
}
```

### Spread Operator

```javascript
// Array spreading
const combined = [...array1, ...array2];
const copied = [...original];

// Object spreading
const enhanced = { ...original, newProp: value };
```

### Optional Chaining

```javascript
// Without optional chaining
const street = user && user.address && user.address.street;

// With optional chaining (ES2020)
const street = user?.address?.street;
```

### Nullish Coalescing

```javascript
// Logical OR returns right side if left is falsy (0, "", false, etc.)
const value = input || "default";

// Nullish coalescing only returns right side if left is null/undefined
const value = input ?? "default";
```

## DOM Manipulation

### Selecting Elements

```javascript
// By ID
const element = document.getElementById("elementId");

// By class name
const elements = document.getElementsByClassName("className");

// By tag name
const elements = document.getElementsByTagName("div");

// CSS selectors
const element = document.querySelector(".class");
const elements = document.querySelectorAll("div.className");
```

### Modifying Elements

```javascript
// Content
element.textContent = "Text only";
element.innerHTML = "<span>HTML content</span>";

// Attributes
element.setAttribute("attr", "value");
element.getAttribute("attr");
element.removeAttribute("attr");

// Classes
element.classList.add("newClass");
element.classList.remove("oldClass");
element.classList.toggle("toggleClass");
element.classList.contains("checkClass");

// Styles
element.style.color = "red";
element.style.fontSize = "16px";
```

### Creating and Modifying DOM

```javascript
// Create element
const div = document.createElement("div");

// Modify
div.textContent = "New element";
div.classList.add("container");

// Add to DOM
parentElement.appendChild(div);
parentElement.insertBefore(div, referenceElement);
parentElement.replaceChild(div, oldElement);
parentElement.removeChild(childElement);

// Modern methods
parentElement.append(...nodes); // Add at end
parentElement.prepend(...nodes); // Add at beginning
element.before(...nodes); // Add before element
element.after(...nodes); // Add after element
element.replaceWith(...nodes); // Replace element
element.remove(); // Remove element
```

### Events

```javascript
// Add event listener
element.addEventListener("click", function (event) {
  // Handle event
  event.preventDefault(); // Prevent default action
  event.stopPropagation(); // Stop bubbling
});

// Remove event listener
element.removeEventListener("click", handlerFunction);

// Common events:
// click, dblclick, mousedown, mouseup, mousemove, mouseover, mouseout
// keydown, keyup, keypress
// submit, change, input, focus, blur
// load, DOMContentLoaded, resize, scroll
```

## Async JavaScript

### Callbacks

```javascript
function fetchData(callback) {
  setTimeout(() => {
    callback("Data");
  }, 1000);
}

fetchData((data) => {
  console.log(data);
});
```

### Promises

```javascript
// Creating a promise
const promise = new Promise((resolve, reject) => {
  // Async operation
  if (success) {
    resolve(value);
  } else {
    reject(error);
  }
});

// Using promises
promise
  .then((value) => {
    // Handle success
    return newValue;
  })
  .catch((error) => {
    // Handle error
  })
  .finally(() => {
    // Always executes
  });

// Promise methods
Promise.all([promise1, promise2]); // Resolves when all resolve
Promise.race([promise1, promise2]); // Resolves when first resolves
Promise.allSettled([promise1, promise2]); // Waits for all to complete
Promise.any([promise1, promise2]); // Resolves when first resolves successfully
Promise.resolve(value); // Creates resolved promise
Promise.reject(error); // Creates rejected promise
```

### Async/Await

```javascript
async function fetchData() {
  try {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    return data;
  } catch (error) {
    console.error("Error:", error);
    throw error;
  }
}

// Using async function
fetchData()
  .then((data) => console.log(data))
  .catch((error) => console.error(error));

// Or with IIFE
(async () => {
  try {
    const data = await fetchData();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
})();
```

## Error Handling

### Try-Catch

```javascript
try {
  // Code that might throw an error
  throw new Error("Something went wrong");
} catch (error) {
  // Handle error
  console.error(error.message);
} finally {
  // Always executes
  console.log("Cleanup");
}
```

### Custom Errors

```javascript
class ValidationError extends Error {
  constructor(message) {
    super(message);
    this.name = "ValidationError";
  }
}

try {
  throw new ValidationError("Invalid data");
} catch (error) {
  if (error instanceof ValidationError) {
    // Handle validation error
  } else {
    // Handle other errors
  }
}
```

## Modules

### ES Modules (ESM)

```javascript
// Exporting
export const name = "Module";
export function hello() {
  return "Hello";
}
export default class User {
  /* ... */
}

// Named imports
import { name, hello } from "./module.js";

// Default import
import User from "./module.js";

// Rename imports
import { name as moduleName } from "./module.js";

// Import all
import * as module from "./module.js";

// Dynamic import
import("./module.js").then((module) => {
  // Use module
});
```

### CommonJS (Node.js)

```javascript
// Exporting
module.exports.name = "Module";
module.exports.hello = function () {
  return "Hello";
};
module.exports = { name, hello };

// Importing
const module = require("./module");
const { name, hello } = require("./module");
```

## Regular Expressions

### Creating RegExp

```javascript
// Literal notation
const re1 = /pattern/flags;

// Constructor
const re2 = new RegExp('pattern', 'flags');
```

### Common Flags

```
i - case-insensitive
g - global (match all occurrences)
m - multiline
s - dot matches newlines
y - sticky
u - unicode
```

### Methods

```javascript
// RegExp methods
regexp.test(string); // Returns boolean
regexp.exec(string); // Returns match info or null

// String methods
string.match(regexp); // Returns matches
string.matchAll(regexp); // Returns iterator of all matches
string.search(regexp); // Returns index or -1
string.replace(regexp, replacement); // Returns new string
string.replaceAll(regexp, replacement); // ES2021
string.split(regexp); // Split string by pattern
```

### Common Patterns

```javascript
/^\d+$/            // Only digits
/^[A-Za-z]+$/      // Only letters
/^[A-Za-z0-9_]+$/  // Alphanumeric + underscore
/^\S+@\S+\.\S+$/   // Simple email validation
/^#[0-9A-Fa-f]{6}$/ // Hex color code
```

## Best Practices

### Code Quality

- Use strict mode: `'use strict';`
- Prefer `const` and `let` over `var`
- Use meaningful variable and function names
- Keep functions small and focused
- Use arrow functions for short callbacks
- Comment complex sections but write self-documenting code
- Use linters (ESLint) and formatters (Prettier)

### Performance

- Minimize DOM manipulation
- Use event delegation
- Debounce/throttle expensive operations
- Be careful with closures (memory leaks)
- Avoid deep nesting of loops
- Use appropriate data structures
- Consider web workers for CPU-intensive tasks

### Security

- Validate user input
- Don't use `eval()`
- Sanitize HTML content before insertion (prevent XSS)
- Use HTTPS for external resources
- Be cautious with third-party libraries
- Use Content Security Policy (CSP)

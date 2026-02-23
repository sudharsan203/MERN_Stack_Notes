# JavaScript Programming Language - Complete Guide for Beginners

## Table of Contents
1. [Introduction to JavaScript](#introduction-to-javascript)
2. [Getting Started](#getting-started)
3. [Variables and Data Types](#variables-and-data-types)
4. [Operators](#operators)
5. [Control Structures](#control-structures)
6. [Functions](#functions)
7. [Arrays](#arrays)
8. [Objects](#objects)
9. [String Methods](#string-methods)
10. [DOM Manipulation](#dom-manipulation)
11. [Events](#events)
12. [Asynchronous Programming](#asynchronous-programming)
13. [Error Handling](#error-handling)
14. [ES6+ Features](#es6-features)
15. [Best Practices](#best-practices)

---

## Introduction to JavaScript

JavaScript is a **versatile, lightweight programming language** that runs in web browsers and servers (Node.js). It's commonly used for:
- **Frontend Development**: Creating interactive web pages
- **Backend Development**: Building servers with Node.js
- **Full-Stack Development**: Both frontend and backend
- **Mobile Development**: React Native, Ionic
- **Desktop Applications**: Electron

### Why Learn JavaScript?
- Runs everywhere (browsers, servers, mobile)
- Easy to learn for beginners
- High demand in job market
- Vast ecosystem and libraries
- Can build complete applications with just JavaScript

---

## Getting Started

### 1. Running JavaScript

**In Browser:**
```html
<!-- Inside an HTML file -->
<script>
  console.log('Hello, JavaScript!');
</script>
```

**In Node.js (Terminal):**
```bash
# Create a file: hello.js
console.log('Hello, JavaScript!');

# Run with: node hello.js
```

**Browser Console:**
- Press `F12` to open Developer Tools
- Go to Console tab
- Type JavaScript directly

### 2. Basic Output

```javascript
console.log('Hello World');        // Print to console
console.error('This is an error'); // Print error
console.warn('This is a warning'); // Print warning
alert('Show dialog box');          // Show popup in browser
document.write('Write to page');   // Write to HTML page
```

---

## Variables and Data Types

### Declaring Variables

JavaScript has three ways to declare variables:

```javascript
// 1. var (old way - avoid in modern JavaScript)
var name = 'John';

// 2. let (preferred - block-scoped)
let age = 25;

// 3. const (preferred - for constants, block-scoped)
const salary = 50000;
```

**Key Differences:**
- `let` and `const` are block-scoped (limited to `{}`)
- `var` is function-scoped
- `const` cannot be reassigned (immutable)

### Data Types

JavaScript has 7 primitive data types:

```javascript
// 1. String - Text data
let firstName = 'John';
let lastName = "Doe";
let fullName = `${firstName} ${lastName}`; // Template literal (backticks)

// 2. Number - Integer or decimal
let age = 25;
let salary = 50000.50;
let negativeNum = -10;

// 3. Boolean - True or False
let isStudent = true;
let isEmployed = false;

// 4. Undefined - Variable declared but not assigned
let x;
console.log(x); // undefined

// 5. Null - Intentional absence of value
let empty = null;

// 6. Symbol - Unique identifier (advanced)
let sym = Symbol('id');

// 7. BigInt - Very large numbers
let bigNum = 123456789012345678901234567890n;

// 8. Object - Collections of data (not primitive)
let person = {
  name: 'John',
  age: 25
};
```

### Type Checking

```javascript
typeof 'hello';      // "string"
typeof 42;           // "number"
typeof true;         // "boolean"
typeof undefined;    // "undefined"
typeof null;         // "object" (special case)
typeof {};           // "object"
typeof [];           // "object"
typeof function(){}; // "function"
```

### Type Conversion

```javascript
// String conversion
String(42);           // "42"
String(true);         // "true"
(42).toString();      // "42"

// Number conversion
Number('42');         // 42
Number(true);         // 1
Number(false);        // 0
parseInt('42');       // 42 (integer)
parseFloat('42.5');   // 42.5

// Boolean conversion
Boolean(0);           // false
Boolean(1);           // true
Boolean('');          // false
Boolean('hello');     // true
Boolean(null);        // false
```

---

## Operators

### 1. Arithmetic Operators

```javascript
let a = 10, b = 3;

console.log(a + b);   // 13 (addition)
console.log(a - b);   // 7  (subtraction)
console.log(a * b);   // 30 (multiplication)
console.log(a / b);   // 3.33... (division)
console.log(a % b);   // 1 (modulus - remainder)
console.log(a ** b);  // 1000 (exponentiation)
```

### 2. Assignment Operators

```javascript
let x = 10;

x += 5;  // x = x + 5 (15)
x -= 3;  // x = x - 3 (12)
x *= 2;  // x = x * 2 (24)
x /= 4;  // x = x / 4 (6)
x %= 2;  // x = x % 2 (0)
```

### 3. Comparison Operators

```javascript
console.log(5 > 3);    // true
console.log(5 < 3);    // false
console.log(5 >= 5);   // true
console.log(5 <= 3);   // false
console.log(5 == '5'); // true (loose equality - type conversion)
console.log(5 === '5'); // false (strict equality - no type conversion)
console.log(5 != '5'); // false (loose inequality)
console.log(5 !== '5'); // true (strict inequality)
```

### 4. Logical Operators

```javascript
// AND (&&) - Returns true if BOTH conditions are true
console.log(true && true);   // true
console.log(true && false);  // false
console.log(false && true);  // false

// OR (||) - Returns true if AT LEAST ONE condition is true
console.log(true || false);  // true
console.log(false || false); // false

// NOT (!) - Reverses boolean value
console.log(!true);          // false
console.log(!false);         // true

// Example
let age = 25;
let hasLicense = true;
if (age >= 18 && hasLicense) {
  console.log('Can drive');
}
```

### 5. Ternary Operator

```javascript
// condition ? valueIfTrue : valueIfFalse
let age = 20;
let status = age >= 18 ? 'Adult' : 'Minor';
console.log(status); // "Adult"

// Nested ternary
let score = 85;
let grade = score >= 90 ? 'A' : score >= 80 ? 'B' : score >= 70 ? 'C' : 'F';
console.log(grade); // "B"
```

---

## Control Structures

### 1. If-Else Statements

```javascript
let age = 20;

if (age < 13) {
  console.log('Child');
} else if (age < 18) {
  console.log('Teenager');
} else if (age < 65) {
  console.log('Adult');
} else {
  console.log('Senior');
}
```

### 2. Switch Statement

```javascript
let day = 3;
let dayName;

switch (day) {
  case 1:
    dayName = 'Monday';
    break;
  case 2:
    dayName = 'Tuesday';
    break;
  case 3:
    dayName = 'Wednesday';
    break;
  default:
    dayName = 'Unknown day';
}

console.log(dayName); // "Wednesday"

// Note: 'break' is important - without it, execution continues to next case
```

### 3. For Loop

```javascript
// Traditional for loop
for (let i = 0; i < 5; i++) {
  console.log(i); // 0, 1, 2, 3, 4
}

// For loop with array
let fruits = ['Apple', 'Banana', 'Orange'];
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}

// For-of loop (simpler array iteration)
for (let fruit of fruits) {
  console.log(fruit);
}

// For-in loop (iterates over object keys)
let person = { name: 'John', age: 25, city: 'NYC' };
for (let key in person) {
  console.log(key + ': ' + person[key]);
}
```

### 4. While Loop

```javascript
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}

// Do-While (executes at least once)
let j = 0;
do {
  console.log(j);
  j++;
} while (j < 5);
```

### 5. Break and Continue

```javascript
// break - exits the loop
for (let i = 0; i < 10; i++) {
  if (i === 5) break; // stops loop when i is 5
  console.log(i);
}

// continue - skips current iteration
for (let i = 0; i < 5; i++) {
  if (i === 2) continue; // skips when i is 2
  console.log(i); // 0, 1, 3, 4
}
```

---

## Functions

### Basic Function Declaration

```javascript
// Function declaration
function greet(name) {
  return 'Hello, ' + name;
}

console.log(greet('John')); // "Hello, John"
```

### Function Expression

```javascript
// Function expression (anonymous function)
const add = function(a, b) {
  return a + b;
};

console.log(add(5, 3)); // 8
```

### Arrow Functions (Modern JavaScript)

```javascript
// Arrow function (concise syntax)
const multiply = (a, b) => {
  return a * b;
};

// Shorthand for single expression
const square = x => x * x;

console.log(multiply(5, 3)); // 15
console.log(square(4));      // 16
```

### Default Parameters

```javascript
function greet(name = 'Guest', greeting = 'Hello') {
  return greeting + ', ' + name;
}

console.log(greet());              // "Hello, Guest"
console.log(greet('John'));        // "Hello, John"
console.log(greet('John', 'Hi'));  // "Hi, John"
```

### Rest Parameters

```javascript
// Accept multiple arguments
function sum(...numbers) {
  let total = 0;
  for (let num of numbers) {
    total += num;
  }
  return total;
}

console.log(sum(1, 2, 3, 4, 5)); // 15
```

### Function Scope

```javascript
let globalVar = 'I am global';

function myFunction() {
  let localVar = 'I am local';
  console.log(globalVar); // Can access global
  console.log(localVar);  // Can access local
}

myFunction();
console.log(globalVar); // Works - global
// console.log(localVar); // Error - not accessible outside function
```

### Hoisting

```javascript
// Function declarations are hoisted
console.log(add(5, 3)); // Works! 8
function add(a, b) {
  return a + b;
}

// Function expressions NOT hoisted
// console.log(multiply(5, 3)); // Error!
const multiply = function(a, b) {
  return a * b;
};
```

---

## Arrays

### Creating Arrays

```javascript
// Array literal
let fruits = ['Apple', 'Banana', 'Orange'];

// Array constructor
let numbers = new Array(1, 2, 3, 4, 5);

// Array with different types
let mixed = [1, 'hello', true, null, { name: 'John' }];

// Accessing elements
console.log(fruits[0]); // "Apple"
console.log(fruits.length); // 3
```

### Array Methods

```javascript
let arr = [1, 2, 3, 4, 5];

// Add/Remove elements
arr.push(6);           // Add to end: [1,2,3,4,5,6]
arr.pop();             // Remove from end: [1,2,3,4,5]
arr.unshift(0);        // Add to start: [0,1,2,3,4,5]
arr.shift();           // Remove from start: [1,2,3,4,5]

// Finding elements
arr.includes(3);       // true
arr.indexOf(3);        // 2 (index of element)
arr.find(x => x > 3);  // 4 (first element matching condition)

// Transform arrays
let doubled = arr.map(x => x * 2);     // [2,4,6,8,10]
let evens = arr.filter(x => x % 2 === 0); // [2,4]
let sum = arr.reduce((a, b) => a + b, 0); // 15

// Other methods
arr.slice(1, 3);       // [2, 3] (copy portion, doesn't modify)
arr.splice(1, 2);      // Remove 2 elements starting at index 1
arr.reverse();         // Reverse array
arr.sort();            // Sort array
arr.join('-');         // "1-2-3-4-5" (convert to string)
```

### Array Destructuring

```javascript
let [first, second, third] = [1, 2, 3];
console.log(first);  // 1
console.log(second); // 2

// Skip elements
let [a, , c] = [10, 20, 30];
console.log(a, c); // 10, 30
```

---

## Objects

### Creating Objects

```javascript
// Object literal
let person = {
  name: 'John',
  age: 25,
  city: 'New York',
  email: 'john@example.com'
};

// Using constructor
let car = new Object();
car.brand = 'Toyota';
car.model = 'Camry';
car.year = 2020;
```

### Accessing Object Properties

```javascript
let person = { name: 'John', age: 25 };

// Dot notation
console.log(person.name); // "John"

// Bracket notation
console.log(person['age']); // 25

// Dynamic access
let prop = 'name';
console.log(person[prop]); // "John"
```

### Modifying Objects

```javascript
let person = { name: 'John', age: 25 };

// Add property
person.city = 'NYC';

// Modify property
person.age = 26;

// Delete property
delete person.city;
```

### Methods in Objects

```javascript
let person = {
  name: 'John',
  age: 25,
  greet: function() {
    return 'Hi, I am ' + this.name;
  }
};

console.log(person.greet()); // "Hi, I am John"

// Shorthand method syntax (ES6)
let person2 = {
  name: 'Jane',
  greet() {
    return 'Hi, I am ' + this.name;
  }
};
```

### Object Destructuring

```javascript
let person = { name: 'John', age: 25, city: 'NYC' };

// Extract properties
let { name, age } = person;
console.log(name); // "John"
console.log(age);  // 25

// Rename properties
let { name: personName, age: personAge } = person;
console.log(personName); // "John"
```

### Object Methods

```javascript
let person = { name: 'John', age: 25 };

// Get keys
Object.keys(person);       // ['name', 'age']

// Get values
Object.values(person);     // ['John', 25]

// Get key-value pairs
Object.entries(person);    // [['name', 'John'], ['age', 25]]

// Check if property exists
'name' in person;          // true
person.hasOwnProperty('name'); // true

// Merge objects
let merged = Object.assign({}, person, { city: 'NYC' });
// or using spread operator
let merged2 = { ...person, city: 'NYC' };
```

---

## String Methods

### Creating Strings

```javascript
let str1 = 'Hello';
let str2 = "World";
let str3 = `Template literal`;

// String concatenation
let full = str1 + ' ' + str2; // "Hello World"
let full2 = `${str1} ${str2}`; // "Hello World"

// String length
console.log(str1.length); // 5
```

### Common String Methods

```javascript
let str = 'Hello World';

// Case conversion
str.toUpperCase();           // "HELLO WORLD"
str.toLowerCase();           // "hello world"

// Getting characters
str.charAt(0);               // "H"
str[0];                      // "H"
str.charCodeAt(0);           // 72 (ASCII code)

// Finding substrings
str.indexOf('World');        // 6
str.lastIndexOf('o');        // 7
str.includes('World');       // true
str.startsWith('Hello');     // true
str.endsWith('World');       // true

// Extracting parts
str.slice(0, 5);             // "Hello"
str.substring(0, 5);         // "Hello"
str.substr(0, 5);            // "Hello" (deprecated)

// Replacing
str.replace('World', 'JS');  // "Hello JS"
str.replaceAll('o', '0');    // "Hell0 W0rld"

// Splitting
str.split(' ');              // ['Hello', 'World']
str.split('');               // ['H','e','l','l','o',' ','W'...]

// Trimming
let str2 = '  Hello  ';
str2.trim();                 // "Hello"
str2.trimStart();            // "Hello  "
str2.trimEnd();              // "  Hello"

// Repeating
str.repeat(2);               // "Hello WorldHello World"

// Padding
str.padStart(15, '*');       // "****Hello World"
str.padEnd(15, '*');         // "Hello World****"
```

---

## DOM Manipulation

### What is the DOM?

The **Document Object Model (DOM)** is a tree structure representing all elements in an HTML document. JavaScript can access and modify it.

### Selecting Elements

```javascript
// By ID
let element = document.getElementById('myId');

// By class name
let elements = document.getElementsByClassName('myClass');

// By tag name
let divs = document.getElementsByTagName('div');

// Modern way - query selector (CSS selector)
let element = document.querySelector('#myId'); // Single element
let elements = document.querySelectorAll('.myClass'); // All elements
```

### Modifying Elements

```javascript
let element = document.getElementById('myElement');

// Change text content
element.textContent = 'New text';
element.innerText = 'New text';

// Change HTML content
element.innerHTML = '<b>Bold text</b>';

// Change attributes
element.setAttribute('class', 'newClass');
element.setAttribute('id', 'newId');
element.getAttribute('class');

// Shorthand for common attributes
element.id = 'newId';
element.className = 'myClass';
element.title = 'Hover text';

// Change styles
element.style.color = 'red';
element.style.backgroundColor = 'blue';
element.style.fontSize = '20px';
```

### Creating and Adding Elements

```javascript
// Create new element
let newParagraph = document.createElement('p');
newParagraph.textContent = 'This is a new paragraph';

// Add to page
let container = document.getElementById('container');
container.appendChild(newParagraph); // Add as last child
container.insertBefore(newParagraph, container.firstChild); // Add as first child

// Remove element
container.removeChild(newParagraph);
newParagraph.remove(); // Direct remove (modern)

// Replace element
let newDiv = document.createElement('div');
container.replaceChild(newDiv, newParagraph);
```

### Traversing the DOM

```javascript
let element = document.getElementById('myElement');

// Parent
element.parentElement;
element.parentNode;

// Children
element.children;        // HTMLCollection
element.childNodes;      // NodeList (includes text nodes)
element.firstChild;
element.lastChild;

// Siblings
element.nextSibling;
element.previousSibling;
element.nextElementSibling;
element.previousElementSibling;
```

### Classes and Styles

```javascript
let element = document.getElementById('myElement');

// Working with classes
element.classList.add('active');
element.classList.remove('active');
element.classList.toggle('active'); // Add if not present, remove if present
element.classList.contains('active');

// Get all classes
element.className; // Space-separated string
element.classList; // DOMTokenList

// Multiple classes at once
element.classList.add('class1', 'class2');
element.classList.remove('class1', 'class2');
```

---

## Events

### What are Events?

Events are actions or occurrences in the browser (click, type, load, etc.). JavaScript can respond to these events.

### Adding Event Listeners

```html
<!-- HTML -->
<button id="myButton">Click me</button>
<input type="text" id="myInput">
<div id="myDiv"></div>

<script>
// Method 1: addEventListener (recommended)
let button = document.getElementById('myButton');
button.addEventListener('click', function() {
  console.log('Button clicked!');
});

// Method 2: Inline in HTML (not recommended)
// <button onclick="handleClick()">Click me</button>
// function handleClick() { console.log('Clicked'); }

// Remove event listener
function handleClick() {
  console.log('Clicked');
}
button.addEventListener('click', handleClick);
button.removeEventListener('click', handleClick);
</script>
```

### Common Events

```javascript
let input = document.getElementById('myInput');
let div = document.getElementById('myDiv');

// Click event
element.addEventListener('click', (event) => {
  console.log('Clicked');
});

// Double click
element.addEventListener('dblclick', () => {
  console.log('Double clicked');
});

// Mouse events
element.addEventListener('mouseover', () => console.log('Mouse over'));
element.addEventListener('mouseout', () => console.log('Mouse out'));
element.addEventListener('mousedown', () => console.log('Mouse down'));
element.addEventListener('mouseup', () => console.log('Mouse up'));

// Keyboard events
input.addEventListener('keydown', (e) => console.log('Key pressed:', e.key));
input.addEventListener('keyup', (e) => console.log('Key released:', e.key));
input.addEventListener('keypress', (e) => console.log('Key pressed:', e.key));

// Form events
input.addEventListener('input', () => console.log('Input value:', input.value));
input.addEventListener('change', () => console.log('Input changed'));
input.addEventListener('focus', () => console.log('Focused'));
input.addEventListener('blur', () => console.log('Lost focus'));

// Document events
document.addEventListener('DOMContentLoaded', () => {
  console.log('DOM fully loaded');
});

window.addEventListener('load', () => {
  console.log('All resources loaded');
});

window.addEventListener('scroll', () => {
  console.log('Page scrolled');
});

window.addEventListener('resize', () => {
  console.log('Window resized');
});
```

### Event Object

```javascript
element.addEventListener('click', (event) => {
  console.log('Event object:', event);
  
  event.type;           // 'click'
  event.target;         // Element that triggered event
  event.currentTarget;  // Element with listener
  event.clientX;        // Mouse X position relative to viewport
  event.clientY;        // Mouse Y position relative to viewport
  event.key;            // Keyboard key pressed
  event.code;           // Keyboard key code
  event.preventDefault(); // Prevent default action
  event.stopPropagation(); // Stop event bubbling
});
```

---

## Asynchronous Programming

### What is Asynchronous Programming?

By default, JavaScript is **synchronous** (code runs line by line). **Asynchronous** code allows multiple operations to happen independently.

### Callbacks

```javascript
// Simple callback
function greet(name, callback) {
  console.log('Hello ' + name);
  callback();
}

greet('John', function() {
  console.log('Greeting complete');
});

// Callback with data
function fetchData(callback) {
  setTimeout(() => {
    const data = { id: 1, name: 'John' };
    callback(data);
  }, 1000);
}

fetchData((data) => {
  console.log(data);
});

// Problem: Callback Hell
fetchData((user) => {
  fetchUserPosts(user.id, (posts) => {
    fetchPostComments(posts[0].id, (comments) => {
      console.log(comments);
    });
  });
});
```

### Promises

```javascript
// Creating a promise
const myPromise = new Promise((resolve, reject) => {
  let success = true;
  
  if (success) {
    resolve('Operation successful!');
  } else {
    reject('Operation failed!');
  }
});

// Using a promise
myPromise
  .then((result) => {
    console.log('Success:', result);
  })
  .catch((error) => {
    console.log('Error:', error);
  })
  .finally(() => {
    console.log('Operation complete');
  });

// Practical example: Simulating API call
function fetchUserData(userId) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      if (userId > 0) {
        resolve({ id: userId, name: 'John', age: 25 });
      } else {
        reject('Invalid user ID');
      }
    }, 1000);
  });
}

fetchUserData(1)
  .then((user) => {
    console.log('User:', user);
    return fetchUserData(2); // Chain promises
  })
  .then((user) => {
    console.log('Next user:', user);
  })
  .catch((error) => {
    console.log('Error:', error);
  });
```

### Async/Await (Modern Way)

```javascript
// Async function returns a promise
async function getData() {
  try {
    const response = await fetch('https://api.example.com/users');
    const data = await response.json();
    return data;
  } catch (error) {
    console.log('Error:', error);
  }
}

// Using async function
getData()
  .then((data) => console.log(data))
  .catch((error) => console.log(error));

// Or with async/await all the way
async function main() {
  try {
    const data = await getData();
    console.log(data);
  } catch (error) {
    console.log('Error:', error);
  }
}

main();

// Multiple async operations
async function fetchMultipleUsers() {
  try {
    const user1 = await fetchUserData(1);
    const user2 = await fetchUserData(2);
    console.log(user1, user2);
  } catch (error) {
    console.log('Error:', error);
  }
}

// Execute in parallel (faster)
async function fetchMultipleUsersParallel() {
  try {
    const [user1, user2] = await Promise.all([
      fetchUserData(1),
      fetchUserData(2)
    ]);
    console.log(user1, user2);
  } catch (error) {
    console.log('Error:', error);
  }
}
```

### setTimeout and setInterval

```javascript
// setTimeout - Execute after delay (milliseconds)
setTimeout(() => {
  console.log('This runs after 2 seconds');
}, 2000);

// Cancel setTimeout
const timerId = setTimeout(() => {
  console.log('This might not run');
}, 2000);
clearTimeout(timerId);

// setInterval - Execute repeatedly
const intervalId = setInterval(() => {
  console.log('This runs every second');
}, 1000);

// Cancel setInterval
clearInterval(intervalId);

// Practical example
let count = 0;
const interval = setInterval(() => {
  count++;
  console.log('Count:', count);
  
  if (count === 5) {
    clearInterval(interval);
  }
}, 1000);
```

---

## Error Handling

### Try-Catch Block

```javascript
try {
  // Code that might throw error
  let result = 10 / 0; // Won't throw error, but let's use a bad example
  undefinedVariable; // This will throw ReferenceError
} catch (error) {
  // Handle error
  console.log('Error caught:', error.message);
  console.log('Error type:', error.name);
} finally {
  // Always runs, whether error or not
  console.log('Cleanup code here');
}

// Example
function divide(a, b) {
  try {
    if (b === 0) {
      throw new Error('Division by zero not allowed');
    }
    return a / b;
  } catch (error) {
    console.log('Error:', error.message);
    return null;
  }
}

console.log(divide(10, 0)); // Error: Division by zero not allowed
```

### Throwing Custom Errors

```javascript
function validateAge(age) {
  if (age < 0) {
    throw new Error('Age cannot be negative');
  }
  if (age > 150) {
    throw new RangeError('Age must be less than 150');
  }
  return 'Valid age';
}

try {
  console.log(validateAge(-5));
} catch (error) {
  console.log('Caught error:', error.message);
}
```

### Error Types

```javascript
// Different error types
new Error('Generic error');
new TypeError('Type mismatch');
new ReferenceError('Invalid reference');
new SyntaxError('Syntax problem');
new RangeError('Value out of range');
new URIError('URI error');

// Error properties
const error = new Error('Something went wrong');
console.log(error.message);     // "Something went wrong"
console.log(error.name);        // "Error"
console.log(error.stack);       // Stack trace
```

---

## ES6+ Features

### Template Literals

```javascript
let name = 'John';
let age = 25;

// Regular concatenation (old way)
let message1 = 'My name is ' + name + ' and I am ' + age + ' years old';

// Template literal (modern way)
let message2 = `My name is ${name} and I am ${age} years old`;

// Multi-line strings
let text = `
  Hello everyone!
  This is a multi-line string.
  No need to use \n anymore.
`;
```

### Destructuring

```javascript
// Array destructuring
const [a, b, c] = [1, 2, 3];
const [first, ...rest] = [1, 2, 3, 4, 5]; // rest gets [2,3,4,5]

// Object destructuring
const { name, age, city } = { name: 'John', age: 25, city: 'NYC' };
const { name: personName } = { name: 'John' }; // Rename

// Function parameters
function greet({ name, age }) {
  console.log(`Hello ${name}, you are ${age} years old`);
}
greet({ name: 'John', age: 25 });
```

### Spread Operator

```javascript
// Array spread
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const combined = [...arr1, ...arr2]; // [1,2,3,4,5,6]

// Object spread
const obj1 = { name: 'John', age: 25 };
const obj2 = { city: 'NYC', ...obj1 };
// { city: 'NYC', name: 'John', age: 25 }

// Copy array/object (shallow)
const copy = [...arr1];
const objCopy = { ...obj1 };

// Function arguments
function sum(a, b, c) {
  return a + b + c;
}
const numbers = [1, 2, 3];
console.log(sum(...numbers)); // 6
```

### Classes

```javascript
class Person {
  // Constructor
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  
  // Method
  greet() {
    return `Hello, I am ${this.name}`;
  }
  
  // Getter
  get info() {
    return `${this.name} is ${this.age} years old`;
  }
  
  // Setter
  set age(newAge) {
    if (newAge > 0) {
      this._age = newAge;
    }
  }
  
  // Static method (called on class, not instance)
  static compare(person1, person2) {
    return person1.age > person2.age;
  }
}

// Using class
const john = new Person('John', 25);
console.log(john.greet());  // "Hello, I am John"
console.log(john.info);     // "John is 25 years old"

// Inheritance
class Employee extends Person {
  constructor(name, age, salary) {
    super(name, age); // Call parent constructor
    this.salary = salary;
  }
  
  greet() {
    return super.greet() + ` and I earn ${this.salary}`;
  }
}

const emp = new Employee('Jane', 30, 50000);
console.log(emp.greet());
```

### Arrow Functions

```javascript
// Regular function
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => {
  return a + b;
};

// Shorthand (single expression)
const add = (a, b) => a + b;

// Single parameter (no parentheses needed)
const square = x => x * x;

// Array methods with arrow functions
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(x => x * 2);
const evens = numbers.filter(x => x % 2 === 0);
```

### Default and Rest Parameters

```javascript
// Default parameters
function greet(name = 'Guest', greeting = 'Hello') {
  return `${greeting}, ${name}!`;
}

// Rest parameters
function sum(...numbers) {
  return numbers.reduce((a, b) => a + b, 0);
}

console.log(sum(1, 2, 3, 4, 5)); // 15
```

### Let and Const

```javascript
// var (function-scoped, avoid)
var x = 10;

// let (block-scoped, can reassign)
let y = 20;
y = 30; // OK

// const (block-scoped, cannot reassign)
const z = 40;
// z = 50; // Error!

// But for objects/arrays, properties can be modified
const obj = { name: 'John' };
obj.age = 25; // Allowed - modifying property
// obj = {}; // Error - cannot reassign

// Best practice: Use const by default, let if you need to reassign
```

---

## Best Practices

### 1. Code Organization
```javascript
// ✓ Good: Organized and modular
// data.js
export function fetchUsers() { /* ... */ }

// ui.js
import { fetchUsers } from './data.js';
function displayUsers() { /* ... */ }

// ✗ Bad: Everything in one file
function fetchUsers() { /* ... */ }
function displayUsers() { /* ... */ }
// ... hundreds more functions
```

### 2. Naming Conventions
```javascript
// ✓ Good: Descriptive names
const userAge = 25;
const isAdmin = true;
function calculateTotalPrice(items) { /* ... */ }

// ✗ Bad: Non-descriptive names
const ua = 25;
const a = true;
function calc(i) { /* ... */ }
```

### 3. Comments and Documentation
```javascript
// ✓ Good: Clear comments
// Calculate the area of a rectangle
function calculateArea(width, height) {
  return width * height;
}

// ✗ Bad: No comments
function ca(w, h) {
  return w * h;
}

// ✗ Bad: Obvious comments
const age = 25; // Set age to 25
```

### 4. Error Handling
```javascript
// ✓ Good: Proper error handling
async function fetchData() {
  try {
    const response = await fetch(url);
    if (!response.ok) throw new Error('Network error');
    return await response.json();
  } catch (error) {
    console.error('Failed to fetch data:', error);
    return null;
  }
}

// ✗ Bad: Ignoring errors
async function fetchData() {
  const response = await fetch(url);
  return await response.json();
}
```

### 5. Avoid Global Variables
```javascript
// ✓ Good: Use functions/modules
const app = {
  counter: 0,
  increment() { this.counter++; }
};

// ✗ Bad: Global variable
let counter = 0;
function increment() { counter++; }
```

### 6. Use Const by Default
```javascript
// ✓ Good: Default to const
const name = 'John';
const calculateAge = (birthYear) => new Date().getFullYear() - birthYear;
let count = 0; // Use let only if you need to reassign

// ✗ Bad: Using var everywhere
var name = 'John';
var calculateAge = function(birthYear) { /* ... */ };
```

### 7. Keep Functions Small and Focused
```javascript
// ✓ Good: Single responsibility
function validateEmail(email) {
  return email.includes('@');
}

function validatePassword(password) {
  return password.length >= 8;
}

// ✗ Bad: Doing too much
function validate(email, password) {
  // Complex validation logic
  // Saving to database
  // Sending email
}
```

### 8. Use Meaningful Variable Names
```javascript
// ✓ Good
const userData = { name: 'John', age: 25 };
const userList = [user1, user2, user3];
const isActive = true;

// ✗ Bad
const data = { name: 'John', age: 25 };
const list = [user1, user2, user3];
const flag = true;
```

### 9. Avoid Nested Callbacks (Callback Hell)
```javascript
// ✓ Good: Use promises or async/await
async function processData() {
  try {
    const users = await fetchUsers();
    const posts = await fetchPosts(users[0].id);
    const comments = await fetchComments(posts[0].id);
    return comments;
  } catch (error) {
    console.error(error);
  }
}

// ✗ Bad: Callback hell
fetchUsers((users) => {
  fetchPosts(users[0].id, (posts) => {
    fetchComments(posts[0].id, (comments) => {
      console.log(comments);
    });
  });
});
```

### 10. DRY Principle (Don't Repeat Yourself)
```javascript
// ✓ Good: Reusable function
function formatPrice(price) {
  return '$' + price.toFixed(2);
}

const price1 = formatPrice(100);
const price2 = formatPrice(200);

// ✗ Bad: Repeating code
const price1 = '$' + (100).toFixed(2);
const price2 = '$' + (200).toFixed(2);
```

---

## Quick Reference

### Data Types Summary
| Type | Example | Check |
|------|---------|-------|
| String | `'hello'`, `"world"` | `typeof x === 'string'` |
| Number | `42`, `3.14`, `-10` | `typeof x === 'number'` |
| Boolean | `true`, `false` | `typeof x === 'boolean'` |
| Null | `null` | `x === null` |
| Undefined | `undefined` | `x === undefined` |
| Object | `{}`, `[]`, `{}` | `typeof x === 'object'` |
| Symbol | `Symbol('id')` | `typeof x === 'symbol'` |

### Common Array Methods
| Method | Purpose | Returns |
|--------|---------|---------|
| `push()` | Add element to end | New length |
| `pop()` | Remove from end | Removed element |
| `map()` | Transform elements | New array |
| `filter()` | Keep matching elements | New array |
| `find()` | Get first match | Element or undefined |
| `includes()` | Check if exists | Boolean |
| `join()` | Convert to string | String |

### Common String Methods
| Method | Purpose |
|--------|---------|
| `toUpperCase()` | Convert to uppercase |
| `toLowerCase()` | Convert to lowercase |
| `slice(start, end)` | Extract substring |
| `split(separator)` | Split into array |
| `includes(substring)` | Check if contains |
| `replace(old, new)` | Replace text |
| `trim()` | Remove whitespace |

### Useful Keyboard Shortcuts (Browser DevTools)
- `F12` - Open DevTools
- `Ctrl + Shift + I` - Open DevTools
- `Ctrl + Shift + J` - Open Console
- `Ctrl + Shift + K` - Go to Console

---

## Summary

### Key Points for Beginners
1. **JavaScript is versatile** - Use it for web, mobile, and desktop apps
2. **Practice regularly** - Build projects to reinforce learning
3. **Understand variables and data types** - Foundation of programming
4. **Master functions** - Core building block of JavaScript
5. **Learn array and object methods** - Most useful tools
6. **Async programming is important** - Modern web development depends on it
7. **Error handling prevents crashes** - Always handle errors gracefully
8. **Use modern syntax** - ES6+ features make code cleaner
9. **Read existing code** - Learn by studying well-written code
10. **Debug with browser DevTools** - Essential skill for developers

### Next Steps
1. **Practice basic syntax** - Variables, operators, control structures
2. **Build simple projects** - Calculator, To-do list, Weather app
3. **Learn DOM manipulation** - Interact with web pages
4. **Understand async programming** - Make API calls
5. **Study popular frameworks** - React, Vue, Angular
6. **Build more complex projects** - Apply everything you've learned

---

## Resources for Further Learning

- **MDN Web Docs**: https://developer.mozilla.org/en-US/docs/Web/JavaScript/
- **JavaScript.info**: https://javascript.info/
- **FreeCodeCamp**: YouTube channel with comprehensive courses
- **Codecademy**: Interactive JavaScript course

---

**Happy Learning! Remember: Consistency is key. Practice regularly and build projects to master JavaScript.** 🚀

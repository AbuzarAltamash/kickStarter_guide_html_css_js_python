# 🚀 JavaScript Basics

JavaScript is the programming language that makes websites interactive. While HTML provides structure and CSS handles styling, JavaScript adds behavior and functionality to web pages.

## 📋 What You'll Learn
- What JavaScript is and how it works
- Variables and data types
- Operators and expressions
- Conditional statements (if/else)
- Loops
- Functions
- Working with arrays and objects
- Basic DOM manipulation (interacting with HTML elements)

## 🚀 Let's Start!

### What is JavaScript?
JavaScript is a programming language that runs in web browsers. It allows you to:
- Respond to user actions (like button clicks)
- Update content dynamically without reloading the page
- Create interactive features like sliders, forms, and games
- Communicate with servers to fetch or send data

### How to Add JavaScript to HTML

There are three ways to add JavaScript to your HTML:

#### 1. Inline JavaScript
```html
<button onclick="alert('Hello, World!')">Click Me</button>
```

#### 2. Internal JavaScript (in the `<script>` tag)
```html
<!DOCTYPE html>
<html>
<head>
    <title>My Page</title>
    <script>
        function sayHello() {
            alert('Hello, World!');
        }
    </script>
</head>
<body>
    <button onclick="sayHello()">Click Me</button>
</body>
</html>
```

#### 3. External JavaScript (in a separate .js file) - BEST PRACTICE!
Create a file named `script.js`:
```javascript
function sayHello() {
    alert('Hello, World!');
}
```

Then link it in your HTML:
```html
<!DOCTYPE html>
<html>
<head>
    <title>My Page</title>
    <script src="script.js"></script>
</head>
<body>
    <button onclick="sayHello()">Click Me</button>
</body>
</html>
```

### Variables and Data Types

Variables are containers for storing data. In JavaScript, you can declare variables using `var`, `let`, or `const`:

```javascript
// Using let (recommended for variables that will change)
let age = 18;
let name = "John";

// Using const (for variables that won't change)
const PI = 3.14159;

// You can also declare without assigning a value
let score;
score = 100; // Assign later
```

JavaScript has several data types:

```javascript
// String (text)
let greeting = "Hello, World!";

// Number
let age = 18;
let price = 9.99;

// Boolean (true/false)
let isStudent = true;

// Array (list of items)
let colors = ["red", "green", "blue"];

// Object (collection of name-value pairs)
let person = {
    firstName: "John",
    lastName: "Doe",
    age: 30
};

// Undefined
let something;  // Value is undefined

// Null (explicitly nothing)
let empty = null;
```

### Operators

JavaScript has various operators for performing operations:

```javascript
// Arithmetic operators
let sum = 5 + 3;       // Addition: 8
let difference = 10 - 5; // Subtraction: 5
let product = 4 * 3;    // Multiplication: 12
let quotient = 15 / 3;  // Division: 5
let remainder = 10 % 3; // Modulus (remainder): 1

// Assignment operators
let x = 10;
x += 5;  // Same as: x = x + 5; (now x is 15)
x -= 3;  // Same as: x = x - 3; (now x is 12)
x *= 2;  // Same as: x = x * 2; (now x is 24)
x /= 4;  // Same as: x = x / 4; (now x is 6)

// Comparison operators
let isEqual = 5 == "5";     // Equality (true, only checks value)
let isStrictEqual = 5 === "5"; // Strict equality (false, checks value and type)
let isNotEqual = 5 != 10;   // Not equal (true)
let isGreater = 10 > 5;     // Greater than (true)
let isLess = 3 < 8;         // Less than (true)

// Logical operators
let andResult = true && false;  // Logical AND (false)
let orResult = true || false;   // Logical OR (true)
let notResult = !true;          // Logical NOT (false)
```

### Conditional Statements

Conditional statements help your code make decisions:

```javascript
// If statement
let age = 18;

if (age >= 18) {
    console.log("You are an adult");
}

// If-else statement
if (age >= 18) {
    console.log("You are an adult");
} else {
    console.log("You are a minor");
}

// If-else if-else statement
let score = 85;

if (score >= 90) {
    console.log("Grade: A");
} else if (score >= 80) {
    console.log("Grade: B");
} else if (score >= 70) {
    console.log("Grade: C");
} else {
    console.log("Grade: F");
}

// Ternary operator (shorthand if-else)
let message = age >= 18 ? "You can vote" : "You cannot vote";
```

### Loops

Loops help you repeat code:

```javascript
// For loop
for (let i = 0; i < 5; i++) {
    console.log(i); // Prints 0, 1, 2, 3, 4
}

// While loop
let count = 0;
while (count < 5) {
    console.log(count);
    count++;
}

// For...of loop (for arrays)
let fruits = ["apple", "banana", "orange"];
for (let fruit of fruits) {
    console.log(fruit);
}

// For...in loop (for objects)
let person = {name: "John", age: 30, city: "New York"};
for (let key in person) {
    console.log(key + ": " + person[key]);
}
```

### Functions

Functions are reusable blocks of code:

```javascript
// Function declaration
function greet(name) {
    return "Hello, " + name + "!";
}

// Function call
let greeting = greet("John"); // "Hello, John!"

// Function with default parameter
function greetWithDefault(name = "Guest") {
    return "Hello, " + name + "!";
}

greetWithDefault(); // "Hello, Guest!"

// Arrow function (shorter syntax)
const multiply = (a, b) => a * b;
multiply(5, 3); // 15
```

### Arrays

Arrays store multiple values in a single variable:

```javascript
// Create an array
let fruits = ["apple", "banana", "orange"];

// Access array elements (indexing starts at 0)
let firstFruit = fruits[0]; // "apple"

// Add elements to an array
fruits.push("mango"); // Adds to the end
fruits.unshift("grape"); // Adds to the beginning

// Remove elements
let lastFruit = fruits.pop(); // Removes from the end
let firstFruitRemoved = fruits.shift(); // Removes from the beginning

// Array length
let numberOfFruits = fruits.length;

// Find element index
let index = fruits.indexOf("banana");

// Loop through an array
fruits.forEach(function(fruit) {
    console.log(fruit);
});

// Create a new array by transforming another
let uppercaseFruits = fruits.map(function(fruit) {
    return fruit.toUpperCase();
});

// Filter an array
let longFruits = fruits.filter(function(fruit) {
    return fruit.length > 5;
});
```

### Objects

Objects store data in name-value pairs:

```javascript
// Create an object
let person = {
    firstName: "John",
    lastName: "Doe",
    age: 30,
    hobbies: ["reading", "music", "sports"],
    address: {
        street: "123 Main St",
        city: "New York"
    },
    fullName: function() {
        return this.firstName + " " + this.lastName;
    }
};

// Access object properties
let age = person.age; // Dot notation
let lastName = person["lastName"]; // Bracket notation

// Update properties
person.age = 31;

// Add new properties
person.email = "john@example.com";

// Call object methods
let fullName = person.fullName(); // "John Doe"
```

### DOM Manipulation

DOM (Document Object Model) manipulation allows you to interact with HTML elements:

```javascript
// Select elements by ID
let heading = document.getElementById("myHeading");

// Select elements by class
let paragraphs = document.getElementsByClassName("myParagraph");

// Select elements by tag name
let allParagraphs = document.getElementsByTagName("p");

// More modern selectors (return first match)
let element = document.querySelector(".myClass");

// Modern selectors (return all matches as NodeList)
let elements = document.querySelectorAll("p.myClass");

// Change content
element.textContent = "New text content"; // Just text
element.innerHTML = "Text with <strong>HTML</strong>"; // With HTML

// Change styles
element.style.color = "blue";
element.style.fontSize = "18px";

// Add/remove CSS classes
element.classList.add("highlight");
element.classList.remove("old-class");
element.classList.toggle("visible");

// Create new elements
let newParagraph = document.createElement("p");
newParagraph.textContent = "This is a new paragraph";

// Add elements to the DOM
document.body.appendChild(newParagraph); // Add at the end of body
parentElement.insertBefore(newParagraph, existingElement);

// Remove elements
element.remove();
// Or old way
parentElement.removeChild(childElement);
```

### Event Handling

Events allow you to respond to user actions:

```javascript
// Add event with addEventListener
let button = document.getElementById("myButton");

button.addEventListener("click", function() {
    alert("Button was clicked!");
});

// With a named function
function handleClick() {
    alert("Button was clicked!");
}
button.addEventListener("click", handleClick);

// Common events
// click, dblclick, mouseover, mouseout, keydown, keyup, submit, load, change
```

## 🎯 Practice Exercise

Create a simple counter application:

1. Create an HTML file with:
   - A heading that displays the current count
   - Buttons to increment and decrement the count
   - A reset button

2. Create a JavaScript file that:
   - Tracks the current count
   - Updates the display when buttons are clicked
   - Resets the count when the reset button is clicked

## 📚 Next Steps

Once you're comfortable with these JavaScript basics, move on to [JavaScript Practicals](/javascript/practicals/README.md) to build some interactive projects! 
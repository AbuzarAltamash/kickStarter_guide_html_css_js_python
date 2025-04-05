# 🧩 JavaScript Practicals

Now that you've learned the basics of JavaScript, let's build some fun and practical projects to strengthen your skills!

## 🎯 What You'll Build

In this section, you'll create:
1. A simple counter
2. An interactive to-do list
3. A simple calculator
4. A form validator

## Project 1: Simple Counter 🔢

### What You'll Create
A webpage with buttons to increase, decrease, and reset a counter.

### Step-by-Step Guide

1. Create an HTML file named `counter.html`:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Counter</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        #count {
            font-size: 60px;
            margin: 20px;
        }
        button {
            padding: 10px 20px;
            margin: 0 5px;
            font-size: 16px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
        }
        .increase {
            background-color: #4CAF50;
            color: white;
        }
        .decrease {
            background-color: #f44336;
            color: white;
        }
        .reset {
            background-color: #808080;
            color: white;
        }
    </style>
</head>
<body>
    <h1>Counter</h1>
    <div id="count">0</div>
    <div>
        <button class="decrease" id="decreaseBtn">Decrease</button>
        <button class="reset" id="resetBtn">Reset</button>
        <button class="increase" id="increaseBtn">Increase</button>
    </div>
    
    <script src="counter.js"></script>
</body>
</html>
```

2. Create a JavaScript file named `counter.js`:

```javascript
// Get elements from the DOM
const countDisplay = document.getElementById('count');
const increaseBtn = document.getElementById('increaseBtn');
const decreaseBtn = document.getElementById('decreaseBtn');
const resetBtn = document.getElementById('resetBtn');

// Initialize count
let count = 0;

// Update the display
function updateDisplay() {
    countDisplay.textContent = count;
    
    // Change color based on value
    if (count > 0) {
        countDisplay.style.color = '#4CAF50'; // Green
    } else if (count < 0) {
        countDisplay.style.color = '#f44336'; // Red
    } else {
        countDisplay.style.color = 'black';   // Default
    }
}

// Event listeners for buttons
increaseBtn.addEventListener('click', function() {
    count++;
    updateDisplay();
});

decreaseBtn.addEventListener('click', function() {
    count--;
    updateDisplay();
});

resetBtn.addEventListener('click', function() {
    count = 0;
    updateDisplay();
});

// Initialize the display
updateDisplay();
```

Open the HTML file in your browser to see your counter in action!

## Project 2: To-Do List 📝

### What You'll Create
An interactive to-do list where users can add, check off, and delete tasks.

### Step-by-Step Guide

1. Create an HTML file named `todo.html`:

```html
<!DOCTYPE html>
<html>
<head>
    <title>To-Do List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 500px;
            margin: 0 auto;
            padding: 20px;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        .input-container {
            display: flex;
            margin-bottom: 20px;
        }
        #taskInput {
            flex-grow: 1;
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ddd;
            border-radius: 4px 0 0 4px;
        }
        #addButton {
            padding: 10px 15px;
            background-color: #4CAF50;
            color: white;
            font-size: 16px;
            border: none;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            padding: 10px 15px;
            margin-bottom: 10px;
            background-color: #f9f9f9;
            border-radius: 4px;
            display: flex;
            align-items: center;
        }
        li.completed {
            text-decoration: line-through;
            color: #888;
            background-color: #f0f0f0;
        }
        .delete-btn {
            margin-left: auto;
            color: #ff4d4d;
            background: none;
            border: none;
            font-size: 18px;
            cursor: pointer;
        }
        .task-text {
            margin-left: 10px;
            flex-grow: 1;
        }
    </style>
</head>
<body>
    <h1>My To-Do List</h1>
    <div class="input-container">
        <input type="text" id="taskInput" placeholder="Add a new task...">
        <button id="addButton">Add</button>
    </div>
    <ul id="taskList"></ul>

    <script src="todo.js"></script>
</body>
</html>
```

2. Create a JavaScript file named `todo.js`:

```javascript
// Get elements from the DOM
const taskInput = document.getElementById('taskInput');
const addButton = document.getElementById('addButton');
const taskList = document.getElementById('taskList');

// Function to add a new task
function addTask() {
    // Get the task text
    const taskText = taskInput.value.trim();
    
    // Only add if the input isn't empty
    if (taskText !== '') {
        // Create a new list item
        const li = document.createElement('li');
        
        // Create a checkbox
        const checkbox = document.createElement('input');
        checkbox.type = 'checkbox';
        checkbox.addEventListener('change', function() {
            if (this.checked) {
                li.classList.add('completed');
            } else {
                li.classList.remove('completed');
            }
        });
        
        // Create a span for the task text
        const span = document.createElement('span');
        span.className = 'task-text';
        span.textContent = taskText;
        
        // Create a delete button
        const deleteButton = document.createElement('button');
        deleteButton.className = 'delete-btn';
        deleteButton.textContent = '×';
        deleteButton.addEventListener('click', function() {
            li.remove();
        });
        
        // Assemble the list item
        li.appendChild(checkbox);
        li.appendChild(span);
        li.appendChild(deleteButton);
        
        // Add the new task to the list
        taskList.appendChild(li);
        
        // Clear the input field
        taskInput.value = '';
        
        // Focus back on the input
        taskInput.focus();
    }
}

// Add a task when the button is clicked
addButton.addEventListener('click', addTask);

// Also add a task when Enter key is pressed
taskInput.addEventListener('keypress', function(e) {
    if (e.key === 'Enter') {
        addTask();
    }
});
```

Open the HTML file in your browser to see your to-do list in action!

## Project 3: Simple Calculator 🧮

### What You'll Create
A basic calculator that can perform simple arithmetic operations.

### Step-by-Step Guide

1. Create an HTML file named `calculator.html`:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f5f5f5;
        }
        .calculator {
            background-color: #333;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        .display {
            background-color: #eee;
            border: none;
            padding: 20px;
            font-size: 24px;
            text-align: right;
            width: 100%;
            margin-bottom: 20px;
            border-radius: 5px;
            box-sizing: border-box;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 10px;
        }
        button {
            background-color: #4d4d4d;
            color: white;
            border: none;
            padding: 15px;
            font-size: 18px;
            cursor: pointer;
            border-radius: 5px;
        }
        button:hover {
            background-color: #666;
        }
        .operator {
            background-color: #ff9500;
        }
        .operator:hover {
            background-color: #ffb13d;
        }
        .equals {
            background-color: #4CAF50;
        }
        .equals:hover {
            background-color: #68c36c;
        }
        .clear {
            background-color: #f44336;
        }
        .clear:hover {
            background-color: #f77066;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" class="display" id="display" disabled>
        <div class="buttons">
            <button class="clear" id="clear">C</button>
            <button class="operator" id="backspace">⌫</button>
            <button class="operator" id="divide">÷</button>
            <button class="operator" id="multiply">×</button>
            
            <button id="seven">7</button>
            <button id="eight">8</button>
            <button id="nine">9</button>
            <button class="operator" id="subtract">-</button>
            
            <button id="four">4</button>
            <button id="five">5</button>
            <button id="six">6</button>
            <button class="operator" id="add">+</button>
            
            <button id="one">1</button>
            <button id="two">2</button>
            <button id="three">3</button>
            <button class="equals" id="equals">=</button>
            
            <button id="zero" style="grid-column: span 2;">0</button>
            <button id="decimal">.</button>
        </div>
    </div>
    
    <script src="calculator.js"></script>
</body>
</html>
```

2. Create a JavaScript file named `calculator.js`:

```javascript
// Get elements from the DOM
const display = document.getElementById('display');
const buttons = document.querySelectorAll('button');

// Initialize variables
let currentInput = '';
let firstOperand = null;
let operator = null;
let waitingForSecondOperand = false;

// Function to update the display
function updateDisplay() {
    display.value = currentInput || '0';
}

// Function to handle digit input
function inputDigit(digit) {
    if (waitingForSecondOperand) {
        currentInput = digit;
        waitingForSecondOperand = false;
    } else {
        // If current input is '0', replace it, otherwise append
        currentInput = currentInput === '0' ? digit : currentInput + digit;
    }
}

// Function to handle decimal point
function inputDecimal() {
    // If waiting for second operand, start with '0.'
    if (waitingForSecondOperand) {
        currentInput = '0.';
        waitingForSecondOperand = false;
        return;
    }
    
    // Only add decimal if there isn't one already
    if (!currentInput.includes('.')) {
        currentInput += '.';
    }
}

// Function to handle operators
function handleOperator(nextOperator) {
    const inputValue = parseFloat(currentInput);
    
    // If there's a pending operation and we already have a first operand
    if (operator && waitingForSecondOperand) {
        // Just update the operator
        operator = nextOperator;
        return;
    }
    
    // If this is the first operand
    if (firstOperand === null) {
        firstOperand = inputValue;
    } else if (operator) {
        // If we already have a first operand and an operator, 
        // calculate the result
        const result = performCalculation();
        currentInput = String(result);
        firstOperand = result;
    }
    
    waitingForSecondOperand = true;
    operator = nextOperator;
}

// Function to perform calculation
function performCalculation() {
    const secondOperand = parseFloat(currentInput);
    let result = 0;
    
    switch (operator) {
        case '+':
            result = firstOperand + secondOperand;
            break;
        case '-':
            result = firstOperand - secondOperand;
            break;
        case '×':
            result = firstOperand * secondOperand;
            break;
        case '÷':
            result = firstOperand / secondOperand;
            break;
        default:
            return secondOperand;
    }
    
    return result;
}

// Function to reset the calculator
function resetCalculator() {
    currentInput = '';
    firstOperand = null;
    operator = null;
    waitingForSecondOperand = false;
}

// Function to backspace
function backspace() {
    currentInput = currentInput.slice(0, -1);
}

// Add event listeners to all buttons
buttons.forEach(button => {
    button.addEventListener('click', function() {
        // Digits 0-9
        if (button.id >= 'zero' && button.id <= 'nine') {
            const digit = button.textContent;
            inputDigit(digit);
            updateDisplay();
        }
        
        // Decimal point
        else if (button.id === 'decimal') {
            inputDecimal();
            updateDisplay();
        }
        
        // Operators
        else if (button.id === 'add') {
            handleOperator('+');
            updateDisplay();
        }
        else if (button.id === 'subtract') {
            handleOperator('-');
            updateDisplay();
        }
        else if (button.id === 'multiply') {
            handleOperator('×');
            updateDisplay();
        }
        else if (button.id === 'divide') {
            handleOperator('÷');
            updateDisplay();
        }
        
        // Equals
        else if (button.id === 'equals') {
            if (operator && !waitingForSecondOperand) {
                const result = performCalculation();
                currentInput = String(result);
                firstOperand = result;
                operator = null;
                waitingForSecondOperand = false;
                updateDisplay();
            }
        }
        
        // Clear
        else if (button.id === 'clear') {
            resetCalculator();
            updateDisplay();
        }
        
        // Backspace
        else if (button.id === 'backspace') {
            backspace();
            updateDisplay();
        }
    });
});

// Initialize display
updateDisplay();
```

Open the HTML file in your browser to see your calculator in action!

## Project 4: Form Validator 📋

### What You'll Create
A form with validation that checks user inputs and shows error messages.

### Step-by-Step Guide

1. Create an HTML file named `form.html`:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Form Validator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
        }
        .container {
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            padding: 30px;
            width: 100%;
            max-width: 500px;
        }
        h2 {
            text-align: center;
            margin-bottom: 30px;
            color: #333;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: #555;
        }
        input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
            box-sizing: border-box;
        }
        button {
            background-color: #4CAF50;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
            font-size: 16px;
            margin-top: 10px;
        }
        button:hover {
            background-color: #45a049;
        }
        .error {
            color: #f44336;
            font-size: 14px;
            margin-top: 5px;
            display: none;
        }
        input.error-border {
            border-color: #f44336;
        }
        .success-message {
            text-align: center;
            color: #4CAF50;
            font-weight: bold;
            margin-top: 20px;
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Sign Up Form</h2>
        <form id="registrationForm">
            <div class="form-group">
                <label for="username">Username</label>
                <input type="text" id="username" placeholder="Enter username">
                <div id="usernameError" class="error">Username must be at least 3 characters</div>
            </div>
            
            <div class="form-group">
                <label for="email">Email</label>
                <input type="text" id="email" placeholder="Enter email">
                <div id="emailError" class="error">Please enter a valid email</div>
            </div>
            
            <div class="form-group">
                <label for="password">Password</label>
                <input type="password" id="password" placeholder="Enter password">
                <div id="passwordError" class="error">Password must be at least 6 characters</div>
            </div>
            
            <div class="form-group">
                <label for="confirmPassword">Confirm Password</label>
                <input type="password" id="confirmPassword" placeholder="Confirm password">
                <div id="confirmPasswordError" class="error">Passwords do not match</div>
            </div>
            
            <button type="submit">Submit</button>
        </form>
        
        <div id="successMessage" class="success-message">
            Registration successful!
        </div>
    </div>
    
    <script src="form.js"></script>
</body>
</html>
```

2. Create a JavaScript file named `form.js`:

```javascript
// Get form elements
const form = document.getElementById('registrationForm');
const username = document.getElementById('username');
const email = document.getElementById('email');
const password = document.getElementById('password');
const confirmPassword = document.getElementById('confirmPassword');
const successMessage = document.getElementById('successMessage');

// Show error function
function showError(input, errorId, message) {
    const errorElement = document.getElementById(errorId);
    input.classList.add('error-border');
    errorElement.textContent = message;
    errorElement.style.display = 'block';
}

// Show success function (removes error styling)
function showSuccess(input, errorId) {
    const errorElement = document.getElementById(errorId);
    input.classList.remove('error-border');
    errorElement.style.display = 'none';
}

// Check email validity
function isValidEmail(email) {
    const re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(String(email).toLowerCase());
}

// Check required fields
function checkRequired(input, errorId, message) {
    if (input.value.trim() === '') {
        showError(input, errorId, message);
        return false;
    } else {
        showSuccess(input, errorId);
        return true;
    }
}

// Check input length
function checkLength(input, errorId, min, max, fieldName) {
    if (input.value.length < min) {
        showError(input, errorId, `${fieldName} must be at least ${min} characters`);
        return false;
    } else if (max && input.value.length > max) {
        showError(input, errorId, `${fieldName} must be less than ${max} characters`);
        return false;
    } else {
        showSuccess(input, errorId);
        return true;
    }
}

// Check passwords match
function checkPasswordsMatch(password1, password2, errorId) {
    if (password1.value !== password2.value) {
        showError(password2, errorId, 'Passwords do not match');
        return false;
    } else {
        showSuccess(password2, errorId);
        return true;
    }
}

// Form submit event
form.addEventListener('submit', function(e) {
    e.preventDefault(); // Prevent form from submitting
    
    // Check all validations
    const isUsernameValid = checkRequired(username, 'usernameError', 'Username is required') && 
                            checkLength(username, 'usernameError', 3, 15, 'Username');
    
    const isEmailValid = checkRequired(email, 'emailError', 'Email is required');
    
    // If email is entered, check if it's valid
    if (isEmailValid && !isValidEmail(email.value)) {
        showError(email, 'emailError', 'Please enter a valid email');
        isEmailValid = false;
    }
    
    const isPasswordValid = checkRequired(password, 'passwordError', 'Password is required') &&
                           checkLength(password, 'passwordError', 6, 25, 'Password');
    
    const isConfirmPasswordValid = checkRequired(confirmPassword, 'confirmPasswordError', 'Please confirm password') &&
                                   checkPasswordsMatch(password, confirmPassword, 'confirmPasswordError');
    
    // If all validations pass
    if (isUsernameValid && isEmailValid && isPasswordValid && isConfirmPasswordValid) {
        // Hide form and show success message
        form.style.display = 'none';
        successMessage.style.display = 'block';
        
        // You would typically send the form data to a server here
    }
});
```

Open the HTML file in your browser to see your form validator in action!

## 🚀 Challenge Project

Try combining what you've learned to create a small quiz application:

1. Create a quiz with multiple-choice questions
2. Display one question at a time with options
3. Keep track of the user's score
4. Show the final score at the end
5. Allow the user to restart the quiz

## 📚 Next Steps

Once you've completed these JavaScript practical projects, you're ready to move on to [Python Basics](/python/basics/README.md) to learn a versatile programming language used for web development, data analysis, artificial intelligence, and more! 
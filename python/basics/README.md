# 🐍 Python Basics

Python is a versatile, easy-to-learn programming language used in web development, data analysis, artificial intelligence, scientific computing, and more. Its simple syntax and readability make it perfect for beginners!

## 📋 What You'll Learn
- What Python is and why it's useful
- Variables and data types
- Operators and expressions
- Conditional statements (if/elif/else)
- Loops
- Functions
- Working with lists, tuples, and dictionaries
- Basic file handling

## 🚀 Let's Start!

### What is Python?

Python is a high-level, interpreted programming language created by Guido van Rossum in 1991. It's known for:
- Easy-to-read syntax
- Versatility (web, data science, AI, automation)
- Large standard library
- Strong community support
- Cross-platform compatibility

### Setting Up Python

Before we begin coding, you need to have Python installed:

1. Download Python from [python.org](https://www.python.org/downloads/)
2. Install it, checking the "Add Python to PATH" option on Windows
3. Verify installation by opening a command prompt/terminal and typing:
   ```
   python --version
   ```
   or on some systems:
   ```
   python3 --version
   ```

### Your First Python Program

Let's write the classic "Hello, World!" program:

```python
print("Hello, World!")
```

Save this in a file named `hello.py` and run it from your command prompt/terminal:
```
python hello.py
```

### Variables and Data Types

Variables store data that can be used and manipulated in a program:

```python
# Integer (whole number)
age = 18

# Float (decimal number)
price = 19.99

# String (text)
name = "John"
also_a_string = 'Alice'  # Single quotes work too

# Boolean (True/False)
is_student = True
is_working = False

# None (represents absence of a value)
address = None
```

Python is dynamically typed, meaning you don't need to declare variable types explicitly. The type is inferred from the value.

### Basic Operations

#### Arithmetic Operators

```python
x = 10
y = 3

addition = x + y        # 13
subtraction = x - y     # 7
multiplication = x * y  # 30
division = x / y        # 3.3333... (returns a float)
floor_division = x // y # 3 (returns an integer, rounds down)
modulus = x % y         # 1 (remainder of division)
exponent = x ** y       # 1000 (x to the power of y)
```

#### String Operations

```python
first_name = "John"
last_name = "Doe"

# Concatenation
full_name = first_name + " " + last_name  # "John Doe"

# Repetition
repeated = "Ha" * 3  # "HaHaHa"

# Length
name_length = len(full_name)  # 8

# Accessing characters (zero-indexed)
first_char = full_name[0]  # "J"
last_char = full_name[-1]  # "e"

# Slicing
slice1 = full_name[0:4]    # "John"
slice2 = full_name[5:]     # "Doe"

# String methods
uppercase = full_name.upper()       # "JOHN DOE"
lowercase = full_name.lower()       # "john doe"
replaced = full_name.replace("Doe", "Smith")  # "John Smith"
```

#### Comparison Operators

```python
x = 10
y = 5

equal = x == y          # False
not_equal = x != y      # True
greater_than = x > y    # True
less_than = x < y       # False
greater_equal = x >= y  # True
less_equal = x <= y     # False
```

#### Logical Operators

```python
a = True
b = False

and_result = a and b    # False (both must be True)
or_result = a or b      # True (at least one must be True)
not_result = not a      # False (inverts the boolean)
```

### Input and Output

Getting input from users:

```python
name = input("Enter your name: ")
print("Hello, " + name + "!")

# Converting input to numbers
age = int(input("Enter your age: "))
height = float(input("Enter your height in meters: "))
```

Formatted output:

```python
name = "Alice"
age = 25

# Using f-strings (Python 3.6+)
print(f"Name: {name}, Age: {age}")

# Using format() method
print("Name: {}, Age: {}".format(name, age))

# Using % operator (older style)
print("Name: %s, Age: %d" % (name, age))
```

### Conditional Statements

Making decisions in code:

```python
age = 18

# Simple if statement
if age >= 18:
    print("You are an adult")
    
# if-else statement
if age >= 18:
    print("You are an adult")
else:
    print("You are a minor")
    
# if-elif-else statement
if age < 13:
    print("Child")
elif age < 18:
    print("Teenager")
elif age < 65:
    print("Adult")
else:
    print("Senior")
    
# Nested if statements
if age >= 18:
    if age < 21:
        print("Adult but cannot drink in the US")
    else:
        print("Full adult")
```

### Loops

Repeating code:

#### For Loops

```python
# Loop through a range
for i in range(5):  # 0 to 4
    print(i)

# Specifying start and end
for i in range(2, 5):  # 2 to 4
    print(i)
    
# With step value
for i in range(0, 10, 2):  # 0, 2, 4, 6, 8
    print(i)
    
# Loop through a list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
    
# Loop through a string
for char in "Hello":
    print(char)
    
# Loop with index
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")
```

#### While Loops

```python
# Basic while loop
count = 0
while count < 5:
    print(count)
    count += 1  # Same as: count = count + 1
    
# Break statement
count = 0
while True:
    print(count)
    count += 1
    if count >= 5:
        break  # Exit the loop
        
# Continue statement
for i in range(10):
    if i % 2 == 0:
        continue  # Skip even numbers
    print(i)  # Only prints odd numbers
```

### Lists

Lists store ordered collections of items:

```python
# Creating a list
fruits = ["apple", "banana", "cherry"]
mixed = [1, "hello", True, 3.14]

# Accessing elements (zero-indexed)
first_fruit = fruits[0]  # "apple"
last_fruit = fruits[-1]  # "cherry"

# Slicing
first_two = fruits[0:2]  # ["apple", "banana"]

# Changing elements
fruits[1] = "orange"  # Now fruits is ["apple", "orange", "cherry"]

# List length
num_fruits = len(fruits)  # 3

# Adding elements
fruits.append("mango")  # Add to the end
fruits.insert(1, "blueberry")  # Insert at specific position

# Removing elements
fruits.remove("cherry")  # Remove by value
popped = fruits.pop()  # Remove and return the last item
del fruits[0]  # Remove by index

# Checking if an item exists
has_apple = "apple" in fruits  # True or False

# Sorting
fruits.sort()  # Sort in place
sorted_fruits = sorted(fruits)  # Return a new sorted list
fruits.reverse()  # Reverse in place

# List comprehensions (create lists with a compact syntax)
squares = [x**2 for x in range(1, 6)]  # [1, 4, 9, 16, 25]
even = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]
```

### Tuples

Tuples are like lists but immutable (cannot be changed after creation):

```python
# Creating a tuple
coordinates = (10, 20)
person = ("John", 25, "New York")

# Accessing elements
x = coordinates[0]  # 10
y = coordinates[1]  # 20

# Unpacking a tuple
name, age, city = person

# Single item tuple (note the comma)
single_item = (42,)

# Cannot modify tuples
# coordinates[0] = 15  # This would cause an error

# Tuple methods
count = coordinates.count(10)  # Count occurrences
index = coordinates.index(20)  # Find position of a value
```

### Dictionaries

Dictionaries store key-value pairs:

```python
# Creating a dictionary
person = {
    "name": "John",
    "age": 30,
    "city": "New York"
}

# Accessing values
name = person["name"]  # "John"
# OR
name = person.get("name")  # "John" (safer, won't error if key doesn't exist)

# Changing values
person["age"] = 31

# Adding new key-value pairs
person["email"] = "john@example.com"

# Removing items
del person["city"]
email = person.pop("email")  # Remove and return the value

# Check if a key exists
has_age = "age" in person  # True

# Dictionary methods
keys = person.keys()  # Get all keys
values = person.values()  # Get all values
items = person.items()  # Get all key-value pairs as tuples

# Looping through a dictionary
for key in person:
    print(key, person[key])
    
# OR
for key, value in person.items():
    print(key, value)
```

### Functions

Functions are reusable blocks of code:

```python
# Defining a function
def greet(name):
    """This function greets the person passed in as a parameter."""
    return "Hello, " + name + "!"

# Calling a function
greeting = greet("Alice")  # "Hello, Alice!"

# Default parameters
def greet_with_default(name="Guest"):
    return "Hello, " + name + "!"

greeting1 = greet_with_default()  # "Hello, Guest!"
greeting2 = greet_with_default("Bob")  # "Hello, Bob!"

# Multiple parameters
def add(a, b):
    return a + b

sum_result = add(5, 3)  # 8

# Keyword arguments
def describe_person(name, age, city):
    return f"{name} is {age} years old and lives in {city}."

description = describe_person(age=30, city="Paris", name="Alice")

# Variable number of arguments
def sum_all(*numbers):
    """Sum any number of arguments."""
    return sum(numbers)

total = sum_all(1, 2, 3, 4, 5)  # 15

# Variable number of keyword arguments
def print_info(**kwargs):
    """Print all keyword arguments."""
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=30, city="Paris")
```

### File Handling

Reading and writing files:

```python
# Writing to a file
with open("sample.txt", "w") as file:
    file.write("Hello, World!\n")
    file.write("This is a sample file.")

# Reading an entire file
with open("sample.txt", "r") as file:
    contents = file.read()
    print(contents)

# Reading line by line
with open("sample.txt", "r") as file:
    for line in file:
        print(line.strip())  # strip() removes leading/trailing whitespace

# Appending to a file
with open("sample.txt", "a") as file:
    file.write("\nAppending more text.")
```

The `with` statement automatically closes the file when the block is exited, even if an error occurs.

### Error Handling

Dealing with errors gracefully:

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number
    print("Result:", result)
except ValueError:
    print("Please enter a valid number!")
except ZeroDivisionError:
    print("You cannot divide by zero!")
except:
    print("Something went wrong!")
finally:
    print("This code always runs, regardless of errors.")
```

## 🎯 Practice Exercises

1. **Simple Calculator**: Write a program that asks for two numbers and performs basic arithmetic operations (+, -, *, /).

2. **Temperature Converter**: Create a program that converts temperatures between Celsius and Fahrenheit.

3. **Number Guessing Game**: Write a program that generates a random number and lets the user guess it, providing hints if the guess is too high or too low.

4. **To-Do List**: Create a simple to-do list that allows the user to add, view, and remove tasks.

5. **Word Counter**: Write a program that reads a text file and counts the occurrences of each word.

## 📚 Next Steps

Once you're comfortable with these Python basics, move on to [Python Practicals](/python/practicals/README.md) to build some real-world applications!

Remember, the best way to learn programming is by practicing. Try to solve the exercises on your own, and don't worry about making mistakes—they're a normal part of the learning process! 
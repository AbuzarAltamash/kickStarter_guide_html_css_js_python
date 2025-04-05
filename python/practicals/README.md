# 🐍 Python Practicals

Now that you've learned the basics of Python, let's build some fun and practical projects to strengthen your skills!

## 🎯 What You'll Build

In this section, you'll create:
1. A command-line calculator
2. A simple text-based game
3. A to-do list application
4. A data analysis tool
5. A simple web scraper

## Project 1: Interactive Calculator 🧮

### What You'll Create
A command-line calculator that can perform multiple operations and remembers previous results.

### Step-by-Step Guide

1. Create a new file named `calculator.py`:

```python
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        return "Error! Division by zero."
    return x / y

def power(x, y):
    return x ** y

def main():
    memory = None  # To store the previous result
    
    print("Welcome to Calculator Pro!")
    print("==========================")
    
    while True:
        print("\nOperations:")
        print("1. Add")
        print("2. Subtract")
        print("3. Multiply")
        print("4. Divide")
        print("5. Power")
        print("6. Clear memory")
        print("7. Exit")
        
        # If we have a previous result, display it
        if memory is not None:
            print(f"\nCurrent memory: {memory}")
        
        # Get user choice
        choice = input("\nEnter choice (1-7): ")
        
        # Exit condition
        if choice == '7':
            print("Thank you for using Calculator Pro!")
            break
        
        # Clear memory
        if choice == '6':
            memory = None
            print("Memory cleared!")
            continue
        
        # Get input values
        if memory is not None:
            use_memory = input(f"Use memory value ({memory})? (y/n): ").lower()
            if use_memory == 'y':
                num1 = memory
            else:
                num1 = float(input("Enter first number: "))
        else:
            num1 = float(input("Enter first number: "))
            
        num2 = float(input("Enter second number: "))
        
        # Perform the calculation
        if choice == '1':
            result = add(num1, num2)
            print(f"{num1} + {num2} = {result}")
        elif choice == '2':
            result = subtract(num1, num2)
            print(f"{num1} - {num2} = {result}")
        elif choice == '3':
            result = multiply(num1, num2)
            print(f"{num1} * {num2} = {result}")
        elif choice == '4':
            result = divide(num1, num2)
            print(f"{num1} / {num2} = {result}")
        elif choice == '5':
            result = power(num1, num2)
            print(f"{num1} ^ {num2} = {result}")
        else:
            print("Invalid input! Please try again.")
            continue
        
        # Store the result in memory
        memory = result

if __name__ == "__main__":
    try:
        main()
    except ValueError:
        print("Error! Invalid number.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")
```

To run the program:
```
python calculator.py
```

## Project 2: Number Guessing Game 🎮

### What You'll Create
A game where the computer thinks of a number and the player tries to guess it with hints.

### Step-by-Step Guide

1. Create a new file named `guessing_game.py`:

```python
import random
import time

def main():
    print("Welcome to the Number Guessing Game!")
    print("===================================")
    print("I'm thinking of a number between 1 and 100.")
    print("Can you guess it?")
    
    # Set difficulty and determine the number of guesses
    print("\nChoose difficulty level:")
    print("1. Easy (10 guesses)")
    print("2. Medium (7 guesses)")
    print("3. Hard (5 guesses)")
    
    difficulty_choice = input("Enter your choice (1-3): ")
    
    if difficulty_choice == '1':
        max_guesses = 10
    elif difficulty_choice == '2':
        max_guesses = 7
    elif difficulty_choice == '3':
        max_guesses = 5
    else:
        print("Invalid choice. Defaulting to medium difficulty.")
        max_guesses = 7
    
    # The computer picks a random number
    secret_number = random.randint(1, 100)
    
    # For dramatic effect
    print("\nThinking of a number", end="")
    for _ in range(3):
        time.sleep(0.5)
        print(".", end="", flush=True)
    print("\nOkay, got it!")
    
    # Track number of guesses and previous guesses
    guess_count = 0
    previous_guesses = []
    
    # Game loop
    while guess_count < max_guesses:
        remaining = max_guesses - guess_count
        print(f"\nYou have {remaining} {'guess' if remaining == 1 else 'guesses'} left.")
        
        # Show previous guesses if any
        if previous_guesses:
            print(f"Previous guesses: {', '.join(map(str, previous_guesses))}")
        
        # Get the player's guess
        try:
            guess = int(input("Enter your guess (1-100): "))
            
            # Validate the guess
            if guess < 1 or guess > 100:
                print("Please enter a number between 1 and 100.")
                continue
            
            # Check if the guess is a repeat
            if guess in previous_guesses:
                print("You already guessed that number. Try again.")
                continue
            
            # Add to guesses list and increment counter
            previous_guesses.append(guess)
            guess_count += 1
            
            # Check the guess
            if guess < secret_number:
                print("Too low!")
            elif guess > secret_number:
                print("Too high!")
            else:
                print(f"\n🎉 Congratulations! You guessed the number ({secret_number}) in {guess_count} guesses!")
                break
                
        except ValueError:
            print("Please enter a valid number.")
    
    # If they run out of guesses
    if guess_count >= max_guesses and guess != secret_number:
        print(f"\nGame over! You've used all your guesses. The number was {secret_number}.")
    
    # Ask if they want to play again
    play_again = input("\nWould you like to play again? (y/n): ").lower()
    if play_again == 'y':
        main()
    else:
        print("Thanks for playing! Goodbye.")

if __name__ == "__main__":
    try:
        main()
    except KeyboardInterrupt:
        print("\nGame interrupted. Goodbye!")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")
```

To run the game:
```
python guessing_game.py
```

## Project 3: To-Do List Manager 📝

### What You'll Create
A command-line application to manage a to-do list, with options to add, view, mark as completed, and delete tasks.

### Step-by-Step Guide

1. Create a new file named `todo_list.py`:

```python
import json
import os
from datetime import datetime

# File to store tasks
TASKS_FILE = "tasks.json"

def load_tasks():
    # Load tasks from file or create a new list if file doesn't exist
    if os.path.exists(TASKS_FILE):
        with open(TASKS_FILE, 'r') as file:
            try:
                return json.load(file)
            except json.JSONDecodeError:
                return []
    return []

def save_tasks(tasks):
    # Save tasks to file
    with open(TASKS_FILE, 'w') as file:
        json.dump(tasks, file, indent=4)

def show_tasks(tasks):
    # Display all tasks with their status
    if not tasks:
        print("Your to-do list is empty.")
        return
    
    print("\nYour To-Do List:")
    print("----------------")
    
    for index, task in enumerate(tasks, 1):
        status = "✓" if task["completed"] else " "
        date = task["date"]
        print(f"{index}. [{status}] {task['title']} (Added: {date})")
    
    print()

def add_task(tasks, title):
    # Add a new task to the list
    current_date = datetime.now().strftime("%Y-%m-%d")
    new_task = {
        "title": title,
        "completed": False,
        "date": current_date
    }
    tasks.append(new_task)
    save_tasks(tasks)
    print(f"Task '{title}' added successfully!")

def mark_completed(tasks, task_index):
    # Mark a task as completed or toggle its status
    if 1 <= task_index <= len(tasks):
        tasks[task_index-1]["completed"] = not tasks[task_index-1]["completed"]
        status = "completed" if tasks[task_index-1]["completed"] else "incomplete"
        print(f"Task '{tasks[task_index-1]['title']}' marked as {status}.")
        save_tasks(tasks)
    else:
        print("Invalid task number.")

def delete_task(tasks, task_index):
    # Delete a task from the list
    if 1 <= task_index <= len(tasks):
        deleted_task = tasks.pop(task_index-1)
        print(f"Task '{deleted_task['title']}' deleted.")
        save_tasks(tasks)
    else:
        print("Invalid task number.")

def main():
    print("Welcome to the To-Do List Manager!")
    print("=================================")
    
    tasks = load_tasks()
    
    while True:
        print("\nOptions:")
        print("1. Show tasks")
        print("2. Add a task")
        print("3. Mark task as completed/incomplete")
        print("4. Delete a task")
        print("5. Exit")
        
        choice = input("\nEnter your choice (1-5): ")
        
        if choice == '1':
            show_tasks(tasks)
        
        elif choice == '2':
            title = input("Enter task title: ")
            if title.strip():
                add_task(tasks, title)
            else:
                print("Task title cannot be empty.")
        
        elif choice == '3':
            show_tasks(tasks)
            if tasks:
                try:
                    task_index = int(input("Enter the task number to toggle completion: "))
                    mark_completed(tasks, task_index)
                except ValueError:
                    print("Please enter a valid number.")
        
        elif choice == '4':
            show_tasks(tasks)
            if tasks:
                try:
                    task_index = int(input("Enter the task number to delete: "))
                    delete_task(tasks, task_index)
                except ValueError:
                    print("Please enter a valid number.")
        
        elif choice == '5':
            print("Thank you for using the To-Do List Manager. Goodbye!")
            break
        
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    try:
        main()
    except KeyboardInterrupt:
        print("\nProgram interrupted. Goodbye!")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")
```

To run the to-do list manager:
```
python todo_list.py
```

## Project 4: Simple Data Analyzer 📊

### What You'll Create
A program that analyzes CSV data and provides statistical information.

### Step-by-Step Guide

1. First, create a sample data file named `sample_data.csv` with the following content:

```csv
Name,Age,Score
Alice,22,85
Bob,25,92
Charlie,20,78
David,23,95
Emma,24,88
Frank,21,73
Grace,22,91
Hannah,24,82
Ian,23,79
Julia,25,94
```

2. Create a new file named `data_analyzer.py`:

```python
import csv
import statistics
import matplotlib.pyplot as plt

def load_data(filename):
    # Load data from a CSV file
    data = []
    
    try:
        with open(filename, 'r') as file:
            csv_reader = csv.DictReader(file)
            for row in csv_reader:
                # Convert numeric strings to numbers
                for key, value in row.items():
                    try:
                        row[key] = int(value)
                    except ValueError:
                        try:
                            row[key] = float(value)
                        except ValueError:
                            pass  # Keep as string if not a number
                data.append(row)
        return data
    except FileNotFoundError:
        print(f"Error: File '{filename}' not found.")
        return None

def display_summary(data, numeric_column):
    # Display summary statistics for a numeric column
    if not data:
        return
    
    # Extract values from the column
    try:
        values = [row[numeric_column] for row in data]
        
        # Calculate statistics
        minimum = min(values)
        maximum = max(values)
        mean_val = statistics.mean(values)
        median_val = statistics.median(values)
        
        # Try to calculate mode and std deviation (may not work for all data)
        try:
            mode_val = statistics.mode(values)
        except statistics.StatisticsError:
            mode_val = "N/A (no unique mode)"
            
        try:
            std_dev = statistics.stdev(values)
        except statistics.StatisticsError:
            std_dev = "N/A (not enough data)"
        
        # Display statistics
        print(f"\nStatistics for '{numeric_column}':")
        print(f"Count: {len(values)}")
        print(f"Minimum: {minimum}")
        print(f"Maximum: {maximum}")
        print(f"Range: {maximum - minimum}")
        print(f"Mean: {mean_val:.2f}")
        print(f"Median: {median_val}")
        print(f"Mode: {mode_val}")
        print(f"Standard Deviation: {std_dev if isinstance(std_dev, str) else std_dev:.2f}")
        
    except (KeyError, TypeError):
        print(f"Error: '{numeric_column}' is not a valid numeric column.")

def plot_data(data, x_column, y_column, plot_type):
    # Plot data using matplotlib
    if not data:
        return
    
    # Extract data for plotting
    try:
        x_values = [row[x_column] for row in data]
        y_values = [row[y_column] for row in data]
        
        # Create figure
        plt.figure(figsize=(10, 6))
        
        # Create the specified plot
        if plot_type == "bar":
            plt.bar(x_values, y_values)
        elif plot_type == "scatter":
            plt.scatter(x_values, y_values)
        elif plot_type == "line":
            plt.plot(x_values, y_values, marker='o')
        else:
            print(f"Error: Unknown plot type '{plot_type}'")
            return
        
        # Add labels and title
        plt.xlabel(x_column)
        plt.ylabel(y_column)
        plt.title(f"{plot_type.capitalize()} Plot of {y_column} vs {x_column}")
        
        # Add grid
        plt.grid(True, linestyle='--', alpha=0.7)
        
        # Adjust layout and show plot
        plt.tight_layout()
        plt.show()
        
    except (KeyError, TypeError):
        print(f"Error: Invalid columns for plotting.")

def main():
    print("Simple Data Analyzer")
    print("===================")
    
    # Get the filename
    filename = input("Enter the CSV file to analyze (default: sample_data.csv): ").strip()
    
    if not filename:
        filename = "sample_data.csv"
    
    # Load the data
    data = load_data(filename)
    
    if not data:
        return
    
    # Get column names from the first row
    columns = list(data[0].keys())
    
    while True:
        print("\nOptions:")
        print("1. Display column names")
        print("2. Display first few rows")
        print("3. Calculate statistics for a column")
        print("4. Create a plot")
        print("5. Exit")
        
        choice = input("\nEnter your choice (1-5): ")
        
        if choice == '1':
            print("\nColumn names:")
            for i, column in enumerate(columns, 1):
                print(f"{i}. {column}")
        
        elif choice == '2':
            n_rows = min(5, len(data))
            print(f"\nFirst {n_rows} rows:")
            for i, row in enumerate(data[:n_rows], 1):
                print(f"Row {i}: {row}")
        
        elif choice == '3':
            print("\nAvailable columns:")
            for i, column in enumerate(columns, 1):
                print(f"{i}. {column}")
            
            col_choice = input("\nEnter column name or number for statistics: ")
            
            # Convert to column name if a number was entered
            try:
                col_index = int(col_choice) - 1
                if 0 <= col_index < len(columns):
                    col_choice = columns[col_index]
            except ValueError:
                pass
            
            display_summary(data, col_choice)
        
        elif choice == '4':
            print("\nAvailable columns:")
            for i, column in enumerate(columns, 1):
                print(f"{i}. {column}")
            
            x_col = input("\nEnter x-axis column name or number: ")
            y_col = input("Enter y-axis column name or number: ")
            
            # Convert to column names if numbers were entered
            try:
                x_index = int(x_col) - 1
                if 0 <= x_index < len(columns):
                    x_col = columns[x_index]
            except ValueError:
                pass
                
            try:
                y_index = int(y_col) - 1
                if 0 <= y_index < len(columns):
                    y_col = columns[y_index]
            except ValueError:
                pass
            
            print("\nPlot types:")
            print("1. Bar plot")
            print("2. Scatter plot")
            print("3. Line plot")
            
            plot_choice = input("Enter plot type (1-3): ")
            
            plot_types = {
                '1': 'bar',
                '2': 'scatter',
                '3': 'line'
            }
            
            if plot_choice in plot_types:
                plot_data(data, x_col, y_col, plot_types[plot_choice])
            else:
                print("Invalid plot type. Please try again.")
        
        elif choice == '5':
            print("Thank you for using the Data Analyzer. Goodbye!")
            break
        
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    try:
        main()
    except KeyboardInterrupt:
        print("\nProgram interrupted. Goodbye!")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")
        print("Tip: Make sure you have matplotlib installed (pip install matplotlib)")
```

To run the data analyzer:
```
python data_analyzer.py
```

Note: You'll need to install matplotlib:
```
pip install matplotlib
```

## Project 5: Simple Web Scraper 🕸️

### What You'll Create
A program that extracts information from a webpage and saves it to a file.

### Step-by-Step Guide

1. Create a new file named `web_scraper.py`:

```python
import requests
from bs4 import BeautifulSoup
import csv
import json
import os
import time

def fetch_webpage(url):
    # Fetch the content of a webpage
    try:
        # Add a user-agent to mimic a browser
        headers = {
            'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36'
        }
        
        response = requests.get(url, headers=headers, timeout=10)
        response.raise_for_status()  # Raise an exception for bad status codes
        
        return response.text
    except requests.exceptions.RequestException as e:
        print(f"Error fetching webpage: {e}")
        return None

def extract_quotes(html_content):
    # Extract quotes from a webpage
    quotes = []
    
    try:
        soup = BeautifulSoup(html_content, 'html.parser')
        
        # Find all quote elements
        quote_elements = soup.select('.quote')
        
        for quote_element in quote_elements:
            # Extract the quote text
            text_element = quote_element.select_one('.text')
            text = text_element.get_text() if text_element else "No text found"
            
            # Extract the author
            author_element = quote_element.select_one('.author')
            author = author_element.get_text() if author_element else "Unknown author"
            
            # Extract the tags
            tags_elements = quote_element.select('.tag')
            tags = [tag.get_text() for tag in tags_elements] if tags_elements else []
            
            # Create a quote dictionary
            quote = {
                'text': text,
                'author': author,
                'tags': tags
            }
            
            quotes.append(quote)
        
        return quotes
    except Exception as e:
        print(f"Error parsing HTML: {e}")
        return []

def save_to_csv(quotes, filename):
    # Save quotes to a CSV file
    try:
        with open(filename, 'w', newline='', encoding='utf-8') as file:
            fieldnames = ['text', 'author', 'tags']
            writer = csv.DictWriter(file, fieldnames=fieldnames)
            
            writer.writeheader()
            for quote in quotes:
                # Convert tags list to a string for CSV
                quote_copy = quote.copy()
                quote_copy['tags'] = ', '.join(quote_copy['tags'])
                writer.writerow(quote_copy)
        
        print(f"Quotes saved to {filename}")
        return True
    except Exception as e:
        print(f"Error saving to CSV: {e}")
        return False

def save_to_json(quotes, filename):
    # Save quotes to a JSON file
    try:
        with open(filename, 'w', encoding='utf-8') as file:
            json.dump(quotes, file, indent=4)
        
        print(f"Quotes saved to {filename}")
        return True
    except Exception as e:
        print(f"Error saving to JSON: {e}")
        return False

def main():
    print("Simple Web Scraper")
    print("=================")
    
    # Example URL that works with this scraper
    default_url = "http://quotes.toscrape.com"
    
    url = input(f"Enter the URL to scrape (default: {default_url}): ").strip()
    if not url:
        url = default_url
    
    print(f"\nFetching content from {url}...")
    html_content = fetch_webpage(url)
    
    if not html_content:
        print("Failed to fetch webpage content. Exiting.")
        return
    
    print("Extracting quotes...")
    quotes = extract_quotes(html_content)
    
    if not quotes:
        print("No quotes found or error in extraction. Exiting.")
        return
    
    print(f"Found {len(quotes)} quotes.")
    
    # Display a few quotes as a preview
    print("\nPreview of extracted quotes:")
    for i, quote in enumerate(quotes[:3], 1):
        print(f"\nQuote {i}:")
        print(f"Text: {quote['text']}")
        print(f"Author: {quote['author']}")
        print(f"Tags: {', '.join(quote['tags'])}")
    
    if len(quotes) > 3:
        print("\n... (more quotes available)")
    
    # Ask for output format
    print("\nOutput options:")
    print("1. Save as CSV")
    print("2. Save as JSON")
    print("3. Save as both")
    print("4. Exit without saving")
    
    choice = input("\nEnter your choice (1-4): ")
    
    if choice in ('1', '3'):
        csv_filename = input("\nEnter CSV filename (default: quotes.csv): ").strip()
        if not csv_filename:
            csv_filename = "quotes.csv"
        if not csv_filename.lower().endswith('.csv'):
            csv_filename += '.csv'
        save_to_csv(quotes, csv_filename)
    
    if choice in ('2', '3'):
        json_filename = input("\nEnter JSON filename (default: quotes.json): ").strip()
        if not json_filename:
            json_filename = "quotes.json"
        if not json_filename.lower().endswith('.json'):
            json_filename += '.json'
        save_to_json(quotes, json_filename)
    
    if choice == '4':
        print("Exiting without saving.")
    
    print("\nThank you for using the Web Scraper. Goodbye!")

if __name__ == "__main__":
    try:
        main()
    except KeyboardInterrupt:
        print("\nProgram interrupted. Goodbye!")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")
        print("Tip: Make sure you have requests and beautifulsoup4 installed:")
        print("pip install requests beautifulsoup4")
```

To run the web scraper:
```
python web_scraper.py
```

Note: You'll need to install the required packages:
```
pip install requests beautifulsoup4
```

## 🚀 Challenge Project

Try combining what you've learned to create a weather application:

1. Use the requests library to fetch weather data from a free API like OpenWeatherMap
2. Parse the JSON response to extract weather information
3. Create a user-friendly interface to display current weather and forecasts
4. Add options to search for different cities and save favorite locations

## 📚 Next Steps

Congratulations on completing the Python practical projects! You've now built a solid foundation in Python programming with real-world applications. Here are some suggestions for continuing your Python journey:

1. **Learn a Python Framework**
   - Web Development: Django or Flask
   - Data Science: Pandas, NumPy, and Matplotlib
   - Machine Learning: Scikit-learn, TensorFlow, or PyTorch

2. **Explore Advanced Python Topics**
   - Object-Oriented Programming
   - Decorators and Generators
   - Multithreading and Multiprocessing
   - Regular Expressions

3. **Contribute to Open Source**
   - Find beginner-friendly Python projects on GitHub
   - Fix bugs or add features
   - Learn from experienced developers

4. **Build Your Own Projects**
   - Think of a problem you'd like to solve
   - Plan the solution
   - Implement it step by step

Remember, programming is a skill that improves with practice. Keep coding, keep learning, and have fun! 
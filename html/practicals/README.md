# 🛠️ HTML Practicals

Now that you've learned the basics of HTML, let's put your knowledge to work with some fun practical projects!

## 🎯 What You'll Build

In this section, you'll create:
1. A personal profile page
2. A recipe page
3. A mini blog layout
4. A simple form

## Project 1: Personal Profile Page 👤

### What You'll Create
A webpage about yourself that includes your photo, information, and interests.

### Step-by-Step Guide

1. Create a new file called `profile.html`
2. Set up the HTML structure:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Profile</title>
</head>
<body>
    <!-- Your content will go here -->
</body>
</html>
```

3. Add a heading with your name:

```html
<h1>Your Name</h1>
```

4. Add a profile image (you can use a placeholder image if you want):

```html
<img src="https://via.placeholder.com/150" alt="Your Name">
```

5. Add a section about yourself:

```html
<h2>About Me</h2>
<p>
    Write a few sentences about yourself here. What do you like to do?
    What are you interested in learning?
</p>
```

6. Add your interests as a list:

```html
<h2>My Interests</h2>
<ul>
    <li>Interest 1</li>
    <li>Interest 2</li>
    <li>Interest 3</li>
</ul>
```

7. Add a section for your favorite websites with links:

```html
<h2>My Favorite Websites</h2>
<ul>
    <li><a href="https://example.com">Example Website</a></li>
    <li><a href="https://another-example.com">Another Website</a></li>
</ul>
```

Open this file in your browser to see your profile page!

## Project 2: Recipe Page 🍕

### What You'll Create
A webpage that displays a recipe with ingredients and instructions.

### Step-by-Step Guide

1. Create a new file called `recipe.html`
2. Set up the HTML structure with a title for your recipe:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Favorite Recipe</title>
</head>
<body>
    <h1>My Favorite Recipe: [Recipe Name]</h1>
</body>
</html>
```

3. Add an image of the dish:

```html
<img src="https://via.placeholder.com/300x200" alt="Recipe Name">
```

4. Add a description:

```html
<h2>Description</h2>
<p>
    Write a brief description of the dish. What does it taste like?
    Where is it from? Why do you like it?
</p>
```

5. Add an ingredients list:

```html
<h2>Ingredients</h2>
<ul>
    <li>Ingredient 1</li>
    <li>Ingredient 2</li>
    <li>Ingredient 3</li>
    <!-- Add more ingredients as needed -->
</ul>
```

6. Add step-by-step instructions:

```html
<h2>Instructions</h2>
<ol>
    <li>First step of the recipe...</li>
    <li>Second step of the recipe...</li>
    <li>Third step of the recipe...</li>
    <!-- Add more steps as needed -->
</ol>
```

7. Add a table for nutritional information:

```html
<h2>Nutritional Information</h2>
<table border="1">
    <tr>
        <th>Nutrient</th>
        <th>Amount</th>
    </tr>
    <tr>
        <td>Calories</td>
        <td>XXX</td>
    </tr>
    <tr>
        <td>Protein</td>
        <td>XX g</td>
    </tr>
    <tr>
        <td>Carbohydrates</td>
        <td>XX g</td>
    </tr>
</table>
```

## Project 3: Mini Blog Layout 📝

### What You'll Create
A simple blog homepage with multiple articles.

### Step-by-Step Guide

1. Create a new file called `blog.html`
2. Set up the HTML structure:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Blog</title>
</head>
<body>
    <header>
        <h1>My Awesome Blog</h1>
        <p>Welcome to my thoughts and ideas!</p>
    </header>
    
    <nav>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>
    
    <main>
        <!-- Blog posts will go here -->
    </main>
    
    <footer>
        <p>&copy; 2023 My Blog. All rights reserved.</p>
    </footer>
</body>
</html>
```

3. Add a few blog posts in the `<main>` section:

```html
<article>
    <h2>My First Blog Post</h2>
    <p><small>Posted on: January 1, 2023</small></p>
    <p>
        This is the content of my first blog post. Write a few sentences here
        about anything you're interested in!
    </p>
    <a href="#">Read more</a>
</article>

<article>
    <h2>My Second Blog Post</h2>
    <p><small>Posted on: January 5, 2023</small></p>
    <p>
        This is the content of my second blog post. Write about something
        else that interests you!
    </p>
    <a href="#">Read more</a>
</article>
```

## Project 4: Simple Contact Form 📨

### What You'll Create
A webpage with a form that collects user information.

### Step-by-Step Guide

1. Create a new file called `contact.html`
2. Set up the HTML structure:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Contact Me</title>
</head>
<body>
    <h1>Contact Me</h1>
    <p>Fill out this form to get in touch!</p>
    
    <form>
        <!-- Form elements will go here -->
    </form>
</body>
</html>
```

3. Add form elements:

```html
<form>
    <div>
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required>
    </div>
    
    <div>
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>
    </div>
    
    <div>
        <label for="subject">Subject:</label>
        <select id="subject" name="subject">
            <option value="general">General Inquiry</option>
            <option value="support">Support</option>
            <option value="feedback">Feedback</option>
        </select>
    </div>
    
    <div>
        <label for="message">Message:</label>
        <textarea id="message" name="message" rows="5" required></textarea>
    </div>
    
    <div>
        <label>
            <input type="checkbox" name="subscribe" value="yes">
            Subscribe to newsletter
        </label>
    </div>
    
    <button type="submit">Send Message</button>
</form>
```

## 🚀 Challenge Project

Now that you've completed the guided projects, try combining all these elements to create a personal website with:

- A homepage (with your profile)
- A blog page (with a few sample posts)
- A recipes page (with your favorite recipes)
- A contact page (with a form)

Link all the pages together with a navigation menu!

## 📚 Next Steps

Once you've completed these HTML practical projects, you're ready to move on to [CSS Basics](/css/basics/README.md) to learn how to make your webpages look beautiful! 
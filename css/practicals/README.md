# 🎨 CSS Practicals

Now that you've learned the basics of CSS, let's put your knowledge to work with some fun and practical styling projects!

## 🎯 What You'll Build

In this section, you'll:
1. Style your personal profile page
2. Create a beautiful recipe card
3. Design a blog layout
4. Style a contact form

## Project 1: Style Your Personal Profile 👤

Let's style the personal profile page you created in the HTML practicals section.

### Step-by-Step Guide

1. Create a new file called `profile.css`
2. Link it to your profile HTML:

```html
<!-- Add this in the <head> section of your profile.html -->
<link rel="stylesheet" href="profile.css">
```

3. Style the body and container:

```css
body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    color: #333;
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
}

.container {
    width: 80%;
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    background-color: white;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    border-radius: 5px;
}
```

4. Style your headings:

```css
h1 {
    color: #2c3e50;
    text-align: center;
    border-bottom: 2px solid #3498db;
    padding-bottom: 10px;
}

h2 {
    color: #3498db;
    border-left: 3px solid #3498db;
    padding-left: 10px;
}
```

5. Style your profile image:

```css
img {
    display: block;
    margin: 0 auto;
    max-width: 150px;
    border-radius: 50%;
    border: 3px solid #3498db;
}
```

6. Style your lists:

```css
ul {
    list-style-type: square;
    padding-left: 20px;
}

li {
    margin-bottom: 5px;
}
```

7. Style your links:

```css
a {
    color: #3498db;
    text-decoration: none;
}

a:hover {
    text-decoration: underline;
    color: #2980b9;
}
```

8. Add these classes to your HTML elements:

```html
<div class="container">
    <!-- Your content here -->
</div>
```

## Project 2: Beautiful Recipe Card 🍕

Let's transform your recipe page into an attractive recipe card.

### Step-by-Step Guide

1. Create a new file called `recipe.css`
2. Link it to your recipe HTML
3. Style the recipe card:

```css
body {
    font-family: 'Georgia', serif;
    line-height: 1.6;
    background-color: #f9f5f0;
    margin: 0;
    padding: 20px;
}

.recipe-card {
    max-width: 800px;
    margin: 0 auto;
    background-color: white;
    border-radius: 10px;
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
    overflow: hidden;
}

.recipe-header {
    text-align: center;
    padding: 20px;
    background-color: #f8e9d6;
}

h1 {
    color: #d35400;
    margin-top: 0;
}

.recipe-image {
    width: 100%;
    height: 300px;
    object-fit: cover;
}

.recipe-content {
    padding: 20px;
}

h2 {
    color: #d35400;
    border-bottom: 2px dashed #f8e9d6;
    padding-bottom: 5px;
}
```

4. Style the ingredients and instructions:

```css
.ingredients-list {
    background-color: #f8f9fa;
    padding: 15px;
    border-radius: 5px;
}

.ingredients-list li {
    margin-bottom: 8px;
}

.instructions {
    padding: 0 15px;
}

.instructions li {
    margin-bottom: 15px;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin: 20px 0;
}

th, td {
    padding: 10px;
    border: 1px solid #ddd;
    text-align: left;
}

th {
    background-color: #f8e9d6;
    color: #d35400;
}
```

5. Add these classes to your HTML elements:

```html
<div class="recipe-card">
    <div class="recipe-header">
        <h1>My Favorite Recipe: [Recipe Name]</h1>
    </div>
    
    <img class="recipe-image" src="your-image.jpg" alt="Recipe Name">
    
    <div class="recipe-content">
        <h2>Description</h2>
        <p>Your description here...</p>
        
        <h2>Ingredients</h2>
        <ul class="ingredients-list">
            <!-- Your ingredients -->
        </ul>
        
        <h2>Instructions</h2>
        <ol class="instructions">
            <!-- Your instructions -->
        </ol>
        
        <!-- Your table -->
    </div>
</div>
```

## Project 3: Blog Layout Styling 📝

Let's create a responsive blog layout with CSS.

### Step-by-Step Guide

1. Create a new file called `blog.css`
2. Link it to your blog HTML
3. Style the overall layout:

```css
body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    color: #333;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
    overflow: hidden;
}

header {
    background-color: #35424a;
    color: white;
    padding: 20px 0;
    text-align: center;
}

header h1 {
    margin: 0;
}

nav {
    background-color: #2c3e50;
    padding: 10px 0;
}

nav ul {
    list-style: none;
    padding: 0;
    margin: 0;
    text-align: center;
}

nav li {
    display: inline-block;
    margin: 0 10px;
}

nav a {
    color: white;
    text-decoration: none;
    padding: 5px 10px;
}

nav a:hover {
    background-color: #3498db;
    border-radius: 3px;
}
```

4. Style the blog content:

```css
main {
    padding: 20px 0;
}

article {
    background-color: white;
    margin-bottom: 20px;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

article h2 {
    color: #2c3e50;
    margin-top: 0;
    border-bottom: 1px solid #eee;
    padding-bottom: 10px;
}

article small {
    color: #777;
    display: block;
    margin-bottom: 10px;
}

article a {
    display: inline-block;
    margin-top: 10px;
    color: #3498db;
    text-decoration: none;
}

article a:hover {
    text-decoration: underline;
}

footer {
    text-align: center;
    padding: 20px;
    background-color: #35424a;
    color: white;
    margin-top: 20px;
}
```

5. Add responsiveness:

```css
@media (min-width: 768px) {
    main {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }
    
    article {
        width: 48%;
    }
}

@media (max-width: 767px) {
    nav li {
        display: block;
        margin: 5px 0;
    }
}
```

6. Add these classes to your HTML:

```html
<div class="container">
    <header>
        <!-- Header content -->
    </header>
    
    <nav>
        <!-- Nav content -->
    </nav>
    
    <main>
        <!-- Articles -->
    </main>
    
    <footer>
        <!-- Footer content -->
    </footer>
</div>
```

## Project 4: Contact Form Styling 📨

Let's make your contact form look professional and user-friendly.

### Step-by-Step Guide

1. Create a new file called `contact.css`
2. Link it to your contact HTML
3. Style the form container:

```css
body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    color: #333;
    background-color: #f4f4f4;
    margin: 0;
    padding: 20px;
}

.contact-container {
    max-width: 600px;
    margin: 0 auto;
    background-color: white;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    padding: 20px;
}

h1 {
    text-align: center;
    color: #2c3e50;
    margin-top: 0;
}
```

4. Style the form elements:

```css
.form-group {
    margin-bottom: 15px;
}

label {
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
}

input, select, textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-size: 16px;
}

textarea {
    resize: vertical;
    min-height: 100px;
}

input:focus, select:focus, textarea:focus {
    outline: none;
    border-color: #3498db;
    box-shadow: 0 0 5px rgba(52, 152, 219, 0.5);
}

.checkbox-group {
    margin: 20px 0;
}

.checkbox-group label {
    font-weight: normal;
    display: flex;
    align-items: center;
}

.checkbox-group input {
    width: auto;
    margin-right: 10px;
}

button {
    background-color: #3498db;
    color: white;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    border-radius: 4px;
    cursor: pointer;
    display: block;
    width: 100%;
}

button:hover {
    background-color: #2980b9;
}
```

5. Add these classes to your HTML:

```html
<div class="contact-container">
    <h1>Contact Me</h1>
    <p>Fill out this form to get in touch!</p>
    
    <form>
        <div class="form-group">
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required>
        </div>
        
        <div class="form-group">
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
        </div>
        
        <div class="form-group">
            <label for="subject">Subject:</label>
            <select id="subject" name="subject">
                <option value="general">General Inquiry</option>
                <option value="support">Support</option>
                <option value="feedback">Feedback</option>
            </select>
        </div>
        
        <div class="form-group">
            <label for="message">Message:</label>
            <textarea id="message" name="message" rows="5" required></textarea>
        </div>
        
        <div class="checkbox-group">
            <label>
                <input type="checkbox" name="subscribe" value="yes">
                Subscribe to newsletter
            </label>
        </div>
        
        <button type="submit">Send Message</button>
    </form>
</div>
```

## 🚀 Challenge Project

Try combining all of your styled pages into a cohesive personal website:

1. Create a common style for your header/navigation that appears on all pages
2. Make a consistent color scheme and typography across all pages
3. Add a responsive layout that works well on both desktop and mobile
4. Use CSS animations to add subtle effects (like hover effects on buttons)

## 📚 Next Steps

Now that you've learned how to make beautiful pages with CSS, let's move on to [JavaScript Basics](/javascript/basics/README.md) to add interactivity to your websites! 
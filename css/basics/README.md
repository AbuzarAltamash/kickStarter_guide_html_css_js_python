# 🎨 CSS Basics

CSS (Cascading Style Sheets) is what makes websites look good! While HTML provides the structure, CSS adds colors, layouts, fonts, and all the visual styles.

## 📋 What You'll Learn
- What CSS is and how it works
- How to connect CSS to HTML
- Basic CSS properties and values
- Selectors and how to target HTML elements
- Colors, fonts, and layout basics

## 🚀 Let's Start!

### What is CSS?
CSS is a **style sheet language** that describes how HTML elements should be displayed on screen. It controls layout, colors, fonts, spacing, and more!

### How to Connect CSS to HTML

There are three ways to add CSS to your HTML:

#### 1. Inline CSS (directly in HTML elements)
```html
<h1 style="color: blue; font-size: 24px;">This is a blue heading</h1>
```

#### 2. Internal CSS (in the `<head>` section)
```html
<!DOCTYPE html>
<html>
<head>
    <title>My Page</title>
    <style>
        h1 {
            color: blue;
            font-size: 24px;
        }
    </style>
</head>
<body>
    <h1>This is a blue heading</h1>
</body>
</html>
```

#### 3. External CSS (in a separate .css file) - BEST PRACTICE!
Create a file named `styles.css`:
```css
h1 {
    color: blue;
    font-size: 24px;
}
```

Then link it in your HTML:
```html
<!DOCTYPE html>
<html>
<head>
    <title>My Page</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>This is a blue heading</h1>
</body>
</html>
```

### CSS Syntax

CSS consists of **selectors** and **declarations**:

```css
selector {
    property: value;
    another-property: another-value;
}
```

For example:
```css
h1 {
    color: blue;
    font-size: 24px;
}
```

- `h1` is the selector (targets all h1 elements)
- `color` and `font-size` are properties
- `blue` and `24px` are values

### Basic Selectors

#### Element Selector
Selects all elements of the specified type:
```css
p {
    color: red;
}
```

#### ID Selector
Selects a single unique element with the specified ID:
```css
#special-paragraph {
    color: green;
}
```
(Used with `<p id="special-paragraph">` in HTML)

#### Class Selector
Selects all elements with the specified class:
```css
.highlight {
    background-color: yellow;
}
```
(Used with `<p class="highlight">` in HTML)

### Common CSS Properties

#### Text Styling
```css
p {
    color: #333333;              /* Text color */
    font-family: Arial, sans-serif; /* Font */
    font-size: 16px;             /* Font size */
    font-weight: bold;           /* Bold text */
    text-align: center;          /* Alignment (left, right, center, justify) */
    text-decoration: underline;  /* Underline, overline, line-through */
    line-height: 1.5;            /* Line spacing */
}
```

#### Colors
CSS has several ways to define colors:

```css
/* Color names */
p { color: red; }

/* Hexadecimal values */
p { color: #FF0000; }  /* Same as red */

/* RGB values */
p { color: rgb(255, 0, 0); }  /* Same as red */

/* RGBA (with transparency) */
p { color: rgba(255, 0, 0, 0.5); }  /* Semi-transparent red */
```

#### Backgrounds
```css
div {
    background-color: lightblue;
    background-image: url('background.jpg');
    background-repeat: no-repeat;  /* Options: repeat, repeat-x, repeat-y, no-repeat */
    background-position: center;
}
```

#### Borders
```css
div {
    border-width: 2px;
    border-style: solid;  /* Options: none, solid, dashed, dotted, double */
    border-color: black;
    
    /* Shorthand */
    border: 2px solid black;
    
    /* Border radius (rounded corners) */
    border-radius: 10px;
}
```

#### Margin and Padding
Margin is space outside an element, padding is space inside:

```css
div {
    margin: 10px;      /* Space around the outside */
    padding: 20px;     /* Space inside */
    
    /* You can set individual sides too */
    margin-top: 5px;
    margin-right: 10px;
    margin-bottom: 15px;
    margin-left: 20px;
    
    /* Shorthand: top right bottom left (clockwise) */
    margin: 5px 10px 15px 20px;
}
```

#### Width and Height
```css
div {
    width: 300px;
    height: 200px;
    
    /* You can also use percentages */
    width: 50%;        /* 50% of parent's width */
    
    /* Min and max values */
    max-width: 500px;  /* Never wider than 500px */
    min-height: 200px; /* Never shorter than 200px */
}
```

### Basic Layout Properties

#### Display Property
```css
div {
    display: block;     /* Default for div: takes up the full width */
    /* Other options */
    display: inline;    /* Like a span: only takes needed width */
    display: inline-block; /* Inline but can set width/height */
    display: none;      /* Removes the element from view */
}
```

#### Position Property
```css
div {
    position: static;    /* Default: follows normal flow */
    /* Other options */
    position: relative;  /* Relative to normal position */
    position: absolute;  /* Relative to positioned parent */
    position: fixed;     /* Relative to viewport (stays on screen) */
    
    /* Used with top, right, bottom, left */
    top: 20px;
    left: 30px;
}
```

### Comments in CSS
You can add comments that won't affect your styles:

```css
/* This is a CSS comment */
p {
    color: blue;  /* This text will be blue */
}
```

## 🎯 Practice Exercise

1. Create an HTML file with various elements (headings, paragraphs, divs, etc.)
2. Create a separate CSS file
3. Link the CSS file to your HTML
4. Try styling:
   - Make headings a different color
   - Change the font for paragraphs
   - Add background colors to divs
   - Add margins and padding
   - Style a navigation menu using display properties
   
## 📚 Next Steps

Once you're comfortable with these CSS basics, move on to [CSS Practicals](/css/practicals/README.md) to apply these styles to real webpages! 
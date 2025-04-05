# 🌐 HTML Basics

HTML (HyperText Markup Language) is the building block of all websites. It's like the skeleton that gives structure to web pages!

## 📋 What You'll Learn
- What HTML is and how it works
- Basic HTML document structure
- Common HTML tags and elements
- How to create links and add images
- How to structure content with lists and tables

## 🚀 Let's Start!

### What is HTML?
HTML is a **markup language** that tells web browsers how to structure and display content. HTML uses **tags** to define elements on the page.

HTML tags look like this:
```html
<tagname>Content goes here</tagname>
```

### Basic HTML Document Structure

Every HTML document follows this basic structure:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Web Page</title>
</head>
<body>
    Content goes here!
</body>
</html>
```

- `<!DOCTYPE html>` tells the browser this is an HTML5 document
- `<html>` is the root element
- `<head>` contains meta-information (not visible)
- `<title>` sets the page title (shown in browser tab)
- `<body>` contains all visible content

### Common HTML Tags

#### Headings
HTML has six heading levels:

```html
<h1>Heading 1 (Largest)</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6 (Smallest)</h6>
```

#### Paragraphs
```html
<p>This is a paragraph of text.</p>
```

#### Text Formatting
```html
<b>Bold text</b>
<i>Italic text</i>
<u>Underlined text</u>
<strong>Important text</strong>
<em>Emphasized text</em>
```

#### Links
```html
<a href="https://www.example.com">Click here to visit Example</a>
```

#### Images
```html
<img src="image.jpg" alt="Description of image">
```

#### Lists

Unordered List (bullet points):
```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
```

Ordered List (numbered):
```html
<ol>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ol>
```

#### Tables
```html
<table>
    <tr>
        <th>Name</th>
        <th>Age</th>
    </tr>
    <tr>
        <td>John</td>
        <td>25</td>
    </tr>
    <tr>
        <td>Sarah</td>
        <td>22</td>
    </tr>
</table>
```

### Comments in HTML
You can add comments that won't be displayed in the browser:

```html
<!-- This is a comment and won't be displayed -->
```

## 🎯 Practice Exercise

Create a simple HTML page about yourself with:
1. A heading with your name
2. A paragraph about yourself
3. A list of your hobbies
4. An image (if you have one)
5. A link to your favorite website

## 📚 Next Steps

Once you're comfortable with these basics, move on to [HTML Practicals](/html/practicals/README.md) to build some real webpages! 
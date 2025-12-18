# HTML Basics - Complete Guide
## From Absolute Beginner to Intermediate

---

## Table of Contents
1. [Introduction to HTML](#introduction-to-html)
2. [HTML Document Structure](#html-document-structure)
3. [Basic HTML Elements](#basic-html-elements)
4. [Text Formatting](#text-formatting)
5. [Links and Navigation](#links-and-navigation)
6. [Images and Media](#images-and-media)
7. [Lists](#lists)
8. [Tables](#tables)
9. [Forms](#forms)
10. [Semantic HTML](#semantic-html)
11. [Practice Exercises](#practice-exercises)

---

## 1. Introduction to HTML

### What is HTML?

**HTML** stands for **HyperText Markup Language**. Let's break this down:

- **HyperText**: Text that contains links to other texts (hyperlinks)
- **Markup**: The process of annotating text with tags to give it structure and meaning
- **Language**: A system of communication, in this case, a computer language

### Why Learn HTML?

HTML is the foundation of every web page you see on the internet. It provides the structure and content of web pages. Think of HTML as the skeleton of a website - it defines where everything goes.

### How HTML Works

HTML uses **tags** (also called elements) to mark up content. Tags are keywords surrounded by angle brackets `< >`. Most tags come in pairs: an opening tag `<tag>` and a closing tag `</tag>`.

---

## 2. HTML Document Structure

### The Basic HTML Template

Every HTML document follows a specific structure. Let's examine it line by line:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Web Page</title>
</head>
<body>
    <h1>Welcome to My Website</h1>
    <p>This is my first paragraph.</p>
</body>
</html>
```

### Line-by-Line Explanation

#### Line 1: `<!DOCTYPE html>`
- **Purpose**: This is a **document type declaration** (not an HTML tag)
- **What it does**: Tells the browser "this document uses HTML5"
- **Why it's important**: Ensures the browser renders your page correctly
- **Note**: Must be the very first line in your HTML file

#### Line 2: `<html lang="en">`
- **Purpose**: The root element of the HTML document
- **What it contains**: All other HTML elements
- **`lang="en"`**: An attribute that specifies the language (English)
- **Why `lang` matters**: Helps screen readers and search engines understand the content
- **Closing tag**: `</html>` must be the last tag in your document

#### Lines 3-7: The `<head>` Section
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Web Page</title>
</head>
```

**The `<head>` element:**
- **Purpose**: Contains metadata (data about the document)
- **Not visible**: Nothing in `<head>` appears on the webpage
- **Contains**: Title, CSS links, JavaScript links, meta information

**Line 4: `<meta charset="UTF-8">`**
- **Purpose**: Defines the character encoding
- **UTF-8**: Supports all characters and symbols in all languages
- **Why important**: Without this, special characters might display incorrectly
- **Must be**: Within the first 1024 bytes of your document

**Line 5: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`**
- **Purpose**: Makes your page mobile-responsive
- **`width=device-width`**: Sets page width to match device width
- **`initial-scale=1.0`**: Sets initial zoom level to 100%
- **Why important**: Without this, mobile devices might show a tiny desktop version

**Line 6: `<title>My First Web Page</title>`**
- **Purpose**: Sets the title shown in the browser tab
- **Also used**: As the default bookmark name
- **SEO impact**: Important for search engines

#### Lines 8-11: The `<body>` Section
```html
<body>
    <h1>Welcome to My Website</h1>
    <p>This is my first paragraph.</p>
</body>
```

**The `<body>` element:**
- **Purpose**: Contains all visible content of the webpage
- **Everything you see**: All text, images, links, etc. go here
- **One per page**: Only one `<body>` tag per HTML document

---

## 3. Basic HTML Elements

### Headings: `<h1>` to `<h6>`

HTML provides six levels of headings, from most important to least important:

```html
<h1>This is Heading Level 1</h1>
<h2>This is Heading Level 2</h2>
<h3>This is Heading Level 3</h3>
<h4>This is Heading Level 4</h4>
<h5>This is Heading Level 5</h5>
<h6>This is Heading Level 6</h6>
```

**Important Rules:**
- `<h1>` should appear only once per page (main topic)
- Use headings in order (don't skip from h2 to h4)
- Headings create document structure and help with SEO

### Paragraphs: `<p>`

The `<p>` tag defines a paragraph:

```html
<p>This is a paragraph. It can contain multiple sentences.</p>
<p>This is another paragraph. Browsers automatically add spacing between paragraphs.</p>
```

**Purpose:**
- Groups related sentences together
- Browsers add spacing before and after paragraphs
- Essential for readable text

### Line Breaks: `<br>`

Creates a line break without starting a new paragraph:

```html
<p>This is line one.<br>This is line two in the same paragraph.</p>
```

**Key Points:**
- Self-closing tag (no closing tag needed in HTML5)
- Use sparingly - prefer paragraphs for structure
- Can also be written as `<br />`

### Horizontal Rule: `<hr>`

Creates a horizontal line (thematic break):

```html
<p>First section</p>
<hr>
<p>Second section</p>
```

**Purpose:**
- Separates content sections visually
- Indicates a thematic change in content

---

## 4. Text Formatting

### Bold and Strong: `<b>` vs `<strong>`

```html
<p>This text is <b>bold</b> using the b tag.</p>
<p>This text is <strong>important</strong> using the strong tag.</p>
```

**Difference:**
- `<b>`: Visual styling only (bold appearance)
- `<strong>`: Semantic meaning (indicates importance) - preferred for accessibility

### Italic and Emphasis: `<i>` vs `<em>`

```html
<p>This text is <i>italic</i> using the i tag.</p>
<p>This text has <em>emphasis</em> using the em tag.</p>
```

**Difference:**
- `<i>`: Visual styling only (italic appearance)
- `<em>`: Semantic meaning (indicates emphasis) - preferred for accessibility

### Other Text Formatting Tags

```html
<p>This is <mark>highlighted</mark> text.</p>
<p>This is <small>smaller</small> text.</p>
<p>This is <del>deleted</del> text (crossed out).</p>
<p>This is <ins>inserted</ins> text (underlined).</p>
<p>This is <sub>subscript</sub> text (H<sub>2</sub>O).</p>
<p>This is <sup>superscript</sup> text (E=mc<sup>2</sup>).</p>
```

**Purpose of each:**
- `<mark>`: Highlights text (like a marker pen)
- `<small>`: Makes text smaller (often used for disclaimers)
- `<del>`: Marks text as deleted (shows edits)
- `<ins>`: Marks text as inserted (shows additions)
- `<sub>`: Subscript (for formulas, footnotes)
- `<sup>`: Superscript (for exponents, footnotes)

---

## 5. Links and Navigation

### Creating Links: `<a>` Tag

The `<a>` (anchor) tag creates hyperlinks:

```html
<a href="https://www.example.com">Visit Example.com</a>
```

**Breaking it down:**
- `<a>`: Opening anchor tag
- `href`: Attribute (hypertext reference) - the URL destination
- `"https://www.example.com"`: The URL value (always in quotes)
- `Visit Example.com`: The visible link text (called "link text")
- `</a>`: Closing tag

### Types of Links

**1. External Links (to other websites):**
```html
<a href="https://www.google.com">Go to Google</a>
```

**2. Internal Links (to other pages on your site):**
```html
<a href="about.html">About Us</a>
```

**3. Links to Sections (within same page):**
```html
<!-- First, create an id on the target element -->
<h2 id="section1">Section 1</h2>

<!-- Then link to it -->
<a href="#section1">Jump to Section 1</a>
```

**4. Email Links:**
```html
<a href="mailto:example@email.com">Send Email</a>
```

**5. Phone Links:**
```html
<a href="tel:+1234567890">Call Us</a>
```

### Link Attributes

**Target Attribute:**
```html
<!-- Opens in same tab (default) -->
<a href="https://example.com">Same Tab</a>

<!-- Opens in new tab -->
<a href="https://example.com" target="_blank">New Tab</a>

<!-- Opens in new tab with security (recommended) -->
<a href="https://example.com" target="_blank" rel="noopener noreferrer">Secure New Tab</a>
```

**Explanation:**
- `target="_blank"`: Opens link in new tab/window
- `rel="noopener noreferrer"`: Security attribute that prevents the new page from accessing the original window

---

## 6. Images and Media

### Adding Images: `<img>` Tag

```html
<img src="image.jpg" alt="Description of image">
```

**Breaking it down:**
- `<img>`: Image tag (self-closing)
- `src`: Source attribute - path to the image file
- `alt`: Alternative text - description for screen readers and when image fails to load
- **Important**: Always include `alt` text for accessibility

### Image Examples

**1. Image in same folder:**
```html
<img src="photo.jpg" alt="A beautiful sunset">
```

**2. Image in subfolder:**
```html
<img src="images/photo.jpg" alt="A beautiful sunset">
```

**3. Image from internet:**
```html
<img src="https://example.com/image.jpg" alt="A beautiful sunset">
```

**4. Image with width and height:**
```html
<img src="photo.jpg" alt="A beautiful sunset" width="500" height="300">
```

**Note:** In modern web development, use CSS for sizing instead of HTML attributes.

### Adding Videos: `<video>` Tag

```html
<video controls width="640" height="360">
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    Your browser does not support the video tag.
</video>
```

**Explanation:**
- `controls`: Shows play/pause/volume controls
- `width` and `height`: Set video dimensions
- `<source>`: Multiple sources for browser compatibility
- Fallback text: Shows if browser doesn't support video

### Adding Audio: `<audio>` Tag

```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    <source src="audio.ogg" type="audio/ogg">
    Your browser does not support the audio tag.
</audio>
```

---

## 7. Lists

### Ordered Lists: `<ol>`

Creates numbered lists:

```html
<ol>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ol>
```

**Result:**
1. First item
2. Second item
3. Third item

**Attributes:**
```html
<!-- Start from 5 -->
<ol start="5">
    <li>Fifth item</li>
    <li>Sixth item</li>
</ol>

<!-- Reverse numbering -->
<ol reversed>
    <li>Third item</li>
    <li>Second item</li>
    <li>First item</li>
</ol>

<!-- Use letters instead of numbers -->
<ol type="A">
    <li>First item</li>
    <li>Second item</li>
</ol>
```

### Unordered Lists: `<ul>`

Creates bulleted lists:

```html
<ul>
    <li>Apple</li>
    <li>Banana</li>
    <li>Orange</li>
</ul>
```

**Result:**
- Apple
- Banana
- Orange

### Nested Lists

You can put lists inside lists:

```html
<ul>
    <li>Fruits
        <ul>
            <li>Apple</li>
            <li>Banana</li>
        </ul>
    </li>
    <li>Vegetables
        <ul>
            <li>Carrot</li>
            <li>Broccoli</li>
        </ul>
    </li>
</ul>
```

### Description Lists: `<dl>`

For terms and descriptions:

```html
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language</dd>
    
    <dt>CSS</dt>
    <dd>Cascading Style Sheets</dd>
</dl>
```

**Explanation:**
- `<dl>`: Description list container
- `<dt>`: Term/Name (definition term)
- `<dd>`: Description/Definition

---

## 8. Tables

Tables organize data in rows and columns:

```html
<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Age</th>
            <th>City</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>John</td>
            <td>25</td>
            <td>New York</td>
        </tr>
        <tr>
            <td>Jane</td>
            <td>30</td>
            <td>London</td>
        </tr>
    </tbody>
</table>
```

### Table Structure Explained

**`<table>`**: Container for the entire table

**`<thead>`**: Table header section (contains column headers)
- Usually contains the first row with `<th>` elements
- Optional but recommended for accessibility

**`<tbody>`**: Table body section (contains data rows)
- Contains most of the table data

**`<tfoot>`**: Table footer section (optional)
```html
<tfoot>
    <tr>
        <td>Total</td>
        <td>55</td>
        <td></td>
    </tr>
</tfoot>
```

**`<tr>`**: Table row (horizontal line of cells)

**`<th>`**: Table header cell (bold, centered by default)
- Used in `<thead>` for column names

**`<td>`**: Table data cell (regular cell)

### Table Attributes (Advanced)

```html
<!-- Merge cells across columns (colspan) -->
<tr>
    <td colspan="2">Spans 2 columns</td>
    <td>Normal cell</td>
</tr>

<!-- Merge cells across rows (rowspan) -->
<tr>
    <td rowspan="2">Spans 2 rows</td>
    <td>Row 1</td>
</tr>
<tr>
    <td>Row 2</td>
</tr>
```

---

## 9. Forms

Forms collect user input. Essential elements:

### Basic Form Structure

```html
<form action="/submit" method="POST">
    <!-- Form elements go here -->
</form>
```

**Attributes:**
- `action`: URL where form data is sent
- `method`: HTTP method (GET or POST)
  - GET: Data visible in URL (for searches)
  - POST: Data hidden (for passwords, submissions)

### Text Input

```html
<label for="username">Username:</label>
<input type="text" id="username" name="username" required>
```

**Explanation:**
- `<label>`: Descriptive text for the input
- `for="username"`: Links label to input with matching `id`
- `<input>`: Input field
- `type="text"`: Single-line text input
- `id="username"`: Unique identifier
- `name="username"`: Name used when submitting form
- `required`: Makes field mandatory

### Different Input Types

```html
<!-- Password (hides text) -->
<label for="password">Password:</label>
<input type="password" id="password" name="password" required>

<!-- Email (validates email format) -->
<label for="email">Email:</label>
<input type="email" id="email" name="email" required>

<!-- Number -->
<label for="age">Age:</label>
<input type="number" id="age" name="age" min="1" max="120">

<!-- Date -->
<label for="birthday">Birthday:</label>
<input type="date" id="birthday" name="birthday">

<!-- Checkbox -->
<label>
    <input type="checkbox" name="subscribe" value="yes">
    Subscribe to newsletter
</label>

<!-- Radio buttons (choose one option) -->
<label>
    <input type="radio" name="gender" value="male">
    Male
</label>
<label>
    <input type="radio" name="gender" value="female">
    Female
</label>

<!-- Dropdown select -->
<label for="country">Country:</label>
<select id="country" name="country">
    <option value="">Choose a country</option>
    <option value="us">United States</option>
    <option value="uk">United Kingdom</option>
    <option value="ca">Canada</option>
</select>

<!-- Textarea (multi-line text) -->
<label for="message">Message:</label>
<textarea id="message" name="message" rows="4" cols="50"></textarea>

<!-- File upload -->
<label for="file">Upload file:</label>
<input type="file" id="file" name="file">

<!-- Range slider -->
<label for="volume">Volume:</label>
<input type="range" id="volume" name="volume" min="0" max="100" value="50">

<!-- Color picker -->
<label for="color">Choose color:</label>
<input type="color" id="color" name="color">
```

### Submit Button

```html
<button type="submit">Submit Form</button>
<!-- OR -->
<input type="submit" value="Submit Form">
```

### Complete Form Example

```html
<form action="/submit" method="POST">
    <fieldset>
        <legend>Personal Information</legend>
        
        <label for="firstname">First Name:</label>
        <input type="text" id="firstname" name="firstname" required>
        
        <label for="lastname">Last Name:</label>
        <input type="text" id="lastname" name="lastname" required>
        
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>
        
        <label for="country">Country:</label>
        <select id="country" name="country" required>
            <option value="">Select country</option>
            <option value="us">United States</option>
            <option value="uk">United Kingdom</option>
        </select>
        
        <button type="submit">Submit</button>
    </fieldset>
</form>
```

**New Elements:**
- `<fieldset>`: Groups related form elements
- `<legend>`: Title for the fieldset

---

## 10. Semantic HTML

Semantic HTML uses tags that clearly describe their meaning and purpose. This is important for:
- **Accessibility**: Screen readers understand structure
- **SEO**: Search engines understand content
- **Maintainability**: Code is easier to read and maintain

### Common Semantic Elements

```html
<header>
    <h1>Website Title</h1>
    <nav>
        <a href="index.html">Home</a>
        <a href="about.html">About</a>
    </nav>
</header>

<main>
    <article>
        <h2>Article Title</h2>
        <p>Article content...</p>
    </article>
    
    <aside>
        <h3>Sidebar</h3>
        <p>Related information...</p>
    </aside>
</main>

<footer>
    <p>&copy; 2024 My Website</p>
</footer>
```

**Element Purposes:**

- `<header>`: Top section (logo, navigation, title)
- `<nav>`: Navigation links
- `<main>`: Main content (only one per page)
- `<article>`: Self-contained content (blog post, news article)
- `<section>`: Thematic grouping of content
- `<aside>`: Sidebar content (related info, ads)
- `<footer>`: Bottom section (copyright, links, contact)

### Complete Semantic Page Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Semantic HTML Example</title>
</head>
<body>
    <header>
        <h1>My Blog</h1>
        <nav>
            <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="about.html">About</a></li>
                <li><a href="contact.html">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <article>
            <header>
                <h2>Article Title</h2>
                <p>Published on <time datetime="2024-01-15">January 15, 2024</time></p>
            </header>
            
            <section>
                <h3>Introduction</h3>
                <p>This is the introduction section...</p>
            </section>
            
            <section>
                <h3>Main Content</h3>
                <p>This is the main content section...</p>
            </section>
        </article>
    </main>
    
    <footer>
        <p>&copy; 2024 My Blog. All rights reserved.</p>
    </footer>
</body>
</html>
```

---

## 11. Practice Exercises

### Exercise 1: Basic Page Structure
Create an HTML page with:
- Proper document structure
- A title
- A heading
- Three paragraphs
- A link to another website

### Exercise 2: Personal Page
Create a personal introduction page with:
- Your name as h1
- A short biography in paragraphs
- A list of your hobbies
- A link to your email
- An image (or placeholder)

### Exercise 3: Product List
Create a page showing 5 products with:
- Product name (heading)
- Product image
- Product description
- Price
- "Add to Cart" button (form button)

### Exercise 4: Contact Form
Create a contact form with:
- Name field
- Email field
- Phone field
- Message textarea
- Submit button
- Proper labels and accessibility

### Exercise 5: Restaurant Menu
Create a restaurant menu using:
- Semantic HTML
- Tables for menu items and prices
- Headings for categories (Appetizers, Main Course, Desserts)
- Proper structure with header, main, footer

---

## Key Takeaways

1. **HTML provides structure** - It defines what content goes where
2. **Always use semantic HTML** - Makes your code more accessible and maintainable
3. **Validate your HTML** - Use tools like W3C Validator to check for errors
4. **Accessibility matters** - Always include alt text, labels, and proper structure
5. **Practice regularly** - Build small projects to reinforce learning

---

## Next Steps

After mastering HTML basics, you're ready to learn:
- CSS for styling and layout
- Advanced HTML features
- HTML5 APIs
- Form validation
- Responsive design principles

---

*Remember: Every expert was once a beginner. Keep practicing, keep building, and keep learning!*


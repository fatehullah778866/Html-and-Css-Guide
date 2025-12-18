# CSS Basics - Complete Guide
## From Absolute Beginner to Intermediate

---

## Table of Contents
1. [Introduction to CSS](#introduction-to-css)
2. [How CSS Works](#how-css-works)
3. [CSS Syntax](#css-syntax)
4. [Selectors](#selectors)
5. [Colors](#colors)
6. [Typography](#typography)
7. [Box Model](#box-model)
8. [Layout Basics](#layout-basics)
9. [Backgrounds](#backgrounds)
10. [Borders and Shadows](#borders-and-shadows)
11. [Display Property](#display-property)
12. [Positioning](#positioning)
13. [Practice Exercises](#practice-exercises)

---

## 1. Introduction to CSS

### What is CSS?

**CSS** stands for **Cascading Style Sheets**. Let's break this down:

- **Cascading**: Styles cascade down from multiple sources (browser defaults, user styles, author styles)
- **Style**: How elements look (colors, fonts, spacing, layout)
- **Sheets**: The CSS file contains rules for styling

### Why Learn CSS?

CSS controls the **visual presentation** of web pages. While HTML provides structure, CSS makes it beautiful. CSS handles:
- Colors and typography
- Layout and positioning
- Spacing and sizing
- Animations and transitions
- Responsive design

### CSS and HTML Relationship

Think of it this way:
- **HTML** = The skeleton (structure)
- **CSS** = The skin and clothes (appearance)

---

## 2. How CSS Works

### Three Ways to Add CSS

#### Method 1: Inline Styles (Not Recommended for Production)

```html
<p style="color: blue; font-size: 18px;">This text is blue and 18px.</p>
```

**Pros:**
- Quick for testing
- High specificity (overrides other styles)

**Cons:**
- Hard to maintain
- Can't reuse styles
- Mixes content with presentation

#### Method 2: Internal/Embedded Styles

```html
<head>
    <style>
        p {
            color: blue;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <p>This paragraph is styled.</p>
</body>
```

**Pros:**
- All styles in one place
- Easy for small projects

**Cons:**
- Can't reuse across multiple pages
- Mixes HTML with CSS

#### Method 3: External Stylesheet (Recommended)

**HTML file:**
```html
<head>
    <link rel="stylesheet" href="styles.css">
</head>
```

**styles.css file:**
```css
p {
    color: blue;
    font-size: 18px;
}
```

**Pros:**
- Separates concerns (HTML vs CSS)
- Reusable across multiple pages
- Easier to maintain
- Can be cached by browser

**This is the method you should use in production!**

### CSS File Structure

Create a `styles.css` file and link it in your HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Page</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Welcome</h1>
    <p>This page uses external CSS.</p>
</body>
</html>
```

---

## 3. CSS Syntax

### Basic Syntax Structure

```css
selector {
    property: value;
    property: value;
}
```

### Breaking Down the Syntax

```css
p {
    color: red;
    font-size: 16px;
}
```

**Explanation:**
- `p`: The **selector** - which HTML element to style
- `{ }`: Curly braces contain the **declaration block**
- `color: red;`: A **declaration** (property: value pair)
- `color`: The **property** - what aspect to change
- `red`: The **value** - how to change it
- `;`: Semicolon ends each declaration (required)

### Multiple Declarations

You can have multiple properties in one rule:

```css
p {
    color: blue;
    font-size: 18px;
    font-weight: bold;
    margin: 10px;
    padding: 5px;
}
```

**Important:** Each declaration must end with a semicolon `;`

### Comments in CSS

```css
/* This is a single-line comment */

/* This is a 
   multi-line comment */

p {
    color: blue; /* This is an inline comment */
}
```

---

## 4. Selectors

Selectors determine which HTML elements the CSS rules apply to.

### Element Selector

Selects all elements of a specific type:

```css
p {
    color: blue;
}

h1 {
    color: red;
}
```

**What it selects:**
- `p` selects all `<p>` elements
- `h1` selects all `<h1>` elements

### Class Selector

Selects elements with a specific class attribute:

```html
<p class="highlight">This is highlighted</p>
<p>This is not highlighted</p>
```

```css
.highlight {
    background-color: yellow;
}
```

**Syntax:** Use a dot `.` followed by the class name

**Multiple classes:** Elements can have multiple classes:
```html
<p class="highlight important">This has two classes</p>
```

### ID Selector

Selects an element with a specific ID:

```html
<p id="intro">Introduction paragraph</p>
```

```css
#intro {
    font-size: 24px;
    font-weight: bold;
}
```

**Syntax:** Use a hash `#` followed by the ID name

**Important:** IDs must be unique (only one element per page can have a specific ID)

### Universal Selector

Selects all elements:

```css
* {
    margin: 0;
    padding: 0;
}
```

**Common use:** Reset styles (removing default margins/padding)

### Attribute Selector

Selects elements based on attributes:

```css
/* Elements with a specific attribute */
input[type="text"] {
    border: 1px solid #ccc;
}

/* Elements with the attribute (regardless of value) */
a[href] {
    color: blue;
}

/* Attribute contains value */
a[href*="example"] {
    color: green;
}
```

### Descendant Selector

Selects elements inside other elements:

```html
<div class="container">
    <p>This paragraph is selected</p>
</div>
<p>This paragraph is NOT selected</p>
```

```css
.container p {
    color: red;
}
```

**Syntax:** `parent child` (space-separated)

### Child Selector

Selects direct children only:

```html
<div class="parent">
    <p>Selected (direct child)</p>
    <section>
        <p>NOT selected (grandchild)</p>
    </section>
</div>
```

```css
.parent > p {
    color: red;
}
```

**Syntax:** `parent > child` (using `>`)

### Adjacent Sibling Selector

Selects element immediately following another:

```html
<h2>Heading</h2>
<p>This paragraph is selected</p>
<p>This paragraph is NOT selected</p>
```

```css
h2 + p {
    color: red;
}
```

**Syntax:** `element1 + element2`

### General Sibling Selector

Selects all siblings following an element:

```html
<h2>Heading</h2>
<p>Selected</p>
<p>Also selected</p>
```

```css
h2 ~ p {
    color: red;
}
```

**Syntax:** `element1 ~ element2`

### Pseudo-classes

Select elements in a specific state:

```css
/* Unvisited link */
a:link {
    color: blue;
}

/* Visited link */
a:visited {
    color: purple;
}

/* Hover state */
a:hover {
    color: red;
}

/* Active state (while clicking) */
a:active {
    color: green;
}

/* Focus state (for keyboard navigation) */
input:focus {
    border: 2px solid blue;
}

/* First child */
li:first-child {
    font-weight: bold;
}

/* Last child */
li:last-child {
    margin-bottom: 0;
}

/* nth child */
li:nth-child(2) {
    color: red;
}

li:nth-child(even) {
    background-color: #f0f0f0;
}

li:nth-child(odd) {
    background-color: white;
}
```

### Pseudo-elements

Style specific parts of an element:

```css
/* First line */
p::first-line {
    font-weight: bold;
}

/* First letter */
p::first-letter {
    font-size: 200%;
    color: red;
}

/* Before content */
p::before {
    content: "→ ";
}

/* After content */
p::after {
    content: " ←";
}
```

### Selector Specificity

When multiple rules target the same element, CSS uses specificity:

**Order of priority (lowest to highest):**
1. Element selectors (`p`, `div`)
2. Class selectors (`.class`)
3. ID selectors (`#id`)
4. Inline styles (`style="..."`)

```css
/* Specificity: 1 (element) */
p { color: black; }

/* Specificity: 10 (class) */
.text { color: blue; }

/* Specificity: 100 (ID) */
#intro { color: red; }
```

**If same specificity, last rule wins:**
```css
p { color: blue; }
p { color: red; } /* This wins */
```

---

## 5. Colors

### Color Values

CSS provides several ways to specify colors:

#### Named Colors

```css
p {
    color: red;
    background-color: blue;
    border-color: green;
}
```

**Common named colors:** red, blue, green, black, white, yellow, orange, purple, pink, gray, etc.

#### RGB (Red, Green, Blue)

```css
p {
    color: rgb(255, 0, 0); /* Red */
    color: rgb(0, 255, 0); /* Green */
    color: rgb(0, 0, 255); /* Blue */
    color: rgb(128, 128, 128); /* Gray */
}
```

**Values:** 0-255 for each color component

#### RGBA (RGB with Alpha/Transparency)

```css
p {
    background-color: rgba(255, 0, 0, 0.5); /* Red with 50% opacity */
}
```

**Alpha value:** 0.0 (fully transparent) to 1.0 (fully opaque)

#### Hexadecimal

```css
p {
    color: #ff0000; /* Red */
    color: #00ff00; /* Green */
    color: #0000ff; /* Blue */
    color: #ffffff; /* White */
    color: #000000; /* Black */
    color: #ff00ff; /* Magenta */
}
```

**Format:** `#RRGGBB` (each pair is 00-FF in hexadecimal)

**Shorthand:** `#f00` = `#ff0000`, `#0f0` = `#00ff00`

#### HSL (Hue, Saturation, Lightness)

```css
p {
    color: hsl(0, 100%, 50%); /* Red */
    color: hsl(120, 100%, 50%); /* Green */
    color: hsl(240, 100%, 50%); /* Blue */
}
```

**Values:**
- Hue: 0-360 (color wheel)
- Saturation: 0-100% (0% = gray, 100% = full color)
- Lightness: 0-100% (0% = black, 50% = normal, 100% = white)

#### HSLA (HSL with Alpha)

```css
p {
    background-color: hsla(0, 100%, 50%, 0.5); /* Red with 50% opacity */
}
```

### Color Properties

```css
/* Text color */
p {
    color: blue;
}

/* Background color */
p {
    background-color: yellow;
}

/* Border color */
p {
    border: 2px solid red;
}
```

---

## 6. Typography

### Font Properties

#### Font Family

```css
p {
    font-family: Arial, sans-serif;
}
```

**Font stacks:** Provide fallbacks (browser tries first font, then next, etc.)

**Generic font families:**
- `serif`: Times New Roman, Georgia
- `sans-serif`: Arial, Helvetica, Verdana
- `monospace`: Courier, monospace
- `cursive`: Brush Script, cursive
- `fantasy`: Impact, fantasy

**Best practice:** Always end with a generic family name

#### Font Size

```css
p {
    font-size: 16px; /* Pixels */
    font-size: 1em; /* Relative to parent */
    font-size: 1rem; /* Relative to root */
    font-size: 100%; /* Percentage */
    font-size: 12pt; /* Points (for print) */
}
```

**Common sizes:**
- `12px` - Small text
- `14px` - Default body text
- `16px` - Standard body text (browser default)
- `18px` - Larger body text
- `24px` - Subheadings
- `32px` - Headings

#### Font Weight

```css
p {
    font-weight: normal; /* 400 */
    font-weight: bold; /* 700 */
    font-weight: 100; /* Thin */
    font-weight: 400; /* Normal */
    font-weight: 700; /* Bold */
    font-weight: 900; /* Black */
}
```

#### Font Style

```css
p {
    font-style: normal;
    font-style: italic;
    font-style: oblique;
}
```

#### Font Shorthand

```css
p {
    font: italic bold 16px/1.5 Arial, sans-serif;
}
```

**Order:** style weight size/line-height family

### Text Properties

#### Text Alignment

```css
p {
    text-align: left; /* Default */
    text-align: right;
    text-align: center;
    text-align: justify; /* Spreads text across full width */
}
```

#### Text Decoration

```css
a {
    text-decoration: none; /* Remove underline */
    text-decoration: underline;
    text-decoration: overline;
    text-decoration: line-through;
}
```

#### Text Transform

```css
p {
    text-transform: none;
    text-transform: uppercase;
    text-transform: lowercase;
    text-transform: capitalize; /* First letter of each word */
}
```

#### Letter Spacing

```css
h1 {
    letter-spacing: 2px; /* Space between letters */
    letter-spacing: -1px; /* Tighter spacing */
}
```

#### Line Height

```css
p {
    line-height: 1.5; /* 1.5 times font size */
    line-height: 24px; /* Specific pixel value */
    line-height: 150%; /* Percentage */
}
```

**Best practice:** Use unitless values (1.5 instead of 1.5em) to avoid inheritance issues

#### Word Spacing

```css
p {
    word-spacing: 5px; /* Space between words */
}
```

---

## 7. Box Model

The CSS Box Model is fundamental to understanding layout. Every element is a rectangular box with four areas:

### Box Model Components

```
┌─────────────────────────────────────┐
│         MARGIN (transparent)        │
│  ┌───────────────────────────────┐  │
│  │       BORDER                  │  │
│  │  ┌─────────────────────────┐  │  │
│  │  │    PADDING              │  │  │
│  │  │  ┌───────────────────┐  │  │  │
│  │  │  │                   │  │  │  │
│  │  │  │     CONTENT       │  │  │  │
│  │  │  │                   │  │  │  │
│  │  │  └───────────────────┘  │  │  │
│  │  └─────────────────────────┘  │  │
│  └───────────────────────────────┘  │
└─────────────────────────────────────┘
```

### Margin

Space **outside** the border (between elements):

```css
p {
    margin: 10px; /* All sides */
    margin: 10px 20px; /* Top/bottom, Left/right */
    margin: 10px 20px 30px 40px; /* Top, Right, Bottom, Left (clockwise) */
    
    /* Individual sides */
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 30px;
    margin-left: 40px;
}
```

**Negative margins:** Can overlap elements:
```css
.box {
    margin-top: -10px; /* Moves element up */
}
```

### Padding

Space **inside** the border (between border and content):

```css
p {
    padding: 10px; /* All sides */
    padding: 10px 20px; /* Top/bottom, Left/right */
    padding: 10px 20px 30px 40px; /* Top, Right, Bottom, Left */
    
    /* Individual sides */
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 30px;
    padding-left: 40px;
}
```

**Difference from margin:** Padding affects background color, margin does not.

### Border

The line around the element:

```css
p {
    border: 1px solid black;
}
```

**Shorthand:** `width style color`

**Individual properties:**
```css
p {
    border-width: 1px;
    border-style: solid;
    border-color: black;
}
```

**Border styles:**
- `solid`: Solid line
- `dashed`: Dashed line
- `dotted`: Dotted line
- `double`: Double line
- `groove`: 3D grooved
- `ridge`: 3D ridged
- `inset`: 3D inset
- `outset`: 3D outset
- `none`: No border

**Individual sides:**
```css
p {
    border-top: 2px solid red;
    border-right: 2px solid blue;
    border-bottom: 2px solid green;
    border-left: 2px solid yellow;
}
```

### Content Area

The actual content (text, images, etc.):

```css
p {
    width: 300px; /* Content width */
    height: 200px; /* Content height */
}
```

### Box-Sizing Property

Controls how width and height are calculated:

```css
/* Default behavior (content-box) */
.box {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    /* Total width = 300 + 40 + 10 = 350px */
}

/* Border-box (includes padding and border in width) */
.box {
    box-sizing: border-box;
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    /* Total width = 300px (content shrinks) */
}
```

**Best practice:** Use `border-box` for predictable sizing:

```css
* {
    box-sizing: border-box;
}
```

---

## 8. Layout Basics

### Width and Height

```css
.box {
    width: 300px; /* Fixed width */
    width: 50%; /* Percentage of parent */
    width: auto; /* Default - fills available space */
    
    height: 200px; /* Fixed height */
    height: 100vh; /* Viewport height (100% of screen) */
    height: auto; /* Default - fits content */
}
```

**Viewport units:**
- `vw`: 1% of viewport width
- `vh`: 1% of viewport height
- `vmin`: 1% of smaller viewport dimension
- `vmax`: 1% of larger viewport dimension

### Max and Min Dimensions

```css
.container {
    max-width: 1200px; /* Won't exceed 1200px */
    min-width: 300px; /* Won't be smaller than 300px */
    max-height: 500px;
    min-height: 200px;
}
```

**Common use:** Responsive containers:
```css
.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto; /* Centers the container */
}
```

### Overflow

Controls what happens when content exceeds container:

```css
.box {
    overflow: visible; /* Default - content overflows */
    overflow: hidden; /* Hides overflow */
    overflow: scroll; /* Adds scrollbar */
    overflow: auto; /* Adds scrollbar only if needed */
    
    /* Individual axes */
    overflow-x: scroll;
    overflow-y: hidden;
}
```

---

## 9. Backgrounds

### Background Color

```css
body {
    background-color: #f0f0f0;
    background-color: rgb(240, 240, 240);
    background-color: rgba(240, 240, 240, 0.5); /* With transparency */
}
```

### Background Image

```css
body {
    background-image: url('image.jpg');
}
```

**Important:** Provide fallback color:
```css
body {
    background-color: #f0f0f0; /* Fallback */
    background-image: url('image.jpg');
}
```

### Background Repeat

```css
body {
    background-image: url('pattern.png');
    background-repeat: repeat; /* Default - tiles */
    background-repeat: no-repeat; /* Single image */
    background-repeat: repeat-x; /* Horizontal only */
    background-repeat: repeat-y; /* Vertical only */
}
```

### Background Position

```css
body {
    background-image: url('image.jpg');
    background-position: center; /* center, top, bottom, left, right */
    background-position: 50% 50%; /* Percentage */
    background-position: 10px 20px; /* Pixels */
}
```

### Background Size

```css
body {
    background-image: url('image.jpg');
    background-size: cover; /* Covers entire area, may crop */
    background-size: contain; /* Fits entire image, may show gaps */
    background-size: 100% 100%; /* Stretches to fill */
    background-size: 300px 200px; /* Specific size */
}
```

### Background Attachment

```css
body {
    background-image: url('image.jpg');
    background-attachment: scroll; /* Default - scrolls with content */
    background-attachment: fixed; /* Stays fixed while scrolling */
}
```

### Background Shorthand

```css
body {
    background: #f0f0f0 url('image.jpg') no-repeat center/cover fixed;
}
```

**Order:** color image repeat position/size attachment

---

## 10. Borders and Shadows

### Border Radius (Rounded Corners)

```css
.box {
    border-radius: 10px; /* All corners */
    border-radius: 10px 20px; /* Top-left/bottom-right, Top-right/bottom-left */
    border-radius: 10px 20px 30px 40px; /* Top-left, Top-right, Bottom-right, Bottom-left */
    
    /* Individual corners */
    border-top-left-radius: 10px;
    border-top-right-radius: 20px;
    border-bottom-right-radius: 10px;
    border-bottom-left-radius: 20px;
    
    /* Perfect circle (if element is square) */
    border-radius: 50%;
}
```

### Box Shadow

Adds shadow to elements:

```css
.box {
    box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
}
```

**Syntax:** `offset-x offset-y blur-radius spread-radius color`

```css
.box {
    /* Simple shadow */
    box-shadow: 2px 2px 5px black;
    
    /* With spread */
    box-shadow: 0 0 10px 5px rgba(0, 0, 0, 0.2);
    
    /* Inset shadow (inside) */
    box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.5);
    
    /* Multiple shadows */
    box-shadow: 
        0 2px 5px rgba(0, 0, 0, 0.2),
        0 5px 10px rgba(0, 0, 0, 0.1);
}
```

### Text Shadow

Adds shadow to text:

```css
h1 {
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}
```

**Syntax:** `offset-x offset-y blur-radius color`

```css
h1 {
    /* Simple shadow */
    text-shadow: 2px 2px 4px black;
    
    /* Multiple shadows (glow effect) */
    text-shadow: 
        0 0 10px #fff,
        0 0 20px #fff,
        0 0 30px #fff;
}
```

---

## 11. Display Property

Controls how elements are displayed:

### Block

```css
div {
    display: block; /* Default for div, p, h1-h6 */
}
```

**Characteristics:**
- Takes full width available
- Starts on new line
- Can set width and height
- Can have margin and padding

### Inline

```css
span {
    display: inline; /* Default for span, a, strong, em */
}
```

**Characteristics:**
- Only takes width of content
- Stays on same line
- Cannot set width and height
- Only horizontal margin/padding work

### Inline-Block

```css
.button {
    display: inline-block;
}
```

**Characteristics:**
- Stays on same line (like inline)
- Can set width and height (like block)
- Best of both worlds

**Common use:** Navigation buttons, icon lists

### None

```css
.hidden {
    display: none; /* Completely removes element */
}
```

**Note:** Element is removed from document flow (unlike `visibility: hidden`)

### Flex (Advanced - covered later)

```css
.container {
    display: flex;
}
```

### Grid (Advanced - covered later)

```css
.container {
    display: grid;
}
```

---

## 12. Positioning

Controls where elements are positioned:

### Static (Default)

```css
.box {
    position: static; /* Default - normal document flow */
}
```

### Relative

```css
.box {
    position: relative;
    top: 20px; /* Moves 20px down from original position */
    left: 30px; /* Moves 30px right from original position */
}
```

**Characteristics:**
- Element stays in document flow
- Can use top, right, bottom, left to offset
- Original space is preserved

### Absolute

```css
.box {
    position: absolute;
    top: 50px;
    left: 100px;
}
```

**Characteristics:**
- Removed from document flow
- Positioned relative to nearest positioned ancestor
- If no positioned ancestor, positioned relative to body
- Other elements act like it doesn't exist

**Example:**
```html
<div class="parent" style="position: relative;">
    <div class="child" style="position: absolute; top: 0; right: 0;">
        Absolutely positioned
    </div>
</div>
```

### Fixed

```css
.header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
}
```

**Characteristics:**
- Removed from document flow
- Positioned relative to viewport (screen)
- Stays in same place when scrolling
- Common use: Fixed headers, navigation bars

### Sticky

```css
.header {
    position: sticky;
    top: 0;
}
```

**Characteristics:**
- Behaves like relative until scrolled to threshold
- Then behaves like fixed
- Requires top, right, bottom, or left value

---

## 13. Practice Exercises

### Exercise 1: Basic Styling
Create a page with:
- A heading styled with your favorite color
- Paragraphs with custom font size and line height
- Links with hover effects
- A styled button

### Exercise 2: Box Model Practice
Create boxes demonstrating:
- Different margin values
- Different padding values
- Different border styles
- Box-sizing differences

### Exercise 3: Typography
Create a page showcasing:
- Different font families
- Different font sizes
- Different font weights
- Text alignment options
- Line height variations

### Exercise 4: Navigation Bar
Create a horizontal navigation bar with:
- List items displayed inline
- Hover effects
- Active state styling
- Proper spacing

### Exercise 5: Card Component
Create a card component with:
- Border radius
- Box shadow
- Padding
- Image
- Text content
- Button

---

## Key Takeaways

1. **CSS controls appearance** - HTML is structure, CSS is style
2. **Use external stylesheets** - Best practice for maintainability
3. **Understand the box model** - Fundamental to layout
4. **Learn selectors well** - They determine what gets styled
5. **Practice regularly** - Build projects to reinforce concepts

---

## Next Steps

After mastering CSS basics, you're ready to learn:
- CSS Layout (Flexbox and Grid)
- Responsive Design (Media Queries)
- CSS Advanced (Animations, Transitions)
- CSS Preprocessors (SASS, LESS)
- CSS Frameworks (Bootstrap, Tailwind)

---

*Remember: CSS is about experimentation. Try different values, see what happens, and learn by doing!*


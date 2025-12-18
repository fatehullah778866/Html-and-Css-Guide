# CSS Advanced - Complete Guide
## Intermediate to Advanced Level

---

## Table of Contents
1. [Flexbox Layout](#flexbox-layout)
2. [CSS Grid Layout](#css-grid-layout)
3. [Responsive Design with Media Queries](#responsive-design-with-media-queries)
4. [CSS Variables (Custom Properties)](#css-variables-custom-properties)
5. [Transitions](#transitions)
6. [Animations](#animations)
7. [Transform](#transform)
8. [Advanced Selectors](#advanced-selectors)
9. [Pseudo-classes and Pseudo-elements Deep Dive](#pseudo-classes-and-pseudo-elements-deep-dive)
10. [CSS Architecture and Methodology](#css-architecture-and-methodology)
11. [Advanced Techniques](#advanced-techniques)
12. [Performance Optimization](#performance-optimization)

---

## 1. Flexbox Layout

Flexbox (Flexible Box Layout) is a powerful layout system for arranging items in one dimension (row or column).

### Flex Container Basics

To use Flexbox, set `display: flex` on a parent element:

```css
.container {
    display: flex;
}
```

**What happens:**
- Child elements become flex items
- Items arrange in a row by default
- Items shrink to fit container

### Flex Direction

Controls the direction of flex items:

```css
.container {
    display: flex;
    flex-direction: row; /* Default - left to right */
    flex-direction: row-reverse; /* Right to left */
    flex-direction: column; /* Top to bottom */
    flex-direction: column-reverse; /* Bottom to top */
}
```

### Justify Content

Aligns items along the main axis (horizontal for row, vertical for column):

```css
.container {
    display: flex;
    justify-content: flex-start; /* Default - start */
    justify-content: flex-end; /* End */
    justify-content: center; /* Center */
    justify-content: space-between; /* Space between items */
    justify-content: space-around; /* Space around items */
    justify-content: space-evenly; /* Equal space everywhere */
}
```

**Visual Example:**
```
flex-start:    [Item1][Item2][Item3]
flex-end:                      [Item1][Item2][Item3]
center:            [Item1][Item2][Item3]
space-between: [Item1]      [Item2]      [Item3]
space-around:  [ Item1 ]  [ Item2 ]  [ Item3 ]
space-evenly:  [  Item1  ][  Item2  ][  Item3  ]
```

### Align Items

Aligns items along the cross axis (vertical for row, horizontal for column):

```css
.container {
    display: flex;
    align-items: stretch; /* Default - fills cross axis */
    align-items: flex-start; /* Start of cross axis */
    align-items: flex-end; /* End of cross axis */
    align-items: center; /* Center */
    align-items: baseline; /* Align by text baseline */
}
```

### Flex Wrap

Controls whether items wrap to new line:

```css
.container {
    display: flex;
    flex-wrap: nowrap; /* Default - no wrapping */
    flex-wrap: wrap; /* Wrap to new line */
    flex-wrap: wrap-reverse; /* Wrap in reverse */
}

/* Shorthand */
.container {
    flex-flow: row wrap; /* direction and wrap together */
}
```

### Align Content

Aligns wrapped lines (only works with `flex-wrap: wrap`):

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: stretch; /* Default */
    align-content: flex-start;
    align-content: flex-end;
    align-content: center;
    align-content: space-between;
    align-content: space-around;
}
```

### Gap (Modern Flexbox)

Adds space between flex items:

```css
.container {
    display: flex;
    gap: 20px; /* Space between all items */
    row-gap: 10px; /* Space between rows */
    column-gap: 15px; /* Space between columns */
}
```

### Flex Item Properties

These properties are set on child elements (flex items):

#### Flex Grow

How much an item should grow relative to others:

```css
.item {
    flex-grow: 0; /* Default - don't grow */
    flex-grow: 1; /* Grow to fill available space */
}

.item-1 {
    flex-grow: 1; /* Takes 1 part */
}
.item-2 {
    flex-grow: 2; /* Takes 2 parts (twice as much) */
}
```

#### Flex Shrink

How much an item should shrink relative to others:

```css
.item {
    flex-shrink: 1; /* Default - can shrink */
    flex-shrink: 0; /* Don't shrink */
}
```

#### Flex Basis

Initial size before growing/shrinking:

```css
.item {
    flex-basis: auto; /* Default - use width/height */
    flex-basis: 200px; /* Initial size 200px */
    flex-basis: 25%; /* Initial size 25% of container */
}
```

#### Flex Shorthand

```css
.item {
    flex: 1 1 200px; /* grow shrink basis */
    flex: 1; /* Same as flex: 1 1 0% */
    flex: 0 0 200px; /* Don't grow or shrink, stay 200px */
}
```

#### Align Self

Overrides `align-items` for individual item:

```css
.item {
    align-self: auto; /* Default - use parent's align-items */
    align-self: flex-start;
    align-self: flex-end;
    align-self: center;
    align-self: stretch;
}
```

### Complete Flexbox Example

```html
<div class="flex-container">
    <div class="flex-item">Item 1</div>
    <div class="flex-item">Item 2</div>
    <div class="flex-item">Item 3</div>
</div>
```

```css
.flex-container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
    height: 300px;
}

.flex-item {
    flex: 1; /* Grow equally */
    padding: 20px;
    background-color: #f0f0f0;
}
```

---

## 2. CSS Grid Layout

CSS Grid is a two-dimensional layout system (rows AND columns simultaneously).

### Grid Container Basics

```css
.container {
    display: grid;
}
```

### Defining Grid Columns and Rows

#### Using grid-template-columns

```css
.container {
    display: grid;
    grid-template-columns: 200px 200px 200px; /* 3 columns, 200px each */
    grid-template-columns: 1fr 1fr 1fr; /* 3 equal columns (fr = fraction) */
    grid-template-columns: repeat(3, 1fr); /* Same as above */
    grid-template-columns: 200px 1fr 2fr; /* First 200px, second 1 part, third 2 parts */
}
```

#### Using grid-template-rows

```css
.container {
    display: grid;
    grid-template-rows: 100px 200px 100px; /* 3 rows with specific heights */
    grid-template-rows: repeat(3, 1fr); /* 3 equal rows */
}
```

#### Combined Example

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 100px);
}
```

### Grid Gap

```css
.container {
    display: grid;
    gap: 20px; /* Both row and column gap */
    row-gap: 10px;
    column-gap: 15px;
    
    /* Older syntax (still works) */
    grid-gap: 20px;
    grid-row-gap: 10px;
    grid-column-gap: 15px;
}
```

### Grid Template Areas

Named grid areas for easier layout:

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr;
    grid-template-rows: auto 1fr auto;
    grid-template-areas: 
        "header header"
        "sidebar main"
        "footer footer";
}

.header {
    grid-area: header;
}
.sidebar {
    grid-area: sidebar;
}
.main {
    grid-area: main;
}
.footer {
    grid-area: footer;
}
```

### Grid Item Placement

#### Grid Column

```css
.item {
    grid-column: 1 / 3; /* Start at line 1, end at line 3 (spans 2 columns) */
    grid-column: 1 / span 2; /* Same as above */
    grid-column-start: 1;
    grid-column-end: 3;
}
```

#### Grid Row

```css
.item {
    grid-row: 1 / 3; /* Start at line 1, end at line 3 */
    grid-row: 1 / span 2;
    grid-row-start: 1;
    grid-row-end: 3;
}
```

#### Grid Area (Shorthand)

```css
.item {
    grid-area: 1 / 1 / 3 / 3; /* row-start / col-start / row-end / col-end */
}
```

### Auto-Fit and Auto-Fill

Responsive grid columns:

```css
.container {
    display: grid;
    /* Creates as many columns as fit, minimum 200px each */
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    
    /* Creates columns even if empty */
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
}
```

### Grid Alignment

#### Justify Items

Aligns grid items horizontally within their cells:

```css
.container {
    display: grid;
    justify-items: start; /* Default */
    justify-items: end;
    justify-items: center;
    justify-items: stretch; /* Default */
}
```

#### Align Items

Aligns grid items vertically within their cells:

```css
.container {
    display: grid;
    align-items: start;
    align-items: end;
    align-items: center;
    align-items: stretch; /* Default */
}
```

#### Place Items (Shorthand)

```css
.container {
    place-items: center; /* align-items and justify-items */
    place-items: start end; /* align-items justify-items */
}
```

#### Justify Content and Align Content

Aligns the entire grid within the container (when grid is smaller than container):

```css
.container {
    display: grid;
    justify-content: center; /* Center grid horizontally */
    align-content: center; /* Center grid vertically */
}
```

### Complete Grid Example

```html
<div class="grid-container">
    <header class="header">Header</header>
    <aside class="sidebar">Sidebar</aside>
    <main class="main">Main Content</main>
    <footer class="footer">Footer</footer>
</div>
```

```css
.grid-container {
    display: grid;
    grid-template-columns: 200px 1fr;
    grid-template-rows: auto 1fr auto;
    grid-template-areas: 
        "header header"
        "sidebar main"
        "footer footer";
    gap: 20px;
    height: 100vh;
}

.header {
    grid-area: header;
    background-color: #333;
    color: white;
}

.sidebar {
    grid-area: sidebar;
    background-color: #f0f0f0;
}

.main {
    grid-area: main;
    background-color: white;
}

.footer {
    grid-area: footer;
    background-color: #333;
    color: white;
}
```

---

## 3. Responsive Design with Media Queries

Media queries allow different styles for different screen sizes.

### Basic Syntax

```css
@media (condition) {
    /* CSS rules */
}
```

### Common Breakpoints

```css
/* Mobile first approach (default styles for mobile) */

/* Small devices (phones, 600px and up) */
@media (min-width: 600px) {
    .container {
        width: 600px;
    }
}

/* Medium devices (tablets, 768px and up) */
@media (min-width: 768px) {
    .container {
        width: 750px;
    }
}

/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) {
    .container {
        width: 970px;
    }
}

/* Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) {
    .container {
        width: 1170px;
    }
}
```

### Max-Width Media Queries

```css
/* Desktop first approach */

/* Default styles for desktop */

/* Tablets and below */
@media (max-width: 768px) {
    .sidebar {
        display: none;
    }
}

/* Mobile */
@media (max-width: 480px) {
    .container {
        padding: 10px;
    }
}
```

### Common Media Query Features

```css
/* Width */
@media (min-width: 768px) { }
@media (max-width: 1024px) { }

/* Height */
@media (min-height: 600px) { }

/* Orientation */
@media (orientation: portrait) { }
@media (orientation: landscape) { }

/* Device pixel ratio (retina displays) */
@media (-webkit-min-device-pixel-ratio: 2) { }

/* Print styles */
@media print {
    .no-print {
        display: none;
    }
}

/* Screen only */
@media screen {
    body {
        background-color: white;
    }
}
```

### Combining Conditions

```css
/* AND */
@media (min-width: 768px) and (max-width: 1024px) {
    /* Styles for tablets only */
}

/* OR */
@media (max-width: 768px), (orientation: portrait) {
    /* Styles for mobile OR portrait */
}

/* NOT */
@media not print {
    /* Styles for everything except print */
}
```

### Mobile-First Approach

```css
/* Base styles (mobile) */
.container {
    width: 100%;
    padding: 10px;
}

.nav {
    display: block;
}

/* Tablet and up */
@media (min-width: 768px) {
    .container {
        width: 750px;
        margin: 0 auto;
        padding: 20px;
    }
    
    .nav {
        display: flex;
    }
}

/* Desktop and up */
@media (min-width: 992px) {
    .container {
        width: 970px;
    }
}
```

### Responsive Images

```css
img {
    max-width: 100%;
    height: auto;
}
```

### Responsive Typography

```css
/* Fluid typography */
h1 {
    font-size: clamp(24px, 5vw, 48px);
    /* Minimum 24px, preferred 5vw, maximum 48px */
}

/* Or using media queries */
h1 {
    font-size: 24px;
}

@media (min-width: 768px) {
    h1 {
        font-size: 36px;
    }
}

@media (min-width: 1200px) {
    h1 {
        font-size: 48px;
    }
}
```

---

## 4. CSS Variables (Custom Properties)

CSS variables allow you to store values for reuse throughout your stylesheet.

### Defining Variables

Variables must be defined within a selector, typically `:root` for global access:

```css
:root {
    --primary-color: #3498db;
    --secondary-color: #2ecc71;
    --font-size-base: 16px;
    --spacing-unit: 8px;
}
```

**Naming convention:** Use `--` prefix and kebab-case

### Using Variables

```css
.button {
    background-color: var(--primary-color);
    font-size: var(--font-size-base);
    padding: var(--spacing-unit);
}
```

### Variable Fallbacks

```css
.button {
    background-color: var(--primary-color, #3498db);
    /* Uses fallback if variable doesn't exist */
    
    padding: var(--spacing-small, 10px) var(--spacing-large, 20px);
}
```

### Scoped Variables

Variables can be scoped to specific elements:

```css
.card {
    --card-padding: 20px;
    padding: var(--card-padding);
}

.card-large {
    --card-padding: 40px; /* Overrides for .card-large */
}
```

### Dynamic Variables with JavaScript

```css
:root {
    --theme-color: #3498db;
}
```

```javascript
// Change variable value
document.documentElement.style.setProperty('--theme-color', '#e74c3c');

// Get variable value
const color = getComputedStyle(document.documentElement)
    .getPropertyValue('--theme-color');
```

### Complete Example

```css
:root {
    --primary: #3498db;
    --secondary: #2ecc71;
    --danger: #e74c3c;
    --spacing: 1rem;
    --border-radius: 4px;
}

.button {
    padding: calc(var(--spacing) * 0.5) var(--spacing);
    border-radius: var(--border-radius);
    border: none;
    cursor: pointer;
}

.button-primary {
    background-color: var(--primary);
    color: white;
}

.button-secondary {
    background-color: var(--secondary);
    color: white;
}

.button-danger {
    background-color: var(--danger);
    color: white;
}
```

---

## 5. Transitions

Transitions allow smooth changes between CSS property values.

### Basic Syntax

```css
.element {
    transition: property duration timing-function delay;
}
```

### Individual Properties

```css
.button {
    background-color: blue;
    transition-property: background-color;
    transition-duration: 0.3s;
    transition-timing-function: ease;
    transition-delay: 0s;
}

.button:hover {
    background-color: red; /* Smoothly transitions from blue to red */
}
```

### Shorthand

```css
.button {
    transition: background-color 0.3s ease 0s;
}

/* Multiple properties */
.button {
    transition: background-color 0.3s, color 0.3s, transform 0.5s;
}

/* All properties (use carefully) */
.button {
    transition: all 0.3s;
}
```

### Transition Duration

```css
.element {
    transition-duration: 0.3s; /* 300 milliseconds */
    transition-duration: 1s; /* 1 second */
    transition-duration: 500ms; /* milliseconds */
}
```

### Timing Functions

Controls the speed curve of the transition:

```css
.element {
    transition-timing-function: ease; /* Default - slow, fast, slow */
    transition-timing-function: linear; /* Constant speed */
    transition-timing-function: ease-in; /* Slow start */
    transition-timing-function: ease-out; /* Slow end */
    transition-timing-function: ease-in-out; /* Slow start and end */
    transition-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1); /* Custom */
}
```

**Common cubic-bezier values:**
- `cubic-bezier(0.25, 0.1, 0.25, 1)` - ease (default)
- `cubic-bezier(0, 0, 1, 1)` - linear
- `cubic-bezier(0.42, 0, 1, 1)` - ease-in
- `cubic-bezier(0, 0, 0.58, 1)` - ease-out
- `cubic-bezier(0.42, 0, 0.58, 1)` - ease-in-out

### Transition Delay

```css
.element {
    transition-delay: 0.2s; /* Waits 0.2s before starting */
}
```

### Properties That Can Be Transitioned

Most properties can be transitioned:
- Colors (color, background-color, border-color)
- Dimensions (width, height, padding, margin)
- Position (top, left, right, bottom)
- Transform (transform, transform-origin)
- Opacity
- Visibility (with workarounds)

### Complete Example

```css
.card {
    width: 200px;
    height: 200px;
    background-color: #3498db;
    transition: all 0.3s ease;
}

.card:hover {
    width: 250px;
    height: 250px;
    background-color: #2ecc71;
    transform: scale(1.1);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}
```

---

## 6. Animations

Animations allow more complex, multi-step animations with keyframes.

### Keyframes

Define the animation steps:

```css
@keyframes slideIn {
    from {
        transform: translateX(-100%);
    }
    to {
        transform: translateX(0);
    }
}

/* Or with percentages */
@keyframes bounce {
    0% {
        transform: translateY(0);
    }
    50% {
        transform: translateY(-50px);
    }
    100% {
        transform: translateY(0);
    }
}
```

### Animation Properties

```css
.element {
    animation-name: slideIn;
    animation-duration: 1s;
    animation-timing-function: ease;
    animation-delay: 0s;
    animation-iteration-count: 1;
    animation-direction: normal;
    animation-fill-mode: none;
    animation-play-state: running;
}
```

### Animation Shorthand

```css
.element {
    animation: slideIn 1s ease 0s 1 normal none running;
    /* name duration timing-function delay iteration-count direction fill-mode play-state */
}
```

### Animation Properties Explained

#### Animation Duration

```css
.element {
    animation-duration: 2s;
}
```

#### Animation Iteration Count

```css
.element {
    animation-iteration-count: 1; /* Default - plays once */
    animation-iteration-count: 3; /* Plays 3 times */
    animation-iteration-count: infinite; /* Plays forever */
}
```

#### Animation Direction

```css
.element {
    animation-direction: normal; /* Default - forwards */
    animation-direction: reverse; /* Backwards */
    animation-direction: alternate; /* Forward then backward */
    animation-direction: alternate-reverse; /* Backward then forward */
}
```

#### Animation Fill Mode

Controls styles before/after animation:

```css
.element {
    animation-fill-mode: none; /* Default - no styles applied */
    animation-fill-mode: forwards; /* Keeps final keyframe styles */
    animation-fill-mode: backwards; /* Applies first keyframe styles during delay */
    animation-fill-mode: both; /* Both forwards and backwards */
}
```

#### Animation Play State

```css
.element {
    animation-play-state: running; /* Default */
    animation-play-state: paused; /* Pauses animation */
}
```

### Multiple Animations

```css
.element {
    animation: 
        slideIn 1s ease,
        fadeIn 1s ease,
        rotate 2s linear infinite;
}
```

### Complete Examples

#### Fade In Animation

```css
@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}

.fade-in {
    animation: fadeIn 1s ease;
}
```

#### Pulse Animation

```css
@keyframes pulse {
    0%, 100% {
        transform: scale(1);
    }
    50% {
        transform: scale(1.1);
    }
}

.pulse {
    animation: pulse 2s ease-in-out infinite;
}
```

#### Loading Spinner

```css
@keyframes spin {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(360deg);
    }
}

.spinner {
    border: 4px solid #f3f3f3;
    border-top: 4px solid #3498db;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    animation: spin 1s linear infinite;
}
```

---

## 7. Transform

The transform property allows you to rotate, scale, skew, or translate elements.

### Transform Functions

#### Translate (Move)

```css
.element {
    transform: translateX(50px); /* Move 50px right */
    transform: translateY(-20px); /* Move 20px up */
    transform: translate(50px, -20px); /* X and Y together */
}
```

#### Scale (Resize)

```css
.element {
    transform: scale(1.5); /* 150% size (both X and Y) */
    transform: scaleX(2); /* Double width */
    transform: scaleY(0.5); /* Half height */
    transform: scale(2, 0.5); /* X and Y separately */
}
```

#### Rotate

```css
.element {
    transform: rotate(45deg); /* Rotate 45 degrees clockwise */
    transform: rotate(-45deg); /* Rotate 45 degrees counter-clockwise */
    transform: rotate(1turn); /* Full rotation (360deg) */
}
```

#### Skew

```css
.element {
    transform: skewX(20deg); /* Skew horizontally */
    transform: skewY(10deg); /* Skew vertically */
    transform: skew(20deg, 10deg); /* X and Y */
}
```

### Combining Transforms

```css
.element {
    transform: translate(50px, 50px) rotate(45deg) scale(1.2);
}
```

**Important:** Order matters! Transform functions are applied from right to left.

### Transform Origin

Sets the point around which transforms occur:

```css
.element {
    transform-origin: center; /* Default */
    transform-origin: top left;
    transform-origin: 50% 50%;
    transform-origin: 0 0; /* Top-left corner */
}
```

### 3D Transforms

```css
.element {
    transform: perspective(1000px) rotateY(45deg);
    transform: translateZ(50px);
    transform: rotateX(45deg);
    transform-style: preserve-3d; /* For 3D children */
}
```

---

## 8. Advanced Selectors

### Attribute Selectors (Advanced)

```css
/* Attribute exists */
a[href] { }

/* Attribute equals value */
input[type="text"] { }

/* Attribute contains value */
a[href*="example"] { }

/* Attribute starts with value */
a[href^="https"] { }

/* Attribute ends with value */
a[href$=".pdf"] { }

/* Attribute contains word (space-separated) */
a[rel~="nofollow"] { }

/* Attribute starts with value or value- */
a[class|="btn"] { } /* Matches "btn" or "btn-primary" */
```

### Pseudo-classes (Advanced)

```css
/* First child */
li:first-child { }

/* Last child */
li:last-child { }

/* Only child */
p:only-child { }

/* nth-child */
li:nth-child(2) { } /* 2nd child */
li:nth-child(even) { } /* Even children */
li:nth-child(odd) { } /* Odd children */
li:nth-child(3n) { } /* Every 3rd child */
li:nth-child(3n+1) { } /* 1st, 4th, 7th, etc. */

/* nth-of-type */
p:nth-of-type(2) { } /* 2nd paragraph */

/* First of type */
p:first-of-type { }

/* Last of type */
p:last-of-type { }

/* Only of type */
p:only-of-type { }

/* Empty */
div:empty { }

/* Not */
:not(.special) { } /* Everything except .special */
:not(p) { } /* Everything except paragraphs */
```

### Pseudo-elements (Advanced)

```css
/* Before and After */
.element::before {
    content: "";
    /* Must have content property, even if empty string */
}

.element::after {
    content: "→";
}

/* Selection */
::selection {
    background-color: yellow;
    color: black;
}

/* First line and letter (covered in basics) */
p::first-line { }
p::first-letter { }
```

### Combinators (Review)

```css
/* Descendant */
div p { }

/* Child */
div > p { }

/* Adjacent sibling */
h2 + p { }

/* General sibling */
h2 ~ p { }
```

---

## 9. Pseudo-classes and Pseudo-elements Deep Dive

### Form Pseudo-classes

```css
/* Focused input */
input:focus { }

/* Checked checkbox/radio */
input:checked { }

/* Disabled */
input:disabled { }

/* Enabled */
input:enabled { }

/* Required */
input:required { }

/* Optional */
input:optional { }

/* Valid (matches pattern, etc.) */
input:valid { }

/* Invalid */
input:invalid { }

/* In-range (for number inputs) */
input:in-range { }

/* Out-of-range */
input:out-of-range { }
```

### Link and Interaction Pseudo-classes

```css
/* Unvisited link */
a:link { }

/* Visited link */
a:visited { }

/* Hover */
a:hover { }

/* Active (while clicking) */
a:active { }

/* Focus */
a:focus { }

/* Target (when URL has #anchor) */
:target { }
```

### Language Pseudo-class

```css
p:lang(en) { } /* Paragraphs in English */
p:lang(fr) { } /* Paragraphs in French */
```

---

## 10. CSS Architecture and Methodology

### BEM (Block Element Modifier)

Naming convention for CSS classes:

```css
/* Block */
.button { }

/* Element (part of block) */
.button__icon { }
.button__text { }

/* Modifier (variant of block or element) */
.button--primary { }
.button--large { }
.button__icon--left { }
```

**HTML:**
```html
<button class="button button--primary">
    <span class="button__icon button__icon--left">→</span>
    <span class="button__text">Click Me</span>
</button>
```

### SMACSS (Scalable and Modular Architecture)

Organize CSS into categories:
- Base (defaults)
- Layout (major components)
- Module (reusable components)
- State (states like .is-active)
- Theme (colors, typography)

### OOCSS (Object-Oriented CSS)

Separate structure from skin:

```css
/* Structure */
.button {
    padding: 10px 20px;
    border-radius: 4px;
}

/* Skin */
.button-primary {
    background-color: blue;
    color: white;
}
```

---

## 11. Advanced Techniques

### Calc()

Perform calculations in CSS:

```css
.element {
    width: calc(100% - 50px);
    height: calc(100vh - 100px);
    margin: calc(20px + 10px);
}
```

### Clamp()

Clamp a value between minimum and maximum:

```css
.element {
    font-size: clamp(16px, 4vw, 24px);
    /* Minimum 16px, preferred 4vw, maximum 24px */
    width: clamp(200px, 50%, 800px);
}
```

### Min() and Max()

```css
.element {
    width: min(100%, 800px); /* Smaller value */
    width: max(300px, 50%); /* Larger value */
}
```

### Aspect Ratio

Maintain aspect ratio:

```css
.video-container {
    aspect-ratio: 16 / 9;
    width: 100%;
}
```

### CSS Filters

Apply visual effects:

```css
.image {
    filter: blur(5px);
    filter: brightness(1.5);
    filter: contrast(1.2);
    filter: grayscale(100%);
    filter: hue-rotate(90deg);
    filter: invert(100%);
    filter: opacity(0.5);
    filter: saturate(200%);
    filter: sepia(100%);
    
    /* Multiple filters */
    filter: blur(2px) brightness(1.2) contrast(1.1);
}
```

### Backdrop Filter

Apply filters to background:

```css
.modal {
    backdrop-filter: blur(10px);
    backdrop-filter: brightness(0.8);
}
```

---

## 12. Performance Optimization

### Use Efficient Selectors

```css
/* Good - specific */
.button-primary { }

/* Bad - too specific */
div.container div.row div.col button.button-primary { }
```

### Avoid Over-qualified Selectors

```css
/* Good */
.button { }

/* Bad */
div.button { }
```

### Minimize Reflows and Repaints

Use transforms and opacity for animations (they're GPU-accelerated):

```css
/* Good */
.element {
    transform: translateX(100px);
    opacity: 0.5;
}

/* Bad */
.element {
    left: 100px; /* Causes reflow */
    visibility: hidden; /* Causes repaint */
}
```

### Use Will-Change Sparingly

```css
.animated-element {
    will-change: transform; /* Hint browser to optimize */
}

/* Remove after animation */
.animated-element.animation-complete {
    will-change: auto;
}
```

### Critical CSS

Inline critical CSS in `<head>` for above-the-fold content.

### Minify CSS

Remove whitespace and comments for production.

---

## Summary

You've now learned:
- Flexbox and Grid for modern layouts
- Responsive design with media queries
- CSS variables for theming
- Transitions and animations
- Advanced selectors and pseudo-classes
- Performance optimization techniques

**Next Steps:**
- Practice building complex layouts
- Learn CSS preprocessors (SASS/SCSS)
- Study CSS frameworks (Bootstrap, Tailwind)
- Build responsive projects
- Master CSS architecture patterns

---

*CSS mastery comes from building real projects. Keep practicing and experimenting!*


# HTML Advanced - Complete Guide
## Intermediate to Advanced Level

---

## Table of Contents
1. [HTML5 New Features](#html5-new-features)
2. [Advanced Form Features](#advanced-form-features)
3. [HTML5 Semantic Elements Deep Dive](#html5-semantic-elements-deep-dive)
4. [Multimedia Elements](#multimedia-elements)
5. [Embedding Content](#embedding-content)
6. [Data Attributes](#data-attributes)
7. [HTML Entities and Special Characters](#html-entities-and-special-characters)
8. [Meta Tags and SEO](#meta-tags-and-seo)
9. [Accessibility (ARIA)](#accessibility-aria)
10. [Performance Optimization](#performance-optimization)
11. [HTML APIs](#html-apis)
12. [Best Practices](#best-practices)

---

## 1. HTML5 New Features

### What Changed in HTML5?

HTML5 introduced many new elements and APIs. Let's explore the most important ones:

### New Semantic Elements

HTML5 added several semantic elements that make code more meaningful:

```html
<header>    <!-- Site header -->
<nav>       <!-- Navigation -->
<main>      <!-- Main content -->
<article>   <!-- Article content -->
<section>   <!-- Section of content -->
<aside>     <!-- Sidebar -->
<footer>    <!-- Site footer -->
<figure>    <!-- Self-contained content (images, diagrams) -->
<figcaption> <!-- Caption for figure -->
<mark>      <!-- Highlighted text -->
<time>      <!-- Date/time -->
<details>   <!-- Collapsible content -->
<summary>   <!-- Summary for details -->
```

### Figure and Figcaption

Perfect for images with captions:

```html
<figure>
    <img src="chart.png" alt="Sales chart showing growth">
    <figcaption>Figure 1: Sales growth over the past year</figcaption>
</figure>
```

**Why use it:**
- Semantically links image and caption
- Better for screen readers
- Better for search engines

### Time Element

Properly mark up dates and times:

```html
<p>Published on <time datetime="2024-01-15">January 15, 2024</time></p>
<p>Event starts at <time datetime="2024-02-20T19:00">7:00 PM on February 20</time></p>
```

**Attributes:**
- `datetime`: Machine-readable date/time (ISO 8601 format)
- Content: Human-readable date/time

**Why important:**
- Search engines understand dates
- Can be used for calendar applications
- Screen readers can announce dates properly

### Details and Summary

Create collapsible content sections:

```html
<details>
    <summary>Click to expand</summary>
    <p>This content is hidden by default and can be toggled.</p>
    <p>More content here...</p>
</details>
```

**Use cases:**
- FAQ sections
- Expandable help text
- Show/hide additional information

---

## 2. Advanced Form Features

### New Input Types

HTML5 introduced many new input types that provide better validation and user experience:

```html
<!-- Color picker -->
<label for="color">Choose a color:</label>
<input type="color" id="color" name="color" value="#ff0000">

<!-- Date picker -->
<label for="date">Select date:</label>
<input type="date" id="date" name="date">

<!-- Date and time -->
<label for="datetime">Date and time:</label>
<input type="datetime-local" id="datetime" name="datetime">

<!-- Month picker -->
<label for="month">Select month:</label>
<input type="month" id="month" name="month">

<!-- Week picker -->
<label for="week">Select week:</label>
<input type="week" id="week" name="week">

<!-- Time picker -->
<label for="time">Select time:</label>
<input type="time" id="time" name="time">

<!-- Search box (styled differently on some browsers) -->
<label for="search">Search:</label>
<input type="search" id="search" name="search">

<!-- URL (validates URL format) -->
<label for="website">Website:</label>
<input type="url" id="website" name="website">

<!-- Telephone -->
<label for="phone">Phone:</label>
<input type="tel" id="phone" name="phone">
```

### Form Validation Attributes

#### Required Attribute

```html
<input type="text" name="username" required>
```

**What it does:**
- Prevents form submission if field is empty
- Browser shows error message
- Can be overridden with CSS `:invalid` pseudo-class

#### Pattern Attribute

Validates input against a regular expression:

```html
<!-- Only numbers -->
<input type="text" pattern="[0-9]+" title="Numbers only">

<!-- Phone number format -->
<input type="tel" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" 
       title="Format: 123-456-7890">

<!-- Password: at least 8 characters, one uppercase, one lowercase, one number -->
<input type="password" 
       pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
       title="Must contain at least 8 characters, one uppercase, one lowercase, and one number">
```

**Explanation:**
- `pattern`: Regular expression pattern
- `title`: Message shown when validation fails

#### Min, Max, and Step (for numbers)

```html
<!-- Age: between 18 and 100 -->
<input type="number" name="age" min="18" max="100">

<!-- Quantity: 0 to 10, steps of 2 -->
<input type="number" name="quantity" min="0" max="10" step="2">

<!-- Date: no dates before today -->
<input type="date" name="event-date" min="2024-01-01">
```

#### Minlength and Maxlength

```html
<!-- Username: 5 to 20 characters -->
<input type="text" name="username" minlength="5" maxlength="20">

<!-- Message: up to 500 characters -->
<textarea name="message" maxlength="500"></textarea>
```

### Form Attributes

#### Autocomplete

Helps browsers suggest values:

```html
<input type="text" name="name" autocomplete="name">
<input type="email" name="email" autocomplete="email">
<input type="tel" name="phone" autocomplete="tel">
<input type="address-line1" name="address" autocomplete="street-address">
```

**Common values:**
- `name`, `email`, `tel`, `address-line1`, `address-line2`
- `city`, `country`, `postal-code`
- `username`, `current-password`, `new-password`

#### Placeholder

Hint text shown in empty fields:

```html
<input type="email" name="email" placeholder="your.email@example.com">
```

**Important:** Placeholder is NOT a substitute for labels! Always use `<label>` tags.

#### Autofocus

Automatically focuses field when page loads:

```html
<input type="text" name="search" autofocus>
```

**Use carefully:** Only one autofocus per page, and consider accessibility.

#### Disabled and Readonly

```html
<!-- Disabled: can't interact, value not submitted -->
<input type="text" name="username" value="admin" disabled>

<!-- Readonly: can't edit, but value IS submitted -->
<input type="text" name="user-id" value="12345" readonly>
```

### Datalist Element

Provides autocomplete suggestions:

```html
<label for="browser">Choose a browser:</label>
<input list="browsers" id="browser" name="browser">

<datalist id="browsers">
    <option value="Chrome">
    <option value="Firefox">
    <option value="Safari">
    <option value="Edge">
    <option value="Opera">
</datalist>
```

**How it works:**
- `input` has `list` attribute matching `datalist` id
- Users can type or select from suggestions
- Unlike `<select>`, users can enter custom values

### Output Element

Displays calculation results:

```html
<form oninput="result.value = parseInt(a.value) + parseInt(b.value)">
    <input type="number" id="a" value="10"> +
    <input type="number" id="b" value="20"> =
    <output name="result" for="a b">30</output>
</form>
```

---

## 3. HTML5 Semantic Elements Deep Dive

### Main Element

```html
<main>
    <!-- Primary content of the page -->
    <!-- Only one <main> per page -->
    <!-- Should not be inside <article>, <aside>, <footer>, <header>, or <nav> -->
</main>
```

**Rules:**
- Only ONE `<main>` per page
- Must be unique (not repeated)
- Should contain the main content area

### Article vs Section

**Article:** Self-contained, independently distributable content
```html
<article>
    <header>
        <h2>Blog Post Title</h2>
        <p>By John Doe</p>
    </header>
    <p>Article content...</p>
    <footer>
        <p>Published on January 15, 2024</p>
    </footer>
</article>
```

**Section:** Thematic grouping of content
```html
<section>
    <h2>Introduction</h2>
    <p>Content about the introduction...</p>
</section>

<section>
    <h2>Main Content</h2>
    <p>Content about the main topic...</p>
</section>
```

**Rule of thumb:**
- If content makes sense on its own → use `<article>`
- If content is part of a larger whole → use `<section>`

### Navigation Element

```html
<nav>
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>
```

**Not every link group needs `<nav>`:**
- Main site navigation → yes
- Footer links → optional (can be in footer)
- Social media links → no (use regular links)
- Table of contents → yes

---

## 4. Multimedia Elements

### Advanced Video Attributes

```html
<video 
    src="video.mp4" 
    controls 
    autoplay 
    loop 
    muted 
    poster="thumbnail.jpg"
    preload="metadata"
    width="640" 
    height="360">
    <p>Your browser doesn't support video. 
       <a href="video.mp4">Download the video</a> instead.</p>
</video>
```

**Attributes explained:**
- `controls`: Shows play/pause controls
- `autoplay`: Starts playing automatically (works only if `muted` is also set)
- `loop`: Video repeats when finished
- `muted`: Starts muted
- `poster`: Image shown before video plays
- `preload`: How video loads
  - `none`: Don't preload
  - `metadata`: Load metadata only
  - `auto`: Load entire video (default)

### Multiple Video Sources

Provide fallbacks for browser compatibility:

```html
<video controls>
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    <source src="video.ogv" type="video/ogg">
    <p>Your browser doesn't support HTML5 video.</p>
</video>
```

**Why important:** Different browsers support different formats.

### Track Element (Subtitles/Captions)

```html
<video controls>
    <source src="video.mp4" type="video/mp4">
    <track kind="subtitles" src="subtitles-en.vtt" srclang="en" label="English">
    <track kind="captions" src="captions-en.vtt" srclang="en" label="English">
    <track kind="subtitles" src="subtitles-es.vtt" srclang="es" label="Spanish">
</video>
```

**Track attributes:**
- `kind`: `subtitles`, `captions`, `descriptions`, `chapters`, `metadata`
- `src`: Path to WebVTT file
- `srclang`: Language code (en, es, fr, etc.)
- `label`: User-friendly label
- `default`: Set one track as default

### Iframe for Embedding

Embed external content:

```html
<!-- YouTube video -->
<iframe 
    width="560" 
    height="315" 
    src="https://www.youtube.com/embed/VIDEO_ID" 
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen>
</iframe>

<!-- Google Map -->
<iframe 
    src="https://www.google.com/maps/embed?pb=..." 
    width="600" 
    height="450" 
    style="border:0" 
    allowfullscreen>
</iframe>
```

**Security considerations:**
- `sandbox` attribute: Restricts iframe capabilities
- `allow`: Permissions API (camera, microphone, etc.)
- Always be careful embedding untrusted content

---

## 5. Embedding Content

### Object and Embed Elements

For embedding plugins and external content:

```html
<!-- PDF -->
<object data="document.pdf" type="application/pdf" width="800" height="600">
    <p>Cannot display PDF. <a href="document.pdf">Download instead</a>.</p>
</object>

<!-- Flash (legacy, rarely used now) -->
<embed src="animation.swf" type="application/x-shockwave-flash">
```

### SVG Inline

You can embed SVG directly in HTML:

```html
<svg width="100" height="100">
    <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="red" />
</svg>
```

**Advantages:**
- Can be styled with CSS
- Can be animated
- Scales perfectly
- Accessible via DOM

---

## 6. Data Attributes

Data attributes store custom data on HTML elements:

```html
<div data-user-id="12345" data-role="admin" data-last-login="2024-01-15">
    User Content
</div>
```

**Syntax:** `data-*` where `*` can be any name

**Accessing in JavaScript:**
```javascript
const element = document.querySelector('div');
const userId = element.dataset.userId; // "12345"
const role = element.dataset.role; // "admin"
```

**Use cases:**
- Store data for JavaScript
- CSS styling based on data
- Testing attributes

---

## 7. HTML Entities and Special Characters

Some characters have special meaning in HTML. Use entities to display them:

```html
<!-- Common entities -->
&lt;        <!-- < (less than) -->
&gt;        <!-- > (greater than) -->
&amp;       <!-- & (ampersand) -->
&quot;      <!-- " (double quote) -->
&apos;      <!-- ' (apostrophe) -->

<!-- Examples -->
<p>5 &lt; 10</p>              <!-- Displays: 5 < 10 -->
<p>I said &quot;Hello&quot;</p> <!-- Displays: I said "Hello" -->
<p>AT&amp;T</p>                <!-- Displays: AT&T -->
```

### Common Entities

```html
&nbsp;      <!-- Non-breaking space -->
&copy;      <!-- © (copyright) -->
&reg;       <!-- ® (registered) -->
&trade;     <!-- ™ (trademark) -->
&euro;      <!-- € (euro) -->
&pound;     <!-- £ (pound) -->
&yen;       <!-- ¥ (yen) -->
&deg;       <!-- ° (degree) -->
&plusmn;    <!-- ± (plus-minus) -->
&frac14;    <!-- ¼ -->
&frac12;    <!-- ½ -->
&frac34;    <!-- ¾ -->
```

### Numeric Character References

You can also use numeric codes:

```html
&#169;      <!-- © (decimal) -->
&#xA9;      <!-- © (hexadecimal) -->
&#128512;   <!-- 😀 (emoji) -->
```

---

## 8. Meta Tags and SEO

### Essential Meta Tags

```html
<head>
    <!-- Character encoding (MUST be first) -->
    <meta charset="UTF-8">
    
    <!-- Viewport for responsive design -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Page description (for search engines) -->
    <meta name="description" content="Brief description of your page (150-160 characters)">
    
    <!-- Keywords (less important now, but some use it) -->
    <meta name="keywords" content="keyword1, keyword2, keyword3">
    
    <!-- Author -->
    <meta name="author" content="Your Name">
    
    <!-- Robots (search engine indexing) -->
    <meta name="robots" content="index, follow">
    <!-- Options: index/noindex, follow/nofollow -->
</head>
```

### Open Graph Meta Tags (Social Media)

Make your links look good when shared on social media:

```html
<meta property="og:title" content="Your Page Title">
<meta property="og:description" content="Page description">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:url" content="https://example.com/page">
<meta property="og:type" content="website">
```

### Twitter Card Meta Tags

Similar to Open Graph, for Twitter:

```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Your Page Title">
<meta name="twitter:description" content="Page description">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

---

## 9. Accessibility (ARIA)

ARIA (Accessible Rich Internet Applications) makes web content more accessible.

### ARIA Labels

```html
<!-- Button with icon only -->
<button aria-label="Close dialog">
    <span>&times;</span>
</button>

<!-- Image with meaningful description -->
<img src="chart.png" alt="Sales chart" aria-describedby="chart-description">
<p id="chart-description">This chart shows 25% growth in Q4.</p>
```

### ARIA Roles

```html
<!-- Navigation -->
<nav role="navigation">
    <!-- ... -->
</nav>

<!-- Main content -->
<main role="main">
    <!-- ... -->
</main>

<!-- Complementary content -->
<aside role="complementary">
    <!-- ... -->
</aside>

<!-- Banner (header) -->
<header role="banner">
    <!-- ... -->
</header>

<!-- Content info (footer) -->
<footer role="contentinfo">
    <!-- ... -->
</footer>
```

### ARIA States and Properties

```html
<!-- Hidden from screen readers -->
<div aria-hidden="true">
    Decorative content
</div>

<!-- Live region (announces changes) -->
<div aria-live="polite" aria-atomic="true">
    <span id="status">Loading...</span>
</div>

<!-- Required field -->
<input type="text" aria-required="true">

<!-- Invalid field -->
<input type="email" aria-invalid="true" aria-describedby="email-error">
<span id="email-error">Please enter a valid email address</span>

<!-- Disabled -->
<button aria-disabled="true">Disabled Button</button>
```

### ARIA Landmarks

Help screen reader users navigate:

```html
<body>
    <header role="banner">
        <!-- Site header -->
    </header>
    
    <nav role="navigation">
        <!-- Main navigation -->
    </nav>
    
    <main role="main">
        <!-- Main content -->
    </main>
    
    <aside role="complementary">
        <!-- Sidebar -->
    </aside>
    
    <footer role="contentinfo">
        <!-- Site footer -->
    </footer>
</body>
```

---

## 10. Performance Optimization

### Lazy Loading Images

Load images only when needed:

```html
<img src="image.jpg" alt="Description" loading="lazy">
```

**Benefits:**
- Faster initial page load
- Saves bandwidth
- Better user experience

**Note:** Native lazy loading supported in modern browsers.

### Preconnect and DNS Prefetch

Speed up external resource loading:

```html
<!-- Preconnect to external domain -->
<link rel="preconnect" href="https://fonts.googleapis.com">

<!-- DNS prefetch (lighter than preconnect) -->
<link rel="dns-prefetch" href="https://cdn.example.com">
```

### Preload Critical Resources

```html
<!-- Preload critical CSS -->
<link rel="preload" href="styles.css" as="style">

<!-- Preload critical font -->
<link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>

<!-- Preload critical JavaScript -->
<link rel="preload" href="script.js" as="script">
```

### Defer and Async Scripts

```html
<!-- Normal (blocks HTML parsing) -->
<script src="script.js"></script>

<!-- Async (downloads parallel, executes immediately) -->
<script src="script.js" async></script>

<!-- Defer (downloads parallel, executes after HTML parsing) -->
<script src="script.js" defer></script>
```

**When to use:**
- `async`: For independent scripts (analytics, ads)
- `defer`: For scripts that depend on DOM (preferred)

---

## 11. HTML APIs

### Geolocation API

```html
<button onclick="getLocation()">Get Location</button>
<p id="location"></p>

<script>
function getLocation() {
    if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(showPosition);
    } else {
        document.getElementById("location").innerHTML = 
            "Geolocation is not supported.";
    }
}

function showPosition(position) {
    document.getElementById("location").innerHTML = 
        "Latitude: " + position.coords.latitude + 
        "<br>Longitude: " + position.coords.longitude;
}
</script>
```

### Local Storage

Store data in browser:

```html
<script>
// Store data
localStorage.setItem('username', 'John');

// Retrieve data
const username = localStorage.getItem('username');

// Remove data
localStorage.removeItem('username');

// Clear all
localStorage.clear();
</script>
```

### Session Storage

Similar to localStorage, but cleared when tab closes:

```html
<script>
sessionStorage.setItem('tempData', 'value');
const data = sessionStorage.getItem('tempData');
</script>
```

### Canvas API (Basic)

```html
<canvas id="myCanvas" width="200" height="100"></canvas>

<script>
const canvas = document.getElementById('myCanvas');
const ctx = canvas.getContext('2d');
ctx.fillStyle = 'red';
ctx.fillRect(10, 10, 50, 50);
</script>
```

---

## 12. Best Practices

### Code Organization

1. **Indentation:** Use consistent indentation (2 or 4 spaces)
2. **Comments:** Add comments for complex sections
3. **Naming:** Use descriptive IDs and classes
4. **Structure:** Follow semantic HTML structure

### Validation

Always validate your HTML:
- W3C Markup Validator: https://validator.w3.org/
- Fix all errors and warnings

### Accessibility Checklist

- [ ] All images have alt text
- [ ] Forms have proper labels
- [ ] Use semantic HTML elements
- [ ] Ensure keyboard navigation works
- [ ] Use ARIA attributes where needed
- [ ] Test with screen reader

### Performance Checklist

- [ ] Optimize images (compress, use correct format)
- [ ] Use lazy loading for images
- [ ] Minimize HTML size
- [ ] Use semantic HTML (reduces CSS needed)
- [ ] Add preconnect for external resources

### Security Checklist

- [ ] Never trust user input
- [ ] Escape special characters
- [ ] Use HTTPS
- [ ] Validate forms on server-side too
- [ ] Be careful with iframes

---

## Summary

You've now learned:
- HTML5 new features and semantic elements
- Advanced form validation and input types
- Multimedia embedding techniques
- Accessibility with ARIA
- Performance optimization techniques
- HTML APIs basics

**Next Steps:**
- Practice building complex forms
- Learn CSS for styling
- Study JavaScript for interactivity
- Practice accessibility techniques
- Build real-world projects

---

*Mastery comes from practice. Build projects, experiment, and keep learning!*


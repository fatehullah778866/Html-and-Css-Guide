# HTML & CSS Projects - Complete Implementation Guide
## From Simple to Intermediate Level Projects

---

## Table of Contents
1. [Introduction](#introduction)
2. [Step 1: Simple Projects (Beginner Level)](#step-1-simple-projects-beginner-level)
3. [Step 2: Intermediate Projects (Building Skills)](#step-2-intermediate-projects-building-skills)
4. [Step 3: Advanced Intermediate Projects (Combining Concepts)](#step-3-advanced-intermediate-projects-combining-concepts)
5. [Best Practices and Tips](#best-practices-and-tips)
6. [Troubleshooting Common Issues](#troubleshooting-common-issues)

---

## Introduction

### What This Guide Covers

This guide takes you through **real-world projects** that combine HTML and CSS. You'll learn by building actual websites, starting from simple projects and progressing to intermediate-level applications.

### Prerequisites

Before starting, you should have:
- Basic understanding of HTML structure and elements
- Basic understanding of CSS (selectors, properties, box model)
- A code editor (VS Code recommended)
- A web browser (Chrome, Firefox, or Edge)

### How to Use This Guide

1. **Read each step carefully** - Don't skip ahead
2. **Type out all code** - Don't copy-paste; typing helps you learn
3. **Test frequently** - Open your HTML file in a browser after each major change
4. **Experiment** - Try changing values and see what happens
5. **Complete each project** - Finish one before moving to the next

### Project Structure

Each project includes:
- **Project Overview** - What we're building and why
- **Step-by-Step Instructions** - Detailed breakdown
- **Line-by-Line Code Explanation** - Understanding every part
- **Final Code** - Complete working example
- **Challenges** - Optional improvements to try

---

## Step 1: Simple Projects (Beginner Level)

In this step, we'll build **3 simple projects** that teach you the fundamentals of combining HTML and CSS:

1. **Personal Profile Card** - Your first styled component
2. **Simple Landing Page** - Building a complete page
3. **Product Card** - Reusable component design

Let's start with the first project!

---

### Project 1.1: Personal Profile Card

#### Project Overview

We're building a **Personal Profile Card** - a simple, beautiful card that displays personal information. This project teaches you:
- Basic HTML structure
- CSS styling fundamentals
- Box model (padding, margin, border)
- Colors and typography
- Centering elements

#### What You'll Learn

- Creating semantic HTML structure
- Using CSS classes and IDs
- Styling with colors, fonts, and spacing
- Understanding the box model
- Creating rounded corners and shadows

#### Step-by-Step Implementation

**Step 1: Create the HTML File**

Create a new file called `profile-card.html` in your project folder.

**Step 2: Set Up Basic HTML Structure**

Let's start with the basic HTML document structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Personal Profile Card</title>
</head>
<body>
    
</body>
</html>
```

**Line-by-Line Explanation:**

- `<!DOCTYPE html>` - Tells the browser this is an HTML5 document
- `<html lang="en">` - Root element, `lang="en"` specifies English language
- `<head>` - Contains metadata (information about the page, not visible content)
- `<meta charset="UTF-8">` - Sets character encoding to support all characters
- `<meta name="viewport"...>` - Makes the page responsive on mobile devices
- `<title>` - Text that appears in the browser tab
- `<body>` - Contains all visible content

**Step 3: Add the Card Structure**

Inside the `<body>` tag, add the card structure:

```html
<body>
    <div class="card">
        <div class="card-header">
            <img src="https://via.placeholder.com/150" alt="Profile Picture" class="profile-img">
        </div>
        <div class="card-body">
            <h2 class="name">John Doe</h2>
            <p class="title">Web Developer</p>
            <p class="description">Passionate about creating beautiful and functional websites.</p>
            <div class="social-links">
                <a href="#" class="social-link">LinkedIn</a>
                <a href="#" class="social-link">GitHub</a>
                <a href="#" class="social-link">Twitter</a>
            </div>
        </div>
    </div>
</body>
```

**Line-by-Line Explanation:**

- `<div class="card">` - Main container for the entire card
  - `class="card"` - CSS class name we'll use for styling
- `<div class="card-header">` - Top section of the card (for the image)
- `<img src="..." alt="...">` - Profile picture
  - `src` - Image source URL (using placeholder for now)
  - `alt` - Alternative text for accessibility
  - `class="profile-img"` - CSS class for styling the image
- `<div class="card-body">` - Main content section
- `<h2 class="name">` - Name heading (h2 is a semantic heading tag)
- `<p class="title">` - Job title paragraph
- `<p class="description">` - Description paragraph
- `<div class="social-links">` - Container for social media links
- `<a href="#" class="social-link">` - Individual social link
  - `href="#"` - Link destination (# means same page, placeholder)
  - `class="social-link"` - CSS class for styling links

**Step 4: Add Internal CSS**

Now let's add CSS styling. We'll use internal CSS (inside `<style>` tag in the `<head>`) for this simple project:

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Personal Profile Card</title>
    <style>
        /* Reset default browser styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }
        
        .card {
            background-color: white;
            border-radius: 15px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 350px;
            overflow: hidden;
        }
        
        .card-header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 30px;
            text-align: center;
        }
        
        .profile-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            border: 5px solid white;
            object-fit: cover;
        }
        
        .card-body {
            padding: 30px;
            text-align: center;
        }
        
        .name {
            color: #333;
            font-size: 24px;
            margin-bottom: 10px;
        }
        
        .title {
            color: #667eea;
            font-size: 16px;
            font-weight: 600;
            margin-bottom: 15px;
        }
        
        .description {
            color: #666;
            font-size: 14px;
            line-height: 1.6;
            margin-bottom: 25px;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
        }
        
        .social-link {
            color: white;
            background-color: #667eea;
            padding: 10px 20px;
            border-radius: 25px;
            text-decoration: none;
            font-size: 14px;
            transition: background-color 0.3s ease;
        }
        
        .social-link:hover {
            background-color: #764ba2;
        }
    </style>
</head>
```

**Line-by-Line CSS Explanation:**

**Universal Reset:**
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```
- `*` - Universal selector (targets all elements)
- `margin: 0` - Removes default margins
- `padding: 0` - Removes default padding
- `box-sizing: border-box` - Makes width/height include padding and border (easier sizing)

**Body Styling:**
```css
body {
    font-family: 'Arial', sans-serif;
    background-color: #f0f0f0;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    padding: 20px;
}
```
- `font-family` - Sets the font (Arial, with sans-serif fallback)
- `background-color` - Light gray background (#f0f0f0)
- `display: flex` - Makes body a flex container
- `justify-content: center` - Centers content horizontally
- `align-items: center` - Centers content vertically
- `min-height: 100vh` - Minimum height is 100% of viewport height (full screen)
- `padding: 20px` - Adds space around content on small screens

**Card Container:**
```css
.card {
    background-color: white;
    border-radius: 15px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    width: 100%;
    max-width: 350px;
    overflow: hidden;
}
```
- `background-color: white` - White card background
- `border-radius: 15px` - Rounds the corners (15px radius)
- `box-shadow` - Adds shadow for depth
  - `0 4px 6px` - Shadow offset (x, y, blur)
  - `rgba(0, 0, 0, 0.1)` - Shadow color (black with 10% opacity)
- `width: 100%` - Full width on small screens
- `max-width: 350px` - Maximum width of 350px
- `overflow: hidden` - Hides content that overflows (keeps rounded corners clean)

**Card Header:**
```css
.card-header {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    padding: 30px;
    text-align: center;
}
```
- `background: linear-gradient(...)` - Creates a gradient background
  - `135deg` - Gradient angle (diagonal)
  - `#667eea` - Starting color (purple-blue)
  - `#764ba2` - Ending color (purple)
- `padding: 30px` - Space inside the header
- `text-align: center` - Centers content horizontally

**Profile Image:**
```css
.profile-img {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    border: 5px solid white;
    object-fit: cover;
}
```
- `width: 120px` - Image width
- `height: 120px` - Image height (makes it square)
- `border-radius: 50%` - Makes it circular (50% of width/height)
- `border: 5px solid white` - White border around image
- `object-fit: cover` - Ensures image covers the area without distortion

**Card Body:**
```css
.card-body {
    padding: 30px;
    text-align: center;
}
```
- `padding: 30px` - Space inside the body
- `text-align: center` - Centers all text

**Name Styling:**
```css
.name {
    color: #333;
    font-size: 24px;
    margin-bottom: 10px;
}
```
- `color: #333` - Dark gray text color
- `font-size: 24px` - Large font size
- `margin-bottom: 10px` - Space below the name

**Title Styling:**
```css
.title {
    color: #667eea;
    font-size: 16px;
    font-weight: 600;
    margin-bottom: 15px;
}
```
- `color: #667eea` - Purple color matching the gradient
- `font-size: 16px` - Medium font size
- `font-weight: 600` - Semi-bold text
- `margin-bottom: 15px` - Space below the title

**Description:**
```css
.description {
    color: #666;
    font-size: 14px;
    line-height: 1.6;
    margin-bottom: 25px;
}
```
- `color: #666` - Medium gray for less emphasis
- `font-size: 14px` - Smaller font size
- `line-height: 1.6` - Space between lines (improves readability)
- `margin-bottom: 25px` - Space below description

**Social Links Container:**
```css
.social-links {
    display: flex;
    justify-content: center;
    gap: 15px;
}
```
- `display: flex` - Makes it a flex container
- `justify-content: center` - Centers the links
- `gap: 15px` - Space between links (modern CSS, replaces margin)

**Social Link Buttons:**
```css
.social-link {
    color: white;
    background-color: #667eea;
    padding: 10px 20px;
    border-radius: 25px;
    text-decoration: none;
    font-size: 14px;
    transition: background-color 0.3s ease;
}
```
- `color: white` - White text
- `background-color: #667eea` - Purple background
- `padding: 10px 20px` - Vertical and horizontal padding (makes it button-like)
- `border-radius: 25px` - Very rounded corners (pill shape)
- `text-decoration: none` - Removes underline from links
- `font-size: 14px` - Button text size
- `transition: background-color 0.3s ease` - Smooth color change on hover

**Hover Effect:**
```css
.social-link:hover {
    background-color: #764ba2;
}
```
- `:hover` - Pseudo-class (applies when mouse hovers)
- Changes background to darker purple on hover

#### Complete Code

Here's the complete `profile-card.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Personal Profile Card</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }
        
        .card {
            background-color: white;
            border-radius: 15px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 350px;
            overflow: hidden;
        }
        
        .card-header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 30px;
            text-align: center;
        }
        
        .profile-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            border: 5px solid white;
            object-fit: cover;
        }
        
        .card-body {
            padding: 30px;
            text-align: center;
        }
        
        .name {
            color: #333;
            font-size: 24px;
            margin-bottom: 10px;
        }
        
        .title {
            color: #667eea;
            font-size: 16px;
            font-weight: 600;
            margin-bottom: 15px;
        }
        
        .description {
            color: #666;
            font-size: 14px;
            line-height: 1.6;
            margin-bottom: 25px;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
        }
        
        .social-link {
            color: white;
            background-color: #667eea;
            padding: 10px 20px;
            border-radius: 25px;
            text-decoration: none;
            font-size: 14px;
            transition: background-color 0.3s ease;
        }
        
        .social-link:hover {
            background-color: #764ba2;
        }
    </style>
</head>
<body>
    <div class="card">
        <div class="card-header">
            <img src="https://via.placeholder.com/150" alt="Profile Picture" class="profile-img">
        </div>
        <div class="card-body">
            <h2 class="name">John Doe</h2>
            <p class="title">Web Developer</p>
            <p class="description">Passionate about creating beautiful and functional websites.</p>
            <div class="social-links">
                <a href="#" class="social-link">LinkedIn</a>
                <a href="#" class="social-link">GitHub</a>
                <a href="#" class="social-link">Twitter</a>
            </div>
        </div>
    </div>
</body>
</html>
```

#### Testing Your Card

1. **Save the file** as `profile-card.html`
2. **Open it in a browser** - Double-click the file or right-click → Open with → Browser
3. **Check the result** - You should see a centered card with a gradient header, profile image, and social links

#### What You've Learned

✅ Created semantic HTML structure  
✅ Used CSS classes for styling  
✅ Applied the box model (padding, margin)  
✅ Used colors and typography  
✅ Created rounded corners and shadows  
✅ Centered elements with Flexbox  
✅ Added hover effects  

#### Challenge Exercises

Try these improvements:

1. **Change the colors** - Use your favorite color scheme
2. **Add more information** - Email, phone number, location
3. **Change the layout** - Put image on the side instead of top
4. **Add animations** - Make the card fade in when page loads
5. **Make it responsive** - Adjust sizes for mobile devices

---

### Project 1.2: Simple Landing Page

#### Project Overview

We're building a **Simple Landing Page** - a complete webpage with header, hero section, features, and footer. This project teaches you:
- Multi-section page layout
- Navigation bar
- Hero section design
- Feature cards
- Footer design
- Responsive basics

#### What You'll Learn

- Structuring a complete webpage
- Creating navigation menus
- Hero sections with call-to-action
- Grid/Flexbox layouts
- Footer design
- Basic responsive design

#### Step-by-Step Implementation

**Step 1: Create the HTML File**

Create `landing-page.html`

**Step 2: HTML Structure**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Landing Page</title>
    <style>
        /* CSS will go here */
    </style>
</head>
<body>
    <!-- Header/Navigation -->
    <header class="header">
        <nav class="navbar">
            <div class="logo">MyBrand</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Welcome to Our Amazing Product</h1>
            <p>Discover the future of web development with our innovative solutions.</p>
            <button class="cta-button">Get Started</button>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <h2>Our Features</h2>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">🚀</div>
                <h3>Fast Performance</h3>
                <p>Lightning-fast loading times for the best user experience.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🔒</div>
                <h3>Secure</h3>
                <p>Your data is protected with enterprise-grade security.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">📱</div>
                <h3>Responsive</h3>
                <p>Works perfectly on all devices, from mobile to desktop.</p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <p>&copy; 2024 MyBrand. All rights reserved.</p>
    </footer>
</body>
</html>
```

**Line-by-Line HTML Explanation:**

**Header Section:**
```html
<header class="header">
```
- `<header>` - Semantic HTML5 element for page header
- `class="header"` - CSS class for styling

```html
<nav class="navbar">
```
- `<nav>` - Semantic element for navigation
- `class="navbar"` - CSS class for navigation bar

```html
<div class="logo">MyBrand</div>
```
- Logo container (could be an image or text)

```html
<ul class="nav-links">
    <li><a href="#home">Home</a></li>
```
- `<ul>` - Unordered list for navigation items
- `<li>` - List item
- `<a href="#home">` - Anchor link (hash # links to section with id="home")

**Hero Section:**
```html
<section class="hero" id="home">
```
- `<section>` - Semantic element for page sections
- `id="home"` - ID for anchor link navigation

```html
<button class="cta-button">Get Started</button>
```
- `<button>` - Button element for call-to-action
- `class="cta-button"` - CSS class (CTA = Call To Action)

**Features Section:**
```html
<div class="features-grid">
```
- Container for feature cards in a grid layout

```html
<div class="feature-icon">🚀</div>
```
- Icon container (using emoji, could be image or icon font)

**Step 3: Add CSS Styling**

```html
<style>
    /* Reset */
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: 'Arial', sans-serif;
        line-height: 1.6;
        color: #333;
    }

    /* Header */
    .header {
        background-color: #2c3e50;
        color: white;
        padding: 1rem 0;
        position: sticky;
        top: 0;
        z-index: 100;
    }

    .navbar {
        max-width: 1200px;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 20px;
    }

    .logo {
        font-size: 24px;
        font-weight: bold;
    }

    .nav-links {
        display: flex;
        list-style: none;
        gap: 30px;
    }

    .nav-links a {
        color: white;
        text-decoration: none;
        transition: color 0.3s;
    }

    .nav-links a:hover {
        color: #3498db;
    }

    /* Hero Section */
    .hero {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: white;
        padding: 100px 20px;
        text-align: center;
    }

    .hero-content {
        max-width: 800px;
        margin: 0 auto;
    }

    .hero h1 {
        font-size: 48px;
        margin-bottom: 20px;
    }

    .hero p {
        font-size: 20px;
        margin-bottom: 30px;
    }

    .cta-button {
        background-color: white;
        color: #667eea;
        padding: 15px 40px;
        border: none;
        border-radius: 30px;
        font-size: 18px;
        font-weight: bold;
        cursor: pointer;
        transition: transform 0.3s;
    }

    .cta-button:hover {
        transform: scale(1.05);
    }

    /* Features Section */
    .features {
        padding: 80px 20px;
        max-width: 1200px;
        margin: 0 auto;
    }

    .features h2 {
        text-align: center;
        font-size: 36px;
        margin-bottom: 50px;
    }

    .features-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 30px;
    }

    .feature-card {
        background-color: #f8f9fa;
        padding: 40px;
        border-radius: 10px;
        text-align: center;
        transition: transform 0.3s;
    }

    .feature-card:hover {
        transform: translateY(-5px);
    }

    .feature-icon {
        font-size: 48px;
        margin-bottom: 20px;
    }

    .feature-card h3 {
        font-size: 24px;
        margin-bottom: 15px;
    }

    .feature-card p {
        color: #666;
    }

    /* Footer */
    .footer {
        background-color: #2c3e50;
        color: white;
        text-align: center;
        padding: 30px;
    }
</style>
```

**Line-by-Line CSS Explanation:**

**Header Styling:**
```css
.header {
    background-color: #2c3e50;
    color: white;
    padding: 1rem 0;
    position: sticky;
    top: 0;
    z-index: 100;
}
```
- `background-color: #2c3e50` - Dark blue-gray
- `padding: 1rem 0` - Vertical padding (1rem = 16px typically)
- `position: sticky` - Sticks to top when scrolling
- `top: 0` - Sticks at top of viewport
- `z-index: 100` - Ensures header stays above other content

**Navbar Layout:**
```css
.navbar {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
}
```
- `max-width: 1200px` - Limits width on large screens
- `margin: 0 auto` - Centers the navbar
- `display: flex` - Flexbox layout
- `justify-content: space-between` - Logo left, links right
- `align-items: center` - Vertically centers items

**Navigation Links:**
```css
.nav-links {
    display: flex;
    list-style: none;
    gap: 30px;
}
```
- `list-style: none` - Removes bullet points
- `gap: 30px` - Space between links

**Hero Section:**
```css
.hero {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    padding: 100px 20px;
    text-align: center;
}
```
- `padding: 100px 20px` - Large vertical padding for hero feel
- `text-align: center` - Centers all content

**CTA Button:**
```css
.cta-button {
    background-color: white;
    color: #667eea;
    padding: 15px 40px;
    border: none;
    border-radius: 30px;
    font-size: 18px;
    font-weight: bold;
    cursor: pointer;
    transition: transform 0.3s;
}
```
- `border: none` - Removes default button border
- `border-radius: 30px` - Rounded pill shape
- `cursor: pointer` - Shows hand cursor on hover
- `transition: transform 0.3s` - Smooth transform animation

**Features Grid:**
```css
.features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
}
```
- `display: grid` - CSS Grid layout
- `repeat(auto-fit, minmax(300px, 1fr))` - Responsive grid:
  - Creates columns that are at least 300px wide
  - Automatically fits as many as possible
  - Each column takes equal space (1fr)
- `gap: 30px` - Space between grid items

**Feature Card Hover:**
```css
.feature-card:hover {
    transform: translateY(-5px);
}
```
- `translateY(-5px)` - Moves card up 5px on hover (lift effect)

#### Complete Code

[The complete code would be the combination of HTML and CSS above]

#### Testing Your Landing Page

1. Save as `landing-page.html`
2. Open in browser
3. Test scrolling - header should stick to top
4. Hover over buttons and cards - see the effects
5. Resize browser - grid should adapt

#### What You've Learned

✅ Multi-section page structure  
✅ Sticky navigation bar  
✅ Hero section with gradient  
✅ CSS Grid for responsive layouts  
✅ Hover effects and transitions  
✅ Footer design  

#### Challenge Exercises

1. Add a contact form in a new section
2. Add more feature cards
3. Change color scheme
4. Add smooth scroll behavior
5. Make navigation mobile-friendly

---

### Project 1.3: Product Card

#### Project Overview

We're building a **Product Card** component - a reusable card for displaying products with image, title, description, price, and button. This teaches you:
- Component-based design
- Image handling
- Price display
- Button states
- Card hover effects

#### What You'll Learn

- Creating reusable components
- Image optimization concepts
- Pricing display design
- Interactive button states
- Advanced hover effects

#### Step-by-Step Implementation

**Step 1: Create HTML File**

Create `product-card.html`

**Step 2: HTML Structure**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Product Card</title>
    <style>
        /* CSS will go here */
    </style>
</head>
<body>
    <div class="container">
        <div class="product-card">
            <div class="product-image">
                <img src="https://via.placeholder.com/300x200" alt="Product Image">
                <span class="badge">New</span>
            </div>
            <div class="product-info">
                <h3 class="product-title">Wireless Headphones</h3>
                <p class="product-description">Premium quality wireless headphones with noise cancellation.</p>
                <div class="product-rating">
                    <span class="stars">★★★★★</span>
                    <span class="rating-text">(4.8)</span>
                </div>
                <div class="product-footer">
                    <div class="price">
                        <span class="current-price">$99.99</span>
                        <span class="old-price">$149.99</span>
                    </div>
                    <button class="add-to-cart">Add to Cart</button>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```

**Step 3: Add CSS**

```html
<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: 'Arial', sans-serif;
        background-color: #f5f5f5;
        padding: 50px 20px;
    }

    .container {
        max-width: 1200px;
        margin: 0 auto;
        display: flex;
        justify-content: center;
    }

    .product-card {
        background-color: white;
        border-radius: 12px;
        overflow: hidden;
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        max-width: 350px;
        transition: transform 0.3s, box-shadow 0.3s;
    }

    .product-card:hover {
        transform: translateY(-8px);
        box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
    }

    .product-image {
        position: relative;
        width: 100%;
        height: 250px;
        overflow: hidden;
    }

    .product-image img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: transform 0.3s;
    }

    .product-card:hover .product-image img {
        transform: scale(1.1);
    }

    .badge {
        position: absolute;
        top: 15px;
        right: 15px;
        background-color: #e74c3c;
        color: white;
        padding: 5px 12px;
        border-radius: 20px;
        font-size: 12px;
        font-weight: bold;
    }

    .product-info {
        padding: 25px;
    }

    .product-title {
        font-size: 22px;
        margin-bottom: 10px;
        color: #333;
    }

    .product-description {
        color: #666;
        font-size: 14px;
        line-height: 1.6;
        margin-bottom: 15px;
    }

    .product-rating {
        display: flex;
        align-items: center;
        gap: 8px;
        margin-bottom: 20px;
    }

    .stars {
        color: #ffc107;
        font-size: 18px;
    }

    .rating-text {
        color: #666;
        font-size: 14px;
    }

    .product-footer {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .price {
        display: flex;
        flex-direction: column;
    }

    .current-price {
        font-size: 28px;
        font-weight: bold;
        color: #2ecc71;
    }

    .old-price {
        font-size: 16px;
        color: #999;
        text-decoration: line-through;
    }

    .add-to-cart {
        background-color: #3498db;
        color: white;
        border: none;
        padding: 12px 30px;
        border-radius: 25px;
        font-size: 16px;
        font-weight: bold;
        cursor: pointer;
        transition: background-color 0.3s, transform 0.2s;
    }

    .add-to-cart:hover {
        background-color: #2980b9;
        transform: scale(1.05);
    }

    .add-to-cart:active {
        transform: scale(0.98);
    }
</style>
```

**Key CSS Concepts Explained:**

**Image Zoom Effect:**
```css
.product-card:hover .product-image img {
    transform: scale(1.1);
}
```
- When card is hovered, image scales to 110% (zoom effect)

**Badge Positioning:**
```css
.badge {
    position: absolute;
    top: 15px;
    right: 15px;
}
```
- `position: absolute` - Positions relative to parent (`.product-image`)
- Places badge in top-right corner

**Price Display:**
```css
.old-price {
    text-decoration: line-through;
}
```
- `line-through` - Strikes through text (shows original price)

**Button Active State:**
```css
.add-to-cart:active {
    transform: scale(0.98);
}
```
- `:active` - When button is clicked
- Slightly shrinks for tactile feedback

#### Complete Code

[Combination of HTML and CSS above]

#### Testing Your Product Card

1. Save and open in browser
2. Hover over card - should lift and image zoom
3. Hover over button - should change color
4. Click button - should slightly shrink

#### What You've Learned

✅ Component-based design  
✅ Image hover effects  
✅ Badge positioning  
✅ Price display with strikethrough  
✅ Button states (hover, active)  
✅ Card elevation effects  

#### Challenge Exercises

1. Create multiple product cards in a grid
2. Add a "Sale" badge with different color
3. Add quantity selector
4. Add favorite/heart icon
5. Create different card styles

---

## Step 2: Intermediate Projects (Building Skills)

Great job completing Step 1! 🎉 Now we're going to build bigger projects. Think of Step 1 like learning to ride a bike with training wheels. Step 2 is like taking off those training wheels - you'll use everything you learned, but make it bigger and better!

### What Makes Step 2 Different?

**Step 1 was like:** Building one toy at a time  
**Step 2 is like:** Building a whole toy box with many toys inside!

In Step 2, you'll learn:
- How to put many things together on one page
- How to make pages that work on phones AND computers
- How to organize your code better
- How to reuse the same styles for different things

---

### Project 2.1: Restaurant Menu Page

#### What Are We Building? (Like Explaining to a Friend)

Imagine you go to a restaurant. You sit down, and the waiter gives you a menu. The menu has:
- The restaurant's name at the top
- Different sections like "Appetizers", "Main Courses", "Desserts"
- Each food item with its name, description, and price

That's exactly what we're building! A beautiful menu page that a restaurant could use on their website.

#### Why Are We Building This?

**Why?** Because it teaches you:
- How to organize information in sections (like chapters in a book)
- How to make things look nice in rows and columns
- How to use colors and fonts to make it look professional
- How to make it work on phones too!

#### How Does It Work? (Super Simple Explanation)

Think of it like building with LEGO blocks:
1. **The Header** = The top block (restaurant name)
2. **Menu Sections** = Different colored blocks (Appetizers, Main Courses)
3. **Menu Items** = Small blocks inside each section (each food item)
4. **CSS** = The glue that makes everything stick together nicely

Let's build it step by step!

---

#### Step-by-Step: Building the Restaurant Menu

**Step 1: Create the HTML File**

Create a new file called `restaurant-menu.html`

**What is an HTML file?**  
Think of HTML like the skeleton of a person. It's the structure - the bones that hold everything together. Without HTML, there's nothing to show!

**Why do we need a file?**  
Just like you need a notebook to write a story, we need an HTML file to write our website!

**How do we create it?**  
1. Open your code editor (like VS Code)
2. Click "New File"
3. Save it as `restaurant-menu.html`

---

**Step 2: Write the Basic HTML Structure**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Delicious Restaurant Menu</title>
    <style>
        /* Our CSS will go here - this is where we make things pretty! */
    </style>
</head>
<body>
    <!-- This is where our menu will appear -->
</body>
</html>
```

**Line-by-Line Explanation (Like Talking to a 7-Year-Old):**

```html
<!DOCTYPE html>
```
**What?** This tells the computer: "Hey! This is an HTML file!"  
**Why?** Just like you tell your teacher your name, we tell the computer what type of file this is  
**How?** The computer reads this first and knows how to display everything

```html
<html lang="en">
```
**What?** This is like the cover of a book - it wraps everything inside  
**Why?** Everything on our webpage needs to be inside this tag  
**How?** `lang="en"` means "English" - we're telling the computer we're writing in English

```html
<head>
```
**What?** The "head" is like the brain of our webpage  
**Why?** It contains important information that the computer needs, but people don't see  
**How?** Like a secret instruction manual for the computer

```html
<meta charset="UTF-8">
```
**What?** This tells the computer what alphabet to use  
**Why?** So special characters (like é, ñ, or emojis 😊) show up correctly  
**How?** UTF-8 is like a universal translator for all languages

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
**What?** This makes our page work on phones!  
**Why?** Without this, websites look tiny on phones  
**How?** It tells phones: "Hey, make this page fit your screen!"

```html
<title>Delicious Restaurant Menu</title>
```
**What?** This is the name that appears in the browser tab  
**Why?** So people know what page they're looking at  
**How?** You'll see "Delicious Restaurant Menu" at the top of your browser

```html
<style>
```
**What?** This is where we write our CSS (the pretty colors and styles)  
**Why?** This is where we make everything look beautiful  
**How?** We'll write CSS rules inside here

```html
<body>
```
**What?** This is like the body of a person - where all the visible parts go  
**Why?** Everything people see goes inside the body  
**How?** All our menu items will go here

---

**Step 3: Add the Header (Restaurant Name)**

Inside the `<body>` tag, let's add the header:

```html
<body>
    <header class="menu-header">
        <h1>🍕 Tony's Italian Restaurant</h1>
        <p class="subtitle">Authentic Italian Cuisine Since 1985</p>
    </header>
</body>
```

**Line-by-Line Explanation:**

```html
<header class="menu-header">
```
**What?** A header is like the title page of a book  
**Why?** It's the first thing people see - it tells them where they are  
**How?** `<header>` is a special HTML tag that means "this is the top part"

**What is `class="menu-header"`?**  
Think of a class like a name tag. We're giving this header a name tag that says "menu-header". Later, we'll use CSS to style everything with this name tag!

```html
<h1>🍕 Tony's Italian Restaurant</h1>
```
**What?** This is the biggest, most important heading  
**Why?** It's the restaurant name - the most important text  
**How?** `<h1>` means "Heading 1" - the biggest heading. The emoji 🍕 makes it fun!

```html
<p class="subtitle">Authentic Italian Cuisine Since 1985</p>
```
**What?** This is a smaller text below the title  
**Why?** It gives extra information about the restaurant  
**How?** `<p>` means "paragraph" - regular text. `class="subtitle"` gives it a special name so we can style it differently

---

**Step 4: Add Menu Sections**

Now let's add the menu sections. We'll create sections for different types of food:

```html
<body>
    <header class="menu-header">
        <h1>🍕 Tony's Italian Restaurant</h1>
        <p class="subtitle">Authentic Italian Cuisine Since 1985</p>
    </header>

    <main class="menu-container">
        <!-- Appetizers Section -->
        <section class="menu-section">
            <h2 class="section-title">🍴 Appetizers</h2>
            <div class="menu-items">
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Bruschetta</h3>
                        <span class="item-price">$8.99</span>
                    </div>
                    <p class="item-description">Fresh tomatoes, basil, and garlic on toasted bread</p>
                </div>
                
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Caesar Salad</h3>
                        <span class="item-price">$9.99</span>
                    </div>
                    <p class="item-description">Crisp romaine lettuce with Caesar dressing and croutons</p>
                </div>
            </div>
        </section>

        <!-- Main Courses Section -->
        <section class="menu-section">
            <h2 class="section-title">🍝 Main Courses</h2>
            <div class="menu-items">
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Spaghetti Carbonara</h3>
                        <span class="item-price">$16.99</span>
                    </div>
                    <p class="item-description">Creamy pasta with bacon, eggs, and parmesan cheese</p>
                </div>
                
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Margherita Pizza</h3>
                        <span class="item-price">$14.99</span>
                    </div>
                    <p class="item-description">Classic pizza with tomato, mozzarella, and fresh basil</p>
                </div>
            </div>
        </section>

        <!-- Desserts Section -->
        <section class="menu-section">
            <h2 class="section-title">🍰 Desserts</h2>
            <div class="menu-items">
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Tiramisu</h3>
                        <span class="item-price">$7.99</span>
                    </div>
                    <p class="item-description">Classic Italian dessert with coffee and mascarpone</p>
                </div>
                
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Gelato</h3>
                        <span class="item-price">$6.99</span>
                    </div>
                    <p class="item-description">Italian ice cream - choose from vanilla, chocolate, or strawberry</p>
                </div>
            </div>
        </section>
    </main>
</body>
```

**Line-by-Line Explanation:**

```html
<main class="menu-container">
```
**What?** The main content area - like the pages of a book  
**Why?** It holds all the important content (the menu sections)  
**How?** `<main>` is a special tag that means "this is the main content"

```html
<section class="menu-section">
```
**What?** A section is like a chapter in a book  
**Why?** We organize our menu into sections (Appetizers, Main Courses, Desserts)  
**How?** Each `<section>` is one category of food

```html
<h2 class="section-title">🍴 Appetizers</h2>
```
**What?** A smaller heading for the section name  
**Why?** It tells people what category of food this is  
**How?** `<h2>` is smaller than `<h1>` but still a heading

```html
<div class="menu-items">
```
**What?** A container that holds all the food items  
**Why?** Like a box that holds all the items in this section  
**How?** `<div>` is like an invisible box - we use it to group things together

```html
<div class="menu-item">
```
**What?** One food item (like one dish on the menu)  
**Why?** Each food needs its own container so we can style it  
**How?** This wraps around one complete food item

```html
<div class="item-header">
    <h3 class="item-name">Bruschetta</h3>
    <span class="item-price">$8.99</span>
</div>
```
**What?** The header of each menu item - name and price together  
**Why?** We want the name and price on the same line  
**How?** We put them in a container so we can arrange them side by side

**What is `<span>`?**  
Think of `<span>` like a small invisible box. We use it for small pieces of text that we want to style differently (like the price).

```html
<p class="item-description">Fresh tomatoes, basil, and garlic on toasted bread</p>
```
**What?** The description of the food  
**Why?** People want to know what's in the dish  
**How?** Regular paragraph text below the name and price

---

**Step 5: Add CSS to Make It Beautiful!**

Now comes the fun part - making it look pretty! Add this CSS inside the `<style>` tag:

```html
<style>
    /* Reset - This removes default browser styles */
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    /* What is margin and padding? */
    /* Think of margin like the space OUTSIDE a box */
    /* Think of padding like the space INSIDE a box */
    /* We set them to 0 to start fresh! */

    body {
        font-family: 'Georgia', serif;
        background-color: #f5f5f5;
        color: #333;
        line-height: 1.6;
        padding: 20px;
    }

    /* What is font-family? */
    /* It's like choosing what handwriting style to use */
    /* Georgia is a nice, elegant font that looks good for restaurants */

    /* What is background-color? */
    /* It's like the color of the paper - #f5f5f5 is a light gray */

    /* What is line-height? */
    /* It's the space between lines of text - 1.6 means 1.6 times the text size */
    /* This makes text easier to read! */

    /* Header Styles */
    .menu-header {
        text-align: center;
        background: linear-gradient(135deg, #8B4513 0%, #D2691E 100%);
        color: white;
        padding: 40px 20px;
        margin-bottom: 40px;
        border-radius: 10px;
    }

    /* What is text-align: center? */
    /* It's like centering text on a page - everything goes to the middle */

    /* What is linear-gradient? */
    /* It's like mixing two paint colors together smoothly */
    /* #8B4513 is brown, #D2691E is orange-brown */
    /* They blend together to make a beautiful background! */

    /* What is padding? */
    /* Remember - padding is space INSIDE the box */
    /* 40px top/bottom, 20px left/right */

    /* What is margin-bottom? */
    /* Space below the header - pushes the menu sections down */

    /* What is border-radius? */
    /* It rounds the corners - like cutting the corners of a square piece of paper */

    .menu-header h1 {
        font-size: 48px;
        margin-bottom: 10px;
    }

    /* What is font-size? */
    /* How big the text is - 48px is very big! */

    .menu-header .subtitle {
        font-size: 18px;
        opacity: 0.9;
    }

    /* What is opacity? */
    /* How see-through something is - 0.9 means 90% visible (slightly see-through) */

    /* Menu Container */
    .menu-container {
        max-width: 1000px;
        margin: 0 auto;
    }

    /* What is max-width? */
    /* The maximum width - like saying "don't get wider than 1000px" */
    /* This keeps our menu from being too wide on big screens */

    /* What is margin: 0 auto? */
    /* 0 = no top/bottom margin */
    /* auto = center it horizontally (like centering a picture on a wall) */

    /* Menu Section */
    .menu-section {
        margin-bottom: 50px;
        background-color: white;
        padding: 30px;
        border-radius: 10px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    }

    /* What is box-shadow? */
    /* It's like a shadow behind the box - makes it look like it's floating! */
    /* 0 2px 10px = shadow position and blur */
    /* rgba(0, 0, 0, 0.1) = black color with 10% opacity (very light shadow) */

    .section-title {
        font-size: 32px;
        color: #8B4513;
        margin-bottom: 25px;
        border-bottom: 3px solid #D2691E;
        padding-bottom: 10px;
    }

    /* What is border-bottom? */
    /* A line under the text - like underlining but only on the bottom */
    /* 3px = thickness, solid = solid line (not dashed), #D2691E = color */

    /* Menu Items Grid */
    .menu-items {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 25px;
    }

    /* What is display: grid? */
    /* It's like a table or spreadsheet - arranges items in rows and columns */

    /* What is grid-template-columns? */
    /* How many columns we want */
    /* repeat(auto-fit, minmax(300px, 1fr)) is like saying: */
    /* "Make as many columns as fit, each at least 300px wide" */
    /* This makes it responsive - works on phones AND computers! */

    /* What is gap? */
    /* Space between grid items - like the space between tiles on a floor */

    /* Menu Item */
    .menu-item {
        background-color: #fafafa;
        padding: 20px;
        border-radius: 8px;
        transition: transform 0.3s ease;
    }

    /* What is transition? */
    /* It's like saying "when something changes, do it smoothly, not instantly" */
    /* transform 0.3s ease = when we transform (move/scale), take 0.3 seconds */

    .menu-item:hover {
        transform: translateY(-5px);
        box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
    }

    /* What is :hover? */
    /* It's like when you point at something with your mouse */
    /* When you hover over a menu item, it moves up a little! */

    /* What is translateY(-5px)? */
    /* Move it up 5 pixels - like lifting it slightly */

    /* Item Header (Name and Price) */
    .item-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 10px;
    }

    /* What is display: flex? */
    /* It's like putting things in a row and controlling how they're spaced */

    /* What is justify-content: space-between? */
    /* Put space between items - name on left, price on right */

    /* What is align-items: center? */
    /* Center items vertically - so name and price are on the same line */

    .item-name {
        font-size: 20px;
        color: #333;
        font-weight: bold;
    }

    .item-price {
        font-size: 20px;
        color: #8B4513;
        font-weight: bold;
    }

    .item-description {
        color: #666;
        font-size: 14px;
        line-height: 1.6;
    }

    /* Responsive Design - For Phones! */
    @media (max-width: 768px) {
        .menu-header h1 {
            font-size: 32px;
        }

        .menu-items {
            grid-template-columns: 1fr;
        }
    }

    /* What is @media? */
    /* It's like saying "if the screen is smaller than 768px, do this instead" */
    /* This makes our menu work on phones! */

    /* What is grid-template-columns: 1fr? */
    /* 1fr means "one fraction" - just one column */
    /* On phones, we want one item per row, not multiple */
</style>
```

---

#### Complete Code

Here's the complete `restaurant-menu.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Delicious Restaurant Menu</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
            padding: 20px;
        }

        .menu-header {
            text-align: center;
            background: linear-gradient(135deg, #8B4513 0%, #D2691E 100%);
            color: white;
            padding: 40px 20px;
            margin-bottom: 40px;
            border-radius: 10px;
        }

        .menu-header h1 {
            font-size: 48px;
            margin-bottom: 10px;
        }

        .menu-header .subtitle {
            font-size: 18px;
            opacity: 0.9;
        }

        .menu-container {
            max-width: 1000px;
            margin: 0 auto;
        }

        .menu-section {
            margin-bottom: 50px;
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        .section-title {
            font-size: 32px;
            color: #8B4513;
            margin-bottom: 25px;
            border-bottom: 3px solid #D2691E;
            padding-bottom: 10px;
        }

        .menu-items {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }

        .menu-item {
            background-color: #fafafa;
            padding: 20px;
            border-radius: 8px;
            transition: transform 0.3s ease;
        }

        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
        }

        .item-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .item-name {
            font-size: 20px;
            color: #333;
            font-weight: bold;
        }

        .item-price {
            font-size: 20px;
            color: #8B4513;
            font-weight: bold;
        }

        .item-description {
            color: #666;
            font-size: 14px;
            line-height: 1.6;
        }

        @media (max-width: 768px) {
            .menu-header h1 {
                font-size: 32px;
            }

            .menu-items {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header class="menu-header">
        <h1>🍕 Tony's Italian Restaurant</h1>
        <p class="subtitle">Authentic Italian Cuisine Since 1985</p>
    </header>

    <main class="menu-container">
        <section class="menu-section">
            <h2 class="section-title">🍴 Appetizers</h2>
            <div class="menu-items">
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Bruschetta</h3>
                        <span class="item-price">$8.99</span>
                    </div>
                    <p class="item-description">Fresh tomatoes, basil, and garlic on toasted bread</p>
                </div>
                
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Caesar Salad</h3>
                        <span class="item-price">$9.99</span>
                    </div>
                    <p class="item-description">Crisp romaine lettuce with Caesar dressing and croutons</p>
                </div>
            </div>
        </section>

        <section class="menu-section">
            <h2 class="section-title">🍝 Main Courses</h2>
            <div class="menu-items">
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Spaghetti Carbonara</h3>
                        <span class="item-price">$16.99</span>
                    </div>
                    <p class="item-description">Creamy pasta with bacon, eggs, and parmesan cheese</p>
                </div>
                
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Margherita Pizza</h3>
                        <span class="item-price">$14.99</span>
                    </div>
                    <p class="item-description">Classic pizza with tomato, mozzarella, and fresh basil</p>
                </div>
            </div>
        </section>

        <section class="menu-section">
            <h2 class="section-title">🍰 Desserts</h2>
            <div class="menu-items">
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Tiramisu</h3>
                        <span class="item-price">$7.99</span>
                    </div>
                    <p class="item-description">Classic Italian dessert with coffee and mascarpone</p>
                </div>
                
                <div class="menu-item">
                    <div class="item-header">
                        <h3 class="item-name">Gelato</h3>
                        <span class="item-price">$6.99</span>
                    </div>
                    <p class="item-description">Italian ice cream - choose from vanilla, chocolate, or strawberry</p>
                </div>
            </div>
        </section>
    </main>
</body>
</html>
```

#### Testing Your Menu

1. **Save the file** as `restaurant-menu.html`
2. **Open it in a browser** - Double-click the file
3. **What you should see:**
   - A brown/orange header with the restaurant name
   - Three sections: Appetizers, Main Courses, Desserts
   - Each food item with name, price, and description
   - When you hover over items, they lift up slightly
4. **Test on phone:** Resize your browser window - items should stack in one column on small screens

#### What You've Learned

✅ How to organize content into sections  
✅ How to use CSS Grid for responsive layouts  
✅ How to style multiple items consistently  
✅ How to create hover effects  
✅ How to make pages work on phones (responsive design)  
✅ How to use gradients for backgrounds  

#### Challenge Exercises

1. **Add more menu items** - Add 2-3 more items to each section
2. **Change the colors** - Use your favorite color scheme
3. **Add images** - Add food images to each menu item
4. **Add a footer** - Create a footer with restaurant address and hours
5. **Add special badges** - Add "Chef's Special" or "Vegetarian" badges to some items

---

### Project 2.2: Portfolio Website

#### What Are We Building?

Imagine you're an artist, and you want to show your artwork to people. You'd create a portfolio - a collection of your best work. That's what we're building! A portfolio website where someone can show off their projects, skills, and contact information.

#### Why Are We Building This?

**Why?** Because it teaches you:
- How to create a multi-section website
- How to showcase work in a gallery
- How to create a contact form
- How to make a professional-looking website
- How to use external CSS files (separate CSS file)

#### How Does It Work?

Think of it like a photo album:
1. **Header** = The cover with your name
2. **About Section** = A page about you
3. **Projects Gallery** = Pages showing your work
4. **Skills Section** = A list of what you can do
5. **Contact Form** = A way for people to message you

---

#### Step-by-Step: Building the Portfolio

**Step 1: Create Project Folder Structure**

First, let's organize our files properly:

```
portfolio-website/
├── index.html
├── css/
│   └── style.css
└── images/
    └── (we'll use placeholder images)
```

**What is a folder structure?**  
Think of it like organizing your toys:
- `portfolio-website` = The big toy box
- `index.html` = The main toy (the webpage)
- `css/` = A smaller box for all the pretty colors and styles
- `images/` = A box for pictures

**Why organize like this?**  
Just like you organize your room, organizing code makes it easier to find things!

**How to create it:**
1. Create a folder called `portfolio-website`
2. Inside it, create a folder called `css`
3. Inside it, create a folder called `images`

---

**Step 2: Create the HTML File**

Create `index.html` inside the `portfolio-website` folder:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>John Doe - Web Developer Portfolio</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <!-- Our content will go here -->
</body>
</html>
```

**What is `<link rel="stylesheet" href="css/style.css">`?**

**What?** This connects our HTML to our CSS file  
**Why?** Instead of putting CSS inside HTML, we put it in a separate file (cleaner!)  
**How?** `href="css/style.css"` tells the browser: "Go find the CSS file in the css folder"

**Why use external CSS?**  
Think of it like this:
- **Internal CSS** (in `<style>` tag) = Writing notes in your book
- **External CSS** (separate file) = Writing notes in a separate notebook

External is better for bigger projects because:
- You can use the same CSS for multiple pages
- It's easier to organize
- It's easier to find and fix things

---

**Step 3: Add Navigation Header**

```html
<body>
    <header class="main-header">
        <nav class="navbar">
            <div class="logo">John Doe</div>
            <ul class="nav-menu">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
</body>
```

**Line-by-Line Explanation:**

```html
<nav class="navbar">
```
**What?** Navigation is like a map - it helps people move around your website  
**Why?** People need to know how to get to different sections  
**How?** `<nav>` is a special tag that means "this is navigation"

```html
<ul class="nav-menu">
```
**What?** A list of navigation links  
**Why?** We want to show all the sections people can visit  
**How?** `<ul>` means "unordered list" - a list without numbers

```html
<li><a href="#home">Home</a></li>
```
**What?** One navigation item  
**Why?** Each link takes you to a different section  
**How?** 
- `<li>` = list item (one item in the list)
- `<a href="#home">` = a link that goes to the section with `id="home"`
- The `#` means "go to a section on this same page"

---

**Step 4: Add All Sections**

```html
<body>
    <header class="main-header">
        <nav class="navbar">
            <div class="logo">John Doe</div>
            <ul class="nav-menu">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Home/Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Hi, I'm John Doe</h1>
            <p class="hero-subtitle">Web Developer & Designer</p>
            <p class="hero-description">I create beautiful and functional websites</p>
            <a href="#contact" class="cta-button">Get In Touch</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Hello! I'm a passionate web developer with 5 years of experience creating amazing websites. I love turning ideas into beautiful, functional websites.</p>
                    <p>When I'm not coding, you can find me reading tech blogs, experimenting with new design trends, or enjoying a good cup of coffee.</p>
                </div>
                <div class="about-image">
                    <img src="https://via.placeholder.com/300" alt="John Doe">
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <div class="container">
            <h2 class="section-title">My Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <img src="https://via.placeholder.com/400x300" alt="Project 1">
                    <div class="project-info">
                        <h3>E-Commerce Website</h3>
                        <p>A full-featured online store with shopping cart functionality</p>
                        <a href="#" class="project-link">View Project →</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <img src="https://via.placeholder.com/400x300" alt="Project 2">
                    <div class="project-info">
                        <h3>Restaurant Menu App</h3>
                        <p>Interactive menu application for restaurants</p>
                        <a href="#" class="project-link">View Project →</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <img src="https://via.placeholder.com/400x300" alt="Project 3">
                    <div class="project-info">
                        <h3>Portfolio Website</h3>
                        <p>Beautiful portfolio website for creative professionals</p>
                        <a href="#" class="project-link">View Project →</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="skills">
        <div class="container">
            <h2 class="section-title">My Skills</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <div class="skill-icon">HTML</div>
                    <h3>HTML5</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 90%"></div>
                    </div>
                </div>
                
                <div class="skill-item">
                    <div class="skill-icon">CSS</div>
                    <h3>CSS3</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 85%"></div>
                    </div>
                </div>
                
                <div class="skill-item">
                    <div class="skill-icon">JS</div>
                    <h3>JavaScript</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 75%"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <form class="contact-form">
                <input type="text" placeholder="Your Name" required>
                <input type="email" placeholder="Your Email" required>
                <textarea placeholder="Your Message" rows="5" required></textarea>
                <button type="submit" class="submit-button">Send Message</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer class="main-footer">
        <p>&copy; 2024 John Doe. All rights reserved.</p>
    </footer>
</body>
</html>
```

**Key HTML Concepts Explained:**

```html
<section id="home" class="hero">
```
**What?** A section with an ID  
**Why?** The `id="home"` lets our navigation link (`#home`) jump to this section  
**How?** When you click a link with `href="#home"`, the page scrolls to this section

```html
<div class="container">
```
**What?** A container that limits width and centers content  
**Why?** So our content doesn't stretch too wide on big screens  
**How?** We'll style it in CSS to have a max-width and center it

```html
<div class="skill-bar">
    <div class="skill-progress" style="width: 90%"></div>
</div>
```
**What?** A progress bar showing skill level  
**Why?** Visual way to show how good you are at something  
**How?** 
- Outer div = the empty bar
- Inner div = the filled part
- `style="width: 90%"` = fill 90% of the bar (inline style for this example)

```html
<form class="contact-form">
```
**What?** A form for people to send messages  
**Why?** So visitors can contact you  
**How?** `<form>` is a special tag that collects information

```html
<input type="text" placeholder="Your Name" required>
```
**What?** A text input box  
**Why?** So people can type their name  
**How?** 
- `type="text"` = text input
- `placeholder="Your Name"` = hint text that disappears when you type
- `required` = must fill this in before submitting

```html
<textarea placeholder="Your Message" rows="5" required></textarea>
```
**What?** A bigger text box for longer messages  
**Why?** People need space to write a message  
**How?** `rows="5"` = starts with 5 rows tall

---

**Step 5: Create the CSS File**

Create `css/style.css` and add all our styles:

```css
/* Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* What is the reset? */
/* It's like erasing the default styles browsers add */
/* We start with a clean slate! */

body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    color: #333;
}

/* Header */
.main-header {
    background-color: #2c3e50;
    color: white;
    padding: 1rem 0;
    position: sticky;
    top: 0;
    z-index: 1000;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

/* What is position: sticky? */
/* It's like a sticker that sticks to the top when you scroll */
/* The header stays visible even when you scroll down! */

.navbar {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
}

.logo {
    font-size: 24px;
    font-weight: bold;
}

.nav-menu {
    display: flex;
    list-style: none;
    gap: 30px;
}

.nav-menu a {
    color: white;
    text-decoration: none;
    transition: color 0.3s;
}

.nav-menu a:hover {
    color: #3498db;
}

/* Hero Section */
.hero {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    padding: 150px 20px;
    text-align: center;
}

/* What is padding: 150px 20px? */
/* 150px = top and bottom (lots of space!) */
/* 20px = left and right */

.hero-content {
    max-width: 800px;
    margin: 0 auto;
}

.hero h1 {
    font-size: 56px;
    margin-bottom: 20px;
}

.hero-subtitle {
    font-size: 24px;
    margin-bottom: 15px;
    opacity: 0.9;
}

.hero-description {
    font-size: 18px;
    margin-bottom: 30px;
}

.cta-button {
    display: inline-block;
    background-color: white;
    color: #667eea;
    padding: 15px 40px;
    border-radius: 30px;
    text-decoration: none;
    font-weight: bold;
    transition: transform 0.3s;
}

.cta-button:hover {
    transform: scale(1.05);
}

/* Container */
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* Section Title */
.section-title {
    font-size: 36px;
    text-align: center;
    margin-bottom: 50px;
    color: #2c3e50;
}

/* About Section */
.about {
    padding: 80px 0;
    background-color: #f8f9fa;
}

.about-content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 50px;
    align-items: center;
}

/* What is grid-template-columns: 1fr 1fr? */
/* It means "two equal columns" */
/* 1fr = one fraction (equal size) */
/* So we get two columns, each taking half the space */

.about-text p {
    margin-bottom: 20px;
    font-size: 16px;
    line-height: 1.8;
}

.about-image img {
    width: 100%;
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

/* Projects Section */
.projects {
    padding: 80px 0;
}

.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
}

.project-card {
    background-color: white;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s;
}

.project-card:hover {
    transform: translateY(-10px);
}

.project-card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}

.project-info {
    padding: 25px;
}

.project-info h3 {
    margin-bottom: 10px;
    color: #2c3e50;
}

.project-info p {
    color: #666;
    margin-bottom: 15px;
}

.project-link {
    color: #667eea;
    text-decoration: none;
    font-weight: bold;
}

.project-link:hover {
    text-decoration: underline;
}

/* Skills Section */
.skills {
    padding: 80px 0;
    background-color: #f8f9fa;
}

.skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 30px;
}

.skill-item {
    background-color: white;
    padding: 30px;
    border-radius: 10px;
    text-align: center;
    box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
}

.skill-icon {
    font-size: 48px;
    font-weight: bold;
    color: #667eea;
    margin-bottom: 15px;
}

.skill-item h3 {
    margin-bottom: 15px;
    color: #2c3e50;
}

.skill-bar {
    width: 100%;
    height: 10px;
    background-color: #e0e0e0;
    border-radius: 5px;
    overflow: hidden;
}

.skill-progress {
    height: 100%;
    background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
    transition: width 1s ease;
}

/* What is transition: width 1s ease? */
/* When the width changes, animate it over 1 second smoothly */
/* This makes the progress bar fill up smoothly! */

/* Contact Section */
.contact {
    padding: 80px 0;
}

.contact-form {
    max-width: 600px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

/* What is flex-direction: column? */
/* Stack items vertically (one on top of the other) */
/* Instead of side by side */

.contact-form input,
.contact-form textarea {
    padding: 15px;
    border: 2px solid #e0e0e0;
    border-radius: 5px;
    font-size: 16px;
    font-family: inherit;
}

/* What is font-family: inherit? */
/* Use the same font as the parent (body) */
/* So all text looks consistent */

.contact-form input:focus,
.contact-form textarea:focus {
    outline: none;
    border-color: #667eea;
}

/* What is :focus? */
/* When you click in an input box, it's "focused" */
/* We change the border color to show it's active */

.submit-button {
    background-color: #667eea;
    color: white;
    padding: 15px 40px;
    border: none;
    border-radius: 30px;
    font-size: 18px;
    font-weight: bold;
    cursor: pointer;
    transition: background-color 0.3s;
}

.submit-button:hover {
    background-color: #764ba2;
}

/* Footer */
.main-footer {
    background-color: #2c3e50;
    color: white;
    text-align: center;
    padding: 30px;
}

/* Responsive Design */
@media (max-width: 768px) {
    .nav-menu {
        flex-direction: column;
        gap: 10px;
    }

    .hero h1 {
        font-size: 36px;
    }

    .about-content {
        grid-template-columns: 1fr;
    }

    .projects-grid,
    .skills-grid {
        grid-template-columns: 1fr;
    }
}
```

---

#### Complete Files

**index.html** - [Use the HTML from Step 4 above]

**css/style.css** - [Use the CSS from Step 5 above]

#### Testing Your Portfolio

1. **Save both files** in the correct folders
2. **Open `index.html`** in a browser
3. **Test navigation** - Click links, page should scroll to sections
4. **Test responsive** - Resize browser, layout should adapt
5. **Test hover effects** - Hover over project cards and buttons

#### What You've Learned

✅ Multi-section website structure  
✅ External CSS files (separate from HTML)  
✅ Smooth scrolling navigation  
✅ Project gallery with grid layout  
✅ Skill progress bars  
✅ Contact forms  
✅ Responsive design for all screen sizes  

#### Challenge Exercises

1. **Add more projects** - Add 3-4 more project cards
2. **Add social media links** - Add icons for GitHub, LinkedIn, etc.
3. **Add animations** - Make sections fade in when scrolling
4. **Change color scheme** - Use your favorite colors
5. **Add a blog section** - Create a section for blog posts

---

## Step 3: Advanced Intermediate Projects (Combining Concepts)

[This section will be implemented next]

---

## Step 3: Advanced Intermediate Projects (Combining Concepts)

[This section will be implemented in the next phase]

---

## Best Practices and Tips

### HTML Best Practices

1. **Use Semantic HTML** - Use `<header>`, `<nav>`, `<section>`, `<article>`, `<footer>` instead of just `<div>`
2. **Proper Indentation** - Keep code readable with consistent indentation
3. **Alt Text for Images** - Always include `alt` attributes for accessibility
4. **Meaningful Class Names** - Use descriptive names like `.product-card` not `.box1`

### CSS Best Practices

1. **Mobile-First** - Start with mobile styles, then add larger screen styles
2. **Consistent Spacing** - Use a spacing system (4px, 8px, 16px, etc.)
3. **Reusable Classes** - Create utility classes for common patterns
4. **Comments** - Comment complex CSS sections
5. **Organize CSS** - Group related styles together

### Project Organization

```
project-folder/
├── index.html
├── css/
│   └── style.css
├── images/
│   └── (your images)
└── js/
    └── (future JavaScript files)
```

---

## Troubleshooting Common Issues

### Issue: Elements Not Centering

**Solution:** Check if parent has `display: flex` or `text-align: center`

### Issue: Images Not Showing

**Solution:** 
- Check file paths (use relative paths like `./images/photo.jpg`)
- Verify image file exists
- Check browser console for errors

### Issue: Styles Not Applying

**Solution:**
- Check CSS selector specificity
- Verify class names match
- Check for typos
- Use browser DevTools to inspect

### Issue: Layout Breaking on Mobile

**Solution:**
- Add `viewport` meta tag
- Use responsive units (%, rem, vw)
- Test with browser DevTools device mode

---

## Next Steps

After completing Step 1 projects:

1. **Practice** - Build each project 2-3 times
2. **Modify** - Change colors, layouts, content
3. **Combine** - Use multiple cards on one page
4. **Experiment** - Try new CSS properties
5. **Move to Step 2** - When comfortable with Step 1

---

**Congratulations on completing Step 1!** 🎉

You've learned the fundamentals of combining HTML and CSS. In Step 2, we'll build more complex projects that combine multiple concepts and introduce new techniques.


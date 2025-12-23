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

[This section will be implemented in the next phase]

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


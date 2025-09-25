## 🎨 Session 3 — CSS Syntax and Basic Rules

### 📘 Content

---

### 🧠 Learning Objectives

- Learn CSS syntax: selectors → properties → values  
- Identify and use common selectors: type, class, ID  
- Apply basic styling properties to HTML elements  
- Practice clean formatting: indentation, commenting, and visual grouping  
- Understand how CSS rules are interpreted by browsers  

---

### 💬 Visual Design Reflection

> “How does CSS know *what* to style and *how* to style it?”

This session focused on the grammar of CSS — how we write rules that browsers understand. We explored selector types, declaration formatting, and best practices for clean, readable code.

---

## 🔹 Syntax Walkthrough

### 🧪 Example 1: Understanding CSS Syntax

```css
/* 📌 Basic structure of a CSS rule: selector + declaration block */
p {
  color: blue;             /* property: color; value: blue */
  font-size: 16px;         /* sets text size */
}
```

> 🗣️ Remember:  
> - Curly braces `{ }` wrap the declaration block  
> - Each property ends with a semicolon `;`  
> - Colons `:` separate properties from values  

---

## 🔹 Selector Types in Action

### 🧪 Example 2: Type, Class, and ID Selectors

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* 🎯 Type selector: affects all <h2> elements */
    h2 {
      color: green;
    }

    /* 🎯 Class selector: reusable styles */
    .highlight {
      background-color: yellow;
      font-weight: bold;
    }

    /* 🎯 ID selector: unique element */
    #main-title {
      text-transform: uppercase;
      color: darkred;
    }
  </style>
</head>
<body>
  <h1 id="main-title">My CSS Practice</h1>
  <h2>Subheading</h2>
  <p>This is a normal paragraph.</p>
  <p class="highlight">This paragraph is highlighted.</p>
</body>
</html>
```

> 🗣️ Tip:  
> - Use `.class` for reusable styles across multiple elements  
> - Use `#id` for unique styling — only once per page  

---

## 🔹 Formatting & Commenting Best Practices

### 🧪 Example 3: Clean CSS Formatting

```css
/* ✅ CSS rule group: styling paragraph text */
p {
  color: #444;          /* softer dark gray for better readability */
  line-height: 1.6;     /* improves spacing between lines */
  margin-bottom: 16px;  /* creates space between paragraphs */
}
```

> 🗣️ Best Practices:  
> - Group related styles together  
> - Use comments to explain logic  
> - Indent consistently for readability  

---

## 🔹 In-Class Activity: Selector Matching Challenge

We practiced writing selectors for real-world HTML snippets.

**HTML Snippet:**
```html
<p class="notice">This is important!</p>
<div id="hero"></div>
<ul class="menu"><li>Home</li></ul>
```

**Matching Selectors:**
```css
/* Style important text */
p.notice {
  color: red;
  font-weight: bold;
}

/* Style hero section */
#hero {
  background-color: #333;
  height: 300px;
}

/* Style menu items */
.menu li {
  list-style-type: none;
  padding: 10px;
  background-color: #eee;
}
```

> 🧠 Challenge:  
> - Try adding hover effects  
> - Use border or font changes to personalize each selector  

---

## 🔹 Bonus Style Challenge (Optional)

> 🎨 Create a “style your own name” card

**HTML:**
```html
<div class="name-card">Jessel</div>
```

**CSS:**
```css
.name-card {
  background-color: #c8e6c9;
  font-family: 'Courier New', monospace;
  border: 2px dashed #388e3c;
  padding: 20px;
  width: fit-content;
  transition: transform 0.3s ease;
}

/* Hover effect */
.name-card:hover {
  transform: scale(1.1);
}
```

> 🗣️ This previewed hover effects (covered in Session 5) and gave students a chance to personalize their page.

---

## 📘 Homework Prompt — Worked Example with Comments

> **Assignment:** Style Starter Page  
> Use internal CSS to:
> - Style headings and paragraphs using type selectors  
> - Use at least one `.class` and one `#id`  
> - Experiment with two font sizes and two colors  
> - Comment your CSS clearly  

**HTML (`starter.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>CSS Syntax Homework</title>
  <style>
    /* Type selector for headings */
    h1 {
      color: navy;
      font-size: 28px;
    }

    /* Class selector for reusable paragraph style */
    .info {
      color: #555;
      font-size: 16px;
    }

    /* ID selector for unique heading */
    #special-heading {
      color: darkgreen;
      font-size: 24px;
      text-align: center;
    }
  </style>
</head>
<body>
  <h1>Welcome to My Page</h1>
  <h2 id="special-heading">Styled with CSS</h2>
  <p class="info">This paragraph uses a class selector.</p>
  <p>This paragraph uses default styling.</p>
</body>
</html>
```

---

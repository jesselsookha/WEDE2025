## 🎨 Session 1 — Introduction to CSS: Styling the Web

### 📘 Content

---

### 🖼️ Visual Design Reflection

> “What makes a webpage *look* good?”

Before diving into CSS, we explored what makes websites visually appealing. Think about your favorite sites — what stands out? Is it the layout, the colors, the spacing, the typography?

This session introduces CSS as the tool that transforms plain HTML into visually engaging web pages. HTML gives us structure; CSS gives us style.

---

### 🧠 What is CSS?

CSS stands for **Cascading Style Sheets**. It’s the language used to style HTML elements — controlling colors, fonts, spacing, layout, and more.

#### 🔹 CSS Syntax

A CSS rule consists of:
- A **selector** (which HTML element to style)
- A set of **declarations** inside `{ }`
- Each declaration includes a **property** and a **value**

```css
p {
  color: blue;
  font-size: 16px;
}
```

#### 🔹 Ways to Apply CSS

1. **Inline CSS** (inside the HTML tag)  
   ```html
   <p style="color: red;">Hello</p>
   ```
2. **Internal CSS** (inside a `<style>` tag in the `<head>`)  
   ```html
   <style>
     p {
       color: red;
     }
   </style>
   ```
3. **External CSS** (linked `.css` file — preferred method)  
   ```html
   <link rel="stylesheet" href="styles.css">
   ```

---

### 🎬 Live Demo – Visual Remix

We took a basic HTML page and applied different CSS styles to show how appearance can change dramatically.

#### 🧾 HTML Example
```html
<!DOCTYPE html>
<html>
<head>
  <title>Visual Remix</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <h1>Welcome to My Page</h1>
  <p>This is a paragraph of text.</p>
</body>
</html>
```

#### 🎨 CSS Variations
```css
body {
  background-color: #f0f0f0;
  font-family: 'Segoe UI', sans-serif;
  padding: 20px;
}

h1 {
  color: crimson;
  text-align: center;
  font-size: 36px;
}

p {
  color: #333;
  line-height: 1.6;
  margin: 20px;
  font-size: 18px;
}
```

Try changing:
- `color`
- `font-size`
- `text-align`
- `background-color`
- `padding` and `margin`

---

### 🧪 Hands-on Mini Challenge — Solution

> **Challenge:** Style a basic webpage with your own colour and font choices.

#### ✅ Final Solution

**HTML File (`index.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Styled Challenge</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <h1 class="main-heading">My Styled Page</h1>
  <p>This is a paragraph with custom styling.</p>
  <ul>
    <li>HTML Basics</li>
    <li>CSS Styling</li>
    <li>Responsive Design</li>
  </ul>
</body>
</html>
```

**CSS File (`styles.css`):**
```css
body {
  background-color: #e0f7fa;
  font-family: 'Verdana', sans-serif;
  color: #333;
  padding: 30px;
}

.main-heading {
  color: #00796b;
  text-align: center;
  font-size: 32px;
}

p {
  font-size: 18px;
  margin-bottom: 20px;
}

ul {
  background-color: #ffffff;
  padding: 15px;
  border: 1px solid #ccc;
  list-style-type: square;
}
```

---

### 🧩 Homework Recap 

> **Original Prompt:** “Create a webpage with a heading, paragraph, and list. Style it using CSS.”

Here’s a complete solution with comments to explain each part:

**HTML (`homework.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Homework Example</title>
  <!-- Linking external CSS file -->
  <link rel="stylesheet" href="homework.css">
</head>
<body>
  <!-- Main heading -->
  <h1 class="title">Welcome to My Homework Page</h1>

  <!-- Paragraph content -->
  <p>This page demonstrates basic CSS styling.</p>

  <!-- Unordered list -->
  <ul>
    <li>Use of selectors</li>
    <li>Color and font styling</li>
    <li>Spacing with margin and padding</li>
  </ul>
</body>
</html>
```

**CSS (`homework.css`):**
```css
/* Styling the body for background and font */
body {
  background-color: #f9fbe7;
  font-family: 'Arial', sans-serif;
  color: #444;
  padding: 25px;
}

/* Styling the heading */
.title {
  color: #33691e;
  text-align: center;
  font-size: 30px;
}

/* Styling the paragraph */
p {
  font-size: 16px;
  margin-bottom: 15px;
}

/* Styling the list */
ul {
  background-color: #ffffff;
  padding: 10px;
  border: 1px solid #ccc;
  list-style-type: disc;
}
```

---


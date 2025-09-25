## 🎯 Session 5 — Selectors in Depth: Targeting Like a Pro

### 📘 Content

---

### 🧠 Learning Objectives

- Understand selector types: type, class, ID, compound, descendant, child  
- Practice building specific selectors for structured HTML  
- Explore pseudo-classes like `:hover`, `:first-child`, `:nth-child()`  
- Begin reasoning about specificity and how styles compete  

---

### 🔍 Selector Review & Expansion

CSS selectors allow us to target specific elements in the DOM. The more precise the selector, the more control we have over styling.

---

## 🔧 Example 1: Compound Selectors

Compound selectors combine tags, classes, and IDs to narrow the scope of styling.

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* Targets <p> inside <section> */
    section p {
      font-size: 18px;
      color: teal;
    }

    /* Targets <li> inside .nav-menu */
    .nav-menu li {
      display: inline-block;
      margin-right: 10px;
    }

    /* Targets <div> with class .article */
    div.article {
      padding: 20px;
      border: 1px solid #ccc;
    }
  </style>
</head>
<body>
  <section>
    <p>This paragraph is inside a section.</p>
  </section>

  <ul class="nav-menu">
    <li>Home</li>
    <li>About</li>
    <li>Contact</li>
  </ul>

  <div class="article">
    <p>This is an article block.</p>
  </div>
</body>
</html>
```

> 🧠 Compound selectors help us “narrow the beam” — targeting elements only in specific contexts.

---

## 🔧 Example 2: Child vs. Descendant Selectors

**Descendant selectors** target any nested element, while **child selectors** (`>`) target only direct children.

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* Descendant selector */
    .container p {
      color: navy;
    }

    /* Child selector */
    .container > p {
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="container">
    <p>This is a direct child</p>
    <section><p>This is a deeper descendant</p></section>
  </div>
</body>
</html>
```

> 🌱 Use `>` when you want to limit styling to direct children only.

---

## 🔧 Example 3: Pseudo-Classes — Hover & nth-child

Pseudo-classes let us style elements based on their state or position.

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* Hover effect */
    a:hover {
      color: crimson;
      text-decoration: underline;
    }

    /* First item in list */
    ul li:first-child {
      font-weight: bold;
    }

    /* Alternating table rows */
    table tr:nth-child(even) {
      background-color: #f2f2f2;
    }

    table tr:nth-child(odd) {
      background-color: #ffffff;
    }
  </style>
</head>
<body>
  <a href="#">Hover over me</a>

  <ul>
    <li>First</li>
    <li>Second</li>
    <li>Third</li>
  </ul>

  <table>
    <tr><td>Row 1</td></tr>
    <tr><td>Row 2</td></tr>
    <tr><td>Row 3</td></tr>
  </table>
</body>
</html>
```

> 🔍 Pseudo-classes add interactivity and dynamic styling — especially useful for menus, tables, and buttons.

---

## 🧠 Specificity Strategy — Who Wins?

When multiple rules apply to the same element, CSS uses **specificity** to decide which one wins.

**CSS Example:**
```css
/* Low specificity — type selector */
p {
  color: blue;
}

/* Medium specificity — class selector */
.warning {
  color: red;
}

/* High specificity — ID selector */
#urgent {
  color: orange;
}
```

**HTML:**
```html
<p>This is normal.</p>
<p class="warning">This is a warning.</p>
<p id="urgent" class="warning">This is urgent.</p>
```

> 📊 The last `<p>` is orange because ID selectors override class and type selectors.

---

## 🧩 In-Class Activity — Selector Relay

Students were given a mock HTML page and a deck of selector challenges. Here’s a sample layout and solution set:

**HTML (`relay.html`):**
```html
<div id="main-content">
  <h1>Welcome</h1>
  <ul class="menu">
    <li>Home</li>
    <li>About</li>
    <li>Contact</li>
    <li>Blog</li>
    <li>Help</li>
  </ul>
  <a href="#">Click Me</a>
</div>
```

**CSS (`relay.css`):**
```css
/* Style navigation menu */
.menu li {
  display: inline-block;
  padding: 10px;
}

/* Highlight every third item */
.menu li:nth-child(3) {
  background-color: #ffeb3b;
}

/* Color headers inside #main-content */
#main-content h1 {
  color: darkblue;
}

/* Animate links on hover */
a:hover {
  color: crimson;
  text-decoration: underline;
  transition: color 0.3s ease;
}
```

> 🏁 Students scored points for clean selectors and correct specificity — a fun way to reinforce precision.

---

## 📘 Homework Prompt — Worked Example with Comments

> **Challenge:** Style a website menu using pseudo-classes and compound selectors.

**HTML (`menu.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Menu Styling</title>
  <link rel="stylesheet" href="menu.css">
</head>
<body>
  <nav>
    <ul class="main-menu">
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</body>
</html>
```

**CSS (`menu.css`):**
```css
/* Layout styling using class selector */
.main-menu li {
  display: inline-block;
  margin-right: 20px;
}

/* Hover effect using pseudo-class */
.main-menu a:hover {
  color: crimson;
  text-decoration: underline;
}

/* First item styling */
.main-menu li:first-child a {
  font-weight: bold;
}

/* Alternate item styling */
.main-menu li:nth-child(odd) a {
  background-color: #f0f0f0;
}

/* Comments explain selector logic */
```

> 🛠️ Students were asked to:
> - Comment each selector  
> - Create 3 distinct styling behaviors  
> - Push to Git with a short `README.md` explaining selector choices  

---

## 🎨 Session 4 — Understanding Inheritance and the DOM

### 📘 Content

---

### 🧠 Learning Objectives

- Understand how CSS inheritance works and which properties are passed down  
- Explore the DOM tree and how styles flow through nested HTML  
- Recognize when styles are inherited, overridden, or ignored  
- Visualize how the cascade resolves style conflicts  

---

### 🌐 What Is the DOM?

The **DOM (Document Object Model)** is the browser’s internal representation of your HTML. It’s structured like a tree — with parent, child, and sibling relationships.

Example:
```html
<body>
  <div>
    <p>Hello</p>
  </div>
</body>
```

In this structure:
- `<body>` is the root
- `<div>` is a child of `<body>`
- `<p>` is a child of `<div>`, and a grandchild of `<body>`

CSS can target elements at any level, and some styles will **flow down** from parent to child — this is called **inheritance**.

---

## 🔧 Example 1: Inherited vs. Non-Inherited Properties

Let’s look at which properties are inherited and which are not.

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-family: 'Georgia', serif;   /* ✅ Inherited by child elements */
      color: #444;                     /* ✅ Inherited by paragraphs and spans */
      margin: 40px;                    /* ❌ NOT inherited */
    }

    p {
      font-size: 18px;
    }

    span {
      color: blue;  /* Overrides inherited color from body */
    }
  </style>
</head>
<body>
  <p>This text uses the font-family from <code>body</code> and gets <span>blue override</span> here.</p>
</body>
</html>
```

### ✅ Inherited Properties
- `font-family`
- `color`
- `line-height`
- `text-align`

### ❌ Non-Inherited Properties
- `margin`, `padding`, `border`
- `width`, `height`
- `background-color`

> 🔍 Child elements inherit only **text-related** styles by default. Layout and spacing must be applied directly.

---

## 🔧 Example 2: Cascade in Action — Competing Rules

When multiple CSS rules target the same element, the browser uses the **cascade** to decide which one wins.

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* General paragraph rule */
    p {
      color: green;
    }

    /* More specific rule using class */
    .warning {
      color: red;
    }

    /* Most specific rule using ID */
    #urgent {
      color: orange;
    }
  </style>
</head>
<body>
  <p>This is a normal paragraph.</p>
  <p class="warning">This warning is red.</p>
  <p id="urgent" class="warning">This urgent message is orange due to higher specificity.</p>
</body>
</html>
```

### 🧠 What’s Happening Here:
- The first `<p>` uses the general `p` rule → green
- The second `<p>` has a `.warning` class → red
- The third `<p>` has both `.warning` and `#urgent` → orange (ID wins)

> 🔎 CSS uses **specificity** to resolve conflicts. ID selectors are stronger than class selectors, which are stronger than element selectors.

---

## 🌳 DOM Flow Mapping — Visualizing Inheritance

We explored how styles move through nested HTML using a tree-like structure.

**HTML Example:**
```html
<div class="container">
  <section>
    <article>
      <p>Deep content here</p>
    </article>
  </section>
</div>
```

**CSS Example:**
```css
.container {
  font-family: 'Arial', sans-serif;  /* ✅ Inherited by all children */
  color: #333;                        /* ✅ Inherited by <p> */
  padding: 20px;                      /* ❌ NOT inherited */
}

article {
  color: darkblue;  /* Overrides inherited color */
}
```

### 🧠 Style Flow:
- `<p>` inherits `font-family` from `.container`
- `<p>` inherits `color` from `article`, which overrides `.container`
- `<p>` does **not** inherit `padding` — it must be styled directly

> 🗺️ In class, we sketched this as a tree and labeled which styles flowed down and which were overridden.

---

## 🧪 Hands-on Mini Challenge — Solution

> **Challenge:** Create a nested HTML structure and demonstrate inheritance and overrides.

**HTML (`challenge.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Inheritance Challenge</title>
  <link rel="stylesheet" href="challenge.css">
</head>
<body>
  <div class="wrapper">
    <section class="content">
      <p class="highlight">This paragraph inherits font but overrides color.</p>
    </section>
  </div>
</body>
</html>
```

**CSS (`challenge.css`):**
```css
.wrapper {
  font-family: 'Verdana', sans-serif;  /* ✅ inherited */
  color: #555;                          /* ✅ inherited unless overridden */
  margin: 30px;                         /* ❌ not inherited */
}

.content {
  color: #222;  /* overrides wrapper color */
}

.highlight {
  color: crimson;  /* overrides content color */
}
```

> 🧠 Final Result:
- `font-family` flows from `.wrapper` to `.highlight`
- `color` is overridden twice: `.wrapper` → `.content` → `.highlight`
- `margin` applies only to `.wrapper`

---

## 📘 Homework Prompt — Worked Example with Comments

> **Assignment:** Create a cascade challenge page with nested elements and style overrides.

**HTML (`homework.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Cascade Homework</title>
  <link rel="stylesheet" href="homework.css">
</head>
<body>
  <div class="container">
    <section>
      <article>
        <p id="special">This paragraph shows inherited and overridden styles.</p>
      </article>
    </section>
  </div>
</body>
</html>
```

**CSS (`homework.css`):**
```css
/* Parent container styles */
.container {
  font-family: 'Tahoma', sans-serif;  /* ✅ inherited */
  color: #666;                         /* ✅ inherited */
  padding: 40px;                       /* ❌ not inherited */
}

/* Article overrides color */
article {
  color: #333;
}

/* ID selector overrides everything */
#special {
  color: teal;  /* ✅ final color due to highest specificity */
  font-size: 18px;
}
```

**📝 Comments:**
- `font-family` flows from `.container` to all children
- `color` is overridden twice: `.container` → `article` → `#special`
- `padding` applies only to `.container`
- `#special` wins due to ID specificity

---

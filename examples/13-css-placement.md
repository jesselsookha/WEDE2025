## 🎨 Session 2 — How to Apply CSS: Placement Methods

### 📘 Content

---

### 💬 Visual Design Reflection

> “Where does CSS go? And why does placement matter?”

In this session, we explored the different ways CSS can be applied to HTML — and why choosing the right method affects maintainability, scalability, and clarity. We also discussed how placement impacts performance and overrides.

---

## 🔹 CSS Placement Methods

#### ✅ Three Ways to Apply CSS

1. **Inline CSS**
   - CSS is written directly inside the HTML tag using the `style` attribute.
   - Useful for quick testing, but not recommended for long-term use.
   ```html
   <h1 style="color: red;">Hello World</h1>
   ```

2. **Internal CSS**
   - CSS is placed inside a `<style>` tag within the `<head>` of the HTML document.
   - Good for small projects or single-page styling.
   ```html
   <style>
     p {
       font-size: 18px;
       color: navy;
     }
   </style>
   ```

3. **External CSS**
   - CSS is written in a separate `.css` file and linked using `<link>`.
   - Best practice for maintainability and reusability.
   ```html
   <link rel="stylesheet" href="styles.css">
   ```

#### 📂 Why Placement Matters

- **Inline** styles override internal and external styles due to higher specificity.
- **Internal** styles override external styles if placed after the link.
- **External** styles are clean, reusable, and preferred for collaborative projects.

#### 🎯 Best Practices

- Use **external CSS** for all real-world projects.
- Avoid inline styles unless debugging or testing.
- Keep internal styles minimal and only for quick prototypes.

---

### 🎬 In-Class Activity: Placement Comparison

We created a simple HTML page and applied styles using all three methods to observe how they interact.

#### ✅ Full Example

**HTML (`index.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>CSS Placement Demo</title>

  <!-- External CSS -->
  <link rel="stylesheet" href="styles.css">

  <!-- Internal CSS -->
  <style>
    h1 {
      color: green;
    }
  </style>
</head>
<body>
  <!-- Inline CSS -->
  <h1 style="color: red;">Welcome to CSS Placement</h1>
  <p>This paragraph is styled using external CSS.</p>
</body>
</html>
```

**External CSS (`styles.css`):**
```css
body {
  background-color: #f0f0f0;
  font-family: Arial, sans-serif;
  padding: 20px;
}

p {
  color: blue;
  font-size: 16px;
}
```

#### 🔍 Observation:
- The `<h1>` appears red due to inline CSS overriding both internal and external styles.
- The `<p>` uses external styling unless overridden internally or inline.

---

### 🧪 Hands-on Mini Challenge — Solution

> **Challenge:** Apply all three CSS placement methods to style different parts of a webpage.

#### ✅ Final Solution

**HTML (`challenge.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>CSS Placement Challenge</title>

  <!-- External CSS -->
  <link rel="stylesheet" href="challenge.css">

  <!-- Internal CSS -->
  <style>
    h2 {
      color: darkorange;
      font-size: 24px;
    }
  </style>
</head>
<body>
  <!-- Inline CSS -->
  <h1 style="color: crimson; font-family: Georgia;">Inline Styled Heading</h1>

  <h2>Internal Styled Subheading</h2>

  <p>This paragraph is styled using external CSS.</p>
</body>
</html>
```

**External CSS (`challenge.css`):**
```css
body {
  background-color: #e8f5e9;
  font-family: 'Verdana', sans-serif;
  padding: 30px;
}

p {
  color: #2e7d32;
  font-size: 18px;
  line-height: 1.6;
}
```

---

### 📚 Homework Prompt — Worked Example with Comments

> **Original Prompt:** “Create a webpage that uses all three CSS placement methods. Observe which styles take effect.”

**HTML (`homework.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>CSS Placement Homework</title>

  <!-- External CSS -->
  <link rel="stylesheet" href="homework.css">

  <!-- Internal CSS -->
  <style>
    h2 {
      color: teal;
      font-size: 22px;
    }
  </style>
</head>
<body>
  <!-- Inline CSS overrides everything -->
  <h1 style="color: purple; font-size: 28px;">Inline Heading</h1>

  <!-- Internal CSS applies here -->
  <h2>Internal Subheading</h2>

  <!-- External CSS applies here -->
  <p>This paragraph uses external styling.</p>
</body>
</html>
```

**CSS (`homework.css`):**
```css
/* External CSS styles */
body {
  background-color: #fff3e0;
  font-family: 'Tahoma', sans-serif;
  padding: 20px;
}

p {
  color: #6d4c41;
  font-size: 16px;
}
```

**📝 Comments:**
- The `<h1>` is styled inline, so it overrides everything else.
- The `<h2>` uses internal styles from the `<style>` block.
- The `<p>` uses external styles from the linked CSS file.

---


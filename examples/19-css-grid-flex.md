## 🧩 Session 8 — Transitions, Flexbox, and Grid Fundamentals

### 📘 Content

---

### 🧠 Learning Objectives

- Create basic CSS transitions to animate property changes  
- Use Flexbox to lay out elements in one-dimensional rows or columns  
- Use Grid to lay out two-dimensional page structures  
- Understand responsive alignment, spacing, and media queries  

---

## 🎬 Transitions in CSS

Transitions allow properties to change smoothly over time, rather than instantly. This adds polish and interactivity to your designs.

### 🔧 Example 1: Hover Transition on a Button

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .button {
      background-color: #3498db;
      color: white;
      padding: 10px 20px;
      border: none;
      cursor: pointer;
      transition: background-color 0.3s ease, transform 0.2s ease-in-out;
    }

    .button:hover {
      background-color: #2ecc71;
      transform: scale(1.1);
    }
  </style>
</head>
<body>
  <button class="button">Hover Me</button>
</body>
</html>
```

> 💡 Transitions work best with properties like `background-color`, `transform`, `opacity`, and `box-shadow`. Avoid using them on layout properties like `display` or `position`.

---

## 📐 Flexbox Layouts — One-Dimensional Control

Flexbox is ideal for laying out items in a row or column. It simplifies alignment, spacing, and responsiveness.

### 🔧 Example 2: Horizontal Flex Layout

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .flex-container {
      display: flex;
      justify-content: space-around;  /* Distributes items evenly */
      align-items: center;            /* Aligns items vertically */
      height: 120px;
      background-color: #eee;
    }

    .flex-item {
      background-color: #ccc;
      padding: 20px;
      width: 100px;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="flex-container">
    <div class="flex-item">A</div>
    <div class="flex-item">B</div>
    <div class="flex-item">C</div>
  </div>
</body>
</html>
```

> 🔄 Flexbox uses two axes: the **main axis** (row or column) and the **cross axis** (perpendicular). `justify-content` controls spacing along the main axis; `align-items` controls alignment on the cross axis.

---

## 🧮 Grid Fundamentals — Two-Dimensional Layout

Grid is perfect for building structured layouts with rows and columns. It offers precise control over placement and spacing.

### 🔧 Example 3: Simple Grid Layout

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .grid-container {
      display: grid;
      grid-template-columns: repeat(3, 1fr); /* Three equal columns */
      gap: 20px;
      background-color: #f9f9f9;
      padding: 20px;
    }

    .grid-item {
      background-color: #ddd;
      padding: 30px;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="grid-container">
    <div class="grid-item">1</div>
    <div class="grid-item">2</div>
    <div class="grid-item">3</div>
  </div>
</body>
</html>
```

> 🧩 Grid allows for **track-based layout** (rows and columns), **grid areas**, and **template definitions**. It’s ideal for dashboards, galleries, and multi-section pages.

---

## 📱 Responsive Layouts with Media Queries

Media queries allow your layout to adapt to different screen sizes — essential for mobile-friendly design.

### 🔧 Example 4: Responsive Box

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .responsive-box {
      width: 100%;
      padding: 40px;
      background-color: salmon;
      text-align: center;
    }

    @media (min-width: 600px) {
      .responsive-box {
        background-color: teal;
        padding: 80px;
      }
    }
  </style>
</head>
<body>
  <div class="responsive-box">Resize Me!</div>
</body>
</html>
```

> 📱 Use `min-width` to apply styles when the screen is wide enough. Combine with Flexbox or Grid to rearrange content responsively.

---

## 🧪 Hands-on Mini Challenge — Solution

> **Challenge:** Build a mini portfolio layout using transitions, Flexbox, Grid, and media queries.

**HTML (`portfolio.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Mini Portfolio</title>
  <link rel="stylesheet" href="portfolio.css">
</head>
<body>
  <header class="hero">
    <h1>Jessel</h1>
    <p>Curriculum Designer & Educator</p>
  </header>

  <section class="about">
    <div class="about-item">Narrative-driven pedagogy</div>
    <div class="about-item">Modular walkthroughs</div>
    <div class="about-item">Ethical reporting</div>
  </section>

  <section class="gallery">
    <div class="gallery-item">Project 1</div>
    <div class="gallery-item">Project 2</div>
    <div class="gallery-item">Project 3</div>
    <div class="gallery-item">Project 4</div>
  </section>
</body>
</html>
```

**CSS (`portfolio.css`):**
```css
/* Hero section with transition */
.hero {
  background-color: #4a90e2;
  color: white;
  padding: 60px;
  text-align: center;
  transition: background-color 0.4s ease;
}

.hero:hover {
  background-color: #2c3e50;
}

/* Flexbox for About section */
.about {
  display: flex;
  justify-content: space-around;
  padding: 40px;
  background-color: #f0f0f0;
}

.about-item {
  background-color: #fff;
  padding: 20px;
  border: 1px solid #ccc;
  width: 30%;
  text-align: center;
}

/* Grid for Gallery section */
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  padding: 40px;
  background-color: #fafafa;
}

.gallery-item {
  background-color: #e0e0e0;
  padding: 30px;
  text-align: center;
  transition: transform 0.3s ease;
}

.gallery-item:hover {
  transform: scale(1.05);
}

/* Responsive tweaks */
@media (max-width: 600px) {
  .about {
    flex-direction: column;
    align-items: center;
  }

  .about-item {
    width: 80%;
    margin-bottom: 20px;
  }
}
```

> 🧠 This layout combines all four concepts: transitions, Flexbox, Grid, and responsiveness. Students should inspect each section and explain how layout behaviour changes across screen sizes.

---


## 📱 Session 1 — Principles of Responsive Design

### 📘 Content

---

### 🧠 Learning Objectives

- Understand the goals and mindset behind responsive web design  
- Explore fluid grids, flexible media, and mobile-first thinking  
- Learn how the viewport affects layout and scaling  
- Use percentage-based widths and relative units (`em`, `rem`, `vw`, `vh`)  
- Begin reasoning about layout flexibility across devices  

---

## 🌍 What Is Responsive Web Design?

Responsive Web Design (RWD) is the practice of building websites that **adapt** to different screen sizes and devices. Instead of designing for one fixed layout, we design for **fluidity** and **flexibility**.

### 🔑 Core Principles

1. **Fluid Grids** — Layouts that use percentages instead of fixed pixels  
2. **Flexible Media** — Images and videos that scale with their containers  
3. **Media Queries** — CSS rules that activate based on screen size  
4. **Mobile-First Thinking** — Designing for small screens first, then scaling up  

> 🧠 Why it matters: Users access websites on phones, tablets, laptops, TVs — your layout must respond to their context.

---

## 🔧 Example 1: Fluid Grid with Percentages

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .container {
      width: 100%;                  /* Full width of viewport */
      max-width: 1200px;            /* Prevents stretching too wide */
      margin: 0 auto;
      padding: 20px;
    }

    .column {
      float: left;
      width: 50%;                   /* Two columns side-by-side */
      padding: 10px;
      box-sizing: border-box;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="column" style="background-color: #e0f7fa;">Left Column</div>
    <div class="column" style="background-color: #ffe0b2;">Right Column</div>
  </div>
</body>
</html>
```

> 💡 Percentages allow layout to scale with the screen. `box-sizing: border-box` ensures padding doesn’t break the width.

---

## 🔧 Example 2: Flexible Media

Images should resize with their containers — not overflow or distort.

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .responsive-img {
      max-width: 100%;              /* Prevents overflow */
      height: auto;                 /* Maintains aspect ratio */
      border: 2px solid #ccc;
    }
  </style>
</head>
<body>
  <img src="https://via.placeholder.com/600x300" class="responsive-img" alt="Sample Image">
</body>
</html>
```

> 🧠 This ensures images scale on phones, tablets, and desktops without breaking layout.

---

## 🔍 Viewport and Scaling

The **viewport** is the visible area of a webpage on a device. Mobile browsers often scale pages unless told not to.

### 🔧 Example 3: Viewport Meta Tag

**HTML Head Tag:**
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

> 📐 This tells the browser: “Use the device’s actual width and don’t zoom in.” It’s essential for responsive behaviour.

---

## 📏 Relative Units: `em`, `rem`, `vw`, `vh`

Instead of fixed `px`, we use **relative units** that scale with context.

### 🔧 Example 4: Using Relative Units

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-size: 16px;              /* Base size */
    }

    .text {
      font-size: 1.5em;             /* 1.5 × parent size */
      margin: 5vh 0;                /* 5% of viewport height */
      padding: 2vw;                 /* 2% of viewport width */
      background-color: #f0f0f0;
    }
  </style>
</head>
<body>
  <div class="text">This text uses relative units for spacing and sizing.</div>
</body>
</html>
```

> 🧠 `em` and `rem` scale with font size; `vw` and `vh` scale with viewport dimensions — perfect for responsive spacing.

---

## 🧪 Hands-on Mini Challenge — Solution

> **Challenge:** Build a fluid layout with flexible media and relative units.

**HTML (`challenge.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Responsive Challenge</title>
  <link rel="stylesheet" href="challenge.css">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
  <div class="wrapper">
    <h1>Responsive Design</h1>
    <p>This layout adapts to screen size using percentages and relative units.</p>
    <img src="https://via.placeholder.com/800x400" class="responsive-img" alt="Demo Image">
  </div>
</body>
</html>
```

**CSS (`challenge.css`):**
```css
body {
  font-family: 'Arial', sans-serif;
  font-size: 16px;
  margin: 0;
  padding: 0;
}

.wrapper {
  width: 90%;
  max-width: 1000px;
  margin: 0 auto;
  padding: 2em;
}

.responsive-img {
  max-width: 100%;
  height: auto;
  border: 1px solid #ccc;
}
```

> 🧠 Students should resize the browser and observe how the layout and image respond.

---

## 📘 Homework Prompt — Worked Example with Comments

> **Assignment:** Create a responsive landing page with fluid layout and flexible media.

**HTML (`homework.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Responsive Landing</title>
  <link rel="stylesheet" href="homework.css">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
  <header class="hero">
    <h1>Welcome</h1>
    <p>Design that adapts to every screen.</p>
  </header>

  <section class="content">
    <img src="https://via.placeholder.com/600x300" class="responsive-img" alt="Banner">
    <p>This section uses flexible media and percentage-based layout.</p>
  </section>
</body>
</html>
```

**CSS (`homework.css`):**
```css
body {
  font-family: 'Verdana', sans-serif;
  margin: 0;
  padding: 0;
}

.hero {
  text-align: center;
  padding: 5vh 2vw;
  background-color: #e0f7fa;
}

.content {
  width: 90%;
  max-width: 800px;
  margin: 0 auto;
  padding: 2em;
}

.responsive-img {
  max-width: 100%;
  height: auto;
  margin-bottom: 1em;
}
```

**📝 Comments:**
- `meta viewport` ensures proper scaling  
- Layout uses percentages and `vw/vh` for spacing  
- Image scales with container  
- Page remains readable and balanced across devices  

---


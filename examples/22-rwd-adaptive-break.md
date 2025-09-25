## 📐 Session 2 — Responsive vs Adaptive Design & Breakpoints

### 📘 Content

---

### 🧠 Learning Objectives

- Distinguish between **responsive** and **adaptive** design approaches  
- Understand how **media queries** enable layout changes across screen sizes  
- Explore **breakpoint strategies** for modern devices  
- Learn how to write media queries using `min-width`, `max-width`, and orientation  
- Begin reasoning about layout shifts and content prioritisation  

---

## 🔄 Responsive vs Adaptive Design

### 🔧 Responsive Design

- Uses **fluid layouts** that scale based on screen size  
- Content **reflows** naturally using percentages, `vw`, `vh`, and flexible containers  
- Ideal for modern web development — works across all devices  

### 🔧 Adaptive Design

- Uses **fixed layouts** that switch at specific breakpoints  
- Often loads **different templates** for mobile, tablet, desktop  
- Can be useful for performance or legacy systems, but less flexible overall  

> 🧠 Responsive design is like water — it flows into any container. Adaptive design is like ice cubes — each one fits a specific mould.

---

## 📏 What Are Breakpoints?

Breakpoints are the **thresholds** at which your layout changes. They’re defined using **media queries** and allow you to apply different styles based on screen width, height, or orientation.

### 🔧 Example 1: Basic Media Query

```css
/* Default styles for mobile */
body {
  font-size: 16px;
  background-color: #f0f0f0;
}

/* Styles for tablets and up */
@media (min-width: 768px) {
  body {
    font-size: 18px;
    background-color: #e0f7fa;
  }
}
```

> 📱 This query activates when the screen is **768px or wider** — often used for tablets and desktops.

---

## 📊 Breakpoint Evolution — Then vs Now

### 🕰️ Traditional Breakpoints (circa 2010s)

| Device Type | Width |
|-------------|-------|
| Mobile      | 320px – 480px  
| Tablet      | 768px – 1024px  
| Desktop     | 1024px – 1200px  
| Large Desktop | 1200px+  

These were based on common device sizes like iPhones, iPads, and standard monitors.

### 📱 Modern Breakpoints (2020s+)

| Device Type         | Width Range |
|---------------------|-------------|
| Small Mobile        | 320px – 375px  
| Large Mobile        | 375px – 480px  
| Foldables / Phablets| 480px – 600px  
| Tablets             | 600px – 900px  
| Small Laptops       | 900px – 1200px  
| Large Screens / 4K  | 1200px+  

> 🧠 Devices now include foldables, ultra-wide monitors, and high-DPI tablets — so breakpoints should reflect **content needs**, not just device types.

---

## 🔧 Example 2: Multiple Breakpoints

```css
/* Mobile-first default */
.container {
  padding: 1em;
  font-size: 16px;
}

/* Tablet */
@media (min-width: 600px) {
  .container {
    padding: 2em;
    font-size: 18px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .container {
    padding: 3em;
    font-size: 20px;
  }
}
```

> 📐 This approach scales layout progressively — starting with mobile, then enhancing for larger screens.

---

## 🔄 Orientation and Device Features

Media queries can also target **orientation**, **aspect ratio**, and **resolution**.

### 🔧 Example 3: Orientation Query

```css
@media (orientation: landscape) {
  .banner {
    height: 300px;
    background-color: #c8e6c9;
  }
}
```

> 📱 Useful for tablets or phones that rotate — helps optimise layout for horizontal viewing.

---

## 🧪 Hands-on Mini Challenge — Solution

> **Challenge:** Create a layout that adapts across three breakpoints and changes colour in landscape mode.

**HTML (`breakpoints.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Breakpoint Challenge</title>
  <link rel="stylesheet" href="breakpoints.css">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
  <div class="box">Resize me!</div>
</body>
</html>
```

**CSS (`breakpoints.css`):**
```css
.box {
  padding: 20px;
  text-align: center;
  background-color: #ffccbc;
  font-size: 16px;
}

/* Tablet */
@media (min-width: 600px) {
  .box {
    background-color: #ffe082;
    font-size: 18px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .box {
    background-color: #c5e1a5;
    font-size: 20px;
  }
}

/* Landscape mode */
@media (orientation: landscape) {
  .box {
    border: 2px dashed #333;
  }
}
```

> 🧠 Students should resize their browser and rotate their device to observe layout and style changes.

---

## 📘 Homework Prompt — Worked Example with Comments

> **Assignment:** Build a responsive info panel with three breakpoints and orientation styling.

**HTML (`homework.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Responsive Info Panel</title>
  <link rel="stylesheet" href="homework.css">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
  <section class="info-panel">
    <h2>Responsive Design</h2>
    <p>This panel adjusts padding, font size, and background colour based on screen width and orientation.</p>
  </section>
</body>
</html>
```

**CSS (`homework.css`):**
```css
.info-panel {
  padding: 20px;
  background-color: #e1f5fe;
  font-size: 16px;
  border-radius: 8px;
}

/* Tablet */
@media (min-width: 600px) {
  .info-panel {
    padding: 30px;
    font-size: 18px;
    background-color: #b3e5fc;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .info-panel {
    padding: 40px;
    font-size: 20px;
    background-color: #81d4fa;
  }
}

/* Landscape */
@media (orientation: landscape) {
  .info-panel {
    border: 2px solid #0288d1;
  }
}
```

**📝 Comments:**
- Mobile-first layout with progressive enhancement  
- Breakpoints chosen based on **content needs**, not device labels  
- Orientation styling adds polish for rotated screens  
- Students should test across multiple devices or browser widths  

---

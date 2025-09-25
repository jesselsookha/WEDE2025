## 📱 Session 4 — Media Queries and Device Targeting

### 📘 Content

---

### 🧠 Learning Objectives

- Use media queries to apply styles based on screen size and device characteristics  
- Understand breakpoint strategy and how it affects layout decisions  
- Target specific devices and orientations using media features  
- Apply mobile-first logic to progressively enhance layouts  
- Explore how media queries support accessibility and user experience  

---

## 🔍 What Are Media Queries?

Media queries are CSS rules that apply **conditionally** — based on screen width, height, orientation, resolution, or even device type. They allow your layout to **respond** to the user’s environment.

### 🔧 Basic Syntax

```css
@media (min-width: 768px) {
  /* Styles for screens 768px and wider */
}
```

> 🧠 Think of media queries as “if” statements for your CSS — they activate styles only when conditions are met.

---

## 📏 Breakpoint Strategy — Content First, Not Device First

Rather than designing for specific devices (e.g. “iPhone 12”), we design for **content needs**. Breakpoints should reflect **when the layout starts to break**, not when a device appears.

### 🔧 Example 1: Mobile-First Breakpoints

```css
/* Base styles for mobile */
.card {
  padding: 1em;
  font-size: 16px;
}

/* Tablet breakpoint */
@media (min-width: 600px) {
  .card {
    padding: 2em;
    font-size: 18px;
  }
}

/* Desktop breakpoint */
@media (min-width: 1024px) {
  .card {
    padding: 3em;
    font-size: 20px;
  }
}
```

> 📐 This approach starts with mobile and adds enhancements as screen size increases — a best practice for modern responsive design.

---

## 📊 Modern Breakpoint Ranges

| Category           | Range (approximate) |
|--------------------|---------------------|
| Small Mobile       | 320px – 375px  
| Large Mobile       | 375px – 480px  
| Foldables / Phablets | 480px – 600px  
| Tablets            | 600px – 900px  
| Small Laptops      | 900px – 1200px  
| Large Screens / 4K | 1200px+  

> 🧠 These ranges are flexible — use them as starting points, but test your layout to find the **natural breakpoints**.

---

## 📐 Orientation Targeting

Media queries can also respond to **device orientation** — useful for tablets and phones that rotate.

### 🔧 Example 2: Landscape Styling

```css
@media (orientation: landscape) {
  .banner {
    height: 300px;
    background-color: #c8e6c9;
  }
}
```

> 📱 This allows you to adjust layout or styling when the device is held horizontally — great for banners, carousels, or video sections.

---

## 🧠 Combining Conditions

You can combine multiple media features to target specific scenarios.

### 🔧 Example 3: Tablet in Landscape Mode

```css
@media (min-width: 768px) and (orientation: landscape) {
  .gallery {
    grid-template-columns: repeat(4, 1fr);
  }
}
```

> 🔍 This targets tablets and larger devices when rotated — useful for expanding layouts or showing more content.

---

## 🧪 Hands-on Mini Challenge — Solution

> **Challenge:** Create a layout that adapts across three breakpoints and changes layout in landscape mode.

**HTML (`device-targeting.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Device Targeting Challenge</title>
  <link rel="stylesheet" href="device-targeting.css">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
  <section class="panel">
    <h2>Responsive Panel</h2>
    <p>This panel adjusts padding, font size, and layout based on screen width and orientation.</p>
  </section>
</body>
</html>
```

**CSS (`device-targeting.css`):**
```css
.panel {
  padding: 20px;
  background-color: #e1f5fe;
  font-size: 16px;
  border-radius: 8px;
}

/* Tablet */
@media (min-width: 600px) {
  .panel {
    padding: 30px;
    font-size: 18px;
    background-color: #b3e5fc;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .panel {
    padding: 40px;
    font-size: 20px;
    background-color: #81d4fa;
  }
}

/* Landscape */
@media (orientation: landscape) {
  .panel {
    border: 2px solid #0288d1;
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
    <h2>Device-Aware Design</h2>
    <p>This panel adapts to screen width and orientation using media queries.</p>
  </section>
</body>
</html>
```

**CSS (`homework.css`):**
```css
.info-panel {
  padding: 20px;
  background-color: #fce4ec;
  font-size: 16px;
  border-radius: 8px;
}

/* Tablet */
@media (min-width: 600px) {
  .info-panel {
    padding: 30px;
    font-size: 18px;
    background-color: #f8bbd0;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .info-panel {
    padding: 40px;
    font-size: 20px;
    background-color: #f48fb1;
  }
}

/* Landscape */
@media (orientation: landscape) {
  .info-panel {
    border: 2px dashed #ad1457;
  }
}
```

**📝 Comments:**
- Mobile-first layout with progressive enhancement  
- Breakpoints chosen based on layout needs, not device labels  
- Orientation styling adds polish for rotated screens  
- Students should test across multiple devices or browser widths  

---


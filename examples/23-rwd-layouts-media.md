Absolutely, Jessel — here’s the fully expanded, student-facing version of **Session 3: Responsive Layouts with Flexbox & Grid**, now combining your original Sessions 5, 6, and 7. This version goes deep into layout logic, mobile-first thinking, content prioritisation, and responsive media — with full examples and annotations to support student understanding and recap.

---

## 🧩 Session 3 — Responsive Layouts with Flexbox, Grid, and Media

### 📘 Content

---

### 🧠 Learning Objectives

- Build adaptive containers using Flexbox and Grid  
- Switch layouts responsively across screen sizes  
- Nest layout systems for complex page structures  
- Apply mobile-first design and content prioritisation  
- Use responsive images and media with scaling and accessibility in mind  
- Explore responsive frameworks like Bootstrap for rapid prototyping  

---

## 📐 Flexbox Recap — One-Dimensional Layout

Flexbox is ideal for laying out items in a row or column. It simplifies alignment, spacing, and responsiveness.

### 🔧 Example 1: Flexbox Layout with Wrapping

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .flex-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 20px;
      padding: 20px;
      background-color: #f0f0f0;
    }

    .flex-item {
      flex: 1 1 200px; /* Grow, shrink, base width */
      background-color: #c8e6c9;
      padding: 20px;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="flex-container">
    <div class="flex-item">Item 1</div>
    <div class="flex-item">Item 2</div>
    <div class="flex-item">Item 3</div>
  </div>
</body>
</html>
```

> 🧠 `flex: 1 1 200px` means each item can grow, shrink, and starts at 200px — perfect for responsive wrapping.

---

## 🧮 Grid Recap — Two-Dimensional Layout

Grid is ideal for building structured layouts with rows and columns. It offers precise control over placement and spacing.

### 🔧 Example 2: Grid with Auto-Fit and Minmax

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .grid-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      padding: 20px;
      background-color: #e3f2fd;
    }

    .grid-item {
      background-color: #bbdefb;
      padding: 30px;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="grid-container">
    <div class="grid-item">Card 1</div>
    <div class="grid-item">Card 2</div>
    <div class="grid-item">Card 3</div>
    <div class="grid-item">Card 4</div>
  </div>
</body>
</html>
```

> 🔧 `auto-fit` + `minmax` allows the grid to adapt to screen width — stacking on mobile, spreading on desktop.

---

## 📱 Mobile-First & Content Prioritisation

Mobile-first means designing for small screens first, then enhancing for larger ones. It forces us to prioritise essential content and simplify layout.

### 🔧 Example 3: Mobile-First Layout with Flexbox

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .features {
      display: flex;
      flex-direction: column;
      gap: 20px;
      padding: 20px;
    }

    .feature {
      background-color: #fff3e0;
      padding: 20px;
      border: 1px solid #ccc;
    }

    @media (min-width: 768px) {
      .features {
        flex-direction: row;
      }
    }
  </style>
</head>
<body>
  <section class="features">
    <div class="feature">Speed</div>
    <div class="feature">Security</div>
    <div class="feature">Scalability</div>
  </section>
</body>
</html>
```

> 📐 On mobile, features stack vertically. On tablets and desktops, they sit side-by-side — a classic mobile-first pattern.

---

## 🖼️ Responsive Images and Media

Images must scale with their containers and remain readable across devices. We also consider file size, resolution, and accessibility.

### 🔧 Example 4: Responsive Image with `srcset`

**HTML:**
```html
<img 
  src="small.jpg" 
  srcset="medium.jpg 768w, large.jpg 1200w" 
  sizes="(max-width: 768px) 100vw, 50vw" 
  alt="Responsive Image" 
  style="max-width: 100%; height: auto;">
```

> 🧠 `srcset` lets the browser choose the best image based on screen size. `sizes` tells it how much space the image will occupy.

---

## 🎨 Responsive Video Embed

Videos should scale and maintain aspect ratio.

### 🔧 Example 5: Responsive Video Container

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .video-wrapper {
      position: relative;
      padding-bottom: 56.25%; /* 16:9 aspect ratio */
      height: 0;
      overflow: hidden;
    }

    .video-wrapper iframe {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    }
  </style>
</head>
<body>
  <div class="video-wrapper">
    <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allowfullscreen></iframe>
  </div>
</body>
</html>
```

> 📺 This technique ensures the video scales with the container while preserving its aspect ratio.

---

## ⚙️ Using Responsive Frameworks (Bootstrap)

Bootstrap offers pre-built responsive components and layout utilities. It’s great for rapid prototyping and consistent design.

### 🔧 Example 6: Bootstrap Grid Layout

**HTML (with Bootstrap CDN):**
```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
</head>
<body>
  <div class="container">
    <div class="row">
      <div class="col-md-4">Column 1</div>
      <div class="col-md-4">Column 2</div>
      <div class="col-md-4">Column 3</div>
    </div>
  </div>
</body>
</html>
```

> 🧠 Bootstrap’s grid system uses `container`, `row`, and `col-` classes to build responsive layouts quickly.

---

## 🧪 Hands-on Mini Challenge — Solution

> **Challenge:** Build a responsive layout with Flexbox, Grid, and media. Include a responsive image and a video.

**HTML (`layout-challenge.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Responsive Layout Challenge</title>
  <link rel="stylesheet" href="layout-challenge.css">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
  <header class="hero">
    <h1>Responsive Showcase</h1>
  </header>

  <section class="grid-gallery">
    <div class="item">Card A</div>
    <div class="item">Card B</div>
    <div class="item">Card C</div>
  </section>

  <section class="media-section">
    <img src="https://via.placeholder.com/800x400" alt="Demo Image" class="responsive-img">
    <div class="video-wrapper">
      <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allowfullscreen></iframe>
    </div>
  </section>
</body>
</html>
```

**CSS (`layout-challenge.css`):**
```css
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
}

.hero {
  text-align: center;
  padding: 40px;
  background-color: #4db6ac;
  colour: white;
}

.grid-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  padding: 20px;
}
```
---

**🧠 This layout combines all key concepts:**

- **Flexbox** for responsive horizontal and vertical alignment  
- **Grid** for structured, scalable multi-column layouts  
- **Responsive images** with `max-width: 100%` and `srcset` for device optimisation  
- **Responsive video** using aspect-ratio containers  
- **Mobile-first design** with layout switching via media queries  

Students should test this layout across different screen sizes, rotate their devices, and inspect elements using browser DevTools to understand how each part adapts.

---

## 📘 Homework Prompt — Worked Example with Comments

> **Assignment:** Build a responsive landing page using Flexbox and Grid. Include:
> - A hero section with text and background
> - A feature section using Flexbox
> - A gallery using Grid
> - A responsive image and embedded video

**HTML (`homework.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Responsive Landing Page</title>
  <link rel="stylesheet" href="homework.css">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
  <header class="hero">
    <h1>Welcome to My Portfolio</h1>
    <p>Designs that adapt to every screen.</p>
  </header>

  <section class="features">
    <div class="feature">Fast</div>
    <div class="feature">Flexible</div>
    <div class="feature">Accessible</div>
  </section>

  <section class="gallery">
    <div class="gallery-item">Project A</div>
    <div class="gallery-item">Project B</div>
    <div class="gallery-item">Project C</div>
  </section>

  <section class="media">
    <img src="https://via.placeholder.com/800x400" alt="Responsive Image" class="responsive-img">
    <div class="video-wrapper">
      <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allowfullscreen></iframe>
    </div>
  </section>
</body>
</html>
```

**CSS (`homework.css`):**
```css
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
}

/* Hero section */
.hero {
  text-align: center;
  padding: 60px 20px;
  background-color: #4db6ac;
  colour: white;
}

/* Flexbox features */
.features {
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding: 20px;
  background-color: #f0f0f0;
}

.feature {
  background-color: #fff;
  padding: 20px;
  border: 1px solid #ccc;
  text-align: center;
}

@media (min-width: 768px) {
  .features {
    flex-direction: row;
  }
}

/* Grid gallery */
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  padding: 20px;
  background-color: #e3f2fd;
}

.gallery-item {
  background-color: #bbdefb;
  padding: 30px;
  text-align: center;
}

/* Responsive media */
.responsive-img {
  max-width: 100%;
  height: auto;
  margin: 20px 0;
}

.video-wrapper {
  position: relative;
  padding-bottom: 56.25%;
  height: 0;
  overflow: hidden;
}

.video-wrapper iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
```

**📝 Comments:**
- Layout starts mobile-first and scales up with media queries  
- Flexbox used for feature alignment; Grid used for gallery structure  
- Image and video scale responsively with container  
- Students should test across devices and explain how each section adapts  

---



## 🧱 Session 5 — Responsive Components and Final Challenge

### 📘 Content

---

### 🧠 Learning Objectives

- Build reusable responsive components: cards, banners, menus  
- Apply Flexbox and Grid to structure component layout  
- Use media queries to adapt components across screen sizes  
- Combine transitions, transforms, and responsive media  
- Complete a full-page responsive layout challenge  

---

## 🧩 What Are Responsive Components?

Responsive components are **modular UI blocks** that adapt to screen size and context. They’re the building blocks of modern web design — used in portfolios, dashboards, blogs, and e-commerce sites.

### 🔧 Common Examples

- **Cards** — self-contained blocks with image, text, and actions  
- **Hero banners** — large headers with background images and call-to-action  
- **Navigation menus** — horizontal on desktop, collapsible on mobile  
- **Feature panels** — highlight key content or services  

> 🧠 Components should be flexible, accessible, and visually consistent across devices.

---

## 🧱 Example 1: Responsive Card Component

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .card {
      display: flex;
      flex-direction: column;
      max-width: 300px;
      margin: 20px auto;
      border: 1px solid #ccc;
      border-radius: 8px;
      overflow: hidden;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    }

    .card img {
      width: 100%;
      height: auto;
    }

    .card-content {
      padding: 20px;
    }

    .card-content h3 {
      margin-top: 0;
    }

    @media (min-width: 768px) {
      .card {
        flex-direction: row;
        max-width: 600px;
      }

      .card img {
        width: 50%;
      }

      .card-content {
        width: 50%;
      }
    }
  </style>
</head>
<body>
  <div class="card">
    <img src="https://via.placeholder.com/300x200" alt="Card Image">
    <div class="card-content">
      <h3>Responsive Card</h3>
      <p>This card adapts its layout based on screen size.</p>
    </div>
  </div>
</body>
</html>
```

> 🧠 On mobile, the card stacks vertically. On tablets and desktops, it splits into image and content side-by-side.

---

## 🖼️ Example 2: Hero Banner with Responsive Typography

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .hero {
      background-image: url('https://via.placeholder.com/1200x400');
      background-size: cover;
      background-position: center;
      padding: 60px 20px;
      text-align: center;
      colour: white;
      text-shadow: 1px 1px 4px rgba(0,0,0,0.6);
    }

    .hero h1 {
      font-size: 2em;
    }

    @media (min-width: 768px) {
      .hero h1 {
        font-size: 3em;
      }
    }
  </style>
</head>
<body>
  <header class="hero">
    <h1>Welcome to My Site</h1>
  </header>
</body>
</html>
```

> 📐 Typography scales with screen size, and the background image remains centred and readable.

---

## 📱 Example 3: Responsive Navigation Menu

**HTML + Internal CSS + JS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .nav-header {
      background-color: #333;
      padding: 10px;
      text-align: center;
    }

    .nav-toggle {
      background: #444;
      colour: white;
      padding: 10px;
      border: none;
      font-size: 18px;
      cursor: pointer;
    }

    .nav-links {
      display: none;
      background-color: #222;
      padding: 10px;
    }

    .nav-links.show {
      display: block;
    }

    .nav-links a {
      display: block;
      colour: white;
      text-decoration: none;
      margin: 8px 0;
    }

    @media (min-width: 768px) {
      .nav-toggle {
        display: none;
      }

      .nav-links {
        display: flex;
        justify-content: center;
      }

      .nav-links a {
        margin: 0 15px;
      }
    }
  </style>
</head>
<body>
  <header class="nav-header">
    <button class="nav-toggle" onclick="document.querySelector('.nav-links').classList.toggle('show')">☰ Menu</button>
    <nav class="nav-links">
      <a href="#">Home</a>
      <a href="#">Projects</a>
      <a href="#">Contact</a>
    </nav>
  </header>
</body>
</html>
```

> 📱 On mobile, the menu toggles with a button. On desktop, it displays horizontally.

---

## 🧪 Final Challenge — Responsive Portfolio Page

> **Goal:** Build a full-page responsive layout using components from previous sessions.

**Requirements:**
- Hero banner with responsive text and background  
- Navigation menu that adapts across screen sizes  
- Feature section using Flexbox  
- Gallery using Grid  
- Responsive image and video  
- Media queries for layout switching and orientation  

> 🧠 Students should combine everything they’ve learned — layout, media, transitions, and responsiveness — into one cohesive build.

---

## 📘 Homework Prompt — Worked Example with Comments

> **Assignment:** Create a responsive portfolio page using at least three components.

**HTML (`portfolio.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Responsive Portfolio</title>
  <link rel="stylesheet" href="portfolio.css">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
  <header class="hero">
    <h1>Jessel</h1>
    <p>Curriculum Designer & Educator</p>
  </header>

  <nav class="nav-links">
    <a href="#">Home</a>
    <a href="#">Projects</a>
    <a href="#">Contact</a>
  </nav>

  <section class="features">
    <div class="feature">Narrative Pedagogy</div>
    <div class="feature">Modular Design</div>
    <div class="feature">Ethical Reporting</div>
  </section>

  <section class="gallery">
    <div class="gallery-item">Project A</div>
    <div class="gallery-item">Project B</div>
    <div class="gallery-item">Project C</div>
  </section>
</body>
</html>
```

**CSS (`portfolio.css`):**
```css
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
}

/* Hero */
.hero {
  background-color: #4db6ac;
  colour: white;
  text-align: center;
  padding: 60px 20px;
}

/* Navigation */
.nav-links {
  display: flex;
  justify-content: center;
  background-color: #333;
  padding: 10px;
}

.nav-links a {
  colour: white;
  text-decoration: none;
  margin: 0 15px;
}

/* Features */
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

/* Gallery */
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
```

**📝 Comments:**
- Layout adapts across screen sizes using Flexbox and Grid  
- Components are modular and reusable  
- Students should test on mobile, tablet, and desktop  
- Encourage reflection: “What did I prioritise for small screens?”  

---


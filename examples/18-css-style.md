## 🎨 Session 7 — Typography, Colour, Decoration and Styling Links

### 📘 Content

---

### 🧠 Learning Objectives

- Apply font families, sizes, and spacing for readable and expressive typography  
- Use colour values: named colours, hexadecimal (`#FF5733`), `rgb()`, and `hsl()`  
- Style link states: `:link`, `:visited`, `:hover`, `:active`  
- Add decorative styles: borders, shadows, and background images  
- Integrate Google Fonts and understand font stacks  

---

## 🔡 Typography Foundations

Typography is more than just choosing a font — it’s about creating a visual rhythm that supports readability and tone.

### 🔧 Example 1: Typography Basics

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-family: 'Georgia', serif; /* Elegant serif font for readability */
      font-size: 16px;                /* Base text size */
      line-height: 1.6;               /* Improves spacing between lines */
    }

    h1 {
      font-family: 'Arial', sans-serif; /* Switch font for headings */
      font-size: 32px;
      letter-spacing: 2px;               /* Adds space between letters */
    }

    p {
      font-style: italic;
      color: #333;
    }
  </style>
</head>
<body>
  <h1>Typography Matters</h1>
  <p>This paragraph uses italic styling and inherits the body font.</p>
</body>
</html>
```

> 👀 Students should experiment with font stacks — combining primary fonts with fallbacks — and adjust spacing to suit their site’s tone.

---

## 🎨 Colour Exploration

CSS allows for multiple ways to define colour, each with its own strengths.

### 🔧 Example 2: Colour Values in Action

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .color-demo {
      background-color: #f5f5f5;          /* Hexadecimal colour */
      color: rgb(50, 50, 50);             /* RGB text colour */
      border-left: 6px solid hsl(210, 100%, 40%); /* HSL for accent */
      padding: 10px;
    }
  </style>
</head>
<body>
  <div class="color-demo">
    This box uses multiple colour formats for variety and control.
  </div>
</body>
</html>
```

> 💡 HSL is great for adjusting hue and saturation; RGB is intuitive for mixing light; hex is compact and widely used.

---

## 🔗 Styling Link States

Links change appearance based on user interaction. These states help guide navigation and feedback.

### 🔧 Example 3: Link State Styling

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    a:link {
      color: blue;                       /* Default link */
      text-decoration: none;
    }

    a:visited {
      color: purple;                    /* After being clicked */
    }

    a:hover {
      color: orange;                    /* On mouse hover */
      text-decoration: underline;
    }

    a:active {
      color: red;                       /* While clicking */
    }
  </style>
</head>
<body>
  <p><a href="#">Visit our resource page</a></p>
</body>
</html>
```

> 🎯 Encourage students to add cursor changes (`cursor: pointer`) or background transitions for enhanced interactivity.

---

## 🖼️ Decoration Techniques

Borders, shadows, and backgrounds add visual depth and hierarchy.

### 🔧 Example 4: Borders and Shadows

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .fancy-box {
      border: 2px dashed #888;          /* Decorative border */
      box-shadow: 2px 2px 8px rgba(0,0,0,0.2); /* Subtle shadow for depth */
      padding: 20px;
      background-color: #fff;
    }
  </style>
</head>
<body>
  <div class="fancy-box">
    Look at that lovely box! This styling adds dimension and visual focus.
  </div>
</body>
</html>
```

> 🧠 Borders define edges; shadows create separation and layering — both are key to visual clarity.

---

## 🖼️ Background Images + Typography Layer

Combining background images with styled text requires careful attention to contrast and readability.

### 🔧 Example 5: Hero Banner with Text Overlay

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .hero-banner {
      background-image: url('https://via.placeholder.com/600x200'); /* Example image */
      background-size: cover;
      background-position: center;
      padding: 50px;
      color: white;
      font-size: 24px;
      text-shadow: 1px 1px 4px rgba(0,0,0,0.6); /* Improves readability */
    }
  </style>
</head>
<body>
  <div class="hero-banner">
    Welcome to Our Styled Page!
  </div>
</body>
</html>
```

> ⚠️ Use text shadows and colour overlays to ensure accessibility — especially for users with visual impairments.

---

## 🧪 Hands-on Mini Challenge — Solution

> **Challenge:** Create a stylised signature block with fonts, colours, and link styling.

**HTML (`signature.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Signature Block</title>
  <link rel="stylesheet" href="signature.css">
</head>
<body>
  <div class="signature">
    <h2>Jessel</h2>
    <p>Curriculum Designer & Educator</p>
    <a href="#">View Portfolio</a>
  </div>
</body>
</html>
```

**CSS (`signature.css`):**
```css
.signature {
  font-family: 'Georgia', serif;
  background-color: #f0f0f0;
  padding: 20px;
  border: 1px solid #ccc;
  box-shadow: 2px 2px 6px rgba(0,0,0,0.1);
  width: fit-content;
}

.signature h2 {
  font-size: 28px;
  letter-spacing: 1px;
  margin-bottom: 5px;
}

.signature p {
  font-style: italic;
  color: #555;
}

.signature a {
  display: inline-block;
  margin-top: 10px;
  color: navy;
  text-decoration: none;
}

.signature a:hover {
  color: crimson;
  text-decoration: underline;
}
```

> 🧠 This challenge reinforces typography, colour, and link styling in one cohesive block.

---

## 📘 Homework Prompt — Worked Example with Comments

> **Assignment:** Build a stylised biography page with expressive fonts, colours, and link styling.

**HTML (`bio.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Biography Page</title>
  <link rel="stylesheet" href="bio.css">
</head>
<body>
  <header class="hero">
    <h1>Jessel</h1>
    <p>Educator, Designer, Systems Thinker</p>
  </header>

  <section class="bio">
    <p>I specialise in curriculum design, React Native, and algorithmic thinking. My work blends narrative with modular logic.</p>
    <a href="#">Explore my textbook project</a>
  </section>
</body>
</html>
```

**CSS (`bio.css`):**
```css
body {
  font-family: 'Arial', sans-serif;
  background-color: #fafafa;
  color: #333;
  padding: 40px;
}

.hero {
  background-image: url('https://via.placeholder.com/800x200');
  background-size: cover;
  background-position: center;
  padding: 60px;
  color: white;
  text-align: center;
  text-shadow: 1px 1px 4px rgba(0,0,0,0.6);
}

.bio {
  margin-top: 30px;
  padding: 20px;
  border-left: 4px solid #4CAF50;
  background-color: #fff;
  box-shadow: 0 0 10px rgba(0,0,0,0.05);
}

.bio a {
  color: #0077cc;
  text-decoration: none;
}

.bio a:hover {
  color: #ff5722;
  text-decoration: underline;
}
```

**📝 Comments:**
- Typography uses font stacks and spacing for clarity  
- Colour palette is soft and professional  
- Link styling includes hover feedback  
- Decorative touches (border, shadow) create visual hierarchy  

---

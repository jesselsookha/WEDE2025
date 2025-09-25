## 🎓 Session X — Animation, Transforms, and Responsive Navigation

### 📘 Content

---

### 🧠 Learning Objectives

- Animate elements using `@keyframes` and transition effects  
- Apply CSS transforms: rotate, scale, skew, translate  
- Build responsive navigation menus with media queries  
- Explore mobile-first design patterns and interactivity  

---

## 🎬 CSS Transforms and Transitions

CSS transforms allow you to visually manipulate elements — rotating, scaling, skewing, or moving them. Transitions make these changes smooth and animated.

### 🔧 Example 1: Transform on Hover

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .card {
      width: 200px;
      height: 100px;
      background: coral;
      transition: transform 0.3s ease;
      text-align: center;
      line-height: 100px;
      font-weight: bold;
      colour: white;
    }

    .card:hover {
      transform: rotate(5deg) scale(1.05);
    }
  </style>
</head>
<body>
  <div class="card">Hover for flair!</div>
</body>
</html>
```

> 🎯 Transforms change how an element looks; transitions control *how fast* and *how smoothly* that change happens.

---

## 🕺 CSS Animations with `@keyframes`

Animations allow you to define a sequence of visual changes over time. Unlike transitions, they don’t require user interaction — they run automatically or loop continuously.

### 🔧 Example 2: Bouncing Box Animation

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    @keyframes bounce {
      0%   { transform: translateY(0); }
      50%  { transform: translateY(-20px); }
      100% { transform: translateY(0); }
    }

    .bouncing-box {
      width: 100px;
      height: 100px;
      background-color: steelblue;
      animation: bounce 1s infinite;
      margin: 50px auto;
    }
  </style>
</head>
<body>
  <div class="bouncing-box"></div>
</body>
</html>
```

> 🪩 Try changing the direction (`translateX` or `rotate`), duration (`2s`, `0.5s`), or timing (`ease-in`, `linear`) to explore different effects.

---

## 📱 Responsive Navigation with Media Queries

Navigation menus must adapt to different screen sizes. Media queries allow you to change layout and styling based on device width.

### 🔧 Example 3: Flex-Based Responsive Navigation

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    nav {
      background: #333;
      padding: 10px;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-around;
    }

    nav a {
      colour: white;
      margin: 5px;
      text-decoration: none;
      font-weight: bold;
    }

    @media (max-width: 600px) {
      nav {
        flex-direction: column;
        align-items: center;
      }
    }
  </style>
</head>
<body>
  <nav>
    <a href="#">Home</a>
    <a href="#">Gallery</a>
    <a href="#">Contact</a>
  </nav>
</body>
</html>
```

> 🧠 This layout switches from horizontal to vertical when the screen is narrow — a key principle of mobile-first design.

---

## 🧰 Toggle Menu with Basic JavaScript

To make navigation interactive, we can use JavaScript to show or hide menu items — especially useful for mobile menus.

### 🔧 Example 4: Toggle Menu Interaction

**HTML + Internal CSS + JS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .nav-menu {
      display: none;
      background-color: #444;
      padding: 10px;
    }

    .nav-menu.show {
      display: block;
    }

    button {
      background: #222;
      colour: white;
      padding: 8px;
      border: none;
      cursor: pointer;
    }

    .nav-menu a {
      display: block;
      colour: white;
      text-decoration: none;
      margin: 5px 0;
    }
  </style>
</head>
<body>
  <button onclick="document.querySelector('.nav-menu').classList.toggle('show')">Menu</button>
  <div class="nav-menu">
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
  </div>
</body>
</html>
```

> 📱 This is a simple way to add interactivity. Later, students can explore more advanced toggles using JavaScript events and accessibility features.

---

## 🧪 Wrap-Up Challenge — Solution

> **Challenge:** Build a mobile-friendly navigation with animation and transform effects.

**HTML (`nav-challenge.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Animated Navigation</title>
  <link rel="stylesheet" href="nav-challenge.css">
</head>
<body>
  <header class="nav-header">
    <button onclick="document.querySelector('.nav-links').classList.toggle('show')">☰</button>
    <nav class="nav-links">
      <a href="#">Home</a>
      <a href="#">Projects</a>
      <a href="#">Contact</a>
    </nav>
  </header>
</body>
</html>
```

**CSS (`nav-challenge.css`):**
```css
.nav-header {
  background-color: #333;
  padding: 10px;
  text-align: center;
}

button {
  background: #444;
  colour: white;
  padding: 10px;
  border: none;
  font-size: 18px;
  cursor: pointer;
  transition: transform 0.3s ease;
}

button:hover {
  transform: scale(1.1);
}

.nav-links {
  display: none;
  background-color: #222;
  padding: 10px;
  animation: slideDown 0.4s ease forwards;
}

.nav-links.show {
  display: block;
}

.nav-links a {
  display: block;
  colour: white;
  text-decoration: none;
  margin: 8px 0;
  transition: colour 0.3s ease;
}

.nav-links a:hover {
  colour: #ffcc00;
}

@keyframes slideDown {
  from { opacity: 0; transform: translateY(-10px); }
  to   { opacity: 1; transform: translateY(0); }
}

@media (max-width: 600px) {
  .nav-links {
    text-align: center;
  }
}
```

> 🧠 This combines transitions, transforms, keyframes, and responsive layout — a complete introduction to animated navigation.

---


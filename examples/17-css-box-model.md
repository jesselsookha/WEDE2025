## 📦 Session 6 — Layout: CSS Box Model and Positioning

### 📘 Content

---

### 🧠 Learning Objectives

- Understand the **CSS box model**: content → padding → border → margin  
- Use `width`, `height`, and `border` to manipulate box size and appearance  
- Apply `margin` and `padding` to control spacing  
- Use layout properties: `display`, `float`, `position` (static, relative, absolute, fixed)  
- Inspect box model layers using browser Developer Tools  

---

## 🔍 What Is the CSS Box Model?

Every HTML element is treated as a rectangular box. The **box model** defines how space is calculated around and inside that box.

### 🧱 Box Model Layers

1. **Content** — the actual text or image inside the element  
2. **Padding** — space between content and border  
3. **Border** — the visible edge around the element  
4. **Margin** — space outside the border, separating it from other elements  

---

## 🔧 Practical Example 1: Visualizing the Box Model

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .box {
      width: 300px;                  /* Width of content area */
      height: 150px;                 /* Height of content area */
      padding: 20px;                 /* Space inside box */
      border: 2px solid #4CAF50;     /* Border around box */
      margin: 30px;                  /* Space outside box */
      background-color: #f0f8ff;     /* Light blue background */
    }
  </style>
</head>
<body>
  <div class="box">
    <p>This is a styled box. Notice the padding, border, and margin layers.</p>
  </div>
</body>
</html>
```

> 💡 Tip: Use browser DevTools to inspect this box. Hover over the element and look at the computed styles — you’ll see the padding, border, and margin visualized.

---

## 🔧 Practical Example 2: Floats for Layout

Floats allow elements to sit side-by-side, but they also remove them from the normal document flow — which can cause layout issues if not handled properly.

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .box {
      float: left;                   /* Float left for side-by-side layout */
      width: 45%;
      margin: 2.5%;
      padding: 10px;
      background-color: #eee;
    }

    .clearfix {
      clear: both;                   /* Prevents float overlap with parent */
    }
  </style>
</head>
<body>
  <div class="box">Box 1</div>
  <div class="box">Box 2</div>
  <div class="clearfix"></div>
</body>
</html>
```

> 🧠 Floats are useful for simple layouts, but they require a `.clearfix` element to prevent collapsing of parent containers. This is a legacy technique — Flexbox and Grid are more modern alternatives (covered later).

---

## 🔧 Practical Example 3: Positioning

CSS `position` lets you control where elements appear on the page. There are four main types:

1. **Static** — default flow (no positioning)  
2. **Relative** — moves element relative to its normal position  
3. **Absolute** — positions element relative to nearest positioned ancestor  
4. **Fixed** — positions element relative to the viewport  

**HTML + Internal CSS:**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .static-box {
      position: static;             /* Default positioning */
    }

    .relative-box {
      position: relative;
      left: 20px;                   /* Moves 20px to the right */
      top: 10px;                    /* Moves 10px down */
      background-color: #ffddcc;
    }

    .absolute-box {
      position: absolute;
      top: 100px;
      left: 100px;
      background-color: #ccffdd;
      padding: 10px;
    }

    .container {
      position: relative;           /* Needed for absolute child */
      height: 300px;
      border: 1px solid #333;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="static-box">Static Box</div>
    <div class="relative-box">Relative Box</div>
    <div class="absolute-box">Absolute Box (inside container)</div>
  </div>
</body>
</html>
```

> 🧭 Absolute positioning is powerful but must be used carefully. It removes the element from normal flow and anchors it to the nearest positioned ancestor — in this case, `.container`.

---

## 🔬 DevTools Exercise: Box Model Dissection

Use browser Developer Tools to inspect your layout:

- Click on any box and view the **computed styles** tab  
- Identify the **padding**, **border**, and **margin** visually  
- Toggle between `static`, `relative`, and `absolute` to see how the box moves  
- Try adjusting values live in DevTools to experiment with layout  

> 🧠 This exercise helps students connect theory to practice — they can *see* the box model in action.

---

## 🧪 Hands-on Mini Challenge — Solution

> **Challenge:** Create three styled boxes using padding, border, margin, float, and position.

**HTML (`challenge.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Box Model Challenge</title>
  <link rel="stylesheet" href="challenge.css">
</head>
<body>
  <div class="box float-box">Floating Box</div>
  <div class="box absolute-box">Absolute Box</div>
  <div class="box normal-box">Normal Box</div>
</body>
</html>
```

**CSS (`challenge.css`):**
```css
body {
  position: relative;
  padding: 40px;
}

.box {
  width: 250px;
  height: 120px;
  padding: 20px;
  border: 2px solid #333;
  margin: 20px;
  background-color: #f5f5f5;
}

/* Float example */
.float-box {
  float: left;
  background-color: #dcedc8;
}

/* Absolute positioning */
.absolute-box {
  position: absolute;
  top: 100px;
  left: 300px;
  background-color: #ffccbc;
}

/* Normal flow */
.normal-box {
  clear: both;
  background-color: #bbdefb;
}
```

> 🧠 This layout demonstrates how float and absolute positioning affect flow. Students should inspect each box and explain its behavior.

---

## 📘 Homework Prompt — Worked Example with Comments

> **Challenge:** Build a layout page with three content sections styled as boxes.

**HTML (`homework.html`):**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Layout Homework</title>
  <link rel="stylesheet" href="homework.css">
</head>
<body>
  <div class="card float-card">Floating Card</div>
  <div class="card absolute-card">Absolute Card</div>
  <div class="card regular-card">Regular Card</div>
</body>
</html>
```

**CSS (`homework.css`):**
```css
body {
  position: relative;
  padding: 50px;
}

/* Shared box styles */
.card {
  width: 280px;
  height: 140px;
  padding: 20px;
  border: 2px solid #444;
  margin: 25px;
  background-color: #e0f7fa;
}

/* Float example */
.float-card {
  float: left;
  background-color: #c8e6c9;
}

/* Absolute positioning */
.absolute-card {
  position: absolute;
  top: 150px;
  left: 350px;
  background-color: #ffe0b2;
}

/* Normal flow */
.regular-card {
  clear: both;
  background-color: #f3e5f5;
}
```

**📝 Comments:**
- All cards use padding, border, and margin  
- `.float-card` floats left and sits beside others  
- `.absolute-card` is removed from flow and positioned manually  
- `.regular-card` clears the float and returns to normal flow  

---

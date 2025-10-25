# 🔹 Session 4: DOM Basics — Connecting JavaScript to HTML

## 📘 Introduction: What Is the DOM?

The **Document Object Model (DOM)** is a structured, programming interface for your HTML. When a browser loads a webpage, it does two key things:
1.  **Parses** the HTML to render the page visually.
2.  **Creates the DOM**, a live, tree-like model of the page's structure.

This model is crucial because it's the **bridge** that allows JavaScript, a language that initially had nothing to do with web pages, to dynamically interact with and manipulate the webpage.

Think of the DOM not just as a blueprint, but as a **live, interactive API for your HTML**. Every HTML tag, every attribute, and every piece of text becomes an **object** (a "node") in this tree. JavaScript can access these objects, change their properties, create new ones, or delete them, and the browser will instantly reflect those changes on the screen.

---

## 🧠 Key Concepts and Definitions

| **Keyword**             | **Definition**                                                                 |
|--------------------------|--------------------------------------------------------------------------------|
| **DOM**                  | A programming interface for web documents. It represents the page as a hierarchy of nodes and objects, allowing languages like JavaScript to interact with it. |
| **Node**                 | The fundamental building block of the DOM. Everything is a node: an element (like `<div>`), an attribute, a piece of text, even comments. |
| **DOM Access Method**    | A JavaScript function provided by the browser (like `querySelector`) used to find and select element nodes from the DOM tree. |
| **Event**                | An action or occurrence that happens in the browser, often initiated by the user (e.g., click, scroll, keypress). JavaScript can "listen" for these events to make the page reactive. |
| **`innerText`**          | A property that gets or sets the *visible* text content of a node. It ignores any HTML tags that might be inside the element. |
| **`classList`**          | A powerful property that provides methods (`add()`, `remove()`, `toggle()`) to manipulate the CSS classes of an element. This is the preferred way to change an element's appearance. |

---

## 🧩 Accessing and Manipulating the DOM

### 1. **Accessing Elements: Finding Your Target**

Before you can change anything, you first need to *select* the right element from the DOM tree. JavaScript gives you several tools, each with its own use case.

- `getElementById("id")`: The fastest and most direct method. Since IDs must be unique, this returns a single element. **Best for:** When you need to quickly grab one specific element.
- `querySelector(".class")` or `querySelector("tag")`: The modern, versatile Swiss Army knife. It uses CSS selector syntax (e.g., `".item"`, `"#header"`, `"li"`, `"input[type='text']"`) and returns the *first* matching element. **Best for:** Most situations where you need one element.
- `querySelectorAll("tag")`: Also uses CSS selectors, but returns a **NodeList** (a collection) of *all* matching elements. **Best for:** When you need to work with multiple elements of the same type, like all list items or all buttons. You typically loop through this collection.

### 2. **Changing Content and Style: Making Your Mark**

Once you have a reference to an element, you can command the browser to change it.

- **Content:**
    - `element.innerText = "New text"`: Use this when you only want to change the human-readable text. It will render HTML tags as plain text.
    - `element.innerHTML = "<strong>Bold</strong>"`: Use this when you need to insert actual HTML into the element. **Caution:** This can be a security risk if used with unsanitized user input, but is perfectly safe for your own strings.

- **Appearance:**
    - `element.style.color = "blue"`: Directly manipulates the inline `style` attribute. It's useful for quick, one-off changes but can become messy. For more sustainable styling, using `classList` is better.
    - `element.classList.add("highlight")`: Adds a CSS class. This is powerful because you define the visual rules (colors, size, animation) in your CSS file, and JavaScript simply triggers the change.
    - `element.classList.remove("highlight")`: Removes a specific class.
    - `element.classList.toggle("highlight")`: The most efficient way to switch a state on and off (e.g., showing/hiding a menu, switching a theme).

### 3. **Responding to Events: Making it Interactive**

Events are what transform a static page into an interactive application. The browser "fires" an event, and your JavaScript code can "listen" for it and run a function in response.

- **Common Events:**
    - `click`: The most common user interaction.
    - `mouseover` / `mouseout`: When the cursor enters or leaves an element.
    - `keydown` / `keyup`: When a keyboard key is pressed or released.
    - `submit`: Fired when a form is submitted (e.g., the user hits "enter" or clicks a submit button).

- **The Event Listener:** This is the standard way to handle events. It "attaches" a listener to an element.

```js
// 1. Find the element
let myButton = document.querySelector("#myButton");

// 2. Attach an event listener
myButton.addEventListener("click", function() {
  // 3. This function runs when the event occurs
  console.log("The button was clicked!");
  myButton.classList.toggle("active"); // Example action
});
```
---

## 🧪 In-Class Activity: DOM Lab — Change Text and Style

We built a simple webpage that changes a heading’s text and style when a button is clicked.

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* CSS class to highlight the heading */
    .highlight {
      color: white;
      background-color: teal;
      padding: 10px;
    }
  </style>
</head>
<body>
  <!-- Heading with an ID -->
  <h2 id="title">Welcome to My Page</h2>

  <!-- Button that triggers the change -->
  <button onclick="changeContent()">Click Me</button>

  <script>
    // Function that changes the heading text and style
    function changeContent() {
      const heading = document.getElementById("title"); // Access the heading
      heading.innerText = "You clicked the button!";    // Change the text
      heading.classList.add("highlight");               // Add the CSS class
    }
  </script>
</body>
</html>
```

### 🔍 Code Walkthrough

- `getElementById("title")`: Locates the heading.
- `innerText`: Updates the visible text.
- `classList.add("highlight")`: Applies a new style.

🧠 **Explanation**: This example shows how JavaScript can **read and change** HTML content dynamically. It introduces the core idea of **DOM manipulation** — a skill you’ll use in nearly every interactive webpage.

---

## 🧪 In-Class Activity: Visual DOM Tree Sketch

We visualised the DOM as a tree structure using a simple HTML snippet:

```html
<body>
  <div>
    <h1>Title</h1>
    <p>Paragraph</p>
  </div>
</body>
```

### 🧠 Explanation

- `<body>` is the root node.
- `<div>` is a child of `<body>`.
- `<h1>` and `<p>` are children of `<div>`.

We traced how JavaScript would access `<h1>` using:

```js
document.querySelector("h1");
```

This helped students understand that **every tag is a node**, and JavaScript can navigate this structure like a map.

---

## 🧪 Extra Activity: Paragraph Styler

**Can you create a webpage with a button that changes a paragraph’s text and colour when clicked? Let’s build it step by step.**

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .styled {
      color: darkred;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <p id="info">This is a normal paragraph.</p>
  <button onclick="styleParagraph()">Style Me</button>

  <script>
    function styleParagraph() {
      const para = document.getElementById("info");
      para.innerText = "This paragraph has been styled!";
      para.classList.add("styled");
    }
  </script>
</body>
</html>
```

🧠 **Explanation**:
- This reinforces DOM access and styling.
- Students can experiment by adding more styles or toggling them.

---

## 🧪 Extra Activity: DOM Explorer

**What surprised you about how JavaScript interacts with HTML? Let’s explore it by building a mini DOM explorer.**

```html
<!DOCTYPE html>
<html>
<body>
  <h2 id="heading">DOM Explorer</h2>
  <button onclick="explore()">Reveal Tag Name</button>

  <script>
    function explore() {
      const element = document.getElementById("heading");
      alert(`This element is a <${element.tagName.toLowerCase()}> tag.`);
    }
  </script>
</body>
</html>
```

🧠 **Explanation**:
- `element.tagName` returns the type of HTML tag.
- This activity helps students see that JavaScript can inspect and report on the structure of the page.

---

## 🧾 Summary Recap

- The **DOM** is a tree-like model of your webpage, built from HTML.
- JavaScript uses **access methods** like `getElementById` and `querySelector` to locate elements.
- You can **change content**, **apply styles**, and **respond to events** using DOM manipulation.
- Understanding the DOM is essential for building interactive, responsive websites.

By mastering DOM basics, you’re now ready to build pages that react to users — changing content, updating styles, and creating dynamic experiences.

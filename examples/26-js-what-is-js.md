# 🔹 Session 1: What Is JavaScript and What Can It Do?

## 📘 Introduction to JavaScript

JavaScript is one of the core technologies of web development, alongside HTML and CSS. While HTML provides the structure and CSS defines the style, **JavaScript adds behaviour** — it makes websites interactive and responsive to user actions.

### 🧠 Key Concepts and Definitions

| **Keyword**            | **Definition**                                                                 |
|------------------------|--------------------------------------------------------------------------------|
| **JavaScript (JS)**    | A programming language used to create dynamic and interactive web content.     |
| **HTML**               | HyperText Markup Language — defines the structure of a webpage.                |
| **CSS**                | Cascading Style Sheets — controls the visual appearance of a webpage.          |
| **Interactivity**      | The ability of a webpage to respond to user actions like clicks or typing.     |
| **DOM**                | Document Object Model — a tree-like structure representing HTML elements.       |
| **Client-side JS**     | JavaScript that runs in the browser, interacting directly with the webpage.    |
| **Server-side JS**     | JavaScript that runs on a server (e.g., Node.js), handling data and logic.     |

### 🧩 How JavaScript Fits Into Web Development

Think of a webpage as a human body:

- **HTML** is the skeleton — it gives structure to the page.
- **CSS** is the skin — it makes the page look appealing.
- **JavaScript** is the nervous system — it responds to stimuli and controls behaviour.

JavaScript allows developers to:

- Validate forms before submission.
- Load new content without refreshing the page.
- Animate elements for smoother transitions.
- Create interactive components like dropdowns, modals, and tabs.
- Build games, simulations, and real-time applications.

---

## 🧪 In-Class Activity: Static vs Interactive Page

We explored how JavaScript transforms a static webpage into an interactive experience. Below are two versions of an image gallery — one static, one interactive.

### 🖼️ Static HTML Page

```html
<!-- Static HTML Page -->
<!DOCTYPE html>
<html>
<head><title>Static Page</title></head>
<body>
  <h2>Image Gallery</h2>
  <img src="image1.jpg" width="200">
  <img src="image2.jpg" width="200">
</body>
</html>
```

📝 **Explanation**: This page displays two images, but they don’t respond to user actions. There’s no interactivity — it’s purely visual.

---

### ⚡ Interactive Page with JavaScript

```html
<!-- Interactive Page with JavaScript -->
<!DOCTYPE html>
<html>
<head>
  <title>Interactive Gallery</title>
  <style>
    /* Style for the modal box */
    .modal {
      display: none; /* Hidden by default */
      position: fixed;
      top: 20%;
      left: 30%;
      background: white;
      padding: 20px;
      border: 2px solid #333;
    }
  </style>
</head>
<body>
  <h2>Click an image to enlarge</h2>

  <!-- Images with click events -->
  <img src="image1.jpg" width="200" onclick="showModal('image1.jpg')">
  <img src="image2.jpg" width="200" onclick="showModal('image2.jpg')">

  <!-- Modal box to display enlarged image -->
  <div id="modal" class="modal">
    <img id="modalImg" src="" width="400">
    <button onclick="hideModal()">Close</button>
  </div>

  <script>
    // Function to show the modal with selected image
    function showModal(src) {
      document.getElementById("modalImg").src = src;
      document.getElementById("modal").style.display = "block";
    }

    // Function to hide the modal
    function hideModal() {
      document.getElementById("modal").style.display = "none";
    }
  </script>
</body>
</html>
```

### 🔍 Code Walkthrough

- `onclick="showModal('image1.jpg')"`: Adds an event listener to the image.
- `showModal(src)`: Sets the modal image source and displays the modal.
- `hideModal()`: Hides the modal when the close button is clicked.
- `document.getElementById(...)`: Accesses elements in the DOM.

💬 **Expanded Explanation**: This example introduces two key JavaScript concepts — **event handling** (responding to clicks) and **DOM manipulation** (changing the page content dynamically). These are foundational for building interactive websites.

---

## 🧪 Extra Activity: Revealing a Message with Interaction

**How does interactivity change the way we experience a website?**  
Let’s explore this idea by building a simple message box that appears when a button is clicked.

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    #message {
      padding: 10px;
      background-color: lightblue;
      display: none;
    }
  </style>
</head>
<body>
  <button onclick="showMessage()">Click to Reveal Message</button>
  <div id="message">Interactivity makes websites feel alive and responsive!</div>

  <script>
    // Function to reveal the hidden message
    function showMessage() {
      document.getElementById("message").style.display = "block";
    }
  </script>
</body>
</html>
```

### 🧠 Explanation

- This activity demonstrates how a simple button click can reveal hidden content.
- It reinforces the idea that **interactivity improves engagement** and **user control**.
- Students can modify the message to reflect their own thoughts on interactivity.

---

## 🧪 Extra Activity: Logging Interactive Features

**Think about the websites or apps you use every day. What interactive features make them useful or enjoyable?**  
Let’s build a simple logger to record your observations.

```html
<!DOCTYPE html>
<html>
<body>
  <h2>My Favourite Interactive Features</h2>
  <input type="text" id="site" placeholder="Website or App Name">
  <input type="text" id="feature" placeholder="Interactive Feature">
  <button onclick="logFeature()">Add Feature</button>
  <ul id="featureList"></ul>

  <script>
    // Function to add a new feature to the list
    function logFeature() {
      const site = document.getElementById("site").value.trim();
      const feature = document.getElementById("feature").value.trim();
      if (site && feature) {
        const listItem = document.createElement("li");
        listItem.innerText = `${site}: ${feature}`;
        document.getElementById("featureList").appendChild(listItem);
      }
    }
  </script>
</body>
</html>
```

### 🧠 Explanation

- This activity allows students to reflect on real-world applications of JavaScript.
- It uses **DOM creation** (`createElement`) and **event handling** to build a dynamic list.
- Students can revisit this example when brainstorming features for their own projects.

---

## 🧾 Summary Recap

- JavaScript is the **behaviour layer** of web development.
- It enables **interactivity**, **dynamic content**, and **responsive design**.
- Core concepts introduced: **DOM**, **event handling**, **client-side vs server-side JS**.
- Students practised building interactive pages and explored how JS enhances user experience.

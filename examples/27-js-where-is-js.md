## 📘 Introduction: Understanding Script Placement

When building a webpage, one of the most important decisions you'll make is **where to place your JavaScript code**. This decision affects how quickly your page loads, how smoothly it behaves, and whether your code runs correctly.

JavaScript can be placed in different parts of an HTML document:

- Inside the `<head>` tag
- At the end of the `<body>` tag
- In a separate external `.js` file

Each method has its own purpose, advantages, and potential pitfalls. In this session, we’ll explore these options in depth and learn how to make informed decisions about script placement.

---

## 🧠 Concept 1: Placing JavaScript in the `<head>` Tag

### Why Place JS in the `<head>`?

Placing JavaScript in the `<head>` means the browser will load and execute the script **before** rendering any visible content on the page. This can be useful in specific scenarios:

- **Early Execution**: You might need to define global variables, load configuration settings, or run setup code before anything else appears on the screen.
- **Critical Scripts**: Some libraries (like polyfills or layout tools) need to be loaded early to ensure the page behaves correctly.

However, there’s a major drawback:

- **Blocking Behaviour**: Scripts in the `<head>` block the browser from rendering the page until they are fully downloaded and executed. This can slow down the user experience, especially if the script is large or the internet connection is slow.

### ✅ Example: Script in `<head>`

```html
<head>
  <script>
    // This code runs before the body content is rendered
    console.log("This runs before the page content is loaded.");
  </script>
</head>
```

🧠 **Explanation**: This script logs a message before the page content appears. It’s useful for early setup, but not ideal for interacting with page elements that haven’t loaded yet.

---

## 🧠 Concept 2: Placing JavaScript at the End of the `<body>` Tag

### Why Place JS Before `</body>`?

This is the most common and recommended placement for many use cases. Here’s why:

- **Improved Page Load Time**: The browser can render the HTML content first, making the page appear faster to users.
- **DOM Availability**: By the time the script runs, all HTML elements are already loaded. This means your JavaScript can safely interact with buttons, images, and other elements without causing errors.

### ✅ Example: Script at Bottom of `<body>`

```html
<body>
  <div>Some content</div>
  <button id="myButton">Click me!</button>

  <script>
    // This code runs after the DOM is fully loaded
    document.getElementById("myButton").addEventListener("click", function() {
      alert("Button clicked!");
    });
  </script>
</body>
```

🧠 **Explanation**: This script waits until the page is fully loaded before attaching a click event to the button. It’s safe, efficient, and avoids errors caused by missing elements.

---

## 🧠 Concept 3: Using External JavaScript Files

### Why Use External JS Files?

External scripts are stored in separate `.js` files and linked to your HTML. This approach is considered best practice for most professional web development projects.

Benefits include:

- **Separation of Concerns**: Keeps your HTML clean and focused on structure, while your JavaScript handles behaviour.
- **Reusability**: You can use the same script across multiple pages or projects.
- **Caching**: Browsers can cache external files, reducing load times on repeat visits.
- **Performance**: External files can be served from fast content delivery networks (CDNs), improving global performance.

### ✅ Example: Linking an External JS File

```html
<head>
  <script src="scripts.js"></script>
</head>
<!-- or -->
<body>
  <script src="scripts.js"></script>
</body>
```

🧠 **Explanation**: You can place the external script in either location, but using `defer` is recommended to avoid blocking page rendering.

---

## 🧠 Concept 4: When Should You Use External JS?

External scripts are ideal when:

- You’re using the same code across multiple pages.
- Your script is large or complex.
- You’re integrating third-party libraries (e.g., jQuery, React).
- You want to optimise performance and caching.

---

## 📌 Summary of Use-Cases

| **Placement**         | **Use When…**                                                                 |
|-----------------------|--------------------------------------------------------------------------------|
| `<head>`              | You need to run something **before** the page renders (e.g., configuration).   |
| End of `<body>`       | You’re interacting with DOM elements or want to improve page load speed.       |
| External `.js` file   | You want clean code, reusability, and better performance.                      |

🧠 **Tip**: Use the `defer` attribute when linking external scripts in the `<head>` to ensure they run after the page is parsed.

```html
<head>
  <script src="scripts.js" defer></script>
</head>
```

---

## 🧪 In-Class Activity: Script Placement Lab

We experimented with three types of script placement in one HTML file:

```html
<!DOCTYPE html>
<html>
<head>
  <!-- External script with defer -->
  <script src="external.js" defer></script>
</head>
<body>
  <!-- Inline JavaScript -->
  <button onclick="alert('Inline script triggered!')">Click Me</button>

  <!-- Internal JavaScript -->
  <script>
    function greet() {
      alert("Hello from internal script!");
    }
  </script>
  <button onclick="greet()">Greet</button>

  <!-- External JavaScript -->
  <button onclick="externalGreet()">External Greet</button>
</body>
</html>
```

```js
// external.js
function externalGreet() {
  alert("Hello from external file!");
}
```

### 🔍 Code Walkthrough

- **Inline**: Quick but mixes logic with structure.
- **Internal**: Good for small scripts or testing.
- **External**: Clean, scalable, and preferred for production.

---

## 🧪 Extra Activity: Page Load Alert

**Let’s test how internal scripts behave when placed in the `<head>`. Can you create a script that shows a message as soon as the page opens?**

```html
<!DOCTYPE html>
<html>
<head>
  <script>
    // This script runs immediately when the page loads
    alert("Welcome! The page has loaded.");
  </script>
</head>
<body>
  <h2>Page Load Example</h2>
</body>
</html>
```

🧠 **Explanation**:
- This demonstrates how scripts in the `<head>` execute before the body is rendered.
- For DOM manipulation, consider placing scripts at the end of `<body>` or using `defer`.

---

## 🧪 Extra Activity: External Script Interaction

**Can you create a webpage that uses an external script to change a heading when a button is clicked?**

### HTML File

```html
<!DOCTYPE html>
<html>
<head>
  <script src="changeHeading.js" defer></script>
</head>
<body>
  <h2 id="mainHeading">Original Heading</h2>
  <button onclick="updateHeading()">Change Heading</button>
</body>
</html>
```

### External JS File (`changeHeading.js`)

```js
function updateHeading() {
  const heading = document.getElementById("mainHeading");
  heading.innerText = "Heading Updated!";
}
```

🧠 **Explanation**:
- This reinforces the use of external scripts and DOM access.
- Students can reuse this pattern in future projects.

---

## 🧾 Summary Recap

- JavaScript can be placed **inline**, **internally**, or **externally**.
- **Scripts in `<head>`** run early but may block rendering.
- **Scripts at the end of `<body>`** are ideal for DOM interaction and performance.
- **External scripts** promote clean code, reusability, and caching.
- Use `defer` to load scripts without blocking the page.

By understanding script placement, you’ll write more efficient, maintainable, and error-free JavaScript — a vital skill for any web developer.

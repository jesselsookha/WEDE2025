# 🔹 Session 6: Modern JavaScript Interaction — Events & Feedback

## 📘 Introduction: Making Webpages React

Up to this point, we’ve used JavaScript to change content and styles *programmatically*. But the real power of front-end development is creating interfaces that feel alive and respond to the user. That’s where **events** come in.

An **event** is a signal that something has happened in the browser. This is almost always a user action — clicking a button, typing in a field, hovering over an image, submitting a form. JavaScript can **listen** for these events and **respond** by running a block of code, known as an **event handler**.

This session moves beyond one-off scripts and into creating a continuous, interactive dialogue between your webpage and the user. We'll also focus on a critical part of this dialogue: giving clear, accessible **feedback** so the user always knows what's happening.

---

## 🧠 Key Concepts and Definitions

| **Keyword**             | **Definition**                                                                 |
|--------------------------|--------------------------------------------------------------------------------|
| **Event**                | An object representing an occurrence in the browser. It contains properties about what happened (e.g., which element was clicked, which key was pressed). |
| **Event Listener**       | A method that sets up a function to be called whenever a specified event is delivered to the target element. It's like setting a lookout that waits for a specific signal. |
| **Callback Function**    | The function that is passed as an argument to an event listener. It doesn't run immediately; it's "called back" later when the event occurs. This is a fundamental concept in asynchronous JavaScript. |
| **User Feedback**        | Any response from the system that informs the user of the result of their action. Effective feedback is immediate, clear, and guides the user on what to do next. |
| **Accessibility (a11y)** | The practice of ensuring that interactive elements are usable by everyone, including people who use screen readers or navigate only with a keyboard. This often involves using ARIA attributes and managing focus. |

---

## 🧩 Listening for Events

### 1. **Inline Event Handling (The "Old Way")**

This is the most basic method, where you put JavaScript directly inside your HTML attributes.

```html
<button onclick="doSomething()">Click Me</button>
```

🧠 **Deeper Context & Best Practice**:
- **How it works:** The string inside `onclick` is treated as JavaScript code and executed when the click happens.
- **Why we moved on:** This approach is considered outdated because it **mixes HTML structure with JavaScript behaviour**, making code difficult to manage, debug, and scale. It's like having the wiring for your lights built directly into the walls instead of a neat, separate fuse box. While it's good to recognize it, `addEventListener` is the modern, professional standard.

---

### 2. **Using `addEventListener` (The "Modern Way")**

This is the preferred and most powerful method. It keeps your JavaScript separate from your HTML and offers much more flexibility.

```js
// 1. First, get a reference to the element
const button = document.getElementById("myBtn");

// 2. Attach the listener
button.addEventListener("click", function() {
  // 3. This is the callback function that runs on a click
  alert("Button clicked!");
});
```

🧠 **Deeper Context & Best Practice**:
- **Separation of Concerns:** Your HTML handles structure, CSS handles presentation, and JavaScript (in its own file) handles behaviour. This is a cornerstone of modern web development.
- **Multiple Listeners:** You can attach multiple `addEventListener` calls to the same element for the same event, and they will all run. The old `onclick` method would overwrite itself.
- **The Callback Function:** This can be an anonymous function (like in the example) or a separate, named function. Using a named function can make your code cleaner, especially for complex handlers.

---

### 3. **Common Events**

| **Event Type** | **Description**                                  |
|----------------|--------------------------------------------------|
| `click`        | The most common event. Fires on a full mouse press and release. |
| `mouseover` / `mouseout` | Fires when the mouse pointer enters or leaves an element's area. |
| `keydown` / `keyup` | Fires when a keyboard key is pressed down or released. `keydown` is often used for detecting specific keys. |
| `submit`       | Fires on a `<form>` element, not a button. This is crucial for intercepting form data before it's sent to a server. |
| `change`       | Fires for `<input>`, `<select>`, and `<textarea>` when the user commits a change (e.g., after typing and moving focus, or selecting a dropdown option). |
| `focus` / `blur` | Fires when an element gains or loses keyboard focus. Essential for accessibility and form validation styling. |

---

## 🧩 Giving Feedback to Users

Feedback is the cornerstone of a good user experience. Without it, users are left guessing if their action had any effect.

**Why is feedback critical?**
- **Confirmation:** It confirms an action was received (e.g., "Settings Saved").
- **Guidance:** It directs the user to the next step or informs them of an error.
- **Engagement:** It makes the interface feel responsive and polished.

### Types of Feedback:

- **Visual (The most immediate):**
    - Changing colours (e.g., a button turning green on success).
    - Showing/hiding elements (e.g., a loading spinner, a confirmation message).
    - Adding/removing CSS classes via `classList` to trigger animations or state changes.

- **Textual (The most explicit):**
    - Displaying messages like “Form submitted successfully!” or “Invalid email address”.
    - Updating element `innerText` or `innerHTML` to show status, scores, or results.

- **Accessible (The most inclusive):**
    - **Beyond Colour:** Don't rely on colour alone (e.g., red for error). Also use icons and text, as colourblind users may not perceive the difference.
    - **ARIA Attributes:** Use attributes like `aria-live="polite"` to announce feedback to screen reader users automatically.
    - **Focus Management:** Programmatically move the user's keyboard focus to a new message or back to an error field. This is a pro-level accessibility technique.

🧠 **Best Practices Recap & Expansion**:
- **Be Immediate:** Feedback should happen within **100-200 milliseconds** of the user's action to feel instantaneous.
- **Be Clear and Concise:** The user should instantly understand the message without confusion.
- **Use Modular Functions:** Instead of writing the same feedback code repeatedly, create functions like `showMessage(text, type)` or `toggleLoadingSpinner()`. This keeps your code **DRY (Don't Repeat Yourself)** and much easier to maintain.

---

## 🧪 In-Class Activity: Toggle Visibility

We built a simple webpage that shows or hides a box when a button is clicked.

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* Hidden box style */
    #hiddenBox {
      display: none;
      padding: 10px;
      background-color: lightgray;
    }
  </style>
</head>
<body>
  <!-- Button to toggle visibility -->
  <button id="toggleBtn">Show Box</button>

  <!-- Box that appears/disappears -->
  <div id="hiddenBox">This is a hidden box!</div>

  <script>
    // Access elements
    const btn = document.getElementById("toggleBtn");
    const box = document.getElementById("hiddenBox");

    // Add click event listener
    btn.addEventListener("click", () => {
      if (box.style.display === "none") {
        box.style.display = "block";      // Show box
        btn.innerText = "Hide Box";       // Update button text
      } else {
        box.style.display = "none";       // Hide box
        btn.innerText = "Show Box";       // Update button text
      }
    });
  </script>
</body>
</html>
```

### 🔍 Code Walkthrough

- `addEventListener("click", ...)`: Listens for button clicks.
- `box.style.display`: Checks and changes visibility.
- `btn.innerText`: Updates the button label.

🧠 **Explanation**: This example introduces **event-driven behaviour** and **conditional logic**. It’s the foundation for dropdowns, modals, and interactive components.

---

## 🧪 In-Class Activity: Event Mapping

We sketched a fictional product page and marked where events could occur:

- **Hover over product image** → Zoom effect
- **Click “Add to Cart”** → Confirmation message
- **Submit review form** → Validation and thank-you message

🧠 **Explanation**: This helped students visualise how events power real-world interactions.

---

## 🧪 Extra Activity: Interactive Colour Toggle

**Can you build a button that toggles the background colour of a paragraph when clicked? Let’s try it.**

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .highlight {
      background-color: yellow;
    }
  </style>
</head>
<body>
  <p id="text">Click the button to highlight this text.</p>
  <button id="colourBtn">Toggle Highlight</button>

  <script>
    const para = document.getElementById("text");
    const btn = document.getElementById("colourBtn");

    btn.addEventListener("click", () => {
      para.classList.toggle("highlight"); // Add/remove highlight class
    });
  </script>
</body>
</html>
```

🧠 **Explanation**:
- `classList.toggle(...)`: Adds the class if missing, removes it if present.
- This reinforces event handling and style manipulation.

---

## 🧪 Extra Activity: Simple Quiz with Feedback

**Let’s build a mini quiz that gives feedback when the user selects an answer.**

```html
<!DOCTYPE html>
<html>
<body>
  <h3>What is the capital of South Africa?</h3>
  <button onclick="checkAnswer('Cape Town')">Cape Town</button>
  <button onclick="checkAnswer('Pretoria')">Pretoria</button>
  <button onclick="checkAnswer('Durban')">Durban</button>
  <p id="feedback"></p>

  <script>
    function checkAnswer(choice) {
      const feedback = document.getElementById("feedback");
      if (choice === "Pretoria") {
        feedback.innerText = "Correct!";
        feedback.style.color = "green";
      } else {
        feedback.innerText = "Try again.";
        feedback.style.color = "red";
      }
    }
  </script>
</body>
</html>
```

🧠 **Explanation**:
- This introduces **conditional feedback** based on user input.
- Students can expand this into multi-question quizzes or surveys.

---

## 🧾 Summary Recap

- **Events** are user actions that JavaScript can respond to.
- Use `addEventListener` to attach behaviour to elements.
- Provide **clear feedback** to guide users and confirm actions.
- Design interactions with **accessibility** in mind — not just colour, but also text and structure.

By mastering event listeners and feedback, you’re now able to build webpages that feel responsive, intuitive, and user-friendly — a key skill in modern web development.


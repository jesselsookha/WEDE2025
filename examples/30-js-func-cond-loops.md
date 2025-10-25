# 🔹 Session 5: Functions, Conditionals & Loops

## 📘 Introduction: Programming with Purpose

Up until now, we’ve used JavaScript to manipulate content and respond to user actions. But to build more intelligent behaviour — like calculators, quizzes, or dynamic lists — we need to introduce **logic**.

This session focuses on three core programming structures:

- **Functions**: Reusable blocks of code that perform tasks.
- **Conditionals**: Decision-making structures that choose between actions.
- **Loops**: Structures that repeat actions based on conditions.

Together, these tools allow us to write JavaScript that’s **modular**, **responsive**, and **efficient**.

---

## 🧠 Key Concepts and Definitions

| **Keyword**         | **Definition**                                                                 |
|---------------------|--------------------------------------------------------------------------------|
| **Function**         | A named block of code that performs a specific task and can be reused.         |
| **Parameter**        | A placeholder variable used inside a function.                                 |
| **Return Value**     | The result a function gives back when it finishes running.                     |
| **Conditional**      | A structure that chooses between different actions based on a condition.       |
| **Loop**             | A structure that repeats actions while a condition is true.                    |
| **Iteration**        | One cycle or repetition within a loop.                                         |

---

## 🧩 Functions: Reusable Logic

Functions help you organise your code and avoid repetition. You define a function once and call it whenever needed.

### ✅ Function Syntax

```js
function greet(name) {
  return `Hello, ${name}`;
}
```

- `function`: Keyword to define a function.
- `greet`: Name of the function.
- `name`: Parameter — a placeholder for input.
- `return`: Sends back a result.

### 🧠 Why Use Functions?

- Keeps code **modular** and **readable**.
- Allows **reuse** across multiple parts of your site.
- Makes debugging easier — you can test functions in isolation.

---

## 🧩 Conditionals: Making Decisions

Conditionals allow your code to choose between actions based on logic.

### ✅ `if...else` Example

```js
if (age >= 18) {
  console.log("Adult");
} else {
  console.log("Minor");
}
```

- `if`: Checks a condition.
- `else`: Runs if the condition is false.
- `>=`: Comparison operator (greater than or equal to).

### ✅ `switch` Example

```js
switch (day) {
  case "Monday":
    console.log("Start of the week");
    break;
  case "Friday":
    console.log("Weekend is near");
    break;
  default:
    console.log("Regular day");
}
```

🧠 **Explanation**: `switch` is useful when checking multiple specific values.

---

## 🧩 Loops: Repeating Actions

Loops allow you to repeat code without writing it multiple times.

### ✅ `for` Loop

```js
for (let i = 0; i < 5; i++) {
  console.log(`Count: ${i}`);
}
```

- `i = 0`: Start value.
- `i < 5`: Condition to continue.
- `i++`: Increment after each loop.

### ✅ `while` Loop

```js
let count = 0;
while (count < 3) {
  console.log("Repeating...");
  count++;
}
```

### ✅ `forEach` Loop (for arrays)

```js
const fruits = ["Apple", "Banana", "Cherry"];
fruits.forEach(function(fruit) {
  console.log(fruit);
});
```

🧠 **Explanation**: Loops are essential for working with lists, menus, galleries, and dynamic content.

---

## 🧪 In-Class Activity: Function Lab — Simple Calculator

We built a calculator that adds two numbers entered by the user.

```html
<!DOCTYPE html>
<html>
<body>
  <!-- Input fields for numbers -->
  <input type="number" id="num1" placeholder="Enter first number">
  <input type="number" id="num2" placeholder="Enter second number">

  <!-- Button to trigger calculation -->
  <button onclick="calculate()">Add</button>

  <!-- Paragraph to display result -->
  <p id="result"></p>

  <script>
    // Function to handle button click
    function calculate() {
      const a = parseFloat(document.getElementById("num1").value); // Get first number
      const b = parseFloat(document.getElementById("num2").value); // Get second number
      const sum = add(a, b); // Call add function
      document.getElementById("result").innerText = `Result: ${sum}`; // Display result
    }

    // Function to add two numbers
    function add(x, y) {
      return x + y;
    }
  </script>
</body>
</html>
```

### 🔍 Code Walkthrough

- `parseFloat(...)`: Converts input text to a number.
- `add(x, y)`: Reusable function that returns the sum.
- `innerText`: Updates the result on the page.

🧠 **Explanation**: This activity combines **DOM access**, **functions**, and **arithmetic** — a practical example of modular logic.

---

## 🧪 In-Class Activity: Loop Puzzle — Generate List Items

We used a loop to dynamically create a list of fruits.

```html
<!DOCTYPE html>
<html>
<body>
  <div id="listContainer"></div>

  <script>
    const fruits = ["Apple", "Banana", "Cherry", "Date"];
    let html = "<ul>";

    // Loop through the array
    for (let i = 0; i < fruits.length; i++) {
      html += `<li>${fruits[i]}</li>`; // Add each fruit as a list item
    }

    html += "</ul>";
    document.getElementById("listContainer").innerHTML = html; // Insert list into page
  </script>
</body>
</html>
```

🧠 **Explanation**:
- This loop automates content generation.
- Useful for menus, galleries, or search results.

---

## 🧪 Extra Activity: Age Checker Function

**Can you write a function that checks a person’s age and displays a message based on whether they’re under or over 18?**

```html
<!DOCTYPE html>
<html>
<body>
  <input type="number" id="ageInput" placeholder="Enter your age">
  <button onclick="checkAge()">Check</button>
  <p id="message"></p>

  <script>
    function checkAge() {
      const age = parseInt(document.getElementById("ageInput").value);
      const msg = age >= 18 ? "You are an adult." : "You are a minor.";
      document.getElementById("message").innerText = msg;
    }
  </script>
</body>
</html>
```

🧠 **Explanation**:
- Uses a **ternary operator** (`condition ? true : false`) for concise logic.
- Reinforces conditionals and DOM output.

---

## 🧪 Extra Activity: Loop-Based Content Generator

**How can loops help generate content on large websites? Let’s simulate a dynamic FAQ section.**

```html
<!DOCTYPE html>
<html>
<body>
  <div id="faqSection"></div>

  <script>
    const faqs = [
      "What is JavaScript?",
      "How do I link a script?",
      "What is the DOM?",
      "How do I write a function?"
    ];

    let output = "<h3>FAQs</h3><ul>";

    faqs.forEach(function(question) {
      output += `<li>${question}</li>`;
    });

    output += "</ul>";
    document.getElementById("faqSection").innerHTML = output;
  </script>
</body>
</html>
```

🧠 **Explanation**:
- `forEach` loop creates list items from an array.
- This technique is used in real-world sites to display dynamic content.

---

## 🧾 Summary Recap

- **Functions** allow you to write reusable logic.
- **Conditionals** help your code make decisions.
- **Loops** automate repetition and content generation.
- These tools form the **core logic** of interactive web applications.

By mastering functions, conditionals, and loops, you’re now equipped to build intelligent behaviour — from calculators and quizzes to dynamic lists and responsive interfaces.


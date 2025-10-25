# 🔹 Session 3: Writing JavaScript — Syntax and Basics

## 📘 Introduction: Learning the Language of Interaction

JavaScript is a **programming language**, which means it has its own grammar, vocabulary, and rules. Just like learning a spoken language, you’ll start with basic expressions — variables, data types, operators, and statements — and gradually build up to more complex logic.

This session introduces the **core syntax** of JavaScript and helps you understand how to write simple scripts that perform calculations, display messages, and respond to conditions.

---

## 🧠 Key Concepts and Definitions

| **Keyword**         | **Definition**                                                                 |
|---------------------|--------------------------------------------------------------------------------|
| **Variable**        | A named container used to store data.                                          |
| **Data Type**       | The kind of value a variable holds (e.g., number, string, boolean).            |
| **Operator**        | A symbol that performs a calculation or comparison (e.g., `+`, `===`).         |
| **Statement**       | A complete instruction that performs an action (e.g., assigning a value).      |
| **Expression**      | A combination of values and operators that produces a result.                  |
| **ES6**             | A modern version of JavaScript with cleaner syntax and new features.           |

---

## 🧩 JavaScript Building Blocks

### 1. **Variables**

Variables allow you to store and reuse values. JavaScript offers three ways to declare them:

```js
var name = "Jackson";           // Legacy — function-scoped
let age = 25;                   // Preferred — block-scoped and mutable
const country = "South Africa"; // Block-scoped and immutable
```

🧠 **Explanation**:
- Use `let` when the value might change.
- Use `const` when the value should stay the same.
- Avoid `var` in modern code — it behaves unpredictably in some cases.

---

### 2. **Data Types**

JavaScript supports both **primitive** and **non-primitive** data types.

#### Primitive Types:
- `string`: Text — `"Hello"`
- `number`: Numeric — `42`
- `boolean`: True/false — `true`
- `null`: Intentional absence of value
- `undefined`: Variable declared but not assigned
- `symbol`: Unique identifiers (advanced)
- `BigInt`: Large integers beyond normal limits

#### Non-Primitive Types:
- `object`: Key-value pairs — `{ name: "Lebo" }`
- `array`: Ordered list — `[1, 2, 3]`
- `function`: Reusable block of code

---

### 3. **Operators**

Operators perform actions on values.

#### Arithmetic:
```js
+  // Addition
-  // Subtraction
*  // Multiplication
/  // Division
%  // Modulus (remainder)
```

#### Comparison:
```js
===  // Strict equality
!==  // Strict inequality
<    // Less than
>    // Greater than
```

#### Logical:
```js
&&  // AND
||  // OR
!   // NOT
```

---

### 4. **Statements and Expressions**

A **statement** is a complete instruction:

```js
let x = 5;               // Assignment statement
console.log(x);          // Output statement
```

An **expression** is a combination of values and operators:

```js
x + y                   // Expression that adds two values
```

---

### 5. **Modern ES6 Features**

ES6 (ECMAScript 2015) introduced cleaner syntax:

- **Template Literals**:
  ```js
  const name = "Lebo";
  console.log(`Hello, ${name}`); // ` is the backtick character symbol 
  ```

- **Arrow Functions**:
  ```js
  const double = (x) => x * 2;
  ```

- **Destructuring**:
  ```js
  const user = { name: "Lebo", age: 25 };
  const { name } = user;
  ```

🧠 **Explanation**: These features make your code more readable and expressive. They’re widely used in modern JavaScript development.

---

## 🧪 In-Class Activity: Code Clinic — Mini Challenges

We practised writing small scripts directly in the browser to reinforce syntax and logic.

```html
<!DOCTYPE html>
<html>
<body>
  <script>
    // Challenge 1: Greeting
    const name = "Lebo";
    console.log(`Hello, ${name}!`);

    // Challenge 2: Total Price
    let quantity = 3;
    let price = 50;
    let total = quantity * price;
    console.log(`Total: R${total}`);

    // Challenge 3: Toggle Message
    let show = true;
    if (show) {
      console.log("Message is visible");
    } else {
      console.log("Message is hidden");
    }
  </script>
</body>
</html>
```

### 🔍 Code Walkthrough

- `const name = "Lebo"`: Declares a constant string.
- `let total = quantity * price`: Uses arithmetic to calculate a value.
- `if (show) { ... }`: Uses a conditional to decide what message to show.

🧠 **Explanation**: These challenges help you practise variables, arithmetic, and conditionals — the foundation of all programming logic.

---

## 🧪 In-Class Activity: Syntax Speed Round

We compared older syntax with modern ES6 improvements.

```js
// Broken code
var name = "Sam"
console.log("Hello" + name)

// Refactored ES6
const name = "Sam";
console.log(`Hello, ${name}`);
```

🧠 **Explanation**:
- Template literals (`${name}`) are cleaner and easier to read.
- `const` is preferred over `var` for fixed values.
- Semicolons help avoid unexpected behaviour.

---

## 🧪 Extra Activity: Greeting Script

**Can you write a script that greets the user using a predefined name variable? Let’s build it step by step.**

```html
<!DOCTYPE html>
<html>
<body>
  <script>
    // Define a name variable
    const userName = "Amina";

    // Use template literal to display greeting
    console.log(`Welcome, ${userName}!`);
  </script>
</body>
</html>
```

🧠 **Explanation**:
- This script introduces variable declaration and output using `console.log`.
- You can change the name to test different greetings.

---

## 🧪 Extra Activity: ES6 Syntax Fixer

**Let’s practise identifying and correcting syntax errors using modern JavaScript.**

### Broken Code

```js
var age = 20
console.log("Age is " + age)
```

### Refactored Version

```js
const age = 20;
console.log(`Age is ${age}`);
```

🧠 **Explanation**:
- `const` is used for values that don’t change.
- Template literals improve readability.
- Semicolons mark the end of statements.

---

## 🧾 Summary Recap

- JavaScript syntax includes **variables**, **data types**, **operators**, and **statements**.
- Use `let` and `const` instead of `var` for better control and clarity.
- ES6 features like **template literals** and **arrow functions** make code cleaner.
- Practising small challenges helps build fluency and confidence.

By mastering these basics, you’re now ready to write scripts that interact with the page, respond to user input, and perform calculations — all essential for building dynamic websites.


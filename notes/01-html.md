# 🔹 1: Top-Level HTML Structure

In this session, students are introduced to the **foundational structure of an HTML document**. 
You learn how browsers interpret HTML documents, and how the `<html>`, `<head>`, and `<body>` tags define the page's anatomy. 
This session emphasizes the **role of structure before styling**, and helps you understand why writing properly nested, well-organized HTML is 
crucial.

---

### 🧠 Key Concepts

#### 1. `<!DOCTYPE html>` – The Declaration

This is not a tag, but a **document declaration** that must appear at the very top of an HTML document. It tells the browser:

> "This page follows **HTML5 standards** — render it in **standards mode**."

Without it, browsers might fall back into "quirks mode," where old, inconsistent rules apply.

---

#### 2. `<html>` – The Root Element

Every HTML document is wrapped in a single `<html>` tag. It represents the **entire webpage**, including both what users see and what they don’t.

```html
<html lang="en">...</html>
```

The `lang` attribute specifies the page's language for accessibility and search engines.

---

#### 3. `<head>` – Metadata and Logic

The `<head>` section contains information **about** the page, not the content itself:

* Encoding with `<meta charset="UTF-8">`
* Page title (`<title>`) shown in the browser tab
* Mobile responsiveness via `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
* Linking to CSS `<link rel="stylesheet" href="styles.css">` or favicon files
* Later: Scripts, SEO metadata, and Social Media metadata (Open Graph, Twitter Cards) 

This section doesn’t render visible content on the page.

---

#### 4. `<body>` – Visible Content

This is the **main content area** of a webpage. Everything inside `<body>` gets displayed in the browser window: headings, paragraphs, images, 
forms, etc.

---

### 🧩 Tag Reference Table

| Tag               | Purpose                          | Notes                                 |
| ----------------- | -------------------------------- | ------------------------------------- |
| `<!DOCTYPE html>` | Declares HTML5                   | Always at top; enables standards mode |
| `<html>`          | Root container                   | Wraps the entire page. `lang` helps accessibility & SEO |
| `<head>`          | Metadata section                 | Not visible to users                  |
| `<meta>`          | Info for browsers/search engines | Charset, viewport, author, etc.       |
| `<title>`         | Page title                       | Appears in browser tab & search engine preview |
| `<link>`          | Link to external files           | Commonly used for CSS or favicons     |
| `<style>`         | Internal CSS block               | CSS written directly in HTML          |
| `<script>`	      | JavaScript logic	               | Usually placed before `</body>` or in `<head>` with `defer` |
| `<body>`          | Visible content                  | Everything seen by the user           |

---

### 💻 Code Example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Web Page</title>
  </head>
  <body>
    <h1>Hello, Web!</h1>
    <p>This is the body where content lives.</p>
  </body>
</html>
```

---

# 🔹 2: HTML Attributes and Semantics

This session introduces **HTML attributes**, which allow us to configure elements by adding extra information. Attributes define things like 
the destination of a link, the file path for an image, or even simple behaviors like tooltips.

More importantly, we start laying the groundwork for **semantic thinking** — how we structure HTML in a way that’s readable by both humans and
machines.

---

### 🧠 Key Concepts

#### 1. Attribute Anatomy

Attributes always follow the format:

```html
name="value"
```

* They are placed **inside opening tags** and never on closing tags.
* Attribute values must be in quotes.
* Some attributes are boolean, meaning their presence is enough (e.g., `disabled`, `checked`).

Example:

```html
<img src="dog.jpg" alt="A dog playing in the pool">
```

---

#### 2. Informational vs. Functional Attributes

* **Informational**: Provide descriptions (like `alt`, `title`, `lang`) (Describe or identify an element)
* **Functional**: Direct behavior (like `href`, `src`, `target`) (Affect behaviour (e.g., where a link goes)

This distinction helps students understand when they're affecting *what something is* versus *what it does*.

---

#### 3. Semantic Meaning

Semantics in HTML means using the **right element for the right purpose**, not just what "looks right." For example:

* Use `<strong>` instead of `<b>` for importance
* Use `<em>` instead of `<i>` for emphasis
* Descriptive `alt` text improves accessibility

Future reference: 
* Navigation bar	`<nav>` instead of `<div class="nav">`
* Section of content	`<section>` instead of 	`<div>`
* Article or post	`<article>`	instead of `<div>`

This mindset supports better SEO, screen reader usability, and future maintainability.

---

### 🧩 Attribute Summary Table

| Attribute          | Commonly Used On    | Description                                       |
| ------------------ | ------------------- | ------------------------------------------------- |
| `src`              | `<img>`, `<script>` | Path to external resource                         |
| `alt`              | `<img>`             | Description for images (accessibility + SEO)      |
| `href`             | `<a>`, `<link>`     | Target URL                                        |
| `target`           | `<a>`               | Determines where to open link (`_blank`, `_self`) |
| `title`            | Most elements       | Tooltip when hovering                             |
| `width` / `height` | `<img>`, `<video>`  | Controls visible size                             |
| `id`               | Most elements       | Unique identifier for styling or linking          |
| `class`            | Most elements       | Group elements for CSS or JS                      |
 
---

### 💻 Code Example

```html
<!-- Image with descriptive text and size -->
<img src="cat.jpg" alt="A sleepy cat on a couch" title="Cute Cat" width="300">

<!-- Link that opens in new tab -->
<a href="https://example.com" target="_blank" title="Visit external site">Visit Example</a>
```

---

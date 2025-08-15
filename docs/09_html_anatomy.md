## ✅ Structural Review: “The Anatomy of a Web Page”
[Link to webpage](https://github.com/jesselsookha/WEDE2025/blob/main/examples/11-html-anatomy.html)

### 📌 **Top-Level Layout**

```html
<body>
  <header>...</header>
  <main>...</main>
  <footer>...</footer>
</body>
```

* This is the **classic semantic layout**:

  * `<header>`: Contains site identity and navigation.
  * `<main>`: Main content unique to this page (not repeated sitewide).
  * `<footer>`: Site-wide or page-specific footer content.

💡 This layout makes it easy for **screen readers**, **search engines**, and **developers** to understand **the role of each section** of the page.

---

### 🔝 **Header Section**

```html
<header>
  <h1>...</h1>
  <p>...</p>
  <nav>...</nav>
</header>
```

* Contains:

  * A main heading (`<h1>`) identifying the page.
  * A short description.
  * A `<nav>` menu for internal navigation using anchor links (`<a href="#section-id">`).

✅ **Why this works:**

* The `<nav>` element semantically tells browsers and assistive tech “this is a navigation menu.”
* Internal anchor links create smooth intra-page navigation — a best practice for long-form or educational content.

---

### 🧱 **Main Content Sections**

Each section inside `<main>` represents **distinct, meaningful content**, using the `<section>` tag.

```html
<main>
  <section id="introduction">...</section>
  <section id="lists">...</section>
  <section id="links">...</section>
  ...
</main>
```

✅ **Why this works:**

* `<section>` is used for logically grouped content that could stand on its own with a heading.
* Use of `id` attributes makes sections linkable (useful for anchor links).

Let’s break down some notable internal structures within `<main>`:

---

### 🗂️ **Lists Section**

```html
<ol> ... </ol>
<ul> ... </ul>
<dl> ... </dl>
```

This section clearly organizes different list types:

* Ordered steps (`<ol>`)
* Unordered features (`<ul>`)
* Term/definition pairs (`<dl>`, `<dt>`, `<dd>`)

✅ The semantic structure reflects the type of data, helping both readers and machines parse it correctly.

---

### 🔗 **Links Section**

Demonstrates a range of hyperlink types:

* External (`target="_blank"`)
* Internal section jumps
* Email (`mailto:`)
* Top-of-page link

✅ This shows thoughtful integration of navigation for both usability and interactivity.

---

### 🖼️ **Image Section with `<figure>`**

```html
<figure>
  <img src="..." alt="...">
  <figcaption>...</figcaption>
</figure>
```

* `figure` groups the image and its caption together.
* `figcaption` explains or describes the image.

✅ A great example of media semantics — improves both accessibility and SEO.

---

### 📊 **Table Section**

```html
<table>
  <caption>...</caption>
  <thead>...</thead>
  <tbody>...</tbody>
  <tfoot>...</tfoot>
</table>
```

* Structurally correct and accessible.
* `caption` provides a title.
* Head/body/footer separation clarifies structure.

✅ Very effective for screen readers and data parsing.

---

### 📝 **Form Section**

Uses `<form>`, `<fieldset>`, and `<legend>` to create grouped input fields.

```html
<form>
  <fieldset>
    <legend>...</legend>
    ...
  </fieldset>
</form>
```

✅ This is a best practice:

* Grouping related inputs.
* Enhances usability and accessibility.
* Labels are correctly associated with inputs via `for` / `id`.

---

### 📰 **Article Section**

```html
<article>...</article>
<aside>...</aside>
```

* `<article>`: Independent, standalone content (e.g., blog post, news item).
* `<aside>`: Tangential or complementary content — not essential to the main flow.

✅ This usage perfectly models real-world publishing content structures.

---

### 📎 **Footer**

```html
<footer>
  <p>&copy; 2025 ...</p>
</footer>
```

* Contains ownership and navigation back to top.
* Ends the document with a clear boundary.

✅ Semantically marks the conclusion of the content.

---

## 🧠 Summary: Why This Structure Works

| Element     | Role / Purpose                                             |
| ----------- | ---------------------------------------------------------- |
| `<header>`  | Introduces the page, includes navigation.                  |
| `<nav>`     | Helps users move around the document.                      |
| `<main>`    | Central area for meaningful content.                       |
| `<section>` | Breaks up content logically, each with a heading.          |
| `<article>` | Independent content that can stand alone (blog post/news). |
| `<aside>`   | Related, supporting content like tips or trivia.           |
| `<footer>`  | Wraps up the page — credits, links, copyright.             |

---

### ✅ Final Thoughts

* Use **semantic HTML** not for style, but to give **meaning** and **structure**.
* This makes your HTML:

  * More **accessible**
  * Easier to **maintain**
  * Better for **search engines** and **screen readers**
* Think of HTML like outlining an essay: the tags are your **headings, paragraphs, and sections**.

Let me know if you’d like this exported as a PDF or adapted into a printable lesson summary.


### 📘 **Website File Structure and Visual Studio Code**

**Sessions Covered:**
🔹 Session 1 – Website File Structure
🔹 Session 2 – Visual Studio Code Setup
🔹 Session 3 – First HTML Page in VS Code

---

## 🔹 Session 1: Building Good Habits — Website File Structure

### 🎯 Learning Outcome:

Understand how to organize a basic website project into a clear, scalable folder structure.

### 💬 Why File Structure Matters:

When building websites, it’s not just about writing code — it’s also about **staying organized**. A clean folder structure helps:

* **Project Growth**: Your project might begin with one file, but it will grow. A good structure helps you scale.
* **Teamwork**: When others join your project, consistent naming and folders help everyone know where things go.
* **Troubleshooting**: It's easier to debug and maintain a site when you know exactly where to look.

---

### 📁 Common Folder Types

Here’s a typical structure for a small website project:

```
my-website/
├── index.html
├── pages/
│   └── about.html
├── styles/
│   └── main.css
├── scripts/
│   └── app.js
└── assets/
    ├── images/
    │   └── logo.png
    └── fonts/
```

| Folder       | Purpose                                             |
| ------------ | --------------------------------------------------- |
| `index.html` | Main landing page of the site                       |
| `pages/`     | Other pages like `about.html`, `contact.html`       |
| `styles/`    | CSS files to control layout and design              |
| `scripts/`   | JavaScript files that add behaviour and interaction |
| `assets/`    | Static media like images, fonts, downloads          |

🧠 *Think of it like organizing your school bag — each subject (content type) has its own folder.*

---

### ✍️ Naming Conventions

Keep your file and folder names:

* ✅ lowercase (helps with compatibility on different systems)
* ✅ hyphenated (e.g., `main-style.css`, not `main_style.css` or `MainStyle.css`)
* ✅ no spaces or special characters
* ✅ descriptive (e.g., `hero-banner.jpg` instead of `image1.jpg`)

---

### 👩‍💻 In-Class Activity: Build a Folder Structure

* Create a new folder in Windows Explorer called `simpleWebsite`
* Open it in **Visual Studio Code**
* Inside it, create the structure shown above
  🔧 This builds habits for organizing every future web project.

---

### 🧩 Bonus Challenge: Fix the Mess

Students are shown a disorganized set of files (e.g., all lumped together or poorly named).
Their task: **Reorganize** the project using best practices learned in class.

---

## 🔹 Session 2: Installing & Exploring Visual Studio Code

### 🎯 Learning Outcome:

Install VS Code and explore its key features and tools for efficient web development.

---

### 💻 Why Use Visual Studio Code?

| Feature           | Why It Helps                                     |
| ----------------- | ------------------------------------------------ |
| Lightweight       | Runs fast even on basic hardware                 |
| Customizable      | Add extensions to suit your workflow             |
| Popular           | Used by professionals, so your skills will scale |
| Beginner Friendly | Easy to install, navigate, and personalize       |

VS Code is like the **Swiss Army knife** for web development — flexible, powerful, and easy to use.

---

### 🛠️ Key Features You Should Know

* **Syntax highlighting**: Makes your code easier to read
* **IntelliSense / Autocomplete**: Helps you write code faster, with fewer mistakes
* **Multi-cursor editing**: Edit multiple lines at once
* **Emmet shorthand**: Type less, code more (e.g., `ul>li*5` creates a list with 5 items!)
* **Integrated terminal**: Run commands without leaving VS Code

---

### ⭐ Recommended Extensions

| Extension       | What It Does                                                 |
| --------------- | ------------------------------------------------------------ |
| **Live Server** | Instantly preview your site in the browser (auto-refreshes!) |
| **Prettier**    | Automatically formats your code for neatness                 |
| **CSS Peek**    | Jump from HTML to CSS definitions instantly                  |

🔌 *Extensions = upgrades for your editor. Students installed these in class.*

---

### 🔎 Homework: Extension Hunt

Students were asked to:

* Browse the VS Code Extension Marketplace
* Install one tool that improves their workflow
* Write a short reflection: What did it do? Was it helpful?

📝 *Still to follow up and share discoveries as a group!*

---

### ⚖️ Case Study: VS Code vs. Other Editors

Students discussed:

> Why do developers choose VS Code over Notepad, Notepad++, or Brackets?

Answers included: better performance, more community support, and modern tooling.

---

## 🔹 Session 3: First HTML Page in VS Code

### 🎯 Learning Outcome:

Write a simple HTML page using VS Code and preview it in the browser using Live Server.

---

### 🏗️ Writing Basic HTML Boilerplate

In VS Code:

* Type `!` and press `Tab` → generates an HTML5 boilerplate
* Understand structure:

  * `<!DOCTYPE html>`
  * `<html>` → main container
  * `<head>` → metadata, title, links to CSS
  * `<body>` → what users actually see

---

### 🌐 Preview with Live Server

* Right-click your HTML file → **Open with Live Server**
* Browser opens with a live preview
* Save your file → page refreshes automatically!

💡 *Live Server creates a local development server — useful for testing dynamic content later (like JavaScript).*

---

### ⌨️ Handy VS Code Shortcuts

| Shortcut           | What It Does                              |
| ------------------ | ----------------------------------------- |
| `Ctrl + /`         | Comment/uncomment a line                  |
| `Alt + Shift + F`  | Auto-format the document                  |
| `Ctrl + B`         | Toggle sidebar visibility                 |
| `Ctrl + P`         | Quick open any file                       |
| `Ctrl + Shift + E` | Go to File Explorer panel                 |
| Split View         | Open and edit multiple files side-by-side |

---

### 🎉 In-Class Activities

1. **Mini Sprint**:
   Students created a simple homepage (`index.html`) with:

   * A heading (`<h1>`)
   * A paragraph (`<p>`)
   * An image (`<img>`)

2. **Live Editing Relay**:
   In pairs, one student wrote a basic page. The other improved it by:

   * Adding proper structure
   * Adding comments
   * Fixing indentation or typos

---

### 🧠 HTML Boilerplate Breakdown

Students examined what each part of the HTML template does and how VS Code helps reduce repetitive typing through:

* Emmet shorthand
* Snippets
* Code suggestions

---

## ✅ Summary: What Students Should Now Be Able to Do

| Skill                                 | Outcome                                                     |
| ------------------------------------- | ----------------------------------------------------------- |
| Organize project files                | Use folders like `assets/`, `styles/`, and `pages/`         |
| Use good file naming conventions      | Consistent, lowercase, no spaces or special characters      |
| Install & navigate Visual Studio Code | Understand basic panels, tabs, and sidebar                  |
| Add useful extensions                 | Live Server, Prettier, CSS Peek, and more                   |
| Write basic HTML in VS Code           | Use boilerplate, structure content, preview live in browser |
| Use common IDE shortcuts              | Work faster and cleaner                                     |

---

### 🔍 Reflection Questions 

* Why is a clear file structure important in web development?
* Which VS Code feature or extension made your life easier?
* What was tricky about writing your first HTML page?
* What do you want to explore or improve next?

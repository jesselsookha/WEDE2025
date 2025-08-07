# 🔹 **Session: Linking & Embedding Social Media in HTML**

---

## 🎯 **Session Goals**

By the end of this session, you will:

* Understand how to add social media links using standard HTML `<a>` tags
* Learn how to embed posts, videos, or profiles from social platforms
* Know the differences between linking and embedding
* Discover how to add “share” buttons so visitors can share your content on social media
* Explore examples for LinkedIn, Instagram, TikTok, BlueSky, Facebook, and more

---

# 🔸 **Part 1: Linking to Social Media Profiles**

---

## ✅ Using the `<a>` Tag for Profile Links

The most basic way to connect your website to your social media is by linking to your profiles.

### Example:

```html
<a href="https://www.linkedin.com/in/yourprofile" target="_blank" rel="noopener noreferrer">
  LinkedIn Profile
</a>
```

---

### 🎯 Important Attributes:

| Attribute                   | Purpose                                                |
| --------------------------- | ------------------------------------------------------ |
| `href`                      | URL to the social media profile                        |
| `target="_blank"`           | Opens the link in a new tab (good practice)            |
| `rel="noopener noreferrer"` | Security and performance when using `_blank`           |
| `title` (optional)          | Gives additional info on hover, improves accessibility |

---

### ✅ How to Add Social Icons?

Instead of plain text, it’s common to add **social media icons** as links.

Example using icons (you can use free icon libraries like Font Awesome):

```html
<a href="https://www.instagram.com/yourprofile" target="_blank" rel="noopener noreferrer" title="Instagram">
  <img src="instagram-icon.png" alt="Instagram Logo" width="32" height="32">
</a>
```

---

### 🎯 Why link to social profiles?

* Builds credibility and trust
* Helps visitors connect with you on other platforms
* Increases brand visibility

---

# 🔸 **Part 2: Embedding Social Media Content**

---

## ✅ What is Embedding?

Embedding means showing **posts, videos, or feeds** from social platforms directly inside your webpage.

---

### 🔹 Examples of Embedded Content:

| Platform  | What can be embedded?      | Method                                     |
| --------- | -------------------------- | ------------------------------------------ |
| LinkedIn  | Company updates, posts     | Embed code, LinkedIn plugins               |
| Instagram | Photos, videos, stories    | Embed code via Instagram’s sharing options |
| TikTok    | Videos                     | TikTok’s embed widget                      |
| BlueSky   | (Emerging) posts, profiles | TBD, often via embed code or APIs          |
| Facebook  | Posts, videos, pages       | Facebook’s embed code and plugins          |

---

### ✅ How to get embed code:

Most social platforms provide an “Embed” option when you click the share or options menu on a post/video. This gives you a block of HTML code you can paste into your page.

---

### 🎯 Example: Embedding an Instagram Post

1. Find the post on Instagram (desktop)
2. Click the “…” (more) button
3. Select “Embed”
4. Copy the code and paste into your HTML:

```html
<blockquote class="instagram-media" data-instgrm-permalink="https://www.instagram.com/p/yourpostid/" data-instgrm-version="14" style="max-width:540px; margin: auto;">
</blockquote>
<script async src="//www.instagram.com/embed.js"></script>
```

---

### 🎯 Example: Embedding a TikTok Video

1. Find the TikTok video
2. Click “Share” → “Embed”
3. Copy the code:

```html
<blockquote class="tiktok-embed" cite="https://www.tiktok.com/@username/video/1234567890" data-video-id="1234567890" style="max-width: 605px;min-width: 325px;" >
  <section> </section>
</blockquote>
<script async src="https://www.tiktok.com/embed.js"></script>
```

---

### ✅ Note on Scripts:

Embedded content often requires adding `<script>` tags to your page to load platform-specific JavaScript that renders the embedded post correctly.

---

# 🔸 **Part 3: Sharing from Your Website to Social Media**

---

## ✅ What Does “Sharing” Mean?

Sharing lets your website visitors **post links or content from your site directly to their social media** — for example, sharing your blog post on Facebook or Twitter.

---

### ✅ How to Add Share Links

You can create share buttons using simple hyperlinks that open the sharing dialog of each social platform.

---

### 🔹 Examples:

| Social Platform | Share Link Template                                       | Example                                                                                           |
| --------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Facebook        | `https://www.facebook.com/sharer/sharer.php?u=URL`        | `https://www.facebook.com/sharer/sharer.php?u=https://yourwebsite.com/page.html`                  |
| LinkedIn        | `https://www.linkedin.com/sharing/share-offsite/?url=URL` | `https://www.linkedin.com/sharing/share-offsite/?url=https://yourwebsite.com/page.html`           |
| Twitter         | `https://twitter.com/intent/tweet?url=URL&text=TEXT`      | `https://twitter.com/intent/tweet?url=https://yourwebsite.com/page.html&text=Check%20this%20out!` |
| TikTok          | (No direct sharing URL; share manually via app)           | N/A                                                                                               |
| BlueSky         | (Currently limited support)                               | TBD                                                                                               |

---

### 🔹 How to implement a Facebook share button:

```html
<a href="https://www.facebook.com/sharer/sharer.php?u=https://yourwebsite.com/page.html" target="_blank" rel="noopener noreferrer" title="Share on Facebook">
  Share on Facebook
</a>
```

---

### 🔹 Twitter with Pre-filled Text:

```html
<a href="https://twitter.com/intent/tweet?url=https://yourwebsite.com/page.html&text=Check%20out%20this%20awesome%20site!" target="_blank" rel="noopener noreferrer" title="Share on Twitter">
  Share on Twitter
</a>
```

---

# 🔸 **Part 4: Platform-Specific Notes & Tips**

---

| Platform  | Embedding Notes                                                | Sharing Notes                                     |
| --------- | -------------------------------------------------------------- | ------------------------------------------------- |
| LinkedIn  | Can embed posts, but API is limited for personal accounts      | Use LinkedIn sharing URL for easy sharing         |
| Instagram | Only **public** posts can be embedded; no official sharing URL | No official share URL; users share manually       |
| TikTok    | Provides embed code for videos                                 | No URL-based share; users share via app           |
| BlueSky   | Emerging platform; embeds and shares are evolving              | Currently limited, monitor updates                |
| Facebook  | Powerful embed options; page plugins, video embeds             | Simple share URLs, plus official SDKs for buttons |

---

# 💡 **Accessibility & Performance Tips**

* Always include **`title` attributes** on links for screen readers
* Use `rel="noopener noreferrer"` with `target="_blank"` for security
* Use **lazy loading** for embedded content where possible (e.g., `loading="lazy"` on `<iframe>`)
* Provide fallback links or text when embed scripts fail to load

---

# 🧑‍💻 **Hands-On Exercises**

---

### 🔧 Exercise 1: Link Your Social Profiles

Create links to your LinkedIn, Instagram, and Facebook profiles with icons.

---

### 🔧 Exercise 2: Embed a TikTok Video

Find a public TikTok video and embed it into a simple webpage.

---

### 🔧 Exercise 3: Add Share Buttons

Add Facebook and Twitter share buttons on your blog post page.

---

# 🔍 **Reflection Questions**

* What’s the difference between linking a profile and embedding a post?
* Why might you want to embed content instead of just linking it?
* What security or accessibility issues arise from embedding third-party content?
* How do “share” links improve traffic and engagement?

---

# 📚 **Resources for Further Study**

* [LinkedIn Developer Documentation](https://docs.microsoft.com/en-us/linkedin/)
* [Instagram Embed Guide](https://developers.facebook.com/docs/instagram/oembed)
* [TikTok Embed Guide](https://developers.tiktok.com/doc/embed-videos)
* [Facebook Sharing Docs](https://developers.facebook.com/docs/sharing/web)
* [BlueSky Official Site](https://blueskyweb.xyz/) (Watch for updates on embed/share features)
* [Creating Social Share Links](https://css-tricks.com/snippets/html/social-media-share-links/)

---

# 🔹 **Template 1: Social Media Profile Links with Icons**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Social Media Profile Links</title>
  <style>
    /* Simple styling for icons */
    .social-links a {
      margin: 0 10px;
      display: inline-block;
      text-decoration: none;
    }
    .social-links img {
      width: 40px;
      height: 40px;
      vertical-align: middle;
    }
  </style>
</head>
<body>

  <h1>Connect with Me on Social Media</h1>

  <div class="social-links">
    <!-- Replace href with your own profile URLs -->

    <a href="https://www.linkedin.com/in/yourprofile" target="_blank" rel="noopener noreferrer" title="LinkedIn Profile">
      <img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" alt="LinkedIn Logo" />
    </a>

    <a href="https://www.instagram.com/yourprofile" target="_blank" rel="noopener noreferrer" title="Instagram Profile">
      <img src="https://cdn-icons-png.flaticon.com/512/174/174855.png" alt="Instagram Logo" />
    </a>

    <a href="https://www.facebook.com/yourprofile" target="_blank" rel="noopener noreferrer" title="Facebook Profile">
      <img src="https://cdn-icons-png.flaticon.com/512/174/174848.png" alt="Facebook Logo" />
    </a>
  </div>

</body>
</html>
```

---

# 🔹 **Template 2: Embedding an Instagram Post**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Embed Instagram Post</title>
</head>
<body>

  <h1>Instagram Post Embed</h1>

  <!-- Paste the Instagram embed code below -->

  <blockquote class="instagram-media" data-instgrm-permalink="https://www.instagram.com/p/yourpostid/" data-instgrm-version="14" style="max-width:540px; margin: auto;">
  </blockquote>
  <script async src="//www.instagram.com/embed.js"></script>

  <p>Replace the URL above with your own Instagram post URL.</p>

</body>
</html>
```

---

# 🔹 **Template 3: Embedding a TikTok Video**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Embed TikTok Video</title>
</head>
<body>

  <h1>TikTok Video Embed</h1>

  <!-- Paste TikTok embed code below -->

  <blockquote class="tiktok-embed" cite="https://www.tiktok.com/@username/video/1234567890" data-video-id="1234567890" style="max-width: 605px;min-width: 325px;">
    <section></section>
  </blockquote>
  <script async src="https://www.tiktok.com/embed.js"></script>

  <p>Replace the URL and video ID with your own TikTok video URL.</p>

</body>
</html>
```

---

# 🔹 **Template 4: Social Media Share Buttons**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Social Share Buttons</title>
  <style>
    /* Simple button styles */
    .share-buttons a {
      display: inline-block;
      margin: 10px;
      padding: 10px 15px;
      background-color: #0077b5; /* default LinkedIn blue */
      color: white;
      text-decoration: none;
      border-radius: 5px;
      font-weight: bold;
    }
    .share-buttons a.facebook { background-color: #3b5998; }
    .share-buttons a.twitter { background-color: #1da1f2; }
  </style>
</head>
<body>

  <h1>Share This Page on Social Media</h1>

  <div class="share-buttons">
    <!-- Replace URL below with your own page URL -->

    <a href="https://www.facebook.com/sharer/sharer.php?u=https://yourwebsite.com/page.html" 
       class="facebook" target="_blank" rel="noopener noreferrer" title="Share on Facebook">
      Share on Facebook
    </a>

    <a href="https://twitter.com/intent/tweet?url=https://yourwebsite.com/page.html&text=Check%20out%20this%20page!" 
       class="twitter" target="_blank" rel="noopener noreferrer" title="Share on Twitter">
      Share on Twitter
    </a>

    <a href="https://www.linkedin.com/sharing/share-offsite/?url=https://yourwebsite.com/page.html"
       target="_blank" rel="noopener noreferrer" title="Share on LinkedIn">
      Share on LinkedIn
    </a>
  </div>

</body>
</html>
```

---

# 🔹 **Template 5: Combined Example — Links, Embed & Share**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Social Media Example Page</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 2em;
    }
    .social-links a {
      margin: 0 10px;
      text-decoration: none;
    }
    .social-links img {
      width: 32px;
      vertical-align: middle;
    }
    .share-buttons a {
      display: inline-block;
      margin: 10px 10px 20px 0;
      padding: 8px 12px;
      color: white;
      border-radius: 4px;
      text-decoration: none;
      font-weight: bold;
    }
    .share-buttons a.facebook { background-color: #3b5998; }
    .share-buttons a.twitter { background-color: #1da1f2; }
    .share-buttons a.linkedin { background-color: #0077b5; }
  </style>
</head>
<body>

  <h1>My Social Media Hub</h1>

  <section>
    <h2>Follow Me</h2>
    <div class="social-links">
      <a href="https://www.linkedin.com/in/yourprofile" target="_blank" rel="noopener noreferrer" title="LinkedIn">
        <img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" alt="LinkedIn" />
      </a>
      <a href="https://www.instagram.com/yourprofile" target="_blank" rel="noopener noreferrer" title="Instagram">
        <img src="https://cdn-icons-png.flaticon.com/512/174/174855.png" alt="Instagram" />
      </a>
      <a href="https://www.facebook.com/yourprofile" target="_blank" rel="noopener noreferrer" title="Facebook">
        <img src="https://cdn-icons-png.flaticon.com/512/174/174848.png" alt="Facebook" />
      </a>
    </div>
  </section>

  <section>
    <h2>Featured Instagram Post</h2>
    <blockquote class="instagram-media" data-instgrm-permalink="https://www.instagram.com/p/yourpostid/" data-instgrm-version="14" style="max-width:540px; margin:auto;"></blockquote>
    <script async src="//www.instagram.com/embed.js"></script>
  </section>

  <section>
    <h2>Share This Page</h2>
    <div class="share-buttons">
      <a href="https://www.facebook.com/sharer/sharer.php?u=https://yourwebsite.com/page.html" class="facebook" target="_blank" rel="noopener noreferrer" title="Share on Facebook">
        Facebook
      </a>
      <a href="https://twitter.com/intent/tweet?url=https://yourwebsite.com/page.html&text=Check%20this%20out!" class="twitter" target="_blank" rel="noopener noreferrer" title="Share on Twitter">
        Twitter
      </a>
      <a href="https://www.linkedin.com/sharing/share-offsite/?url=https://yourwebsite.com/page.html" class="linkedin" target="_blank" rel="noopener noreferrer" title="Share on LinkedIn">
        LinkedIn
      </a>
    </div>
  </section>

</body>
</html>
```

---

# ⚠️ **Instructions for Students**

* **Replace** all placeholder URLs like `https://yourwebsite.com/page.html` or `https://www.instagram.com/p/yourpostid/` with your **actual URLs** or profile/page links.
* For embed snippets, use the **official embed tools** on the social media platforms to get the latest embed code.
* Test your page by opening the HTML file in a browser to see if links and embeds work.
* Try sharing your page URL on social media to see the sharing functionality in action.

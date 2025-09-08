# HTML Lesson: Understanding `index.html`

## Lesson Objectives

* Identify the purpose of each HTML tag in the file
* Distinguish between **block-level** and **inline** elements
* Apply **accessibility best practices** to these elements

---

## 1. Document Structure

Every HTML document follows the same high-level structure:

```html
<html lang="en">
  <head>…</head>
  <body>…</body>
</html>
```

* `<html lang="en">`

  * **Root element** that wraps all content.
  * The `lang` attribute tells screen readers the primary language of the page (English), improving pronunciation and accessibility.&#x20;
* `<head>`

  * Contains **metadata** (information about the page).&#x20;
* `<body>`

  * Holds the **visible content** users see in the browser.&#x20;

---

## 2. Head Section

```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Document</title>
</head>
```

1. **Character Encoding**

   ```html
   <meta charset="UTF-8" />
   ```

   * Declares the document uses UTF-8 encoding, ensuring characters (like emojis or non-Latin scripts) display correctly.&#x20;

2. **Responsive Viewport**

   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0" />
   ```

   * Instructs mobile browsers to match the screen’s width and zoom level, making the page responsive.&#x20;

3. **Document Title**

   ```html
   <title>Document</title>
   ```

   * Sets the text shown in the browser tab and by screen readers when bookmarking. Always choose a **descriptive** title.&#x20;

---

## 3. Body Content & Tag Explanations

```html
<body>
  <h1>Large Header, only used once on a page</h1>
  <h2>Smaller Header, continues to h6</h2>
  <a href="https://www.bbc.com/">Link Here!</a>

  <p>Am I a block level element or am I inline</p>
  <p>Am I a block level element or am I inline</p>
  <button>Click the button</button>

  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
  </ul>
  <ol>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
  </ol>

  <img src="capy.jpg" alt="Glacier in ocean" />
</body>
```

| Tag             | Purpose & Behavior                                                                                                                                         | Example & Lines                                  |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| `<h1>`–`<h2>`   | **Headings** define sections. `<h1>` is the main title (use once), `<h2>`–`<h6>` are subheadings. They are **block-level** so each starts on a new line.   | `<h1>…</h1>`                                     |
| `<a>`           | **Anchor (link)** to another resource. By default **inline**, flows within text. Always use **descriptive link text** rather than “click here.”            | `<a href="…">Link Here!</a>`                     |
| `<p>`           | **Paragraph** for blocks of text. Always **block-level**.                                                                                                  | `<p>…</p>`                                       |
| `<button>`      | Interactive **button** for actions (forms, scripts). Renders as **inline-block**. Should include `type="button"` or `type="submit"` and accessible labels. | `<button>Click the button</button>`              |
| `<ul>` & `<ol>` | **Unordered** (`<ul>`) and **ordered** (`<ol>`) lists. Both are **block-level**, containing `<li>` items (also block by default).                          | `<ul>…</ul>` <br>`<ol>…</ol>`                    |
| `<li>`          | **List item** inside `<ul>` or `<ol>`.                                                                                                                     | `<li>Item</li>` within above                     |
| `<img>`         | Embeds an image. **Inline** by default and is a *void* element (no closing tag). Always include a meaningful `alt` attribute for screen readers.           | `<img src="capy.jpg" alt="Glacier in ocean" />`  |

---

## 4. Block-Level vs Inline Elements

* **Block-Level** elements

  * Start on a new line, take up the full container width by default
  * Examples: `<h1>`, `<p>`, `<ul>`, `<ol>`

* **Inline** elements

  * Flow within text, only occupy as much width as necessary
  * Examples: `<a>`, `<img>`, `<span>` (and `<button>` displays as `inline-block`)

Choosing the right type affects layout, spacing, and how elements stack.

---

## 5. Accessibility Best Practices

1. **Declare Language**

   * Always set `lang` on `<html>` so screen readers use correct pronunciation.&#x20;

2. **Use Semantic Headings**

   * Maintain a logical order (`<h1>` → `<h2>` → …). Don’t skip levels.&#x20;

3. **Descriptive Titles & Links**

   * Page `<title>` should reflect content.
   * Link text should describe destination (avoid “here” or “click”).&#x20;

4. **Alt Text for Images**

   * Provide concise, descriptive `alt` attributes for `<img>` so non-sighted users understand the image.&#x20;

5. **Button Roles & Labels**

   * Specify `type="button"` or `type="submit"`.
   * If a button’s text isn’t clear, add `aria-label` for screen readers.&#x20;

6. **Responsive Meta Tag**

   * Include `<meta name="viewport">` to ensure content scales correctly on mobile devices.&#x20;

---

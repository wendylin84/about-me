# CSS Styling Basics for High School Freshmen

## Lesson Objectives

* Learn how to link a CSS file to an HTML page
* Understand **selectors** and how CSS decides which rule wins (**specificity**)
* Explore the **box model**, focusing on **padding vs. margin**
* See how **parent** and **child** elements work together in layouts

---

## 1. Connecting CSS to HTML

To make your page look good, you need to tell your HTML about your styles. In the `<head>` of **index2.html**, you’ll find:

```html
<link rel="stylesheet" href="style.css" />
```

* **What it does:**

  * Finds and applies all the rules inside `style.css` to this page.
  * Must go inside `<head>` before any visible content so styles load first.&#x20;

---

## 2. Resetting Defaults & the `box-sizing` Trick

Browsers add their own margin and padding to many elements. To start fresh, we “reset” them:

```css
html,
body,
* {
  font-size: 10px;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
```

* **Selectors used:**

  * `html`, `body` target those specific tags.
  * `*` (the universal selector) targets **every** element.&#x20;
* **Why reset?**

  * Makes spacing predictable by removing browser defaults.
* **`box-sizing: border-box;`**

  * Changes how width and height are calculated: includes padding and borders in the element’s total size, so your boxes don’t suddenly grow bigger when you add padding.&#x20;

---

## 3. Setting Up Your Page’s Look

Next, we give the page a background, text color, and font:

```css
body {
  background-color: #333;
  color: white;
  font-family: Arial, sans-serif;
}
```

* **Background (`#333`)** makes the page dark gray.
* **Text color (`white`)** ensures letters stand out.
* **Font stack**: browser uses Arial if available, otherwise a generic sans-serif.&#x20;

We also make all list items big and white:

```css
li {
  color: white;
  font-size: 3rem;
}
```

* Targets every `<li>` on the page.
* `3rem` means 3 × the base font size (here, 3 × 10px = 30px).&#x20;

---

## 4. Selectors & Specificity: Who Wins?

When two rules clash, CSS picks the one with higher **specificity**. Think of it like a race: the strongest selector wins.

1. **Element selector** (`li`, `h1`)
2. **Class selector** (`.first`)
3. **ID selector** (`#second`)
4. **Inline style** (`style="…"`) — strongest
5. **Universal** (`*`) — weakest

```css
.first {
  color: purple;
}
#second {
  color: blue;
}
```

* Any element with `class="first"` turns purple.&#x20;
* The one element with `id="second"` turns blue—even if it also has `.first`—because IDs beat classes.&#x20;

In **index2.html**, you see:

```html
<li class="first">Item 1</li>
<li id="second">Item 2</li>
```

This makes Item 1 purple and Item 2 blue.&#x20;

---

## 5. Styling Headings

```css
h1 {
  font-size: 10rem;
  text-align: center;
}
h2 {
  font-size: 5rem;
  text-align: center;
}
```

* All `<h1>` tags become huge (10 × base size) and centered.
* All `<h2>` tags are half as big as `<h1>` but also centered.&#x20;

In the HTML:

```html
<h1>Large Header…</h1>
<h2>Smaller Header…</h2>
```

They use these styles to stand out at the top of the page.&#x20;

---

## 6. Styling Images

We wrap images in a container to control their size and look:

```css
.img-container {
  width: 30rem;
  height: 30rem;
  margin: 1rem auto;
  background-color: #fff;
  border-radius: 1rem;
  box-shadow: 0.5rem 0.5rem 1rem rgba(0, 0, 0, 0.5);
}
.img {
  border-radius: 1rem;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

* **`.img-container`**:

  * Fixed 30 × 30rem box.
  * Centered horizontally (`margin: 1rem auto`).
  * White background, rounded corners, and a soft shadow.&#x20;
* **`.img`**:

  * Fills the container (`width`/`height`: 100%).
  * `object-fit: cover` crops or scales the image so it fills nicely without stretching.&#x20;

In **index2.html**:

```html
<div class="img-container">
  <img class="img" src="img/capy.jpg" alt="Glacier in ocean" />
</div>
```

This ensures the picture always looks neat and fits its box.&#x20;

---

## 7. The Box Model: Padding vs. Margin

Every element is a box. The **box model** has:

```
margin (outside)
border
padding (inside)
content
```

### Padding

* Adds space **inside** the box, around the content.
* Doesn’t push other elements away.

```css
.parent {
  width: 50rem;
  height: 50rem;
  background-color: #fff;
  padding: 1rem 0.5rem;
}
```

* Top/bottom padding = 1rem, left/right = 0.5rem&#x20;

### Margin

* Adds space **outside** the box, pushing other elements away.
* Can center an element horizontally with `margin: auto`.

```css
.child-one {
  width: 20rem;
  height: 20rem;
  background-color: red;
  margin: 1rem auto;
}
.child-two {
  width: 20rem;
  height: 20rem;
  background-color: green;
}
```

* `.child-one` sits 1 rem below the parent’s padding, and centers itself.&#x20;
* `.child-two` simply follows below, with no extra margin.&#x20;

In HTML:

```html
<div class="parent">
  <div class="child-one"></div>
  <div class="child-two"></div>
</div>
```

The **parent** sets the stage; its **children** fill in with their own sizes and spacing.&#x20;

---

## 8. Key Takeaways & Best Practices

1. **Always link** your CSS in `<head>` so the page doesn’t flash unstyled.
2. **Reset defaults** and use `box-sizing: border-box` for easier sizing.
3. **Learn specificity**: element < class < ID < inline.
4. **Understand the box model**: padding is inside, margin is outside.
5. **Use parent–child containers** to organize your layout and control spacing.

With these basics, you can start styling any webpage confidently and clearly!

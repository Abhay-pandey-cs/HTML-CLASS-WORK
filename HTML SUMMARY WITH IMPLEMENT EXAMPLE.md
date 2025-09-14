# HTML Tags & Attributes — Student-friendly Guide (step-by-step, no CSS required)

This guide describes common HTML tags and the most useful attributes you will need as a 1st‑year student. It focuses on structure, text formatting, lists, tables, forms, images, multimedia and semantic layout — with short notes and small examples. Where relevant, I point out when CSS is normally used (and when an HTML attribute is deprecated).

Quick notes
- Global attributes available on most elements: id, class, title, data-*, lang (on `<html>`).
- Boolean attributes: written without value: `<input required>` or `<details open>`.
- Prefer semantic HTML first (use CSS for visual styling). Some old HTML attributes (like `bgcolor`, `<font>`) are deprecated — they still exist in legacy pages but should be avoided in modern sites.

---

1. Document structure (skeleton)
- `<!DOCTYPE html>` — declare HTML5 (top of file).
- `<html lang="en">` — root element; set `lang` for accessibility.
- `<head>` — metadata container: `<meta>`, `<title>`, `<link>`, `<script>`.
  - `<meta charset="utf-8">` — set encoding.
  - `<title>` — text shown in browser tab.
  - `<link rel="stylesheet" href="styles.css">` — link CSS (recommended).
  - `<script src="app.js" defer></script>` — JavaScript file (use `defer` to run after parsing).
- `<body>` — visible content.

Basic starting template:
```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>My Page</title>
</head>
<body>
  <!-- content here -->
</body>
</html>
```

Step 1: always start with this skeleton.

---

2. Headings and paragraphs
- Headings: `<h1>` to `<h6>` — from most to least important.
  - Useful attribute: `id` for linking / anchors: `<h2 id="intro">Intro</h2>`.
- Paragraph: `<p>` — text block.
- Line break: `<br>` — forced new line (use sparingly).
- Horizontal rule: `<hr>` — thematic break.

Example:
```html
<h1 id="title">My Website</h1>
<p>Welcome to my site. This is the first paragraph.</p>
<p>New paragraph<br>with a line break.</p>
<hr>
```

Step 2: add headings and paragraphs to structure content.

---

3. Inline text formatting (no CSS)
These tags change meaning or presentation without CSS.

- `<strong>` — important text (semantic; screen readers emphasize).
- `<em>` — emphasized text (semantic; usually italic).
- `<b>` / `<i>` — bold / italic (presentational).
- `<u>` — underline (presentational).
- `<small>` — smaller text.
- `<mark>` — highlighted text.
- `<del datetime="2025-09-14">` — removed text (with optional `datetime`).
- `<ins datetime="2025-09-14">` — inserted text.
- `<sup>` — superscript: e.g., H<sup>2</sup>O.
- `<sub>` — subscript: e.g., CO<sub>2</sub>.
- `<abbr title="HyperText Markup Language">HTML</abbr>` — abbreviation with tooltip.
- `<code>`, `<pre>` — code and preformatted text.

Examples:
```html
<p><strong>Note:</strong> Use <em>semantic</em> tags when possible.</p>
<p>Water formula: H<sub>2</sub>O. 10<sup>6</sup> = 1,000,000.</p>
<p><abbr title="Cascading Style Sheets">CSS</abbr> goes in a separate file (recommended).</p>
<pre><code>console.log('hello')</code></pre>
```

Short note: use `<strong>` / `<em>` for meaning; use `<b>` / `<i>` only when purely presentational.

---

4. Quotes and citations
- Inline quote: `<q cite="URL">short quote</q>` — browsers usually add quotation marks.
  - `cite` is optional and indicates the source URL.
- Block quote: `<blockquote cite="URL">Block-level quote</blockquote>` — for longer quotations.
  - Add a `<cite>` tag inside or after blockquote to name the source.
- `<cite>` — title of a work or author (semantic).

Examples:
```html
<p>She said <q cite="https://example.com/article">this is important</q>.</p>

<blockquote cite="https://example.com/article">
  <p>This is a long quote from a source.</p>
  <footer>— <cite>Author Name</cite></footer>
</blockquote>
```

Tip: use `<blockquote>` for multi-line quotes, `<q>` for short inline quotes.

---

5. Links & anchors
- `<a href="URL">link text</a>` — main attributes:
  - `href` — destination (URL, `mailto:`, `tel:`, or `#id`).
  - `target` — `_self` (same tab), `_blank` (new tab).
  - `rel` — security/relationship: use `rel="noopener noreferrer"` with `target="_blank"`.
  - `download` — hint to download the linked resource.
- Anchors: use `id` on an element and link to it: `<a href="#section1">Go</a>`.

Example:
```html
<a href="https://example.com" target="_blank" rel="noopener noreferrer">Visit</a>
<a href="#contact">Contact section</a>
```

Accessibility note: use meaningful link text (avoid "click here").

---

6. Images and figures
- `<img src="url" alt="description" width="300" height="200" loading="lazy">`
  - `src` — image URL.
  - `alt` — required for accessibility; describe the image.
  - `width` / `height` — intrinsic size (helps layout).
  - `loading` — `lazy` defers off-screen images.
  - `srcset` / `sizes` — responsive images (advanced).
- `<figure>` and `<figcaption>` — group image with caption.

Example:
```html
<figure>
  <img src="cat.jpg" alt="Sleeping cat" width="400" loading="lazy">
  <figcaption>A sleeping cat.</figcaption>
</figure>
```

Note: visual styling like background color or font inside images requires CSS or editing the image. HTML itself does not change fonts/colors (except deprecated tags like `<font>` — avoid them).

---

7. Lists (ordered, unordered, description)
- Unordered list: `<ul>` with `<li>` items (bullets).
- Ordered list: `<ol>` with `<li>` items (numbers).
  - Useful attributes for `<ol>`: `start="3"` and `reversed` (count down).
  - `<li value="10">` can set a specific number (only meaningful inside `<ol>`).
- Description list: `<dl>` with pairs of `<dt>` (term) and `<dd>` (description).

Examples:
```html
<ul>
  <li>Apple</li>
  <li>Banana</li>
</ul>

<ol start="3">
  <li>Third</li>
  <li>Fourth</li>
</ol>

<dl>
  <dt>HTTP</dt>
  <dd>HyperText Transfer Protocol, used to fetch webpages.</dd>
</dl>
```

Study tip: nest lists by placing another `<ul>`/`<ol>` inside an `<li>`.

---

8. Tables (structure and merging cells)
- Basic tags:
  - `<table>` — container.
  - `<caption>` — short title (place immediately after `<table>`).
  - `<thead>`, `<tbody>`, `<tfoot>` — group rows (optional but recommended).
  - `<tr>` — table row.
  - `<th>` — header cell (use `scope="col"` or `scope="row"`).
  - `<td>` — data cell.
- Merging cells:
  - `colspan="n"` — span cell across n columns.
  - `rowspan="n"` — span cell across n rows.
- Optional: `<colgroup>` / `<col>` — declare columns (for grouping/presentation).

Examples:
```html
<table>
  <caption>Monthly sales</caption>
  <thead>
    <tr>
      <th scope="col">Month</th>
      <th scope="col">Product A</th>
      <th scope="col">Product B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Jan</td>
      <td>120</td>
      <td>80</td>
    </tr>
    <tr>
      <td>Feb</td>
      <td colspan="2">Data not available</td>
    </tr>
  </tbody>
</table>
```

Accessibility: always add `<caption>` and `scope` on `<th>` for clearer meaning to screen readers.

---

9. Forms and inputs (formatting without CSS)
- `<form action="/submit" method="post">` — main form attributes:
  - `action` — where data goes.
  - `method` — `get` or `post`.
- `<label for="id">Label</label>` — associates a label with an input; clicking the label focuses the control.
- Common `<input>` attributes:
  - `type` — `text`, `email`, `password`, `number`, `checkbox`, `radio`, `file`, `date`, `hidden`.
  - `name` — the field name sent to server.
  - `id` — used by `label` and scripts.
  - `placeholder` — hint text (not a substitute for label).
  - `required` — makes field mandatory.
  - `readonly`, `disabled` — control user interaction.
  - `min`, `max`, `step` — for numeric/date types.
  - `maxlength` / `minlength`, `pattern` — validation hints.
  - `accept` — file type filter (for `type="file"`), `multiple` — allow multiple files.
- `<textarea rows="4" cols="40"></textarea>` — multi-line input.
- `<select name="country"> <option value="in" selected>India</option> </select>` — drop-down.
- `<button type="submit">Submit</button>` — submit/reset/button types.
- `<fieldset>` and `<legend>` — group related controls; `disabled` on fieldset disables children.

Small form example:
```html
<form action="/submit" method="post">
  <label for="name">Name</label>
  <input id="name" name="name" type="text" placeholder="Your name" required>

  <label for="email">Email</label>
  <input id="email" name="email" type="email" required>

  <fieldset>
    <legend>Preferences</legend>
    <label><input type="checkbox" name="subscribe" value="yes"> Subscribe</label>
  </fieldset>

  <button type="submit">Send</button>
</form>
```

Note: Formatting the layout (spacing, colors, fonts) is done with CSS. HTML provides the structure and semantic meaning.

---

10. Semantic layout tags (structure)
- `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>` — semantic regions.
  - Useful attributes: `id`, `class`, `aria-label` (for accessibility), e.g., `<nav aria-label="Main navigation">`.
- Generic containers: `<div>` (block) and `<span>` (inline) — use `class`/`id` to target with CSS or JS.
- Small interactive element: `<details><summary>Title</summary>Hidden content</details>` — `open` shows content by default.

Example:
```html
<header><h1>Site title</h1></header>
<nav aria-label="Main menu"><a href="#home">Home</a></nav>
<main><article><h2>Post</h2><p>Content</p></article></main>
<footer>© 2025</footer>
```

---

11. Accessibility reminders (important)
- Always set `alt` for images.
- Use `<label for="...">` for form controls.
- Add `lang` on `<html>` for correct screen reader language.
- Use table `<caption>` and `<th scope="col|row">` for clarity.
- Avoid conveying meaning by color alone (use text or icons too).
- Use semantic tags (article, nav, header) to help assistive tech.

---

12. Step-by-step mini-project (put concepts together)
Follow these steps to build a simple page using only HTML (no CSS):

Step A — Create the skeleton
```html
<!doctype html><html lang="en"><head><meta charset="utf-8"><title>Mini Page</title></head><body>...</body></html>
```

Step B — Add header and nav
```html
<header><h1>Site</h1></header>
<nav aria-label="Main menu"><ul><li><a href="#content">Content</a></li></ul></nav>
```

Step C — Add content: headings, paragraphs, lists
```html
<main id="content">
  <h2>About</h2>
  <p>This page shows HTML tags and attributes.</p>
  <ul><li>Item 1</li><li>Item 2</li></ul>
</main>
```

Step D — Add an image with caption
```html
<figure><img src="pic.jpg" alt="A picture"><figcaption>Picture caption</figcaption></figure>
```

Step E — Add a table with caption and header scope
```html
<table><caption>Scores</caption>
  <thead><tr><th scope="col">Name</th><th scope="col">Score</th></tr></thead>
  <tbody><tr><td>Alice</td><td>95</td></tr></tbody>
</table>
```

Step F — Add a simple form
```html
<form action="/submit" method="post">
  <label for="n">Name</label><input id="n" name="name" type="text" required>
  <button type="submit">Send</button>
</form>
```

Step G — Validate: check `alt`, `label` usage, `lang` set on `<html>`.

---

13. Quick reference cheat-sheets (very short)

Inline formatting
- strong, em, b, i, u, small, mark, del (datetime), ins (datetime), sub, sup, abbr (title), code, pre

Block-level content
- header, nav, main, section, article, aside, footer, h1-h6, p, blockquote (cite), figure, figcaption, details/summary

Lists & description
- ul, ol (start, reversed), li (value), dl, dt, dd

Tables
- table, caption, thead, tbody, tfoot, tr, th (scope), td (colspan, rowspan), colgroup/col

Forms
- form (action, method, enctype), label (for), input (type, name, id, placeholder, required, readonly, disabled), textarea (rows, cols), select/option (value, selected), button (type), fieldset/legend

Media
- img (src, alt, width, height, loading), picture/source (media, type), audio/video (controls, autoplay, loop, muted, poster)

---

Wrapping up
This file collects the most useful tags and attributes you will need to practice HTML without using CSS for styling. It explains what each tag does, shows small examples, and gives a simple step-by-step mini project to combine them.

If you want, I can now:
- produce a single HTML demo file showing all examples live, or
- create printable flashcards from these items.

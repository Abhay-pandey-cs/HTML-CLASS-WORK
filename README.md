# HTML Tags Cheatsheet (Serial-wise — expanded)

1. Document structure
   - `<!DOCTYPE>` — Declares the document type and enables standards mode (HTML5).
   - `<html lang="en">` — Root element; `lang` sets document language.
   - `<head>` — Metadata container (title, links, meta tags, scripts).
   - `<meta charset="utf-8">` — Character encoding.
   - `<meta name="viewport" content="width=device-width, initial-scale=1">` — Mobile/responsive viewport.
   - `<title>` — Page title shown in browser tab/bookmarks.
   - `<base href="...">` — Base URL for relative links.
   - `<link rel="stylesheet" href="styles.css">` — External CSS.
   - `<script src="app.js" defer></script>` — JavaScript; use `defer`/`async`.
   - `<body>` — Visible content of the page; main script execution area.

     

2. Text structure & headings
   - `<h1> ... <h6>` — Headings; `<h1>` highest importance. Use for semantic document outline.
   - `<p>` — Paragraph block of text.
   - `<br>` — Line break (use sparingly).
   - `<hr>` — Thematic break / horizontal rule (semantic separator).
   - `<address>` — Contact information for author/owner.
   - Semantic note: use headings in order to help accessibility and SEO.

     

3. Text formatting & emphasis
   - `<strong>` — Strong importance (screen readers emphasize; usually bold).
   - `<b>` — Presentational bold (no added semantic weight).
   - `<em>` — Emphasis (usually italic; spoken emphasis for assistive tech).
   - `<i>` — Presentational italic.
   - `<small>` — Side-comments or small print.
   - `<mark>` — Highlighted text.
   - `<del>` / `<ins>` — Deleted/inserted text (strikethrough/underline semantics).
   - `<sub>` / `<sup>` — Subscript / superscript.
   - `<abbr title="...">` — Abbreviation with expansion tooltip.
   - `<cite>` — Citation of a work.
   - `<q>` — Short inline quotation; browser may add quotation marks.
   - `<blockquote>` — Block quotation; use `cite` attribute for source.

     

4. Links & navigation
   - `<a href="url">` — Anchor/link to other pages or resources.
     - Attributes: `target="_blank"`, `rel="noopener noreferrer"`, `download`, `href="#id"`.
   - `mailto:` and `tel:` — Special link schemes (email/phone).
   - `<nav>` — Navigation section with primary links.
   - Use descriptive link text and `aria-current="page"` for active nav items.

     

5. Images & multimedia
   - `<img src="img.jpg" alt="description">` — Image with required `alt` text.
     - Attributes: `width`, `height`, `srcset`, `sizes`, `loading="lazy"`.
   - `<figure>` — Self-contained content (image, diagram).
   - `<figcaption>` — Caption for `<figure>`.
   - `<picture>` — Art direction (multiple sources, `source` elements).
   - `<audio controls src="audio.mp3">` — Audio with controls.
   - `<video controls src="video.mp4">` — Video with controls; support multiple sources.

     

6. Lists
   - `<ul>` — Unordered list (bulleted).
   - `<ol>` — Ordered list (numbered); `start`, `type` attributes.
   - `<li>` — List item.
   - Nested lists — Lists within `<li>` for sub-items.
   - `<dl>` — Description list (definition list).
   - `<dt>` — Term/name in a description list.
   - `<dd>` — Description/details for the term.
   - `<menu>` / `<menuitem>` — Context or toolbar menus (limited browser support).

     

7. Tables
   - `<table>` — Table container.
   - `<caption>` — Table title/description.
   - `<thead>`, `<tbody>`, `<tfoot>` — Logical grouping of rows.
   - `<tr>` — Table row.
   - `<th scope="col|row">` — Header cell (use `scope` for accessibility).
   - `<td>` — Data cell.
   - Attributes: `colspan`, `rowspan`.
   - Use tables for tabular data only (not layout).

     

8. Forms & input
   - `<form action="/submit" method="post">` — Form container.
   - `<label for="id">` — Associates label with control (improves accessibility).
   - `<input>` — Versatile control with `type` variants:
     - `text`, `password`, `email`, `tel`, `number`, `date`, `range`, `checkbox`, `radio`, `file`, `hidden`, `search`, `url`, `color`.
   - Attributes: `name`, `id`, `value`, `placeholder`, `required`, `readonly`, `disabled`, `maxlength`, `pattern`, `autocomplete`.
   - `<textarea>` — Multi-line text input.
   - `<select>` + `<option>` — Drop-down list; `multiple` for multi-select.
   - `<button type="submit|reset|button">` — Buttons for actions.
   - `<fieldset>` / `<legend>` — Group related controls with a caption.
   - `<datalist>` — Predefined options for inputs.
   - Client-side validation: use HTML attributes and supplement with JS for better UX.

     

9. Semantic & layout helpers
   - `<header>` — Introductory content or page/section header.
   - `<nav>` — Navigation links (repeated for clarity).
   - `<main>` — Main content area (one per page).
   - `<section>` — Themed grouping of content.
   - `<article>` — Independent, self-contained content (e.g., blog post).
   - `<aside>` — Sidebar or tangential content.
   - `<footer>` — Footer for a section/page.
   - `<div>` — Generic block-level container (no semantic meaning).
   - `<span>` — Generic inline container (no semantic meaning).
   - `<details>` / `<summary>` — Collapsible widget for disclosure.
   - `<template>` — Holds inert DOM for cloning via JS.
   - `<dialog>` — Modal/dialog window (use with JS and accessibility patterns).
   - ARIA: use semantic HTML first; add ARIA attributes only when semantics are insufficient.

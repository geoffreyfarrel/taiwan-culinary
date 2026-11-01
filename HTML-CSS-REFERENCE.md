# HTML & CSS Reference

Every HTML tag and CSS property used in this site, with what it does.
Updated in the same change that first uses a new tag or property.

**Used in** — Home = `index.html`, 小吃 = `pages/classic-snacks.html`,
夜市 = `pages/night-market.html`, CSS = `css/style.css`.

## HTML — document structure

| Tag | Usage | Used in |
| --- | --- | --- |
| `<!doctype html>` | Tells the browser this is an HTML5 document. Always the first line | All pages |
| `<html lang="zh-Hant-TW">` | Root element of the page; `lang` says the content is Traditional Chinese | All pages |
| `<head>` | Information about the page that is not shown: title, charset, CSS link | All pages |
| `<meta charset="utf-8">` | Lets the page display Chinese characters correctly | All pages |
| `<meta name="viewport">` | Makes the page scale properly on phones | All pages |
| `<title>` | Text shown on the browser tab | All pages |
| `<link rel="stylesheet">` | Connects the page to `css/style.css` | All pages |
| `<body>` | Everything visible on the page | All pages |

## HTML — semantic layout

| Tag | Usage | Used in |
| --- | --- | --- |
| `<header>` | Top area of the page: site title and navigation | All pages |
| `<nav>` | A group of navigation links: the main menu, and the on-page table of contents | All pages (menu), 小吃, 夜市 (table of contents) |
| `<main>` | The main content of the page; only one per page | All pages |
| `<section>` | A themed group of content with its own heading, e.g. one food category | All pages |
| `<article>` | One self-contained item that makes sense on its own, e.g. one dish or one topic card | All pages |
| `<div>` | A box with no meaning, used only to group things for layout (the card grid, form fields) | All pages |

## HTML — text

| Tag | Usage | Used in |
| --- | --- | --- |
| `<h1>` | The page title; one per page | All pages |
| `<h2>` | A section heading | All pages |
| `<h3>` | A heading inside a section, e.g. the name of one dish | All pages |
| `<p>` | A paragraph of text | All pages |

## HTML — lists

| Tag | Usage | Used in |
| --- | --- | --- |
| `<ul>` | Unordered list: bullet points, order does not matter (menu, ingredients, tips) | All pages |
| `<ol>` | Ordered list: numbered steps, order matters (travel plan, recipe steps, table of contents) | All pages |
| `<li>` | One item inside a `<ul>` or `<ol>` | All pages |

## HTML — links and media

| Tag / attribute | Usage | Used in |
| --- | --- | --- |
| `<a href="page.html">` | A link to another page of this site | All pages |
| `<a href="#id">` | A link that jumps to the element with that `id` on the same page | 小吃, 夜市 |
| `<a href="https://…" target="_blank" rel="noopener">` | A link to another website; `target="_blank"` opens a new tab, `rel="noopener"` keeps that tab from controlling this one | Home |
| `id` | A unique name for an element, used as a jump target and to link a `<label>` to its field | All pages |
| `<img src alt width height>` | Shows an image; `src` is the file, `alt` describes it for screen readers, `width`/`height` reserve space while it loads | All pages |
| `<figure>` | Wraps an image or video together with its caption | All pages |
| `<figcaption>` | The caption under an image or video | 小吃, 夜市 |
| `<video controls preload poster>` | Plays a video; `controls` shows play/volume buttons, `preload="none"` waits for a click before downloading, `poster` is the image shown before playing | 夜市 |
| `<source src type>` | Gives the video file and its format inside `<video>` | 夜市 |

## HTML — tables

| Tag / attribute | Usage | Used in |
| --- | --- | --- |
| `<table>` | A table of rows and columns | 小吃, 夜市 |
| `<caption>` | The table's title | 小吃, 夜市 |
| `<thead>` | The header rows of the table | 小吃, 夜市 |
| `<tbody>` | The body (data) rows of the table | 小吃, 夜市 |
| `<tfoot>` | The footer rows of the table, e.g. a note | 夜市 |
| `<tr>` | One table row | 小吃, 夜市 |
| `<th>` | A header cell: describes a column or row | 小吃, 夜市 |
| `<td>` | A normal data cell | 小吃, 夜市 |
| `scope` | Tells screen readers what a `<th>` labels: `col`, `row`, `colgroup`, or `rowgroup` | 小吃, 夜市 |
| `colspan` | Makes a cell stretch across several columns (group titles, the note row) | 小吃, 夜市 |
| `rowspan` | Makes a cell stretch down several rows (台北 covers two night markets) | 夜市 |

## HTML — forms

| Tag / attribute | Usage | Used in |
| --- | --- | --- |
| `<form action="#" method="post">` | A form; `method="post"` sends the data in the request body. There is no backend, so nothing is saved | Home |
| `<label for>` | The text name of a field; `for` links it to the field's `id`, so clicking the text selects the field | Home |
| `<input type="text">` | A one-line text box | Home |
| `<input type="email">` | A text box that checks the value looks like an email address | Home |
| `<input type="radio">` | A choice where only one option in the group (same `name`) can be picked | Home |
| `required` | The browser will not submit the form while this field is empty | Home |
| `<select>` / `<option>` | A dropdown list and its choices | Home |
| `<div class="radio-group">` | Groups the radio buttons in a box; a `<p>` inside gives the question | Home |
| `<textarea rows>` | A multi-line text box; `rows` sets its height | Home |
| `<button type="submit">` | The button that submits the form | Home |

## HTML — accessibility attributes

| Attribute | Usage | Used in |
| --- | --- | --- |
| `aria-label` | Gives an element a name screen readers announce, e.g. which `<nav>` is the main menu | All pages |
| `aria-current="page"` | Marks the menu link of the page you are on, for screen readers | All pages |
| `role="radiogroup"` | Tells screen readers that the radio buttons inside belong together as one question | Home (form) |
| `aria-labelledby` | Names an element using the text of another element, by its `id` (the radio group uses the question's `<p>`) | Home (form) |

## CSS — selectors

| Selector | Usage | Example in CSS |
| --- | --- | --- |
| Element | Styles every element of that type | `body`, `h2`, `table` |
| Class `.name` | Styles elements with `class="name"` | `.card`, `.site-header` |
| Descendant `A B` | Styles B only when it is inside A | `.site-nav a`, `thead th` |
| Group `A, B` | Applies the same rule to several selectors | `h1, h2, h3` |
| `:hover` | Styles an element while the mouse is over it | `a:hover`, `.button:hover` |

## CSS — color and background

| Property | Usage | Used in |
| --- | --- | --- |
| `background-color` | Fills the background of an element with a color | Body, header, intro, cards, button, table header |
| `color` | Sets the text color | Body, links, nav, table header |

## CSS — box model and spacing

| Property | Usage | Used in |
| --- | --- | --- |
| `margin` | Space outside an element, between it and its neighbors. `margin: 0 auto` centers a box | Most rules |
| `margin-top` / `margin-bottom` / `margin-right` | Margin on just one side | Headings, sections, cards, labels |
| `padding` | Space inside an element, between its content and its border | Header, main, cards, table cells, inputs |
| `border` | A line around an element: width, style, color | Cards, table cells, inputs |
| `border-top` / `border-bottom` | A line on one side only | Header |
| `border-radius` | Rounds the corners | Cards, intro, images, inputs, button |
| `border-collapse` | `collapse` merges the borders of neighboring table cells into one line | `table` |
| `box-sizing` | `border-box` makes `width` include padding and border, so boxes do not overflow | Cards, inputs |
| `width` / `max-width` | Sets how wide an element is / the widest it may get | Cards, images, tables, `main` |
| `height` | `auto` keeps a video's proportions when its width changes; `250px` gives every photo the same height | Images, video |
| `object-fit` | `cover` fills the box with the photo and crops the extra, without stretching it | Photos |

## CSS — text

| Property | Usage | Used in |
| --- | --- | --- |
| `font-family` | Which font to use, with a fallback; headings use a serif font, body a sans-serif font | Body, headings |
| `font-size` | Text size | Site title, captions, inputs, button |
| `font-weight` | Text thickness; `bold` makes it bold | Labels, table caption |
| `line-height` | Space between lines of text | Body |
| `text-align` | Left, center, or right alignment | Intro, captions, table cells |
| `text-decoration` | `none` removes the underline from links | Site title, nav |
| `list-style` | `none` removes the bullets from a list | Main menu |

## CSS — layout

| Property | Usage | Used in |
| --- | --- | --- |
| `display` | `block` puts an element on its own line; `inline-block` keeps it in the line; `flex` lines children up in a row | Header, menu, card grid, labels |
| `flex-wrap` | Lets flex items move to the next line when there is no room | Header, card grid |
| `justify-content` | Spreads flex items out horizontally (`space-between`) | Header, card grid |
| `align-items` | Lines flex items up vertically (`center`) | Header |
| `@media (max-width: 768px)` | Rules that apply only on narrow (phone) screens | End of CSS |

## CSS — other

| Feature | Usage | Used in |
| --- | --- | --- |
| `cursor` | `pointer` shows the hand cursor | Button |
| `/* … */` | A CSS comment, used to label each part of the file | Throughout CSS |

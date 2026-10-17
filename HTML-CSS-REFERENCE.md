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
| `<footer>` | Bottom area of the page: credits, copyright | All pages |
| `<div>` | A box with no meaning, used only to group things for layout (the card grid, form fields) | All pages |

## HTML — text

| Tag | Usage | Used in |
| --- | --- | --- |
| `<h1>` | The page title; one per page | All pages |
| `<h2>` | A section heading | All pages |
| `<h3>` | A heading inside a section, e.g. the name of one dish | All pages |
| `<p>` | A paragraph of text | All pages |
| `&copy;` | An HTML entity: writes the © symbol | All pages (footer) |

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
| `aria-current="page"` | Marks the menu link of the page you are on; the CSS also colors it red | All pages |
| `role="radiogroup"` | Tells screen readers that the radio buttons inside belong together as one question | Home (form) |
| `aria-labelledby` | Names an element using the text of another element, by its `id` (the radio group uses the question's `<p>`) | Home (form) |

## CSS — selectors

| Selector | Usage | Example in CSS |
| --- | --- | --- |
| Element | Styles every element of that type | `body`, `h2`, `table` |
| Class `.name` | Styles elements with `class="name"` | `.card`, `.site-header` |
| Descendant `A B` | Styles B only when it is inside A | `.site-nav a`, `thead th` |
| Child `A > B` | Styles B only when it is directly inside A | `main > section` |
| Group `A, B` | Applies the same rule to several selectors | `h1, h2, h3` |
| Attribute `[attr="value"]` | Styles elements with that attribute value | `a[aria-current="page"]` |
| `:hover` | Styles an element while the mouse is over it | `a:hover`, `.button:hover` |
| `:last-child` | Styles an element only if it is the last one inside its parent | `.card li:last-child` |
| `:focus-visible` | Styles an element when it is focused with the keyboard (Tab key) | `a:focus-visible` |
| `::marker` | Styles the bullet or number of a list item | `li::marker` |
| Universal `*` | Matches every element | `*` (reduced-motion rule) |

## CSS — color and background

| Property | Usage | Used in |
| --- | --- | --- |
| `background-color` | Fills the background of an element with a color | Body, header, footer, intro, buttons, table header |
| `color` | Sets the text color | Body, links, nav, footer, table header |

## CSS — box model and spacing

| Property | Usage | Used in |
| --- | --- | --- |
| `margin` | Space outside an element, between it and its neighbors. `margin: 0 auto` centers a box | Most rules |
| `margin-top` / `margin-bottom` / `margin-right` | Margin on just one side | Headings, paragraphs, lists, sections |
| `padding` | Space inside an element, between its content and its border | Header, main, cards, table cells, inputs |
| `padding-left` / `padding-bottom` | Padding on just one side | Lists, `h2` |
| `border` | A line around an element: width, style, color | Cards, table cells, inputs |
| `border-bottom` / `border-top` / `border-left` | A line on one side only | `h2` underline, header, footer, intro |
| `border-radius` | Rounds the corners | Cards, images, inputs, buttons |
| `border-collapse` / `border-spacing` | `separate` with spacing `0` keeps cell borders apart so the table's rounded corners work | `table` |
| `box-sizing` | `border-box` makes `width` include padding and border, so boxes do not overflow | Cards, inputs, nav links |
| `width` / `max-width` | Sets how wide an element is / the widest it may get | Cards, images, `main`, hero text |
| `height` | `auto` keeps an image's proportions when its width changes; a fixed value sizes the radio buttons | Images, radios |
| `min-height` | The smallest height allowed; keeps links and controls at least 44px tall, easy to tap | Nav links, TOC pills, inputs, button |
| `overflow` | `hidden` clips content to the box, so table corners stay rounded | `table` |
| `aspect-ratio` | Fixes an element's width-to-height shape, e.g. `16 / 10` | Photos |
| `object-fit` | `cover` fills the box with the image and crops the extra, without stretching | Photos |
| `object-position` | Chooses which part of the image stays visible when it is cropped | `.focus-bottom` photos |
| `box-shadow` | A soft shadow under a box | Cards, form |
| `outline` / `outline-offset` | A line drawn outside the border, used as the keyboard focus ring; offset adds a gap | Links and controls on focus |

## CSS — text

| Property | Usage | Used in |
| --- | --- | --- |
| `font-family` | Which font to use, with fallbacks; headings use a serif font, body a sans-serif font | Body, headings, inputs, buttons |
| `font-size` | Text size | Headings, body, footer, captions |
| `font-weight` | Text thickness; `700` is bold | Site title, labels, caption, button |
| `line-height` | Space between lines of text; also centers radio labels vertically | Body, headings, radio labels |
| `letter-spacing` | Extra space between characters | `h1`, site title, button, table group row |
| `text-align` | Left, center, or right alignment | Hero, footer, captions, table cells |
| `text-decoration` | Adds or removes the underline on links | Links, nav, TOC |
| `text-underline-offset` | Moves the link underline a little lower, easier to read | Links |
| `list-style` | `none` removes the bullets from a list | Main menu, TOC |
| `overflow-wrap` | `anywhere` lets long words or links break onto the next line instead of overflowing | Photo credits |
| `vertical-align` | Lines an inline element up with the text next to it | Radio buttons |

## CSS — layout

| Property | Usage | Used in |
| --- | --- | --- |
| `display` | `block` puts an element on its own line; `inline-block` stays in the line but takes a height; `flex` lines children up in a row | Header, menu, TOC, card grid, labels, images |
| `flex-wrap` | Lets flex items move to the next line when there is no room | Header, menu, TOC, card grid |
| `align-items` | Lines flex items up vertically (`center`) | Header |
| `justify-content` | Spreads flex items out horizontally (`space-between`) | Header, card grid |
| `@media (max-width: 768px)` | Rules that apply only on narrow screens | End of CSS |
| `@media (prefers-reduced-motion: reduce)` | Rules for people who turned off animations in their system settings | End of CSS |

## CSS — other

| Feature | Usage | Used in |
| --- | --- | --- |
| `:root { --name: value; }` | Defines CSS variables once, for colors, spacing, and font sizes | Top of CSS |
| `var(--name)` | Uses a CSS variable's value | Most rules |
| `rgba(r, g, b, a)` | A color with transparency; `a` goes from 0 (invisible) to 1 (solid) | Shadow variables |
| `transition` | Animates a change smoothly, e.g. color on hover over 0.2s | Links, nav, buttons, cards, inputs |
| `transform: translateY()` | Moves an element up or down without affecting the layout around it | Card hover lift |
| `accent-color` | Colors the browser's built-in radio buttons and checkboxes | Radios |
| `cursor` | `pointer` shows the hand cursor | Button, radio labels |
| `/* … */` | A CSS comment, used to label each part of the file | Throughout CSS |

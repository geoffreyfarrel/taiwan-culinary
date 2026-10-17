# 台灣美食 (taiwan-culinary)

A static website introducing Taiwan's food culture, built for a school co-working web design
course at NTPU. Its purpose is learning HTML and CSS basics, so the code itself is the
deliverable: it should show clear, correct use of semantic HTML and basic CSS.

The site covers four topics:

1. 台灣必吃經典小吃 — owner: Geoffrey
2. 台灣夜市美食 — owner: Geoffrey
3. 台灣特色甜點與飲料 — owner: partner
4. 台灣各地特色美食 — owner: partner

## Requirements

1. Every page is a full HTML document structured as `<head>` and `<body>`.
2. The body is structured with semantic elements, especially `<section>` and `<article>`
   (plus `<header>`, `<nav>`, `<main>`, `<footer>` where they fit).
3. Use lists, both unordered (`<ul>`) and ordered (`<ol>`).
4. Use links (`<a href>`), images (`<img>`), and video (`<video>`).
5. Use tables with `<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>`, `<td>`, including
   `colspan` (and `rowspan` where it makes sense).
6. Use a `<form>` with `method="post"`. No backend: the form only needs to be valid markup.
7. Use CSS for background color, padding, and margin. The site should look good while using
   only basic CSS.
8. Keep `HTML-CSS-REFERENCE.md` up to date: a table of every HTML tag and CSS property used,
   with a column explaining what it is for. Update it in the same change that introduces a new
   tag or property.

**Out of scope:**

- JavaScript in the midterm phase. JS will probably be added in the final-term phase. Do not
  add any script until the user says so.
- Any backend, database, or real form handling.
- CSS frameworks, preprocessors, build tools, or libraries. Vanilla HTML and CSS only.

## Constraints

- **Two phases:** midterm (HTML + CSS only), then final term (may add basic JS).
- **Two authors:** Geoffrey builds topics 1-2. The partner builds topics 3-4 and sends that
  code as a zip, which is merged into this repo by hand. Until then, navigation entries for
  topics 3-4 stay empty placeholders. Do not write topic 3-4 content.
- **Language:** all page content is in Traditional Chinese (`<html lang="zh-Hant-TW">`).
- **Browsers:** current desktop browsers. Pages open directly from the file system, so use
  relative paths only.
- Deadlines: <!-- TODO: midterm and final-term due dates -->

## Repository

| | |
| --- | --- |
| Host | GitHub — `git@github.com:geoffreyfarrel/taiwan-culinary.git` |
| Default branch | `main` |
| Branch naming | Work happens on `main`. The partner's code arrives as a zip, not as a branch. |
| Deploy target | None yet. Pages are opened locally in a browser. |
| Environments | Local only |

## Working rules

- Commits are atomic and follow Conventional Commits.
- No decorative emojis in code, comments, logs, commit messages, or docs.
- Patterns that must stay consistent are recorded in `CODINGSTYLE.md` (code) and `DESIGN.md`
  (appearance), not left to memory.

## Project standards

- Coding conventions and tech stack: @CODINGSTYLE.md
- Design tokens and styling rules: @DESIGN.md
- Recent work and session context: @LOG.md
- Architecture decisions: docs/adr/
- HTML tags and CSS properties used, with their purpose: `HTML-CSS-REFERENCE.md`

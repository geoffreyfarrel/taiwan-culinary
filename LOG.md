# Log

Working context for this repository, newest first. This is a handoff document for the next
session — it records what the code cannot say for itself.

> Maintained under Structure. Append after completing a unit of work.
> Record why, what was rejected, gotchas, and where you stopped — not a diff summary.
> Keep 10 entries verbatim; compact the rest into Consolidated history. Delete lines whose
> value has expired.

---

## 2026-10-17 — Real photos from Wikimedia Commons

**Did:** Replaced the 11 SVG placeholders with freely licensed JPGs (800px wide) from Wikimedia
Commons, fixed alt text to describe each photo, and added a `.credits` section to every page.
Photos are cropped to 16:10 in CSS.

**Why:** CC BY / CC BY-SA licenses require naming the author, linking the source, and naming
the license, hence the credits section. Rejected candidates: a "xiaolongbao" photo that was
really 包子, a cutlet photo of a cook's back, and photos with recognizable faces.

**Watch out:** If a photo is swapped, update its credit line on every page that uses it
(滷肉飯 and 大雞排 also appear on the home page). The video file itself is still missing; only
the poster is real.

**Next:** Add `videos/night-market.mp4`, then merge the partner's zip.

---

## 2026-10-17 — CSS redesign with ui-ux-pro-max

**Did:** Rewrote `css/style.css` and `DESIGN.md`: warm cream page, deep red brand, gold
accent, serif headings, red hero intro, pill nav and TOC, raised cards, rounded tables, and a
form panel. Recolored the placeholder SVGs. HTML unchanged.

**Why:** User asked for a redesign with the ui-ux-pro-max skill. Took its Restaurant/Food
palette but darkened the red (`#dc2626` to `#b91c1c`) so links pass AA on the cream page, and
replaced its cool slate gray with a warm one. Rejected its Newsreader/Roboto fonts: they are
Latin-only web fonts and the project uses no web fonts. Used system Chinese serif instead.

**Watch out:** Heading serif depends on the OS (PMingLiU on Windows, Songti on macOS), so it
looks slightly different per machine. 44px minimum touch targets and the gold focus ring are
deliberate. Keep them when adding controls.

**Next:** Same as below: real media, then merge the partner's zip.

---

## 2026-10-17 — Home page and topic 1-2 pages

**Did:** Built `index.html`, `pages/classic-snacks.html`, `pages/night-market.html`, and
`css/style.css`. Together they cover every course requirement: head/body, section/article,
ul/ol, links, img, video, tables with colspan/rowspan, and a POST form. Filled in
`HTML-CSS-REFERENCE.md` to match.

**Why:** Placeholder SVGs in `images/` stand in for photos so layout can be checked now. The
form sits on the home page because it is about all four topics.

**Watch out:** `videos/night-market.mp4` does not exist yet. The video shows its poster and
will not play until a file is added. Git does not track the empty `videos/` folder. Prices in
the snack table are rough ranges, labeled as such.

**Open:** Real photos and a video. Partner's topics 3-4 (nav links are `href="#"`, home cards
say 內容製作中).

**Next:** Swap in real media, then merge the partner's zip.

---

## 2026-10-17 — Project governance bootstrap

**Did:** Added `CLAUDE.md`, `CODINGSTYLE.md`, `DESIGN.md`, `LOG.md`, `docs/adr/`,
`HTML-CSS-REFERENCE.md`, and configs for Prettier, html-validate, and Stylelint. No site pages
yet.

**Why:** School web design project (NTPU). Goal is learning HTML and CSS, so the stack is
vanilla HTML/CSS. Layout chosen as home page + one page per topic so the partner's topics 3-4
can be dropped in as separate files. Look chosen: clean and light, white with one red accent.

**Watch out:** The partner delivers code as a zip, not through git. Check tools run through
`npx` with no `package.json`; keep it that way.

**Open:** Midterm and final-term due dates not recorded yet (TODO in `CLAUDE.md`).

**Next:** Build `index.html`, `css/style.css`, and the topic 1-2 pages. Nav links for topics 3-4
stay as placeholders.

---

## Consolidated history

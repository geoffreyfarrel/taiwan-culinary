# Log

Working context for this repository, newest first. This is a handoff document for the next
session — it records what the code cannot say for itself.

> Maintained under Structure. Append after completing a unit of work.
> Record why, what was rejected, gotchas, and where you stopped — not a diff summary.
> Keep 10 entries verbatim; compact the rest into Consolidated history. Delete lines whose
> value has expired.

---

## 2026-11-01 — Menu on partner pages, no h2 bar, home photos for topics 3-4

**Did:** Gave `pages/sweet.html` and `pages/food.html` the shared header and menu, pointed
them at `../css/style.css`, and moved each page's `h1` from her header into her `.intro`
(inline style dropped). Removed the red left bar from every `h2`. Added Commons photos to the
topic 3-4 home cards: 春水堂珍珠奶茶 (CC0) and 台南度小月擔仔麵 (CC BY 2.0). Then removed the
`.credits` section and the footer from every page, with their CSS and doc rows.

**Why:** Credits and footer removed at the user's request, after being told CC BY photos
require an attribution line; user chose removal over a separate credits page. User asked to remove the bar beside 本頁目錄 "and any similar component"; it was the
same rule on all `h2`, so it went sitewide. Danzai noodles stand for regional food because
beef noodle soup is already a topic-1 photo. The partner's hotlinked photos (shop and blog
sites) were not reused: not freely licensed.

**Watch out:** Her pages still fail html-validate and Prettier: unclosed `<article>` (傳統豆花)
in `sweet.html`, missing `</main>` in both, plus her formatting. Left as hers. The bubble-tea
photo is portrait, so the 250px card crop shows only the middle of the glass. Home page not yet
checked in a browser (Playwright blocks `file:` URLs).

The CC BY / CC BY-SA photos now have no on-page attribution; a credits page is the fix if
the course or license ever needs it (sources are each file's Commons page).

**Next:** Merge the partner's pages fully (structure, local images); add the video.

---

## 2026-10-31 — Beginner-level CSS, links to partner pages

**Did:** Linked the menu and home cards to the partner's `pages/sweet.html` (topic 3) and
`pages/food.html` (topic 4). Rewrote `css/style.css` from 543 to about 250 lines at a beginner
level: plain hex and px values, no CSS variables, transitions, shadows, `::marker`,
`:focus-visible`, or attribute selectors. Updated `DESIGN.md`, `CODINGSTYLE.md`, and the CSS
part of `HTML-CSS-REFERENCE.md` to match.

**Why:** User wants the CSS to look like a beginner wrote it after searching the web, not an
intermediate design system. User chose plain values over keeping a few variables.

**Watch out:** Photos are now a fixed 250px tall with `object-fit: cover`; the `focus-bottom`
class was removed, so the fried-chicken photo crops at the center. The current menu item is no
longer highlighted (the `aria-current` attribute stays for screen readers). The partner's pages
link `style.css` in `pages/` (missing), have no shared header, and use inline styles and
emojis. Not fixed: they are hers until the merge.

**Next:** Merge the partner's pages into the site's structure and stylesheet; add the video.

---

## 2026-10-17 — Real photos from Wikimedia Commons

**Did:** Replaced the 11 SVG placeholders with freely licensed JPGs (800px wide) from Wikimedia
Commons, fixed alt text to describe each photo, and added a `.credits` section to every page.
Photos are cropped to 16:10 in CSS.

**Why:** CC BY / CC BY-SA licenses require naming the author, linking the source, and naming
the license, hence the credits section. Rejected candidates: a "xiaolongbao" photo that was
really 包子, a cutlet photo of a cook's back, and photos with recognizable faces.

**Watch out:** The video file itself is still missing; only the poster is real.

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

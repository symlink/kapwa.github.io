# kapwa.dev

Marketing site for Kapwa, a technology studio run by Bobby Gaza. It's a static site with no build step, framework or dependencies, and it should stay that way.

## Files

- `index.html`: the whole site. CSS and JS are inline.
- `find-your-speed.html`: the "Find your speed" bubble quiz. It runs standalone and also inside the takeover on `index.html` (`find-your-speed.html#embed`).
- `og-image.png` (1200×630), `favicon.svg`, `favicon.png`, `apple-touch-icon.png`, `bobby-gaza.jpg`.

## Page order

| # | Section | Anchor | Label |
|---|---------|--------|-------|
| 1 | Header, nav, hero, J-card | `#top` | |
| 2 | Stats | | |
| 3 | Past sessions (cassette shell, tape strip) | `#past-sessions` | Side A |
| 4 | On repeat (tracklist) | `#beliefs` | Side B |
| 5 | Liner notes | `#liner-notes` | Liner notes |
| 6 | Choose your speed | `#speeds` | Side B |
| 7 | Contact and footer | `#contact` | |

The nav reads Side A → `#past-sessions`, Side B → `#beliefs`, Liner notes → `#liner-notes`. If sections move, keep the Side labels and the nav in page order.

## Copy

- Source of truth: the "kapwa.dev copy" page in Bobby's KAPWA Notion hub, which holds the "Site sections" database with one row per section.
- When asked to sync, pull rows with Status = Ready, apply them to the HTML, then set those rows to Live.
- Never publish Notion links anywhere on the site or in files.
- Quiz content lives in the Bubbles database on the "Find your speed" Notion page.
- Style:
  - Sentence case everywhere (the mono labels are uppercased by CSS, not in the text).
  - No em-dashes. Use a colon, a period or a middle dot (·).
  - Tape and audio language is the voice: sessions, sides, tracks, liner notes, speeds, rec.
  - "We" is fine. It's a studio.
- Locked hero:
  - Eyebrow: A technology studio · Recorded in Oakland, CA
  - Headline: Hi-fi engineering and leadership.
  - Subhead: We've built the iconic platforms fans live on. Now we help you build yours.
- If the headline changes, update `<title>`, the meta description, the og/twitter tags and `og-image.png` in the same commit.

## Brand

| Token | Value |
|-------|-------|
| Stripes s1 to s6 | `#F3B63F` `#EF8A32` `#E4573A` `#C93A45` `#9C2C57` `#5C2452` |
| Paper | `#F2EBDC` |
| Card | `#F8F4EA` |
| Ink | `#1B1816` |
| Ink 2 | `#3A342F` |
| Muted | `#5A524A` |
| Photo | `#E3D9C4` |
| On dark | `#D9D0BF` |
| Line on dark | `#4A423C` |

Type:
- Helvetica Neue for headlines and body.
- IBM Plex Mono (Google Fonts) for labels, eyebrows and numbers in the UI.
- The wordmark is URW Gothic, lowercase, always as outlined SVG paths and never live text. Keep the extended p slot (the gap below the p) intact.

## Design rules

- **Stripe budget.** The full sunset stripe band appears in three places only: the header, the contact band and the footer badge. Don't add more stripe bands.
- **Boxes mean "pick one."** Outlined boxes are only for the J-card and the speed cards. Everything else is open type on paper with thin rules.
- **Speed blocks.** SP = 1 block (s1), LP = 2 (s2, s3), EP = 3 (s4, s5, s6).
  - Right-aligned in menus.
  - Use the same counts everywhere, including the quiz.
- **Chevron tags** (the HS / E-HG row from tape packaging) are the house button accent. The gold chevron is the "keep going" cue.
- **Primary button.** The gold "Start a session" split button with the SP/LP/EP menu. Don't add new button styles.
- **Rec dot** breathes slowly (2.8s). Keep motion subtle.
- Every animation must respect `prefers-reduced-motion`.
- **Only one dark full-width block:** the footer. Past sessions is an inset card on purpose.

## Checks before every commit

1. Open the page at 1280px and 390px widths. There must be no horizontal scroll at 390 (`document.documentElement.scrollWidth === 390`).
2. The "Start a session" menus, J-card speeds, quiz takeover (open, Escape, back button) and the "Flip to Side B" link all still work.
3. No em-dashes in the visible text: `grep -n "—" index.html find-your-speed.html` returns nothing.
4. Keep commits to one section each. Commit messages are in sentence case.

## Don't

- Don't add a framework, bundler or package.json.
- Don't load fonts or scripts from anywhere except Google Fonts.
- Don't change the logo paths, the stripe colors or the locked hero copy without being asked.
- Don't put SPAN Digital anywhere beyond the R channel line in liner notes.

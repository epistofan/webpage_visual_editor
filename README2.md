# Page Builder

A single self-contained HTML file — a visual, drag-and-drop page builder for quick landing pages (no build step, no dependencies, works offline except for optional Google Fonts and embeds).

## Basics

- **Drag a block** from the left panel onto the canvas. Blocks already on the canvas can be dragged to reorder them too.
- **Click any text** to edit it in place. A floating panel appears with color, size, and alignment controls. Click a button/link and the same panel adds background color, corner radius, and padding controls for that button.
- **Hover a block** to reveal its toolbar (top-right): style presets, background color, border, shadow, outer margin, inner padding, reorder (↑↓), delete — plus a few controls that only appear on relevant blocks (photo lightbox toggle, sticky header).
- **Click a photo slot** to upload your own image (stored as base64, so exported files are fully self-contained — no separate image files to keep track of).

## Blocks available

**Structure:** Header (mobile burger menu, optional sticky), Hero, Divider, Text block, Table / price list, Embed / iframe (maps, video, booking widgets), Footer.

**Content grids:** 3-card features, Gallery 3×1, Photo cards (auto-adjusts columns to however many cards you have — a single leftover card centers itself instead of stretching full-width), Gallery carousel (same idea as the gallery, but with prev/next arrows and no limit on how many photos you add).

**Split layouts:** Text + Photo, Photo + Text, Address + Map (text on one side, a map/embed on the other), Photo with text overlay.

**Other:** Testimonial, CTA banner (can also take a background photo), Contact form, single Image, Photo carousel (one large image at a time, with arrows and dot indicators).

## Per-block tools

- **Style presets (★)** — one-click combos (card, thin border, soft shadow, rounded, reset), plus "apply to all blocks" to copy the current block's border/shadow/radius to every other block on the page.
- **Border (▢) / Shadow (▤)** — full manual control if the presets aren't quite right.
- **Margin (↕) / Padding (⬚)** — outer spacing between blocks vs. inner spacing within a block.
- **Photo modal (🔍)** — appears on any block with photos; toggles whether clicking a photo opens it full-size in a lightbox on the exported page.
- **Sticky header (📌)** — header-only; keeps it pinned to the top while scrolling.
- Blocks with repeatable items (header menu links, table rows, photo cards, carousel photos) get **+ / ×** controls on hover to add or remove items freely.

## Page-level controls (top bar)

- **Width** — desktop/tablet/phone presets or a custom px value (affects the content container's `max-width` for design purposes; real responsiveness at export is still driven by actual browser width via media queries, not this preset).
- **Page background** — color for the whole document.
- **Fonts** — a few heading+body font pairings (some load from Google Fonts, so the exported page needs internet to render them).

## Save / Load / Export

- **Save** — downloads `project.json` with the entire page state (blocks, content, styles, settings). Keep this if you want to keep editing later.
- **Load** — restores a page from a previously saved `project.json`.
- **Export HTML** — downloads a clean, standalone `page.html` with no editor UI, ready to deploy. Photos are embedded as base64 right in the file — nothing else to upload alongside it, just drop the one file on your server (e.g. straight into an nginx static folder; turn gzip on for it, base64 text compresses well).

## Notes / limitations

- Responsive behavior (mobile menu, column collapsing, sticky header) is driven by real browser width, not by the width preset in the editor — resize the actual browser window (or check on a real phone) to see it.
- CTA buttons/links have no `href` set by default — edit the exported HTML directly if you need real links, or ask for that feature to be added.
- No multi-page support yet — one page per file.
- No undo — use Save regularly if you're making risky edits.
- Google Fonts and any Embed blocks (maps, video, forms) load from the visitor's own browser at view time, not from your server — your server just serves the static HTML either way.

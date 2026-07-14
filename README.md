webpage visual block constructor
# Page Builder

A single self-contained HTML file — a visual, drag-and-drop page builder for quick landing pages (no build step, no dependencies, works offline except for optional Google Fonts).

## Basics

- **Drag a block** from the left panel onto the canvas.
- **Click any text** to edit it in place. Click a button/link to also get color, size, alignment, and (for buttons) background/radius/padding controls.
- **Hover a block** to reveal its toolbar (top-right): style presets, background color, border, shadow, margin, padding, reorder (↑↓), delete.
- **Click a photo slot** to upload your own image (stored as base64, so exported files are fully self-contained).

## Blocks available

Header (with mobile burger menu, optional sticky), Hero, 3-card features, Text, Table/price list, Embed/iframe, Gallery 3×1, Testimonial, CTA banner, Contact form, Footer, Divider, Image, Text+Photo, Photo+Text, Photo with text overlay, Carousel.

## Page-level controls (top bar)

- **Width** — desktop/tablet/phone presets or a custom px value (affects the content container's `max-width` for design purposes; real responsiveness at export is still driven by actual browser width via media queries).
- **Page background** — color for the whole document.
- **Fonts** — a few heading+body font pairings (some load from Google Fonts, so the exported page needs internet to render them).

## Save / Load / Export

- **Save** — downloads `project.json` with the entire page state (blocks, content, styles, settings). Keep this if you want to keep editing later.
- **Load** — restores a page from a previously saved `project.json`.
- **Export HTML** — downloads a clean, standalone `page.html` with no editor UI, ready to deploy (e.g. drop straight into your nginx static folder).

## Notes / limitations

- Responsive behavior (mobile menu, column collapsing, sticky header) is driven by real browser width, not by the width preset in the editor — resize the actual browser window (or check on a real phone) to see it.
- CTA buttons/links have no `href` set by default — edit the exported HTML directly if you need real links, or ask for that feature to be added.
- No multi-page support yet — one page per file.
- No undo — use Save regularly if you're making risky edits.

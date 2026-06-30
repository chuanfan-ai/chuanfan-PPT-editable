# Editable PPTX Rules

Use these rules when the output must become a practical PowerPoint file.

## What Must Stay Editable

Keep these as text or simple shapes:

- slide titles
- subtitles
- body copy
- captions
- chart labels
- diagram labels
- timeline labels
- table text
- footnotes and sources

## What May Be Flattened

These can be images:

- photos
- generated cover art
- screenshots
- complex backgrounds
- visual textures
- decorative abstract artwork
- map tiles
- highly complex information graphics

Tell the user when important elements are flattened.

## HTML Constraints

When using HTML as the source:

- Use a fixed 16:9 slide canvas.
- Keep text in normal HTML text nodes, not SVG text.
- Avoid nested transforms around text.
- Avoid `filter`, `backdrop-filter`, blend modes, and complex masks.
- Avoid long text inside auto-sized elements.
- Prefer absolute or grid-positioned boxes with stable dimensions.
- Give text boxes enough width and height.
- Use standard fonts or common fallbacks.
- Avoid very thin text below 16 px.

## Visual Tradeoff

For editable PPTX, choose:

- simple rectangles instead of complex card effects
- hairlines instead of shadows
- real text over text baked into images
- fewer but stronger shapes
- diagrams made from native text + shape objects

The full-fidelity HTML/PDF can be more expressive than the PPTX. The PPTX should remain useful, not necessarily identical pixel for pixel.

## Verification

Before delivery:

- Confirm the PPTX opens.
- Confirm page count matches.
- Confirm key text is selectable/editable.
- Confirm no text is clipped.
- Confirm images are not stretched.
- Confirm the first and last slide render correctly.

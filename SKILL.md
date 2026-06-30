---
name: chuanfan-ppt-editable
description: Create high-aesthetic, Chinese-first, editable presentation decks with an HTML-first workflow and best-effort PPTX/PDF export. Use when the user asks to make PPT, slides, deck, lecture slides, report decks, roadshow decks, courseware, or wants to combine Huashu-style HTML design quality with Guizang-style Swiss/magazine presentation aesthetics while preserving editable PowerPoint text where practical.
---

# chuanfan-PPT-editable

Use this skill as a PPT design director. Produce decks that can be presented beautifully in HTML/PDF and remain practical to edit in PPTX whenever the user needs PowerPoint output.

## Operating Model

Default to this sequence:

1. Understand the audience, topic, source material, output format, and editability requirement.
2. Convert the material into a page-level narrative table.
3. Pick a visual system based on the content, not personal taste.
4. Decide image needs page by page.
5. Build an HTML deck as the source artifact unless the user only needs a conventional PPTX.
6. Export PDF automatically when tooling is available.
7. Export editable PPTX when requested or clearly useful, while preserving editable text and simple shapes.
8. Verify the rendered deck before delivery.

If the user says "just do it" or gives only a topic, make conservative assumptions and proceed. State those assumptions in the final delivery note.

## Format Decision

- **HTML deck first**: default for designed talks, reports, roadshows, class presentations, and visually rich material.
- **Direct PPTX first**: use when the user explicitly needs ordinary PowerPoint editing, corporate templates, speaker collaboration, or strict `.pptx` compatibility.
- **PDF only**: use for locked visual delivery, printing, sharing, or when the HTML design uses effects that cannot survive editable PPTX export.

Never sacrifice the main message to preserve decorative editability. Preserve titles, body copy, labels, diagrams, and simple charts as editable objects first; allow only background art, photos, and complex visual effects to become images.

## Page Planning

Before designing, create a concise table:

```text
Page -> role -> key message -> layout -> image need -> editability priority
```

Use one page for one job:

- cover / hook
- context
- problem
- framework
- evidence or example
- comparison
- roadmap
- takeaway
- closing

Avoid continuous same-shape card pages. Every 3-4 pages, change rhythm with a hero page, data page, visual diagram, quote, or transition page.

## Style Selection

Read `references/style-system.md` when style choice matters or the user mentions aesthetics.

Fast defaults:

- AI, technology, engineering, education policy, strategy, data: Swiss system.
- Human story, industry observation, cultural topic, founder narrative: Magazine system.
- Internal report, leadership briefing, consulting style output: Executive system.
- Training and courseware: Courseware system.

If the user mentions Guizang, Swiss Style, grid, Helvetica, data-driven, or stronger presentation aesthetics, bias toward Swiss. If the user mentions Huashu, high-fidelity, HTML demo, motion, design review, or "make it beautiful", bias toward HTML-first and stronger visual polish.

## Source Material

When the user provides files, old slides, articles, screenshots, or notes:

1. Extract claims, structure, evidence, examples, and reusable images.
2. Do not paste long source paragraphs directly onto slides.
3. Put raw files in the project `sources/` folder if creating a project directory.
4. Put selected reusable images in `assets/` or `images/`.
5. Keep provenance notes for quotes, data, screenshots, and third-party material.

Do not invent data, quotes, institutions, product facts, release dates, or citations.

For current companies, products, people, laws, standards, software versions, or recent events, verify with current sources before making factual claims.

## Image Policy

Read `references/image-policy.md` before adding or generating images.

Default rules:

- Use real user-provided or official assets for real schools, brands, products, people, places, and screenshots.
- Use structured diagrams for abstract ideas: maps, matrices, timelines, capability systems, flywheels, and roadmaps.
- Use generated images only for concept visuals, cover art, neutral scene-setting, or redesigned information graphics.
- Do not add decorative stock-style images that do not carry information.

For editable PPTX, prefer diagrams made from text and shapes over flattened image infographics.

## Editable PPTX Rules

Read `references/editable-pptx-rules.md` before building a deck that needs PPTX.

Core constraints:

- Build in a 16:9 frame, usually 960 pt x 540 pt or 1920 px x 1080 px.
- Keep headings, body text, captions, axis labels, and diagram labels as real text.
- Use simple rectangles, lines, circles, and image objects.
- Avoid complex SVG text, CSS filters, heavy shadows, clipped text, unusual blend modes, and nested transforms.
- Use fewer fonts and predictable font weights.
- Keep text inside stable boxes with enough padding.

If a visual effect cannot be exported as editable PowerPoint objects, keep the HTML/PDF as the full-fidelity version and say what became flattened in PPTX.

## Construction Guidance

Use HTML/CSS when building the visual source:

- Fixed slide canvas.
- Strong grid.
- Stable margins and safe areas.
- Clear text hierarchy.
- No emoji as UI or content icons unless the topic itself requires them.
- No generic purple-blue gradient as a default "AI" look.
- No pile of rounded cards as the main aesthetic.
- Prefer lucide or simple line icons only when an icon clarifies meaning.

For Chinese decks:

- Prefer short slide titles.
- Use large line-height-safe boxes.
- Avoid tiny labels below 14 px in projected decks.
- Split dense content across pages instead of shrinking text.

## Export And Verification

When local tooling is available:

1. Render screenshots or a contact sheet for all slides.
2. Export PDF and check page count.
3. Export PPTX and check page count.
4. Open or inspect the PPTX enough to confirm that main text remains editable.
5. Run through `references/quality-checklist.md`.

If a local browser, converter, or dependency is blocked, explain the limitation and still provide the best available source artifact.

## Delivery Note

When finished, tell the user:

- where the HTML deck is
- where the PDF is, if generated
- where the PPTX is, if generated
- which parts are editable
- which parts are images or flattened effects
- any assumptions made from missing user input

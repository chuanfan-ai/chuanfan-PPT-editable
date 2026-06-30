---
name: chuanfan-ppt-editable
description: Create high-aesthetic, Chinese-first, editable presentation decks with an HTML-first workflow, stable visual-anchor planning, dual-channel image sourcing, candidate filtering, subject cutouts, and best-effort PPTX/PDF export. Use when the user asks to make PPT, slides, deck, lecture slides, report decks, roadshow decks, courseware, visually rich case-based presentations, or wants to combine Huashu-style HTML design quality with Guizang-style Swiss/magazine presentation aesthetics while preserving editable PowerPoint text where practical.
---

# chuanfan-PPT-editable

Use this skill as a PPT design director. Produce decks that can be presented beautifully in HTML/PDF and remain practical to edit in PPTX whenever the user needs PowerPoint output.

## Operating Model

Default to this sequence:

1. Understand the audience, topic, source material, output format, and editability requirement.
2. Convert the material into a page-level narrative table.
3. Pick a visual system based on the content, not personal taste.
4. Create a page-level visual-anchor and image-acquisition plan: memory point, carrier, search keywords, generation prompt, fallback, and asset role.
5. Build a filtered candidate asset pool before layout: real search assets, generated concept assets, cutout candidates, and explicit no-image decisions.
6. Select `selected_images` during layout, not during search. Match image choice to page role and visual system.
7. Build an HTML deck as the source artifact unless the user only needs a conventional PPTX.
8. Export PDF automatically when tooling is available.
9. Export editable PPTX when requested or clearly useful, while preserving editable text and simple shapes.
10. Verify the rendered deck before delivery.

If the user says "just do it" or gives only a topic, make conservative assumptions and proceed. State those assumptions in the final delivery note.

## Format Decision

- **HTML deck first**: default for designed talks, reports, roadshows, class presentations, and visually rich material.
- **Direct PPTX first**: use when the user explicitly needs ordinary PowerPoint editing, corporate templates, speaker collaboration, or strict `.pptx` compatibility.
- **PDF only**: use for locked visual delivery, printing, sharing, or when the HTML design uses effects that cannot survive editable PPTX export.

Never sacrifice the main message to preserve decorative editability. Preserve titles, body copy, labels, diagrams, and simple charts as editable objects first; allow only background art, photos, and complex visual effects to become images.

For PPTX delivery, do not flatten an entire designed slide into a screenshot or single full-slide PNG. Treat real photos, logos, screenshots, and generated artwork as image objects, but rebuild titles, body copy, captions, cards, diagrams, arrows, and labels as editable PowerPoint text/shapes.

## Page Planning

Before designing, create a concise table:

```text
Page -> role -> key message -> layout -> visual anchor -> visual carrier -> source plan -> fallback -> editability priority
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

## Visual Anchor Planning

Every page must receive a visual decision, but not every page needs a picture. Decide what should carry the audience's memory of the page:

- Brand anchor: logo, wordmark, signature product, mascot, packaging, object, or icon that immediately identifies the case.
- Real image: named brand, product, place, person, event, campus, factory, store, or screenshot.
- Generated image: abstract future scene, concept cover, neutral metaphor, or non-factual illustrative scene.
- Editable diagram: process, matrix, flywheel, comparison, roadmap, capability map, data relationship, or agent workflow.
- Typography-only: quote, strong claim, transition, closing, or page where words are the intended impact.
- No extra visual asset: dense source proof, appendix-like content, or a page where visuals would distract.

For case pages, brand pages, people pages, product pages, and place pages, first identify the most precise brand anchor. It may be a small logo, mascot, product, packaging, or signature object; do not default to a large photo. Use a large scene photo only when the argument is about place, channel, scale, or environment. For abstract pages, prefer editable diagrams before generated image infographics.

For mascot, character, product, packaging, red envelope, plush toy, symbolic object, or logo-like anchors, prefer an isolated subject asset: source image -> subject cutout -> transparent PNG -> independent image object. Examples include LABUBU, Snow King, CS50 Duck, branded red envelopes, and signature packaging. Keep the original background only when the background itself proves channel, place, scale, or usage context.

Before building slides, write a compact visual plan:

```text
Page -> memory point -> visual carrier -> search keywords -> generation prompt -> fallback -> final file
```

Use this plan during construction and delivery. Do not invent or fake real-world visuals. If a real asset cannot be sourced reliably, use a clearly non-factual generated concept image or an editable diagram instead.

Do not place every visual in the same fixed slot. Choose placement from the page job:

- Hero or opening page: full-bleed, oversized, or background visual with strong title overlay.
- Company/context page: real store/product image may lead the slide, with analysis text beside or below it.
- Framework page: use a centered editable diagram; avoid decorative photos.
- Case page: choose the smallest sufficient proof. A logo + representative object can be stronger than a large scene photo when the point is brand cognition; use a collage only when multiple evidence types are necessary.
- Takeaway page: use action cards, roadmap, or typography; a small supporting visual is optional.

During QA, scan the contact sheet. If three or more pages repeat the same text-left/image-right layout without a content reason, redesign the rhythm before delivery.

Also inspect visual taste, not just asset existence. A page fails QA if real assets look like a raw collage, compete with the title, use mismatched crops, or appear included only to prove they were found. Prefer one strong, well-cropped proof image or one clean subject cutout over several weak images.

## Image Acquisition Pipeline

When a deck needs meaningful visuals, use the pipeline below before rendering:

1. Generate 1-3 page-specific image search keywords from the page message and visual anchor. Prefer concrete entity queries over abstract nouns: brand + product, brand + mascot, brand + packaging, company + store, person + organization, course + artifact.
2. Use two acquisition channels:
   - Real asset channel: user-provided files, official assets, screenshots, public search results, product pages, press pages, and stable attributable sources.
   - Generated asset channel: concept visuals, future scenes, neutral metaphors, abstract covers, and non-factual illustrations.
3. Put every useful result into a candidate pool. Do not insert images directly into slides from search results.
4. Filter candidates in two passes:
   - Relevance: does the candidate match the current page's concrete subject, proof, emotion, or memory point?
   - Quality: is it clear, high-resolution enough, well-composed, low-watermark, low-noise, not overloaded with text, and suitable for the intended crop or cutout?
5. Decide whether each retained candidate should become a normal crop, small proof mark, hero image, screenshot, grid item, subject cutout, or be rejected.
6. Let the layout stage choose `selected_images` from the filtered pool. A candidate can be good but still unused if the layout needs typography, a diagram, or a smaller brand anchor.
7. If no candidate passes relevance and quality, do not force a weak image. Use an editable diagram, typography-only page, or explicit no-extra-asset decision.

Record the candidate pool in the asset manifest:

```text
page | anchor | query_or_prompt | channel | source | local_file | relevance | quality | role | selected | notes
```

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
- Keep a local asset manifest for every non-trivial image: page, visual anchor, source/generation note, file path, crop/ratio, and fallback decision.

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

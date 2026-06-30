# Image Policy

Images should carry meaning. Do not add pictures just to make a slide look filled.

## Required Visual Decision

Every page needs a visual decision, not necessarily a picture. Choose one carrier:

```text
brand anchor | real image | official/brand asset | screenshot | generated concept image | editable diagram | typography-only | no extra asset
```

Record the decision in the page visual plan before construction. This prevents both extremes: under-illustrated text decks and mechanical picture stuffing.

The visual decision also includes placement. Do not default every meaningful image to a right-side rectangle. Let the asset's role decide whether it should be full-bleed, cropped as evidence, placed as a collage, used as a small proof mark, or omitted.

Real assets need art direction. Use fewer, stronger images; crop with intent; align image temperature, background, and scale with the page. Avoid raw collages where unrelated photos, logos, and diagrams fight each other.

For brand or case pages, look for the smallest visual that makes recognition instant: wordmark, logo, mascot, signature product, packaging, or symbolic object. Do not make a large photo the default. The image size follows the argument: brand cognition may need only a logo and object; channel or place arguments may need a store/campus/factory photo.

## Subject Cutouts

For mascot, character, product, package, red envelope, plush toy, symbolic object, or logo-like proof, prefer a cut-out subject asset:

```text
source image or screenshot -> isolate subject -> transparent PNG -> independent image object in PPTX
```

Use this for anchors such as LABUBU, Snow King, CS50 Duck, branded red envelopes, product packaging, retail props, and other recognizable objects. A clean cutout often works better than a full rectangular photo because it can sit inside the layout, overlap typography or shapes intentionally, and avoid the "stock image box" feeling.

Keep the original background only when the background is part of the evidence: store scene, campus, factory, classroom, event, shelf placement, channel context, crowd scale, or usage environment.

Do not fake real logos, mascots, products, packaging, screenshots, or people with AI generation. Use official, user-provided, or attributable source images, then crop or cut out the subject. Generated cutouts are acceptable only for non-factual conceptual objects.

If automated background removal is unavailable or unreliable, use an image editing or generation tool to extract the subject. If that still fails, keep a clean crop and record the fallback in the asset manifest.

## Decision Test

Ask for every image:

```text
If this image is removed, does the audience lose information, proof, emotion, or memory?
```

If the answer is no, skip it.

Also ask:

```text
Is this page about a concrete entity, an abstract relationship, or a sentence that should stand alone?
```

- Concrete entity: look for a real or official visual.
- Brand cognition: prefer logo, mascot, product, package, or signature object.
- Abstract relationship: build an editable diagram.
- Strong sentence: consider typography-only.
- Weak or decorative image idea: skip it.

## Source Priority

1. User-provided assets.
2. Official assets for real organizations, products, people, and places.
3. Public-domain or openly licensed material.
4. Generated images for abstract, conceptual, or illustrative needs.
5. Honest placeholder when the right image is unavailable.

For external real assets, prefer pages that are stable and attributable: official websites, official press pages, public company profiles, product pages, and reputable media. Save the asset locally and record the source URL or generation note in an asset manifest.

## Use Real Assets For

- school campuses
- company logos
- products
- UI screenshots
- named people
- named places
- press images
- user-provided materials

Do not replace these with generic AI imagery.

Do not use AI generation to fake a real person's portrait, a brand mascot, a product photo, a logo, a store, a campus, or a screenshot. If a real visual cannot be obtained, switch to a labeled concept image or an editable diagram.

## Use Diagrams For

- AI capability systems
- learning workflows
- governance models
- roadmaps
- before / after comparisons
- matrices
- flywheels
- data flows

For editable PPTX, build diagrams from text and shapes when possible.

## Use Generated Images For

- cover concepts
- future scenes
- neutral visual metaphors
- abstract backgrounds
- stylized conceptual illustrations
- redesigned non-factual infographics

Generated images should match the chosen style system:

- Swiss: minimal, geometric, high-contrast, grid-aware, limited colors.
- Magazine: editorial, photographic or art-directed, image-led.
- Executive: restrained, clean, low distraction.
- Courseware: explanatory and clear.

Generated images should be used sparingly in case-based decks. They work best for cover atmosphere, future scenes, and conceptual transitions; they are a fallback for real-world pages, not a substitute for real proof.

## Asset Manifest

For each selected image, keep a simple local record:

```text
page | anchor | carrier | source_or_prompt | local_file | ratio | fallback
```

Use the manifest during verification to confirm that images match page meaning, exist locally, and are not stretched. For cutouts, record whether the asset has a transparent background and whether it came from an official/user-provided/attributable source.

## Ratios

Use stable ratios:

- cover or hero: 16:9 or 21:9
- side image: 4:3 or 16:10
- image grid: consistent 3:2, 4:3, or 16:10
- concept diagram: 16:9 or native slide-width layout

Do not mix random image proportions in one visual group.

For cutout PNGs, preserve the native subject proportion. Do not force a mascot, bottle, package, phone, or vertical product into a 16:9 box.

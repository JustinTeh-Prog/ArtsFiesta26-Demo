# Claude Design & Build Instruction Prompt — Arts Fiesta 2026 “Lightchaser”

## Role and objective

Act as a senior creative developer, interaction designer and front-end engineer. Build a complete, production-ready, public-facing static website for **Arts Fiesta 2026**.

The site must feel like a **lightchaser journey** centred on a lighthouse. It should combine:

- A painterly, two-dimensional children’s-book illustration style
- Small musician, filmmaker, dancer, writer, photographer and art-object characters
- A sleek, minimal, predominantly black and maroon interface
- Restrained neon glows, atmospheric fog and a moving lighthouse beam
- One continuous, long-scroll narrative with obvious but refined scroll-driven animation

The moodboard images supplied alongside this prompt are the visual authority. Use them to understand texture, composition, atmosphere and character treatment, but create an original website rather than copying any single reference.

Build the actual website, not a wireframe or design essay.

---

## Non-negotiable technical constraints

1. Use only:
   - Semantic HTML5
   - CSS3
   - Vanilla JavaScript

2. Do not use:
   - React, Vue, Svelte or other frameworks
   - Bootstrap, Tailwind or component libraries
   - GSAP, jQuery, Lenis or other animation libraries
   - A build system, package manager or server-side code
   - Remote image hotlinking
   - Runtime crawling or external API dependencies

3. The site must work when deployed as a normal static website on GitHub Pages or any basic static host.

4. Keep all editable event data in one JavaScript data file where practical.

5. Use `IntersectionObserver`, CSS transitions and lightweight `requestAnimationFrame` logic for scroll effects.

6. Ensure the website remains fully usable when JavaScript is unavailable or motion is reduced.

7. Do not invent:
   - Admission prices
   - Registration requirements
   - Band names
   - Missing performance titles
   - Awards, club histories or unsupported claims
   - Additional programme timings

8. Remove all internal planning language from the public website, including:
   - TBC
   - Buffer
   - Setup
   - Teardown
   - Line check
   - Soundcheck
   - Shift handover
   - Riser or floor instructions
   - Administrative remarks

---

## Required output structure

Create and return the complete contents of this file structure:

```text
/
├── index.html
├── css/
│   └── styles.css
├── js/
│   ├── content.js
│   ├── photo-manifest.js
│   └── main.js
├── asset/
│   ├── aaf25_photostream/
│   ├── brand/
│   │   └── scape-logo-placeholder.svg
│   ├── fonts/
│   │   ├── KabelBlack-Regular.woff2
│   │   └── ITCBenguiatCondensed-Bold.woff2
│   ├── illustrations/
│   │   ├── lighthouse/
│   │   └── characters/
│   ├── textures/
│   │   └── grain-placeholder.png
│   └── moodboard/
└── README.md
```

The existing photo folder is:

```text
asset/aaf25_photostream/
```

Web paths must use forward slashes even if the original local path was written with backslashes.

At generation time, scan the filenames available in `asset/aaf25_photostream/` and write them into `js/photo-manifest.js`. A browser cannot enumerate a static folder on its own, so do not attempt runtime directory scanning.

---

## Visual direction

### Core concept

The page is a journey towards a lighthouse at night.

The lighthouse should act as the site’s visual anchor and scroll-progress device:

- Its beam slowly sweeps as the visitor scrolls.
- The beam reveals illustrated characters, club cards, programme entries and photo fragments.
- The lighthouse can shift between foreground, midground and silhouette states across sections.
- The beam should feel atmospheric rather than like a harsh spotlight.
- Small painterly characters can appear as musicians, dancers, paintbrushes, film reels, cameras, books, instruments and theatrical props.
- The characters should feel handmade and storybook-like, while the interface remains sharp and minimal.

Create original illustrations or simple original SVG/CSS placeholders when final illustrated assets are not yet available.

### Style balance

Use the painterly elements as focal accents. Do not make every UI element textured.

The interface should remain:

- Clean
- Spacious
- Dark
- Editorial
- Cinematic
- Easy to scan
- Mobile-friendly

Avoid:

- Generic cyberpunk styling
- Rainbow neon
- Excessive glow
- Heavy glassmorphism
- Large blocks of centred body text
- Cartoonish rounded SaaS cards
- Busy particle effects
- Constant motion
- Illegible text over illustrations

---

# DESIGN SYSTEM — Visual language derived from the supplied artwork

This section is the implementation authority for the website’s visual style. Treat the supplied images as one coherent development set: polished key art, colour exploration, character studies, lighthouse iterations and a final isolated lighthouse render.

Do not merely place the images onto a dark page. Reproduce their **visual logic** throughout the interface: composition, colour restraint, imperfect shapes, mixed-media texture, lighting, character design and pacing.

## 1. Design thesis

The design should feel like:

```text
an illustrated night signal × a student sketchbook × a restrained editorial website
```

The artwork is not glossy fantasy art and it is not conventional neon cyberpunk. Its identity comes from the tension between:

- A nearly black cinematic field
- A warm lighthouse flare
- Muted maroon and dusty mauve shapes
- Loose pencil and crayon-like marks
- Flat, cut-paper forms
- Small absurd or charming arts-object characters
- A precise, minimal interface beneath the handmade surface

The frontend must therefore follow a two-layer model.

### Layer A — Functional interface

- Crisp layout
- Strong hierarchy
- Legible text
- Accurate spacing
- Restrained borders
- Predictable controls
- Accessible interaction

### Layer B — Illustrated atmosphere

- Grain
- Pencil texture
- Slightly irregular silhouettes
- Warm light
- Painterly masks
- Small character moments
- Imperfect motion

The illustration layer may feel handmade. The functional layer must never feel unfinished.

---

## 2. Reference-by-reference visual study

The six supplied references should be understood as follows.

### Reference 1 — Arts Fiesta title key art

Observed qualities:

- Strong central symmetry organised around the lighthouse.
- The lighthouse lens sits at the exact visual centre and acts as the brightest point.
- The title is integrated into the two opposing beams rather than placed in a normal rectangular header.
- The cream outer letterforms create tall framing arches on both sides.
- The background is not flat black. It contains dense red, green and neutral grain, similar to scanned film, charcoal dust or low-light sensor noise.
- Maroon lettering remains dark and earthy rather than fluorescent.
- The lighthouse is composed from broad flat colour fields with visible directional hatching.
- The beam has a hand-brushed core, soft smoky falloff and scratch-like radial streaks.
- The composition is mostly static and iconic. Drama comes from contrast and silhouette, not from many objects.

Frontend implication:

- Treat the hero as a poster-like lockup.
- Keep the lighthouse and wordmark visually dominant.
- Do not crowd the hero with cards, floating badges or long copy.
- Allow only essential event metadata and the countdown to compete with the key art.
- If the supplied Arts Fiesta wordmark is available as a transparent image, use it as artwork. Do not attempt to reconstruct the hand-lettered wordmark with ordinary HTML text.
- The required Kabel Black font applies to interface headings and a fallback title, not to replacement of the illustrated logo.

### Reference 2 — Lighthouse and creature colour exploration

Observed qualities:

- Loose graphite contours remain visible beneath translucent digital colour.
- Mauve, dusty rose, blue-grey, muted green and parchment tones overlap without perfect registration.
- Edges are soft and sometimes doubled, creating a watercolour or tracing-paper effect.
- The creatures are reduced to compact silhouettes with one recognisable feature.
- Faces use minimal marks: dot eyes, a simple mouth and almost no detail.
- The lighthouse is tall and irregular, with stacked architectural masses rather than a mathematically perfect cylinder.
- White space is used generously around studies.

Frontend implication:

- Decorative characters should be sparse and surrounded by negative space.
- Colour washes may extend slightly outside linework.
- Use transparent texture layers and low-opacity overlays instead of polished vector gradients.
- Keep characters readable at small sizes by limiting them to three to five dominant shapes.
- Avoid detailed cartoon faces, realistic anatomy or elaborate shading.

### Reference 3 — Guitar and fountain-pen character study

Observed qualities:

- Objects become characters through limbs and posture rather than costumes or facial complexity.
- The guitar character is wide and expressive, with exaggerated arms supporting the instrument.
- The pen character is vertical and compact, using the nib as a clear silhouette.
- Pencil lines vary in pressure, overlap and confidence.
- Feet and hands are broad gestural marks.
- The design is playful but not juvenile; it resembles an animation model sheet.

Frontend implication:

- Base each club character on one immediately recognisable object.
- Use pose to communicate activity:
  - Guitar or amplifier for Bands
  - Music note, mouth or microphone for Vocomotives
  - Pen nib or book for Writer’s Block
  - Camera body for Photogcircle
  - Paint tube, brush or palette for Visual Arts
  - Film camera, projector or screen for SUTDio
- Do not dress generic mascots in club costumes.
- Character motion should be pose-like: lean, glance, step, point or sway by a few pixels.

### Reference 4 — Wind ensemble object study

Observed qualities:

- Instruments retain their long, unusual silhouettes.
- The humour comes from scale contrast and staging.
- Figures are drawn with thin, scratchy monochrome marks.
- Small accessories, such as a music stand or lantern-like object, establish a scene without needing a full background.
- Composition is horizontal and spacious.

Frontend implication:

- Use clusters of two or three objects to suggest an activity.
- Let unusual instrument silhouettes cross grid boundaries as decorative elements.
- Keep detail in the line art, while the surrounding interface stays quiet.
- For wide desktop sections, use small narrative vignettes at the edges rather than filling the entire viewport.

### Reference 5 — Lighthouse iteration sheet

Observed qualities:

- The lighthouse silhouette was explored through tapering, stacked segments.
- A spiral ribbon or band wraps around the tower and creates directional movement.
- The top resembles a satellite dish, projector or receiving instrument rather than a traditional roof.
- Several versions separate the top, tower and bottom disc so the structure appears suspended or assembled.
- Windows are tiny arched cut-outs.
- Forms are intentionally uneven: leaning rims, varying widths and asymmetrical curves.
- Coral-red tests are used as selective blocks, not as an all-over colour.

Frontend implication:

- Preserve the lighthouse’s peculiar identity. Do not replace it with a generic nautical lighthouse icon.
- Use the spiral band as a recurring line motif for dividers, scroll paths and timeline connectors.
- Use floating discs and separated layers for section transitions.
- Allow slight optical imbalance and hand-built geometry.
- Do not “correct” the tower into perfect circles and straight engineering lines.

### Reference 6 — Isolated finished lighthouse

Observed qualities:

- The final lighthouse uses a black field, dusty mauve tower sections, maroon structural parts and cream bands.
- Flat fills are enriched by short linear hatching rather than realistic lighting.
- The lens is overexposed warm white with a large soft aura.
- Each beam contains many thin hand-drawn streaks inside a fog-like cone.
- The satellite-dish top creates a strong asymmetrical crown.
- The lower tower is visually heavy, while the separated top and bottom discs make it feel slightly magical or mechanical.
- The silhouette remains readable even without surrounding text.

Frontend implication:

- Use this reference as the canonical lighthouse model.
- If an isolated transparent asset is supplied, preserve its proportions and avoid cropping the dish.
- The main beam should originate from the exact centre of the lens.
- Use CSS or SVG for beam extension, atmosphere and masking, but keep the illustrated lighthouse itself as an image asset where possible.
- Do not add glossy highlights, bevels, 3D extrusion or photorealistic stone texture.

---

## 3. Style synthesis

### Primary visual characteristics

The final website must consistently express all of these:

1. **Dark illustrated editorialism**  
   Large negative spaces, oversized titles, precise content alignment and art-led pacing.

2. **Warm signal light**  
   Cream-white light is the emotional focal point. It should feel like projection, stage light or a beacon, not a cool LED.

3. **Mixed-media imperfection**  
   Pencil, dry-brush, crayon, scanned paper and slight colour misregistration.

4. **Restricted colour**  
   Black, maroon, dusty mauve, cream and desaturated slate dominate. Avoid adding unrelated hues.

5. **Object-based characters**  
   Instruments and art tools become small performers through posture and minimal facial marks.

6. **Asymmetry within structure**  
   The layout grid is disciplined, while illustrations tilt, overlap and drift slightly.

7. **Slow reveal**  
   The page should feel discovered by light, not presented all at once.

### Emotional tone

Aim for:

- Curious
- Nocturnal
- Handmade
- Slightly strange
- Youthful without appearing childish
- Theatrical without becoming ornate
- Intimate despite the public-event scale

Do not aim for:

- Corporate event branding
- Futuristic technology conference
- Luxury fashion minimalism
- Haunted-horror imagery
- Nautical tourism
- Generic school carnival
- Bright children’s animation

---

## 4. Colour architecture

The user-specified colours remain the official UI palette. The artwork contains additional sampled tones that may be used only as supporting illustration and lighting tokens.

### Official UI palette

```css
:root {
  --maroon: #953939;
  --cream: #D7CBB1;
  --slate: #4E5A5A;
  --black: #1B1B1D;
  --charcoal: #272D2D;
  --deep-slate: #2F3737;
}
```

### Moodboard-derived supporting tones

These approximate tones are derived from the supplied key art and lighthouse render:

```css
:root {
  --art-void: #0D0609;
  --art-aubergine: #211316;
  --art-plum: #4D2C2F;
  --art-wine-shadow: #684B4B;
  --art-dust-mauve: #9F8C96;
  --art-lamp-cream: #F3E2D5;
  --art-paper: #EFEBED;
}
```

Rules:

- The supporting tones do not replace the required title and text colours.
- Use `--maroon` for interface emphasis and official heading accents.
- Use `--art-plum` and `--art-wine-shadow` inside illustrations, shadows and textured masks.
- Use `--art-dust-mauve` for lighthouse surfaces and occasional illustration fields.
- Use `--art-lamp-cream` only at the hottest part of the lens, beam and selected highlights.
- Use `--cream` for readable body copy.
- Use `--slate` for subdued metadata and low-contrast structure.
- Never introduce bright cyan, electric blue, acid green or saturated violet.

### Recommended visual ratio

Across a typical viewport:

```text
70–78%  black, charcoal and near-black
12–18%  maroon, plum and dusty mauve
6–10%   cream and warm light
0–4%    slate or muted supporting colour
```

The page should read as dark before it reads as colourful.

### Light behaviour

The “neon” requirement must be interpreted as a **soft phosphorescent lighthouse glow**, not tube neon.

Use:

- Warm cream core
- Off-white brush streaks
- Dusty maroon reflected halo
- Low-opacity grey fog
- Soft radial falloff
- Irregular mask edges

Avoid:

- Clean laser cones
- Sharp white polygons
- Cyan-magenta bloom
- Multiple coloured outer glows
- Heavy `box-shadow` around every component

---

## 5. Texture system

Texture is essential to the identity but must be controlled.

### Texture hierarchy

#### A. Global film grain

Use one fixed, non-interactive overlay above backgrounds and below core text.

Target appearance:

- Fine multichannel speckle
- Slight red and green variation
- No obvious repeating tile
- Low enough opacity that body text remains clean

Recommended implementation:

```css
.site-grain {
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: 80;
  opacity: 0.055;
  mix-blend-mode: soft-light;
  background: url("../asset/textures/grain-placeholder.png") repeat;
  background-size: 240px 240px;
}
```

Rules:

- Keep the grain static. Do not animate it every frame.
- A carefully compressed texture image is preferred to a full-screen animated SVG filter.
- Ensure the overlay does not create banding or materially reduce performance.
- Reduce opacity on small mobile screens.
- Never place grain between text glyphs and their background at high opacity.

#### B. Illustration hatching

Use directional pencil or dry-brush marks inside the lighthouse and characters.

Characteristics:

- Short, uneven strokes
- Generally follow the form
- 6–15% opacity
- Mostly maroon-black or cream-black
- Not a uniform crosshatch pattern

Implementation options:

- Texture baked into transparent PNG/WebP illustrations
- SVG masks with hand-drawn paths
- Small clipped texture layers

Do not simulate all hatching with repeated CSS stripes; it will look mechanical.

#### C. Colour misregistration

Selected illustration fills may sit one to three pixels outside the line art.

Use this only on artwork, never on functional text or controls.

Possible method:

```css
.character__wash {
  transform: translate(2px, 1px) rotate(-0.4deg);
  opacity: 0.72;
}
```

#### D. Paper and wash

Use paper texture only in:

- Character close-ups
- Workshop activity illustrations
- Rare section-transition panels
- Lightbox captions or small editorial inserts

Do not convert the whole page into beige paper. The dominant world remains black.

---

## 6. Shape language

### Lighthouse

Mandatory characteristics:

- Tapered stacked tower
- Slight asymmetry
- Spiral cream band
- Small arched windows
- Separated or floating base disc
- Projector/satellite-dish crown
- Wide central lens
- Mauve and maroon blocks
- Hand-drawn surface marks

Do not use:

- Red-and-white maritime stripes
- A generic triangular roof
- A photorealistic coastal tower
- Perfectly cylindrical geometry
- Blue ocean imagery

### Characters

Each character should use:

- One dominant recognisable art object
- Two to four limb shapes
- Dot or oval eyes
- One simple mouth where useful
- A readable silhouette at 80–140 px
- Slightly overlarge hands or feet
- A pose that suggests the club’s activity

Character complexity budget:

```text
3–5 major shapes
1–3 facial marks
1 signature prop
1 dominant pose
```

Avoid:

- Human bodies with object heads unless strongly justified
- Detailed clothing
- Shading-heavy anime treatment
- Mascot costumes
- Identical body templates reused for every club

### UI geometry

The interface should contrast with the loose artwork.

Use:

- Straight editorial alignments
- Thin rules
- Minimal corner radii
- Occasional notched or clipped corners
- Open cards without heavy containers
- Tall, narrow labels
- Long horizontal dividers inspired by a beam
- Spiral or curved connectors used sparingly

Recommended radii:

```css
--radius-hairline: 2px;
--radius-card: 4px;
--radius-media: 6px;
```

Do not use 16–32 px rounded SaaS cards.

---

## 7. Stroke and edge language

Illustrated lines should feel scanned or pressure-sensitive.

Use:

- Variable stroke thickness
- Slight wobble
- Occasional doubled contour
- Broken line segments
- Rounded line caps
- Imperfect joins
- Dark plum or graphite rather than pure black where possible

Approximate illustration stroke ranges:

```text
Small character: 1.5–2.5 px
Medium character: 2–4 px
Large lighthouse detail: 3–7 px
```

Functional UI rules and borders must stay crisp at one device pixel.

This separation is important:

```text
illustration edges = imperfect
interface edges = precise
```

---

## 8. Typography and wordmark behaviour

### Official illustrated wordmark

The hero reference contains a custom hand-drawn Arts Fiesta title integrated with the lighthouse beam.

Rules:

- Treat it as a logo or key-art image.
- Preserve its aspect ratio.
- Do not typeset over the illustrated letters.
- Do not apply CSS text shadows to the logo image.
- Do not recolour it unless a prepared alternate asset is supplied.
- Keep sufficient empty space around the tall outer letterforms.
- On mobile, allow the wordmark and lighthouse to stack or crop within a controlled poster frame, but do not shrink them into illegibility.

### Interface typography

Use Kabel Black Regular for:

- Section titles
- Major numeric moments
- Large calls to action
- Fallback text title when the illustrated wordmark is unavailable

Use ITC Benguiat Condensed Bold for:

- Body copy
- Programme details
- Club descriptions
- Captions
- Navigation
- Labels

Editorial treatment:

- Prefer large type with short lines.
- Use line breaks intentionally.
- Keep paragraphs left-aligned except for the hero lockup.
- Avoid thin weights, as neither type family is intended to appear delicate.
- Use cream body text on dark surfaces.
- Use maroon for large headings, not long paragraphs.
- Let text occupy clean zones that are free from dense grain and beam streaks.

Suggested scale:

```css
:root {
  --step--1: clamp(0.82rem, 0.78rem + 0.18vw, 0.95rem);
  --step-0: clamp(1rem, 0.94rem + 0.28vw, 1.18rem);
  --step-1: clamp(1.25rem, 1.12rem + 0.62vw, 1.65rem);
  --step-2: clamp(1.65rem, 1.36rem + 1.35vw, 2.5rem);
  --step-3: clamp(2.2rem, 1.72rem + 2.3vw, 4rem);
  --step-4: clamp(3.1rem, 2.2rem + 4.2vw, 6.8rem);
  --step-5: clamp(4.2rem, 2.6rem + 7.5vw, 10rem);
}
```

---

## 9. Layout and composition

### Grid

Use a twelve-column desktop grid with:

```css
--page-gutter: clamp(1.25rem, 4vw, 5rem);
--content-max: 1440px;
--text-max: 62ch;
```

Preferred compositions:

- Hero: central symmetry around the lens
- Synopsis: asymmetrical 7/5 split
- Photo stream: full-bleed ribbons with controlled page gutters
- Club finder: staged landscape or offset twelve-column field
- Programme: 4/8 split or two parallel lanes
- Activities: editorial masonry or alternating 5/7 layouts
- Footer: return to central symmetry

### Negative space

The concept sketches use large amounts of blank paper. Translate that into dark negative space.

Requirements:

- Each major section should have at least one clean visual pause.
- Do not fill every gap with a doodle.
- Keep a minimum clear zone of approximately one character-width around major illustrations.
- Use section spacing in the range of `clamp(6rem, 12vw, 12rem)`.
- Allow some sections to feel almost empty before the next beam reveal.

### Controlled overlap

Artwork may overlap:

- Section boundaries
- Photo edges
- Timeline lines
- The outer grid gutter

Artwork may not overlap:

- Body copy
- Form controls
- Countdown digits
- Essential times
- Focus indicators
- Lightbox controls

### Z-index plan

Use a documented layer system:

```css
:root {
  --z-background: 0;
  --z-atmosphere: 10;
  --z-art: 20;
  --z-content: 30;
  --z-nav: 60;
  --z-grain: 80;
  --z-dialog: 100;
}
```

The grain may sit visually above the art but must not interfere with dialog readability.

---

## 10. Lighthouse beam construction

The beam is the central interaction device and must resemble the artwork.

### Beam anatomy

Build it from three layers:

1. **Core flare**
   - Small, almost white radial gradient
   - High brightness
   - Slight warm tint
   - Limited radius

2. **Atmospheric cone**
   - Wide cream-to-transparent gradient
   - Blurred edge
   - Low opacity
   - Mild asymmetry

3. **Hand-drawn streak layer**
   - Thin irregular SVG paths or a transparent texture
   - Varying lengths
   - Concentrated near the lens
   - Fades before reaching the viewport edge

The beam should not be one clean CSS triangle.

Suggested visual variables:

```css
:root {
  --beam-core: #F3E2D5;
  --beam-mid: rgb(215 203 177 / 0.34);
  --beam-edge: rgb(215 203 177 / 0);
  --beam-shadow: rgb(149 57 57 / 0.12);
}
```

### Beam masking

Use `mask-image`, `clip-path`, SVG or layered pseudo-elements to reveal content.

Provide fallbacks:

- Without mask support, use opacity and transform reveals.
- Essential content must already be readable.
- The beam should enhance discovery, not gate information.

### Beam placement

- The beam origin must stay visually attached to the lighthouse lens.
- When the lighthouse changes scale or position, update the beam transform origin.
- Avoid a beam that rotates from the viewport centre when the lighthouse is elsewhere.
- The hero may use opposing left and right beams.
- Interior sections may simplify the beam to one directional sweep or a narrow vertical reveal.

---

## 11. Component styling

### Navigation

Use a slim, quiet progress navigation.

Desktop:

- Vertical series of lighthouse-window-like markers
- Current marker glows cream
- Labels appear on hover and focus
- Maroon active line

Mobile:

- Compact top progress bar or bottom beacon control
- No full-height side rail
- Always preserve access to the menu and skip link

### Buttons and links

Primary action:

- Text-led
- Cream label
- Maroon underline or beam trace
- Minimal dark surface
- One small directional glyph

Secondary action:

- Transparent
- Slate-to-cream hover transition
- No filled pill

Interaction:

```text
hover/focus duration: 160–240 ms
scale change: none or max 1.01
translation: 2–4 px
glow: local and subtle
```

Avoid:

- Large rounded buttons
- Gradient fills
- Pulsing CTAs
- Arrow icons that move continuously

### Cards

Use cards only where the content genuinely needs grouping.

Card appearance:

- Transparent or near-black surface
- One-pixel cream or slate rule at low opacity
- Four-pixel maximum radius
- No heavy drop shadow
- Internal artwork may break the edge
- On hover or focus, reveal a warm beam wash from one side

Suggested border:

```css
border: 1px solid rgb(215 203 177 / 0.16);
```

Suggested active border:

```css
border-color: rgb(215 203 177 / 0.42);
```

### Tags

- Compact rectangular labels
- No pill shape
- Border-only by default
- Cream text
- Maroon active state
- Use an icon or text label in addition to colour

### Programme timeline

- Main line resembles a narrow vertical beam.
- Time labels are fixed-width with tabular numerals.
- Programme entries sit slightly off-axis, alternating where space permits.
- Setlist expansion uses a clean plus/minus control.
- Expanded content enters with a short vertical reveal, not an accordion bounce.
- Workshop lane uses a secondary slate line rather than a completely different colour.

### Lightbox

- Near-black surface
- Large image with generous margins
- Cream controls
- Minimal caption
- Grain reduced or disabled inside the dialog
- Do not add decorative illustrations behind the enlarged photograph

---

## 12. Photography treatment

The event photography must remain documentary and should not be forced into the illustration style.

Use:

- Natural photographs
- Dark surrounding frames
- Cream captions
- Occasional maroon rule
- Varied aspect ratios
- Offset ribbon movement
- Mild image grain only if it does not destroy detail

Optional treatment:

- On initial state, use slightly reduced saturation and contrast.
- On hover, focus or beam reveal, restore the natural image.
- Do not apply the same maroon duotone to every photo.
- Avoid aggressive blend modes that make faces or performances unclear.

The photo stream should look like physical prints passing through a projector beam.

---

## 13. Illustration-to-interface integration

### Correct integration

- A character leans on a timeline line.
- A camera character appears beside the photostream heading.
- A pen-nib character points towards Writer’s Block.
- An instrument silhouette crosses behind a club title.
- The spiral lighthouse band becomes a section divider.
- The lens briefly illuminates a programme time.

### Incorrect integration

- Characters inside every button.
- Sketch-paper backgrounds behind all text.
- Random doodles used as bullet points throughout.
- Multiple large illustrations competing in one viewport.
- Grain so strong that typography appears distressed.
- Painterly decoration used to hide weak layout.

Use a maximum of:

```text
1 major illustration focal point per viewport
2–4 small supporting objects per viewport
```

---

## 14. Motion language

Motion should resemble an illustrated scene coming alive, not a software-product demo.

### Core motion traits

- Slow beam sweep
- Small pose changes
- Layered parallax
- Masked reveal
- Slight rotational imperfection
- Short stop-motion-like transitions for characters
- Long still moments between movements

### Timing

Recommended:

```css
:root {
  --ease-reveal: cubic-bezier(0.22, 0.8, 0.2, 1);
  --ease-settle: cubic-bezier(0.2, 0.65, 0.25, 1);
  --duration-fast: 180ms;
  --duration-ui: 260ms;
  --duration-reveal: 700ms;
  --duration-scene: 1400ms;
}
```

Guidance:

- Hero beam entrance: approximately 1.6–2.2 seconds
- Text reveal: 450–800 milliseconds
- Character pose shift: 280–500 milliseconds
- Section atmosphere change: 800–1400 milliseconds
- Hover feedback: below 260 milliseconds

### Movement ranges

- Character translation: 4–18 px
- Character rotation: 0.4–2 degrees
- Background parallax: 2–8% of scroll distance
- Foreground parallax: 8–18%
- Hover scale: maximum 1.01

Avoid:

- Large elastic easing
- Constant bobbing
- Fast cursor-following particles
- Continuous spinning
- Floating every illustration indefinitely
- Page-wide blur transitions
- Scroll-jacking

### Reduced motion

Under `prefers-reduced-motion: reduce`:

- Stop beam rotation.
- Remove parallax.
- Reveal all essential content immediately.
- Keep only short opacity transitions where acceptable.
- Preserve the static lighthouse and warm lens glow.

---

## 15. Responsive interpretation of the key art

### Desktop

- Preserve the iconic central poster composition.
- Lighthouse occupies roughly 30–45% of viewport height in the hero.
- Wordmark can extend across the beam.
- Countdown and event metadata sit below or beside the central lockup without covering the lens.

### Tablet

- Reduce beam width.
- Keep the lighthouse central.
- Move metadata into a clean block below the artwork.
- Use fewer peripheral characters.

### Mobile

- Treat the hero as a vertical poster.
- Place the lighthouse above the countdown or partially behind the title.
- Do not compress the full wide wordmark beyond legibility.
- Use a prepared stacked wordmark asset or a controlled fallback title.
- Let one beam travel vertically or diagonally rather than forcing the desktop bilateral beam.
- Decorative characters become a vertical sequence through later sections.

---

## 16. Venue-partner treatment

Arts Fiesta 2026’s venue partner is **\*SCAPE**.

Public-facing credit:

```text
Venue Partner — *SCAPE
```

Rules:

- Include the credit near the hero event metadata and in the footer.
- Keep it visually secondary to Arts Fiesta.
- If an official \*SCAPE logo asset is supplied, use that asset without redrawing, stretching or recolouring it beyond approved variants.
- Preserve clear space around the logo.
- Do not describe \*SCAPE as organiser, sponsor or co-presenter unless separately confirmed.
- Do not place the partner logo inside the lighthouse beam or merge it with the Arts Fiesta wordmark.

---

## 17. Content-density rules

The website should communicate a substantial event without reading like a proposal document.

Limits:

- Hero supporting text: maximum two short lines
- Synopsis: maximum two short paragraphs
- Club description: one sentence
- Activity description: one or two sentences
- Programme entry: title first; setlist hidden until expanded
- Section introduction: maximum 30 words where possible
- No mission statement repeated in multiple sections

Use the long-term Arts Fiesta ambition as background direction, not as a large manifesto.

Preferred editorial approach:

```text
show the event now
briefly establish where it came from
quietly signal where it is going
```

---

## 18. CSS token foundation

Use or adapt this token structure in `styles.css`:

```css
:root {
  /* Official palette */
  --maroon: #953939;
  --cream: #D7CBB1;
  --slate: #4E5A5A;
  --black: #1B1B1D;
  --charcoal: #272D2D;
  --deep-slate: #2F3737;

  /* Artwork support */
  --art-void: #0D0609;
  --art-aubergine: #211316;
  --art-plum: #4D2C2F;
  --art-wine-shadow: #684B4B;
  --art-dust-mauve: #9F8C96;
  --art-lamp-cream: #F3E2D5;
  --art-paper: #EFEBED;

  /* Semantic colour */
  --bg-page: var(--black);
  --bg-deep: var(--art-void);
  --bg-raised: var(--charcoal);
  --bg-muted: var(--deep-slate);
  --text-primary: var(--cream);
  --text-muted: #9E9A90;
  --text-heading: var(--maroon);
  --line-subtle: rgb(215 203 177 / 0.16);
  --line-visible: rgb(215 203 177 / 0.36);
  --focus-ring: var(--art-lamp-cream);

  /* Lighting */
  --beam-core: var(--art-lamp-cream);
  --beam-mid: rgb(215 203 177 / 0.34);
  --beam-edge: rgb(215 203 177 / 0);
  --beam-reflection: rgb(149 57 57 / 0.12);
  --lens-glow:
    0 0 14px rgb(243 226 213 / 0.90),
    0 0 42px rgb(215 203 177 / 0.48),
    0 0 96px rgb(149 57 57 / 0.16);

  /* Type */
  --font-title: "Kabel Black", "Arial Black", sans-serif;
  --font-text: "ITC Benguiat Condensed", Georgia, serif;

  /* Layout */
  --page-gutter: clamp(1.25rem, 4vw, 5rem);
  --content-max: 1440px;
  --text-max: 62ch;
  --section-space: clamp(6rem, 12vw, 12rem);

  /* Shape */
  --radius-hairline: 2px;
  --radius-card: 4px;
  --radius-media: 6px;

  /* Motion */
  --ease-reveal: cubic-bezier(0.22, 0.8, 0.2, 1);
  --ease-settle: cubic-bezier(0.2, 0.65, 0.25, 1);
  --duration-fast: 180ms;
  --duration-ui: 260ms;
  --duration-reveal: 700ms;

  /* Layering */
  --z-background: 0;
  --z-atmosphere: 10;
  --z-art: 20;
  --z-content: 30;
  --z-nav: 60;
  --z-grain: 80;
  --z-dialog: 100;
}
```

---

## 19. Visual acceptance criteria

The design is successful only if all statements below are true.

- The first impression is black, maroon and warm cream rather than multicoloured neon.
- The lighthouse is recognisably the same unusual satellite-dish, spiral-band design language as the supplied references.
- The hero resembles a cinematic illustrated poster, not a standard event landing page.
- The wordmark and lighthouse remain the visual centre.
- Grain is visible in large dark areas but does not damage text clarity.
- Characters look like handmade object studies rather than generic vector mascots.
- Illustrations contain slight wobble, hatching and colour offset.
- UI alignment, controls and typography remain precise.
- Large amounts of negative space are preserved.
- The beam feels smoky, streaked and warm rather than geometrically perfect.
- Cards are minimal and not heavily rounded.
- Motion is slow, intentional and tied to discovery.
- The page remains complete and legible with animation disabled.
- The \*SCAPE venue-partner credit is accurate and visually secondary.
- No sketch-sheet white background is used as a full-page production background.
- The final site does not look like cyberpunk, a SaaS product or a generic children’s website.

---

## 20. Production asset guidance

Treat the supplied files according to their role:

- Polished key art: eligible for hero use if high-resolution and cleared for publication.
- Isolated lighthouse render: preferred production illustration for the hero and recurring lighthouse motif.
- Sketch sheets: visual development references; do not place them wholesale into the public website.
- Character sketches: use as shape and line-language references, or clean them into transparent final assets before use.
- Grain: create a dedicated lightweight production texture rather than using a compressed screenshot of the key art.
- Partner branding: use only an official \*SCAPE logo file supplied for the project.

When producing new illustration assets, match the references through:

- Muted flat fills
- Visible pencil or dry-brush linework
- Warm cream highlights
- Slightly imperfect edges
- Sparse facial features
- Simple, expressive poses
- Transparent backgrounds
- Exported WebP or PNG at appropriate display resolution

Do not trace or automatically vectorise the sketches into perfectly smooth paths.

---

## Colour system

Use these exact colours as the primary palette:

```css
:root {
  --maroon: #953939;
  --cream: #D7CBB1;
  --slate: #4E5A5A;
  --black: #1B1B1D;
  --charcoal: #272D2D;
  --deep-slate: #2F3737;
}
```

Application:

- Main page background: `#1B1B1D`
- Alternate section surfaces: `#272D2D` and `#2F3737`
- Primary headings and key accents: `#953939`
- Main text: `#D7CBB1`
- Secondary labels, borders and fog: `#4E5A5A`
- Neon effect: restrained maroon halos derived from `#953939`
- Use cream highlights sparingly for the lighthouse beam and selected text

The maroon heading colour may be used directly for large text. For small text, ensure sufficient contrast through size, weight, background treatment or a slightly lighter derived maroon tint.

---

## Typography

### Required fonts

- Title font: **Kabel Black Regular**
- Text font: **ITC Benguiat Condensed Bold**

Use licensed local font files only:

```css
@font-face {
  font-family: "Kabel Black";
  src: url("../asset/fonts/KabelBlack-Regular.woff2") format("woff2");
  font-display: swap;
}

@font-face {
  font-family: "ITC Benguiat Condensed";
  src: url("../asset/fonts/ITCBenguiatCondensed-Bold.woff2") format("woff2");
  font-display: swap;
}
```

Do not download, embed or redistribute unlicensed font files. Assume the user will provide licensed files at the specified paths.

Fallbacks:

```css
--font-title: "Kabel Black", "Arial Black", sans-serif;
--font-text: "ITC Benguiat Condensed", Georgia, serif;
```

Typography behaviour:

- Large display titles: Kabel Black
- Body copy, club descriptions and programme text: ITC Benguiat Condensed Bold
- Use `font-variant-numeric: tabular-nums` for the countdown
- Keep line lengths around 45–70 characters
- Use uppercase sparingly for labels
- Avoid extreme letter spacing

---

## Page architecture

Build one continuous page in this order:

1. Hero and countdown
2. Arts Fiesta synopsis
3. Arts Fiesta 2025 photo stream
4. Participating-club “lightbeam finder”
5. Programme schedule
6. Things to do: workshops and booths
7. Closing lighthouse scene and footer

Add a minimal fixed navigation indicator with section names or small luminous markers. It should collapse into a compact progress control on mobile.

---

# Public-facing copy and section requirements

## 1. Hero and countdown

### Primary copy

```text
ARTS FIESTA 2026
CHASE THE LIGHT.
```

Supporting line:

```text
One rooftop. Twelve student arts groups. An evening of music, movement, theatre, art and making.
```

Event line, using this wording:

```text
Arts Fiesta 2026 happening at *SCAPE Treetop
```

Event details:

```text
2 October 2026
2:00 PM – 8:00 PM
*SCAPE Treetop, Singapore
Venue Partner — *SCAPE
```

### Countdown

Create a live countdown in this exact format:

```text
DD:HH:MM:SS
```

Use these timezone-safe constants:

```js
const COUNTDOWN_START = "2026-08-31T23:59:00+08:00";
const EVENT_START = "2026-10-02T14:00:00+08:00";
```

Required behaviour:

- Before `COUNTDOWN_START`, show:
  - `THE LIGHT APPEARS IN`
  - A countdown to 31 August 2026, 23:59 SGT, or a restrained “Countdown begins 31 Aug, 23:59 SGT” state
- From `COUNTDOWN_START`, count down to `EVENT_START`
- Use Singapore time through the explicit `+08:00` offset
- Update once per second
- Pad each unit to at least two digits
- Do not rely on the visitor’s local timezone
- At the event start, freeze at `00:00:00:00` and reveal:
  - `THE LIGHT IS ON`
- Use a clean digit-slide, mask or flip transition without imitating a generic airport board
- Prevent layout shift by fixing digit widths

Suggested labels:

```text
DAYS  HOURS  MINUTES  SECONDS
```

Primary call to action:

```text
FOLLOW THE LIGHT
```

Secondary action:

```text
SEE LAST YEAR
```

### Hero motion

- Begin with a near-black scene and a distant lighthouse glow.
- As the page loads, the beam sweeps once and reveals the title.
- Small illustrated arts characters emerge briefly at the edge of the light.
- The hero should have depth through layered silhouettes and subtle parallax, not 3D rendering.
- Keep interaction smooth at 60 fps on modern devices.

---

## 2. Synopsis of Arts Fiesta

Section label:

```text
WHAT THE LIGHT FINDS
```

Heading:

```text
A NIGHT OF STUDENT-MADE ART
```

Use this copy:

```text
Arts Fiesta is a by-students-for-students showcase created to platform SUTD’s Arts Cluster. Following its successful 2025 debut at Our Tampines Hub, the 2026 edition moves to *SCAPE Treetop and opens the experience to youths across Singapore.

Music, dance, theatre, visual art, writing and hands-on making share one stage, building towards an annual platform where emerging SUTD talent can be seen, heard and discovered.
```

Keep this section to the two short paragraphs above. Do not turn the long-term ambition into a large manifesto or claim that Arts Fiesta is already a cornerstone of Singapore’s arts scene.

Design:

- Use a large editorial text block with short line lengths.
- Let painterly instruments and art objects drift into view at the section edges.
- Animate individual phrases only once as they enter the viewport.
- Do not use a conventional boxed “About” card.

---

## 3. Arts Fiesta 2025 photo stream

Section label:

```text
LAST YEAR, IN THE LIGHT
```

Heading:

```text
ARTS FIESTA 2025
```

Supporting copy:

```text
A moving stream of performances, people and small moments from last year’s Arts Fiesta.
```

Source all local images from:

```text
asset/aaf25_photostream/
```

Link the section and its final call to action to:

```text
https://flic.kr/s/aHBqjCxdN1
```

Required interaction:

- Create two or three staggered horizontal image ribbons.
- Their movement should respond to vertical scroll with different speeds and directions.
- Do not force continuous autoplay when the page is idle.
- Use a mix of landscape and portrait crops while preserving meaningful subjects.
- Clicking an image opens an accessible lightbox.
- The lightbox must support:
  - Keyboard navigation
  - Escape to close
  - Previous and next controls
  - Visible focus styles
  - Image alt text
- Add a final external link:
  - `OPEN THE FULL 2025 ALBUM`
- Mark the Flickr link as external and use `rel="noopener noreferrer"`.

Performance:

- Use native lazy loading.
- Include explicit width and height or aspect ratios to prevent layout shift.
- Do not load every full-resolution image immediately.
- Prefer responsive derivatives if supplied.

---

## 4. Participating-club lightbeam finder

Section label:

```text
FIND THE MAKERS
```

Heading:

```text
TWELVE CLUBS, ONE BEAM
```

Intro copy:

```text
Move through the gallery and let the lighthouse reveal the performers, makers and storytellers behind Arts Fiesta 2026.
```

### Core interaction

Create a “lightbeam finder” rather than a standard card grid:

- Place twelve illustrated club objects or small characters in a dark, painterly scene.
- Tie the lighthouse beam’s horizontal or diagonal position to scroll progress.
- When the beam reaches an object, reveal the club name, one-line description and participation tag.
- Keep every club accessible in the DOM even before its visual reveal.
- On keyboard focus or tap, reveal the same information without requiring precise pointer movement.
- On mobile, convert the scene into a vertical illuminated gallery.
- Provide visible filter controls:
  - All
  - Performance
  - Workshop
  - Booth
- The filter must be optional. The full list should remain easy to browse.
- Do not make the visitor “hunt” for essential information.

### Club content

Use the display names, one-line descriptions and participation tags below.

#### Vocomotives Club

```text
A vocal ensemble bringing contemporary favourites to life through layered voices and stage presence.
```

Tags:

```text
Performance
```

#### Ballroom Dancing Club

```text
Partnered dance in polished ballroom styles, moving from dramatic tango to sweeping Viennese waltz.
```

Tags:

```text
Performance
```

#### Wind Ensemble Club

```text
A concert wind ensemble performing cinematic, jazz and contemporary repertoire with scale and colour.
```

Tags:

```text
Performance
```

#### Chamber Ensemble Club

```text
Small-ensemble musicians creating intimate, detail-rich performances across classical and contemporary works.
```

Tags:

```text
Performance
```

#### Chinese Orchestra Club

```text
Chinese orchestral music blending traditional instruments, familiar melodies and percussion-led energy.
```

Tags:

```text
Performance
Booth
```

#### Dance DerivativeZ Club

```text
A high-energy dance crew translating contemporary tracks into sharp, expressive choreography.
```

Tags:

```text
Performance
Booth
```

#### Bands Club

```text
Student bands spanning pop, rock, alternative and indie sounds across eight live sets.
```

Tags:

```text
Performance
Booth
```

#### Drama Club

```text
Theatre-makers building live stories through performance, improvisation and collaborative play.
```

Tags:

```text
Workshop
Performance
```

#### Visual Arts Club

```text
A visual art community for drawing, making, experimentation and hands-on creative work.
```

Tags:

```text
Workshop
Booth
```

#### SUTDio Club

```text
An interdisciplinary art collective exploring human experience through physical works and interactive installations.
```

Tags:

```text
Booth
```

#### Writer’s Block

```text
A home for student writers, readers and playful literary encounters.
```

Tags:

```text
Booth
```

#### Photogcircle

```text
A photography community capturing people, performances and shared moments through image-making.
```

Tags:

```text
Booth
```

### Accuracy rule

The official ROOT directory is the authority for current club names. Do not add unsupported histories, achievements or claims. The one-line descriptions above are concise editorial copy for this event website.

---

## 5. Programme schedule

Section label:

```text
FOLLOW THE BEAM
```

Heading:

```text
2 OCTOBER 2026
```

Supporting copy:

```text
From the first chord to the final set, follow the stage and workshop programme from 2:00 PM to 8:00 PM.
```

### Timeline design

- Use a vertical timeline resembling a descending lighthouse beam.
- Time markers should remain highly legible.
- On desktop, allow parallel “Stage” and “Workshop” lanes.
- On mobile, stack items chronologically.
- Each performance can expand to show its setlist.
- Do not show internal notes, TBC labels or setup remarks.
- Do not show activities before 2:00 PM or after 8:00 PM.
- Include the 8:00 PM performance because it begins at the end boundary.

### Public programme content

#### 2:00 PM — Bands Club

```text
Bands 1 & 2 — Pop/Rock
```

#### 2:30 PM — Bands Club

```text
Bands 3 & 4 — Alternative/Indie
```

#### 3:30 PM — Wind Ensemble Club × Chamber Ensemble Club

Setlist:

```text
Great Music Adventures — John Williams, arranged by Michael Sweeney
Dream Solister — Yusuke Kato, arranged by Akito Matsuda
Hard Times Come Again No More — arranged by The Westerlies, transposed by Ong Yong Kang
Time Flows Ever Onward (from Frieren: Beyond Journey’s End) — Evan Call, arranged by Daniel Kim
So What — Miles Davis, arranged by Michael Philip Mossman
St. Thomas — Sonny Rollins, arranged by Mark Taylor
```

Parallel workshop:

```text
Visual Arts Club — Shrink Dink Keychain Workshop, Slot 1
```

#### 4:00 PM — Vocomotives Club

Setlist:

```text
My Way — KATSEYE
Every Summertime — NIKI
ATM — JIHYO
Release Me — Arcando
```

#### 4:30 PM — Ballroom Dancing Club

Setlist:

```text
Sway (Tango) — Michael Bublé, DJ Maksy remix
Merry-Go-Round of Life (Viennese Waltz) — Joe Hisaishi
```

#### 5:00 PM — Drama Club Workshop

```text
Beginner-friendly theatre ice-breakers, improvisation and devised scene-making.
```

#### 6:00 PM — Chinese Orchestra Club

Setlist:

```text
大鱼 (Big Fish) — Zhou Shen, arranged by Giannong (Tina) Wu
青花瓷 (Blue and White Porcelain) — Jay Chou
老虎磨牙 (Tiger Grinding Its Teeth) — percussion piece composed by 安志顺
```

Parallel workshop:

```text
Visual Arts Club — Shrink Dink Keychain Workshop, Slot 2
```

#### 6:30 PM — Drama Club

```text
Live drama performance
```

Do not invent a skit title.

#### 6:50 PM — Dance DerivativeZ Club

Setlist:

```text
it boy — bbno$
REDRED — CORTIS
Sticky (feat. GloRilla, Sexyy Red & Lil Wayne)
```

#### 7:30 PM — Bands Club

```text
Bands 5 & 6 — Alternative/Indie
```

#### 8:00 PM — Bands Club

```text
Bands 7 & 8 — Rock
```

---

## 6. Things to do: workshops and booths

Section label:

```text
STEP INTO THE LIGHT
```

Heading:

```text
MAKE, PLAY, WRITE, SHOOT
```

Intro copy:

```text
Between performances, explore hands-on workshops, interactive art, instruments, books, photography and club showcases.
```

Use a modular gallery of activity cards. Each card should include:

- Club name
- Activity type
- A concise description
- A small original illustrated icon or character
- A clear visual cue if it is a workshop or booth

Do not display PDPA planning columns or internal operating notes.

### Workshops

#### Visual Arts Club — Shrink Dink Keychain Workshop

```text
Draw a miniature design with markers and pencils, cut it from shrink plastic, watch it bake down, then finish it as a keychain.
```

Optional supporting note:

```text
Club facilitators will handle the baking and help with cutting or assembly where needed.
```

#### Drama Club — Theatre and Improvisation Workshop

```text
Warm up with playful ice-breakers, try beginner-friendly improvisation games, then work in a small group to devise a short scene.
```

Optional supporting note:

```text
Suitable for first-timers and experienced performers who want to experiment, collaborate and share a few laughs.
```

### Booths

#### Writer’s Block — Literary Playground

```text
Choose a mystery read at Book Blind Date, add a thought to the Hear Me Out board, draw a paper fortune and browse books, bookmarks, stickers and keychains.
```

#### Chinese Orchestra Club — Club Showcase and Merchandise

```text
Meet the club, discover its work and browse Chinese Orchestra T-shirts, stickers, prints, postcards and keychains.
```

#### Dance DerivativeZ Club — Dance Showcase Booth

```text
Discover DDZ through club visuals and browse merchandise from past productions and Arts Fiesta.
```

#### SUTDio Club — IsTrue(human)

```text
Explore an exhibition about humanity in an age of automation through small artworks, creative journals, physical inspirations and a public interactive artwork.
```

Use this thematic line as secondary copy:

```text
Emotion, intuition, imperfection and presence: the things that cannot be computed.
```

#### Photogcircle — Walk-in Photobooth

```text
Step into a walk-in portrait session, have your photograph taken by club members and take home an instantly printed photostrip for a small fee.
```

Do not imply that advance registration is required.

#### Visual Arts Club — Art Merchandise

```text
Browse club-made sketchbooks, T-shirts, stickers and other visual-art merchandise.
```

Do not show unconfirmed future merchandise.

#### Bands Club — Instrument Try-outs and Showcase

```text
Try electric and bass guitars, amplifiers and a compact drum setup, watch clips from past club events and browse Bands merchandise.
```

---

## 7. Closing scene and footer

Closing heading:

```text
THE LIGHT IS WAITING
```

Closing copy:

```text
2 October 2026 · 2:00 PM–8:00 PM
*SCAPE Treetop, Singapore
```

Final actions:

```text
VIEW THE PROGRAMME
OPEN THE 2025 ALBUM
RETURN TO THE LIGHTHOUSE
```

Footer content:

```text
Arts Fiesta 2026
A by-students-for-students platform for the SUTD Arts Cluster
Venue Partner — *SCAPE
```

Include links to:

- The page’s programme section
- The Flickr 2025 album
- The official ROOT student organisation directory

Do not add unconfirmed social accounts, ticket links or sponsor logos.

---

# Scroll-driven animation specification

The scroll effects must be visible and memorable, but not obstruct content.

## Global lighthouse system

Create a CSS custom-property-based scroll system:

```css
--scroll-progress
--beam-angle
--beam-x
--beam-opacity
--fog-offset
```

Update these values through a throttled `requestAnimationFrame` loop.

The lighthouse beam should:

- Rotate or translate gradually across the page
- Brighten around major section entrances
- Reveal content using masks, gradients or opacity transitions
- Never make text unreadable
- Avoid following the cursor on touch devices
- Pause or simplify under reduced-motion preferences

## Section transitions

- Hero: title revealed by the first sweep of light
- Synopsis: text lines rise subtly through fog
- Photo stream: ribbons translate horizontally at different scroll ratios
- Club finder: characters illuminate one at a time
- Programme: the beam travels down the timeline
- Things to do: activity objects drift into a clean grid
- Footer: the lighthouse becomes a warm static beacon

## Motion limits

- No scroll-jacking
- No forced smooth-scroll library
- No long intro lockout
- No animation that delays access to content
- No rapidly flashing light
- No continuous high-cost canvas animation
- Use opacity and transforms instead of animating layout properties
- Respect `prefers-reduced-motion: reduce`

---

# Responsive behaviour

Design mobile-first and test at:

```text
360 px
390 px
768 px
1024 px
1440 px
```

Requirements:

- No horizontal page overflow
- Countdown remains on one line where possible; otherwise use a clean two-row layout
- Programme entries remain readable without horizontal scrolling
- Club finder becomes a vertical sequence on small screens
- Photo ribbons support touch and do not trap horizontal gestures
- Fixed navigation does not cover content
- Tap targets are at least 44 × 44 px
- Text remains readable at 200% zoom

---

# Accessibility

Meet WCAG 2.2 AA where practical.

Required:

- Semantic landmarks and heading hierarchy
- A visible skip link
- Keyboard-operable navigation, filters, accordions and lightbox
- Clear focus indicators
- Descriptive image alt text
- Empty alt text for purely decorative painterly objects
- No information conveyed by colour alone
- Sufficient text contrast
- Reduced-motion support
- Dialog semantics and focus trapping for the lightbox
- `aria-expanded` for expandable programme items
- `aria-live="polite"` only for meaningful countdown state changes, not every second
- Do not make the lighthouse animation essential to understanding the page

---

# Performance and quality

Target:

- Lighthouse Performance score: 90+
- Accessibility score: 95+
- No console errors
- No broken paths
- No cumulative layout shift caused by images or fonts
- Smooth scrolling without main-thread stutter

Implementation guidance:

- Preload only the most important font and hero asset
- Use `font-display: swap`
- Lazy-load below-the-fold images
- Use WebP or AVIF where supplied, with fallbacks
- Minimise blur filters on large full-screen layers
- Use CSS gradients instead of large transparent PNGs where possible
- Defer non-critical scripts
- Keep JavaScript modular and commented
- Use passive scroll listeners
- Avoid unnecessary DOM duplication

---

# SEO and sharing

Include:

- Descriptive page title
- Meta description using concise copy such as:
  - `Arts Fiesta 2026 is a by-students-for-students showcase of SUTD’s Arts Cluster at *SCAPE Treetop, featuring performances, workshops, booths and exhibitions.`
- Open Graph tags
- Twitter card tags
- Favicon placeholders
- Canonical URL placeholder
- Theme colour
- Event structured data using JSON-LD

JSON-LD should include only verified details:

```json
{
  "@context": "https://schema.org",
  "@type": "Event",
  "name": "Arts Fiesta 2026",
  "startDate": "2026-10-02T14:00:00+08:00",
  "endDate": "2026-10-02T20:00:00+08:00",
  "eventAttendanceMode": "https://schema.org/OfflineEventAttendanceMode",
  "location": {
    "@type": "Place",
    "name": "*SCAPE Treetop",
    "address": {
      "@type": "PostalAddress",
      "addressCountry": "SG"
    }
  }
}
```

Do not invent an organiser address, ticket price or attendance status.

---

# Content and code architecture

In `js/content.js`, store:

- Event metadata
- Countdown dates
- Club data
- Programme entries
- Workshop data
- Booth data
- External links

Render repeatable cards and timeline entries from data rather than duplicating large blocks of HTML.

Suggested shape:

```js
export const eventData = {
  title: "Arts Fiesta 2026",
  start: "2026-10-02T14:00:00+08:00",
  end: "2026-10-02T20:00:00+08:00",
  countdownStart: "2026-08-31T23:59:00+08:00",
  venue: "*SCAPE Treetop",
  venuePartner: "*SCAPE",
  flickrAlbum: "https://flic.kr/s/aHBqjCxdN1",
  rootDirectory: "https://root.sutd.edu.sg/student-life/stu-org-directory"
};
```

Use stable IDs for deep links:

```text
#synopsis
#photostream
#clubs
#programme
#things-to-do
```

---

# Required README

Create a short `README.md` that explains:

1. How to preview the website with a simple local server
2. Where to add moodboard, lighthouse, character and texture assets
3. Where to place the official venue-partner logo if supplied
4. Where to place the licensed font files
5. How to update `photo-manifest.js`
6. How to edit club, programme and activity content
7. How to deploy to GitHub Pages
8. That the site has no framework or build step

Recommended local preview command:

```bash
python -m http.server 8000
```

---

# Final acceptance checklist

Before presenting the result, verify all of the following:

- [ ] The website uses HTML, CSS and vanilla JavaScript only.
- [ ] It is one long, scrollable page.
- [ ] The lighthouse is the central visual and interaction motif.
- [ ] Painterly storybook characters are present without making the UI childish or cluttered.
- [ ] The site uses the specified fonts and palette.
- [ ] The polished lighthouse, hand-drawn character and mixed-media texture language is visibly reproduced.
- [ ] The lighthouse retains its satellite-dish crown, spiral band, mauve-maroon structure and warm streaked beam.
- [ ] Grain is restrained and does not reduce text readability.
- [ ] The interface stays precise and minimal while illustrations remain deliberately imperfect.
- [ ] The hero reads as an illustrated poster rather than a generic event landing page.
- [ ] Venue Partner — *SCAPE is credited accurately and without implying a different role.
- [ ] The countdown starts at 31 August 2026, 23:59 SGT and targets 2 October 2026, 2:00 PM SGT.
- [ ] The countdown displays `DD:HH:MM:SS`.
- [ ] The local 2025 photo folder is used through a generated manifest.
- [ ] Every photo links or leads clearly to the Flickr album.
- [ ] All twelve participating clubs are shown with the correct participation modes.
- [ ] The club finder remains accessible without the visual gimmick.
- [ ] The programme includes only public activities from 2:00 PM to 8:00 PM.
- [ ] No TBC or administrative remarks appear.
- [ ] The booth and workshop content matches the supplied source document.
- [ ] No unverified facts have been invented.
- [ ] Mobile, keyboard and reduced-motion experiences work.
- [ ] There are no console errors, broken links or missing-path crashes.
- [ ] The final output includes all code files and a README.

---

# Source references

Use these as the factual source of truth:

```text
programme_flow.pdf
booth_workshop_details.pdf
https://root.sutd.edu.sg/student-life/stu-org-directory
https://flic.kr/s/aHBqjCxdN1
```

The moodboard images will be supplied separately and should be treated as visual references, not factual content.

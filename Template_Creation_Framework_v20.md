# Template Creation Framework v20
> **This is the source-of-truth PRD for the JioAICloud Greetings Template System.**
> All archetype definitions, wizard flows, track specs, layout rules, colour palettes, font pairings, illustration library, and prompt engineering patterns are defined here.
> Cursor: treat this file as the primary reference for ALL code decisions in this repo.

**Phase 1 — All 7 Archetypes + Layout Reference**
JioAICloud Greetings & Creation



**Phase 1 -- All 7 Archetypes + Layout Reference**

JioAICloud Greetings & Creation

**Document Index**


**SCOPE**


**▪  Scope & Caveats**


**ARCHETYPE OVERVIEW**


**▪  Phase 1 Template Archetypes**


**▪  All 7 Archetypes — At a Glance**


**B1 PHOTO BACKGROUND**


**▪  B1 Photo Background — BRD**

–  Step 1 — Template Selection
–  Step 2 — Overlay Treatment
–  Step 3 — Layout
–  Step 4 — Track (Photography Aesthetic)
–  Step 5 — Scene Elements
–  Step 6 — Mood
–  Step 7 — Intensity
–  Step 8 — Font & Text
–  B1 Prompt Output Format

**FRAME / OVERLAY / LAYOUT REFERENCE**


**▪  A. Frame Types — Step 2 (A1)**

–  F1 — Full Perimeter
–  F2 — Dual Band
–  F3 — Single Band
–  F4 — Corner Accents
–  F5 — Arch / Canopy

**▪  B. Overlay Types — Step 2 (B1 & D1)**

–  O1 — Full Dark Overlay
–  O2 — Gradient Top-Heavy
–  O3 — Gradient Bottom-Heavy
–  O4 — Vignette
–  O5 — Caption Bar

**▪  C. Text + Illustration Layouts — Step 3**

–  L1 — Text Top
–  L2 — Overlay / Text Center
–  L3 — Text Left
–  L4 — Text Right
–  L5 — Text Bottom

**SHARED DESIGN SYSTEMS**


**▪  D. Frame × Layout Compatibility Matrix**


**▪  Overview — Design System**

–  How This Pack Works

**▪  Step 4 — Curated Colour Palettes (per Track)**


**▪  Step 5 — Curated Font Pairings (per Track)**


**▪  Step 6 — Illustration & Image Library**


**▪  AI Prompt Generation**


**TRACK LIBRARY — PER-TRACK SPEC SHEETS**


**▪  Creator Customization Areas**


**▪  Track Library — Per-Track Spec Sheets**


**▪  Track A — Shiny Maximal ✨**

–  Detailed BRD — Track A
·  1. Colour System — Design Tokens
·  2. Typography System
·  3. Canvas & Layout BRD
·  4. Rendering Pipeline & Prompt Construction
·  5. Finish — Background Treatment
·  6. Illustration Rendering Sub-Styles
·  7. Motif Set — Indian Mass-Market Patterns
·  8. Customisation Presets
·  9. Frame Motif Selection
·  10. Reference / Moodboard

**▪  Track B — Modern Desi 🎨**

–  Detailed BRD — Track B

**▪  Track C — Minimalist Classy 🎬**

–  Detailed BRD — Track C

**▪  Track D — Artsy Playful 🎉**

–  Detailed BRD — Track D

**▪  Track E — Soft & Warm 🌷**

–  Detailed BRD — Track E

**▪  Future Enhancements — Track A (Parked)**


**Scope & Caveats**

This section outlines what the current document and prototype cover, and what is explicitly out of scope or pending further iteration. Please review before deep-diving into the spec.

**✅ What IS in the Current Document / Prototype**

1. Complete wizard flow for all 3 archetype families — A1 (Illustrated Background), A2 (Illustrated + Frame), and B1 (Photo Background) with step-by-step BRD for each, including all decision points, options, and UI behaviour.
2. 5 aesthetic tracks fully specced — Shiny Maximal, Modern Desi, Minimalist Classy, Artsy Playful, and Soft & Warm, each with colour palettes, font pools, illustration render styles, and photography aesthetics for B1.
3. Working prompt generator prototype (HTML) — Interactive v5 tool that walks through the full wizard, generates platform-specific prompts (Adobe Firefly With Text, Adobe Firefly No Text, Midjourney, Leonardo.AI, Google Gemini), and includes a QA audit table for every output.
4. Full illustration catalogue (49 items, 6 categories) — Common across all Good Morning archetypes, with photorealistic B1 descriptions mapped for each item.
5. Layout × Overlay compatibility system — 6 layouts × 5 overlays with Best / Works / With Care badges, plus frame decoration levels (A2) and intensity-driven density control.

**⚠️ What is NOT in the Current Document / Prototype (Pending Items)**

1. Text rendering & typography on posters (P1) — AI image generators don’t reliably render text. For Phase 1, text overlay will be handled manually / via a compositing layer post-generation. Not solved in prompt spec.
2. Multiple illustrations for A1 (P1 fix) — A2 now supports curated sub-illustrations (pick main → select 0–2 accent props from curated list, density auto-calculated). A1 still supports single illustration only. Multi-select needs extending to A1 in future.
3. Colour palette expansion & additional illustrations (P0 fix) — Current 6 palettes per track and 49 illustration items are a starting set. Both need expansion based on user testing feedback and designer input. This is a priority-zero fix before launch.
4. Prompt refinement (ongoing) — Prompt templates are functional but need further tuning through real image generation testing across Midjourney, Leonardo, and Firefly. Expect iterative prompt engineering as we test at scale.
5. Advanced customisation layers (future complexity) — Additional controls like custom colour input, user-uploaded illustrations, regional/festival-specific presets, and finer prompt tweaking to expand poster variety and creative depth.
6. Remaining archetypes (C1–D2) — C1 (Typographic), C2 (Minimal Quote), D1 (Collage), and D2 (Abstract Art) are defined at archetype level but do not yet have detailed prompt generator step BRDs or prototype implementations.
7. End-to-end automation pipeline — The current prototype generates prompts for manual copy-paste into AI platforms. API-based generation, automatic compositing (text + image), and batch production workflows are not yet built.

**8. Ability to use existing Adobe stock images as background**


# Phase 1 Template Archetypes


**Code**


**Name**


**Defining Characteristic**


**Custom Step 1**


**A1**


**Text + Frame**

A border/frame element is the defining visual. Text and optional illustration sit inside.
F1-F5 Frame Type

**A2**


**Text + Illustrations**

Illustrations are the primary visual. No dominant frame.
Illustration Weight

**B1**


**Full Photo Background**

A photograph fills the entire background. Text overlaid.
O1-O5 Overlay Type

**C1**


**Animated Elements**

On-canvas elements animate (particles, loops, reveals).
Animation Style

**C2**


**Animated Text**

The text itself animates. Background is minimal.
Text Animation Style

**D1**


**Video Background**

A looping video clip forms the background. Text overlaid.
Video Category (4 types)

**E1**


**AI Avatar**

An AI-generated human figure is the primary visual.
Rendering Style (Realistic/Illustrated)

**A1 -- Text + Frame**

A visible frame is the defining device. Text is primary; illustration is optional.

**TERMINOLOGY NOTE [NEW] -- 3 separate asset types in A1:**

(1) BACKGROUND = solid colour or gradient fill behind the whole canvas. No AI generation needed.
(2) FRAME ELEMENTS = the decorative motifs on the border frame itself (florals, paisleys, mandalas). Set via Frame Decoration Level in Step 5.
(3) ILLUSTRATION = the standalone flat 2D asset placed inside the canvas (chai cup, lotus, sunshine, bird etc.). Chosen from the illustration library in Step 5 and generated as a separate AI image.  These are three distinct things -- combine them in a single prompt only when generating the background + frame together. Never render text in any AI-generated asset.

**Step**


**Name**


**Options**


**Notes / Eliminations**


**1**


**Frame Type**

Custom Step

**F1 -- Full Perimeter  Border on all 4 edges. Eliminates edge bleed for all layouts.**


**F2 -- Dual Band  Straight horizontal bands at top + bottom. L1/L5 edge space reduced.**


**F3 -- Single Band  One edge only. Most permissive frame.**


**F4 -- Corner Accents  Patches at corners only. Maximum layout flexibility.**


**F5 -- Arch / Canopy  Curved arch shape overhead. L1 (Text Top) constrained. L5 pairs best**

Frame choice filters layouts in Step 2. See Compatibility Matrix in Layout Reference.

**2**


**Layout**


**L1 -- Text Top  Text fills Header + Upper rows. Illustration in Centre + Lower + Footer rows.**


**L2 -- Overlay  Illustration fills entire canvas. Text sits in Centre row with contrast treatment.**


**L3 -- Text Left  Left column = text (all rows). Centre + Right columns = illustration.**


**L4 -- Text Right  Right column = text (all rows). Left + Centre columns = illustration.**


**L5 -- Text Bottom  Illustration fills Header + Upper + Centre rows. Text in Lower + Footer rows.**

L6 -- Text Centre: Frame defines all 4 edges. Background/gradient fills canvas. Small illustration anchored at top or bottom inside frame. Text occupies the central zone. Best with F1, F2, F4. Not recommended with F5 (arch restricts centre zone).
Options shown are filtered by frame choice from Step 1. L6 added: for text-centre compositions where frame holds all edges and illustration is a small accent only.

**3**


**Track**

A — Shiny Maximal  3D extruded sticker, glossy shimmer, clustered ornate motifs, gold + saturated palette. Tier 2–3, 35+.
B — Modern Desi  Anokhi-meets-Insta. Two sub-modes: B1 Painterly (watercolor + linework + block-print) and B2 Lifestyle Photo (golden-hour home). Urban, 25–40.
C — Cinematic  Magazine / film-poster. Real photography, low-key dramatic light, editorial type, geometric or metallic motifs only (no florals). Premium, 28–45.
D — Playful Illustrated  Cartoon sticker-pack energy. Flat vector / sticker outline / doodle / 3D cartoon. 18–30, gen-Z. Hard-blocked for Devotional / Political / Sympathy.
Hard fork. Locks palette, font, illustration render, frame motif, background sub-style, and density for ALL downstream steps. Subject library stays universal per vertical; Track locks treatment. Disallowed combinations are filtered out of the downstream UI silently.

**4**


**Colour**


**Background Colour  From theme palette -- solid or gradient**


**Text Colour  Contrast pair for the chosen background**


**Frame / Accent Colour  Sets the colour of the frame element (regardless of whether it is plain or ornate)**

Select BG + text as a pair. Minimum 4.5:1 contrast ratio for text legibility.

**5**


**Font**


**Serif  Traditional, formal, devotional**


**Sans-Serif  Modern, clean, motivational**


**Script / Calligraphic  Romantic, festive, expressive**


**Display / Decorative  Bold, festive, high-impact**

One primary font. Weight (Regular/Bold/Black) chosen per line hierarchy.

**6**


**Illustration**


**Choose from category pack  e.g. Devotional: deities, diyas, lotus, rangoli**

Frame Decoration Level [UPDATED]  Controls how ornate the frame border itself is (separate from the illustration inside the frame)
Plain:  Clean border lines only. No motifs. Modern, minimal. Prompt: "simple clean border frame, no motifs, no ornamentation"
Simple:  Minimal motifs at corners or midpoints only (1-2 motif types). Prompt: "delicate corner motifs only, restrained border decoration"
Detailed:  Full ornate frame -- florals, paisleys, mandalas throughout border. Traditional, festive. Use only when ornamentation IS the statement.
Default recommendation: Simple. Use Detailed only for traditional/devotional themes. Use Plain for modern/motivational themes.

**Density: Minimal  1-2 hero elements**


**Density: Moderate  3-5 elements**


**Density: None  Text-only template (frame only, no illustration)**


**Illustration Size [NEW]  How much canvas the illustration occupies. Separate from Density (count).**


**Small Accent:  <15% canvas. Decorative accent, not dominant. Text is the star.**


**Medium:  30-40% canvas. Balanced visual weight. Text and illustration share space.**

Large / Hero:  50%+ canvas. Illustration is the dominant visual. Use only with L1, L5 or L3/L4 (text pushed to edge zone).
Illustration placed in the zone defined by layout.
THREE DISTINCT ASSET CONTROLS [NEW]:  (1) Frame Decoration Level = motifs on the frame border itself. (2) Illustration = the flat 2D asset inside the canvas (chai cup, lotus, sunshine etc.). (3) Background = solid/gradient fill behind everything. These are three separate things -- never merge them in prompts.

**7**


**Mood Check**


**Does it feel right for the theme?**


**Is the text clearly readable?**


**Is the frame balanced with the illustration?**


**Would a Bharat user share this?**

Qualitative pass. Revisit the failing step.

**A2 -- Text + Illustrations**

Illustrations are the primary visual. No dominant frame.

**Step**


**Name**


**Options**


**Notes / Eliminations**


**1**


**Layout [Density step removed — auto-calculated]**

Custom Step

**Light -- 1-2 hero elements  Single focal illustration. Clean background.**


**Medium -- 3-5 elements  Balanced composition. Main + supporting accents.**


**Dense -- 6+ / Pattern  Rich texture, border-like. Illustration IS the background.**

[UPDATE v5.1] Illustration density step has been removed from A2. Density is now auto-calculated from the number of accent sub-illustrations selected: 0 items = Light (lots of breathing space), 1 item = Medium (balanced), 2 items = Dense (rich vibrant scene). User picks 1 main illustration, then optionally selects 0–2 curated accent props from a per-item curated list. Accent items use illusDesc (illustrated descriptions) from the shared ACCENT_ITEMS library.

**2**


**Layout**


**L1 -- Text Top  Text fills Header + Upper rows. Illustration in Centre + Lower + Footer rows.**


**L2 -- Overlay  Illustration fills entire canvas. Text sits in Centre row with contrast treatment.**


**L3 -- Text Left  Left column = text (all rows). Centre + Right columns = illustration.**


**L4 -- Text Right  Right column = text (all rows). Left + Centre columns = illustration.**


**L5 -- Text Bottom  Illustration fills Header + Upper + Centre rows. Text in Lower + Footer rows.**

No frame to filter -- all 5 layouts fully available. Dense weight pairs best with L2.

**3**


**Track**


**A -- Shiny Maximal  Gold/jewel palette, ornamental motifs, festive maximalism**


**B -- Modern Desi  Muted Indian palette, clean geometry, editorial restraint**


**C -- Cinematic  Photoreal/filmic, deep contrast, moody lighting**


**D -- Playful Illustrated  Bright flat palette, hand-drawn character, playful energy**

Hard fork. Locks palette, font, illustration render, frame motif, background sub-style for the remaining steps. One selection per template.

**4**


**Colour**


**Background Colour  Sets tone for the whole template**


**Text Colour  Contrast pair for the chosen background**


**Illustration Colour Mode  Full colour / Duotone / Monochrome**

Background and illustration colours should feel cohesive, not competing.

**5**


**Font**


**Serif  Traditional, formal**


**Sans-Serif  Clean, modern**


**Script  Festive, expressive**


**Display  High-impact**

One primary font. Match font character to illustration style.

**6**


**Illustration Pack**


**Choose pack from category library  e.g. Good Morning: sunshine, birds, cups, flowers**


**Specify element count  Based on weight chosen in Step 1**


**Specify placement zone  Auto-derived from layout choice**

Scatter/floating element style is an illustration placement choice, not a layout choice.

**7**


**Mood Check**


**Is the illustration the visual star?**


**Is text legible over/beside the illustration?**


**Does density feel right -- not too sparse, not too cluttered?**


**Would a Bharat user share this?**

Qualitative pass. Revisit failing step.

**B1 Photo Background — Prompt Generator Steps (v5 Revamp)**

The B1 Photo Background template generates photorealistic photography prompts (not illustrations). The wizard flow is fundamentally different from A1/A2. Below is the complete 8-step wizard specification as implemented in the Prompt Generator v5.

**Step 1 — Template Selection**

User selects B1 (Photo Background). This locks the entire flow into the photorealistic photography pipeline. No frames, no illustration render styles, no background finishes, no motifs.

**Step 2 — Text Placement & Overlay (Merged Step)**

Overlay + Layout are now merged into a single step. The user selects a text position (L1–L6), and the overlay direction is auto-determined from the text position (e.g., Text Top → darker overlay at top). The only additional choice is overlay strength: Light (subtle semi-transparent) or Darker (heavy opaque). This eliminates one wizard step while giving more intelligent overlay control.

**O1 — Full Dark: Uniform dark overlay across entire image. Maximum text contrast.**


**O2 — Gradient Top Heavy: Darker toward top, brighter at bottom. Best for text at top (L1).**


**O3 — Gradient Bottom Heavy: Darker toward bottom, brighter at top. Best for text at bottom (L5).**


**O4 — Vignette: Centre bright and vivid, edges darkened. Best for centred text (L2).**


**O5 — Caption Bar: Lower strip naturally darker. Text sits in a defined bar at bottom.**


**Step 3 — Layout (Text & Visual Arrangement)**

Same 6 layouts (L1–L6). For B1, layout cards show compatibility badges (Best / Works / With Care) based on overlay selection. Defines where the text overlay sits on the photograph.

**Step 4 — Track (Photography Aesthetic)**

Track names stay the same (Shiny Maximal, Modern Desi, etc.) but each card shows a blue callout explaining what the track means for photography:
Track A — Shiny Maximal → HDR Saturated: Viral WhatsApp-forward energy. HDR punch, oversaturated, dramatic.
Track B — Modern Desi → Editorial Muted: Kodak Portra film look. Muted earthy tones, editorial restraint.
Track C — Minimalist Classy → Desaturated Minimal: High contrast, low saturation. Architectural, clean lines.
Track D — Artsy Playful → Bright Lifestyle: Poppy blog photography. Bright, airy, slightly overexposed.
Track E — Soft & Warm → Soft Dreamy: Pastel bokeh, soft focus edges. Romantic, gentle warmth.

**Step 5 — Scene Elements (Multi-Select 1–3)**

Redesigned: User picks 1 main element from the illustration catalogue. The system then shows 2–4 curated accent props (from 30-item ACCENT_ITEMS library) specific to that main element. User optionally selects 0–2 accent items. Accent items are small scene-setting props (biscuits with tea, newspaper, dew drops, scattered petals) — not competing hero illustrations. Each accent item has a photorealistic description (photoDesc) tailored for B1 photography prompts.

**Selection Order Matters:**

First selected = Main subject (hero, foreground, focal point, larger in frame)
Second/third selected = Supporting elements (background, mid-ground, smaller, contextual)
The UI shows a chip strip above the grid: ⭐ Main vs ○ Supporting with remove buttons. Each card in the grid shows its assigned role. Prompts explicitly phrase “as the main subject in the foreground” for element 1 and “as supporting elements in the background” for elements 2–3.
Each illustration item has a B1_PHOTO_DESC lookup providing a photorealistic description (e.g. “Steaming Chai Cup” → “a steaming ceramic cup of chai with visible steam rising”).

**Step 6 — Mood (Merged Lighting + Colour Treatment)**

Previously two separate steps (Mood/Lighting + Colour Grading), now merged into one to reduce decision fatigue. Each option bundles both the physical lighting and the colour processing:

**MD-1 — Golden Warm: Sunrise glow + warm amber tones. Classic Good Morning energy.**


**MD-2 — Misty Soft: Morning fog + muted natural tones. Dreamy, ethereal, calm.**


**MD-3 — Bright & Vivid: Clear daylight + saturated punchy colours. Crisp, sharp.**


**MD-4 — Dramatic Rays: God rays through clouds/trees + high contrast. Theatrical.**


**MD-5 — Vintage Film: Soft diffused light + faded film look. Nostalgic, analog.**


**MD-6 — Soft Pastel: Overcast gentle light + desaturated pastels. Calm, airy.**

Track-specific suggestions are shown with ⭐ Best badges (e.g. Soft & Warm track suggests Soft Pastel or Golden Warm).

**Step 7 — Intensity (Camera Distance & Detail)**

Unlike A1/A2 where intensity controls decoration density, in B1 intensity controls camera distance and detail level:
Basic — Wide & Airy: Wide-angle, distant framing. Lots of sky/space. Scene elements small in frame. Environmental context dominates.

**Medium — Balanced: Standard focal length. Scene elements at comfortable scale. Good detail with environmental context.**

Complex — Close & Immersive: Tight framing, shallow depth of field. Scene elements fill the frame. Maximum detail density, bokeh blur.

**Step 8 — Font & Text**

Same as A1/A2. Typography style (4 options per track) and user message input. Text colour for B1 is always white (on the darkened overlay zone).

**Steps Removed for B1**

The following steps from A1/A2 are NOT shown when B1 is selected: Colour Palette (no background colour — the photo IS the background), Background Finish (no texture/gradient — it’s a photograph), Illustration Render Style (always photorealistic), Motif Patterns (no decorative motifs on photos), Illustration Size Picker (intensity controls camera distance instead), Frame Decoration Level (no frames on B1).

**B1 Prompt Output Format**

B1 prompts are fundamentally different from A1/A2. They generate photorealistic photography with: scene composition (main subject + supporting elements), merged mood (lighting + colour treatment), track photography aesthetic, camera framing from intensity, overlay treatment for text zones, and strong negative prompts blocking illustration/cartoon/vector/frame/border elements.
Platforms: Adobe Firefly With Text (≤950 chars, includes text rendering instruction), Adobe Firefly No Text (≤950 chars, explicit no-text guards), Midjourney (single paragraph, --ar 9:16 --s 250 --no flags), Leonardo.AI (structured sections, ≤1400 chars), Google Gemini (verbose descriptive sections, no character limit). B1 prompts include colour temperature per mood (Kelvin values), DSLR quality anchoring, natural depth of field, and overlay strength in prompt language.

**B1 -- Full Photo Background**

A photograph fills the entire background canvas. Overlay makes text readable.

**Step**


**Name**


**Options**


**Notes / Eliminations**


**1**


**Overlay Type**

Custom Step

**O1 -- Full Dark  Uniform overlay. Text anywhere.**


**O2 -- Gradient Top-Heavy  Text at top. Photo shines at bottom.**


**O3 -- Gradient Bottom-Heavy  Text at bottom. Photo shines at top.**


**O4 -- Vignette  Dark edges, bright centre. Portrait-friendly.**


**O5 -- Caption Bar  Solid bar (header or footer). Photo-first.**

Overlay choice strongly guides layout in Step 2. O2->L1, O3->L5, O4->L2, O5->L1 or L5.

**2**


**Layout**


**L1 -- Text Top  Text fills Header + Upper rows. Best with O2 (Gradient Top) or O5 (Caption Bar top).**


**L2 -- Overlay (primary)  Illustration fills canvas. Text in Centre. Default for O1 and O4.**


**L3 -- Text Left  Left column = text. Works with portrait photos + O1.**


**L4 -- Text Right  Right column = text. Mirror of L3.**


**L5 -- Text Bottom  Illustration fills top. Text in Lower + Footer. Best with O3 or O5.**

Layout is constrained by overlay choice. Incompatible combinations auto-filtered.

**3**


**Track**


**C -- Cinematic  Photoreal/filmic, deep contrast, moody lighting -- native fit for B1 photo archetype**


**B -- Modern Desi  Muted Indian palette, clean geometry -- editorial photo treatment**

A -- Shiny Maximal  Gold-tint grade, bokeh sparkle, ornamental corner motifs overlaid on photo. Cheesy/festive photo treatment.
D -- Playful Illustrated  Photo + hand-drawn sticker overlays (doodles, hearts, stars, playful frames). Jazzy/fun photo treatment.
All 4 tracks valid for B1. C and B are native photo fits. A and D layer ornamental/illustrated treatments onto the photo for cheesy or playful variants -- both proven WhatsApp winners.
Hard fork. Locks photo treatment style, text overlay palette, and frame motif for the remaining steps. All 4 tracks supported -- C/B keep the photo clean; A adds gold/bokeh/motif overlay; D adds sticker/doodle overlay.

**4**


**Colour**


**Text Colour only  Background IS the photo -- no BG colour needed**


**Overlay colour / opacity  Dark black vs warm sepia vs cool blue -- set per theme**

Use high-contrast text. White or cream over dark overlays. Dark over light caption bars.

**5**


**Font**


**Bold / Black weight recommended  Photo BG demands strong contrast**


**Serif  Warmth, tradition**


**Sans-Serif Bold  Clean, readable at all sizes**


**Display  High-impact headings**

Avoid thin/light font weights on photo backgrounds -- they disappear.

**6**


**Photo Source**


**Stock library -- category-filtered  e.g. Devotional: temple, deity, sunrise**


**User upload  Creator brings their own photo**


**AI-generated  Generate a scene matching theme + mood**

Photo must be safe for text placement -- avoid complex backgrounds in text zones.

**7**


**Mood Check**


**Is the text readable over the photo?**


**Does overlay feel natural for the theme?**


**Is the photo the hero -- not just a faded blur?**


**Would a Bharat user share this?**

Qualitative pass. Revisit failing step.

**C1 -- Animated Elements**

Static template with animated elements layered on top.

**Step**


**Name**


**Options**


**Notes / Eliminations**


**1**


**Animation Style**

Custom Step
Particle  Multiple small elements moving independently across the canvas (e.g., 20-50 petals drifting, snowflakes falling, confetti bouncing). Continuous, random-path motion. Canvas is always in motion.
Loop  A single larger element with a repeating animation cycle (e.g., a diya flame flickering, a sun rotating, a flower blooming and repeating). One focused motion element, not many.
Reveal  Elements animate IN on load (fade up, burst, slide in) then hold static. Canvas is still after the reveal completes. Good for "arrival" moments.
Animation style chosen here defines the element type available in Step 5.

**2**


**Layout**


**L1 -- Text Top**


**L2 -- Overlay**


**L3 -- Text Left**


**L4 -- Text Right**


**L5 -- Text Bottom**

All 5 layouts available. Animation layer sits above the illustration zone.

**3**


**Colour**


**Background Colour  Sets canvas tone**


**Text Colour  Contrast pair**


**Animation Element Colour  Can match BG or be accent colour**

Animation elements should complement, not overpower, the text.

**4**


**Font**


**Serif**


**Sans-Serif**


**Script**


**Display**

Animation adds energy -- font can be simpler.

**5**


**Animated Element Pack**


**Choose from category-specific animation library**


**Particle: Density -- Sparse / Medium / Dense**

Density = number of animated elements visible simultaneously. Sparse = 5-10 elements (airy, breathing room). Medium = 15-25 elements (balanced). Dense = 40+ elements (heavy -- snowstorm, full confetti burst).

**Loop: Count: 1-2 / 3-5 / Several +  Speed -- Slow / Medium / Fast**


**Reveal: Timing -- Instant / Staggered / Sequential**

Staggered = elements appear in waves with a small delay between groups (feels organic)
Sequential = each element appears one-by-one in a fixed order, e.g., left-to-right or largest-first (feels choreographed).
Elements placed in illustration zone defined by layout. Particles can span full canvas.

**6**


**Mood Check**


**Does the animation enhance or distract?**


**Is text readable while animation plays?**


**Does the motion fit the theme energy?**


**Would a Bharat user share this?**

Qualitative pass. Revisit failing step.

**C2 -- Animated Text**

The text itself is the animated element. Background is minimal.

**Step**


**Name**


**Options**


**Notes / Eliminations**


**1**


**Text Animation Style**

Custom Step

**Typewriter  Characters typed one by one. Monospace font works best.**


**Fade-In  Text fades in word by word or line by line. Universal.**


**Slide  Text slides in from bottom, top, or side. Clean, modern.**


**Bounce / Pop  Playful bounce on entry. Birthday, celebration.**


**Glow / Shimmer  Text shimmers or pulses. Devotional, festive.**

Animation style informs font recommendation in Step 4.

**2**


**Layout**


**L1 -- Text Top  Text fills Header + Upper rows. Text animates in upper zone.**


**L2 -- Overlay  Illustration fills canvas. Text animates over full background. Most dramatic.**


**L3 -- Text Left  Left column = text. Text animates in left zone.**


**L4 -- Text Right  Right column = text. Text animates in right zone.**


**L5 -- Text Bottom  Text fills Lower + Footer rows. Text animates in lower zone.**

Text-centric layouts work best. L2 recommended for maximum impact.

**3**


**Colour**


**Background Colour  Sets stage for text animation**


**Text Colour  Should pop clearly on BG**

High contrast is critical -- text is the entire visual message.

**4**


**Font**


**Monospace  Required for Typewriter style**


**Sans-Serif Medium/Bold  Best for Fade, Slide, Bounce**


**Script / Calligraphic  Best for Glow/Shimmer style**


**Display / Decorative  High-impact for Bounce/Pop**

Font must match animation style. Mismatched combos (e.g. script + typewriter) feel wrong.

**5**


**Background Element**


**Solid colour  Cleanest -- text is the entire story**


**Subtle pattern / texture  Low-opacity. Must not compete with text animation.**


**Static illustration  In illustration zone only -- text zone stays clear**

Background is intentionally minimal in C2 -- text is the star.

**6**


**Mood Check**


**Does the animation feel smooth and intentional?**


**Is the text the undisputed focal point?**


**Does animation speed feel right for the message sentiment?**


**Would a Bharat user share this?**

Qualitative pass. Revisit failing step.

**D1 -- Video Background**

A looping video clip forms the background. Text readability across all frames is key.

**Step**


**Name**


**Options**


**Notes / Eliminations**


**1**


**Video Category**

Custom Step

**Calm & Natural  River flow, forest breeze, sunrise/sunset, clouds, sky timelapse**


**Sacred & Devotional  Temple lamp, incense smoke, flower offerings, river ghats, bells**


**Celebratory  Confetti, fireworks, sparklers, balloon release**


**Abstract Motion  Bokeh, light rays, colour gradient morphs, particle fields**

Video choice must match the content theme. Mismatched video undermines the message.

**2**


**Layout**


**L2 -- Overlay (primary)  Video fills canvas, text in Centre. Most common.**


**L1 -- Text Top  Use with O2-style treatment (dark top, video visible bottom)**


**L5 -- Text Bottom  Use with O3-style treatment (dark bottom, video visible top)**

D1 strongly favours L2. L1/L5 require gradient overlay for text readability over motion.

**3**


**Colour**


**Text Colour only  Background IS the video**


**Overlay opacity level  Light (20-30%) / Medium (40-50%) / Heavy (60-70%)**


**Overlay tint  Neutral black / Warm sepia / Cool blue**

More motion = heavier overlay needed for text readability.

**4**


**Font**


**Bold / Black weight required  Motion BG demands heavy strokes**


**Sans-Serif Bold**


**Display / Slab Serif**


**Avoid Script/Thin  Disappear over motion**

Font readability is non-negotiable over video.

**5**


**Video Source**


**Curated stock loop library  Category-filtered, safe for text placement**


**User upload  Creator brings their own video clip**

Stock loops should be tested for text zone safety before inclusion in library.

**6**


**Mood Check**


**Is text readable during ALL frames of the video loop?**


**Does video movement feel right for the message -- calming or energising?**


**Is the overlay natural, not just a blurred photo?**


**Would a Bharat user share this?**

Must check across multiple frames of the loop, not just the first.

**E1 -- AI Avatar**

An AI-generated human figure is the primary visual. Personalisation is the key value.

**Step**


**Name**


**Options**


**Notes / Eliminations**


**1**


**Avatar Rendering Style**

Custom Step

**Realistic  Photorealistic face/figure. Formal, credible, news-adjacent.**


**Illustrated / Cartoon  Stylised character. Friendly, approachable, inclusive.**

Rendering style sets the visual register. Attire and cultural expression are customised in Step 5.

**2**


**Layout**


**L3 -- Text Left, Avatar Right  Avatar on right, text/message on left**


**L4 -- Text Right, Avatar Left  Avatar on left, text/message on right**


**L2 -- Overlay  Avatar full canvas / bust shot, text overlaid with contrast treatment**

E1 strongly favours L3/L4 to give avatar the visual weight it needs.

**3**


**Colour**


**Background Colour  Should complement avatar attire, not clash**


**Text Colour  Contrast pair with BG**

Background colour is critical with avatars -- defines whether avatar stands out or blends in.

**4**


**Font**


**Sans-Serif  Clean, modern -- pairs with all avatar styles**


**Serif  Formal, traditional -- pairs with Realistic avatar**


**Script  Use sparingly, only for short greetings with Illustrated avatar**

Font should feel like it belongs in the same visual world as the avatar style.

**5**


**Avatar Customisation**


**Rendering: Realistic or Illustrated  Confirmed from Step 1**


**Skin Tone  Range representing India's diversity**


**Outfit / Attire  Contemporary casual / Business formal / Traditional-Cultural (saree, kurta, sherwani, regional)**


**Expression  Neutral / Smiling / Namaste gesture / Celebratory**


**Accessories  Tilak, bindi, maang tikka, glasses -- optional.**

Avatar is the personalisation hook. More options = higher engagement.

**6**


**Mood Check**


**Does the avatar look credible and well-rendered?**


**Does the outfit match the content theme?**


**Is the avatar-to-text balance natural?**


**Would a Bharat user associate with this avatar?**

Avatar quality is the highest-stakes element here.

# All 7 Archetypes -- At a Glance


**Note: E1 Step 1 updated to Rendering Style (Realistic/Illustrated). D1 Step 1 updated to 4 MECE Video Categories**


**Step**


**A1**

Text + Frame

**A2**

Text + Illus

**B1**

Full Photo BG

**C1**

Animated Elems

**C2**

Animated Text

**D1**

Video BG

**E1**

AI Avatar

**1 Custom**

Frame Type (F1-F5)
Illus Weight (Light/Med/Dense)
Overlay Type (O1-O5)
Anim Style (Particle/Loop/Reveal)
Text Anim (Typewriter/Fade/etc)
Video Category (4 types)
Rendering Style (Realistic/Illustrated)

**2 Layout**

L1-L5 filtered by F
L1-L5 all available
L2 primary, L1/L5 with overlay
L1-L5 all available
L1-L5 text-centric
L2 primary
L3/L4 primary

**3 Colour**

BG + Text Colour Pair
BG + Text Colour Pair
BG + Text Colour Pair
BG + Text Colour Pair
BG + Text Colour Pair
BG + Text Colour Pair
BG + Text Colour Pair

**4 Font**

Font Family + Weight
Font Family + Weight
Font Family + Weight
Font Family + Weight
Font Family + Weight
Font Family + Weight
Font Family + Weight

**5 Asset**

Illus pack + Frame style
Illustration pack
Stock/Upload/AI photo
Animated element pack
Static BG element
Stock loop / Upload
Avatar customisation

**6 Mood**

Qualitative Mood Check
Qualitative Mood Check
Qualitative Mood Check
Qualitative Mood Check
Qualitative Mood Check
Qualitative Mood Check
Qualitative Mood Check

**Next: Devotion Pack Deep-Dive**

After Devotion: Motivational -> Good Morning/Night -> Festival -> Birthday -> Romantic/Shayari -> National/Patriotic

**Layout Reference**

Step 2 (Frame / Overlay) + Step 3 (Text & Illustration Layout) -- Reference for all archetypes
Canvas Zone Legend:
Frame
Text
Illus
Open
Arch
Fade
Overlay

# A. Frame Types -- Step 2 (A1 Templates)

Six MECE frame categories. Distinction is structural (which zones are occupied) -- not colour, thickness, or decorative style. Frame STYLE (plain vs ornate with motifs) is chosen in Step 5.

## F1 -- Full Perimeter


**Principle**

Frame runs along all 4 edges -- complete border enclosing the canvas.

**Zones Blocked**

Header, Footer, Left edge, Right edge.

**Text Rules**

Text stays inside inner content area. Cannot break frame boundary.

**Illus Rules**

Illustration confined to inner zone. No edge bleed.

**Eliminates**

L3/L4 side columns tightened. L1/L5 lose edge space. L2 works cleanest.

**Best For**

A1 -- formal, ornate, devotional/traditional festive

**CANVAS**

Frame
Frame
Frame
Frame
Open
Frame
Frame
Open
Frame
Frame
Open
Frame
Frame
Frame
Frame

## F2 -- Dual Band


**Principle**

Straight horizontal bands at header and footer only -- sides fully open.

**Zones Blocked**

Header row + Footer row.

**Text Rules**

Text in Upper/Centre/Lower rows only. Cannot overlap bands.

**Illus Rules**

Centre rows fully available. Full horizontal width.

**Eliminates**

L1 loses top illustration space. L5 loses footer anchor.

**Best For**

A1 -- magazine-style, banner cards, clean structured

**CANVAS**

Band
Band
Band
Open
Open
Open
Open
Open
Open
Open
Open
Open
Band
Band
Band

## F3 -- Single Band


**Principle**

One edge only -- footer band or header bar (not both).

**Zones Blocked**

Header OR Footer row only.

**Text Rules**

One end anchored; rest of canvas fully open.

**Illus Rules**

Maximum freedom -- 4 of 5 rows fully available.

**Eliminates**

Minimal -- all 5 layouts compatible.

**Best For**

A1 -- understated, minimal, modern

**CANVAS**

Open
Open
Open
Open
Open
Open
Open
Open
Open
Open
Open
Open
Band
Band
Band

## F4 -- Corner Accents


**Principle**

Small decorative patches at corners only.

**Zones Blocked**

Corner patches only (4 corners).

**Text Rules**

Text anywhere. Avoid placing primary text over corner patch.

**Illus Rules**

All zones fully open.

**Eliminates**

Nothing -- all 5 layouts fully compatible.

**Best For**

A1/A2 -- elegant, versatile; pairs with every layout

**CANVAS**

Corner
Open
Corner
Open
Open
Open
Open
Open
Open
Open
Open
Open
Corner
Open
Corner

## F5 -- Arch / Canopy


**Principle**

Curved arch overhead -- occupies header zone and upper side patches.

**Zones Blocked**

Header row + partial Upper-Left and Upper-Right.

**Text Rules**

Primary text at Upper-Centre or Centre row. Avoid Header for text.

**Illus Rules**

Illustration in Lower/Footer. Side columns open from Centre down.

**Eliminates**

L1 (Text Top) constrained -- arch is at header. L5 pairs perfectly.

**Best For**

A1 -- devotional, ceremonial (deity arch, lotus canopy, Diwali torans)

**CANVAS**

Arch
Arch
Arch
Arch
Open
Arch
Open
Open
Open
Open
Open
Open
Open
Open
Open

# B. Overlay Types -- Step 2 (B1 & D1 Templates)

Five overlay patterns for Full Photo (B1) and Video (D1) backgrounds. Defines how the photo/video is treated so text remains readable.

## O1 -- Full Dark Overlay


**Description**

Uniform semi-opaque dark layer across entire canvas (~40-60% opacity).

**Text Placement**

Text anywhere -- uniform contrast across full canvas.

**Best For**

Night/moon themes, serious tone. Works with L2.

**CANVAS**

Dark
Dark
Dark
Dark
Dark
Dark
Dark
Text
Dark
Dark
Dark
Dark
Dark
Dark
Dark

## O2 -- Gradient Top-Heavy


**Description**

Dark gradient from top, fades to transparent by centre. Photo visible in lower half.

**Text Placement**

Text at Header + Upper. Lower section shows photo.

**Best For**

Sky/sunrise photos, morning themes. Pairs with L1.

**CANVAS**

Dark
Dark
Dark
Dark
Text
Dark
Fade
Fade
Fade
Photo
Photo
Photo
Photo
Photo
Photo

## O3 -- Gradient Bottom-Heavy


**Description**

Dark gradient from footer, fades to transparent near centre. Photo clear in upper half.

**Text Placement**

Text at Lower + Footer. Upper shows photo.

**Best For**

Quote cards, shayari, evening themes. Pairs with L5.

**CANVAS**

Photo
Photo
Photo
Photo
Photo
Photo
Fade
Fade
Fade
Dark
Text
Dark
Dark
Dark
Dark

## O4 -- Vignette


**Description**

Darkened edges, bright centre window. Photo visible in middle.

**Text Placement**

Text in Centre row -- natural focal point.

**Best For**

Portrait photos, romantic themes. Pairs with L2.

**CANVAS**

Dark
Fade
Dark
Fade
Photo
Fade
Fade
Text
Fade
Fade
Photo
Fade
Dark
Fade
Dark

## O5 -- Caption Bar


**Description**

Semi-opaque solid bar at header or footer. Rest of canvas is full photo.

**Text Placement**

Text sits inside caption bar. Photo visible above or below.

**Best For**

Photo-first, minimal text. Works with L1 or L5.

**CANVAS**

Photo
Photo
Photo
Photo
Photo
Photo
Photo
Photo
Photo
Photo
Photo
Photo
Bar
Text
Bar

# C. Text + Illustration Layouts -- Step 3

Five positional layouts. These define WHERE text lives and WHERE illustration lives. Stylistic choices (density, opacity, scatter) are in Step 5.

## L1 -- Text Top


**Description**

Text anchored in upper portion. Illustration fills lower two-thirds.

**Text Zone**

Header + Upper rows

**Illus Zone**

Centre + Lower + Footer rows

**Constraint**

F5 (Arch) conflicts with header text -- shift to Upper row when F5 selected.

**Frame Compat**

F0 F3 F4 fully. F2 F1 F5 partially.

**CANVAS**

Text
Text
Text
Text
Text
Text
Illus
Illus
Illus
Illus
Illus
Illus
Illus
Illus
Illus

## L2 – Overlay / Text Center


**Description**

Illustration fills entire canvas. Text sits in the centre with contrast treatment.

**Text Zone**

Centre row (primary). Upper or Lower as secondary.

**Illus Zone**

All 5 rows -- full canvas bleed.

**Constraint**

Text must have sufficient contrast. Use bold font or local opacity bar.

**Frame Compat**

All frames -- universally compatible. Primary for B1 and D1.

**CANVAS**

Illus
Illus
Illus
Illus
Illus
Illus
Illus
Text
Illus
Illus
Illus
Illus
Illus
Illus
Illus

## L3 -- Text Left


**Description**

Left column holds text. Right two columns hold illustration.

**Text Zone**

Left column across all rows.

**Illus Zone**

Centre + Right columns across all rows.

**Constraint**

F1 tightens left column. F4 works perfectly.

**Frame Compat**

F0 F2 F3 F4 F5 fully. F1 partially.

**CANVAS**

Text
Illus
Illus
Text
Illus
Illus
Text
Illus
Illus
Text
Illus
Illus
Text
Illus
Illus

## L4 -- Text Right


**Description**

Right column holds text. Left two columns hold illustration.

**Text Zone**

Right column across all rows.

**Illus Zone**

Left + Centre columns across all rows.

**Constraint**

Mirror of L3. Same frame constraints apply.

**Frame Compat**

F0 F2 F3 F4 F5 fully. F1 partially.

**CANVAS**

Illus
Illus
Text
Illus
Illus
Text
Illus
Illus
Text
Illus
Illus
Text
Illus
Illus
Text

## L5 -- Text Bottom


**Description**

Illustration fills upper two-thirds. Text anchored at lower portion.

**Text Zone**

Lower + Footer rows.

**Illus Zone**

Header + Upper + Centre rows.

**Constraint**

F5 (Arch) enhances this layout -- arch top + text bottom = ceremonial frame. F2 reduces footer space.

**Frame Compat**

F0 F3 F4 F5 fully. F1 F2 partially.

**CANVAS**

Illus
Illus
Illus
Illus
Illus
Illus
Illus
Illus
Illus
Text
Text
Text
Text
Text
Text

# D. Frame x Layout Compatibility Matrix

Quick-filter: use in Step 3 to determine which layouts are available given the frame type chosen in Step 2.

**Frame**


**L1 Text Top**


**L2 Overlay/Center**


**L3 Text Left**


**L4 Text Right**


**L5 Text Bottom**


**Notes**


**F1 Full Perimeter**

~
checkmark
~
~
~
All layouts pushed inward. L2 cleanest.

**F2 Dual Band**

~
checkmark
checkmark
checkmark
~
Bands block top+bottom. L1/L5 lose edge space.

**F3 Single Band**

checkmark
checkmark
checkmark
checkmark
checkmark
Single band minimal -- all 5 work.

**F4 Corner Accents**

checkmark
checkmark
checkmark
checkmark
checkmark
Corners never block major zones.

**F5 Arch/Canopy**

~
checkmark
checkmark
checkmark
checkmark
Arch in header blocks L1. L5 pairs best.
checkmark = Fully compatible   ~ = Partially compatible (minor adjustment needed)

**Good Morning**

Vertical Content Pack  |  JioAICloud Greetings & Creation

**Overview**

Good Morning is one of the highest-volume greeting categories in India -- millions of WhatsApp forwards daily. The JioAICloud Good Morning pack curates a specific set of colour palettes, font pairings, illustration libraries, and AI prompt formulas that match the visual and emotional signature of this category.
The pack does NOT redefine the 7-step creation flow. It sits on top of the framework and pre-populates Steps 4, 5, and 6 with vertical-appropriate options, filtered by the user's Track choice at Step 3. A user can generate a complete Good Morning poster by selecting defaults alone -- no custom prompt required.

**How This Pack Works**


**Step Group**


**What it covers**


**Source**


**Steps 1 + 2**

Archetype-specific. Already defined in the main framework. Step 1 (custom choice) directly constrains Step 2 (layout options). These do NOT change per vertical.
Framework

**Step 3**

Track (hard fork). User picks ONE of A Shiny Maximal / B Modern Desi / C Cinematic / D Playful Illustrated / E Soft & Warm. The chosen Track filters every Good Morning palette, font pairing, and illustration sub-category shown in Steps 4-6. Cringe Ceiling enforced -- incompatible combinations hidden from UI.
Framework

**Steps 4 + 5 + 6**

Vertical-curated. The Good Morning Pack provides pre-approved colour palettes, font pairings, and illustration categories that match the Good Morning vibe across ALL archetypes, filtered by the Track chosen at Step 3.
This Pack

**Step 7**

Mood check. Universal. Run at the end regardless of archetype or vertical.
Universal

**Step 4  --  Curated Colour Palettes (per Track)**

Six palettes curated specifically for Good Morning. Each palette is named and coded (GM-C1 through GM-C6) for easy reference in prompt generation. All palettes pass WCAG contrast minimum for overlay text readability.
Track variants within each palette -- bold shifts, not subtle.  Each GM palette family (GM-C1..C6) keeps its identity -- GM-C1 always reads as "warm sunrise" regardless of Track -- but the Track rewrites the whole background treatment: specific hex, saturation, brightness, fill style (gradient vs. flat), finish (matte vs. metallic). A user seeing GM-C1-A next to GM-C1-C should register them as visibly different worlds that happen to share a lineage, not as minor tweaks. Concrete shifts for GM-C1 Golden Hour below; same logic applies to GM-C2..C6.
A  Shiny Maximal (jazzy desi):  Neon marigold dominant #FF8C1A (not amber), electric saffron accent #FF6B00, hot gold highlight #FFD700, deep maroon punch #8B0000. 3 NEW exclusive palettes: Hot Pink Festive #EC4899, Royal Purple #7C3AED, Peacock Teal #0891B2. Background finish options: Plain Solid, Radial Gradient, Sparkle/Glitter, Metallic Foil, Bokeh Glow. Think: Punjabi wedding invite, Diwali card on overdrive, Bollywood poster. Loud on purpose.
B  Modern Desi (muted earthy):  Dusty terracotta dominant #C2410C, ochre accent #B45309, cream highlight #FEF3C7, sage grounding #84A98C. Background is flat matte with subtle paper-grain or gouache texture; no gradients, no metallic finishes. Think: contemporary editorial, Scroll.in morning feature, Kulture Shop print. Restrained on purpose.
C  Cinematic (classy muted):  Soft pale yellow dominant #FDE68A (not amber, not neon -- the restrained "morning light" yellow), deep navy shadow #1E3A5F for contrast, warm off-white highlight #FEFCE8, teal grading accent #0E7490. Background is a delicate gradient wash with fine film grain; no saturation, no ornaments. Think: film still, Kodak Portra 400, Wes Anderson pastel, luxury hotel print. Understated on purpose.
D  Playful Illustrated (flat bright):  Bright sunny yellow dominant #FACC15, coral pink accent #FB7185 (breaks the warm monotone), mint surprise #A7F3D0, sky blue pop #38BDF8. Background is flat solid colour-blocks with thick outlines, no gradients, no texture -- like a sticker sheet. Think: WhatsApp emoji palette, kids’ picture book, Bhavesh Bhatia-style doodle. Cheerful on purpose.
E  Soft & Warm (gentle pastels):  Warm cream dominant #FFF3E0, soft peach accent #FFAB91, blush pink #FFF0F0, gentle lavender #F3E5F5, soft mint #E0F2F1. Background finishes: Watercolour Wash, Plain Pastel, Soft Warm Gradient. Illustration renders: Watercolour Botanical, Tonal Silhouette, Soft Pastel Flat. Think: hand-painted greeting card, soft botanical art, calming morning energy. Gentle on purpose.
Quick visual diff for GM-C1: A is neon-marigold festive foil, B is dusty-terracotta matte paper, C is pale-yellow film wash, D is sunny-yellow sticker flat, E is warm-cream soft botanical. Five visibly different worlds under one "Golden Hour" family. The hex table below shows the GM-C1 base -- full 5-column per-Track hex ladder (GM-C1-A, GM-C1-B, GM-C1-C, GM-C1-D, GM-C1-E) maintained in the design system repo. Same per-Track logic applies to GM-C2 (Rose Dawn), GM-C3 (Pastel Sky), GM-C4 (Royal), GM-C5 (Devotional), GM-C6 (Minimal White) -- see Track Library at end of document for complete mapping.

**ID**


**Palette Name**


**BG**


**Text**


**Accent**


**Best For / Vibe**


**GM-C1**


**Sunrise Gold**

#F59E0B
#7C2D12
#F97316
Warm, energetic, celebratory. Best for festive Good Morning.

**GM-C2**


**Soft Dawn**

#FDE8D8
#78350F
#FCA5A5
Gentle, personal, warm. Best for family/relationship messages.

**GM-C3**


**Morning Sky**

#BFDBFE
#1E3A5F
#FFFFFF
Fresh, calm, uplifting. Best for motivational/nature themes.

**GM-C4**


**Fresh Garden**

#D1FAE5
#064E3B
#FEF08A
Natural, peaceful, earthy. Best for wellness/nature imagery.

**GM-C5**


**Sacred Saffron**

#FEF3C7
#7F1D1D
#D97706
Devotional, traditional. Best for spiritual Good Morning.

**GM-C6**


**Minimal White**

#F9FAFB
#1F2937
#F87171
Clean, modern, versatile. Works across all archetypes.

**Step 5  --  Curated Font Pairings (per Track)**

Four font pairings covering the full emotional range of Good Morning content. Each pairing specifies a heading font (for the main greeting) and a body font (for sub-text or quote). All fonts are available on Google Fonts and Adobe Fonts.
Track-specific font pools.  The four pairings above are the universal base. Each Track narrows/expands the pool so the typography feels native to the fork rather than generic:
A  Shiny Maximal:  jazzier pool -- ornamental display (Cinzel Decorative, Samarkan, Ranchers, Alfa Slab One, Yatra One, Rozha One), script (Great Vibes, Allura, Sacramento, Parisienne), bold sans body (Montserrat Black, Poppins Bold, Mukta Bold). Drop-shadows, gold-fill, metallic gradient, emboss treatments allowed. Think: wedding card meets Bollywood poster.
B  Modern Desi:  contemporary editorial pool -- geometric sans (Gilroy, Inter, DM Sans), modern serifs (Fraunces, Playfair Display), clean Devanagari (Tiro Devanagari, Mukta). No scripts, no drop-shadows. Think: Kulture Shop / Scroll.in type aesthetic.
C  Cinematic:  restrained title-card pool -- high-contrast serifs (Bodoni, Canela, Didot), condensed sans (Oswald, Bebas Neue) for captions. Sparing use, letter-spacing emphasised, always single-weight per composition. Think: film credits / Netflix poster.
D  Playful Illustrated:  hand-drawn + rounded pool -- marker/crayon display (Caveat, Kalam, Patrick Hand, Shadows Into Light), rounded sans (Fredoka, Baloo 2). Slight rotation/wobble allowed. Think: sticker pack / kids' book.
The 4 base pairings in the table below map into these Track pools -- GM-F1/F2/F3/F4 each have a Track-specific font substitution. Pool discipline is what keeps the fork visually consistent across hundreds of generated templates.

**ID**


**Pairing Name**


**Heading Font**


**Body Font**


**Feel**


**Best Palette Combos**


**GM-F1**


**Warm Script**

Kalam / Dancing Script
Nunito / Poppins Light
Personal, warm, handwritten
GM-C1, GM-C2, GM-C5

**GM-F2**


**Bold Display**

Poppins 700 / Playfair Bold
Poppins Regular
Energetic, confident, impactful
GM-C1, GM-C3, GM-C6

**GM-F3**


**Clean Modern**

Poppins SemiBold
Poppins Regular
Contemporary, clean, versatile
All palettes

**GM-F4**


**Elegant Serif**

Libre Baskerville / Lora Bold
Source Serif / Lora
Traditional, sophisticated, literary
GM-C4, GM-C5

**Step 6  --  Illustration & Image Library (per Track)**

Five illustration sub-categories curated for Good Morning. Each sub-category maps to specific archetypes where it works best. The illustration library is the input that populates the VISUAL_SUBJECT variable in the AI prompt formula.
Illustration treatment per Track -- same subject, rendered four different ways.  A subject like "chai cup + marigold" below is rendered in radically different illustration techniques depending on the Track. The illustration library holds the subject; the Track locks how it's drawn (medium, texture, line quality, composition discipline):
A  Shiny Maximal:  3 sub-styles: IR-1 Ornamental Vector (gold-foil, paisley/mandala borders, symmetric, stamped-metal), IR-2 Colourful Vector (vivid flat colours, bold outlines, no gold, poster style), IR-3 3D Glossy (raised embossed, candy sheen, dimensional). NEW: 10 motif sets (Paisley, Mandala, Marigold Chain, Lotus, Peacock, Diya, Rangoli, Temple Arch, Mehndi, Bel Patta). Customisation presets: Basic/Medium/Complex auto-set density, gold, sparkle, metallic finish. Reference: wedding invitations, Diwali cards, Madhubani, Bollywood posters, truck art, Tanjore painting, zardozi, Kalamkari.
B  Modern Desi:  Loose editorial watercolour or gouache; visible brushstrokes, bleeding edges, paper texture underneath; asymmetric composition with deliberate negative space. No outlines. Reference: Scroll.in illustrated features, The Hindu weekend magazine, Studio Kohl. Density: low to medium (breathable).
C  Cinematic:  Photographic or photorealistic render; shallow depth of field, single hero subject, atmospheric lighting, film grain, letterbox crop. Subject rendered with product-photography precision. Reference: The Ken hero images, Condé Nast Traveller India, film stills. Density: minimal (subject + negative space only).
D  Playful Illustrated:  Hand-drawn sticker-style, thick marker outlines, flat colour-blocks, slight rotation/wobble on each element, doodle decorations (stars, hearts, squiggles, "zzz" icons). Subject looks like a Bitmoji or WhatsApp sticker. Reference: Alicia Souza comics, Gemma Correll doodles, Apple Memoji. Density: medium to high (decorated).
Same subject (say IL-3 Chai+Marigold from the table below) can live in all 5 Tracks; the Track decides the rendering. Illustration customisation knobs per Track -- all preset-based (density Low/Medium/High/Max, outline weight Thin/Standard/Bold, texture intensity Subtle/Paper/Rough, ornament count Minimal/Balanced/Busy) -- defined in the Track Library at the end of this document.

**ID**


**Illustration / Image**


**Description & Context**


**Archetypes**


**Style**


**GM-I1  BEVERAGES  (8 items)**


**GM-I1-01**


**Steaming Chai Cup**

Classic ceramic cup with rising steam wisps. Most iconic Good Morning visual in India.
All
Flat illus / watercolor / photo

**GM-I1-02**


**Clay Kulhad with Chai**

Earthen kulhad filled with masala chai -- culturally resonant, especially Tier 2/3 Bharat.
A1, A2, C1
Flat illus / watercolor

**GM-I1-03**


**Brass Tumbler (Davara Set)**

Traditional South Indian brass tumbler + davara set with filter coffee. Strong regional affinity.
A1, A2
Flat illus / photo

**GM-I1-04**


**Masala Chai with Spices Spread**

Chai cup surrounded by cinnamon sticks, cardamom pods, ginger, cloves. Aromatic feel.
A2, C1
Flat illus / watercolor

**GM-I1-05**


**Glass of Fresh Orange Juice**

Bright citrus energy. Best for summer or uplifting Good Morning variant.
A2, B1
Photo / flat illus

**GM-I1-06**


**Haldi Doodh (Turmeric Milk)**

Glass of golden milk with turmeric. Wellness angle -- growing cultural trend.
A2, C1
Flat illus

**GM-I1-07**


**Decorative Ceramic Teapot + Cup**

Patterned ceramic teapot with matching cup. Pairs well with floral frames (F4, F5).
A1, A2
Flat illus / watercolor

**GM-I1-08**


**Tender Coconut Water**

Fresh coconut with straw. Works for coastal/tropical Good Morning and health-angle posts.
A2, B1
Photo / flat illus

**GM-I2  NATURE & SKYSCAPES  (9 items)**


**GM-I2-01**


**Sunrise over Green Hills**

Wide golden horizon with soft mist in valley. Timeless, universal Good Morning backdrop.
All
Photo / watercolor

**GM-I2-02**


**Sun Rays through Forest Trees**

Morning light filtering through dense tree canopy. Spiritual, peaceful tone.
B1, D1, A2
Photo / watercolor

**GM-I2-03**


**Dew Drops on Green Leaf**

Close-up macro dew drops with sunrise bokeh behind. Fresh, pure, minimal.
A2, B1
Photo / flat illus

**GM-I2-04**


**Morning Mist over River**

Still river with golden mist rising, sun just above horizon. Meditative quality.
B1, D1
Photo

**GM-I2-05**


**Sunrise over Ocean Horizon**

Wide golden sea with sun on horizon, gentle waves. Universal appeal, coastal feel.
B1, D1
Photo

**GM-I2-06**


**Mountain Peak at Golden Hour**

Rocky or snow peak bathed in warm orange first light. Aspirational, motivational.
B1, A2
Photo / watercolor

**GM-I2-07**


**Foggy Valley with Light Shafts**

Dense morning fog with god rays cutting through. Dramatic, ethereal, high-shareability.
B1, D1, C1
Photo

**GM-I2-08**


**Rainbow after Morning Rain**

Fresh rainbow over green landscape after early shower. Hope and new beginnings.
B1, A2, C1
Photo / flat illus

**GM-I2-09**


**Dawn Sky Colour Gradient**

Abstract sky -- navy to lavender to peach to gold. Pure colour wash. Ideal for C2 BG.
C2, B1, D1
Photo / gradient art

**GM-I3  FLOWERS & BOTANICALS  (9 items)**


**GM-I3-01**


**Marigold Garland (Genda Phool)**

Classic Indian flower garland -- used in temples, festivals, weddings. Highest cultural resonance.
A1, A2, C1
Flat illus / watercolor

**GM-I3-02**


**Lotus in Full Bloom**

Open lotus on still water. Sacred, pure, new beginnings -- perfect Good Morning symbol.
A1, A2, C1, B1
Flat illus / photo / watercolor

**GM-I3-03**


**Jasmine Buds (Mogra)**

Small white jasmine buds on vine. Subtle, fragrant, feminine. High affinity in South India.
A1, A2
Flat illus / watercolor

**GM-I3-04**


**Hibiscus (Gudhal Phool)**

Large red hibiscus. Morning puja flower. Strong colour, works well against light BG.
A1, A2
Flat illus

**GM-I3-05**


**Sunflower Facing Sun**

Single sunflower turning toward sunrise. Instantly communicates morning energy.
A2, B1, C1
Flat illus / photo

**GM-I3-06**


**Champa / Frangipani**

Creamy yellow-white tropical flower. Associated with temples and calm spiritual mornings.
A1, A2
Flat illus / watercolor

**GM-I3-07**


**Rose Bud with Dew**

Fresh rose bud with morning dew on petals. Universally appealing, romantic-friendly.
A2, B1
Photo / watercolor

**GM-I3-08**


**Petals Floating on Water**

Colourful rose and marigold petals on calm water with golden reflection.
B1, A2
Photo / flat illus

**GM-I3-09**


**Cherry Blossom Branches**

Soft pink blossom branches. Elegant, aspirational. Works for modern/urban Good Morning.
A1, A2, C1
Flat illus / watercolor

**GM-I4  SPIRITUAL & DEVOTIONAL  (9 items)**


**GM-I4-01**


**Lit Diya with Warm Glow**

Single diya with flame glow and soft light halo. Devotional, auspicious. Works in all archetypes.
All
Flat illus / photo

**GM-I4-02**


**OM Symbol with Light Rays**

OM in gold with radiant glow. Sacred, universal Hindu symbol. Strong on dark BG.
A1, A2, C1, C2
Flat illus / 3D art

**GM-I4-03**


**Hands in Namaste**

Joined palms greeting gesture. Universal Indian Good Morning symbol. Works with E1.
A2, E1, C2
Flat illus / photo

**GM-I4-04**


**Incense Stick (Agarbatti) Smoke**

Single lit agarbatti with rising smoke curl. Evokes temple morning, calm, purity.
A1, A2, B1
Flat illus / photo

**GM-I4-05**


**Tulsi Plant in Brass Pot**

Sacred tulsi in traditional brass/clay planter. Morning puja association -- strong Bharat signal.
A1, A2
Flat illus / photo

**GM-I4-06**


**Temple Bell (Ghanti)**

Brass temple bell. Evokes morning aarti, awakening. Strong cultural anchor for Bharat.
A1, A2
Flat illus / photo

**GM-I4-07**


**Shankh (Conch Shell)**

White conch shell blown at dawn in temples. Sacred, auspicious, calls the day to start.
A1, A2
Flat illus / photo

**GM-I4-08**


**Rangoli at Dawn**

Colourful rangoli pattern with early morning light falling on it. Joyful, celebratory.
A1, A2, C1
Flat illus / photo

**GM-I4-09**


**Peacock Feather**

Single peacock feather. Associated with Krishna, beauty, and the divine. Decorative + spiritual.
A1, A2
Flat illus / watercolor

**GM-I5  LIFESTYLE & HUMAN MOMENTS  (8 items)**


**GM-I5-01**


**Surya Namaskar Silhouette**

Person doing sun salutation at sunrise. Aspirational, wellness, Bharat-relevant.
A2, B1, E1
Flat illus / silhouette / photo

**GM-I5-02**


**Meditating Figure at Sunrise**

Seated meditation silhouette against rising sun. Calm, spiritual, motivational.
A2, B1, E1
Flat illus / silhouette

**GM-I5-03**


**Open Window with Sunrise View**

Interior frame looking out at golden morning sky. Warmth, welcome, new day begins.
A1, A2, B1
Flat illus / photo

**GM-I5-04**


**Book and Chai on Morning Desk**

Open book, steaming chai, early light. Intellectual, cosy, aspirational.
A2, B1
Photo / flat illus

**GM-I5-05**


**Morning Walk on Tree-Lined Path**

Silhouette or person walking on park path in early morning light.
B1, A2, E1
Photo / flat illus

**GM-I5-06**


**Watering Plants on Balcony**

Morning routine -- watering indoor or balcony plants, soft sunlight behind.
A2, B1, E1
Photo / flat illus

**GM-I5-07**


**Family at Morning Breakfast**

Warm group scene sharing morning meal. Relatable, festive, high share-rate.
B1, E1
Photo

**GM-I5-08**


**Farmer in Field at Sunrise**

Silhouette of farmer with tools in golden sunrise field. Bharat-rooted, grounding.
B1, A2
Photo / flat illus / silhouette

**GM-I6  BIRDS & WILDLIFE  (6 items)**


**GM-I6-01**


**Bird Flock at Sunrise (V-Formation)**

Birds flying in morning sky. Freedom, new beginnings. Universal Good Morning trope.
B1, A2, C1
Photo / flat illus / silhouette

**GM-I6-02**


**Sparrow on Flowering Branch**

Small sparrow perched on blossom branch in morning light. Delicate, intimate, gentle.
A2, A1
Watercolor / flat illus

**GM-I6-03**


**Peacock with Fanned Tail**

Peacock displaying in golden morning light. Majestic, Indian identity, celebratory.
A2, B1, C1
Flat illus / photo / watercolor

**GM-I6-04**


**Parrot on Mango Branch**

Green parrot on leafy branch. Bright colour, tropical, cheerful energy.
A2, A1
Flat illus / watercolor

**GM-I6-05**


**Sarus Crane in Misty Field**

Elegant crane standing in foggy morning field. Peaceful, serene, poetic quality.
B1, A2
Photo / watercolor

**GM-I6-06**


**Butterflies on Flowers at Dawn**

Two or three butterflies on morning flowers. Light, hopeful, soft feel.
A2, C1, B1
Flat illus / watercolor / photo

**GM-I7  FOOD & MORNING RITUAL  (6 items)**


**GM-I7-01**


**Idli-Sambar Plate**

Classic South Indian breakfast -- idli, sambar, coconut chutney. Regional identity, home warmth.
A2, B1
Photo / flat illus

**GM-I7-02**


**Poha Bowl with Garnish**

Light yellow poha with coriander, lemon, pomegranate. Everyday Bharat breakfast.
A2, B1
Photo / flat illus

**GM-I7-03**


**Butter Paratha on Rustic Plate**

Hot paratha with melting butter. Comfort, home, warmth. High relate-factor.
A2, B1
Photo

**GM-I7-04**


**Seasonal Fruit Bowl**

Mixed fruits -- mango, banana, pomegranate, orange. Freshness and health angle.
A2, B1, C1
Flat illus / photo

**GM-I7-05**


**Newspaper with Chai**

Folded newspaper + steaming chai cup. Classic Indian morning routine. Nostalgic.
A2, B1
Photo / flat illus

**GM-I7-06**


**Morning Puja Thali**

Small plate with flowers, tilak powder, fruits for morning puja ritual. Devotional.
A1, A2
Photo / flat illus

**AI Prompt Generation**

Once a user completes Steps 1-5, the system auto-generates an AI image prompt for Midjourney and Adobe Firefly. The formula below maps each step selection to a prompt variable. All sample prompts below use default Good Morning selections (GM-C1 palette + GM-I1 Chai Cup + L1 Text Top).
Midjourney Formula: /imagine [VISUAL_SUBJECT] + [SETTING] + [COLOUR_TONE] + [STYLE] + [COMPOSITION] + --ar 9:16 [--style raw for photo]
Adobe Firefly Formula: [VISUAL_SUBJECT] in [STYLE] style, [COLOUR_TONE], morning light, [COMPOSITION_NOTE], 9:16 portrait

**Variable Reference:**


**VISUAL_SUBJECT: From Step 5 illustration/image selection (e.g. "steaming chai cup", "sunrise over hills")**


**SETTING: Always: "warm morning sunrise setting" / "golden hour" / "peaceful morning"**


**COLOUR_TONE: From Step 3 palette in plain English (e.g. Sunrise Gold -> "warm amber and golden tones")**

STYLE: From archetype: A1/A2 -> "flat illustration" or "soft watercolor", B1 -> "photorealistic", C1/C2 -> "minimal background", E1 -> "photorealistic digital art"
COMPOSITION: From Step 2 layout: L1 -> "space for text at top", L2 -> "centered text overlay space", L3 -> "left side text space, right for visual", L4 -> "right side text space, left for visual", L5 -> "space for text at bottom"

**Per-Archetype Default Prompts**

These are the auto-generated prompts using default selections for each archetype. Creators can override any variable through the customisation fields below.
Prompt assembly -- every default prompt is built from 8 locked basis options.  Sharp prompts require sharp inputs. Each prompt in the table below concatenates the following selections in order so the generator cannot drift:
(1) Track (A/B/C/D/E) -- sets style keywords + negatives; e.g., Track C injects "cinematic, shallow DOF, film grain, Kodak Portra 400, letterbox" and negatives "no cartoon, no flat illustration, no stickers"; Track E injects "soft warm gentle morning poster, calming pastel botanical aesthetic" and negatives "harsh, neon, loud, metallic, glitter".
(2) Archetype (A1/A2/B1/B2/C1/C2/D1) -- sets composition type (frame, free illustration, full photo, photo w/ object, animated elements, diptych, abstract).
(3) Layout (L1/L2/L3/L4) -- dictates where negative space sits (top-third, bottom-third, centred, split). Prompt explicitly reserves that region as "empty/clean/no elements" so text can be layered later without collision.
(4) Palette (GM-C1..C6) -- exact hex codes injected into prompt, e.g. "dominant #F59E0B warm amber, accent #7C2D12 deep terracotta, highlight #FEF3C7 cream". Track variant shift applied on top.
(5) Subject (from vertical-specific subject library) -- the hero object/scene, with concrete descriptors baked in: e.g., not just "chai cup" but "brass-handled kulhad with steam rising, wet saucer, one marigold placed beside".
(6) Mood anchor -- one of: devotional / celebratory / peaceful / energetic / nostalgic. Explicit in prompt, not left to model interpretation.
(7) Technical specs -- aspect ratio (--ar 9:16 default for WhatsApp status), style flag (--style raw for C, default for A/B/D), stylize value (--s 250 for A, --s 50 for B, --s 150 for C, --s 400 for D).
(8) Negative prompt -- universal + Track-specific. Universal: "no text, no logo, no watermark, no distorted faces, no Western fonts, no Christmas/Halloween motifs." Track-specific appended on top.
Defaults below now reflect the 8-basis assembly for Track C (Cinematic) + Good Morning vertical + GM-C1 Golden Hour palette + devotional/peaceful mood. Override any single basis and the prompt regenerates deterministically.

**Code**


**Archetype**


**Midjourney Prompt (Default)**


**Adobe Firefly Prompt**


**Production Note**


**A1**


**Text + Frame**

[Track A Shiny Maximal + Archetype A1 Text+Frame + Layout L1 Top-Text + Palette GM-C1 Golden Hour + Subject: devotional chai morning + Mood: celebratory]  Ornate symmetric decorative border frame filling all 4 edges of a 9:16 portrait, gold-leaf filigree with paisley and marigold motifs rendered in warm amber (#F59E0B) on deep saffron (#B45309) ground, central bordered panel (empty clean plate, no elements) reserved for heading text in the top third, below panel a small centred illustration of a brass kulhad chai cup with curling steam wisps and three marigold blossoms, gradient gold ink wash, flat vector illustration with metallic gold accents, ornamental Indian wedding-card aesthetic, celebratory warm morning mood, --ar 9:16 --s 400 --stylize high. Negative: no text, no logo, no watermark, no photography, no cartoon, no Western fonts, no Christmas motifs.
Ornamental symmetric decorative frame border on all 4 edges, gold filigree with paisley and marigold motifs, warm amber (#F59E0B) on deep saffron (#B45309), centre-bottom illustration of brass kulhad chai cup with steam and 3 marigold blossoms, top third reserved as clean empty panel for text, flat vector illustration with gold metallic accents, Indian wedding-card ornamental style, celebratory mood, 9:16 portrait, high detail. Exclude: text, logos, photography, cartoon, Western motifs.
L2 (Overlay) or L1 (Text Top) work best for A1 + F1 frame.

**A2**


**Text + Illustrations**

[Track B Modern Desi + Archetype A2 Text+Illustrations + Layout L1 Top-Text + Palette GM-C1 Golden Hour (muted) + Subject: chai+marigold+morning birds + Mood: peaceful nostalgic]  Contemporary editorial watercolor illustration, 9:16 portrait, top third reserved as clean empty negative space (no elements, smooth gradient wash) for heading text overlay, centre-to-bottom composition featuring a brass kulhad chai cup with rising steam wisps (anatomically precise, asymmetric placement left-of-centre), cluster of 5-7 marigold blossoms rendered loose watercolour at bottom-right, two silhouetted morning bulbul birds in soft focus top-right corner, scattered tulsi leaves and a small clay diya, muted terracotta (#C2410C) + ochre (#D97706) + sage (#84A98C) palette with hints of cream (#FEF3C7), soft watercolour paper texture, hand-painted feel, peaceful nostalgic Indian morning mood, gentle warm morning light from upper-left, negative space top 30 percent, --ar 9:16 --s 50 --style raw. Negative: no text, no logo, no watermark, no heavy outlines, no saturated neon colours, no Western iconography, no Christmas motifs.
Loose editorial watercolour illustration, brass kulhad chai cup left-of-centre with rising steam, cluster of marigold blossoms bottom-right, two silhouetted bulbul birds top-right in soft focus, small clay diya, scattered tulsi leaves, muted terracotta + ochre + sage palette with cream highlights, paper texture, peaceful nostalgic Indian morning, top 30 percent empty gradient wash reserved for text, 9:16 portrait, high detail. Exclude: text, logos, heavy outlines, neon colours, cartoon style.
Medium or Dense illustration weight. All layouts available.

**B1**


**Full Photo BG**

[Track C Cinematic + Archetype B1 Full Photo BG + Layout L2 Gradient-Top Overlay + Palette GM-C1 Golden Hour (cinematic grade) + Subject: sunrise over Indian landscape + Mood: peaceful reverent]  Photorealistic landscape photograph, 9:16 portrait framing, golden-hour sunrise over layered misty Himalayan foothills or a Uttarakhand tea-estate valley, warm god-rays filtering through silhouetted deodar trees on left-third, low horizon placed at bottom 40 percent, sun partially hidden behind a ridgeline creating a gentle lens flare, atmospheric haze with volumetric light shafts, distant temple spire or village silhouette barely visible mid-ground (tiny, non-distracting), shot on Kodak Portra 400 film aesthetic, teal-amber cinematic colour grade with deep #1E3A5F shadows and warm #F59E0B highlights, shallow depth of field with softly blurred foreground grass blades, subtle film grain, letterbox composition, peaceful reverent morning mood, top 35 percent of frame intentionally underexposed/darkened for overlay text legibility, --ar 9:16 --style raw --s 150 --chaos 0. Negative: no text, no logo, no watermark, no people faces, no cartoon, no flat illustration, no HDR over-saturation, no Christmas motifs, no fake rainbow.
Photorealistic golden-hour sunrise over misty Himalayan foothills or tea-estate valley, god-rays through silhouetted deodar trees on left, low horizon bottom 40 percent, sun behind ridgeline with soft lens flare, atmospheric haze, distant temple spire silhouette mid-ground, Kodak Portra 400 film look, teal-amber cinematic grade, deep navy shadows, warm gold highlights, shallow depth of field, subtle grain, top 35 percent darkened for text overlay, peaceful reverent mood, 9:16 portrait, no text, no logos, no people, no cartoon.
Apply O2 (Gradient Top-Heavy) overlay so text at top stays readable.

**C1**


**Animated Elements**

[Track C Cinematic + Archetype C1 Animated Elements + Layout L3 Centre-Framed + Palette GM-C1 Golden Hour + Subject: soft gradient sky backdrop for particle animation + Mood: peaceful meditative]  Static background frame (animation loop added in post), 9:16 portrait, soft vertical gradient sky from deep saffron (#B45309) at top to warm amber (#F59E0B) mid-frame to cream (#FEF3C7) at bottom, gentle bokeh orbs of light scattered across mid-frame suggesting suspended marigold petals and dust particles (positioned asymmetrically, never centred, avoiding the central text-safe zone of 60 percent x 40 percent in frame middle), no hard subject, no sharp focal point, minimal composition with wide breathable negative space, silhouetted temple spire or banyan branch in extreme top-right corner at 15 percent opacity (barely visible), subtle film grain, peaceful meditative mood, cinematic depth, --ar 9:16 --s 150 --style raw --chaos 0. Negative: no text, no logo, no watermark, no animated elements (particles added in prod pipeline), no flat cartoon, no dense composition, no centred subject, no distracting detail.
Soft vertical gradient morning sky, deep saffron top to warm amber mid to cream bottom, scattered asymmetric bokeh light orbs (never centred), wide breathable negative space in centre for text, silhouetted banyan branch in top-right at 15 percent opacity, subtle grain, cinematic depth, peaceful meditative mood, 9:16 portrait. Exclude: text, logos, dense subjects, centred elements, cartoon style, hard focal points.
This is the static BG frame -- animation elements (particles, loops) are added in production layer.

**C2**


**Animated Text**

Warm golden gradient background, soft morning light rays, clean minimal design, generous space centred for large animated text overlay, sunrise colour palette, --ar 9:16
Warm golden gradient with subtle morning rays, minimal background for text animation, portrait 9:16
Background must be clean and low-contrast -- text animation is the hero.

**D1**


**Video Background**

[Not applicable -- use video source] Runway AI prompt: slow sunrise timelapse with golden rays warming across misty landscape, peaceful morning motion, looping 6-8 seconds, no text, --ar 9:16
[Not applicable -- source from stock sunrise loop or AI video tool like Runway / Pika]
Best video category: Calm & Natural. O2 overlay recommended for text readability.

**E1**


**AI Avatar**

Indian woman in traditional morning salwar kameez, hands in Namaste greeting gesture, soft warm morning light through window, photorealistic, space for greeting text overlay at top, --ar 9:16 --style raw
Indian woman in traditional attire doing Namaste greeting, warm morning indoor light, photorealistic, space for text at top, portrait 9:16
Realistic style recommended for Good Morning. Avatar attire (Step 5) should be morning-appropriate -- kurta, salwar, sari.

**Creator Customization Areas**

Creators can override any of the following fields. All other steps remain at their selected or default values. Customization modifies the corresponding prompt variable and updates the generated prompt in real time.

**Customizable Field**


**What It Does**


**Input Method**


**Recipient Name**

Personalise the greeting -- "Good Morning [Name]!" adds intimacy. Optional. If blank, generic text is used.
Creator input (text field)

**Message / Quote**

Short blessing, motivational line, or Shayari. Max 2 lines recommended. Hindi / English / Hinglish.
Creator input (text or pick from curated library)

**Language**

Hindi / English / Hinglish (default). Regional language support TBD in Phase 2.
Creator selection (dropdown)

**Specific Visual Override**

Replaces Step 5 default with a specific visual request -- e.g. "use lotus instead of chai cup". Modifies the AI prompt VISUAL_SUBJECT variable.
Creator input (optional text)

**Time of Day Variant**

Good Morning (default) / Good Afternoon / Good Evening / Good Night. Changes colour palette recommendation and prompt SETTING variable.
Creator selection (optional)

**Track Library  --  Per-Track Spec Sheet**

Each Track Library row locks one dimension (palette / fonts / illustration / customisation / prompt flags / negatives / references / approved archetypes). Tracks are hard-forked -- no cross-contamination between Libraries. Examples below use GM (Good Morning) vertical; NY (New Year), Anniversary, Festival verticals follow the same structure with vertical-specific palette families.

**Track A -- Shiny Maximal  (jazzy desi -- festive, celebratory, loud on purpose)**


**Dimension**


**Specification**


**Palette family**

9 palettes (GM-C1-A through GM-C9-A). GM-C1-A: Dominant #FF8C1A neon marigold / Accent #FF6B00 electric saffron / Highlight #FFD700 hot gold / Punch #8B0000 deep maroon. 3 NEW Track-A-exclusive palettes: GM-C7-A Hot Pink Festive (#EC4899), GM-C8-A Royal Purple (#7C3AED), GM-C9-A Peacock Teal (#0891B2). All paired with gold accents.

**Finish options [NEW]**

5 background treatments: FN-1 Plain Solid, FN-2 Radial Gradient, FN-3 Sparkle/Glitter, FN-4 Metallic Foil, FN-5 Bokeh Glow. Each injects specific prompt language controlling background surface.

**Font pool**

Display: Cinzel Decorative, Samarkan, Ranchers, Alfa Slab One, Yatra One, Rozha One. Script: Great Vibes, Allura, Sacramento, Parisienne. Body: Montserrat Black, Poppins Bold, Mukta Bold. Treatments: gold-fill, metallic gradient, drop-shadow, outer glow, emboss.

**Illustration rendering**

3 sub-styles: IR-1 Ornamental Vector (gold-foil, paisley/mandala borders, symmetric, stamped-metal), IR-2 Colourful Vector (vivid flat colours, bold outlines, no gold, poster style), IR-3 3D Glossy (raised embossed, candy sheen, dimensional). User selects one per template.

**Motif set [NEW]**

10 Indian mass-market patterns: MT-1 Paisley, MT-2 Mandala, MT-3 Marigold Chain, MT-4 Lotus Border, MT-5 Peacock, MT-6 Diya Row, MT-7 Rangoli, MT-8 Temple Arch, MT-9 Mehndi Swirls, MT-10 Bel Patta Vine. Applied to frame borders + background accents.

**Customisation presets [NEW]**

3-tier master control: Basic (restrained festive) / Medium (balanced bling) / Complex (maximum desi). Auto-sets 6 knobs: ornament density, gold amount, shimmer/sparkle, metallic finish, motif coverage, drop shadow. Individual knobs remain accessible.

**Prompt style flags**

Midjourney: --ar 9:16 --s 400 --chaos 5 --weird 25 --stylize 400. Leonardo: Alchemy ON, PhotoReal OFF. Firefly: stylize 80, Art content type. Platform-specific prompt templates with [FINISH_PROMPT], [MOTIF_PROMPT], [ILLUSTRATION_RENDERING_STYLE] injection.

**Negative prompt**

No minimalism, no muted colours, no sans-serif only, no empty/breathable composition, no photorealism, no film grain, no Western ornaments, no pastel palette.

**Reference aesthetics**

Punjabi wedding invitations, Diwali greeting cards, Madhubani-revival digital art, Bollywood film posters (80s-90s), FabIndia festive packaging, ShareChat/Moj top GM posts, Rajasthani miniature-meets-digital, temple decoration art, Indian truck art, Meenakari enamel, Patachitra, zardozi embroidery, Kalamkari, Tanjore gold leaf, Banarasi brocade.

**Approved archetypes**

A1 (best fit), A2, B1 (photo with ornamental overlay). Not recommended: C2 minimal, D1 illustrated (conflict with maximalism).

**Detailed BRD -- Track A Shiny Maximal**

Prototype-ready specification. Every design token below is engineering-resolvable -- hex codes, font stacks, pixel dimensions, model flags.

**1. Colour System -- Design Tokens**


**Role**


**Hex / Value | Name | Usage rule**


**Primary 1 / Dominant**

#FF8C1A | Neon Marigold | Background fill 60%, primary brand surface, edge-to-edge canvas fills

**Primary 2 / Dominant**

#FF6B00 | Electric Saffron | Background gradient stop, deep saturated accent blocks

**Primary 3 / Highlight**

#FFD700 | Hot Gold | Metallic foil fills, decorative borders, headline text-gradient top stop

**Primary 4 / Highlight**

#DAA520 | Antique Gold | Headline text-gradient bottom stop, ornamental strokes

**Accent 1 / Punch**

#8B0000 | Deep Maroon | Text on light gold, contrast accent, bottom-band fills

**Accent 2 / Punch**

#B8001F | Kumkum Red | CTA buttons, sindoor tika motif, dot-accents

**Accent 3 / Sparkle**

#FFFFFF | Spark White | Sparkle particle cores, lens-flare highlights

**Neutral / Deep**

#1A0F00 | Ink Black | Body caption text fallback

**Neutral / Cream**

#FFF8E7 | Ivory Cream | Secondary surface, text-box underlays at 85% opacity

**Gradient A**

linear-gradient(135deg, #FF6B00 0%, #FFD700 100%) | Saffron-Gold Diagonal | Headline fill, CTA hover

**Gradient B**

radial-gradient(circle at 50% 40%, #FFD700 0%, #FF8C1A 55%, #8B0000 100%) | Sunburst Radial | Full-bleed hero backgrounds

**Shadow / Glow**

rgba(139,0,0,0.45) | Maroon Drop | Text drop-shadow offset 0,4 blur 12

**Glow / Outer**

rgba(255,215,0,0.70) | Gold Outer Glow | Headline outer-glow blur 24, sparkle bloom

**Extended palette -- Track-A-exclusive colours [NEW]:**


**Palette**


**Hex Values | Vibe**


**GM-C7-A Hot Pink Festive**

BG: #EC4899 | Text: #FFFFFF | Accent: #FBBF24 (gold) | Secondary: #BE185D (magenta). Bollywood glamour, shaadi pink.

**GM-C8-A Royal Purple**

BG: #7C3AED | Text: #FEF3C7 (cream) | Accent: #FFD700 (gold) | Secondary: #5B21B6. Regal, Dussehra, Navratri, premium festive.

**GM-C9-A Peacock Teal**

BG: #0891B2 | Text: #FFFFFF | Accent: #FFD700 (gold) | Secondary: #155E75. Peacock motif energy, Krishna, blue-gold.

**1b. Colour Role Assignment -- Zone-to-Colour Mapping [NEW]**

Core rule: The background colour stays vivid and lively (Good Morning category design decision). BUT the illustration subject, frame/motif, and text MUST use contrasting palette colours -- never the same hue as the background. This creates visual hierarchy: vivid background -> distinct frame -> standout illustration -> readable text.

**Colour zones and their roles:**


**Zone**


**Role and Rule**


**Canvas Fill**

The dominant background surface (60% of canvas). Uses the palette BG colour. Stays vivid.

**Frame / Motif**

Decorative frame + motif elements. Must be VISUALLY DISTINCT from canvas fill. Default: gold (#FFD700) on most backgrounds. On gold/saffron backgrounds: use deep maroon or brown.

**Illustration Primary**

Main colour of the illustration subject. Must CONTRAST against canvas fill. NEVER the same hue as the background. E.g., on orange background, chai cup is rendered in maroon + cream + gold, NOT orange.

**Illustration Accent**

Secondary details on illustration. Complements illustration primary. Can use darker/lighter variant of illustration primary.

**Text**

Headline + body text colour. Must pass 4.5:1 contrast ratio against canvas fill. Typically the darkest palette colour.

**Sparkle / Glow**

Particle highlights. Always white (#FFFFFF) regardless of palette -- needs to pop everywhere.

**Shadow**

Drop shadows. Always the darkest palette colour at reduced opacity.

**Per-palette colour role maps:**


**GM-C1-A Sunrise Gold:**


**Zone**


**Hex | Colour | Prompt Description**


**Canvas Fill**

#FF8C1A | Neon Marigold | "warm vivid orange-amber background"

**Frame / Motif**

#FFD700 / #DAA520 | Hot Gold / Antique Gold | "golden metallic frame, antique gold motifs"

**Illustration**

#8B0000 / #FFF8E7 | Deep Maroon + Ivory | "rendered in deep maroon, cream, white -- NOT orange"

**Illus Accent**

#B8001F / #FFD700 | Kumkum Red + Gold | "red and gold detail accents"

**Text**

#8B0000 or #FFFFFF | Maroon or White | "dark maroon or white text on orange"

**GM-C3-A Morning Sky:**


**Zone**


**Hex | Colour | Prompt Description**


**Canvas Fill**

#3B82F6 | Vivid Blue | "vivid sky blue background"

**Frame / Motif**

#FFD700 / #FBBF24 | Gold | "rich gold frame on blue -- royal blue-gold"

**Illustration**

#FFFFFF / #FBBF24 | White + Gold | "in white, gold, warm tones -- NOT blue"

**Text**

#FFFFFF or #FBBF24 | White or Gold | "white or gold text on blue"

**GM-C7-A Hot Pink Festive:**


**Zone**


**Hex | Colour | Prompt Description**


**Canvas Fill**

#EC4899 | Hot Pink | "vivid hot pink background"

**Frame / Motif**

#FFD700 / #FBBF24 | Gold | "gold frame on pink -- Bollywood glamour"

**Illustration**

#FFFFFF / #FFD700 / #BE185D | White + Gold + Deep Magenta | "NOT pink"

**Text**

#FFFFFF or #FBBF24 | White or Gold | "white or gold on pink"

**GM-C8-A Royal Purple:**


**Zone**


**Hex | Colour | Prompt Description**


**Canvas Fill**

#7C3AED | Vivid Purple | "rich vivid purple background"

**Frame / Motif**

#FFD700 | Gold | "gold frame on purple -- regal royalty"

**Illustration**

#FEF3C7 / #FFD700 / #FFFFFF | Cream + Gold + White | "NOT purple"

**Text**

#FEF3C7 or #FFD700 | Cream or Gold | "cream or gold on purple"

**GM-C9-A Peacock Teal:**


**Zone**


**Hex | Colour | Prompt Description**


**Canvas Fill**

#0891B2 | Peacock Blue | "rich peacock teal-blue background"

**Frame / Motif**

#FFD700 | Gold | "gold frame on teal -- peacock energy"

**Illustration**

#FFD700 / #FFFFFF / #FEF3C7 | Gold + White + Cream | "NOT teal/blue"

**Text**

#FFFFFF or #FFD700 | White or Gold | "white or gold on teal"

**Colour Harmony Enforcement Rules:**

1. NEVER render illustration in the dominant background colour. If BG is orange, illustration must use maroon/cream/gold/red -- never orange. The negative prompt must explicitly ban the BG colour on the illustration.
2. Frame/motif colour must be visually distinct from background. Gold frame on most backgrounds works. On gold/saffron backgrounds, use maroon or deep brown frame.
3. Text must pass 4.5:1 contrast ratio against background. Maroon on orange, white on dark backgrounds, gold on blue/purple/teal.
4. Sparkle particles always white (#FFFFFF) regardless of palette.
5. Negative prompt must include: "[BG_COLOUR_NAME] illustration, [BG_COLOUR_NAME] subject, monochrome, single-colour illustration" to prevent the AI from making everything the same colour.

**2. Typography System**


**Role**


**Font family | Weight / size / tracking | Use case**


**Display / Headline EN**

Cinzel Decorative | 900 / 96-140px / -0.5px | Main greeting headline

**Display / Headline HI**

Rozha One | 400 / 84-120px / 0px | Devanagari headline

**Display / Alt EN**

Samarkan | 400 / 72-110px / 0px | Festive alt headline

**Script / Tagline**

Great Vibes | 400 / 48-72px / 1px | Tagline, sub-headline flourish

**Script / Alt [NEW]**

Sacramento | 400 / 48-72px / 0px | Elegant script alternative

**Script / Festive [NEW]**

Parisienne | 400 / 36-60px / 0px | Romantic/festive tagline

**Sans / Subheadline**

Montserrat Black | 900 / 42-56px / 0px | Sub-headline, quote attribution

**Sans / Body**

Poppins Bold | 700 / 24-32px / 0.2px | Short body lines, CTA label

**Slab / Accent**

Alfa Slab One | 400 / 64-90px / 0px | Date / year badge / festival name

**Devanagari Display [NEW]**

Yatra One | 400 / 84-120px / 0px | Bold Devanagari festive display

**Body / Devanagari [NEW]**

Mukta Bold | 700 / 24-32px / 0.2px | Devanagari body text

**Mono / Caption**

JetBrains Mono | 500 / 14-18px / 0.5px | Meta info

**Treatments**

Allowed: gold-fill, metallic gradient, drop-shadow (blur 12, offset 0,4), outer glow (blur 24, #FFD700), emboss (depth 2, angle 45).

**3. Canvas & Layout BRD**


**Element**


**Specification | Rule**


**Canvas EG (portrait)**

1080 x 1920 px | Instagram Reels / Stories / WhatsApp status

**Canvas Square**

1080 x 1080 px | Instagram feed / WhatsApp DP

**Canvas Portrait 4:5**

1080 x 1350 px | Instagram feed portrait

**Safe Margin**

72 px all sides (7.5% of width) | No subject/text outside safe zone

**Headline Zone**

Top 35% of canvas OR bottom 30% | Never center unless subject is symmetric mandala

**Subject Focal Point**

Rule-of-thirds upper-right intersection (Tx=720, Ty=640 for 1080x1920)

**Brand Mark Zone**

Bottom-right, 24x24px logo, 48px margin | Jio leaf mark at 85% opacity

**Ornament Band**

Top 8% and bottom 8% strips | Decorative border / lattice work

**Text Underlay**

Ivory Cream #FFF8E7 at 78% opacity, blur-behind 8px | Only when headline over busy backdrop

**Spacing / Baseline**

8px grid, 16px gutters | All element alignment snaps to grid

**4. Rendering Pipeline & Prompt Construction**


**Platform-specific prompt templates [NEW -- replaces single-platform approach]:**


**Platform**


**Configuration**


**Primary Model**

Midjourney v6.1 | For ornamental, painterly, festive scenes

**Secondary Model**

SDXL + LoRA indian-ornamental-v2 | When MJ style drift; tighter control

**Tertiary Model [NEW]**

Leonardo.ai (Alchemy mode ON, PhotoReal OFF) | Alternative festive generation

**Midjourney prompt template:**


**Component**


**Value**


**MJ Flags**

--ar 9:16 --s 400 --chaos 5 --weird 25 --stylize 400

**Style Prefix**

"ornate festive Indian greeting, [FINISH_PROMPT], [MOTIF_PROMPT], warm radiant lighting,"

**Style Suffix**

"shimmering metallic highlights, [SPARKLE_PROMPT], radial sunburst glow, traditional Indian aesthetic, high detail, 8K --no minimalism, flat, modern, grunge, grayscale"

**Negative (--no)**

minimalism, flat design, grunge, dirty, grayscale, muted, monochrome, bauhaus, swiss, hand-drawn doodle, sticker, kawaii, cartoon

**Leonardo.ai prompt template:**

[SUBJECT]. [ILLUSTRATION_RENDERING_STYLE]. [FINISH_PROMPT]. [MOTIF_PROMPT]. Ornate festive Indian style, [COLOUR_DESC], [CUSTOMIZATION_PROMPT]. Portrait 9:16 format. Negative: minimalism, flat design, grayscale, muted, cartoon, sticker, Western ornaments, text, letters, watermark.

**Adobe Firefly prompt template:**

[SUBJECT]. [ILLUSTRATION_RENDERING_STYLE]. [FINISH_PROMPT]. [MOTIF_PROMPT]. Ornate festive Indian greeting style, [COLOUR_DESC], [CUSTOMIZATION_PROMPT]. Portrait 9:16 for mobile. Content type: Art. Stylize: 80. Do not include any text, letters, words, typography, watermarks, logos, or minimalist elements.

**Post-processing pipeline:**


**Step**


**Spec | Purpose**


**Post-process 1**

Lens flare overlay (Anamorphic Gold), 35% opacity, screen blend | Upper-right third

**Post-process 2**

Sparkle particle layer, 8-12 particles, 6-18px, Gold #FFD700, additive blend | Around focal point

**Post-process 3**

Vignette dark corners, 25% density, 1800px radius | Cinematic depth

**Post-process 4**

Grain 4% at 3200 ISO (Filmic subtle) | Prevents over-digital feel

**5. Finish -- Background Treatment [NEW]**

Controls how the background colour fill is rendered. Same hex, dramatically different visual feel. User selects one per template. Injected as [FINISH_PROMPT].

**ID / Name**


**Prompt Injection | Description**


**FN-1 Plain Solid**

"solid flat colour fill, clean matte surface, no texture, no effects on background." | Clean flat fill. Lets frame + illustration do the talking.

**FN-2 Radial Gradient**

"radial gradient from bright centre to darker edges, smooth luminous colour transition, glowing centre." | Centre-outward shimmer. Most versatile default.

**FN-3 Sparkle / Glitter**

"sparkle particle overlay across background, tiny golden glitter dots scattered throughout, festive shimmer texture." | Diwali card / celebration energy.

**FN-4 Metallic Foil**

"stamped metallic gold foil texture on background surface, embossed metallic finish, rich luxurious hammered gold." | Wedding card premium. Maximum bling.

**FN-5 Bokeh Glow**

"soft bokeh light orbs floating in background, warm golden out-of-focus lights, festive fairy light atmosphere." | Warm fuzzy festive lights.

**6. Illustration Rendering Sub-Styles [NEW]**

Track A supports 3 distinct rendering approaches. Same subject rendered in different visual treatments. User selects one per template. Injected as [ILLUSTRATION_RENDERING_STYLE].

**ID / Name**


**Prompt Description | Character | Reference**


**IR-1 Ornamental Vector**

"ornamental vector illustration with gold-foil fills, paisley and mandala borders, stamped-metal shading, drop-shadows, sparkle particles, symmetric composition, Indian ornamental art style." | Classic Track A -- wedding card energy. High to max density. | Madhubani-revival, Tanjore painting, wedding cards.

**IR-2 Colourful Vector**

"vivid colourful flat vector illustration, bright saturated colours (reds, oranges, yellows, pinks, greens), clean bold outlines, festive Indian colour palette, no gold treatment, celebratory and cheerful." | Bright flat colours, bold outlines. Red rose = bright red. | Bollywood poster art, Indian truck art palette, festival prints.

**IR-3 3D Glossy**

"3D glossy rendered illustration, raised embossed effect, smooth reflective surface, dimensional depth, candy-like sheen, modern premium sticker aesthetic, sharp highlights and soft shadows." | Raised/embossed, glossy reflective. Modern premium. | Apple emoji 3D, premium WhatsApp sticker packs.

**7. Motif Set -- Indian Mass-Market Pattern Library [NEW]**

User selects one primary motif set per template. Drives frame border decoration, background accents, corner/edge fills. Injected as [MOTIF_PROMPT].

**Motif**


**Prompt Keywords | Cultural Anchor | Best Palette Pairing**


**MT-1 Paisley (Ambi)**

"paisley mango motif pattern, traditional ambi teardrop design, Kashmir shawl ornament." | Universal Indian, pan-India. | GM-C1, GM-C5

**MT-2 Mandala**

"circular mandala pattern, geometric sacred concentric rings, symmetrical radial ornament." | Spiritual, universal. | GM-C5, GM-C8

**MT-3 Marigold Chain**

"marigold garland chain pattern as border, genda phool string, toran flower garland." | Puja, wedding, festival. Highest GM resonance. | GM-C1, GM-C2

**MT-4 Lotus Border**

"lotus flower border pattern, sacred lotus row design, padma petal chain." | Devotional, auspicious. | GM-C4, GM-C5

**MT-5 Peacock Motif**

"peacock feather eye motif pattern, mor pankh fan design, royal peacock ornament." | Royal, Krishna. | GM-C9, GM-C8

**MT-6 Diya Row**

"row of lit diyas oil lamp pattern as border, deepawali lamp chain." | Diwali, devotional. | GM-C1, GM-C5

**MT-7 Rangoli Corners**

"rangoli geometric pattern at corners, traditional kolam dot-grid design." | South + Central India. | GM-C4, GM-C6

**MT-8 Temple Arch**

"temple gopuram arch motif as frame header, mandir gate pillared design." | Devotional. Best with F5 Arch frame. | GM-C5, GM-C1

**MT-9 Mehndi Swirls**

"mehndi henna swirl pattern, intricate vine and dot flowing design, bridal mehandi." | Wedding, feminine. | GM-C7, GM-C2

**MT-10 Bel Patta Vine**

"bel leaf vine creeper border, sacred bilva leaf chain ornament." | Auspicious, nature-devotional. | GM-C4, GM-C5
Motif-to-Illustration auto-suggestion: Chai/Beverages -> Marigold Chain, Paisley. Nature/Sunrise -> Lotus Border, Bel Patta. Flowers -> matching flower motif. Spiritual -> Mandala, Diya Row, Temple Arch. Birds/Peacock -> Peacock Motif. Food/Ritual -> Marigold Chain, Rangoli.

**8. Customisation Presets -- Basic / Medium / Complex [NEW]**

Master control that auto-tunes all visual intensity knobs in one click. Controls how "maximal" the Shiny Maximal track actually gets.

**Knob**


**Basic (Restrained Festive) -> Medium (Balanced Bling) -> Complex (Maximum Desi)**


**Ornament Density**

Minimal (1-2 at corners) -> Balanced (3-5 at corners + midpoints) -> Rich (6+ throughout, no empty space)

**Gold Amount**

Accent only (highlights) -> Prominent (borders + frame fills + accents) -> Dominant (gold fills throughout)

**Shimmer / Sparkle**

Off -> Subtle (faint glow, 2-4 particles) -> Heavy (dense sparkle, 10-15 particles)

**Metallic Finish**

Matte -> Satin (subtle sheen) -> Full Foil (hammered metallic throughout)

**Motif Coverage**

Corners only -> Corners + midpoints (8 anchors) -> Throughout border AND background

**Drop Shadow**

None -> Soft (gentle on headline) -> Deep (strong on text + all elements)

**Individual knobs (preserved from existing, can override presets):**


**Knob**


**Options (default)  |  Effect**


**Ornament Density**

Low / Medium / High / Max (default: High) | Controls mandala/rangoli element count

**Gold Intensity**

Subtle / Balanced / Strong / Max (default: Strong) | Foil shine + highlight spread

**Sparkle Count**

Off / Few / Some / Many (default: Some) | Number of sparkle particles

**Text Glow Radius**

Off / Soft / Medium / Strong (default: Medium) | Outer glow on headline

**Headline Fill Mode**

solid / gradient / foil (default: foil) | Text fill treatment

**Subject Prominence**

Balanced / Hero / Dominant (default: Balanced) | Subject vs background visual weight

**Language Pair**

EN-only / HI-only / EN+HI stacked / EN+HI parallel (default: EN+HI stacked)

**Border Style**

none / lotus-lattice / chevron-foil / mandala-ring (default: lotus-lattice) | Top/bottom ornament band

**9. Frame Motif Selection -- Restructured A1 Flow [NEW]**

For A1 (Text + Frame), the visual setup step is restructured to ensure frame motifs and illustration choices are coherent:

**New A1 Visual Setup sub-step order:**

(1) Illustration Selection -- Pick category -> specific item -> size (existing flow).
(2) Frame Motif Selection [NEW] -- Pick motif pattern from Motif Set (MT-1 through MT-10). Tool auto-suggests motifs that complement the illustration. E.g., Lotus illustration -> Lotus Border (MT-4) and Mandala (MT-2) highlighted as "Best match."
(3) Frame Complexity -- Pick Plain / Simple / Detailed (existing options, now applied to the selected motif).
Frame overspill (Detailed only): When complexity = Detailed, prompt includes: "decorative motif elements allowed to extend slightly beyond the frame boundary, organic ornamental overspill at corners and edges, lush border that breathes and extends, not rigidly contained within straight lines." Reference: viral WhatsApp Good Morning posters with gold scrollwork + floral corner overspill.

**10. Reference / Moodboard [EXPANDED]**


**Reference**


**Description**


**Ref 1**

Punjabi wedding invitations -- gold foil, marigold, paisley, maximalist ornament

**Ref 2**

Diwali greeting cards -- diyas, rangoli, sparkle, saffron-gold palette

**Ref 3**

Madhubani-revival digital art -- folk patterns rendered with modern precision

**Ref 4**

Bollywood film posters (80s-90s era) -- dramatic, colourful, gold text

**Ref 5**

FabIndia festive packaging -- contemporary Indian ornamental, clean execution

**Ref 6**

ShareChat/Moj top Good Morning posts -- actual viral format, mass-market taste

**Ref 7**

Rajasthani miniature-meets-digital -- detailed scenes, ornate borders

**Ref 8**

Temple decoration art -- floral garlands, gold leaf, sacred geometry

**Ref 9**

Indian truck art -- vivid colour, bold patterns, unapologetic maximalism

**Ref 10**

Meenakari enamel work -- jewel tones, gold outlines, intricate fill

**Ref 11**

Patachitra folk art -- scroll painting, narrative panels, border storytelling

**Ref 12**

Zardozi embroidery -- raised gold threadwork, dimensional texture

**Ref 13**

Kalamkari textile prints -- hand-painted florals, mythological scenes

**Ref 14**

Tanjore painting gold leaf -- raised gold relief, gem-like colours, devotional

**Ref 15**

Banarasi brocade -- metallic zari patterns, silk texture, regal repetition

**Forbidden**

Minimalism, Scandinavian, Bauhaus, Swiss, grunge, pastel-only, Western holiday, Japanese kawaii
11. Approved Archetypes: A1 (best fit -- frame + ornament native), A2 (illustration-forward with festive palette), B1 (photo with ornamental overlay). Not recommended: C2 minimal (brand conflict), D1 illustrated/sticker (aesthetic conflict).

**Track B -- Modern Desi  (muted earthy -- contemporary editorial, restrained on purpose)**


**Palette family (GM-C1 example)**

GM-C1-B: Dominant #C2410C dusty terracotta / Accent #B45309 ochre / Highlight #FEF3C7 cream / Grounding #84A98C sage. Finish: flat matte, paper-grain or gouache texture. No gradients, no metallic.
Finish
4 options: Flat Matte, Paper Grain, Gouache Wash, Linen/Raw Cotton
Illustration Rendering
3 sub-styles: Loose Watercolour, Block Print, Ink Line + Wash
Motifs
8 options: Leaf Vine, Chai Steam, Block Stamp, Brush Stroke, Kolam Dots, Banana Leaf, Pichwai Lotus, Warli Figures
Customisation Presets
3 knobs (Minimal, Balanced, Expressive) control negative space, colour saturation, brush weight, texture
Prompt Flags
Minimal/Balanced/Expressive inject restraint + muted earth + editorial energy
Negative Prompt
Forbidden: Bollywood, Manyavar, loud/maximalist, gold foil, sparkle, metallic
References
Scroll.in, The Hindu weekend, Studio Kohl, Kulture Shop, Nicobar, Good Earth, The Ken, Paper Boat, Fabindia, Ellementry, Kinfolk
Approved Archetypes
A1-A7, B1-B3, C1-C3 (any Track B palette × any finish × any IR sub-style)
Colour Role System
Canvas is muted/earthy. Illustration uses slightly more saturated or darker tones within an earthy palette. Contrast is gentle, not dramatic.

**Detailed BRD -- Track B Modern Desi**


**Colour Role System**

Canvas is muted/earthy. Illustration uses slightly more saturated or darker tones within an earthy palette. Contrast is gentle, not dramatic.

**Palettes (8)**


**Palette ID**


**Name / Canvas / Accent / Illustration / Text / Vibe**

GM-C1-B
Terracotta Morning: #C2410C dusty terracotta / #B45309 ochre / Cream #FEF3C7 + Sage #84A98C / #FEF3C7 / Clay pottery warmth
GM-C2-B
Peach Silk: #FDE8D8 soft peach / #BC6C58 rose-brown / Deep Brown #78350F + white / #78350F / Banarasi silk softness
GM-C3-B
Indigo Calm: #4A5568 muted indigo / #9CA3AF warm grey / Cream #FEF3C7 + Rust #D97706 / #FEF3C7 / Ajrakh textile energy
GM-C4-B
Sage Garden: #D1FAE5 sage mint / #064E3B deep forest / Deep Forest #064E3B + cream / #064E3B / Tulsi morning
GM-C5-B
Turmeric Warm: #E8A317 warm turmeric / #78350F deep brown / Deep Maroon #7F1D1D + ivory / #7F1D1D / Haldi spice warmth
GM-C6-B
Clay + Cream: #FAF3E0 warm cream / #C2410C terracotta / Terracotta #C2410C + sage #84A98C / #3D2B1F / Studio pottery
GM-C7-B
Kalamkari: #7F1D1D deep maroon / #B8860B gold ochre / Cream #FEF3C7 + olive #6B7F3B / #FEF3C7 / Traditional textile
GM-C8-B
Pichwai Blue: #2D6A6A muted teal / #B8860B ochre / Cream #FFF8E7 + coral #E8967D / #FFF8E7 / Nathdwara painting

**Finish (4 options)**


**ID**


**Name / Prompt**

FN-B1
Flat Matte: solid flat matte colour fill, clean surface, no texture
FN-B2
Paper Grain: subtle handmade paper grain texture, kraft paper feel, slight fibrous texture
FN-B3
Gouache Wash: gouache paint wash background, visible brushstrokes at edges, wet watercolour bleeding
FN-B4
Linen / Raw Cotton: fine linen fabric or raw unbleached cotton textile surface, handloom khadi cloth feel

**Illustration Rendering (3 sub-styles)**


**ID**


**Name / Prompt**

IR-B1
Loose Watercolour: loose editorial watercolour illustration, visible brushstrokes, bleeding edges, paper texture, asymmetric, deliberate negative space, no outlines, Scroll.in editorial style
IR-B2
Block Print: Indian block print style, woodcut stamp aesthetic, 2-3 colours only, visible print grain, imperfect registration, handcrafted, Rajasthani ajrakh energy
IR-B3
Ink Line + Wash: fine ink line drawing with selective watercolour wash, detailed pen linework, sparse colour accents, botanical illustration precision, premium Indian greeting card style

**Motifs (8)**


**ID**


**Name / Prompt**

MT-B1
Leaf Vine: loose hand-drawn leaf vine border, organic trailing creeper
MT-B2
Chai Steam: wispy rising steam curl motif, delicate single-line smoke trails
MT-B3
Block Stamp: repeated small block-print stamp motif as border, woodcut flower pattern
MT-B4
Brush Stroke: single horizontal brush stroke divider, gouache swipe
MT-B5
Kolam Dots: simple geometric kolam dot pattern, minimal grid design, South Indian
MT-B6
Banana Leaf: banana leaf border element, broad tropical leaf
MT-B7
Pichwai Lotus: stylised pichwai painting lotus motif, single lotus Nathdwara style
MT-B8
Warli Figures: simple warli tribal art border, stick figure line art, Maharashtra folk

**Customisation Presets (3)**


**Knob**


**Minimal / Balanced / Expressive**

Negative Space
50-60% / 35-45% / 20-30%
Colour Saturation
40% cap / 55% cap / 65% cap
Brush Weight
Fine hairline / Medium stroke / Bold loose
Texture
Flat / Paper grain 12% / Gouache 25%
Prompt
Minimal='extremely restrained, 50% negative space, muted, fine hairline, flat, editorial minimalism' | Balanced='editorial balanced, deliberate negative space, muted warm, medium brush, subtle paper grain, contemporary Indian' | Expressive='rich editorial, bold loose brushstrokes, moderate space, warm saturated earth tones, visible gouache, maximum artistic expression'

**References**

Scroll.in, The Hindu weekend, Studio Kohl, Kulture Shop, Nicobar, Good Earth, The Ken, Paper Boat, Fabindia, Ellementry, Kinfolk photography. Forbidden: Bollywood, Manyavar, loud/maximalist, gold foil, sparkle, metallic.

**Approved Archetypes**

A1 through A7, B1 through B3, C1 through C3. Any Track B palette (GM-C1-B through GM-C8-B) × any finish × any IR sub-style creates a valid template combination.
Track C -- Minimalist Classy  (maximum restraint -- tonal elegance -- single element, generous space, typography is the hero)

**Palette family (GM-C1 example)**

GM-C1-C: Amber Glow #E8A317 canvas / #B8860B deep amber frame / Dark brown #6B4423 tonal illustration / Ivory #FFF8E7 accent (<5%) / #4A2C0A deep brown text. Tonal harmony: illustration uses SAME colour family as background (darker/lighter tones only). One accent colour allowed.
Finish
3 options: Flat Matte, Soft Gradient, Fine Paper
Illustration Rendering
3 sub-styles: Tonal Flat, Embossed/Stamp, Fine Line + Wash
Motifs
4 near-zero decoration: None, Hairline Rule, Corner Brackets, Single Dot
Customisation Presets
3 knobs (Ultra-Minimal, Balanced, Warm Elegant) control empty space (80%/70%/60%), illustration size, colour tones, frame, accent
Prompt Flags
Ultra-Minimal/Balanced/Warm Elegant inject tonal monochrome + maximum restraint + typography dominance
Negative Prompt
Forbidden: Ornate, gold foil, sparkle, metallic, bold display, multiple illustrations, busy, vivid, gradients, doodles
References
Muji, Aesop packaging, Japanese zen cards, premium Indian invitations (restrained), Nicobar, Olio Stories, Paper+Cloth stationery, Byredo, The School of Life
Approved Archetypes
A1-A7, B1-B3, C1-C3 (any Track C palette × any finish × any IR sub-style)
Colour Role System
UNIQUE: Illustration uses SAME colour family as background (darker/lighter tones). One accent colour allowed (<5% canvas).

**Detailed BRD -- Track C Minimalist Classy**


**Colour Role System**

UNIQUE: Illustration uses SAME colour family as background (darker/lighter tones). One accent colour allowed (<5% canvas). Tonal harmony is the defining constraint.

**Palettes (8)**


**Palette ID**


**Name / Canvas / Frame / Illustration (tonal) / Accent / Text / Vibe**

GM-C1-C
Amber Glow: #E8A317 warm amber / #B8860B deep amber / Dark brown #6B4423 tonal / Ivory #FFF8E7 dot / #4A2C0A / Saffron bird stamp
GM-C2-C
Soft Peach: #FDDCB5 pale peach / #BC6C58 rose-brown / Terracotta #A0522D on peach / Blue-grey #94A3B8 / #5D3A1A / Champa flower
GM-C3-C
Morning Cream: #FAF3E0 warm ivory / #B8860B ochre / Brown #8B6914 sepia on cream / Sage #84A98C leaf / #3D2B1F / Boutique card
GM-C4-C
Sage Mist: #E8F0E8 pale sage / #5F7A5F deep sage / Forest #3D5A3D on sage / Terracotta #C2410C / #2D4A2D / Botanical garden
GM-C5-C
Lavender Haze: #E8E0F0 pale lavender / #8B7DA8 muted purple / Purple-grey #5B4F7A on lavender / Soft gold #D4AF37 / #3D3456 / Evening calm
GM-C6-C
Slate Dawn: #D4CFC8 warm slate / #6B6560 charcoal / Deep charcoal #3D3835 on slate / Rust #B8501A / #2D2926 / Architectural
GM-C7-C
Rose Dust: #D4A0A0 dusty rose / #8B5A5A deep rose / Maroon-rose #6B3A3A on rose / Gold #D4AF37 / #4A2020 / Feminine premium
GM-C8-C
Teal Quiet: #A8C8C8 muted teal / #5A8080 deep teal / Dark teal #3A5858 on teal / Ochre #C8A050 / #2A4848 / Morning sea calm

**Finish (3 options)**


**ID**


**Name / Prompt**

FN-C1
Flat Matte: perfectly flat matte colour, no texture, absolutely clean surface
FN-C2
Soft Gradient: very subtle tonal gradient, barely perceptible, slightly lighter centre to deeper edges
FN-C3
Fine Paper: fine cotton rag paper texture, very subtle, premium stationery surface

**Illustration Rendering (3 sub-styles)**


**ID**


**Name / Prompt**

IR-C1
Tonal Flat: flat vector illustration in tonal shades of the background colour family only, darker silhouette values, monochromatic, elegant simplified forms, clean outlines in slightly darker shade
IR-C2
Embossed / Stamp: illustration as embossed stamp effect, tone-on-tone impression, debossed seal on background, subtle raised texture illusion, same colour family with shadow depth
IR-C3
Fine Line + Wash: delicate fine line illustration, thin precise pen lines, very selective soft wash in muted tones, botanical precision, generous empty space within illustration

**Motifs (4 — near-zero decoration)**


**ID**


**Name / Prompt**

MT-C1
None: no decorative motifs, no patterns, completely clean
MT-C2
Hairline Rule: single thin hairline rule border, 1px, geometric precision
MT-C3
Corner Brackets: minimal corner bracket marks, thin L-shaped crop marks
MT-C4
Single Dot: single small decorative dot or star at one corner, tiny accent

**Customisation Presets (3)**


**Knob**


**Ultra-Minimal / Balanced / Warm Elegant**

Empty Space
80%+ / 70% / 60%
Illustration Size
<15% canvas / 15-25% / 25-35%
Colour Tones
2 tones only / 3 tones + accent / 4 tones + accent
Frame
None / Hairline / Corner brackets
Accent
None (monochrome) / One subtle (<3%) / One + highlight (<5%)
Prompt
Ultra-Minimal='extremely minimal, tiny element <15%, 80% empty, pure tonal monochrome, no accent, no frame, typography dominant' | Balanced='minimal elegant, small element, 70% space, tonal + subtle accent, thin hairline frame, refined' | Warm Elegant='refined elegant, element at comfortable scale, 60% space, tonal + accent + highlight, corner brackets, warm sophisticated'

**Font Pool**

Heading: Cormorant Garamond Thin, Libre Caslon Display, EB Garamond, Spectral Light. Devanagari: Tiro Devanagari Hindi, Noto Serif Devanagari Light. Body: Inter Light, Source Sans 3 Light, Libre Franklin Light. Treatments: Flat only. Letter-spacing +100 to +200. No gradient/glow/shadow/outline. Single weight.

**References**

Muji, Aesop packaging, Japanese zen cards, premium Indian invitations (restrained), Nicobar, Olio Stories, Paper+Cloth stationery, Byredo, The School of Life. Forbidden: Ornate, gold foil, sparkle, metallic, bold display, multiple illustrations, busy, vivid, gradients, doodles.

**Approved Archetypes**

A1 through A7, B1 through B3, C1 through C3. Any Track C palette (GM-C1-C through GM-C8-C) × any finish × any IR sub-style creates a valid template combination.
Track D -- Artsy Playful  (flat bright -- sticker-sheet energy -- cheerful on purpose -- WhatsApp emoji meets kids' picture book)

**Palette family (GM-C1 example)**

GM-C1-D: Sunny Yellow #FACC15 canvas / #1E293B slate outline / Coral #FB7185 + Mint #A7F3D0 illustration (NOT yellow) / #7C2D12 text. Finish: flat solid, dot pattern, confetti scatter, striped. Bright contrast: background is bright flat, illustration uses DIFFERENT bright colours with thick dark outlines. Maximum pop.
Finish
4 options: Flat Solid, Dot Pattern, Confetti Scatter, Striped
Illustration Rendering
4 sub-styles: Flat Sticker, Doodle/Hand-Drawn, 3D Cartoon, Kawaii/Chibi
Motifs
6 options: Stars + Hearts, Squiggles + Swirls, Speech Bubbles, Confetti Shapes, Flower Doodles, Emoji Accents
Customisation Presets
3 knobs (Simple, Fun, Maximum) control density, outline, accents, wobble, pattern, sticker border
Prompt Flags
Simple/Fun/Maximum inject playful energy + bright pop + cheerful density
Negative Prompt
Forbidden: Photorealism, cinematic, ornate, editorial, gold, film grain, muted, serif
References
Alicia Souza, Gemma Correll, Apple Memoji, LINE Friends, WhatsApp Sticker Pack, Canva kids, Moonbow, Bhavesh Bhatia, Pixar flat-colour, Zomato/Swiggy illustrations, Chumbak, Nykaa packaging
Approved Archetypes
A1-A7, B1-B3, C1-C3 (any Track D palette × any finish × any IR sub-style)
Colour Role System
Background is a bright flat solid. Illustration uses DIFFERENT bright colours with thick dark outlines. Maximum pop.

**Detailed BRD -- Track D Artsy Playful**


**Colour Role System**

Background is a bright flat solid. Illustration uses DIFFERENT bright colours with thick dark outlines. Maximum pop and contrast.

**Palettes (10)**


**Palette ID**


**Name / Canvas / Outline / Illustration / Text / Vibe**

GM-C1-D
Sunny Yellow: #FACC15 / #1E293B slate / Coral #FB7185 + Mint #A7F3D0 / #7C2D12 / Cheerful
GM-C2-D
Pink Blush: #FECDD3 / #1E293B slate / Rose #881337 + Yellow #FDE68A / #881337 / Cute
GM-C3-D
Sky Pop: #38BDF8 / #1E293B slate / White + Coral + Yellow / #0C4A6E / Fresh
GM-C4-D
Lime Fresh: #4ADE80 / #1E293B slate / Yellow #FDE68A + Coral / #14532D / Tropical
GM-C5-D
Warm Saffron: #FDE68A / #1E293B slate / Orange #FB923C + White / #92400E / Warm fun
GM-C6-D
Clean White: #F9FAFB / #1E293B slate / Coral + Mint + Sky multicolour / #1F2937 / Modern
GM-C7-D
Candy Lavender: #C084FC / #1E293B slate / Coral + Yellow + Mint / #FFFFFF / Gen-Z
GM-C8-D
Tropical Tangerine: #FB923C / #1E293B slate / Sky + Pink + Lime / #FFFFFF / Fruit salad
GM-C9-D
Bubblegum: #F472B6 / #1E293B slate / Yellow + Sky + White / #FFFFFF / Pop art
GM-C10-D
Electric Mint: #34D399 / #1E293B slate / Coral + Yellow + Purple / #064E3B / Energetic

**Finish (4 options)**


**ID**


**Name / Prompt**

FN-D1
Flat Solid: solid flat colour block, completely flat, no gradient, no texture, sticker sheet background
FN-D2
Dot Pattern: small evenly-spaced polka dots in slightly darker shade, playful dot grid
FN-D3
Confetti Scatter: scattered confetti shapes (triangles circles stars squiggles) in bright colours
FN-D4
Striped: thick diagonal stripes in two alternating bright colours, bold graphic pattern

**Illustration Rendering (4 sub-styles)**


**ID**


**Name / Prompt**

IR-D1
Flat Sticker: flat vector sticker, thick dark outline 4px, solid flat colour fills, no gradient, no shadow, WhatsApp sticker style
IR-D2
Doodle / Hand-Drawn: hand-drawn doodle, marker pen style, wobbly lines, casual sketch energy, fun imperfect, filled colours
IR-D3
3D Cartoon: 3D cartoon Pixar/claymation style, smooth rounded surfaces, soft shadows, cute chunky proportions
IR-D4
Kawaii / Chibi: kawaii chibi style, oversized head tiny body, sparkle eyes blush cheeks, ultra-cute

**Motifs (6)**


**ID**


**Name / Prompt**

MT-D1
Stars + Hearts: scattered hand-drawn stars and hearts, small floating accents with thick outlines
MT-D2
Squiggles + Swirls: playful squiggly lines, wavy doodle borders, hand-drawn swirl accents
MT-D3
Speech Bubbles: comic speech bubble shapes as decorative elements, pop art accents
MT-D4
Confetti Shapes: scattered geometric confetti — triangles circles diamonds in bright colours
MT-D5
Flower Doodles: simple hand-drawn flower doodles, five-petal daisies with smiley centres
MT-D6
Emoji Accents: small emoji-style expression faces, simple circle faces different expressions

**Customisation Presets (3)**


**Knob**


**Simple / Fun / Maximum**

Density
1-2 elements / 3-5 elements / 6+ busy
Outline
3px thin / 4px standard / 6px chunky
Accents
None / Stars + hearts / Dense confetti + squiggles
Wobble
0° clean / ±3° slight / ±8° chaotic
Pattern
None flat / Dots / Confetti + stripes
Sticker Border
None / 4px white / 6px white + hard shadow
Prompt
Simple='clean playful, 1-2 elements, thin outlines, flat, no accents, simple cheerful' | Fun='playful with star and heart accents, standard outlines, slight wobble, polka dots, moderate cheerful fun' | Maximum='maximum playful energy, dense doodle accents everywhere, chunky outlines, chaotic rotation, confetti background, no empty space, sticker border hard shadow, busy cheerful'

**Font Pool**

Display: Fraunces italic, Bagel Fat One. Devanagari: Kalam, Baloo 2. Body: Nunito Bold. Script: Caveat. Marker: Permanent Marker. Treatments: Hard drop-shadow (offset only), white sticker border 6px, speech-bubble frame. Forbidden: gradient, foil, film grain, metallic.

**References**

Alicia Souza, Gemma Correll, Apple Memoji, LINE Friends, WhatsApp Sticker Pack, Canva kids, Moonbow, Bhavesh Bhatia, Pixar flat-colour, Zomato/Swiggy illustrations, Chumbak, Nykaa packaging. Forbidden: Photorealism, cinematic, ornate, editorial, gold, film grain, muted, serif.

**Approved Archetypes**

A1 through A7, B1 through B3, C1 through C3. Any Track D palette (GM-C1-D through GM-C10-D) × any finish × any IR sub-style creates a valid template combination.
Track Library is the single source of truth. Any new archetype, vertical, or creator customisation flows through one of these 5 Track Libraries. Adding a 6th Track means authoring a complete Library row-by-row -- no partial forks allowed.

**Track E -- Soft & Warm  (gentle pastels -- hand-painted botanical -- calming morning energy -- greeting card warmth)**


**Palette family (GM-C1 example)**

GM-C1-E: Warm Cream #FFF3E0 canvas / Soft terracotta #FFAB91 thin frame lines / Warm brown #5D4037 + Peach #FFAB91 illustration (NOT cream) / #5D4037 text. Finish: watercolour wash, plain pastel, soft warm gradient, peripheral watercolour. Soft organic: background is warm and light, illustration uses earthy warm tones with gentle forms. Maximum calm.
Illustration rendering
3 sub-styles: IR-E1 Watercolour Botanical (soft painted, bleeding edges, hand-painted greeting card feel), IR-E2 Tonal Silhouette (monochromatic in slightly darker shades of background, embossed stamp quality), IR-E3 Soft Pastel Flat (clean gentle outlines, muted pastel fills, airy rounded forms, premium stationery style).
Font pairings
GM-F1-E: Sacramento + Quicksand (flowing gentle script with rounded soft body). GM-F2-E: Playfair Display + Lato (elegant serif display with clean light body). GM-F3-E: Nunito SemiBold + Quicksand (rounded soft modern with gentle body). GM-F4-E: Cormorant Garamond + Lora Light (refined thin serif with delicate body).
Motif options
4 options: MT-E1 None (completely clean), MT-E2 Faint Mandala (very faint watercolour mandala behind illustration, barely visible), MT-E3 Soft Leaf Border (delicate organic leaf vine trailing along edges), MT-E4 Dot Scatter (tiny soft dots scattered sparsely, like dewdrops).
Presets (intensity)
Minimal (Maximum Calm -- 70%+ empty, whisper-thin), Balanced (Soft Standard -- 50% empty, gentle warm), Rich (Warm Botanical -- 30% empty, richer warm, layered botanicals).
Style phrase
"soft warm gentle morning poster, calming pastel botanical aesthetic, hand-painted greeting card feel, organic soft forms, generous breathing space, serene and inviting"
Negatives
harsh, neon, loud, metallic, glitter, sparkle, ornate heavy decoration, bold thick outlines
Valid combos
A1-A7, B1-B3, C1-C3 (any Track E palette × any finish × any IR sub-style)

**Detailed BRD -- Track E Soft & Warm**


**Colour Role System**

Background is a soft warm pastel. Illustration uses slightly deeper warm tones from the same family with gentle organic forms. Frame uses thin soft-toned lines. Emphasis on breathing space and calm.

**Palettes (9)**


**Palette ID**


**Name / Canvas / Frame / Illustration / Text / Vibe**

GM-C1-E
Sunrise Gold: #FFF3E0 warm cream / #FFAB91 soft terracotta frame / Warm brown #5D4037 + Peach #FFAB91 / #5D4037 / Warm calm
GM-C2-E
Soft Dawn: #FFF0F0 blush pink / #E8A0BF rose frame / Rose #E8A0BF + Misty pink #FFE4E1 / #5D4037 / Gentle personal
GM-C3-E
Morning Sky: #E8F4FD soft sky / #90CAF9 gentle blue frame / Blue #90CAF9 + Light blue #BBDEFB / #37474F / Fresh calm
GM-C4-E
Fresh Garden: #F1F8E9 soft mint / #A5D6A7 gentle green frame / Green #A5D6A7 + Light green #C8E6C9 / #33691E / Natural serene
GM-C5-E
Sacred Saffron: #FFF8E1 soft warm amber / #FFD54F gentle gold frame / Gold #FFD54F + Pale amber #FFECB3 / #5D4037 / Warm spiritual
GM-C6-E
Minimal White: #FAFAFA pure soft white / #BDBDBD warm grey frame / Grey #BDBDBD + Light grey #F5F5F5 / #424242 / Clean minimal
GM-C7-E
Hot Pink Festive: #FFF0F5 soft blush / #F8BBD0 gentle rose frame / Rose #F8BBD0 + Pink #FCE4EC / #880E4F / Soft feminine
GM-C8-E
Royal Purple: #F3E5F5 soft lavender / #CE93D8 gentle purple frame / Lilac #CE93D8 + Lavender #E1BEE7 / #4A148C / Gentle regal
GM-C9-E
Peacock Teal: #E0F2F1 soft mint teal / #80CBC4 gentle cyan frame / Teal #80CBC4 + Mint #B2DFDB / #004D40 / Fresh calming

**Illustration Rendering Styles (3)**


**ID**


**Prompt Phrase**


**When to use**


**IR-E1 Watercolour Botanical**

"soft watercolour botanical illustration, realistic proportions, visible brushstrokes, bleeding paint edges, organic soft forms, hand-painted greeting card style, gentle and delicate"
Realistic soft botanical subjects -- flowers, leaves, garden scenes. Hand-painted card energy.

**IR-E2 Tonal Silhouette**

"tonal monochromatic illustration in slightly darker shades of the background colour family, silhouette-like clean forms, subtle embossed stamp quality, same-hue rendering, minimal and elegant"
Minimal elegant subjects -- silhouettes, simple forms. Embossed stamp energy. Maximum breathing space.

**IR-E3 Soft Pastel Flat**

"soft flat illustration with clean gentle outlines, muted pastel colour fills, rounded airy forms, light and delicate, premium stationery greeting card style"
Clean gentle icon subjects -- birds, cups, simple flowers. Premium stationery card energy.

**Background Finish Options (4)**

FN-E1 Watercolour Wash: Soft painted wash with visible colour bleeding at edges. Organic and artistic. FN-E2 Plain Pastel: Solid flat pastel colour. Clean and calm. FN-E3 Soft Warm Gradient: Very gentle gradient, lighter centre to slightly deeper warm edges, subtle ambient glow. FN-E4 Peripheral Watercolour: Very light watercolour concentrated at edges and corners only — centre stays almost white/very pale. Softer and lighter than full wash. Natural vignette that frames the text zone.

**Combinatorics**

A1 through A7, B1 through B3, C1 through C3. Any Track E palette (GM-C1-E through GM-C9-E) × any finish × any IR sub-style creates a valid template combination.

**Prompt Generator v5 Changes (April 2026)**

Bug Fixes: (1) Motif boundary enforcement separated from ornamental guard -- now activates for ALL render styles, not just IR-1, preventing motif overlap on illustrations. (2) Frame independence phrasing added -- illustration render style (e.g. 3D Glossy) no longer bleeds into border/frame appearance. (3) Layout-aware illustration positioning -- each layout (L1-L6) now maps to explicit position phrases instead of hardcoded “central”. (4) Font heading/body + text colour added to MJ and Firefly builders (previously only in Leonardo). (5) Firefly intensity truncation fixed -- now uses full description instead of splitting. (6) L6 size force-override removed -- size follows user selection, not layout assumption.
Structural Improvements: (1) All 3 prompt builders (MJ, Leonardo, Firefly) restructured with labeled sections mapping to wizard steps for traceability. (2) Prompt Audit panel added to output UI -- collapsible panel showing all 14 selections and their corresponding prompt sections. (3) Track E “Soft & Warm” added as 5th visual track with 3 render styles, 3 finishes, 4 motifs, 3 presets, 9 palettes, 4 font combos.

**Future Enhancements -- Track A (Parked)**

Items identified for future Track A expansion. Not in current scope but documented for roadmap.
1. Photorealistic Festive rendering (IR-4) -- Hybrid sub-style: painterly-photorealistic compositions with realistic flowers/landscapes + ornate gold frame overlaid. The dominant viral WhatsApp Good Morning style. Requires hybrid A1+B1 prompt engineering.
2. User photo integration -- Users upload their own photo placed inside the ornate frame with Track A treatment (gold border, motif overlay, sparkle particles).
3. Animated sparkle/shimmer for C1 -- Track A sparkle particles as looping GIF/video for WhatsApp status.
4. Regional motif sub-sets -- Warli (Maharashtra), Madhubani (Bihar), Pattachitra (Odisha/Bengal), Gond (Central India), Phulkari (Punjab), Aipan (Uttarakhand).
5. Festival-specific Track A overrides -- Diwali: Diya Row + Sparkle. Holi: Rangoli + Colourful Vector. Navratri: Temple Arch + Royal Purple.
6. Cinematic Track (parked) -- Film-still aesthetic with Kodak Portra, shallow DOF, film grain. Originally Track C. Parked for future B1 photo-focused expansion.
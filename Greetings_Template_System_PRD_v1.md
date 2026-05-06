# JioAICloud Greetings & Creation — Unified PRD v1.1

> **Single source of truth for the JioAICloud Greetings Template System.**
> Combines: Template Creation Framework v20 (engine), Birthday Category Pack v2, Suvichar Category Pack v2, Overlay Pack System v2, **V2 Expansion** (7 new category packs + bottom safe zone + adaptive B1 text colour — see Part 7).
> Implemented in `GoodMorning_Prompt_Generator_v5.html`.

---

## Document Index

### Part 1 — System Architecture
- [1. Overview & Scope](#1-overview--scope)
- [2. The Three-Layer Architecture](#2-the-three-layer-architecture)
- [3. Wizard Flow — Universal Skeleton](#3-wizard-flow--universal-skeleton)
- [4. Glossary of Terms](#4-glossary-of-terms)

### Part 2 — Framework Foundation (v20)
- [5. Archetype Families](#5-archetype-families)
  - [5.1 A1 — Text + Frame](#51-a1--text--frame)
  - [5.2 A2 — Text + Illustrations](#52-a2--text--illustrations)
  - [5.3 B1 — Full Photo Background](#53-b1--full-photo-background)
  - [5.4 C1 / C2 — Animated Elements / Animated Text](#54-c1--c2--animated-elements--animated-text)
  - [5.5 D1 — Video Background](#55-d1--video-background)
  - [5.6 E1 — AI Avatar](#56-e1--ai-avatar)
- [6. Frame Types (F1–F5 + F6)](#6-frame-types-f1f5--f6)
- [7. Overlay Treatments (O1–O5)](#7-overlay-treatments-o1o5)
- [8. Layouts (L1–L6)](#8-layouts-l1l6)
- [9. Frame × Layout Compatibility](#9-frame--layout-compatibility)
- [10. Tracks (A–E)](#10-tracks-ae)
- [11. Colour Palettes](#11-colour-palettes)
- [12. Font Pairings](#12-font-pairings)
- [13. Background Finishes](#13-background-finishes)
- [14. Illustration Render Styles](#14-illustration-render-styles)
- [15. Motif Sets — per Track](#15-motif-sets--per-track)
- [16. Customisation Presets (Intensity)](#16-customisation-presets-intensity)
- [17. Illustration & Image Library — Good Morning Default](#17-illustration--image-library--good-morning-default)
- [18. Shared Accent Items Library (ACC-01..ACC-30)](#18-shared-accent-items-library-acc-01acc-30)

### Part 3 — Base Categories
- [19. Good Morning (default category)](#19-good-morning-default-category)
- [20. Birthday Category Pack v2](#20-birthday-category-pack-v2)
  - [20.1 What this category is](#201-what-this-category-is)
  - [20.2 Wizard flow](#202-wizard-flow)
  - [20.3 Birthday border motif sets per track](#203-birthday-border-motif-sets-per-track)
  - [20.4 Birthday illustration catalogue (34 items)](#204-birthday-illustration-catalogue-34-items)
  - [20.5 Birthday sub-illustration accent library (BD-ACC)](#205-birthday-sub-illustration-accent-library-bd-acc)
  - [20.6 Prompt context — Birthday variables](#206-prompt-context--birthday-variables)
  - [20.7 Birthday layout bias](#207-birthday-layout-bias)
- [21. Suvichar / Daily Quotes Category Pack v2](#21-suvichar--daily-quotes-category-pack-v2)
  - [21.1 What this category is](#211-what-this-category-is)
  - [21.2 Wizard flow](#212-wizard-flow)
  - [21.3 Feeling system (SV-F1..SV-F5)](#213-feeling-system-sv-f1sv-f5)
  - [21.4 Feeling → Track filter](#214-feeling--track-filter)
  - [21.5 Custom text input step](#215-custom-text-input-step)
  - [21.6 Suvichar illustration catalogue (40 items)](#216-suvichar-illustration-catalogue-40-items)
  - [21.7 Suvichar sub-illustration accent library (SV-ACC)](#217-suvichar-sub-illustration-accent-library-sv-acc)
  - [21.8 Prompt context — Suvichar variables](#218-prompt-context--suvichar-variables)
  - [21.9 Suvichar layout bias](#219-suvichar-layout-bias)

### Part 4 — Overlay Pack System (v2)
- [22. Overlay Architecture & Levers](#22-overlay-architecture--levers)
- [23. What an Overlay Cannot Change](#23-what-an-overlay-cannot-change)
- [24. Overlay × Base Compatibility Matrix](#24-overlay--base-compatibility-matrix)
- [25. Overlay × Track Master Filter](#25-overlay--track-master-filter)
- [26. Firefly Prompt Budget & Templates](#26-firefly-prompt-budget--templates)
- [27. Overlay Pack Spec Template](#27-overlay-pack-spec-template)
- [28. Overlay Pack 1: Devotional](#28-overlay-pack-1-devotional)
- [29. Overlay Pack 2: Summer](#29-overlay-pack-2-summer)
- [30. Overlay Pack 3: Rain / Monsoon](#30-overlay-pack-3-rain--monsoon)
- [31. Overlay Pack 4: Cricket / IPL](#31-overlay-pack-4-cricket--ipl)

### Part 5 — Prompt Engineering & Implementation
- [32. Prompt Builder Architecture](#32-prompt-builder-architecture)
- [33. Per-Platform Prompt Formulas](#33-per-platform-prompt-formulas)
- [34. Negative Prompt Strategy](#34-negative-prompt-strategy)
- [35. State Model (STATE)](#35-state-model-state)
- [36. Reset Cascade Rules](#36-reset-cascade-rules)
- [37. Filtering Pipelines (track / illus / motif / frame)](#37-filtering-pipelines-track--illus--motif--frame)
- [38. Audit Panel & Traceability](#38-audit-panel--traceability)

### Part 6 — Extending the System
- [39. Decision Framework — Category vs Overlay](#39-decision-framework--category-vs-overlay)
- [40. Adding a New Base Category](#40-adding-a-new-base-category)
- [41. Adding a New Overlay Pack](#41-adding-a-new-overlay-pack)
- [42. Future Enhancements & Open Items](#42-future-enhancements--open-items)

### Part 7 — V2 Expansion
- [43. Bottom Safe Zone (Personalization Band)](#43-bottom-safe-zone-personalization-band)
- [44. Adaptive B1 Hero Text Colour](#44-adaptive-b1-hero-text-colour)
- [45. Category Pack: Rath Yatra](#45-category-pack-rath-yatra)
- [46. Category Pack: Vat Savitri](#46-category-pack-vat-savitri)
- [47. Category Pack: Father's Day](#47-category-pack-fathers-day)
- [48. Category Pack: Devotional — Shivji](#48-category-pack-devotional--shivji)
- [49. Category Pack: Devotional — Ganeshji](#49-category-pack-devotional--ganeshji)
- [50. Category Pack: Devotional — Jesus](#50-category-pack-devotional--jesus)
- [51. Category Pack: Devotional — Islamic](#51-category-pack-devotional--islamic)
- [52. Master tables — V2 expansion (10 categories total)](#52-master-tables--v2-expansion-10-categories-total)
- [53. Implementation summary — V2 expansion](#53-implementation-summary--v2-expansion)

### Appendices
- [Appendix A — Master Cross-Reference](#appendix-a--master-cross-reference)
- [Appendix B — Illustration ID Conventions](#appendix-b--illustration-id-conventions)
- [Appendix C — Change Log](#appendix-c--change-log)

---

# Part 1 — System Architecture

## 1. Overview & Scope

JioAICloud Greetings is a wizard-driven template generator that produces AI-image prompts for greeting posters across major platforms (Adobe Firefly with-text and no-text, Midjourney, Leonardo.AI, Google Gemini). The user walks through a guided sequence of choices (category, archetype, layout, track, palette, font, finish, illustration, motif, intensity), and the system assembles platform-specific prompts that satisfy each provider's character limits and stylistic conventions.

### What IS in scope (v1)

1. **All 3 active archetype families** — A1 (Illustrated background with frame), A2 (Illustrated, no dominant frame), B1 (Full photo background) — fully wizarded with step-by-step BRD.
2. **5 aesthetic tracks** — A Shiny Maximal, B Modern Desi, C Minimalist Classy, D Artsy Playful, E Soft & Warm — each with palettes, font pools, render styles, finishes, motifs, intensity presets, and (for B1) photography aesthetics.
3. **3 base categories shipped** — Good Morning (default), Birthday (v2), Suvichar / Daily Quotes (v2).
4. **4 overlay packs** — Devotional, Summer, Rain / Monsoon, Cricket / IPL — each composing on top of one or more base categories.
5. **Working prompt-generator prototype** — Single-file HTML (`GoodMorning_Prompt_Generator_v5.html`) that walks through the full wizard, generates per-platform prompts, includes a QA audit panel for every output, and exports an evaluation TSV/HTML clipboard format.
6. **Layout × Overlay compatibility system** — 6 layouts × 5 B1 overlays with Best / Works / With Care badges, frame decoration levels (A1), density auto-calculation (A2), and intensity-driven density.
7. **Shared illustration library** — 49 GM items, 30 SV-native items, 30 BD-native items, plus 30 ACC-* accent props (extended with SV-ACC-* and BD-ACC-* for category-appropriate sub-elements).

### What is NOT in scope yet (deferred)

1. **Native text rendering on posters** — AI image generators render text unreliably. For v1, hero text is composited post-generation via a layering layer; only Firefly with-text uses native text rendering as a best-effort.
2. **Multi-illustration in A1** — A2 supports curated sub-illustrations (main + 0–2 accent props with auto-calculated density). A1 is single-illustration only; multi-select extension parked for a later release.
3. **Palette / illustration expansion** — Current palette set per track and 49-item GM illustration library are starting sets; both will expand based on user-testing feedback and designer input. This is a P0 priority before public launch.
4. **Prompt refinement at scale** — Templates are functional but require iterative tuning across Midjourney / Leonardo / Firefly through real-image testing.
5. **Custom palette input + uploaded illustrations** — Future complexity; only curated options today.
6. **Remaining archetypes** — C1 (Animated Elements), C2 (Animated Text), D1 (Video Background), E1 (AI Avatar) are defined at the archetype level but lack detailed prompt-generator step BRDs and prototype implementations.
7. **End-to-end automation pipeline** — Current prototype generates prompts for manual copy-paste into AI platforms. API-based generation, automatic compositing (text + image), and batch production workflows remain future work.
8. **Adobe-stock background integration** — Not yet wired into the picker.

---

## 2. The Three-Layer Architecture

The system has three distinct layers. Each layer owns a specific set of decisions and never reaches into another layer's territory.

| Layer | What it is | What it owns | Examples |
|-------|-----------|--------------|----------|
| **Framework** | The engine | Archetypes, tracks, layouts, palettes, fonts, render styles, background finishes, prompt builder architecture, wizard flow, density calc, intensity | Template Creation Framework v20 |
| **Base Category** | The content type — defines the hero text | Hero text (e.g. "Good Morning", "Happy Birthday", user-entered quote), full illustration catalogue, full motif set per track, atmosphere & mood keywords, negative terms | Good Morning, Birthday, Suvichar (and future: Diwali, Eid, Holi, Rath Yatra) |
| **Overlay Pack** | A flavour / context modifier — no hero text of its own | Track filtering, illustration additions & restrictions, motif swaps & additions, frame restrictions or special unlocks, atmosphere keyword additions, negative term additions | Devotional, Summer, Rain / Monsoon, Cricket / IPL |

**Composition rule:** An **Occasion** that the user picks = Base Category + (optional) Overlay Pack.

**Selection timing:** Overlay is picked at the start, on the same wizard step as the base category. The overlay's track filter, illustration restrictions, and motif swaps are all applied before any downstream wizard step is rendered.

| User sees | Base Category | Overlay Pack |
|-----------|---------------|--------------|
| Good Morning | Good Morning | — |
| Devotional Good Morning | Good Morning | Devotional |
| Cricket Good Morning | Good Morning | Cricket / IPL |
| Rainy Good Morning | Good Morning | Rain / Monsoon |
| Summer Birthday | Birthday | Summer |
| Birthday | Birthday | — |
| Cricket Birthday | Birthday | Cricket / IPL |
| Suvichar | Suvichar | — |
| Devotional Suvichar | Suvichar | Devotional |
| Rainy Suvichar | Suvichar | Rain / Monsoon |
| Summer Suvichar | Suvichar | Summer |

---

## 3. Wizard Flow — Universal Skeleton

The wizard flow varies by archetype and base category, but follows this canonical skeleton:

```
Step 1: Template            (Category → Overlay → Archetype)
Step 2: Style               (A1: Frame F1–F6, A2: Density auto-calc placeholder, B1: Text+Overlay merged)
Step 3: Layout              (L1–L6, filtered by Frame for A1; auto for B1)
Step 4: Feeling             (Suvichar only — SV-F1..SV-F5; runs before Track)
Step 5: Track               (A–E, filtered by Feeling and Overlay)
Step 6: Colour & Finish     (Palette + Background Finish in one step)
Step 7: Visual              (Illustration → optional sub-accents → Size → Render Style → Frame Deco → Motif)
        OR Scene + Mood     (B1: Scene Elements + Mood + Camera Intensity)
Step 8: Intensity           (Customisation preset — Basic / Medium / Complex per track)
Step 9: Custom Text         (Suvichar only — user-entered quote)
```

### Step-by-step variation per archetype × category

| Step | A1 GM | A2 GM | B1 GM | A1 BD | A2 BD | B1 BD | A1 SV | A2 SV | B1 SV |
|------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
| 1 | Template | Template | Template | Template | Template | Template | Template | Template | Template |
| 2 | Frame | (skip) | Text+Overlay | Frame | (skip) | Text+Overlay | Feeling | Feeling | Feeling |
| 3 | Layout | Layout | Layout | Layout | Layout | Layout | Frame | Layout | Text+Overlay |
| 4 | Track | Track | Track | Track | Track | Track | Layout | Track | Track |
| 5 | Colour+Finish | Colour+Finish | Scene Elements | Colour+Finish | Colour+Finish | Scene Elements | Track | Colour+Finish | Scene Elements |
| 6 | Visual | Visual | Mood | Visual | Visual | Mood | Colour+Finish | Visual | Mood |
| 7 | Intensity | Intensity | Intensity | Intensity | Intensity | Intensity | Visual | Intensity | Intensity |
| 8 | — | — | — | — | — | — | Intensity | Custom Text | Custom Text |
| 9 | — | — | — | — | — | — | Custom Text | — | — |

---

## 4. Glossary of Terms

| Term | Definition |
|------|------------|
| **Archetype** | A structural template family — A1 (frame + text), A2 (illustration + text, no dominant frame), B1 (full photo bg). Locked at Step 1. |
| **Track** | An aesthetic lane — A Shiny Maximal, B Modern Desi, C Minimalist Classy, D Artsy Playful, E Soft & Warm. Locks palette, fonts, render style, motifs, intensity options. |
| **Layout** | Where text and visual sit on the canvas — L1 Top, L2 Overlay/Centre, L3 Left, L4 Right, L5 Bottom, L6 Centre. |
| **Frame Type** | A1-only structural decoration — F1 Full Perimeter, F2 Dual Band, F3 Single Band, F4 Corner Accents, F5 Arch/Canopy, F6 Temple Arch (Devotional unlock). |
| **Overlay Treatment** | B1-only photo-darkening pattern — O1 Full Dark, O2 Gradient Top-Heavy, O3 Gradient Bottom-Heavy, O4 Vignette, O5 Caption Bar. |
| **Frame Decoration Level** | A1-only: how ornate the frame border itself is — Plain / Simple / Detailed. |
| **Illustration Size** | Small Accent (<15%) / Medium (30–40%) / Large (50%+ of canvas). |
| **Motif Set** | Per-track decorative pattern vocabulary used as A1 frame motifs and A2 accent fills. |
| **Background Finish** | Per-track surface treatment — flat, gradient, sparkle, foil, paper grain, watercolour wash, etc. |
| **Render Style** | Per-track illustration rendering medium — ornamental vector, watercolour, ink + wash, flat sticker, doodle, 3D cartoon, etc. |
| **Intensity Preset** | Per-track 3-tier control over decoration density — Basic / Medium / Complex (Track A) etc. |
| **Density (A2)** | Auto-calculated from sub-illustration count: 0 = Light, 1 = Medium, 2 = Dense. |
| **Feeling (Suvichar)** | Emotional tone selector — SV-F1 Rise & Shine / SV-F2 Still Waters / SV-F3 Bittersweet / SV-F4 Everyday Calm / SV-F5 Fire & Drive. Hard-filters the track list. |
| **Hero Text** | The primary greeting text rendered onto the poster. "Good Morning" / "Happy Birthday" / user-typed Suvichar. Owned by base category. |
| **ACCENT_ITEMS** | Shared accent props library (ACC-01..ACC-30) used as A2 sub-elements and B1 supporting props. Extended with SV-ACC-01..06 and BD-ACC-01..06 for category-appropriate accents. |
| **Overlay Pack** | A composable flavour layer (Devotional / Summer / Rain / Cricket) that filters tracks, swaps motifs, adds illustrations, restricts base illustrations, modifies frames, and injects atmosphere/mood/negatives into prompts. Owns **no hero text**. |
| **Occasion** | A user-facing pick = Base Category + (optional) Overlay. Picked at Step 1. |
| **trunc()** | Helper that clips a string at a max char count, preferring a clean break at the last comma. Used by Firefly builders to enforce ≤950 char cap per slot. |
| **stripHex()** | Helper that removes `(#XXXXXX)` hex annotations from palette descriptions to save chars in Firefly prompts. |

---

# Part 2 — Framework Foundation (v20)

## 5. Archetype Families

Seven archetypes are defined at the architecture level; three are fully implemented in v1 (A1, A2, B1).

| Code | Name | Defining Characteristic | Custom Step 1 |
|------|------|-------------------------|---------------|
| **A1** | Text + Frame | A border / frame element is the defining visual. Text and optional illustration sit inside the frame. | F1–F6 Frame Type |
| **A2** | Text + Illustrations | Illustrations are the primary visual. No dominant frame. | (Density auto-calculated from sub-element count) |
| **B1** | Full Photo Background | A photograph fills the entire background. Text overlaid via merged Text+Overlay step. | O1–O5 Overlay Type (auto-determined from text position) |
| C1 | Animated Elements | On-canvas elements animate (particles, loops, reveals). Phase 2. | Animation Style |
| C2 | Animated Text | The text itself animates. Background is minimal. Phase 2. | Text Animation Style |
| D1 | Video Background | A looping video clip forms the background. Text overlaid. Phase 2. | Video Category (4 types) |
| E1 | AI Avatar | An AI-generated human figure is the primary visual. Phase 2. | Rendering Style (Realistic / Illustrated) |

### 5.1 A1 — Text + Frame

A visible frame is the defining device. Text is primary; illustration is optional. **Three distinct asset types** must be kept separate in prompts:

1. **BACKGROUND** = solid colour or gradient fill behind the whole canvas. No AI generation needed for the fill itself; the AI generates the *full poster image*, but the BG is described separately.
2. **FRAME ELEMENTS** = the decorative motifs on the border frame itself (florals, paisleys, mandalas). Set via Frame Decoration Level in Step 5.
3. **ILLUSTRATION** = the standalone flat 2D asset placed inside the canvas (chai cup, lotus, sunshine, bird etc.). Chosen from the illustration library and referenced as a separate visual element. **Never render text inside any AI-generated asset**.

| Step | Name | Options | Notes |
|------|------|---------|-------|
| 1 | Frame Type | F1 Full Perimeter / F2 Dual Band / F3 Single Band / F4 Corner Accents / F5 Arch+Canopy / F6 Temple Arch (Devotional only) | Frame choice filters layouts at Step 2. |
| 2 | Layout | L1 Text Top / L2 Overlay / L3 Text Left / L4 Text Right / L5 Text Bottom / L6 Text Centre (frame) | Filtered by frame choice. |
| 3 | Track | A / B / C / D / E | Hard fork — locks palette, font, render style, motif vocabulary, finish, intensity for all downstream steps. Track filtered by feeling (Suvichar) and overlay (any base). |
| 4 | Colour | BG + Text + Frame/Accent colours (paired) | Min 4.5:1 contrast. |
| 5 | Font | Serif / Sans / Script / Display | One primary font, weight per line hierarchy. |
| 6 | Illustration | Pick from category illustration pack + Frame Decoration Level + Density + Size | Plain / Simple / Detailed frame deco; Small / Medium / Large size. |
| 7 | Mood Check | Qualitative pass | Theme fit, readability, balance, share-ability. |

### 5.2 A2 — Text + Illustrations

Illustrations are the primary visual. No dominant frame.

| Step | Name | Options | Notes |
|------|------|---------|-------|
| 1 | Layout | L1 / L2 / L3 / L4 / L5 / L6 | All available — no frame to filter. |
| 2 | Track | A / B / C / D / E | Same lock-in behaviour as A1. |
| 3 | Colour | BG + Text + Illus Colour Mode (Full / Duotone / Mono) | Cohesive, not competing. |
| 4 | Font | Serif / Sans / Script / Display | Match font character to illustration style. |
| 5 | Illustration Pack | Choose pack → main illustration → 0–2 sub-accents | **Density auto-calculated**: 0 = Light, 1 = Medium, 2 = Dense. |
| 6 | Mood Check | Qualitative pass | Star illus, legibility, density-feel, share-ability. |

**v5.1 update:** The original A2 illustration density step has been **removed**. Density is now auto-derived from the count of selected accent sub-illustrations (drawn from the per-item curated list in `A2_SUB_ELEMENTS` / `SV_A2_SUB_ELEMENTS` / `BD_A2_SUB_ELEMENTS`).

### 5.3 B1 — Full Photo Background

A photograph fills the entire background canvas. Overlay treatment makes text readable.

| Step | Name | Options | Notes |
|------|------|---------|-------|
| 1 | Template Selection | B1 (locks photoreal pipeline) | No frames, no render styles, no background finishes, no motifs. |
| 2 | Text Placement & Overlay (merged) | L1–L6 + Light / Darker overlay strength | Overlay direction auto-determined from text position. |
| 3 | Track | A → HDR Saturated, B → Editorial Muted, C → Desaturated Minimal, D → Bright Lifestyle, E → Soft Dreamy | Track names same as A1/A2; meaning is photographic aesthetic. |
| 4 | Scene Elements | 1 main + 0–2 supporting accents | Main = hero subject, foreground. Supporting = background props. From category catalogue + ACCENT_ITEMS library. |
| 5 | Mood (merged Lighting + Colour) | MD-1..MD-6 | Bundles physical lighting and colour processing — Golden Warm / Misty Soft / Bright & Vivid / Dramatic Rays / Vintage Film / Soft Pastel. Track-specific best-fits flagged with ⭐. |
| 6 | Intensity (Camera Distance & Detail) | Basic Wide / Medium Balanced / Complex Close & Immersive | Controls focal length, framing, depth of field. |
| 7 | Font & Text | Same as A1/A2 — Hindi/English/Hinglish, 4 typography styles. White text on overlay. | Text colour always white for B1. |

**Steps NOT shown for B1:** Colour Palette (photo IS the background), Background Finish, Illustration Render Style (always photoreal), Motif Patterns, Illustration Size Picker (intensity controls camera distance instead), Frame Decoration Level.

**B1 prompt characteristics:** Negative prompts strongly block illustration / cartoon / vector / frame / border. Colour temperature per mood is injected (Kelvin values). DSLR quality anchoring, natural depth of field, overlay strength expressed in prompt language.

### 5.4 C1 / C2 — Animated Elements / Animated Text

**C1 — Animated Elements** (Phase 2). Static template with animated elements layered on top. Three animation styles:
- **Particle** — multiple small elements moving independently (20–50 petals drifting, snowflakes, confetti).
- **Loop** — a single larger element with a repeating animation cycle (diya flame flickering, sun rotating).
- **Reveal** — elements animate IN on load (fade up, burst, slide in) then hold static.

**C2 — Animated Text** (Phase 2). The text itself animates — Typewriter / Fade-In / Slide / Bounce-Pop / Glow-Shimmer. Background intentionally minimal.

### 5.5 D1 — Video Background

Phase 2. A looping video clip forms the background. Four MECE video categories:

- **Calm & Natural** — river flow, forest breeze, sunrise / sunset, clouds, sky timelapse.
- **Sacred & Devotional** — temple lamp, incense smoke, flower offerings, river ghats, bells.
- **Celebratory** — confetti, fireworks, sparklers, balloon release.
- **Abstract Motion** — bokeh, light rays, colour gradient morphs, particle fields.

### 5.6 E1 — AI Avatar

Phase 2. An AI-generated human figure is the primary visual. Two rendering styles: Realistic (photorealistic, formal, news-adjacent) or Illustrated / Cartoon (stylised, friendly, inclusive). Customisation: skin tone, outfit (contemporary / business / traditional-cultural), expression (neutral / smiling / namaste / celebratory), accessories (tilak, bindi, glasses).

---

## 6. Frame Types (F1–F5 + F6)

A1-only structural decoration. F1–F5 are framework defaults; F6 is unlocked by the Devotional overlay.

### F1 — Full Perimeter
- **Principle:** Frame runs along all 4 edges — complete border enclosing the canvas.
- **Zones blocked:** Header, Footer, Left edge, Right edge.
- **Text rules:** Text stays inside inner content area. Cannot break frame boundary.
- **Illus rules:** Illustration confined to inner zone. No edge bleed.
- **Eliminates:** L3/L4 side columns tightened. L1/L5 lose edge space. L2 works cleanest.
- **Best for:** A1 — formal, ornate, devotional/traditional festive.

### F2 — Dual Band
- **Principle:** Straight horizontal bands at header and footer only — sides fully open.
- **Zones blocked:** Header row + Footer row.
- **Text rules:** Text in Upper / Centre / Lower rows only. Cannot overlap bands.
- **Illus rules:** Centre rows fully available. Full horizontal width.
- **Eliminates:** L1 loses top illustration space. L5 loses footer anchor.
- **Best for:** A1 — magazine-style, banner cards, clean structured.

### F3 — Single Band
- **Principle:** One edge only — footer band or header bar (not both).
- **Zones blocked:** Header OR Footer row only.
- **Text rules:** One end anchored; rest of canvas fully open.
- **Illus rules:** Maximum freedom — 4 of 5 rows fully available.
- **Eliminates:** Minimal — all 5 layouts compatible.
- **Best for:** A1 — understated, minimal, modern.

### F4 — Corner Accents
- **Principle:** Small decorative patches at corners only.
- **Zones blocked:** Corner patches only (4 corners).
- **Text rules:** Text anywhere. Avoid placing primary text over corner patch.
- **Illus rules:** All zones fully open.
- **Eliminates:** Nothing — all 5 layouts fully compatible.
- **Best for:** A1 / A2 — elegant, versatile; pairs with every layout.

### F5 — Arch / Canopy
- **Principle:** Curved arch overhead — occupies header zone and upper side patches.
- **Zones blocked:** Header row + partial Upper-Left and Upper-Right.
- **Text rules:** Primary text at Upper-Centre or Centre row. Avoid Header for text.
- **Illus rules:** Illustration in Lower / Footer. Side columns open from Centre down.
- **Eliminates:** L1 (Text Top) constrained; L5 pairs perfectly.
- **Best for:** A1 — devotional, ceremonial (deity arch, lotus canopy, Diwali torans).

### F6 — Temple Arch *(Devotional overlay unlock)*
- **Principle:** Curved temple gopuram / mandir arch silhouette as the top frame element. Arch curves from top-left to top-right corners, descending to ~20% canvas height at the sides. Bottom edge is straight (no frame). Interior fully open for text + illustration.
- **Zones blocked:** Header + partial Upper sides (similar to F5 but with explicit temple architectural language).
- **Visual variation by Frame Decoration Level:** Plain = thin outline only; Simple = outline + small kalash at apex; Detailed = ornate carved arch with miniature temple motifs.
- **Layout compatibility:** Best — L5 (text below arch), L2 (overlay under arch). Works — L1 (text inside upper arch curve). Avoid — L3, L4 (arch doesn't pair with side-text layouts — creates visual imbalance).
- **Activation:** F6 only appears in the Step-2 frame picker when the Devotional overlay is active.

---

## 7. Overlay Treatments (O1–O5)

B1 / D1 only — defines how the photograph is darkened so text remains readable.

| Code | Name | Description | Text Placement | Best For |
|------|------|-------------|----------------|----------|
| **O1** | Full Dark Overlay | Uniform semi-opaque dark layer (~40–60% opacity) across entire canvas. | Text anywhere — uniform contrast. | Night/moon themes, serious tone. Pairs with L2. |
| **O2** | Gradient Top-Heavy | Dark gradient from top, fades to transparent by centre. Photo visible in lower half. | Text at Header + Upper. | Sky / sunrise photos, morning themes. Pairs with L1. |
| **O3** | Gradient Bottom-Heavy | Dark gradient from footer, fades to transparent near centre. Photo clear in upper half. | Text at Lower + Footer. | Quote cards, shayari, evening. Pairs with L5. |
| **O4** | Vignette | Darkened edges, bright centre window. Photo visible in middle. | Text in Centre row — natural focal point. | Portrait photos, romantic themes. Pairs with L2. |
| **O5** | Caption Bar | Semi-opaque solid bar at header or footer. Rest of canvas is full photo. | Text inside caption bar. | Photo-first, minimal text. Pairs with L1 or L5. |

In v5 of the prototype, the B1 wizard merges Layout + Overlay into one step. The user picks a text position (L1–L6); the overlay direction is auto-determined from the text position, plus a single Light vs Darker strength choice.

---

## 8. Layouts (L1–L6)

Six positional layouts — define WHERE text lives and WHERE illustration lives. Stylistic choices (density, opacity, scatter) are decided at the Visual step (Step 6/7).

### L1 — Text Top
- **Description:** Text anchored in upper portion. Illustration fills lower two-thirds.
- **Text zone:** Header + Upper rows.
- **Illus zone:** Centre + Lower + Footer rows.
- **Constraint:** F5 (Arch) conflicts with header text — shift to Upper row when F5 is selected.
- **Frame compat:** F0 / F3 / F4 fully. F1 / F2 / F5 partially.

### L2 — Overlay / Text Centre
- **Description:** Illustration fills entire canvas. Text sits in centre with contrast treatment.
- **Text zone:** Centre row (primary). Upper or Lower as secondary.
- **Illus zone:** All 5 rows — full canvas bleed.
- **Constraint:** Text must have sufficient contrast. Use bold font or local opacity bar.
- **Frame compat:** All frames — universally compatible. Primary for B1 and D1.

### L3 — Text Left
- **Description:** Left column holds text. Right two columns hold illustration.
- **Text zone:** Left column across all rows.
- **Illus zone:** Centre + Right columns across all rows.
- **Constraint:** F1 tightens left column. F4 works perfectly.
- **Frame compat:** F0 / F2 / F3 / F4 / F5 fully. F1 partially.

### L4 — Text Right
- **Description:** Right column holds text. Left two columns hold illustration.
- **Text zone:** Right column across all rows.
- **Illus zone:** Left + Centre columns across all rows.
- **Constraint:** Mirror of L3. Same frame constraints apply.
- **Frame compat:** F0 / F2 / F3 / F4 / F5 fully. F1 partially.

### L5 — Text Bottom
- **Description:** Illustration fills upper two-thirds. Text anchored at lower portion.
- **Text zone:** Lower + Footer rows.
- **Illus zone:** Header + Upper + Centre rows.
- **Constraint:** F5 (Arch) enhances this layout — arch top + text bottom = ceremonial frame. F2 reduces footer space.
- **Frame compat:** F0 / F3 / F4 / F5 fully. F1 / F2 partially.

### L6 — Text Centre (frame)
- **Description:** Frame defines all 4 edges. Background / gradient fills canvas. Small illustration anchored at top or bottom inside frame. Text occupies the central 60% zone.
- **Text zone:** Central 60% as the dominant element.
- **Illus zone:** Small accent at corner only — does not overlap central text.
- **Constraint:** Best with F1, F2, F4. Not recommended with F5 (arch restricts centre zone).
- **Frame compat:** F1 / F2 / F4 best. F3 caution. F5 caution.

**A1 / A2 hide L2:** L2 (Text Overlay) is reserved for B1 in v5 — the prototype filters it out for A1/A2 because illustration-on-illustration text overlay competes too much without a photographic background.

---

## 9. Frame × Layout Compatibility

Quick-filter for Step 3 — determines which layouts are available given the frame chosen at Step 2.

| Frame ↓ / Layout → | L1 Top | L2 Overlay | L3 Left | L4 Right | L5 Bottom | L6 Centre |
|--------------------|:------:|:----------:|:-------:|:--------:|:---------:|:---------:|
| F1 Full Perimeter | ok | ok | ok | ok | ok | **best** |
| F2 Dual Band | ok | **best** | **best** | **best** | ok | ok |
| F3 Single Band | **best** | ok | ok | ok | **best** | caution |
| F4 Corner Accents | **best** | **best** | **best** | **best** | **best** | **best** |
| F5 Arch / Canopy | caution | ok | ok | ok | **best** | caution |
| F6 Temple Arch *(devotional)* | caution | **best** | avoid | avoid | **best** | caution |

A2 density × layout compatibility:

| Density ↓ / Layout → | L1 | L2 | L3 | L4 | L5 | L6 |
|----------------------|:--:|:--:|:--:|:--:|:--:|:--:|
| Light (0 sub-elements) | best | best | best | best | best | ok |
| Medium (1 sub-element) | best | best | best | best | best | ok |
| Dense (2 sub-elements) | ok | best | ok | ok | ok | caution |

B1 overlay × layout:

| Overlay ↓ / Layout → | L1 | L2 | L3 | L4 | L5 | L6 |
|----------------------|:--:|:--:|:--:|:--:|:--:|:--:|
| O1 Full Dark | best | best | ok | ok | best | ok |
| O2 Top-Heavy | best | ok | ok | ok | caution | ok |
| O3 Bottom-Heavy | caution | ok | ok | ok | best | ok |
| O4 Vignette | ok | best | caution | caution | ok | best |
| O5 Caption Bar | ok | ok | ok | ok | best | ok |

---

## 10. Tracks (A–E)

Hard fork at Step 3 (or Step 5 for Suvichar). Each track locks palette, fonts, render style, finishes, motifs, intensity options.

| Track | Name | Tagline | Vibe | Best Audience |
|-------|------|---------|------|---------------|
| **A** | Shiny Maximal | Jazzy desi, festive, loud on purpose | Wedding-card energy meets Diwali poster. 3D extruded sticker, glossy shimmer, clustered ornate motifs, gold + saturated palette. | Tier 2–3, 35+, festive WhatsApp forwarders |
| **B** | Modern Desi | Muted earthy, contemporary editorial | Anokhi-meets-Insta. Two sub-modes: B1 Painterly (watercolour + linework + block-print) and B2 Lifestyle Photo (golden-hour home). | Urban, 25–40, design-aware |
| **C** | Minimalist Classy | Maximum restraint, tonal elegance, single element | Magazine / film-poster. Real photography, low-key dramatic light, editorial type, geometric or metallic motifs only (no florals). | Premium, 28–45 |
| **D** | Artsy Playful | Flat bright, sticker / doodle, cheerful | Cartoon sticker-pack energy. Flat vector / sticker outline / doodle / 3D cartoon. | 18–30, gen-Z |
| **E** | Soft & Warm | Gentle pastels, warm botanicals, calming | Soft hand-painted greeting card; watercolour botanical aesthetic; organic soft forms; generous breathing space. | 25–55, soft / feminine receivers |

**Track-D constraint:** Hard-blocked for Devotional / Political / Sympathy categories — playful doodle treatment of sacred symbols feels disrespectful (enforced by the Devotional overlay's track filter).

**B1 photographic interpretation:**
- Track A → HDR Saturated (viral WhatsApp-forward energy, oversaturated, dramatic).
- Track B → Editorial Muted (Kodak Portra 400 film look, muted earthy).
- Track C → Desaturated Minimal (high contrast, low saturation, architectural).
- Track D → Bright Lifestyle (poppy blog photography, bright, airy, slightly overexposed).
- Track E → Soft Dreamy (pastel bokeh, soft focus edges, romantic warmth).

---

## 11. Colour Palettes

Palettes are organised into named families (e.g. GM-C1 Sunrise Gold) with per-track variants (GM-C1-A through GM-C1-E). Each variant is a visibly different "world" sharing a lineage rather than a minor tweak — Track A interprets GM-C1 as neon-marigold festive foil; Track C interprets it as pale-yellow film wash; etc.

### Good Morning palette family (6 base palettes)

| ID | Palette Name | BG | Text | Accent | Best For / Vibe |
|----|--------------|----|------|--------|-----------------|
| GM-C1 | Sunrise Gold | #F59E0B | #7C2D12 | #F97316 | Warm, energetic, celebratory — festive Good Morning |
| GM-C2 | Soft Dawn | #FDE8D8 | #78350F | #FCA5A5 | Gentle, personal, warm — family / relationship |
| GM-C3 | Morning Sky | #BFDBFE | #1E3A5F | #FFFFFF | Fresh, calm, uplifting — motivational / nature |
| GM-C4 | Fresh Garden | #D1FAE5 | #064E3B | #FEF08A | Natural, peaceful, earthy — wellness / nature |
| GM-C5 | Sacred Saffron | #FEF3C7 | #7F1D1D | #D97706 | Devotional, traditional — spiritual GM |
| GM-C6 | Minimal White | #F9FAFB | #1F2937 | #F87171 | Clean, modern, versatile — works across all archetypes |

### Track A — extended exclusive palettes

Track A unlocks 3 additional palettes beyond the GM-C1..C6 family:

| ID | Palette Name | BG | Text | Accent | Secondary | Vibe |
|----|--------------|----|------|--------|-----------|------|
| GM-C7-A | Hot Pink Festive | #EC4899 | #FFFFFF | #FBBF24 (gold) | #BE185D (magenta) | Bollywood glamour, shaadi pink |
| GM-C8-A | Royal Purple | #7C3AED | #FEF3C7 (cream) | #FFD700 (gold) | #5B21B6 | Regal, Dussehra, Navratri, premium festive |
| GM-C9-A | Peacock Teal | #0891B2 | #FFFFFF | #FFD700 (gold) | #155E75 | Peacock motif, Krishna, blue-gold |

### Per-Track palette count

| Track | Palette Count | Notes |
|-------|:-------------:|-------|
| A Shiny Maximal | 9 (GM-C1-A..C9-A) | Includes 3 exclusive — Hot Pink, Royal Purple, Peacock Teal |
| B Modern Desi | 8 | Muted earthy variants of GM-C1..C6 + 2 editorial extras |
| C Minimalist Classy | 8 | Pale, restrained variants — film-grade tones |
| D Artsy Playful | 10 | Flat saturated brights including extra cheerful options |
| E Soft & Warm | 9 | Pastel watercolour-friendly variants |

### Colour-role assignment rule (Good Morning category)

The background colour stays vivid and lively (category design decision). BUT the illustration subject, frame/motif, and text MUST use contrasting palette colours — never the same hue as the background. This creates visual hierarchy: vivid background → distinct frame → standout illustration → readable text.

| Zone | Role and Rule |
|------|---------------|
| **Canvas Fill** | Dominant background surface (60% of canvas). Uses palette BG colour. Stays vivid. |
| **Frame / Motif** | Decorative frame + motif elements. Must be VISUALLY DISTINCT from canvas fill. Default: gold (#FFD700) on most backgrounds. On gold/saffron backgrounds, use deep maroon or brown. |
| **Illustration Primary** | Main colour of illustration subject. Must CONTRAST against canvas fill. NEVER the same hue as the background. E.g., on orange background, chai cup is rendered in maroon + cream + gold, NOT orange. |
| **Illustration Accent** | Secondary details on illustration. Complements illustration primary. Can use darker / lighter variant. |
| **Text** | Headline + body. Must pass 4.5:1 contrast ratio against canvas fill. Typically the darkest palette colour. |
| **Sparkle / Glow** | Particle highlights. Always white (#FFFFFF) regardless of palette — needs to pop everywhere. |
| **Shadow** | Drop shadows. Always the darkest palette colour at reduced opacity. |

### Per-palette role maps (sample — full set in code)

**GM-C1-A Sunrise Gold (Track A):**
- Canvas Fill #FF8C1A (Neon Marigold) → "warm vivid orange-amber background"
- Frame / Motif #FFD700 / #DAA520 → "golden metallic frame, antique gold motifs"
- Illustration #8B0000 / #FFF8E7 → "rendered in deep maroon, cream, white — NOT orange"
- Illus Accent #B8001F / #FFD700 → "red and gold detail accents"
- Text #8B0000 or #FFFFFF → "dark maroon or white text on orange"

**GM-C3-A Morning Sky (Track A interpretation):**
- Canvas Fill #3B82F6 (Vivid Blue) → "vivid sky blue background"
- Frame / Motif #FFD700 / #FBBF24 → "rich gold frame on blue — royal blue-gold"
- Illustration #FFFFFF / #FBBF24 → "in white, gold, warm tones — NOT blue"
- Text #FFFFFF or #FBBF24 → "white or gold text on blue"

The remaining per-palette role maps for GM-C1-B/C/D/E, GM-C2-* through GM-C9-A are maintained in the design-system repo and consumed by the prompt builder via `getPalette().tracks[STATE.track].roles`.

---

## 12. Font Pairings

Four base font pairings cover the full emotional range of greetings. Each pairing specifies a heading font (for the main greeting) and a body font (for sub-text or quote). All fonts available on Google Fonts and Adobe Fonts.

| ID | Pairing Name | Heading Font | Body Font | Feel | Best Palettes |
|----|--------------|--------------|-----------|------|---------------|
| GM-F1 | Warm Script | Kalam / Dancing Script | Nunito / Poppins Light | Personal, warm, handwritten | GM-C1, GM-C2, GM-C5 |
| GM-F2 | Bold Display | Poppins 700 / Playfair Bold | Poppins Regular | Energetic, confident, impactful | GM-C1, GM-C3, GM-C6 |
| GM-F3 | Clean Modern | Poppins SemiBold | Poppins Regular | Contemporary, clean, versatile | All palettes |
| GM-F4 | Elegant Serif | Libre Baskerville / Lora Bold | Source Serif / Lora | Traditional, sophisticated, literary | GM-C4, GM-C5 |

### Per-Track font pool

| Track | Font Pool |
|-------|-----------|
| **A Shiny Maximal** | Display: Cinzel Decorative, Samarkan, Ranchers, Alfa Slab One, Yatra One, Rozha One. Script: Great Vibes, Allura, Sacramento, Parisienne. Body: Montserrat Black, Poppins Bold, Mukta Bold. Treatments: gold-fill, metallic gradient, drop-shadow, outer glow, emboss. |
| **B Modern Desi** | Geometric sans (Gilroy, Inter, DM Sans), modern serifs (Fraunces, Playfair Display), clean Devanagari (Tiro Devanagari, Mukta). No scripts, no drop-shadows. |
| **C Minimalist Classy** | High-contrast serifs (Bodoni, Canela, Didot), condensed sans (Oswald, Bebas Neue) for captions. Sparing use, letter-spacing emphasised, single-weight per composition. |
| **D Artsy Playful** | Marker/crayon display (Caveat, Kalam, Patrick Hand, Shadows Into Light), rounded sans (Fredoka, Baloo 2). Slight rotation/wobble allowed. |
| **E Soft & Warm** | Soft serifs (Cormorant Garamond, Lora), gentle scripts (Sacramento, Parisienne) sparingly used, rounded sans (Quicksand, Comfortaa). Pastel-ink feel — never bold black weights. |

---

## 13. Background Finishes

Per-track surface treatment options. Selected at Step 6 (Colour & Finish). Each finish has a `promptPhrase` injected into the prompt's BG description.

### Track A — Shiny Maximal finishes

| ID | Name | Description |
|----|------|-------------|
| FN-1 | Plain Solid | Clean flat colour fill. Lets frame + illustration do the talking. |
| FN-2 | Radial Gradient | Centre-outward shimmer. Festive depth. Most versatile default. |
| FN-3 | Sparkle / Glitter | Diwali card / celebration energy. Particles add festivity. |
| FN-4 | Metallic Foil | Wedding card premium feel. Maximum bling. |
| FN-5 | Bokeh Glow | Warm fuzzy festive lights. Creates atmosphere. |

### Track B — Modern Desi finishes

| ID | Name | Description |
|----|------|-------------|
| FN-B1 | Flat Matte | Pure flat. Modern. |
| FN-B2 | Paper Grain | Kraft paper feel. Signature Track B. |
| FN-B3 | Gouache Wash | Painterly background. |
| FN-B4 | Linen / Raw Cotton | Handloom textile feel. |

### Track C — Minimalist Classy finishes

| ID | Name | Description |
|----|------|-------------|
| FN-C1 | Flat Matte | Perfectly clean surface. |
| FN-C2 | Soft Gradient | Barely perceptible tonal shift. |
| FN-C3 | Fine Paper | Premium stationery surface. |

### Track D — Artsy Playful finishes

| ID | Name | Description |
|----|------|-------------|
| FN-D1 | Flat Solid | Pure flat sticker background. |
| FN-D2 | Dot Pattern | Polka dot energy. |
| FN-D3 | Confetti Scatter | Party celebration feel. |
| FN-D4 | Striped | Bold graphic stripes. |

### Track E — Soft & Warm finishes

| ID | Name | Description |
|----|------|-------------|
| FN-E1 | Watercolour Wash | Soft painted wash with visible colour bleeding at edges. Organic. |
| FN-E2 | Plain Pastel | Solid flat pastel colour. Clean and calm. |
| FN-E3 | Soft Warm Gradient | Very gentle gradient — lighter centre to slightly deeper warm edges. |
| FN-E4 | Peripheral Watercolour | Light watercolour concentrated at edges & corners only — centre stays almost white. Natural vignette. |

---

## 14. Illustration Render Styles

Per-track rendering medium for the illustration only — applied to the chosen illustration item, not to the frame or background. Selected at Step 6.

### Track A render styles

| ID | Name | Description |
|----|------|-------------|
| IR-1 | Ornamental Vector | Traditional Indian wedding-card look — gold foil fills, paisley & mandala borders, symmetrical, with metallic shading and sparkle highlights. |
| IR-2 | Colourful Vector | Bright, cheerful poster art — vivid flat colours with bold outlines, no gold or metallic. Like a festive Amul-style illustration. |
| IR-3 | 3D Glossy | Modern 3D-rendered look — raised, shiny surfaces with soft shadows, like a premium toy or app icon. |

### Track B render styles

| ID | Name | Description |
|----|------|-------------|
| IR-B1 | Loose Watercolour | Hand-painted feel — visible brushstrokes, soft bleeding edges on paper. Editorial. |
| IR-B2 | Block Print | Hand-stamped woodcut look — only 2–3 colours, slightly imperfect registration, raw handcrafted texture. |
| IR-B3 | Ink Line + Wash | Detailed fine pen drawing with just a few touches of watercolour. Botanical illustration meets premium greeting card. |

### Track C render styles

| ID | Name | Description |
|----|------|-------------|
| IR-C1 | Tonal Flat | Elegant silhouette using darker / lighter shades of the SAME background colour. Monochromatic and refined. |
| IR-C2 | Embossed / Stamp | Looks like a raised seal or wax stamp pressed into the surface — tone-on-tone with subtle shadow depth. |
| IR-C3 | Fine Line + Wash | Delicate thin pen lines with very minimal colour wash. Lots of white space. |

### Track D render styles

| ID | Name | Description |
|----|------|-------------|
| IR-D1 | Flat Sticker | Bold dark outline with solid flat colour fills inside — no gradients or shadows. Like a WhatsApp sticker or vinyl decal. |
| IR-D2 | Doodle / Hand-Drawn | Casual marker-pen sketch with wobbly lines and imperfect shapes. |
| IR-D3 | 3D Cartoon | Smooth, rounded Pixar / claymation style — cute chunky proportions with soft lighting. |
| IR-D4 | Kawaii / Chibi | Japanese cute style — oversized head, tiny body, big sparkly eyes, blushing cheeks. |

### Track E render styles

| ID | Name | Description |
|----|------|-------------|
| IR-E1 | Watercolour Botanical | Soft painted botanical look — realistic proportions, watercolour bleeding edges, visible brushstrokes. |
| IR-E2 | Tonal Silhouette | Monochromatic illustration in slightly darker shades of the background colour family. |
| IR-E3 | Soft Pastel Flat | Clean gentle outlines with soft muted pastel colour fills — airy, light, rounded forms. |

---

## 15. Motif Sets — per Track

Per-track decorative pattern vocabulary. Used as A1 frame motifs (when Frame Decoration Level is Simple or Detailed) and A2 accent fills (in the auto-density calculation).

### Track A — 10 Indian mass-market motifs (MT-1..MT-10)

| ID | Motif | Description / Best With |
|----|-------|-------------------------|
| MT-1 | Paisley (Ambi) | Universal Indian, Kashmir shawl. Best with GM-C1, GM-C5. |
| MT-2 | Mandala | Spiritual, universal, sacred. Best with GM-C5, GM-C8. |
| MT-3 | Marigold Chain | Puja, wedding, festival. Highest GM resonance. Best with GM-C1, GM-C2. |
| MT-4 | Lotus Border | Devotional, auspicious, sacred. Best with GM-C4, GM-C5. |
| MT-5 | Peacock Motif | Royal, celebratory, Krishna. Best with GM-C9, GM-C8. |
| MT-6 | Diya Row | Diwali, devotional, evening variants. Best with GM-C1, GM-C5. |
| MT-7 | Rangoli Corners | South + Central India, geometric. Best with GM-C4, GM-C6. |
| MT-8 | Temple Arch | Devotional, architecture. Best with F5 frame. Best with GM-C5, GM-C1. |
| MT-9 | Mehndi Swirls | Wedding, feminine, bridal. Best with GM-C7, GM-C2. |
| MT-10 | Bel Patta Vine | Auspicious, nature-devotional. Best with GM-C4, GM-C5. |

### Track B — 8 modern desi motifs (MT-B1..MT-B8)

| ID | Motif | Prompt Phrase |
|----|-------|---------------|
| MT-B1 | Leaf Vine | Loose hand-drawn leaf vine border, organic trailing creeper |
| MT-B2 | Chai Steam | Wispy rising steam curl motif, delicate single-line smoke trails |
| MT-B3 | Block Stamp | Repeated small block-print stamp motif as border, woodcut flower pattern |
| MT-B4 | Brush Stroke | Single horizontal brush stroke divider, gouache swipe |
| MT-B5 | Kolam Dots | Simple geometric kolam dot pattern, minimal grid, South Indian |
| MT-B6 | Banana Leaf | Banana leaf border element, broad tropical leaf |
| MT-B7 | Pichwai Lotus | Stylised pichwai painting lotus motif, Nathdwara style |
| MT-B8 | Warli Figures | Simple warli tribal art border, stick figure line art, Maharashtra folk |

### Track C — 4 minimal motifs (MT-C1..MT-C4)

| ID | Motif | Prompt Phrase |
|----|-------|---------------|
| MT-C1 | None | No decorative motifs, no patterns, completely clean |
| MT-C2 | Hairline Rule | Single thin hairline rule border, 1px, geometric precision |
| MT-C3 | Corner Brackets | Minimal corner bracket marks, thin L-shaped crop marks |
| MT-C4 | Single Dot | Single small decorative dot or star at one corner, tiny accent |

### Track D — 6 playful motifs (MT-D1..MT-D6)

| ID | Motif | Prompt Phrase |
|----|-------|---------------|
| MT-D1 | Stars + Hearts | Scattered hand-drawn stars and hearts, small floating accents with thick outlines |
| MT-D2 | Squiggles | Playful squiggly lines, wavy doodle borders, hand-drawn swirl accents |
| MT-D3 | Speech Bubbles | Comic speech bubble shapes as decorative elements, pop art accents |
| MT-D4 | Confetti | Scattered geometric confetti in bright colours |
| MT-D5 | Flower Doodles | Simple hand-drawn flower doodles, five-petal daisies with smiley centres |
| MT-D6 | Emoji Accents | Small emoji-style expression faces, simple circle faces |

### Track E — 4 soft motifs (MT-E1..MT-E4)

| ID | Motif | Prompt Phrase |
|----|-------|---------------|
| MT-E1 | None | No decorative motifs, no patterns, completely clean |
| MT-E2 | Faint Mandala | Very faint watercolour mandala behind the illustration, barely visible, ghosted circular pattern |
| MT-E3 | Soft Leaf Border | Delicate organic leaf vine trailing along edges, very light and airy |
| MT-E4 | Dot Scatter | Tiny soft dots scattered sparsely as gentle accents, like dewdrops |

**Note on Birthday + Suvichar:** The Birthday category replaces these per-track motif sets with `BIRTHDAY_MOTIF_OPTIONS_A..E` (party-themed). Suvichar uses the same per-track motifs as Good Morning. Overlay packs apply per-track motif **swaps** (1:1 replacement of named base motifs) and **adds** (extra motifs) on top of whatever base set is active.

---

## 16. Customisation Presets (Intensity)

Per-track 3-tier control over decoration density at Step 7. The preset auto-sets multiple knobs (ornament density, gold amount, sparkle, metallic finish, motif coverage, drop shadow) — individual knobs remain accessible.

### Track A presets

| ID | Name | Description |
|----|------|-------------|
| Basic | Restrained Festive | Thin gold lines, matte finish, sparse motif placement, no sparkle. Clean but still festive. |
| Medium | Balanced Bling | Visible gold accents, satin sheen, motifs well-placed, moderate sparkle. The sweet spot. |
| Complex | Maximum Desi | Heavy gold fills, full metallic sheen, dense motifs, lots of sparkle. Indian wedding-card energy. |

### Track B presets

| ID | Name | Description |
|----|------|-------------|
| Minimal | Most Restrained | 50–60% empty space, very muted, fine hairline, flat surface, editorial minimalism. |
| Balanced | Editorial Standard | 35–45% empty, muted warm tones, medium brushstroke, paper grain texture. |
| Expressive | Maximum B | 20–30% empty, bold brushstrokes, warm saturated earths, visible gouache. |

### Track C presets

| ID | Name | Description |
|----|------|-------------|
| Ultra | Ultra-Minimal | 80%+ empty, tiny element <15% canvas, pure monochrome, no accent, no frame. Typography IS the poster. |
| Balanced | Balanced — Refined | 70% empty, small element, tonal with one accent, thin hairline frame. |
| Warm | Warm Elegant | 60% empty, comfortable scale element, accent + highlight, corner brackets. |

### Track D presets

| ID | Name | Description |
|----|------|-------------|
| Simple | Clean Playful | 1–2 elements, thin outlines, flat background, no doodle accents. |
| Fun | Standard Playful | 3–5 elements, stars + hearts accents, slight wobble, polka dots. |
| Maximum | Chaos Cute | 6+ elements, dense confetti, chunky outlines, chaotic rotation, no empty space. |

### Track E presets

| ID | Name | Description |
|----|------|-------------|
| Minimal | Maximum Calm | 70%+ empty space, very soft tones, whisper-thin illustration, no motifs. Maximally serene. |
| Balanced | Soft Standard | 50% empty, gentle warm tones, comfortably-sized illustration, subtle organic accents. |
| Rich | Warm Botanical | 30% empty, richer warm tones, larger illustration, visible watercolour effects, layered botanicals. |

### B1 Camera Intensity (separate set)

For B1, "intensity" controls camera distance + detail rather than decoration density:

| ID | Name | Description |
|----|------|-------------|
| Basic | Wide & Airy | Wide-angle, distant framing. Lots of sky / space. Scene elements small in frame. Environmental context dominates. |
| Medium | Balanced | Standard focal length. Scene elements at comfortable scale. Good detail with environmental context. |
| Complex | Close & Immersive | Tight framing, shallow depth of field. Scene elements fill the frame. Maximum detail density, bokeh blur. |

### B1 Mood (merged Lighting + Colour)

| ID | Name | Description |
|----|------|-------------|
| MD-1 | Golden Warm | Sunrise glow + warm amber tones. Classic Good Morning energy. ~4500K. |
| MD-2 | Misty Soft | Morning fog + muted natural tones. Dreamy, ethereal, calm. ~5500K. |
| MD-3 | Bright & Vivid | Clear daylight + saturated punchy colours. ~5600K. |
| MD-4 | Dramatic Rays | God rays through clouds / trees + high contrast. Theatrical. ~4200K. |
| MD-5 | Vintage Film | Soft diffused light + faded film look. Nostalgic, analog. ~4800K. |
| MD-6 | Soft Pastel | Overcast gentle light + desaturated pastels. Calm, airy. ~6200K. |

Track-specific best fits are flagged in the UI with ⭐ Best (e.g. Soft & Warm track → Soft Pastel or Golden Warm).

---

## 17. Illustration & Image Library — Good Morning Default

41 items across 6 sub-categories. Each item maps to specific archetypes and has a B1 photoreal description (`B1_PHOTO_DESC[id]`).

### GM-I1 — Beverages (6 items)

| ID | Name | Description / Context | Archetypes |
|----|------|----------------------|------------|
| GM-I1-01 | Steaming Chai Cup | Classic ceramic cup with rising steam wisps. Most iconic GM visual. | All |
| GM-I1-02 | Clay Kulhad with Chai | Earthen kulhad with masala chai — Tier 2/3 Bharat resonance. | A1, A2 |
| GM-I1-04 | Masala Chai with Spices Spread | Chai surrounded by cinnamon, cardamom, ginger, cloves. | A2 |
| GM-I1-05 | Glass of Fresh Orange Juice | Bright citrus energy. Summer / uplifting variant. | A2, B1 |
| GM-I1-07 | Decorative Ceramic Teapot + Cup | Patterned teapot. Pairs with floral frames. | A1, A2 |
| GM-I1-08 | Tender Coconut Water | Fresh coconut with straw. Coastal / health. | A2, B1 |

### GM-I2 — Nature & Skyscapes (6 items)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| GM-I2-01 | Sunrise over Green Hills | Golden horizon with valley mist. | All |
| GM-I2-02 | Sun Rays through Forest Trees | God rays through canopy. Spiritual. | B1, A2 |
| GM-I2-04 | Morning Mist over River | Still river, golden mist rising. | B1 |
| GM-I2-05 | Sunrise over Ocean Horizon | Wide golden sea, gentle waves. | B1 |
| GM-I2-06 | Mountain Peak at Golden Hour | Peak in warm first light. Aspirational. | B1, A2 |
| GM-I2-08 | Rainbow after Morning Rain | Hope and new beginnings. | B1, A2 |

### GM-I3 — Flowers & Botanicals (9 items)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| GM-I3-01 | Marigold Garland (Genda Phool) | Highest cultural resonance. | A1, A2, C1 |
| GM-I3-02 | Lotus in Full Bloom | Sacred, pure, new beginnings. | A1, A2, C1, B1 |
| GM-I3-03 | Jasmine Buds (Mogra) | South India affinity, fragrant. | A1, A2 |
| GM-I3-04 | Hibiscus (Gudhal Phool) | Morning puja flower. | A1, A2 |
| GM-I3-05 | Sunflower Facing Sun | Morning energy. | A2, B1, C1 |
| GM-I3-06 | Champa / Frangipani | Temple flower, calm. | A1, A2 |
| GM-I3-07 | Rose Bud with Dew | Romantic, universal. | A2, B1 |
| GM-I3-08 | Petals Floating on Water | Calm water reflection. | B1, A2 |
| GM-I3-09 | Cherry Blossom Branches | Modern / urban. | A1, A2, C1 |

### GM-I4 — Spiritual & Devotional (8 items)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| GM-I4-01 | Lit Diya with Warm Glow | Single diya with halo. Devotional. | All |
| GM-I4-03 | Hands in Namaste | Universal greeting gesture. | A2 |
| GM-I4-04 | Incense Stick Smoke | Lit agarbatti, rising smoke curl. | A1, A2, B1 |
| GM-I4-05 | Tulsi Plant in Brass Pot | Morning puja, Bharat signal. | A1, A2 |
| GM-I4-06 | Temple Bell (Ghanti) | Morning aarti, awakening. | A1, A2 |
| GM-I4-07 | Shankh (Conch Shell) | Sacred, dawn announcement. | A1, A2 |
| GM-I4-08 | Rangoli at Dawn | Joyful, celebratory. | A1, A2 |
| GM-I4-09 | Peacock Feather | Krishna, decorative + spiritual. | A1, A2 |

### GM-I5 — Lifestyle & Human Moments (6 items)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| GM-I5-01 | Surya Namaskar Silhouette | Sun salutation at sunrise. | A2, B1 |
| GM-I5-02 | Meditating Figure at Sunrise | Calm, spiritual silhouette. | A2, B1 |
| GM-I5-03 | Open Window with Sunrise View | Interior frame, golden sky. | A1, A2, B1 |
| GM-I5-04 | Book and Chai on Morning Desk | Cosy intellectual. | A2, B1 |
| GM-I5-05 | Morning Walk on Tree-Lined Path | Casual lifestyle. | B1, A2 |
| GM-I5-06 | Watering Plants on Balcony | Morning routine. | A2, B1 |

### GM-I6 — Birds & Wildlife (6 items)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| GM-I6-01 | Bird Flock at Sunrise (V-Formation) | Universal trope. | B1, A2 |
| GM-I6-02 | Sparrow on Flowering Branch | Delicate, intimate. | A2, A1 |
| GM-I6-03 | Peacock with Fanned Tail | Majestic, Indian identity. | A2, B1 |
| GM-I6-04 | Parrot on Mango Branch | Bright, tropical. | A2, A1 |
| GM-I6-05 | Sarus Crane in Misty Field | Peaceful, poetic. | B1, A2 |
| GM-I6-06 | Butterflies on Flowers at Dawn | Light, hopeful. | A2, B1 |

---

## 18. Shared Accent Items Library (ACC-01..ACC-30)

A flat library of small accent props used as A2 sub-elements (illustrated, in same style as main) and B1 supporting props (photoreal). Each item has both `photoDesc` (B1) and `illusDesc` (A2).

### Kitchen / table props

| ID | Name | photoDesc / illusDesc snippet |
|----|------|------------------------------|
| ACC-01 | Biscuits on a Plate | Plate of Parle-G-style biscuits / illustrated plate of biscuits |
| ACC-02 | Folded Newspaper | Folded morning newspaper / illustrated folded newspaper |
| ACC-03 | Spice Scatter | Scattered cardamom + cinnamon stick / tiny spices scattered |
| ACC-04 | Sugar Bowl | Brass sugar bowl + tiny spoon / illustrated brass sugar bowl |
| ACC-05 | Steel Tray (Thali) | Round steel tray under cup / illustrated round tray |
| ACC-06 | Rustic Cloth Napkin | Folded cotton napkin / illustrated cloth napkin |

### Nature / outdoor accents

| ID | Name | Snippet |
|----|------|---------|
| ACC-07 | Morning Dew Drops | Glistening dew on grass / tiny dewdrops |
| ACC-08 | Fallen Petals | Scattered petals on ground / illustrated petals |
| ACC-09 | Wispy Fog | Thin wisps of morning fog / soft illustrated mist |
| ACC-10 | Distant Birds | Small birds silhouetted in distant sky / 2-3 tiny birds |
| ACC-11 | Wet Leaves | Rain-washed leaves with droplets / illustrated wet leaves |
| ACC-12 | Cobblestone / Path | Textured stone / brick path / illustrated cobblestone |

### Devotional / puja accents

| ID | Name | Snippet |
|----|------|---------|
| ACC-13 | Kumkum Tilak Mark | Small kumkum mark on brass plate / illustrated kumkum |
| ACC-14 | Loose Flower Petals | Loose marigold petals around base / illustrated marigold |
| ACC-15 | Brass Bell (small) | Tiny brass puja bell / illustrated puja bell |
| ACC-16 | Match Sticks | Matchbox + burnt matchstick / illustrated matchbox |
| ACC-17 | Rice Grains | Scattered uncooked rice grains / illustrated rice |

### Lifestyle / cosy accents

| ID | Name | Snippet |
|----|------|---------|
| ACC-18 | Reading Glasses | Reading glasses near book / illustrated glasses |
| ACC-19 | Potted Plant (small) | Small potted succulent / illustrated potted plant |
| ACC-20 | Woven Basket | Small woven cane basket / illustrated woven basket |
| ACC-21 | Curtain with Light | Sheer curtain with morning light / illustrated curtain |
| ACC-22 | Yoga Mat Edge | Rolled edge of yoga mat / illustrated yoga mat |

### Window / architectural

| ID | Name | Snippet |
|----|------|---------|
| ACC-23 | Window Grille Shadow | Geometric shadow patterns / illustrated window shadow |
| ACC-24 | Terracotta Pot | Small terracotta pot with sprout / illustrated terracotta |
| ACC-25 | Hanging Wind Chime | Wind chime catching light / illustrated wind chime |

### Wildlife / garden

| ID | Name | Snippet |
|----|------|---------|
| ACC-26 | Dewy Spider Web | Spider web with morning dew / illustrated spider web |
| ACC-27 | Single Butterfly | Butterfly on petal / illustrated butterfly |
| ACC-28 | Dragonfly on Reed | Dragonfly perched on reed / illustrated dragonfly |

### Steam / smoke

| ID | Name | Snippet |
|----|------|---------|
| ACC-29 | Curl of Steam | Visible curl of steam rising / decorative illustrated steam curl |
| ACC-30 | Incense Smoke Wisp | Thin trail of incense smoke / illustrated smoke trail |

### Suvichar / quote-card extension (SV-ACC-01..06)

| ID | Name | Snippet |
|----|------|---------|
| SV-ACC-01 | Scattered Autumn Leaves | Dried autumn leaves on ground / illustrated autumn leaves |
| SV-ACC-02 | Bookmark | Slim ribbon bookmark in book / illustrated bookmark |
| SV-ACC-03 | Pen Nib / Ink Drop | Calligraphy pen nib or ink drop / illustrated pen nib |
| SV-ACC-04 | Smooth River Pebbles | 2-3 smooth rounded pebbles / illustrated pebbles |
| SV-ACC-05 | Dried Pressed Flower | Dried pressed botanical / illustrated dried botanical |
| SV-ACC-06 | Simple Candle Stub | Short unadorned candle / illustrated slim candle |

### Birthday / celebration extension (BD-ACC-01..06)

| ID | Name | Snippet |
|----|------|---------|
| BD-ACC-01 | Confetti Scatter | Bright scattered confetti / illustrated confetti |
| BD-ACC-02 | Ribbon Curl Accent | Curled satin ribbon / illustrated ribbon curl |
| BD-ACC-03 | Thin Birthday Candles | Slim colourful candles with flames / illustrated candles |
| BD-ACC-04 | Foil Star Accent | Metallic foil star / illustrated metallic star |
| BD-ACC-05 | Sprinkles / Sugar Pearls | Cake sprinkles / illustrated sprinkles |
| BD-ACC-06 | Gift Tag | Blank gift tag with ribbon loop / illustrated gift tag |

**Sub-element mapping:** Each main illustration ID has a curated array of accent IDs in `B1_SUB_ELEMENTS[id]`, `A2_SUB_ELEMENTS[id]`, `SV_*_SUB_ELEMENTS[id]`, `BD_*_SUB_ELEMENTS[id]`. The wizard exposes only those curated accents per main illustration, ensuring every sub-element is contextually relevant.

---

# Part 3 — Base Categories

A base category defines the hero text and ships its own illustration catalogue + per-track motif sets. The framework engine is reused as-is; only category-specific data and (for Suvichar) wizard-flow extensions change.

## 19. Good Morning (default category)

Good Morning is the highest-volume greeting category in India — millions of WhatsApp forwards daily. The pack curates colour palettes, font pairings, illustration libraries, and AI prompt formulas matching the visual and emotional signature.

**Hero text:** "Good Morning" / "शुभ प्रभात" (Hindi/English/Hinglish toggle).

**Wizard flow (per archetype):**
- **A1:** `Template → Frame → Layout → Track → Colour & Finish → Visual → Intensity`
- **A2:** `Template → Layout → Track → Colour & Finish → Visual → Intensity`
- **B1:** `Template → Text + Overlay (merged) → Track → Scene Elements → Mood → Intensity`

**Illustration catalogue:** 41 items across 6 sub-categories (GM-I1 Beverages, GM-I2 Nature, GM-I3 Flowers, GM-I4 Spiritual, GM-I5 Lifestyle, GM-I6 Birds). See [Section 17](#17-illustration--image-library--good-morning-default).

**Motif sets:** Default per-track motifs (MT-1..MT-10 for A; MT-B1..B8; MT-C1..C4; MT-D1..D6; MT-E1..E4). See [Section 15](#15-motif-sets--per-track).

**Atmosphere & mood (used by `getCategoryAtmosphere()`):**

| Variable | Value |
|----------|-------|
| `atmosphereInline` | `early morning Indian setting` |
| `atmosphereSentenceCase` | `Early morning Indian setting` |
| `sceneAuthenticity` | `real Indian morning setting` |
| `gemSettingContext` | `early morning in India` |
| `lightTimeContext` | `natural and time-appropriate for early morning` |
| `stylePhMoodWord` | `morning` |
| Category label | `Good Morning` |

**Sample MJ prompt (Track A + A1 + Devotional GM):**

```
[Track A Shiny Maximal + A1 Text+Frame + L1 Top + GM-C1 Golden Hour + Subject: chai + Mood: celebratory]
Ornate symmetric decorative border frame filling all 4 edges of a 9:16 portrait,
gold-leaf filigree with paisley and marigold motifs rendered in warm amber (#F59E0B)
on deep saffron (#B45309) ground, central bordered panel reserved for heading text in
the top third, below panel a small centred illustration of a brass kulhad chai cup
with curling steam wisps and three marigold blossoms, gradient gold ink wash, flat
vector illustration with metallic gold accents, ornamental Indian wedding-card aesthetic,
celebratory warm morning mood, --ar 9:16 --s 400 --stylize high.
Negative: no text, no logo, no watermark, no photography, no cartoon,
no Western fonts, no Christmas motifs.
```

**Sample B1 prompt (Track C Cinematic):**

```
[Track C + B1 Photo BG + L2 + GM-C1 + Subject: sunrise over Indian landscape + Mood: peaceful reverent]
Photorealistic landscape photograph, 9:16 portrait, golden-hour sunrise over layered
misty Himalayan foothills, warm god-rays through silhouetted deodar trees on left-third,
low horizon at bottom 40%, sun behind ridgeline with gentle lens flare, atmospheric
haze with volumetric light shafts, distant temple spire mid-ground, Kodak Portra 400
film aesthetic, teal-amber cinematic colour grade, deep #1E3A5F shadows, warm #F59E0B
highlights, shallow depth of field, subtle film grain, top 35% darkened for overlay text,
peaceful reverent mood, --ar 9:16 --style raw --s 150 --chaos 0.
Negative: no text, no logos, no people faces, no cartoon, no flat illustration,
no HDR over-saturation, no fake rainbow.
```

**Creator customisation fields (overrides on top of selections):**

| Field | What It Does |
|-------|-------------|
| Recipient Name | Personalises the greeting — "Good Morning [Name]!". Optional. |
| Message / Quote | Short blessing or motivational line. Hindi / English / Hinglish. Max 2 lines. |
| Language | Hindi / English / Hinglish (default). Regional language support TBD Phase 2. |
| Specific Visual Override | Replaces Step 5/7 default with a specific visual request (modifies VISUAL_SUBJECT). |
| Time of Day Variant | Good Morning / Good Afternoon / Good Evening / Good Night. Changes palette recommendation + prompt SETTING. |

---

## 20. Birthday Category Pack v2

> Incremental spec on top of Template Creation Framework v20.
> Documents only what CHANGES or is NEW for the Birthday category.

**Changes from v1:**
- New `BD-ACC-*` sub-illustration accent library — replaces generic GM-themed props (kumkum, incense smoke, marigold petals) with purpose-built birthday celebration accents.
- Sub-element mapping updated for all 30 Birthday illustration items (B1 and A2).
- Birthday-specific negative terms formalised (`funeral, mourning, sad, wilted, dark mood, horror`) — applied to all archetype prompt builders.

### 20.1 What this category is

Birthday is a celebration-first greeting category. Visual energy (balloons, cake, confetti, sparkle) shares the canvas with the greeting text — "Happy Birthday" replaces "Good Morning" as hero text.

**Only two things change from Good Morning:**

1. **Border motifs / A2 accent motifs** — replaced with Birthday-specific motif sets per track.
2. **Illustration catalogue** — replaced with Birthday-specific items (30 new + 4 GM carry-overs).

Everything else — wizard flow, archetypes, tracks, layouts, background finishes, render styles, prompt builder architecture — carries over unchanged.

### 20.2 Wizard flow

**Identical to Good Morning** — no Feeling step, no Custom Text step.

```
A1: Template → Frame → Layout → Track → Colour & Finish → Visual → Intensity
A2: Template → Layout → Track → Colour & Finish → Visual → Intensity
B1: Template → Text + Overlay → Track → Scene Elements → Mood → Intensity
```

Birthday has one emotional lane: celebration. The track system (A–E) provides all the tonal variation needed — from maximal party (Track A) to soft warmth (Track E). All 5 tracks remain available for every Birthday template.

### 20.3 Birthday border motif sets per track

Each track's frame motif vocabulary is **replaced** (not extended) with Birthday-specific motifs. Used in:
- **A1** — Frame decoration motifs (Plain / Simple / Detailed levels)
- **A2** — Accent density fill items (auto-calculated density)

#### Track A — Shiny Maximal

| ID | Motif | Description |
|----|-------|-------------|
| BD-MT-A1 | Gold Foil Balloons | Shiny metallic balloon cluster, gold / rose-gold |
| BD-MT-A2 | Confetti Burst | Dense confetti explosion, multi-colour with gold sparkle |
| BD-MT-A3 | Marigold Garland Border | Thick marigold toran along frame edge, festive Indian |
| BD-MT-A4 | Ornate Gift Bow | Large decorative ribbon bow, satin with gold thread |
| BD-MT-A5 | Sparkle Cluster | Scattered star-sparkle accents, glitter energy |
| BD-MT-A6 | Mithai & Sweets | Decorative Indian sweets — ladoo / barfi with gold leaf |

#### Track B — Modern Desi

| ID | Motif | Description |
|----|-------|-------------|
| BD-MT-B1 | Marigold String Lights | Thin marigold strand with small fairy lights woven through |
| BD-MT-B2 | Rangoli Corner Motifs | Quarter-rangoli patterns in frame corners, geometric floral |
| BD-MT-B3 | Modern Balloon Trio | 3 balloons (1 foil + 2 latex), clean composition |
| BD-MT-B4 | Diya Accent Row | Small line of lit diyas along frame base, warm glow |
| BD-MT-B5 | Bunting Flags (Desi Print) | Triangular bunting with block-print / ikat patterns |
| BD-MT-B6 | Cake Slice (Minimal) | Single clean cake slice, modern plating, side view |

#### Track C — Minimalist Classy

| ID | Motif | Description |
|----|-------|-------------|
| BD-MT-C0 | None | No decorative motifs, completely clean |
| BD-MT-C1 | Single Balloon + String | One balloon with trailing string, elegant negative space |
| BD-MT-C2 | Thin Confetti Scatter | Sparse confetti dots, muted metallic tones |
| BD-MT-C3 | Minimal Candle Line | Row of thin birthday candles, unlit or with tiny flame |
| BD-MT-C4 | Geometric Gift Box | Clean-line gift box silhouette, no texture |
| BD-MT-C5 | Laurel / Leaf Wreath | Simple botanical wreath arc, framing text zone |
| BD-MT-C6 | Dot Sparkle Trail | Minimal dot trail suggesting sparkle, gold or silver |

#### Track D — Artsy Playful

| ID | Motif | Description |
|----|-------|-------------|
| BD-MT-D1 | Hand-drawn Balloons | Sketchy, wobbly balloon outlines, crayon or marker style |
| BD-MT-D2 | Doodle Confetti | Loose hand-drawn confetti shapes — stars, circles, squiggles |
| BD-MT-D3 | Cartoon Cake Slice | Fun illustrated cake with exaggerated frosting, sprinkles |
| BD-MT-D4 | Playful Streamers | Curly ribbon streamers in bright colour, hand-drawn feel |
| BD-MT-D5 | Party Hat (Illustrated) | Classic cone party hat with pom-pom, playful illustration |
| BD-MT-D6 | Sticker-style Stars | Puffy star stickers, slightly 3D, scattered |

#### Track E — Soft & Warm

| ID | Motif | Description |
|----|-------|-------------|
| BD-MT-E0 | None | No decorative motifs, completely clean |
| BD-MT-E1 | Watercolour Balloons | Soft-edge balloons in pastel watercolour wash |
| BD-MT-E2 | Gentle Confetti | Soft-falling confetti in muted pastels, slow-drift feel |
| BD-MT-E3 | Floral Wreath (Soft) | Delicate flower and leaf wreath, watercolour botanical |
| BD-MT-E4 | Pastel Bunting | Soft fabric bunting in cream / blush / sage tones |
| BD-MT-E5 | Candle Glow (Warm) | Single warm candle with soft light bloom, cosy |
| BD-MT-E6 | Ribbon Curl (Soft) | Gentle satin ribbon curl, pastel, no hard edges |

### 20.4 Birthday illustration catalogue (34 items)

#### Carry-over from Good Morning (4 items)

| ID | Name | Archetypes | Notes |
|----|------|------------|-------|
| GM-I3-01 | Marigold / Flowers | A1, A2 | Floral birthday, Indian festive crossover |
| GM-I4-01 | Candle / Diya | All | Birthday candle + devotional blessing |
| GM-I3-02 | Lotus Flower | A1, A2, B1 | Blessing / purity — works for elder birthday wishes |
| GM-I6-01 | Birds in Flight | B1, A2 | Freedom, new chapter metaphor |

#### Party Essentials (10 items)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| BD-I01 | Birthday Cake (Full) | Multi-tier decorated cake with candles lit, front view | A1, A2, B1 |
| BD-I02 | Cake Slice (Plated) | Single slice on plate, frosting layers visible, side angle | A1, A2 |
| BD-I03 | Cupcake (Single) | Decorated cupcake with swirl frosting and single candle | A1, A2 |
| BD-I04 | Balloon Bunch | Cluster of 5–7 balloons (mix latex + foil), strings trailing | A1, A2 |
| BD-I05 | Single Balloon | One balloon with long string, elegant and minimal | A1, A2 |
| BD-I06 | Gift Box (Wrapped) | Neatly wrapped present with ribbon bow, 3/4 angle | A1, A2, B1 |
| BD-I07 | Gift Stack | 2–3 gifts stacked, different sizes and wrapping patterns | A1, A2 |
| BD-I08 | Party Hat | Classic cone party hat with elastic string and pom-pom | A1, A2 |
| BD-I09 | Birthday Candles (Row) | Row of colourful thin birthday candles, lit flames | A1, A2 |
| BD-I10 | Confetti Popper | Party popper mid-burst, confetti and streamers shooting out | A1, A2 |

#### Indian Festive (5 items)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| BD-I11 | Marigold Toran (Hanging) | Draped marigold garland toran, doorway blessing style | A1, A2 |
| BD-I12 | Mithai Box (Open) | Open box of assorted Indian sweets — ladoo, barfi, peda | A1, A2 |
| BD-I13 | Diya Cluster | 3–5 lit clay diyas arranged together, warm flame glow | A1, A2 |
| BD-I14 | Rangoli (Floor) | Circular rangoli pattern, bird's-eye view, colourful powder | A2, B1 |
| BD-I15 | Puja Thali | Decorated thali with kumkum, rice, flowers, diya — blessing | A1, A2 |

#### Decorative & Atmosphere (7 items)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| BD-I16 | Bunting / Banner | Triangular flag bunting string, "Happy Birthday" or plain | A1, A2 |
| BD-I17 | Fairy Lights (String) | Warm fairy light string, soft bokeh glow, draped or straight | A1, A2, B1 |
| BD-I18 | Streamers (Hanging) | Colourful paper streamers hanging from top of frame | A1, A2 |
| BD-I19 | Fireworks (Sky) | Firework burst against dark sky, celebration energy | A2, B1 |
| BD-I20 | Sparkler (Handheld) | Lit sparkler with bright white sparks radiating | A1, A2, B1 |
| BD-I21 | Flower Bouquet | Mixed flower bouquet, wrapped or in vase, gift style | A1, A2 |
| BD-I22 | Star Scatter | Scattered decorative stars, mixed sizes, metallic | A1, A2 |

#### Objects & Symbols (4 items)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| BD-I23 | Crown / Tiara | Birthday crown or tiara, gold with gem accents | A1, A2 |
| BD-I24 | Number Candle | Large decorative number candle (generic "1" shape as reference) | A1, A2 |
| BD-I25 | Ribbon Bow (Standalone) | Satin ribbon bow, gift-wrap style, standalone accent | A1, A2 |
| BD-I26 | Wish Card / Envelope | Greeting card or envelope, partially open, warm | A1, A2 |

#### Human / Figurative — B1 only (4 items)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| BD-I27 | Hands Holding Cake | Two hands presenting a birthday cake, warm lighting | B1 |
| BD-I28 | Blowing Candles (Silhouette) | Person leaning to blow out candles, side profile silhouette | B1 |
| BD-I29 | Group Celebration | 2–3 people cheering / clapping around a table, candid joy | B1 |
| BD-I30 | Child with Balloon | Small child holding a single balloon, back view or silhouette | B1 |

#### Catalogue summary

| Category | Total | Carry-over | New |
|----------|:-----:|:----------:|:---:|
| Good Morning carry-overs | 4 | 4 | — |
| Party Essentials | 10 | — | 10 |
| Indian Festive | 5 | — | 5 |
| Decorative & Atmosphere | 7 | — | 7 |
| Objects & Symbols | 4 | — | 4 |
| Human / Figurative | 4 | — | 4 |
| **Total** | **34** | **4** | **30** |

No feeling-based restriction system — all 34 illustrations are available at all times. Track + archetype filtering is the only gate.

### 20.5 Birthday sub-illustration accent library (BD-ACC)

When a main illustration is selected, the system assigns small secondary accent props. For Birthday, these are drawn from the `BD-ACC-*` set, ensuring supporting props match the celebration aesthetic rather than generic GM props.

| ID | Name | Photo Desc (B1) | Illustration Desc (A2) |
|----|------|----------------|------------------------|
| BD-ACC-01 | Confetti Scatter | small scattered confetti pieces in bright colours on the surface | small illustrated confetti pieces scattered nearby |
| BD-ACC-02 | Ribbon Curl Accent | a short curled satin ribbon in a festive colour | a small illustrated curled ribbon accent nearby |
| BD-ACC-03 | Thin Birthday Candles | one or two slim colourful birthday candles with lit flames | one or two small illustrated thin birthday candles |
| BD-ACC-04 | Foil Star Accent | a metallic foil star or a trailing balloon string accent | a small illustrated metallic star or balloon string |
| BD-ACC-05 | Sprinkles / Sugar Pearls | scattered cake sprinkles or small sugar pearl beads | small illustrated cake sprinkles scattered nearby |
| BD-ACC-06 | Gift Tag | a small blank gift tag with a ribbon loop | a tiny illustrated gift tag with a ribbon loop |

The shared `ACC-08` (Fallen Petals) is also used as a supporting prop for Indian Festive illustrations (Marigold Toran, Diya Cluster, Rangoli, Puja Thali, Flower Bouquet) where fallen petals are contextually natural.

#### Sub-element mapping per main illustration — A2 (illustrated sub-accents)

| Main Illustration | Sub-Accents (in order) |
|-------------------|------------------------|
| BD-I01 Birthday Cake | Confetti, Candles, Sprinkles |
| BD-I02 Cake Slice | Sprinkles, Confetti, Candles |
| BD-I03 Cupcake | Candles, Sprinkles, Confetti |
| BD-I04 Balloon Bunch | Foil Star, Ribbon, Confetti |
| BD-I05 Single Balloon | Foil Star, Ribbon, Confetti |
| BD-I06 Gift Box | Ribbon, Gift Tag, Confetti |
| BD-I07 Gift Stack | Ribbon, Gift Tag, Confetti |
| BD-I08 Party Hat | Confetti, Foil Star, Candles |
| BD-I09 Birthday Candles Row | Sprinkles, Confetti, Ribbon |
| BD-I10 Confetti Popper | Confetti, Foil Star, Ribbon |
| BD-I11 Marigold Toran | Fallen Petals, Confetti, Ribbon |
| BD-I12 Mithai Box | Sprinkles, Confetti, Ribbon |
| BD-I13 Diya Cluster | Fallen Petals, Confetti, Candles |
| BD-I14 Rangoli | Fallen Petals, Confetti, Ribbon |
| BD-I15 Puja Thali | Fallen Petals, Confetti, Ribbon |
| BD-I16 Bunting / Banner | Confetti, Foil Star, Ribbon |
| BD-I17 Fairy Lights | Foil Star, Confetti, Ribbon |
| BD-I18 Streamers | Confetti, Foil Star, Ribbon |
| BD-I20 Sparkler | Confetti, Foil Star, Sprinkles |
| BD-I21 Flower Bouquet | Fallen Petals, Ribbon, Confetti |
| BD-I22 Star Scatter | Foil Star, Confetti, Ribbon |
| BD-I23 Crown / Tiara | Foil Star, Ribbon, Confetti |
| BD-I24 Number Candle | Candles, Sprinkles, Confetti |
| BD-I25 Ribbon Bow | Ribbon, Confetti, Gift Tag |
| BD-I26 Wish Card / Envelope | Gift Tag, Ribbon, Confetti |

#### Sub-element mapping per main illustration — B1 (photorealistic supporting props)

| Main Illustration | Sub-Props (in order) |
|-------------------|----------------------|
| BD-I01 Birthday Cake | Confetti, Candles, Sprinkles |
| BD-I06 Gift Box | Ribbon, Confetti, Gift Tag |
| BD-I14 Rangoli | Fallen Petals, Confetti, Ribbon |
| BD-I17 Fairy Lights | Confetti, Foil Star, Ribbon |
| BD-I19 Fireworks | Confetti, Foil Star, Ribbon |
| BD-I20 Sparkler | Confetti, Foil Star, Sprinkles |
| BD-I27 Hands Holding Cake | Confetti, Candles, Sprinkles |
| BD-I28 Blowing Candles | Confetti, Candles, Foil Star |
| BD-I29 Group Celebration | Confetti, Ribbon, Foil Star |
| BD-I30 Child with Balloon | Confetti, Foil Star, Ribbon |

### 20.6 Prompt context — Birthday variables

Used by `getCategoryAtmosphere()` and surrounding scene language.

| Variable | Good Morning Value | Birthday Value |
|----------|-------------------|----------------|
| Hero text | "Good Morning" | "Happy Birthday" (fixed — no user input step) |
| Text character range | Short greeting (1–2 lines) | Same |
| Optional sub-text | Blessing / quote line | Birthday wish / name personalisation |
| Text language options | Hindi, English, Hinglish | Hindi, English, Hinglish — no change |
| `atmosphereInline` | `early morning Indian setting` | `Indian birthday celebration setting` |
| `atmosphereSentenceCase` | `Early morning Indian setting` | `Indian birthday celebration setting` |
| `sceneAuthenticity` | `real Indian morning setting` | `real Indian birthday celebration` |
| `gemSettingContext` | `early morning in India` | `an Indian birthday celebration` |
| `lightTimeContext` | `natural and time-appropriate for early morning` | `natural and warm for a birthday celebration` |
| `stylePhMoodWord` | `morning` | `birthday` |
| Category label | `Good Morning` | `Happy Birthday` |

#### Birthday-specific negative terms

Appended to per-archetype negatives:

| Archetype | Birthday Additions |
|-----------|-------------------|
| A1 | `funeral, mourning, sad, wilted, dark mood, horror` |
| A2 | `funeral, mourning, sad, wilted, dark mood, horror` |
| B1 | `funeral, mourning, sad, wilted, dark mood, horror, illustrated elements, graphic design, decorative overlay` |

#### Platform-specific notes

All platform adapters (Midjourney, Firefly, Leonardo, Gemini) inherit unchanged. Only context variable values swap.

### 20.7 Birthday layout bias

Guidance, not a hard filter.

| Layout | Birthday Suitability | Reason |
|--------|:-------------------:|--------|
| L5 — Text Bottom | ★ Best | Illustration / cake fills top, "Happy Birthday" anchors at base — classic card |
| L2 — Overlay / Text Centre | ★ Best | Atmospheric party background with centred greeting overlay |
| L1 — Text Top | ✓ Works | "Happy Birthday" at top, illustration below — clean |
| L6 — Text Centre (frame) | ✓ Works | Strong for A1 — frame with centred greeting, corner illustrations |
| L3 / L4 — Text Left / Right | ✓ Works | Birthday illustrations are compact enough for side placement at any size |

Unlike Suvichar (which cautions L3/L4), Birthday works well with side layouts because greeting text is short and illustration subjects (cake, balloons) have clear focal points.

### 20.8 What does NOT change for Birthday

- 3 archetype families (A1, A2, B1) and their wizard flows
- 5 tracks (A–E) and their colour palettes, font pools
- All background finish options (per-track finishes carry over as-is)
- Illustration render style step — fully inherited per track, no locking
- Illustration size — all three sizes available (Small / Medium / Large), no cap
- All 6 layouts (L1–L6) and frame / overlay compatibility rules
- Prompt builder logic / function architecture for all platforms
- Shared ACCENT_ITEMS library (ACC-01..ACC-30) — used where contextually appropriate (ACC-08 Fallen Petals for Indian Festive items)
- Density auto-calculation for A2
- Intensity controls
- Character limits and prompt construction helpers (`stripHex`, `trunc`)

---

## 21. Suvichar / Daily Quotes Category Pack v2

> Incremental spec on top of Template Creation Framework v20.
> Documents only what CHANGES or is NEW for the Suvichar / Quotes category.

**Changes from v1:**
- SV-specific background finishes (SV-BG01..04) **removed** — Suvichar now uses the same per-track finishes as Good Morning and Birthday.
- Locked render styles for Abstract illustrations **reverted** — all illustrations use the standard per-track render style step.
- **Custom text input added** as the final wizard step — user types their actual quote, which feeds directly into the prompt.
- Illustration catalogue reorganised — GM carry-over items now appear inside their semantic category (Nature & Landscape, Objects & Still Life), no separate "Carry-overs" bucket.
- New `SV-ACC-*` sub-illustration accent items replace GM-themed props (morning dew, incense, kumkum) with contemplative, quote-appropriate accents.

### 21.1 What this category is

Suvichar (motivational / inspirational / daily quotes) is a **text-first category**. The quote is the hero — illustration is atmospheric support only.

**Two things change from Good Morning:**

1. A new **Feeling** selector runs before track selection.
2. A **Custom Text** input is the final step — the user types their actual quote, which is rendered in the poster text zone.

### 21.2 Wizard flow

```
A1 (Text + Frame):       Archetype → Feeling → Style → Layout → Track → Colour & Finish → Visual → Intensity → Custom Text
A2 (Text + Illustrations): Archetype → Feeling → Layout → Track → Colour & Finish → Visual → Intensity → Custom Text
B1 (Full Photo BG):      Archetype → Feeling → Text Placement → Track → Scene Elements → Mood → Intensity → Custom Text
```

The **Custom Text** step is the last step for all archetypes in Suvichar. It is required — Next / Generate is disabled until at least one character is entered.

### 21.3 Feeling system (SV-F1..SV-F5)

Five feelings covering the full emotional range of quote content. Each has a distinct visual personality that drives track filtering and illustration selection.

| Code | Name | Visual Personality | What it means | Example quotes |
|------|------|--------------------|---------------|----------------|
| **SV-F1** | **Rise & Shine** | Bright, energetic, forward-moving. Sunrise energy. | Aspirational uplift — "You can do this." Optimistic, outward, action-oriented. | "Every day is a new beginning", gym motivation, achievement |
| **SV-F2** | **Still Waters** | Slow, contemplative, inward. Moon / water / lone tree energy. | Deep reflection — "Sit with this." Philosophical, unhurried, inner-focused. | Rumi, Kabir, self-awareness, philosophy, life lessons |
| **SV-F3** | **Bittersweet** | Honest, aching, tender. Not dark — bittersweet longing. | Emotional honesty — "This too." Acknowledges pain without wallowing. | Loss quotes, nostalgia, longing, shayari, letting go |
| **SV-F4** | **Everyday Calm** | Functional warmth. Cosy desk, morning ritual, gentle habit. | Grounded daily reminder — "Just today." Practical, close-to-home, no drama. | "Drink water", "Rest is productive", micro-habits, stoic reminders |
| **SV-F5** | **Fire & Drive** | Bold, high contrast, kinetic. No softness. | Pure ambition — "Go." Fierce, competitive, zero sentimentality. | Startup grind, sports motivation, hustle, bold declarations |

### 21.4 Feeling → Track filter

Hard filter. Blocked tracks (❌) are hidden from the UI when that feeling is selected.

| Feeling | A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|---------|:-:|:-:|:-:|:-:|:-:|
| SV-F1 Rise & Shine | ✅ | ✅ | ✅ | ✅ | ✅ |
| SV-F2 Still Waters | ❌ | ✅ | ✅ | ❌ | ✅ |
| SV-F3 Bittersweet | ❌ | ✅ | ✅ | ❌ | ✅ |
| SV-F4 Everyday Calm | ❌ | ✅ | ✅ | ✅ | ✅ |
| SV-F5 Fire & Drive | ✅ | ❌ | ✅ | ✅ | ❌ |

### 21.5 Custom text input step

The final step in all Suvichar flows. The user types the actual quote / suvichar to display on the poster.

**Behaviour:**
- Free-text textarea, no character limit enforced (soft guidance only — keep < ~120 chars for legibility).
- Required — Next / Generate is disabled until non-empty.
- Entered text replaces "Suvichar / Quote" everywhere in the prompt output.
- In Firefly with-text mode: `Clean "[user quote]" text in decorative font in the text zone`.
- In all other prompts: atmosphere and scene language remain category-specific; the text content itself is what the user typed.

**UI label:** "Your Quote" / "अपना सुविचार लिखें"

### 21.6 Suvichar illustration catalogue (40 items)

Illustrations are browsed by semantic category. GM carry-over items appear inside the relevant category — there is no separate "Carry-overs" bucket.

**Universality key:**
- **U** = Universal — works for all 5 feelings.
- **R** = Restricted — shown only for the listed feelings, hidden for others.

#### 21.6.1 Abstract (4 items)

| ID | Name | Description | U/R | Feeling Restriction | Archetypes |
|----|------|-------------|:---:|---------------------|------------|
| SV-I01 | Ink Brush Stroke | Single bold sumi-e brushstroke, black or deep colour on neutral | R | F2, F3, F5 | A1, A2 |
| SV-I02 | Geometric Shards | Fragmented low-poly angular shapes, sharp and bold | R | F5 | A1, A2 |
| SV-I03 | Gradient Orb | Blurred radial light bloom as a placed accent element | **U** | — | A1, A2 |
| SV-I04 | Splatter / Paint Burst | Dynamic ink or paint splatter, energy and expression | R | F1, F5 | A1, A2 |

#### 21.6.2 Nature & Landscape (17 items, includes GM carry-overs)

| ID | Name | Description | U/R | Feeling Restriction | Archetypes | Origin |
|----|------|-------------|:---:|---------------------|------------|--------|
| GM-I2-01 | Sunrise over Green Hills | Golden horizon with soft valley mist | **U** | — | All | GM |
| GM-I2-04 | Morning Mist over River | Still water with golden mist rising | **U** | — | B1 | GM |
| GM-I2-05 | Sunrise over Ocean | Wide golden sea, sun on horizon | **U** | — | B1 | GM |
| GM-I2-06 | Mountain Peak at Golden Hour | Peak bathed in warm first light | **U** | — | B1, A2 | GM |
| GM-I2-08 | Rainbow after Morning Rain | Rainbow over green landscape | R | F1, F4 | B1, A2 | GM |
| GM-I3-01 | Marigold Garland (Genda) | Classic Indian flower garland | **U** | — | A1, A2 | GM |
| GM-I3-02 | Lotus in Full Bloom | Open lotus on still water, sacred | **U** | — | A1, A2, B1 | GM |
| GM-I6-01 | Bird Flock at Sunrise | V-formation birds in open sky | **U** | — | B1, A2 | GM |
| SV-I05 | Lone Tree (Silhouette) | Single bare or leafy tree against empty horizon | R | F2, F3, F4 | A1, A2, B1 | SV |
| SV-I06 | Mountain Range (Minimal) | Layered mountain silhouette, clean and minimal | **U** | — | A1, A2, B1 | SV |
| SV-I07 | Winding Path / Road | Path disappearing into distance, journey metaphor | **U** | — | B1 | SV |
| SV-I08 | Falling Leaves | Scattered autumn leaves in gentle drift | R | F2, F3, F4 | A1, A2 | SV |
| SV-I09 | Desert Dunes | Smooth sand dunes, minimalist, warm tones | R | F2, F4 | A1, A2, B1 | SV |
| SV-I10 | Stormy Sky | Dramatic sky, heavy clouds, high contrast | R | F3, F5 | B1 | SV |
| SV-I11 | Sunrays Through Trees | God rays filtering through a forest canopy | **U** | — | B1 | SV |
| SV-I12 | Crescent Moon & Stars | Delicate crescent moon with scattered stars | R | F2, F3 | A1, A2 | SV |
| SV-I13 | Ocean Waves (Minimal) | Simple rolling wave silhouette or horizon line | **U** | — | A1, A2, B1 | SV |

#### 21.6.3 Objects & Still Life (12 items, includes GM carry-overs)

| ID | Name | Description | U/R | Feeling Restriction | Archetypes | Origin |
|----|------|-------------|:---:|---------------------|------------|--------|
| GM-I4-01 | Lit Diya with Warm Glow | Single diya with halo | R | F2, F3, F4 | All | GM |
| GM-I1-01 | Steaming Chai Cup | Classic ceramic cup with rising steam | R | F4 | All | GM |
| SV-I14 | Open Book / Pages | Book open flat, pages in soft light | **U** | — | A1, A2, B1 | SV |
| SV-I15 | Hourglass | Classic hourglass with flowing sand | R | F2, F4 | A1, A2 | SV |
| SV-I16 | Compass | Old brass compass — direction and purpose | **U** | — | A1, A2 | SV |
| SV-I17 | Coffee / Tea Cup (Desk) | Cup on desk beside a notebook | R | F4 | A2, B1 | SV |
| SV-I18 | Quill Pen & Inkwell | Writer's tool — knowledge, craft, expression | R | F2, F4 | A1, A2 | SV |
| SV-I19 | Lantern (Glowing) | Single glowing lantern, warm light in darkness | R | F2, F3, F4 | A1, A2 | SV |
| SV-I20 | Trophy / Medal | Clean minimal trophy silhouette | R | F1, F5 | A1, A2 | SV |
| SV-I21 | Key (Ornate / Minimal) | A key — metaphor for opportunity, unlocking | **U** | — | A1, A2 | SV |
| SV-I22 | Magnifying Glass | Curiosity, discovery, looking closer | R | F2, F4 | A1, A2 | SV |
| SV-I23 | Seed / Sapling | Small plant emerging from soil — growth | R | F1, F4 | A1, A2 | SV |

#### 21.6.4 Fire & Energy (3 items)

| ID | Name | Description | U/R | Feeling Restriction | Archetypes |
|----|------|-------------|:---:|---------------------|------------|
| SV-I24 | Flame / Fire | Single clean flame — ambition, passion | R | F1, F5 | A1, A2 |
| SV-I25 | Lightning Bolt | Bold graphic lightning, energy and power | R | F5 | A1, A2 |
| SV-I26 | Rising Sun (Graphic) | Stylised graphic rising sun with rays, bold | R | F1, F5 | A1, A2 |

#### 21.6.5 Silhouettes — B1 only (4 items)

| ID | Name | Description | U/R | Feeling Restriction | Archetypes |
|----|------|-------------|:---:|---------------------|------------|
| SV-I27 | Arms Raised — Victory | Figure arms raised against sky | R | F1, F5 | B1 |
| SV-I28 | Seated / Meditating | Person in stillness, introspective | R | F2, F3, F4 | B1 |
| SV-I29 | Walking Alone | Figure walking on road or beach | R | F2, F3 | B1 |
| SV-I30 | Running / Sprinting | Dynamic running figure, motion and drive | R | F1, F5 | B1 |

#### 21.6.6 Catalogue summary

| Category | Total | Universal (U) | Restricted (R) |
|----------|:-----:|:-------------:|:--------------:|
| Abstract | 4 | 1 (25%) | 3 (75%) |
| Nature & Landscape | 17 | 10 (59%) | 7 (41%) |
| Objects & Still Life | 12 | 4 (33%) | 8 (67%) |
| Fire & Energy | 3 | 0 | 3 (100%) |
| Silhouettes (B1 only) | 4 | 0 | 4 (100%) |
| **Total** | **40** | **15 (38%)** | **25 (62%)** |

For any given feeling, the always-visible pool = 15 universal items minimum, before restricted items are added.

### 21.7 Suvichar sub-illustration accent library (SV-ACC)

When a main illustration is selected, the system automatically assigns small secondary accent props (A2 density, B1 supporting props). For Suvichar these are drawn from the `SV-ACC-*` set rather than the GM-themed `ACCENT_ITEMS`, ensuring the supporting props match the contemplative quote-card aesthetic.

| ID | Name | Photo Desc (B1) | Illustration Desc (A2) |
|----|------|----------------|------------------------|
| SV-ACC-01 | Scattered Autumn Leaves | a few scattered dried autumn leaves on the ground | a few small illustrated autumn leaves scattered nearby |
| SV-ACC-02 | Bookmark | a slim ribbon bookmark peeking out from a book | a small illustrated ribbon bookmark tucked into the scene |
| SV-ACC-03 | Pen Nib / Ink Drop | a calligraphy pen nib or small ink drop on the surface | a tiny illustrated pen nib or ink drop accent |
| SV-ACC-04 | Smooth River Pebbles | two or three smooth rounded river pebbles on the surface | two or three small illustrated smooth pebbles |
| SV-ACC-05 | Dried Pressed Flower | a single dried pressed flower or botanical sprig | a small illustrated dried pressed botanical |
| SV-ACC-06 | Simple Candle Stub | a short unadorned candle with a small gentle flame | a small illustrated slim candle with a tiny flame |

These supplement (not replace) the shared `ACCENT_ITEMS` library — items like Fallen Petals (ACC-08), Distant Birds (ACC-10), Cobblestone Path (ACC-12), Single Butterfly (ACC-27), Reading Glasses (ACC-18), and Potted Plant (ACC-19) are also used where contextually appropriate.

#### Sub-element mapping per main illustration (representative)

| Main Illustration | B1 Sub-Props | A2 Sub-Accents |
|-------------------|-------------|----------------|
| Lone Tree | Distant Birds, Scattered Leaves, Fallen Petals | Scattered Leaves, Fallen Petals, Distant Birds |
| Mountain Range | Distant Birds, Wet Leaves, Smooth Pebbles | Smooth Pebbles, Distant Birds, Wet Leaves |
| Falling Leaves | — | Scattered Leaves, Fallen Petals, Butterfly |
| Open Book | Reading Glasses, Bookmark, Pen Nib | Reading Glasses, Bookmark, Pen Nib |
| Coffee / Tea Cup | Reading Glasses, Bookmark, Potted Plant | — |
| Lantern | — | Candle Stub, Dried Flower, Fallen Petals |
| Hourglass | — | Smooth Pebbles, Dried Flower, Fallen Petals |
| Crescent Moon | — | Candle Stub, Dried Flower, Fallen Petals |
| Seed / Sapling | — | Smooth Pebbles, Fallen Petals, Butterfly |
| Silhouettes (B1) | Distant Birds / Scattered Leaves / Smooth Pebbles (per pose) | — |

### 21.8 Prompt context — Suvichar variables

| Prompt Element | Good Morning | Suvichar |
|----------------|-------------|----------|
| Hero text | "Good Morning" | User-typed quote (entered in Custom Text step) |
| Scene atmosphere | `early morning Indian setting` | `contemplative quote-card scene` |
| Scene authenticity | `real Indian morning setting` | `real, unposed contemplative scene` |
| Gem setting context | `early morning in India` | `a contemplative natural or interior scene` |
| Light / time context | `natural and time-appropriate for early morning` | `natural and atmospheric` |
| Style mood word | `morning` | `quote` |
| Category label | `Good Morning` | `Suvichar / Quote` |

These swap automatically through `getCategoryAtmosphere()` when category is `'suvichar'`. The GM values are byte-identical to the original framework — no GM prompts are affected.

### 21.9 Suvichar layout bias

Guidance, not a hard filter.

| Layout | Suvichar Suitability | Reason |
|--------|---------------------|--------|
| L2 — Overlay / Text Centre | ★ Best | Quote reads full canvas with atmospheric illustration behind |
| L5 — Text Bottom | ★ Best | Illustration fills top, quote anchors at base — classic card format |
| L1 — Text Top | ✓ Works | Good for short punchy quotes |
| L6 — Text Centre (frame) | ✓ Works | Clean frame + centred quote — strong for A1 archetype |
| L3 / L4 — Text Left / Right | ~ With Care | Works only with Small illustration size |

### 21.10 What does NOT change for Suvichar

- 3 archetype families (A1, A2, B1) and their wizard flows (extended only with Feeling pre-step and Custom Text post-step)
- 5 tracks (A–E) and their colour palettes, font pools, motif sets
- Background finish options per track — Suvichar uses the same per-track finishes as Good Morning (no additions, no removals)
- Illustration render style step — inherited per track, no locking (all illustrations follow track default)
- Illustration size — all three sizes available (Small / Medium / Large), no cap
- All 6 layouts (L1–L6) and frame / overlay compatibility rules
- Prompt builder logic for all 5 platforms (Firefly with-text, Firefly no-text, Midjourney, Leonardo, Gemini)
- Shared ACCENT_ITEMS library (ACC-01..ACC-30) — still used where contextually appropriate alongside SV-ACC-* items
- Density auto-calculation for A2
- Intensity controls
- Character limits and prompt construction helpers (`stripHex`, `trunc`)

---

# Part 4 — Overlay Pack System (v2)

## 22. Overlay Architecture & Levers

An overlay is a thin reusable content modifier sitting between a base category and the user-facing Occasion picker. The user picks the overlay at Step 1 (alongside category and archetype). The overlay's effects are applied **before any downstream wizard step renders**.

An overlay has exactly **four levers** plus prompt-level keyword additions that follow from these.

### Lever 1 — Track Filtering (Hard Block)

An overlay can **hide incompatible tracks** entirely. Blocked tracks are hidden from the Track step, not dimmed.

**Rationale:** Some overlay + track combinations produce visual contradictions. Devotional content in an Artsy Playful doodle style feels disrespectful. Cricket in a Soft & Warm pastel style feels limp.

**Master Track Filter Table:**

| Overlay | A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|---------|:-:|:-:|:-:|:-:|:-:|
| Devotional | ✅ | ✅ | ✅ | ❌ | ✅ |
| Summer | ✅ | ✅ | ✅ | ✅ | ✅ |
| Rain / Monsoon | ❌ | ✅ | ✅ | ✅ | ✅ |
| Cricket / IPL | ✅ | ✅ | ✅ | ✅ | ❌ |

**Why each block:**
- **Devotional blocks D:** Playful doodle / cartoon treatment of sacred symbols (Om, temple, diya) feels tonally wrong. Devotional needs dignity — ornate (A), modern (B), minimal (C), or soft (E) all work.
- **Rain blocks A:** Shiny Maximal's gold sparkle, high gloss, and ornate energy contradicts monsoon's overcast, muted, cosy mood. Rain is naturally muted — desi (B), minimal (C), playful (D), or soft (E) all work.
- **Cricket blocks E:** Soft & Warm's pastel watercolour and gentle energy undercuts cricket's adrenaline. Sports needs punch — shiny (A), modern (B), minimal (C), or playful (D) all work.
- **Summer blocks nothing:** Summer's bright, vibrant energy works across all visual styles.

### Lever 2 — Illustrations: Restrict Base + Add New

| Action | Mechanic | Example |
|--------|---------|---------|
| **Add** themed illustrations | 8–15 new items added to the base category's pool. Tagged with archetype compatibility (A1, A2, B1) like any illustration. | Devotional adds: Temple Silhouette, Praying Hands, Om Symbol, etc. |
| **Restrict** base illustrations | Specific base items hidden when this overlay is active. Listed explicitly by ID — not by category. | Cricket on Good Morning hides "Lotus Flower" and "Candle / Diya" |

**Result:** User sees `(base pool − restricted items) + overlay items`.

Restriction is optional. Most overlays will only add, not restrict. Restrict only when a base item actively clashes with the overlay's energy.

### Lever 3 — Motifs & Decor: Swap + Add per Track

| Action | Mechanic | Example |
|--------|---------|---------|
| **Swap** specific motifs | Replace named base motifs with overlay-specific ones, per track. 1:1 replacement — total motif count per track stays the same. | Devotional on Track A: swap "Sparkle Cluster" → "Om with Gold Halo" |
| **Add** motifs | Add 1–2 extra motifs on top of existing set, per track. Use sparingly — too many motifs crowds the frame. | Rain on Track D: add "Doodle Raindrop Border" alongside existing set |

**How it maps to archetypes:**
- **A1 Frame Decoration:** Swapped / added motifs appear in the Frame Decoration Level options (Plain / Simple / Detailed). Same 3-level system — the motifs themselves change, not the levels.
- **A2 Accent Density:** Swapped / added motifs feed into the density auto-calculator's accent pool. Same density math — different items in the pool.

### Lever 4 — Frame Types: Restrict or Unlock Special

| Action | Mechanic | Example |
|--------|---------|---------|
| **Restrict** | Hide specific frame types (F1–F5) that don't work with this overlay. Hard filter — hidden from UI. | Cricket restricts F5 (Arch / Canopy) — too ornate for sports energy |
| **Unlock special** | Make a special frame type available ONLY when this overlay is active. Defined as a new F-code (F6+). | Devotional unlocks F6 "Temple Arch" — curved temple gopuram silhouette overhead |

**This lever is optional.** Most overlays will not touch frame types at all. Only use when there's a strong visual reason.

---

## 23. What an Overlay Cannot Change

Hard rule. An overlay cannot touch anything below this line, regardless of context.

| Element | Owned by | Why untouchable |
|---------|----------|----------------|
| Hero text | Base Category | "Good Morning" stays "Good Morning" — overlay is flavour, not greeting |
| Colour palettes | Track (Framework) | Palette is a track property |
| Font pairings | Track (Framework) | Same |
| Render styles | Track (Framework) | How it's rendered is the track's job |
| Layouts (L1–L6) | Framework | Composition rules are structural, not thematic |
| Archetypes (A1, A2, B1) | Framework | All archetypes remain available — never filtered |
| Illustration size options | Framework / Category | Size is a canvas decision, not a theme decision |
| Background finishes | Framework / Track | Cross-category only — overlay doesn't add finishes |
| Wizard flow / step order | Framework | No new steps added (overlay selected pre-wizard) |
| Prompt builder functions | Framework | Same functions, different variable values |
| Density auto-calculation | Framework | Math is the same — pool contents change |
| Intensity controls | Framework | Same |

**Note:** Tracks are framework-owned, but overlays CAN filter which tracks are shown (Lever 1). The tracks themselves don't change — they're just hidden when incompatible.

### Prompt-Level Additions

An overlay doesn't change prompt builder functions — it **appends** to the variables that feed into them:

| Prompt element | How overlay modifies it |
|----------------|------------------------|
| **Atmosphere keywords** | Overlay keywords are appended after base category's atmosphere. E.g., base: `"warm golden morning light, India morning atmosphere"` + overlay: `", monsoon atmosphere, overcast sky, rain-washed freshness"` |
| **Mood keywords** | Same append logic. Base mood + overlay mood. |
| **Negative terms** | Overlay negatives are appended to base + archetype negatives. Overlay can only ADD negatives, never remove base negatives. |
| **Scene context (B1)** | Overlay context is appended to base's B1 scene description. E.g., base: `"morning scene in India"` + overlay: `", temple courtyard, devotional setting"` |

---

## 24. Overlay × Base Compatibility Matrix

Not every overlay makes sense with every base category. This is a **hard rule** — the system only offers an overlay within a base category when the pairing is defined here as ✅.

### 24.1 Compatibility Matrix

| Overlay | Good Morning | Suvichar | Birthday | Rationale summary |
|---------|:---:|:---:|:---:|-------------------|
| Devotional | ✅ | ✅ | — | Devotional morning + devotional wisdom are natural. Devotional birthday is awkward — birthday is celebration-first, not prayer. |
| Summer | ✅ | ✅ | ✅ | Summer flavour works everywhere — seasonal energy is universally composable. |
| Rain / Monsoon | ✅ | ✅ | — | Monsoon morning + monsoon wisdom are atmospheric. Rainy birthday feels dampened — birthday wants bright energy, not overcast cosy. |
| Cricket / IPL | ✅ | — | ✅ | Cricket morning + cricket birthday are both high-energy celebrations. Cricket Suvichar is a mismatch — motivational quotes need universality, not sports branding. |

### 24.2 Detailed Rationale — Exclusions

**Devotional × Birthday — excluded.** Birthday's emotional lane is celebration — cake, balloons, confetti, party energy. Devotional's emotional lane is reverence — temple, prayer, sacred stillness. Composing them creates a tonal clash: the overlay tries to make the scene sacred while the base category's illustrations and hero text ("Happy Birthday") push celebration. A user wanting a blessing-style birthday would use a Puja Thali illustration from the Birthday base catalogue (BD-I15) without needing the full devotional overlay. Separately, the devotional overlay's illustration restrictions (which strip party-energy items) would gut the Birthday illustration pool, leaving almost nothing celebratory.

**Rain / Monsoon × Birthday — excluded.** Rain / Monsoon's mood is cosy, introspective, overcast — chai on a window ledge, puddle reflections, grey skies. Birthday's mood is bright, outward, joyful. The overlay's atmosphere keywords (`overcast sky, soft diffused rain light, petrichor mood`) directly contradict birthday's festive energy. Additionally, Rain blocks Track A (Shiny Maximal), which is one of Birthday's strongest tracks — gold foil balloons, confetti bursts, ornate gift bows all live in Track A's energy. Removing Track A from Birthday strips its most natural aesthetic lane.

**Cricket / IPL × Suvichar — excluded.** Suvichar is a wisdom / quote category. The hero text is a thought-provoking quote, not a greeting. Cricket branding (stadium, bat, jersey, scoreboard) around a philosophical quote creates a jarring mismatch — the visual screams "match day" while the text says something contemplative about life. Suvichar also uses a Feeling system (5 feelings) that has no natural mapping to cricket energy. A motivational sports quote is a niche use case better served by a future "Sports Motivation" base category with its own text library, not by forcing cricket visuals onto a general wisdom framework.

### 24.3 What This Means for the Occasion Picker

The Occasion picker (flat list at Step 1) only shows valid combinations. For each base category, the available overlays are:

| Base Category | Available Overlays |
|---------------|-------------------|
| Good Morning | Devotional, Summer, Rain / Monsoon, Cricket / IPL |
| Suvichar | Devotional, Summer, Rain / Monsoon |
| Birthday | Summer, Cricket / IPL |

**Implementation note:** This compatibility table is a config lookup, not a runtime filter. When building the occasion list for a base category, only include overlay options from this table. Invalid combinations never appear in the UI. In the implementation this is encoded via each overlay's `appliesTo: string[]` field.

### 24.4 Future Base Categories

When a new base category is added (e.g., Diwali, Eid, Holi), the overlay compatibility table must be extended. Apply the same logic:

1. Does the overlay's mood complement or contradict the base category's emotional lane?
2. Does the overlay's track filtering remove a critical track for this base category?
3. Does the overlay's illustration restriction gut the base pool?
4. Does the overlay's visual branding clash with the hero text?

If any answer raises a strong flag → exclude the pairing.

---

## 25. Overlay × Track Master Filter

(Repeated here as the master reference; same data as Section 22 Lever 1.)

| Overlay | A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|---------|:-:|:-:|:-:|:-:|:-:|
| Devotional | ✅ | ✅ | ✅ | ❌ | ✅ |
| Summer | ✅ | ✅ | ✅ | ✅ | ✅ |
| Rain / Monsoon | ❌ | ✅ | ✅ | ✅ | ✅ |
| Cricket / IPL | ✅ | ✅ | ✅ | ✅ | ❌ |

---

## 26. Firefly Prompt Budget & Templates

### 26.1 The Constraint

Adobe Firefly has a hard character limit: **≤ 950 characters** for both With-Text and No-Text prompt variants. This applies to all archetypes (A1, A2, B1). The existing `trunc()` function and per-component character caps in the prompt generator enforce this.

The overlay system adds new content to prompts. These additions must fit **within the existing 950-char budget** — they do not get extra characters. Overlays inject through existing variable slots, not new ones.

### 26.2 Prompt Template Formula — A1 / A2 (Illustrated) with Overlay

Without overlay (framework default):

```
[SUBJECT]. [ILLUSTRATION_RENDERING_STYLE]. [FINISH_PROMPT]. [MOTIF_PROMPT].
[TRACK_STYLE], [COLOUR_DESC], [CUSTOMIZATION_PROMPT].
Portrait 9:16 for mobile. Content type: Art. Stylize: 80.
Do not include any text, letters, words, typography, watermarks, logos, or minimalist elements.
```

With overlay active:

```
[SUBJECT]. [ILLUSTRATION_RENDERING_STYLE]. [FINISH_PROMPT]. [OVERLAY_MOTIF_PROMPT].
[TRACK_STYLE], [OVERLAY_ATMOSPHERE_COMPACT], [COLOUR_DESC], [CUSTOMIZATION_PROMPT].
Portrait 9:16 for mobile. Content type: Art. Stylize: 80.
Do not include any text, letters, words, typography, watermarks, logos,
[OVERLAY_NEGATIVE_GUARD], or minimalist elements.
```

**Variable-by-variable changes:**

| Variable | Without overlay | With overlay | Notes |
|----------|----------------|-------------|-------|
| `[SUBJECT]` | Base illustration from category pool | Illustration from `(base pool − restricted) + overlay added` — same slot, different item | If user picks an overlay illustration (e.g., OV-DEV-I09 Temple Silhouette), its name + desc flow into `[SUBJECT]` exactly like any base illustration. No format change. |
| `[ILLUSTRATION_RENDERING_STYLE]` | Track render style (unchanged) | Same — overlay cannot touch render styles | No change. |
| `[FINISH_PROMPT]` | BG finish from track (unchanged) | Same — overlay cannot touch finishes | No change. |
| `[MOTIF_PROMPT]` → `[OVERLAY_MOTIF_PROMPT]` | Base motif from track | Overlay-swapped motif (1:1 replacement) | E.g., Track A base "Sparkle Cluster" becomes "Om with Gold Halo". Same prompt position, different motif name. Compact Firefly motif format: `"Motif: [name] on border frame edges only, separated from illustration."` |
| `[TRACK_STYLE]` | Track style string (unchanged) | Same — overlay cannot touch track styles | No change. |
| `[OVERLAY_ATMOSPHERE_COMPACT]` *(new)* | *(empty — not present)* | Compact atmosphere keywords inserted before `[COLOUR_DESC]` | ≤ 50 chars. E.g., `spiritual devotional warmth, temple dawn glow`. |
| `[COLOUR_DESC]` | Palette hex + role desc (unchanged) | Same — overlay cannot touch palettes | No change. |
| `[CUSTOMIZATION_PROMPT]` | Intensity + preset (unchanged) | Same | No change. |
| `[OVERLAY_NEGATIVE_GUARD]` *(new)* | *(empty — not present)* | Short guard phrase appended to "Do not include" line | E.g., Devotional adds `party, nightclub, cartoon, doodle`. Cricket adds `calm, spiritual, soft, pastel`. Sits inside the existing fixed instruction line — no new prompt section. |

### 26.3 Prompt Template Formula — B1 (Photo Background) with Overlay

Without overlay:

```
Photorealistic [PHOTO_TRACK] [CATEGORY_LABEL] poster, 9:16 vertical, full-bleed photograph,
[CATEGORY_ATMOSPHERE].
[SCENE_DESCRIPTION].
[MOOD].
[PHOTO_TRACK_AESTHETIC].
[INTENSITY].
[TEXT_ZONE], [OVERLAY_STRENGTH] [OVERLAY_DESC].
[TEXT_INSTRUCTION]. DSLR quality, sharp focus.
```

With overlay active:

```
Photorealistic [PHOTO_TRACK] [CATEGORY_LABEL] poster, 9:16 vertical, full-bleed photograph,
[CATEGORY_ATMOSPHERE], [OVERLAY_ATMOSPHERE_COMPACT].
[SCENE_DESCRIPTION], [OVERLAY_B1_SCENE_COMPACT].
[MOOD], [OVERLAY_MOOD_COMPACT].
[PHOTO_TRACK_AESTHETIC].
[INTENSITY].
[TEXT_ZONE], [OVERLAY_STRENGTH] [OVERLAY_DESC].
[TEXT_INSTRUCTION]. DSLR quality, sharp focus.
```

**Variable-by-variable changes:**

| Variable | Without overlay | With overlay | Truncation cap |
|----------|----------------|-------------|:--------------:|
| `[CATEGORY_ATMOSPHERE]` | Base category atmosphere (e.g., `Indian morning atmosphere`) | Base + `, [OVERLAY_ATMOSPHERE_COMPACT]` appended | Part of header ~ 120 chars total |
| `[SCENE_DESCRIPTION]` | Base scene (e.g., `steaming chai on balcony railing, morning light`) | Base + `, [OVERLAY_B1_SCENE_COMPACT]` appended | `trunc(scenePh, 130)` |
| `[MOOD]` | Base mood (e.g., `warm, peaceful, serene`) | Base + `, [OVERLAY_MOOD_COMPACT]` appended | `trunc(mood, 90)` |
| `[PHOTO_TRACK_AESTHETIC]` | Unchanged | Same | `trunc(90)` |
| `[INTENSITY]` | Unchanged | Same | `trunc(80)` |

### 26.4 Compact Keyword Sets for Firefly (≤ 950 char budget)

Each overlay's "Prompt Additions" section defines **full** keyword lists for Midjourney, Leonardo, and Gemini (generous / no char limits). For **Firefly specifically**, only the compact versions below are used — these are the exact strings appended before per-component `trunc()` runs.

#### A1 / A2 Compact Strings

| Overlay | `[OVERLAY_ATMOSPHERE_COMPACT]` (≤ 50 chars) | `[OVERLAY_NEGATIVE_GUARD]` (appended to "Do not include" line) |
|---------|------|------|
| Devotional | `spiritual devotional warmth, temple dawn glow` | `party, nightclub, cartoon, doodle` |
| Summer | `bright Indian summer, harsh golden sunlight` | `cold, snow, fog, rain, overcast` |
| Rain / Monsoon | `Indian monsoon, overcast rain light, petrichor` | `harsh sunlight, desert, clear blue sky` |
| Cricket / IPL | `cricket match energy, stadium floodlight buzz` | `calm, spiritual, soft, pastel, watercolour` |

#### B1 Compact Strings

| Overlay | `[OVERLAY_ATMOSPHERE_COMPACT]` (≤ 50) | `[OVERLAY_MOOD_COMPACT]` (≤ 40) | `[OVERLAY_B1_SCENE_COMPACT]` (≤ 60) |
|---------|------|------|------|
| Devotional | `spiritual devotional warmth, temple dawn glow` | `reverent, peaceful, prayerful, blessed` | `temple courtyard at dawn, pooja room morning light` |
| Summer | `bright Indian summer, harsh golden sunlight` | `vibrant, sunny, refreshing, cheerful` | `Indian summer courtyard, bright harsh sunlight, mango trees` |
| Rain / Monsoon | `Indian monsoon, overcast rain light, petrichor` | `cosy, nostalgic, refreshing, contemplative` | `monsoon balcony, rain-washed streets, overcast lush green` |
| Cricket / IPL | `cricket match energy, stadium floodlight buzz` | `energetic, competitive, exciting, proud` | `floodlit cricket stadium evening, green pitch, packed stands` |

### 26.5 Assembled Example Prompts — Firefly

**Example 1: A1 + Track A + Devotional + Good Morning**

```
Shiny Maximal Good Morning poster, 9:16 vertical. BG: warm amber and deep terracotta,
radial gradient from bright centre to darker edges. Frame: full perimeter frame with
detailed Om with Gold Halo and Brass Bell Garland motifs. Text zone: upper 25%.
Illustration: lower area. Temple Silhouette: Hindu temple gopuram silhouette against
dawn sky, clean outline, backlit with golden-orange sky gradient. Ornamental vector
illustration with gold-foil fills, paisley and mandala borders. Spiritual devotional
warmth, temple dawn glow. Sparkle particles. Clean "Good Morning" text in decorative
font in the text zone, legible, not overlapping illustration.
```
*(~ 620 chars — well within 950)*

**Example 2: A2 + Track B + Summer + Birthday**

```
Modern Desi Happy Birthday poster, 9:16 vertical. BG: earthy warm palette, soft matte
finish. Scattered Block-Print Mango Motif and Nimbu Slice Corner accents around
illustration. Text zone: lower 25%. Illustration: upper area. Mango (Aam): Ripe
Alphonso mango, whole with one sliced half showing orange flesh, vibrant yellow-orange.
Contemporary Indian editorial illustration, warm earthy restraint. Bright Indian
summer, harsh golden sunlight. Accents: Matka Icon, same style. Balanced composition.
Clean "Happy Birthday" text in decorative font in the text zone, legible, not
overlapping illustration.
```
*(~ 640 chars — well within 950)*

**Example 3: B1 + Track B + Rain / Monsoon + Good Morning**

```
Photorealistic Modern Desi Good Morning poster, 9:16 vertical, full-bleed photograph,
India morning atmosphere, Indian monsoon, overcast rain light, petrichor. Steaming
cutting chai glass on window ledge, rain-streaked glass behind, blurred wet street
outside, warm amber tea colour, monsoon balcony, rain-washed streets, overcast lush
green. Warm, peaceful, cosy, nostalgic, refreshing, contemplative. Muted earthy tones,
desaturated naturals, editorial restraint. Medium close-up, environmental detail.
Text zone: upper third, subtle semi-transparent dark overlay. Clean "Good Morning"
text in white decorative font in the text zone, legible. DSLR quality, sharp focus.
```
*(~ 640 chars — well within 950)*

### 26.6 Character Budget Summary

| Archetype | Without overlay (typical) | With overlay (typical) | With overlay (worst case) | Headroom at 950 |
|-----------|:---:|:---:|:---:|:---:|
| A1 | 650–750 | 700–800 | ~ 855 | ~ 95 chars |
| A2 | 700–800 | 750–850 | ~ 880 | ~ 70 chars |
| B1 | 550–680 | 600–730 | ~ 780 | ~ 170 chars |

The worst case (A2 + Track A + Sparkle particles + longest overlay) reaches ~ 880. The final `substring(0, 950)` safety net clips at the last complete word if anything ever exceeds.

### 26.7 How Overlay Additions Enter Each Variable Slot

| Overlay addition | Variable slot it enters | Existing `trunc()` cap | Impact |
|-----------------|------------------------|:---:|------|
| Atmosphere keywords | `[OVERLAY_ATMOSPHERE_COMPACT]` → appended to header (A1 / A2) or `[CATEGORY_ATMOSPHERE]` (B1) | Header ~ 50–120 | + 30–50 chars. Bounded by compact keyword set. |
| Mood keywords | `[OVERLAY_MOOD_COMPACT]` → appended to `[MOOD]` (B1 only) | 90 | Appended before `trunc()`. If combined exceeds 90, clips at last comma. |
| Negative guard | `[OVERLAY_NEGATIVE_GUARD]` → appended to "Do not include" line | N/A (fixed instruction) | + 20–40 chars. Sits inside existing instruction, not a new section. |
| B1 Scene context | `[OVERLAY_B1_SCENE_COMPACT]` → appended to `[SCENE_DESCRIPTION]` | 130 | Appended before `trunc()`. If combined exceeds 130, clips at last comma. |
| Motif swap | `[OVERLAY_MOTIF_PROMPT]` → replaces `[MOTIF_PROMPT]` | ~ 80 | 1:1 replacement — same format, different name. No length change. |
| Illustration swap | `[SUBJECT]` → from overlay pool instead of base pool | ~ 180 | Different item, same slot. No additional budget. |

**Key design principle:** Overlay keywords flow through the same `[VARIABLE]` injection pipeline defined in v20. No new builder functions, no new prompt sections, no structural changes. The `trunc()` per-component caps handle overflow gracefully — if base + overlay exceed a slot's cap, the combined string is clipped at the last comma (preserving complete keyword phrases).

### 26.8 Implementation Guidance

1. **Same template structure as v20.** Overlay content injects through existing `[VARIABLE]` slots. No new prompt sections.
2. **Compact keyword sets (Section 26.4) are mandatory for Firefly.** Full keyword lists are for Midjourney / Leonardo / Gemini only.
3. **Negatives sit inside the existing "Do not include" line.** They don't create a new prompt section — they extend the existing guard phrase. No budget impact on the main prompt body.
4. **`trunc()` handles overflow.** Every variable slot has a per-component char cap. If base + overlay content exceeds the cap, `trunc()` clips at the last comma. No keywords are ever cut mid-word.
5. **Final safety net:** `substring(0, 950)` on the assembled prompt. This only fires if multiple components simultaneously hit their upper bounds — extremely unlikely with compact keyword sets.
6. **Test after every new overlay.** Generate a worst-case prompt (A2 + Track A + longest illustration + overlay active) and verify ≤ 950 chars.

---

## 27. Overlay Pack Spec Template

Every overlay pack follows this structure:

```
OVERLAY PACK: [Name]
APPLIES TO: [List of base categories — must be in Section 24 matrix]
SEASONAL: Yes/No (if Yes, specify active window)

TRACK FILTER:
  Block: [Track letters to hide, e.g., "D" or "None"]
  Allow: [Remaining tracks]

ILLUSTRATIONS
  Add (with archetype tags, grouped by sub-category):
    [Category header]
    [ID] [Name] — [Description] — [A1, A2, B1]
    ...
  Restrict from base (by item name — listed per base category):
    [Base Category]: [Item 1], [Item 2], ...

MOTIFS & DECOR (per allowed track only)
  Track [X] — [Name]:
    Swap: [Base motif] → [Overlay motif + description]
    Add: [New motif + description] (if any)
  (repeat for each allowed track)

FRAME TYPES
  Restrict: [F-codes to hide, or "None"]
  Unlock: [Special frame + description, or "None"]

PROMPT ADDITIONS (full — for Midjourney, Leonardo, Gemini)
  Atmosphere: [keywords to append]
  Mood: [keywords to append]
  Negatives: [terms to append]
  B1 Scene Context: [scene description to append]

PROMPT ADDITIONS — FIREFLY COMPACT (≤950 char budget)
  Atmosphere: [≤50 chars]
  Mood: [≤40 chars]
  B1 Scene: [≤60 chars]
  (Negatives: not in Firefly prompt — no entry needed)
```

---

## 28. Overlay Pack 1: Devotional

**Applies to:** Good Morning, Suvichar.
**Seasonal:** No — always available.

### 28.1 Track Filter

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ❌ | ✅ |

**Blocked:** Track D — playful doodle / cartoon treatment of sacred symbols (Om, temple, diya) feels tonally disrespectful. Devotional content needs visual dignity.

### 28.2 Illustrations — Add (14 items)

#### Sacred Symbols & Objects

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-DEV-I01 | Om Symbol | Stylised Om (ॐ) — clean single form, not overly ornate unless Track A. Warm gold or deep saffron tone. | A1, A2 |
| OV-DEV-I02 | Temple Bell | Brass temple bell, traditional rounded shape with clapper visible. Warm metallic tones, slight patina. | A1, A2 |
| OV-DEV-I03 | Incense Stick (Burning) | Single agarbatti in holder, thin smoke trail curling upward in gentle S-curve. Warm amber tones. | A1, A2 |
| OV-DEV-I04 | Rudraksha Mala | Prayer bead strand in gentle curve or coil, individual beads visible. Deep brown with subtle texture. | A1, A2 |
| OV-DEV-I05 | Shankh (Conch Shell) | Sacred conch shell, side view showing spiral. Creamy white with soft pink interior. | A1, A2 |

#### Flora & Nature (Devotional)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-DEV-I06 | Tulsi Plant (Pot) | Sacred tulsi in traditional earthen tulsi vrindavan pot with vermillion marks. Green leaves, terracotta base. | A1, A2 |
| OV-DEV-I07 | Jasmine Garland (Mogra) | String of white mogra flowers, gently curved. Pure white buds against warm background. | A1, A2 |
| OV-DEV-I08 | Banana Leaf with Offerings | Green banana leaf laid flat with small pooja items (kumkum, turmeric, flower petals, rice grains). | A1, A2 |

#### Scenes & Settings (devotional atmosphere)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-DEV-I09 | Temple Silhouette | Hindu temple gopuram silhouette against dawn sky. Clean outline, backlit with golden-orange sky gradient. | A1, A2, B1 |
| OV-DEV-I10 | Praying Hands (Namaste) | Two hands joined in prayer / namaste, warm side-lighting. Hands only — no face visible. | A1, A2, B1 |
| OV-DEV-I11 | Ganga / River at Dawn | Sacred river at dawn, stone ghats in foreground, temple spires in background. Golden reflection on water. | B1 |
| OV-DEV-I12 | Pooja Thali (Still Life) | Brass thali with lit diya, kumkum, rice, marigold flowers, brass bell. Morning light, warm tones. | A1, A2, B1 |
| OV-DEV-I13 | Temple Doorway (Interior) | View through carved temple doorway, warm light streaming in. Stone architecture, not a specific deity. | B1 |
| OV-DEV-I14 | Oil Lamp Row (Lit) | Row of 5–7 brass oil lamps (deepam) lit in a line, warm flame glow, shallow depth of field. | A1, A2, B1 |

### 28.3 Illustrations — Restrict from Base

#### From Good Morning (11 items)

| Restricted Item | Reason |
|----------------|--------|
| GM-I1-01 Steaming Chai Cup | Daily mundane — undercuts sacred morning atmosphere |
| GM-I1-05 Glass of Fresh Orange Juice | Too casual / modern health-trend — not devotional register |
| GM-I1-08 Tender Coconut Water | Beach / tropical casual — undercuts sacred atmosphere |
| GM-I2-08 Rainbow after Morning Rain | Too playful / cheerful for devotional solemnity |
| GM-I3-05 Sunflower Facing Sun | Too bright / cheerful / modern — not temple energy |
| GM-I3-09 Cherry Blossom Branches | Modern / urban / Japanese aesthetic — clashes with Indian devotional |
| GM-I5-04 Book and Chai on Morning Desk | Casual intellectual — not devotional |
| GM-I5-05 Morning Walk on Tree-Lined Path | Casual lifestyle — too secular |
| GM-I5-06 Watering Plants on Balcony | Casual domestic routine — too mundane for sacred |
| GM-I6-04 Parrot on Mango Branch | Too playful / bright — undercuts devotional gravity |
| GM-I6-06 Butterflies on Flowers at Dawn | Too light / whimsical for devotional |

#### From Suvichar (8 items)

| Restricted Item | Reason |
|----------------|--------|
| SV-I02 Geometric Shards | Angular / aggressive abstract — contradicts devotional softness |
| SV-I04 Splatter / Paint Burst | Dynamic / chaotic energy — contradicts meditative stillness |
| SV-I10 Stormy Sky | Too dark / dramatic — devotional morning is peaceful, not turbulent |
| SV-I20 Trophy / Medal | Achievement / competition — wrong register for devotional |
| SV-I22 Magnifying Glass | Analytical / secular curiosity — not devotional |
| SV-I25 Lightning Bolt | Aggressive energy — contradicts devotional calm |
| SV-I27 Silhouette Arms Raised | Victory / competition pose — sports energy, not devotional |
| SV-I30 Silhouette Running / Sprinting | Athletic / competitive — contradicts meditative stillness |

**Total restrictions:** 11 (GM) + 8 (SV) = 19 items blocked.

### 28.4 Motifs & Decor (per allowed track)

#### Track A — Shiny Maximal

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Sparkle cluster / confetti | Om with Gold Halo | Gold-foil Om symbol (ॐ) at 15–20mm scale, with concentric radiating halo lines. Embossed / raised feel. High-shine gold (#D4AF37). |
| Swap | Butterfly / seasonal accent | Brass Bell Garland | String of 5–7 small brass temple bells connected by gold thread, hung along frame edge. Each bell ~ 8mm, visible clappers. |
| Add | — | Diya Row (Gold) | 3–5 brass diyas with gold flame accents spaced evenly along frame base. Each flame has tiny sparkle highlight. |

#### Track B — Modern Desi

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Geometric accent | Rangoli Om Corner | Om symbol integrated into geometric rangoli quarter-pattern at each frame corner. Clean lines. Saffron + white palette. |
| Swap | Trending / seasonal | Tulsi Pot Accent | Small tulsi vrindavan vignette (~ 20mm) at bottom corner. Simple earthen pot, green leaves. |
| Add | — | Ghee Lamp Line | Thin horizontal row of small lit ghee lamps (3–5) at frame base. Modern clean rendering. Warm amber flame glow. |

#### Track C — Minimalist Classy

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Dot / line accent | Minimal Om Line | Om drawn with a single continuous line stroke. Thin (1px visual weight), clean, no fill. Warm grey or muted gold corner accent. |
| Swap | Geometric shape | Incense Smoke Trail | Single vertical thin line rising from bottom edge, with 2–3 gentle S-curves suggesting smoke. Barely-there opacity (30–40%). |

#### Track E — Soft & Warm

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Watercolour accent | Watercolour Diya | Soft-edge diya shape in warm ochre / saffron watercolour wash. Flame is a small warm yellow bleed. No hard edges. |
| Swap | Soft floral | Marigold Wash | Loose watercolour marigold garland — 3–4 blooms connected by green wash. Diffused edges, pigment pooling at petal tips. |
| Add | — | Incense Haze (Soft) | Gentle warm-toned haze / smoke wash along frame base. Very subtle (20–30% opacity). |

### 28.5 Frame Types

**Restrict:** None.
**Unlock:** F6 — Temple Arch.

| Code | Name | Description | Layout Compatibility |
|------|------|-------------|---------------------|
| F6 | Temple Arch | Curved temple gopuram / mandir arch silhouette as top frame element. Arch curves from top-left to top-right corners, descending to ~ 20% canvas height at the sides. Bottom edge is straight (no frame). Interior is fully open for text + illustration. Arch thickness varies by Frame Decoration Level: Plain = thin outline only, Simple = outline + small kalash at apex, Detailed = ornate carved arch with miniature temple motifs. | Best: L5 (text below arch), L2 (overlay under arch). Works: L1 (text inside upper arch curve). Avoid: L3, L4 (arch doesn't pair with side-text layouts — creates visual imbalance). |

### 28.6 Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `spiritual, sacred, devotional warmth, temple morning atmosphere, divine glow, sacred golden light` |
| Mood | `reverent, peaceful, prayerful, blessed, meditative, serene, devout` |
| Negatives | `party, nightclub, alcohol, modern urban, neon, loud, aggressive, cartoon, doodle, playful, comic, silly` |
| B1 Scene Context | `temple courtyard at dawn, devotional morning setting, sacred river ghats at sunrise, pooja room with morning light streaming in, incense smoke visible in golden light rays` |

#### Prompt Additions — Firefly Compact (≤ 950 char budget)

| Element | Compact value |
|---------|--------------|
| Atmosphere | `spiritual devotional warmth, temple dawn glow` |
| Mood | `reverent, peaceful, prayerful, blessed` |
| B1 Scene | `temple courtyard at dawn, pooja room morning light` |
| Negatives | *(not in Firefly prompt — no budget impact)* |

---

## 29. Overlay Pack 2: Summer

**Applies to:** Good Morning, Birthday, Suvichar.
**Seasonal:** Yes — April to June.

### 29.1 Track Filter

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ✅ | ✅ |

**Blocked:** None — summer's bright, vibrant energy works across all visual styles. A shiny gold mango and a watercolour mango are both valid.

### 29.2 Illustrations — Add (14 items)

#### Fruits & Food (Indian Summer)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-SUM-I01 | Mango (Aam) | Ripe Alphonso mango, whole with one sliced half showing orange flesh. Vibrant yellow-orange skin, green stem. | A1, A2 |
| OV-SUM-I02 | Mango Basket / Crate | Woven bamboo basket or wooden crate with 5–7 assorted mangoes. Market-fresh feel, leaves attached. | A1, A2, B1 |
| OV-SUM-I03 | Watermelon Slice | Bright red wedge-shaped slice with black seeds and green rind. Dripping juice detail. | A1, A2 |
| OV-SUM-I04 | Kulfi / Ice Cream | Traditional matka kulfi with pistachio crumble, or a bright orange ice cream stick. Frosty condensation. | A1, A2 |
| OV-SUM-I05 | Nimbu Paani (Lemonade) | Tall glass of lemon water with ice cubes, fresh mint sprig, condensation droplets. | A1, A2, B1 |
| OV-SUM-I06 | Aam Panna Glass | Glass of raw mango drink, pale green colour, mint garnish. Refreshing summer-specific Indian drink. | A1, A2 |

#### Summer Objects & Accessories

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-SUM-I07 | Hand Fan (Pankha) | Traditional Indian palm-leaf or bamboo fan. Textured, handmade feel. Cream / tan tones. | A1, A2 |
| OV-SUM-I08 | Sunglasses | Bold aviator or wayfarer sunglasses with reflective lenses showing sky. | A1, A2 |
| OV-SUM-I09 | Matka (Clay Water Pot) | Earthen clay matka with water condensation. Traditional Indian summer water cooler. Terracotta brown. | A1, A2 |
| OV-SUM-I10 | Straw Hat / Sun Hat | Woven straw sun hat, casual breezy, tan / natural tones with optional ribbon. | A1, A2 |

#### Scenes & Nature (Summer)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-SUM-I11 | Mango Tree | Laden mango tree branch with hanging fruits and green leaves. Dappled sunlight through canopy. | A2, B1 |
| OV-SUM-I12 | Ceiling Fan / Desert Cooler | Old-style 3-blade ceiling fan or desert cooler with khus curtain. Nostalgic Indian summer interior. | B1 |
| OV-SUM-I13 | Sunny Courtyard | Indian home courtyard in peak summer — bright harsh sunlight, long shadows, tulsi pot. Heat-haze optional. | B1 |
| OV-SUM-I14 | Sunflower | Single bright sunflower facing camera. Bold yellow petals, dark brown centre. | A1, A2 |

### 29.3 Illustrations — Restrict from Base

#### From Good Morning (5 items)

| Restricted Item | Reason |
|----------------|--------|
| GM-I2-04 Morning Mist over River | Mist implies cool / cold weather — contradicts summer heat |
| GM-I4-01 Lit Diya with Warm Glow | Indoor flame warmth in already-hot summer feels redundant |
| GM-I4-04 Incense Stick Smoke | Indoor smoky warmth — summer is about outdoor freshness |
| GM-I5-02 Meditating Figure at Sunrise | Too still / inward — summer energy is outward and active |
| GM-I6-05 Sarus Crane in Misty Field | Misty field = cool weather, contradicts summer |

#### From Birthday (4 items)

| Restricted Item | Reason |
|----------------|--------|
| BD-I13 Diya Cluster | Devotional / indoor — contradicts bright outdoor summer |
| BD-I15 Puja Thali | Devotional — not summer energy |
| BD-I19 Fireworks (Sky) | Night-sky fireworks contradict summer daylight context |
| BD-I28 Blowing Candles (Silhouette) | Dark / indoor intimate moment — contradicts bright summer |

#### From Suvichar (8 items)

| Restricted Item | Reason |
|----------------|--------|
| SV-I05 Lone Tree (Silhouette) | Barren / melancholic silhouette — too sombre for bright summer |
| SV-I08 Falling Leaves | Autumn imagery — wrong season |
| SV-I09 Desert Dunes | Barren dryness without "fun" framing — too harsh |
| SV-I10 Stormy Sky | Dark / dramatic — contradicts bright summer sky |
| SV-I12 Crescent Moon & Stars | Night imagery undercuts summer brightness |
| SV-I19 Lantern (Glowing) | Indoor warm glow — summer is about outdoor light |
| SV-I28 Silhouette Seated / Meditating | Too still / inward for summer's active energy |
| SV-I29 Silhouette Walking Alone | Too solitary / melancholic for summer's vibrant mood |

**Total restrictions:** 5 (GM) + 4 (BD) + 8 (SV) = 17 items blocked.

### 29.4 Motifs & Decor (per track — all 5 allowed)

#### Track A — Shiny Maximal

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Seasonal / floral | Gold Mango Cluster | 3–4 mangoes in triangular cluster with gold leaf accents and tiny gold sparkle highlights. Lush, ornate, max saturation. |
| Swap | Sparkle accent | Sunburst Medallion | Radiating gold sunburst motif at frame top-centre. 12–16 rays, embossed feel. |
| Add | — | Watermelon Wedge (Gold-rimmed) | Small watermelon slice motif with gold rind outline as corner accent. Playful but ornate. |

#### Track B — Modern Desi

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Seasonal | Block-Print Mango Motif | Mango silhouette filled with traditional Indian block-print pattern. Saffron + indigo on cream. Repeatable as border. |
| Swap | Floral | Nimbu Slice Corner | Lemon cross-section as geometric corner accent. Clean lines. Yellow with white pith detail. |
| Add | — | Matka Icon | Small clay pot silhouette with condensation dots. Simple 2-colour modern icon. |

#### Track C — Minimalist Classy

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Dot / line accent | Minimal Sun Arc | Thin quarter-circle arc at frame corner suggesting sun. Single line, ~ 1px weight. Muted gold. |
| Swap | Geometric | Citrus Outline | Single-line lemon / orange cross-section outline. No fill, just clean circular outline with segment lines. |

#### Track D — Artsy Playful

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Doodle | Doodle Mango | Hand-drawn mango with leaf, crayon style. Slightly wobbly outline, scribble fill in yellow-orange. |
| Swap | Sticker | Popsicle Sticker | Puffy ice-lolly orange-bar sticker, slightly 3D with highlight, playful bright colours. |
| Add | — | Doodle Sun (Smiling) | Hand-drawn smiling sun with wavy rays. Classic childhood circle face triangle rays. Warm yellow. |

#### Track E — Soft & Warm

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Watercolour floral | Watercolour Mango | Soft-edge mango in warm yellow-orange watercolour wash. Pigment pooling at base. Green leaf wet-on-wet bleed. |
| Swap | Soft accent | Pastel Citrus Slice | Gentle lemon half-slice in muted yellow-cream pastel. Soft edges, no hard outlines. |
| Add | — | Sun Glow Wash | Gentle warm-toned radial glow at frame top-centre. Very subtle (15–25% opacity). |

### 29.5 Frame Types

**Restrict:** None.
**Unlock:** None.

### 29.6 Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `bright Indian summer, warm harsh sunlight, peak daylight, hot season ambience, golden hour warmth, long shadows` |
| Mood | `vibrant, sunny, refreshing, cheerful, high-energy, bright, juicy, alive` |
| Negatives | `cold, snow, winter, fog, overcast, grey, dark, cloudy, sweater, blanket, rain, umbrella, monsoon, frost` |
| B1 Scene Context | `Indian summer setting, bright sunlight casting strong shadows, courtyard or veranda in afternoon heat, mango trees, earthen pots, summer morning freshness` |

#### Prompt Additions — Firefly Compact (≤ 950 char budget)

| Element | Compact value |
|---------|--------------|
| Atmosphere | `bright Indian summer, harsh golden sunlight` |
| Mood | `vibrant, sunny, refreshing, cheerful` |
| B1 Scene | `Indian summer courtyard, bright harsh sunlight, mango trees` |
| Negatives | *(not in Firefly prompt — no budget impact)* |

---

## 30. Overlay Pack 3: Rain / Monsoon

**Applies to:** Good Morning, Suvichar.
**Seasonal:** Yes — July to September.

### 30.1 Track Filter

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ❌ | ✅ | ✅ | ✅ | ✅ |

**Blocked:** Track A — Shiny Maximal's gold sparkle, high gloss, and ornate energy contradicts monsoon's overcast, muted, cosy mood. Rain is inherently muted and soft — the "maximum shine" lane feels like a visual clash.

### 30.2 Illustrations — Add (15 items)

#### Rain Elements

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-RAIN-I01 | Umbrella (Open, Colourful) | Bright open umbrella from above or side, raindrops bouncing off. Red, yellow, or multi-colour. | A1, A2 |
| OV-RAIN-I02 | Umbrella (Closed, Minimal) | Closed umbrella leaning against wall or held at side. Clean silhouette. | A1, A2 |
| OV-RAIN-I03 | Raindrops on Leaf | Macro: 3–5 clear water droplets on a single green leaf. Sharp focus on drops. | A1, A2, B1 |
| OV-RAIN-I04 | Puddle Reflection | Rain puddle reflecting sky, trees, or temple. Ground-level angle. Concentric ripple rings. | A2, B1 |
| OV-RAIN-I05 | Paper Boat | Small white / newspaper paper boat in gentle rainwater stream along roadside gutter. Childhood nostalgia. | A1, A2 |

#### Comfort & Nostalgia (Monsoon rituals)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-RAIN-I06 | Chai in Rain | Steaming cutting chai on window ledge, rain-streaked glass behind, blurred wet street outside. Warm amber tea colour. | A1, A2, B1 |
| OV-RAIN-I07 | Pakora / Bhajiya Plate | Fresh hot onion pakoras on steel plate or newspaper, steam rising, green chutney side. | A1, A2 |
| OV-RAIN-I08 | Wet Window Pane | Rain streaks running down glass, warm interior light glowing behind. Cosy indoor feel. | A1, A2, B1 |
| OV-RAIN-I09 | Person with Umbrella (Silhouette) | Solo figure walking with umbrella on wet road, seen from behind. Reflection on wet ground. | B1 |

#### Nature & Atmosphere (Monsoon landscape)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-RAIN-I10 | Monsoon Sky (Dramatic) | Heavy cumulus clouds, dark-grey with silver edges. Dramatic formations. Maybe one break of light. | B1 |
| OV-RAIN-I11 | Green Field in Rain | Lush green rice paddy with rain falling. Overcast light, saturated greens. Distant treeline. | B1 |
| OV-RAIN-I12 | Frog on Leaf | Small green frog on wet leaf with water droplets around it. Charming monsoon wildlife. | A1, A2 |
| OV-RAIN-I13 | Wet Marigold | Single marigold flower with rain droplets on petals. Vivid orange against grey-green BG. | A1, A2 |
| OV-RAIN-I14 | Rain on Rooftop | Rain hitting corrugated tin or tile rooftop. Splashing droplets frozen mid-bounce. | B1 |
| OV-RAIN-I15 | Peacock (Rain Dance) | Peacock with fanned tail in rain, classic monsoon image. Side view, feathers glistening. | A2, B1 |

### 30.3 Illustrations — Restrict from Base

#### From Good Morning (11 items)

| Restricted Item | Reason |
|----------------|--------|
| GM-I1-05 Glass of Fresh Orange Juice | Summer drink — not monsoon comfort drink |
| GM-I1-08 Tender Coconut Water | Beach / summer tropical — wrong season |
| GM-I2-01 Sunrise over Green Hills | Clear sky sunrise clashes with overcast monsoon |
| GM-I2-02 Sun Rays through Forest Trees | Sun rays = clear weather, not monsoon |
| GM-I2-05 Sunrise over Ocean Horizon | Clear sky sunrise — contradicts overcast |
| GM-I2-06 Mountain Peak at Golden Hour | Golden hour = clear sky, not monsoon |
| GM-I2-08 Rainbow after Morning Rain | Rainbow = after rain stops — contradicts "in rain" mood |
| GM-I3-05 Sunflower Facing Sun | Implies bright sunny day — not monsoon |
| GM-I5-01 Surya Namaskar Silhouette | Sun salutation outdoors — implies clear sunny sky |
| GM-I6-01 Bird Flock at Sunrise (V-Formation) | Birds in clear sunrise sky — not monsoon atmosphere |
| GM-I6-06 Butterflies on Flowers at Dawn | Butterflies don't fly in rain — wrong weather |

#### From Suvichar (8 items)

| Restricted Item | Reason |
|----------------|--------|
| SV-I09 Desert Dunes | Desert dryness directly contradicts rain / water context |
| SV-I20 Trophy / Medal | Achievement energy doesn't fit monsoon's contemplative mood |
| SV-I23 Seed / Sapling | Implies dry soil and growth — monsoon is about water, not planting |
| SV-I24 Flame / Fire | Open flame in rain feels contradictory |
| SV-I25 Lightning Bolt | Fire & Drive style — wrong energy for monsoon |
| SV-I26 Rising Sun (Graphic) | Bold graphic sun contradicts overcast monsoon sky |
| SV-I27 Silhouette Arms Raised | Victory pose — too energetic for monsoon's contemplative mood |
| SV-I30 Silhouette Running / Sprinting | Athletic energy in rain — contradicts monsoon's cosy / still mood |

**Total restrictions:** 11 (GM) + 8 (SV) = 19 items blocked.

### 30.4 Motifs & Decor (per allowed track — no Track A)

#### Track B — Modern Desi

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Seasonal | Block-Print Umbrella | Umbrella silhouette filled with traditional block-print pattern. Indigo + white on cream. |
| Swap | Floral | Monsoon Vine Border | Wet tropical vine with small white flowers along frame edge. Dewdrops on leaves. Green + white. |
| Add | — | Raindrop Bead String | Thin vertical string of stylised raindrops at frame edge. Modern geometric drops. Blue-grey tones. |

#### Track C — Minimalist Classy

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Dot accent | Minimal Raindrop Line | Thin vertical line of small raindrop-shaped dots, evenly spaced. Metallic grey or silver. |
| Swap | Line accent | Rain Streak (Fine) | 3–4 diagonal fine parallel lines (60° angle) suggesting rain. Sparse and elegant. |

#### Track D — Artsy Playful

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Doodle | Doodle Umbrella | Hand-drawn open umbrella with bouncy raindrop doodles around it. Wobbly outline, crayon fill. |
| Swap | Sticker | Paper Boat Sticker | Puffy paper-boat sticker, slightly 3D with shadow, riding a wavy blue line. Playful childhood. |
| Add | — | Doodle Cloud (Rainy) | Hand-drawn grey cloud with zigzag rain lines. Simple cheerful 2–3 clouds at different sizes. |
| Add | — | Frog Doodle | Tiny hand-drawn frog on lily pad with 2–3 raindrop doodles around. Charming corner accent. |

#### Track E — Soft & Warm

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Watercolour floral | Watercolour Raindrops | 5–7 soft-edge raindrop shapes in blue-grey watercolour wash. Varying sizes, pigment pooling at bottom. |
| Swap | Soft accent | Pastel Umbrella | Gentle closed umbrella outline in muted blue-grey pastel. Soft edges, no hard lines. |
| Add | — | Mist Wash | Light watercolour mist / fog wash along frame base. Very subtle (15–20% opacity), cool grey-blue. |

### 30.5 Frame Types

**Restrict:** None.
**Unlock:** None.

### 30.6 Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `Indian monsoon atmosphere, overcast sky, soft diffused rain light, rain-washed freshness, petrichor mood, humid green lushness` |
| Mood | `cosy, nostalgic, peaceful, contemplative, refreshing, romantic, warm-inside-while-cold-outside` |
| Negatives | `harsh sunlight, desert, dry, arid, bright blue sky, clear sky, scorching, drought, dust, snow, winter` |
| B1 Scene Context | `monsoon setting in India, rain-washed streets or balcony or window scene, wet reflective surfaces, heavy overcast or dramatic cloud sky, lush saturated green foliage, visible rain or recent rain evidence` |

#### Prompt Additions — Firefly Compact (≤ 950 char budget)

| Element | Compact value |
|---------|--------------|
| Atmosphere | `Indian monsoon, overcast rain light, petrichor` |
| Mood | `cosy, nostalgic, refreshing, contemplative` |
| B1 Scene | `monsoon balcony, rain-washed streets, overcast lush green` |
| Negatives | *(not in Firefly prompt — no budget impact)* |

---

## 31. Overlay Pack 4: Cricket / IPL

**Applies to:** Good Morning, Birthday.
**Seasonal:** Yes — April to June (IPL window), also during international Test / ODI / T20 series.

### 31.1 Track Filter

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ✅ | ❌ |

**Blocked:** Track E — Soft & Warm's pastel watercolour and gentle energy undercuts cricket's adrenaline. Sports needs visual punch — even minimal (C) works because "minimal + sharp" reads as sleek, but "soft + warm" reads as passive.

### 31.2 Illustrations — Add (15 items)

#### Equipment & Gear

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-CRK-I01 | Cricket Bat & Ball | Classic willow bat crossed diagonally with red leather ball. Iconic composition. Bat shows grain, ball shows seam. | A1, A2 |
| OV-CRK-I02 | Cricket Ball (Close-up) | Red leather cricket ball isolated, stitched seam prominently visible. Slight scuff marks. Rich red (#8B0000). | A1, A2 |
| OV-CRK-I03 | Stumps & Bails | Three wooden stumps with bails balanced on top. Clean side view, pitch-level angle. Sunlit wood grain. | A1, A2 |
| OV-CRK-I04 | Cricket Helmet | Batsman's helmet with metal grille, front or 3/4 angle. Dark navy or green. Protective gear = intensity. | A1, A2 |
| OV-CRK-I05 | Cricket Gloves | Batting gloves in fist-clenched ready position, white with coloured accents, grip detail visible. | A1, A2 |

#### Action & Players (Silhouettes)

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-CRK-I06 | Batsman Silhouette (Cover Drive) | Batsman mid-cover-drive, classic textbook shot. Full body silhouette, bat extended, weight forward. | A1, A2, B1 |
| OV-CRK-I07 | Bowler Silhouette (Delivery Stride) | Fast bowler at peak delivery stride, arm high back arched. Maximum kinetic energy. | A1, A2, B1 |
| OV-CRK-I08 | Batsman Silhouette (Six — Celebration) | Batsman looking up after hitting a six, bat raised overhead. Crowd-energy implied. | A1, A2, B1 |
| OV-CRK-I09 | Wicketkeeper (Dive) | Keeper diving sideways for catch, horizontal body, gloves extended. Athletic action. | A2, B1 |

#### Celebration & Venue

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-CRK-I10 | Cricket Stadium (Wide) | Floodlit stadium panorama, evening match, packed stands, green pitch centre. Cinematic. | B1 |
| OV-CRK-I11 | Trophy / Cup | Gold cricket trophy with handles (generic, not branded). Spotlight on trophy, dark background. | A1, A2 |
| OV-CRK-I12 | Six / Boundary Burst | Ball flying over boundary rope with graphic energy burst. Motion lines, comic-book energy. | A1, A2 |
| OV-CRK-I13 | Gully Cricket Scene | Informal street cricket in Indian lane, makeshift stumps (bricks), narrow lane, kids playing. | B1 |
| OV-CRK-I14 | Cricket Pitch (Close-up) | Close-up of pitch with crease line, bat shadow, red ball on good length. Textured grass. | B1 |
| OV-CRK-I15 | Scoreboard / Numbers | Abstract scoreboard graphic showing "SIX" or score numbers. Bold typography, stadium-style. | A1, A2 |

### 31.3 Illustrations — Restrict from Base

#### From Good Morning (15 items — Spiritual / Devotional category + calm items)

| Restricted Item | Reason |
|----------------|--------|
| GM-I3-02 Lotus in Full Bloom | Meditative / sacred — contradicts competition |
| GM-I3-03 Jasmine Buds (Mogra) | Too delicate / soft for sports energy |
| GM-I3-06 Champa / Frangipani | Temple flower — spiritual, not sports |
| GM-I3-07 Rose Bud with Dew | Romantic / soft — wrong energy |
| GM-I3-08 Petals Floating on Water | Meditative stillness — contradicts sports action |
| GM-I4-01 Lit Diya with Warm Glow | Devotional — contradicts sports energy |
| GM-I4-03 Hands in Namaste | Devotional prayer — contradicts competitive energy |
| GM-I4-04 Incense Stick Smoke | Temple morning — wrong mood |
| GM-I4-05 Tulsi Plant in Brass Pot | Sacred / devotional — not sports |
| GM-I4-06 Temple Bell | Devotional — not sports |
| GM-I4-07 Shankh (Conch Shell) | Sacred — not sports |
| GM-I4-08 Rangoli at Dawn | Festive / devotional — not sports |
| GM-I4-09 Peacock Feather | Divine / Krishna association — not sports |
| GM-I5-02 Meditating Figure at Sunrise | Meditation = opposite of sports energy |
| GM-I6-05 Sarus Crane in Misty Field | Peaceful / poetic — too contemplative |

#### From Birthday (7 items)

| Restricted Item | Reason |
|----------------|--------|
| BD-I11 Marigold Toran (Hanging) | Devotional / festive — not sports |
| BD-I13 Diya Cluster | Devotional — clashes with cricket |
| BD-I14 Rangoli (Floor) | Devotional / festive — not sports |
| BD-I15 Puja Thali | Devotional — not sports |
| BD-I21 Flower Bouquet | Too soft / romantic for sports energy |
| BD-I26 Wish Card / Envelope | Too gentle / intimate for cricket |
| BD-I28 Blowing Candles (Silhouette) | Quiet personal moment — contradicts stadium energy |

**Total restrictions:** 15 (GM) + 7 (BD) = 22 items blocked.

### 31.4 Motifs & Decor (per allowed track — no Track E)

#### Track A — Shiny Maximal

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Floral / sparkle | Gold Cricket Ball | Metallic gold cricket ball with raised stitch detail. High-shine (#D4AF37), embossed / 3D feel. |
| Swap | Garland / ornate | Stadium Lights Burst | Stylised floodlight burst radiating outward like a star. Gold rays, 12–16 points. |
| Add | — | Bat & Ball Crest | Ornate cricket crest: crossed bat and ball with laurel wreath frame. Gold trophy-style engraving. Heraldic feel. |

#### Track B — Modern Desi

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Rangoli / geometric | Cricket Ball Rangoli | Cricket ball shape integrated into geometric rangoli quarter-pattern at corners. Clean modern lines. Red + white. |
| Swap | Traditional | Modern Stumps Icon | Clean minimal stumps-and-bails graphic in 2-colour line art. Thin strokes. |
| Add | — | Boundary Rope Line | Stylised boundary rope along frame base as decorative line. Subtle wave pattern. |

#### Track C — Minimalist Classy

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Dot / line | Minimal Bat Line | Single continuous thin-line cricket bat profile. No fill, just outline. Warm grey or muted red. |
| Swap | Geometric | Ball Seam Arc | Quarter-circle arc mimicking a cricket ball's seam stitch pattern. 6 small V-shapes along the arc. |

#### Track D — Artsy Playful

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Doodle | Doodle Bat & Ball | Hand-drawn bat and ball with crayon texture. Wobbly outlines, scribble fill. Oversized bat, hand-drawn stitches. |
| Swap | Sticker | "SIX!" Sticker | Puffy comic-book "SIX!" text sticker in bold red / yellow. Slightly 3D with drop shadow. Impact stars around. |
| Add | — | Doodle Stumps (Flying) | Hand-drawn stumps with bails flying off in different directions. Action lines showing impact. Crayon style. |
| Add | — | Cricket Star Burst | Hand-drawn star explosion burst in bright comic colours. "POW" energy as corner accent. |

### 31.5 Frame Types

**Restrict:** F5 — Arch / Canopy (ornate / traditional arch doesn't match modern sports energy).
**Unlock:** None.

### 31.6 Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `cricket match energy, stadium floodlight atmosphere, sporting excitement, Indian cricket fervour, competitive intensity, match-day buzz` |
| Mood | `energetic, competitive, exciting, victorious, spirited, adrenaline, fierce, proud, triumphant` |
| Negatives | `calm, serene, spiritual, devotional, temple, meditation, quiet, peaceful, slow, gentle, soft, pastel, watercolour, muted` |
| B1 Scene Context | `Indian cricket setting, floodlit stadium at evening or bright daytime match, lush green pitch with white crease lines, packed stands with cheering crowd, or nostalgic gully cricket in Indian neighbourhood lane` |

#### Prompt Additions — Firefly Compact (≤ 950 char budget)

| Element | Compact value |
|---------|--------------|
| Atmosphere | `cricket match energy, stadium floodlight buzz` |
| Mood | `energetic, competitive, exciting, proud` |
| B1 Scene | `floodlit cricket stadium evening, green pitch, packed stands` |
| Negatives | *(not in Firefly prompt — no budget impact)* |

---

# Part 5 — Prompt Engineering & Implementation

## 32. Prompt Builder Architecture

The prompt generator is a single-file HTML app (`GoodMorning_Prompt_Generator_v5.html`). All wizard state, data libraries, render functions, and prompt builders live in one inline `<script>` block.

### High-level flow

```
User clicks Step 1..N options
        ↓
select(key, value)            ← updates STATE, runs reset cascade, calls render()
        ↓
render()                      ← renders current step UI based on getCurrentStepId()
        ↓
[user clicks "Generate Prompts" on final step]
        ↓
generatePrompts()             ← validates canProceed() for every step
        ↓
For each platform:
  buildPrompt(platform)
        ↓
  if archetype === 'B1':
    gatherB1PromptData() → buildB1<Platform>Prompt(d)
  else:
    gatherPromptData()   → build<Platform>Prompt(d)
        ↓
GENERATED_PROMPTS[i] stored globally + displayed in 5 result panels
```

### Two gather functions

| Function | Used for | Returns (key fields) |
|----------|----------|----------------------|
| `gatherPromptData()` | A1, A2 | `arch, step2Opt, layout, track, palette, font, finish, illusRender, motif, preset, illusItem, illusSize, roles, sizePh, framePh, overlayPh, densityPh, a2AccentPh, textZonePh, illusPositionPh, bgPh, illusColPh, textColPh, motifPh, motifPhFirefly, renderPh, ornamentalGuard, motifBoundary, stylePh, intensityPh, overlay, overlayAtm, overlayMood, overlayNegs, overlayFireflyAtm, overlayFireflyNegGuard` |
| `gatherB1PromptData()` | B1 | `step2Opt, layout, track, font, photoTrack, mood, intensity, sceneItems, scenePh, overlayPh, textZonePh, negs, overlayStrength, overlay, overlayAtm, overlayMood, overlayB1Scene, overlayFireflyAtm, overlayFireflyMood, overlayFireflyB1Scene` |

The gather functions resolve all selections into rendered prompt phrases, look up overlay metadata, and bundle everything for the platform-specific builders. Builders only assemble strings — they don't make logic decisions.

### Per-platform builders

| Platform | A1 / A2 builder | B1 builder | Char cap |
|----------|----------------|-----------|:--------:|
| Adobe Firefly (with-text) | `buildFireflyWithTextPrompt(d)` | `buildB1FireflyWithTextPrompt(d)` | 950 |
| Adobe Firefly (no-text) | `buildFireflyNoTextPrompt(d)` | `buildB1FireflyNoTextPrompt(d)` | 950 |
| Midjourney | `buildMJPrompt(d)` | `buildB1MJPrompt(d)` | None (uses `--ar 9:16 --s 400 --no <negatives>`) |
| Leonardo.AI | `buildLeonardoPrompt(d)` | `buildB1LeonardoPrompt(d)` | ~ 1400 (soft) |
| Google Gemini | `buildGeminiPrompt(d)` | `buildB1GeminiPrompt(d)` | None (verbose descriptive) |

### Helper functions

| Helper | Purpose |
|--------|---------|
| `stripHex(s)` | Removes `(#XXXXXX)` annotations from palette descriptions. Used by Firefly builders to save chars. |
| `trunc(s, max)` | Truncates `s` to `max` chars at the last comma. Preserves keyword integrity. |
| `getCategoryAtmosphere()` | Returns the per-category atmosphere object: `atmosphereInline`, `atmosphereSentenceCase`, `sceneAuthenticity`, `gemSettingContext`, `lightTimeContext`, `stylePhMoodWord`. Switches on `STATE.category`. |
| `getCategoryLabel()` | "Good Morning" / "Happy Birthday" / "Suvichar / Quote". |
| `getDisplayText()` | Hero text rendered into Firefly with-text prompts. GM/Birthday return literal greeting; Suvichar returns user-typed quote. |
| `getActiveOverlay()` | Returns the active overlay object or null. |
| `applyOverlayToCatalogue(baseCats)` | Layers overlay add + restrict on top of any base catalogue. Used by all 3 catalogue resolvers. |

---

## 33. Per-Platform Prompt Formulas

### 33.1 Midjourney (A1 / A2)

Single dense paragraph, comma-separated visual phrases, ends with `--ar 9:16 --s 400 --no <negatives>`.

**Order of phrases (matches wizard step order for traceability):**

```
[framePh / densityPh / overlayPh]
[textZonePh]
[bgPh, finish.promptPhrase]
the illustration only is [renderPh] of [illusItem.name] [illusItem.desc] rendered in [illusColPh]
[sizePh] [illusPositionPh]
[ornamentalGuard | motifBoundary]
[motifPh]
small accent details nearby: [a2AccentPh], rendered in the same illustration style
[intensityPh]
[stylePh]
[track A only: white sparkle particles scattered]
[overlayAtm if active]
[overlayMood if active]
9:16 portrait format
--ar 9:16 --s 400 --no [buildNegatives() + overlayNegs]
```

### 33.2 Midjourney (B1)

```
photorealistic photograph, full-bleed image filling the entire canvas,
[atm.atmosphereInline + ', ' + overlayAtm if active]
[scenePh + ', ' + overlayB1Scene if active]
[mood.promptPhrase + ', ' + overlayMood if active]
[photoTrack.promptPhrase]
[intensity.promptPhrase]
[colour temperature line based on mood — 4500K / 5500K etc]
[textZonePh]
[overlayPh — auto-determined from layout + strength]
9:16 portrait format, professional DSLR photography, sharp focus on subject,
high dynamic range, natural bokeh where appropriate
--ar 9:16 --s 250 --no [d.negs incl. overlayNegs]
```

### 33.3 Leonardo.AI (A1 / A2)

Compact structured prompt, must stay under ~ 1400 chars. Uses labelled lines:

```
[track.name] [categoryLabel] poster, 9:16 vertical.
BG: [bgPh][, finish.promptPhrase].
Frame: [framePh truncated to 80].
Overlay: [overlayPh].                    (if A2)
Density: [densityPh].                    (if A2)
Layout: [textZonePh]. Illustration [illusPositionPh].
Subject: [illusItem.name], [illusItem.desc].
Render: [renderPh truncated to 120], [illusColPh]. [sizePh].
[Visibility guard: ornamentalGuard or motifBoundary, if relevant]
Motif: [motif.name + placement].
Accents: [a2AccentPh, same style].         (if A2)
Intensity: [intensityPh truncated to 100].
Style: [stylePh truncated to 100][. Sparkle particles. if Track A]
Atmosphere: [overlayAtm].                  (if overlay active)
Mood: [overlayMood].                       (if overlay active)
Negative: [buildLeonardoNegatives + overlayNegs joined]
```

### 33.4 Leonardo.AI (B1)

Same labelled-line structure adapted for photoreal:

```
Photorealistic [photoTrack.name] photograph, [categoryLabel] poster, 9:16 vertical (1080x1920).
Full-bleed photo, no frames, no borders, no illustration.
[atm.atmosphereSentenceCase + ', ' + overlayAtm if active].
Scene: [scenePh + ', ' + overlayB1Scene if active].
Mood: [mood.promptPhrase + ', ' + overlayMood if active].
Aesthetic: [photoTrack.promptPhrase].
Camera: [intensity.promptPhrase].
Text zone: [textZonePh]. Overlay: [strengthWord + overlayPh]. Keep this area darker for white text readability.
Quality: DSLR, sharp focus on subject, natural depth of field.
Negative: [coreNegs + birthday-additions + overlay-negs joined]
```

### 33.5 Adobe Firefly with-text (A1 / A2)

Hard cap ≤ 950 chars. Includes hero text via `getDisplayText()`. Ends with the standard "Clean ... text in decorative font in the text zone, legible, not overlapping illustration." instruction. Per-component truncation via `trunc()`.

```
[track.name] [categoryLabel] poster, 9:16 vertical.
BG: [stripHex(bgPh)][, trunc(finish, 40)].
Frame: [trunc(framePh, 50)].
[trunc(overlayPh, 40)].                    (A2 / B1 only)
[trunc(densityPh, 40)].                    (A2 only)
Text zone: [zone] 25%. Illustration: [opposite] area.
[illusItem.name]: [illusItem.desc]. [trunc(stripHex(renderPh), 60)], [stripHex(illusColPh)]. [sizePh].
[motifPhFirefly].                          (if motif active)
Accents: [trunc(a2AccentPh, 60)], same style.   (A2 only)
[trunc(intensityPh, 60)].
[trunc(stylePh, 60)].
Sparkle particles.                         (Track A only)
[trunc(overlayFireflyAtm, 50)].            (overlay active)
Clean "[displayText]" text in decorative font in the text zone, legible,
not overlapping illustration. Do not include text duplicates[, overlayFireflyNegGuard].
```

If the assembled `result.length > 950`, the final `result.substring(0, 950).replace(/\s+\S*$/, '')` clips at the last whole word.

### 33.6 Adobe Firefly no-text (A1 / A2)

Same structure as 33.5 but with the closing instruction replaced by:

```
... [trunc(stylePh, 60)]. [Sparkle particles. — Track A only]
[trunc(overlayFireflyAtm, 50)].                (overlay active)
Purely visual, no text, no letters, no typography. Do not include [overlayFireflyNegGuard].
```

### 33.7 Adobe Firefly with-text (B1)

```
Photorealistic [photoTrack.name] [categoryLabel] poster, 9:16 vertical, full-bleed photograph,
[atm.atmosphereInline][, trunc(overlayFireflyAtm, 50)].
[trunc(scenePh + ', ' + overlayFireflyB1Scene, 130)].
[trunc(mood.promptPhrase + ', ' + overlayFireflyMood, 90)].
[trunc(photoTrack.promptPhrase, 90)].
[trunc(intensity.promptPhrase, 80)].
[trunc(textZonePh, 60)], [strengthHint] [trunc(overlayPh, 50)].
"[displayText]" text in white decorative font in the text zone, legible.
DSLR quality, sharp focus.
```

### 33.8 Adobe Firefly no-text (B1)

Same as 33.7 but closing instruction replaced with `Purely visual, no text, no letters, no typography.`. Header uses `atm.atmosphereSentenceCase` instead of `atm.atmosphereInline`.

### 33.9 Google Gemini (A1 / A2)

Verbose multi-section structured descriptive sentences, no char cap. Each section maps to a wizard step:

```
A [track.name] style [categoryLabel] greeting poster in vertical 9:16 format.

Background & Finish: [bgPh] with [finish.promptPhrase].

Frame ([step2Opt.name]): A [framePh] encloses the composition. The frame is purely
decorative and does not cover the main illustration. The frame maintains its own
consistent style independent of illustration rendering.

Layout ([layout.name]): [textZonePh]. Illustration [illusPositionPh].

Illustration: [illusItem.name] — [illusItem.desc].
Render style (illustration only): [renderPh]. Coloured in [illusColPh]. The rendering
style applies only to this illustration, not to the frame or background.
Size: [sizePh].
Visibility: The illustration must be clearly visible — [ornamentalGuard | motifBoundary].

Motif: [motifPh]. The motif must appear ONLY on the border frame edges and must NOT
appear near, beside, or around the illustration.       (A1)
or: The motif accents are scattered around and near the illustration ... — they do
NOT appear on the border edges.                          (A2)

Accent details: Small supporting elements nearby — [a2AccentPh]. These accents are
rendered in the exact same illustration style as the main subject.

Decoration intensity: [intensityPh].

Style reference: [stylePh].
Small white sparkle particles are scattered across the design.   (Track A only)

Overlay flavour ([overlay.name]): The poster carries an additional [overlay.name]
atmosphere — [overlayAtm]. The mood is [overlayMood].   (overlay active)

Do not include: [buildNegatives() + overlayNegs joined].
```

### 33.10 Google Gemini (B1)

```
A photorealistic [photoTrack.name] style photograph for a [categoryLabel] greeting
poster in vertical 9:16 format. The image is a full-bleed photograph that fills the
entire canvas — no frames, no borders, no illustration elements. The setting is
[atm.gemSettingContext][, with an additional [overlay.name] flavour: [overlayAtm]].

Scene: The photograph features [scenePh][. The setting includes: [overlayB1Scene]].
The scene should feel natural and authentic — as if captured in a [atm.sceneAuthenticity],
not staged or artificial.

Lighting & Mood: [mood.promptPhrase][. Additional mood layer: [overlayMood]].
The light should feel [atm.lightTimeContext].

Photography Aesthetic: [photoTrack.promptPhrase].

Camera & Framing: [intensity.promptPhrase]. Use natural depth of field appropriate
to the focal length — sharp focus on the main subject with gentle falloff.

Colour Temperature: [Kelvin description from mood map — e.g. "Warm 4500K — amber sunrise"].

Composition & Text Zone: The image has [strengthDesc] — [overlayPh]. The [textZonePh]
— this area should be [distinctly | slightly] darker or muted to ensure white text overlay
is legible against the photograph.

Technical Quality: Professional DSLR quality, sharp focus on the main subject, high
dynamic range, natural bokeh. The image should look like it was shot by a skilled
photographer, not AI-generated.

Do not include: [d.negs joined incl. overlayNegs].
```

---

## 34. Negative Prompt Strategy

Negatives are layered: framework → track → palette → category → archetype-specific guards → overlay.

### Framework defaults (every prompt)

```
text, letters, words, numbers, typography, watermarks, logos, blurry, low quality
```

### Per-track additions

| Track | Negatives added |
|-------|----------------|
| A | `photorealistic, cinematic lighting, landscape background, minimalism, flat modern, grunge, grayscale` |
| B | `Bollywood, maximalist, gold foil, sparkle, metallic, loud colours` |
| C | `photorealistic, ornate, gold foil, busy, multiple illustrations, vivid, gradient, doodles` |
| D | `photorealism, cinematic, ornate, gold, film grain, muted, serif` |
| E | `harsh, neon, loud, metallic, glitter, sparkle, ornate heavy decoration, bold thick outlines` |

### Palette banColour exclusion

If the active palette has a `roles.banColour` (e.g. orange BG → ban orange illustration), the system adds:

```
[banColour] illustration, [banColour] subject, monochrome single-colour
```

This enforces the "illustration must contrast with background" rule from Section 11.

### Render-style guard

```
border style matching illustration style, frame affected by illustration rendering
```

Plus, if `IR-1 Ornamental Vector` is active:

```
illustration hidden behind decoration, illustration merged with ornamental pattern
```

### Motif boundary guard

If a motif is selected and an illustration is present:

```
illustration hidden behind decoration, motif overlapping illustration
```

Then archetype-specific:
- **A1:** `motif near illustration, motif beside illustration, motif around illustration`
- **A2:** `motif on border edges, motif on frame`

### Category-specific (Birthday)

Appended to all archetype negatives:

```
funeral, mourning, sad, wilted, dark mood, horror
```

For B1 specifically, add: `illustrated elements, graphic design, decorative overlay`.

### B1-specific base negatives

```
text, letters, words, numbers, typography, illustration, cartoon, painting, drawing,
sketch, vector, clipart, frame, border, decorative pattern, motif, ornamental,
watermarks, logos, blurry, low quality, artificial, CGI, rendered
```

Per-photo-track additions (B1 only):
- A → `muted, desaturated, flat`
- B → `oversaturated, HDR, neon, vivid`
- C → `colorful, saturated, busy, cluttered`
- D → `dark, moody, desaturated, muted`
- E → `harsh, high contrast, neon, sharp edges`

### Overlay additions

Each overlay's `prompt.negatives` array is appended last (so it always lands at the end of the negative list):

| Overlay | Negatives |
|---------|-----------|
| Devotional | `party, nightclub, alcohol, modern urban, neon, loud, aggressive, cartoon, doodle, playful, comic, silly` |
| Summer | `cold, snow, winter, fog, overcast, grey, dark, cloudy, sweater, blanket, rain, umbrella, monsoon, frost` |
| Rain / Monsoon | `harsh sunlight, desert, dry, arid, bright blue sky, clear sky, scorching, drought, dust, snow, winter` |
| Cricket / IPL | `calm, serene, spiritual, devotional, temple, meditation, quiet, peaceful, slow, gentle, soft, pastel, watercolour, muted` |

### Firefly negative guard (compact)

For Firefly only, the full overlay negative list is replaced with a compact `fireflyNegGuard` that is appended inside the closing instruction line (no new prompt section):

| Overlay | Compact guard |
|---------|---------------|
| Devotional | `party, nightclub, cartoon, doodle` |
| Summer | `cold, snow, fog, rain, overcast` |
| Rain / Monsoon | `harsh sunlight, desert, clear blue sky` |
| Cricket / IPL | `calm, spiritual, soft, pastel, watercolour` |

---

## 35. State Model (STATE)

The single global `STATE` object is the source of truth for the wizard. Reset cascades fire on certain key changes.

```js
const STATE = {
  step: 1,
  category: 'good_morning',         // 'good_morning' | 'suvichar' | 'birthday'
  overlay: 'OV-NONE',               // 'OV-NONE' | 'OV-DEV' | 'OV-SUM' | 'OV-RAIN' | 'OV-CRK'
  feeling: null,                    // Suvichar: 'SV-F1'..'SV-F5'
  customText: '',                   // Suvichar: user-entered quote rendered into the poster
  archetype: null,                  // 'A1' | 'A2' | 'B1'
  step2: null,                      // A1: 'F1'..'F6' frame; A2: density (auto-calc); B1: 'O1'..'O5' overlay
  layout: null,                     // 'L1'..'L6'
  track: null,                      // 'A'..'E'
  palette: null,                    // 'GM-C1'..'GM-C9'
  font: null,                       // 'GM-F1'..'GM-F4'
  finish: null,                     // 'FN-1'..'FN-5' (per track)
  illusRender: null,                // 'IR-1' / 'IR-B1' / 'IR-C1' etc (per track)
  motifSet: null,                   // 'MT-1'..'MT-10' (per track)
  customPreset: null,               // 'Basic' | 'Medium' | 'Complex' (per track)
  illusCategory: null,              // catalogue category id
  illusItem: null,                  // illustration item id (or 'NONE')
  frameDecoration: null,            // 'Plain' | 'Simple' | 'Detailed' (A1 only)
  illusSize: null,                  // 'Small' | 'Medium' | 'Large'
  textInput: '',                    // Hero text input (A1 / A2 only)
  textLang: 'Hindi',                // 'Hindi' | 'English'
  // B1 specific
  sceneElements: [],                // 1 main + 0-2 supporting illustration IDs
  mood: null,                       // 'MD-1'..'MD-6'
  overlayStrength: 'light',         // 'light' | 'heavy'
  a2SubElements: [],                // A2 sub-accent IDs (max 2)
};
```

---

## 36. Reset Cascade Rules

When `select(key, value)` is called, downstream state is invalidated according to these rules:

| Key changed | Resets |
|-------------|--------|
| `category` | `overlay, feeling, customText, archetype, step2, layout, track, palette, font, finish, illusRender, motifSet, customPreset, frameDecoration, illusSize, illusItem, illusCategory, sceneElements, mood, overlayStrength, a2SubElements` (everything downstream) |
| `overlay` | `step2, layout, track, palette, font, finish, illusRender, motifSet, customPreset, frameDecoration, illusSize, illusItem, illusCategory, sceneElements, mood, a2SubElements` (overlay can invalidate previously-picked track via blockedTracks, illustration via restrictByCategory, motif via swap, frame via F5 restrict / F6 unlock) |
| `archetype` | `feeling, step2, layout, track, palette, font, finish, illusRender, motifSet, customPreset, frameDecoration, illusSize, illusItem, illusCategory, sceneElements, mood, overlayStrength, a2SubElements` |
| `feeling` | `track, palette, font, finish, illusRender, motifSet, customPreset, frameDecoration, illusSize, illusItem, illusCategory, sceneElements, mood, a2SubElements` (Suvichar only) |
| `step2` | `layout` (frame change can rule out previously valid layout) |
| `track` | `palette, font, finish, illusRender, motifSet, customPreset, mood` (track defines all of these; B1 keeps mood reset too) |
| `illusItem` | `a2SubElements` (sub-accents are curated per main illustration) |
| `frameDecoration` (set to Plain) | `motifSet` (Plain frame = no motifs) |

The cascade is deliberately conservative — if there's any chance a downstream selection became invalid, it is cleared and re-asked rather than silently kept.

---

## 37. Filtering Pipelines (track / illus / motif / frame)

### Track filter — `getFilteredTracks()`

```js
function getFilteredTracks() {
  let tracks = TRACKS;
  // Suvichar feeling filter
  if (STATE.category === 'suvichar' && STATE.feeling) {
    const feeling = SUVICHAR_FEELINGS.find(f => f.id === STATE.feeling);
    if (feeling) tracks = tracks.filter(t => feeling.allowedTracks.includes(t.id));
  }
  // Overlay hard-block filter (Devotional → blocks D, Rain → blocks A, Cricket → blocks E)
  const ov = getActiveOverlay();
  if (ov && ov.blockedTracks.length) {
    tracks = tracks.filter(t => !ov.blockedTracks.includes(t.id));
  }
  return tracks;
}
```

### Illustration filter — `applyOverlayToCatalogue(baseCats)`

Layered on top of any base catalogue (`ILLUS_CATS` / `getSuvicharIllusCats()` / `getBirthdayIllusCats()`):

1. Filter out items in `overlay.restrictByCategory[STATE.category]`.
2. Group overlay items by their `group` field, filtering by archetype.
3. Append overlay groups as new catalogue categories prefixed with the overlay name (e.g., "Devotional · Sacred Symbols").

### Motif filter — `getMotifOptions()`

```js
function getMotifOptions() {
  // 1. Resolve base motif set (BD-MT-* if Birthday; MT-* / MT-B-* / etc otherwise)
  let base = ...;
  // 2. Apply overlay swaps (1:1 replacement)
  const swapMap = ov.motifSwaps[STATE.track] || {};
  const swapped = base.map(m => swapMap[m.id] ? { ...swapMap[m.id], bestWith: m.bestWith } : m);
  // 3. Append overlay adds
  return [...swapped, ...(ov.motifAdds[STATE.track] || [])];
}
```

### Frame filter — `getStep2Options()`

```js
function getStep2Options() {
  let options = STEP2_OPTIONS[arch.step2Key] || [];
  if (arch.id === 'A1') {
    const ov = getActiveOverlay();
    if (ov) {
      if (ov.frameRestrict.length) options = options.filter(o => !ov.frameRestrict.includes(o.id));
      if (ov.frameUnlock.length) options = [...options, ...ov.frameUnlock];
    }
  }
  return options;
}
```

---

## 38. Audit Panel & Traceability

After `generatePrompts()` runs, the output panel shows a collapsible "PROMPT AUDIT" section listing every wizard step → prompt section mapping. This is the QA check used to verify the prompt actually reflects user choices.

**Audit rows for A1 / A2 (with overlay):**

| Step | Label | Value (example) | Prompt section |
|------|-------|-----------------|----------------|
| 1a | Category | Good Morning | Category selector |
| 1b | Overlay | Devotional | Flavour layer |
| 1c | Template | A1 — Text + Frame | Frame / Density / Overlay |
| 2 | Feeling | Rise & Shine | Emotional tone (Suvichar only) |
| 2/3 | Style | F1 Full Perimeter | Frame ... |
| 3/4 | Layout | L5 Text Bottom | Layout ... |
| 4/5 | Track | Shiny Maximal | Header + Style reference |
| 5a | Palette | Sunrise Gold | Background & Finish |
| 5b | Finish | Radial Gradient | Background & Finish |
| 6a | Illustration | Marigold Garland | Illustration: |
| 6b | Render Style | Ornamental Vector | Render style ... |
| 6c | Size | Medium | Size: |
| 6d | Frame Deco | Detailed | Frame ... |
| 6e | Motif | Om with Gold Halo *(overlay swap)* | Motif: |
| 7 | Intensity | Medium — Balanced Bling | Decoration intensity: |
| 8 | Quote Text | "[user text]" | Rendered text (Suvichar only) |

**Audit rows for B1:**

| Step | Label | Value (example) | Prompt section |
|------|-------|-----------------|----------------|
| 1 | Template | B1 — Photo Background | Photorealistic photograph |
| 1b | Overlay | Rain / Monsoon | Flavour layer |
| 2a | Text Position | L5 Text Bottom | Text zone placement |
| 2b | Overlay Strength | Light | Auto-overlay from text position |
| 3 | Track | Modern Desi (Editorial Muted) | Photography aesthetic |
| 4a | Main Element | Chai in Rain | Scene: hero subject |
| 4b | Supporting | Wet Window Pane, Fallen Petals | Scene: background elements |
| 5 | Mood | Misty Soft | Mood (light + colour) |
| 6 | Intensity | Medium Balanced | Camera & Framing |

The audit panel is collapsible; below it is a TSV / HTML clipboard export aligned with the Prompt Eval Framework v4 spreadsheet (36 columns, Y = AI Eval Prompt).

---

# Part 6 — Extending the System

## 39. Decision Framework — Category vs Overlay

When a new content idea comes up, ask one question:

> **Does it have its own greeting text?**

| Answer | Decision | Example |
|--------|---------|---------|
| **Yes** — it has unique hero text that doesn't belong to any existing category | → **New Base Category** | Rath Yatra ("शुभ रथ यात्रा"), Diwali ("शुभ दीपावली"), Eid ("ईद मुबारक"), Holi ("Happy Holi") |
| **No** — it's a flavour / context that modifies an existing greeting | → **Overlay Pack** | Devotional (still "Good Morning"), Cricket (still "Good Morning" or "Happy Birthday"), Rain (still "Good Morning") |

**Secondary check for Overlays:** Does this flavour apply to more than one base category? If yes, it's definitely an overlay — build it once, compose it with multiple bases.

---

## 40. Adding a New Base Category

To add a new base category (e.g., Diwali), implement the following:

### 40.1 Data layer

1. **Hero text** — define `getCategoryLabel()` and `getDisplayText()` cases for the new category.
2. **Atmosphere bundle** — extend `getCategoryAtmosphere()` with a new branch returning the 6 keys (`atmosphereInline`, `atmosphereSentenceCase`, `sceneAuthenticity`, `gemSettingContext`, `lightTimeContext`, `stylePhMoodWord`).
3. **Per-track motif sets** — define motif arrays (e.g., `DIWALI_MOTIF_OPTIONS_A..E`) and dispatch in `getMotifOptions()`.
4. **Illustration catalogue** — define `DIWALI_ILLUS_CATS` array of categories with items.
5. **Illustration resolver** — implement `getDiwaliIllusCats()` analogous to `getSuvicharIllusCats` / `getBirthdayIllusCats`. Apply archetype + (optional) feeling filter, fold in any GM carry-overs.
6. **Sub-element libraries** — define `DIWALI_B1_SUB_ELEMENTS` and `DIWALI_A2_SUB_ELEMENTS` mapping main item IDs to accent ID arrays. Add new `DIWALI-ACC-*` items to `ACCENT_ITEMS` if needed for category-specific props.
7. **Photo desc map** — define `DIWALI_B1_PHOTO_DESC[id]` for B1 use.
8. **Negative terms** — append category-specific negatives in `buildNegatives()` and `gatherB1PromptData()`.

### 40.2 UI layer

1. Add the category card to `renderStep1()` (line ~ 1474 in `GoodMorning_Prompt_Generator_v5.html`).
2. Add the icon and description.
3. If the category needs a Feeling step or Custom Text step (like Suvichar), update `getSteps()` and add `STEP_LABELS` entries.

### 40.3 Overlay compatibility

1. Update Section 24.1 of this PRD with rationale for which overlays apply to the new category.
2. In each `OVERLAYS[i].appliesTo` array in code, add the new category id where appropriate.
3. For each overlay that applies, add a `restrictByCategory[newCategoryId]` entry listing items that should be hidden.

### 40.4 QA

1. Verify the audit panel shows the new category at row 1a.
2. Generate prompts for all 5 platforms × A1 / A2 / B1 × all 5 tracks, and verify Firefly stays ≤ 950 chars.
3. Run a worst-case check: longest illustration name + Track A + longest preset + longest overlay → confirm ≤ 950.

---

## 41. Adding a New Overlay Pack

### 41.1 Data layer

Add a new entry to the `OVERLAYS` array following the spec template in Section 27. Required fields:

```js
{
  id: 'OV-XXX',
  name: 'Overlay Name',
  icon: '🪔',                  // emoji shown in picker
  desc: 'One-line description for the picker card',
  appliesTo: ['good_morning', ...],  // base category ids
  blockedTracks: [],                  // e.g. ['D'] or []
  illustrations: [                    // 8-15 items
    { id: 'OV-XXX-I01', name, desc, archs: ['A1','A2','B1'], group: 'Sub-category Name' },
    ...
  ],
  restrictByCategory: {
    good_morning: ['GM-Ix-yy', ...],
    ...
  },
  motifSwaps: {                       // per-track 1:1 replacements
    A: { 'MT-1': { id: 'OV-XXX-MT-A1', name, promptPhrase } },
    ...
  },
  motifAdds: {                        // per-track extra motifs (use sparingly)
    A: [{ id, name, promptPhrase }],
    ...
  },
  frameRestrict: [],                  // F-codes to hide for A1
  frameUnlock: [],                    // special frames to add for A1 only when active
  prompt: {
    atmosphere: '<full keyword list>',
    mood: '<full keyword list>',
    negatives: ['neg1', 'neg2', ...],
    b1Scene: '<full B1 scene context>',
    fireflyAtm: '<≤50 chars>',
    fireflyMood: '<≤40 chars>',
    fireflyB1Scene: '<≤60 chars>',
    fireflyNegGuard: '<short comma-separated>',
  },
}
```

### 41.2 Compatibility update

Update Section 24.1 with rationale rows for each base category × new overlay. Default to ❌ unless there's a clear positive case.

### 41.3 UI verification

1. Confirm the overlay appears in Step 1 sub-section 2 only for valid base categories.
2. Confirm blocked tracks are hidden at Step 4/5.
3. Confirm any restricted illustrations are hidden at the Visual / Scene step.
4. Confirm motif swaps appear in the motif picker (Visual step).
5. Confirm any frame restrict / unlock takes effect at Step 2 (A1).
6. Confirm overlay rows appear in the audit panel.

### 41.4 Worst-case prompt budget

Generate this prompt and confirm Firefly stays ≤ 950 chars:

```
Category: Good Morning   Overlay: <new>   Archetype: A2   Track: A
Layout: L2   Palette: GM-C1-A   Finish: Sparkle/Glitter   Render: Ornamental Vector
Illustration: longest-named GM item   Sub-elements: 2   Intensity: Complex
```

---

## 42. Future Enhancements & Open Items

### P0 — must do before public launch

1. **Palette expansion** — current 6 GM palettes per track is a starting set; expand based on user testing.
2. **Illustration expansion** — current 49 GM + 30 BD + 30 SV items is a starting set; expand based on designer input + user testing.
3. **Prompt refinement** — iterative tuning across Midjourney / Leonardo / Firefly through real-image testing at scale.

### P1 — high-value gaps

4. **Native text rendering on posters** — currently handled via post-generation compositing layer. Long-term: explore Firefly's text rendering more deeply, or migrate to a model that handles text reliably.
5. **Multi-illustration in A1** — extend the curated sub-illustrations system from A2 to A1.
6. **Phase 2 archetypes** — implement detailed BRDs for C1 (Animated Elements), C2 (Animated Text), D1 (Video Background), E1 (AI Avatar).
7. **Custom palette input** — allow creators to pick custom hex colours within track guidance.
8. **Uploaded illustrations** — allow creators to bring their own illustration assets.
9. **Regional / festival-specific presets** — Tamil Pongal, Onam, Pohela Boishakh, Lohri.

### P2 — nice-to-have

10. **End-to-end automation pipeline** — API-based generation, automatic compositing (text + image), batch production workflows.
11. **Adobe-stock background integration** — wire stock asset library into B1 background source picker.
12. **Multi-language support beyond Hindi / English** — Tamil, Telugu, Bengali, Marathi, Gujarati, Punjabi.

### Future overlay candidates

| Candidate | Applies to | Notes |
|-----------|-----------|-------|
| Diwali (overlay vs category?) | Good Morning, Suvichar, Birthday | Currently a candidate for new base category; if hero text is just "Happy Diwali" and overlay-style flavouring suffices, could be an overlay. Decision pending. |
| Holi | Good Morning, Birthday, Suvichar | Colours, gulal, water — strong flavour pack candidate. |
| Eid | Good Morning, Birthday | Crescent moon, dates, henna — flavour overlay or new base category. |
| Sports Motivation | Suvichar (new base?) | Cricket overlay × Suvichar was excluded; a dedicated Sports Motivation base category is the alternative. |
| Wedding | Birthday (or new base?) | Floral, henna, mehndi flavour. Possibly a new base category with its own hero text ("Happy Wedding Day", "Anniversary Wishes"). |
| Anniversary | Birthday | Could compose with Birthday base or be its own base. |
| Patriotic / Independence Day | Good Morning, Suvichar | Tricolour, flag motifs — strong national flavour overlay. |

---

# Part 7 — V2 Expansion (live in branch `V2--->-Expansion-to-7-more-categories`)

This part documents three v2 additions on top of the v1 PRD: a **bottom 20% personalization safe zone** that all generated posters now respect, **adaptive B1 hero-text colour** based on photo aesthetic + overlay strength, and **7 new base-category packs** (`CATEGORY_PACKS` config table).

## 43. Bottom Safe Zone (Personalization Band)

### 43.1 Why

Every generated poster needs a clean bottom band where the user can composite their own name / signature / branding post-generation without the AI's main subject or hero text overlapping. The band has to read as intentional, calm space — not a blank gap that feels weird if the user adds nothing. Frame, background fill, sparkle particles, and small motif accents are free to extend so the area never looks empty.

### 43.2 Spec

- **Reserved height:** bottom **20% of canvas** (≈19.52% on the wizard preview).
- **Clamped above safe zone:** hero text, main illustration subject, B1 supporting subject.
- **Free to extend into safe zone:** background fill, frame border, decorative motifs, Track-A sparkle particles, A2 sub-element accents.
- **B1 specific:** photograph extends naturally to the bottom edge with a **soft gradient fade-out**, but the photo's main subject must stay above the band.
- **L5 (Text Bottom):** hero text band moves up to the **60–80% from top** strip so it sits above the safe zone instead of overlapping it.
- **Other layouts (L1, L2, L3, L4, L6):** illustration position phrase appended with "main subject above the bottom 20% personalization safe zone".

### 43.3 Prompt language

Four constants drive consistent language across all 5 platform builders:

| Constant | Used by | Length |
|----------|---------|:------:|
| `SAFE_ZONE_DESC` | A1/A2 — MJ, Leonardo, Gemini (full keyword set) | ~ 280 chars |
| `SAFE_ZONE_DESC_B1` | B1 — MJ, Leonardo, Gemini (full keyword set with photo fade) | ~ 280 chars |
| `SAFE_ZONE_FIREFLY_AB` | A1/A2 — Firefly with-text + no-text (compact) | ~ 110 chars |
| `SAFE_ZONE_FIREFLY_B1` | B1 — Firefly with-text + no-text (compact) | ~ 100 chars |

`SAFE_ZONE_DESC` (A1/A2) verbatim:

> the bottom 20 percent of the canvas is a clean personalization safe zone — the main illustration subject and any hero text must stay above this zone, but the background colour, frame border, and small decorative accents like sparkle particles or scattered motifs may extend naturally into it so the area never looks empty or out of place

`SAFE_ZONE_DESC_B1` verbatim:

> the bottom 20 percent of the canvas is a personalization safe zone — the photograph extends naturally to the bottom edge, but the main subject of the photo must stay above this zone and the bottom should soft-gradient fade slightly to a calmer area so user-added text or branding sits comfortably without looking out of place

### 43.4 Layout text-zone updates (per layout)

| Layout | Pre-v2 text zone | v2 text zone |
|--------|-----------------|--------------|
| L1 Text Top | upper 25% | upper 25% (unchanged) |
| L2 Overlay/Centre | centred | centred at 40–50% from top, never overlapping bottom 20% |
| L3 Text Left | left column all rows | left column, text stays above bottom 20% |
| L4 Text Right | right column all rows | right column, text stays above bottom 20% |
| L5 Text Bottom | lower 25% | **band between 60–80% from top** (above safe zone) |
| L6 Text Centre | central 60% | central 60%, kept above bottom 20% |

### 43.5 Layout diagrams

The wizard's layout-step preview SVGs gain a dashed bottom band labelled "safe zone". For L5, the text rect is redrawn at 60–80% to match the new prompt language.

### 43.6 Character budget impact

Adding the safe-zone phrase to each prompt costs:
- A1/A2 Firefly: + ~ 110 chars (compact)
- A1/A2 MJ / Leonardo / Gemini: + ~ 280 chars (full)
- B1 Firefly: + ~ 100 chars (compact)
- B1 MJ / Leonardo / Gemini: + ~ 280 chars (full)

Worst-case Firefly with-text across all 10 categories × A1 measured at **818–838 chars** post-update — > 110 chars headroom under the 950-char cap.

---

## 44. Adaptive B1 Hero Text Colour

### 44.1 Why

Pre-v2, all B1 prompts hardcoded "white decorative font" / "white text". On bright/airy or muted-earth photographs (Track D, Track E), white type vanishes even with a darker overlay. The fix is to pick the text colour based on the photo's aesthetic register — track-tuned default — with the dark-overlay case still using white.

### 44.2 Spec

New `getB1TextColour()` helper returns `{ name, desc }` based on `STATE.track` and `STATE.overlayStrength`.

**Rule:** Heavy overlay always returns white (the dark band beneath the text guarantees contrast). Light overlay returns the per-track default.

| Track | Light overlay | Heavy overlay | Reasoning |
|-------|---------------|---------------|-----------|
| **A** HDR Saturated | `white` | `white` | High-saturation, often dark/dramatic — white pops |
| **B** Editorial Muted (Portra) | `warm cream off-white (#FFF7E8)` | `white` | Pure white feels harsh on muted earth tones |
| **C** Desaturated Minimal | `very dark grey or near-black` | `white` | High-contrast minimal posters expect dark type |
| **D** Bright Lifestyle (airy) | `dark warm grey / charcoal (#2A1F1A)` | `white` | Bright/overexposed scenes — white vanishes |
| **E** Soft Dreamy (pastel) | `soft warm dark or muted maroon` | `white` | Pastel BG + white = washed out; warm dark reads |

### 44.3 Prompt injection

Replaced hardcoded `white` references in:

| Builder | Pre-v2 | v2 |
|---------|--------|-----|
| `buildB1LeonardoPrompt` | `Keep this area darker for white text readability.` | `Keep this area readable for ${txtColour.desc} text overlay.` |
| `buildB1FireflyWithTextPrompt` | `"${txt}" text in white decorative font in the text zone, legible.` | `"${txt}" text in ${txtColour.name} decorative font in the text zone, legible.` |
| `buildB1GeminiPrompt` | `... ensure white text overlay is legible ...` | `... ensure ${txtColour.desc} text overlay is legible ...` |

`buildB1MJPrompt` and `buildB1FireflyNoTextPrompt` were untouched (no text-rendering instruction in either).

### 44.4 A1/A2 unchanged

Illustrated archetypes (A1, A2) source their text colour from per-palette `roles.textCol`, which is already tuned per palette × track. No change.

### 44.5 No new wizard step

The colour is fully derived from existing wizard inputs (Track + Overlay Strength). No additional UI surface — the wizard stays at 7 steps.

---

## 45. Category Pack: Rath Yatra

> **Hero text:** "शुभ रथ यात्रा" / "Happy Rath Yatra" / "जय जगन्नाथ" (fixed — no Custom Text step).
> **Seasonal:** Yes — June/July (Ashadha Shukla Dwitiya).
> **Track filter:** A ✅, B ✅, C ✅, D ❌, E ✅.
> **Overlay compatibility:** Devotional ✅, Summer ✅, Rain/Monsoon ✅, Cricket —.

### 45.1 What it is

Festival-first devotional category centred on Lord Jagannath's chariot procession. Visual energy from the iconic chariot (rath), the three deities (Jagannath, Balabhadra, Subhadra), procession crowd, and Odia/Puri cultural markers. Track D blocked — playful doodle treatment of sacred deities is tonally disrespectful (same logic as the Devotional overlay).

### 45.2 Illustration catalogue (22 items)

**GM carry-overs (3):** GM-I3-01 Marigold Garland, GM-I4-01 Lit Diya, GM-I3-02 Lotus.

**Chariot & Procession (5):**

| ID | Name | Archetypes |
|----|------|------------|
| RY-I01 | Rath (Chariot) — Full | A1, A2, B1 |
| RY-I02 | Chariot Wheel (Close-up) | A1, A2 |
| RY-I03 | Three Chariots (Procession) | A2, B1 |
| RY-I04 | Procession Crowd | B1 |
| RY-I05 | Chariot Rope (Pulling) | B1 |

**Deities & Sacred (4):**

| ID | Name | Archetypes |
|----|------|------------|
| RY-I06 | Jagannath Face (Iconic) | A1, A2 |
| RY-I07 | Jagannath-Balabhadra-Subhadra Trio | A1, A2 |
| RY-I08 | Sudarshan Chakra | A1, A2 |
| RY-I09 | Neela Chakra (Blue Wheel) | A1, A2, B1 |

**Temple & Setting (3):** RY-I10 Jagannath Temple (Puri), RY-I11 Grand Road (Bada Danda), RY-I12 Temple Doorway (Singha Dwara).

**Decorative & Festive (7):** RY-I13 Marigold Toran with Mango Leaves, RY-I14 Coconut & Banana Offering, RY-I15 Rath Yatra Flag, RY-I16 Conch Shell (Shankh), RY-I17 Puri Beach at Sunrise, RY-I18 Prasad Thali (Mahaprasad), RY-I19 Odia Rangoli (Jhoti Chita).

### 45.3 Per-track motifs (RY-MT-*)

5 motifs each for A/B/C/E (D blocked). Highlights:
- **Track A:** Gold Chariot Wheel, Jagannath Face (Gold), Marigold & Mango Leaf Garland, Sudarshan Chakra (Gold), Temple Spire Silhouette.
- **Track B:** Block-Print Chariot Wheel, Jhoti Chita Corner, Modern Jagannath Icon, Mango Leaf String, Conch Shell (Line Art).
- **Track C:** None / Minimal Wheel Arc / Single Mango Leaf / Dot Mandala (Subtle).
- **Track E:** None / Watercolour Wheel / Soft Marigold Wash / Pastel Lotus.

### 45.4 Prompt context

| Element | Value |
|---------|-------|
| atmosphereInline | `Rath Yatra festival procession, Jagannath temple celebration` |
| sceneAuthenticity | `real Rath Yatra celebration in Puri, Odisha` |
| stylePhMoodWord | `festival` |
| Negatives | `funeral, mourning, sad, dark mood, horror, cartoon, doodle, playful, comic, modern urban, neon, nightclub` |
| Firefly Atmosphere | `Rath Yatra festival, Jagannath procession` |
| Firefly Mood | `devotional, festive, joyful, sacred, grand` |
| Firefly B1 Scene | `Puri chariot procession, temple backdrop, festival crowd` |

### 45.5 Layout bias

L5 ★ Best · L2 ★ Best · L1 ✓ · L6 ✓ · L3/L4 ✓.

---

## 46. Category Pack: Vat Savitri

> **Hero text:** "वट सावित्री व्रत की शुभकामनाएं" / "Happy Vat Savitri" / "सुहाग का त्योहार" (fixed).
> **Seasonal:** Yes — May/June (Jyeshtha Amavasya / Purnima).
> **Track filter:** A ✅, B ✅, C ✅, D ❌, E ✅.
> **Overlay compatibility:** Devotional ✅, Summer ✅, Rain —, Cricket —.

### 46.1 What it is

Married women's vrat — devotion of Savitri to Satyavan; women tie sacred thread around banyan (vat) tree and pray for husband's long life. Visual energy from the sacred banyan, suhag symbols (red bangles, sindoor, mangalsutra, mehendi), and the Savitri-Satyavan legend. Track D blocked — playful treatment of a solemn vrat is disrespectful.

### 46.2 Illustration catalogue (20 items)

**GM carry-overs (3):** GM-I3-01 Marigold Garland, GM-I4-01 Lit Diya, GM-I3-02 Lotus.

**Sacred Tree & Ritual (5):** VS-I01 Banyan Tree (Vat Vriksha), VS-I02 Thread-Tying Ritual (B1), VS-I03 Banyan Tree (Silhouette), VS-I04 Sacred Thread (Mauli), VS-I05 Pooja Thali (Vat Savitri).

**Suhag Symbols (5):** VS-I06 Red Bangles, VS-I07 Sindoor Box (Open), VS-I08 Mangalsutra, VS-I09 Mehendi Hands, VS-I10 Toe Rings (Bichiya).

**Devotional & Atmosphere (7):** VS-I11 Savitri-Satyavan, VS-I12 Banyan Leaf (Close-up), VS-I13 Women at Banyan Tree (B1), VS-I14 Incense & Flowers at Tree Base, VS-I15 Red & Green Saree Drape, VS-I16 Coconut & Banana Offering, VS-I17 Turmeric & Kumkum.

### 46.3 Per-track motifs (VS-MT-*)

- **Track A:** Gold Banyan Leaf, Red Bangle Cluster, Mauli Thread Garland, Gold Sindoor Dot, Marigold & Mango Leaf Toran.
- **Track B:** Block-Print Banyan Leaf, Rangoli Vat Corner, Modern Bangle Icon, Mehendi Pattern Strip, Mango Leaf String.
- **Track C:** None / Minimal Leaf Outline / Thin Thread Line / Dot Bindi Accent.
- **Track E:** None / Watercolour Banyan Leaf / Pastel Bangles / Soft Marigold Wash.

### 46.4 Prompt context

| Element | Value |
|---------|-------|
| atmosphereInline | `Vat Savitri vrat celebration, sacred banyan tree ritual` |
| sceneAuthenticity | `real Indian Vat Savitri celebration, married women's festival` |
| Negatives | `funeral, mourning, dark mood, horror, cartoon, doodle, playful, comic, modern urban, neon, nightclub, widow, white saree, barren` |
| Firefly Atmosphere | `Vat Savitri vrat, sacred banyan tree, suhag` |
| Firefly Mood | `devotional, auspicious, blessed, sacred` |
| Firefly B1 Scene | `banyan tree with thread, women in red saree, pooja` |

### 46.5 Layout bias

L5 ★ Best · L2 ★ Best · L6 ✓ · L1 ✓ · L3/L4 ~ With Care (banyan tree is wide).

---

## 47. Category Pack: Father's Day

> **Hero text:** "Happy Father's Day" / "पापा, आपको सलाम" / "पिता दिवस की शुभकामनाएं" (fixed).
> **Seasonal:** Yes — Third Sunday of June.
> **Track filter:** A ✅, B ✅, C ✅, D ✅, E ✅ (only category that keeps all 5 tracks — secular/emotional, not sacred).
> **Overlay compatibility:** Devotional —, Summer ✅, Rain —, Cricket/IPL ✅.

### 47.1 What it is

Warm celebration of fathers and father-figures — emotional bonds, dad's personal objects (watch, glasses, tie, shoes, briefcase), nostalgic Indian moments (cricket-with-dad, newspaper-and-chai). Universal/cross-cultural — not religious. Cricket + Father's Day is a powerful Indian cultural pairing.

### 47.2 Illustration catalogue (24 items)

**GM carry-overs (2):** GM-I1-01 Steaming Chai Cup ("Chai with Dad"), GM-I6-01 Bird Flock at Sunrise.

**Father-Child Moments (6):** FD-I01 Father & Child (Silhouette), FD-I02 Father Lifting Child, FD-I03 Father & Child on Shoulders, FD-I04 Father & Daughter, FD-I05 Father Teaching (Cycle/Cricket), FD-I06 Old Hands Holding Young Hands.

**Dad's Objects & Symbols (8):** FD-I07 Wristwatch, FD-I08 Spectacles, FD-I09 Necktie, FD-I10 Shoes (Pair), FD-I11 Briefcase, FD-I12 Toolbox/Spanner, FD-I13 Newspaper & Chai, FD-I14 Cricket Bat (Old/Worn).

**Emotional & Atmospheric (8):** FD-I15 Trophy/#1 Dad, FD-I16 Heart, FD-I17 Family Tree, FD-I18 Star/Shield, FD-I19 Moustache (Fun), FD-I20 Crown (King Dad), FD-I21 Garden/Plant in Pot, FD-I22 Sunset/Park Bench (B1).

### 47.3 Per-track motifs (FD-MT-*) — all 5 tracks

- **Track A:** Gold Crown, Gold Star Cluster, Ornate Heart, Trophy Accent, Confetti & Sparkle.
- **Track B:** Block-Print Heart, Modern Moustache Icon, Tie Stripe Pattern, Simple Star Accent.
- **Track C:** None / Minimal Heart Line / Thin Star Outline / Dot Trail.
- **Track D (only Father's Day uses D!):** Doodle Heart, Doodle Crown, Doodle Star Burst, Sticker Moustache, Doodle Trophy.
- **Track E:** None / Watercolour Heart / Pastel Star / Soft Leaf Wreath.

### 47.4 Prompt context

| Element | Value |
|---------|-------|
| atmosphereInline | `Father's Day celebration, warm emotional family setting` |
| sceneAuthenticity | `real warm Indian family moment, father-child bond` |
| Negatives | `funeral, mourning, sad, dark mood, horror, lonely, abandoned, cold, harsh, angry, violent, broken` |
| Firefly Atmosphere | `Father's Day warmth, family bond, proud` |
| Firefly Mood | `warm, proud, loving, nostalgic, grateful` |
| Firefly B1 Scene | `father and child moment, warm golden home or park` |

### 47.5 Layout bias

L5 ★ Best · L2 ★ Best · L1 ✓ · L6 ✓ · L3/L4 ✓.

---

## 48. Category Pack: Devotional — Shivji

> **Hero text:** "ॐ नमः शिवाय" / "हर हर महादेव" / "Om Namah Shivaya" (default — **editable** Custom Text step).
> **Seasonal:** No (peak Sawan July–August + Maha Shivratri).
> **Track filter:** A ✅, B ✅, C ✅, D ❌, E ✅.
> **Overlay compatibility:** Devotional ✅, Summer —, Rain/Monsoon ✅ (Sawan = Shiva's sacred monsoon month), Cricket —.

### 48.1 What it is

Lord Shiva — Mahadev devotional. Visual energy from Shiva's iconic symbols: trishul, damru, Nandi, Ganga, third eye, blue skin reference, Kailash, lingam, rudraksha, snake (Vasuki). Track D blocked — playful treatment of Mahadev is disrespectful.

### 48.2 Wizard flow change

`Archetype → Track → Layout → Colour → Font → Illustration → Intensity → Custom Text ✎`

Custom Text step is pre-filled with the default greeting. User can keep it, pick a language variant from chip-row buttons, or type their own Shiv-bhakti text.

### 48.3 Illustration catalogue (22 items)

**GM carry-overs (2):** GM-I3-02 Lotus, GM-I4-01 Lit Diya.

**Shiva — Iconic Forms (8):** SH-I01 Shiva Lingam, SH-I02 Trishul (Trident), SH-I03 Damru (Drum), SH-I04 Nandi (Bull), SH-I05 Third Eye (Stylised), SH-I06 Rudraksha Mala, SH-I07 Crescent Moon, SH-I08 Snake (Vasuki).

**Shiva — Scenes & Settings (6):** SH-I09 Mount Kailash, SH-I10 Ganga Flowing (B1), SH-I11 Shiva Temple Silhouette, SH-I12 Meditation Cave (B1), SH-I13 Bel/Bilva Tree, SH-I14 Burning Pyre/Sacred Fire.

**Pooja & Devotional (6):** SH-I15 Bilva Leaves on Lingam, SH-I16 Abhishek (Water Pour), SH-I17 Shiva Pooja Thali, SH-I18 Vibhuti (Ash Lines), SH-I19 Kanwar (Water Pot on Pole), SH-I20 Ganga Aarti (B1).

### 48.4 Per-track motifs (SH-MT-*)

- **Track A:** Gold Trishul, Damru with Gold Bells, Rudraksha String, Snake (Ornate), Om with Trishul Halo.
- **Track B:** Block-Print Trishul, Modern Damru Icon, Bilva Leaf Trio, Crescent Moon (Line).
- **Track C:** None / Minimal Trishul Line / Dot Tripundra.
- **Track E:** None / Watercolour Trishul / Pastel Bilva Leaf / Soft Rudraksha Wash.

### 48.5 Prompt context

| Element | Value |
|---------|-------|
| atmosphereInline | `Shiva devotional setting, sacred Mahadev worship atmosphere` |
| sceneAuthenticity | `real Shiva temple or Himalayan sacred setting` |
| Negatives | `funeral, dark mood, horror, cartoon, doodle, playful, comic, modern urban, neon, nightclub, party, alcohol, other deities, cross-faith symbols` |
| Firefly Atmosphere | `Shiva devotional, sacred Mahadev, temple glow` |
| Firefly Mood | `reverent, powerful, meditative, sacred` |
| Firefly B1 Scene | `Shiva temple at dawn, Kailash, lingam pooja` |

### 48.6 Layout bias

L2 ★ Best · L5 ★ Best · L6 ✓ · L1 ✓ · L3/L4 ✓.

---

## 49. Category Pack: Devotional — Ganeshji

> **Hero text:** "गणपति बप्पा मोरया" / "श्री गणेशाय नमः" / "Jai Ganesh" (default — **editable**).
> **Seasonal:** No (peak Ganesh Chaturthi August/September).
> **Track filter:** A ✅, B ✅, C ✅, D ❌, E ✅.
> **Overlay compatibility:** Devotional ✅, Summer —, Rain/Monsoon ✅ (Chaturthi often falls in late monsoon), Cricket —.

### 49.1 What it is

Lord Ganesha — Ganpati bhakti, Ganesh Chaturthi, Wednesday devotional. Visual energy from Ganesha's iconic form (elephant head, modak, mouse, lotus seat) and the warm, auspicious, obstacle-removing energy.

### 49.2 Wizard flow

`Archetype → Track → Layout → Colour → Font → Illustration → Intensity → Custom Text ✎`

### 49.3 Illustration catalogue (22 items)

**GM carry-overs (3):** GM-I3-01 Marigold Garland, GM-I4-01 Lit Diya, GM-I3-02 Lotus.

**Ganesh — Iconic Forms (8):** GN-I01 Ganesh Idol (Seated), GN-I02 Ganesh Face (Close-up), GN-I03 Modak (Sweet), GN-I04 Mouse (Mushak), GN-I05 Om / Ganesha Om, GN-I06 Ganesh Silhouette, GN-I07 Broken Tusk, GN-I08 Lotus Seat (with Ganesh).

**Setting & Scene (4):** GN-I09 Ganesh Mandal/Pandal (B1), GN-I10 Ganesh Visarjan Procession (B1), GN-I11 Ganesh Temple Doorway (B1), GN-I12 Home Pooja Setup.

**Pooja & Devotional (7):** GN-I13 Ganesh Pooja Thali, GN-I14 Durva Grass Bundle, GN-I15 Coconut (Whole), GN-I16 Red Hibiscus, GN-I17 Dhol/Drum, GN-I18 Rangoli (Ganesh) (B1), GN-I19 Mango Leaf Toran with Marigold.

### 49.4 Per-track motifs (GN-MT-*)

- **Track A:** Gold Ganesh Silhouette, Modak String, Marigold & Durva Garland, Om with Ganesh Trunk, Sparkle Cluster.
- **Track B:** Block-Print Ganesh, Rangoli Corner (Ganesh), Modern Modak Icon, Durva Grass Line.
- **Track C:** None / Minimal Ganesh Line / Single Modak Outline.
- **Track E:** None / Watercolour Ganesh / Pastel Hibiscus / Soft Marigold Wash.

### 49.5 Prompt context

| Element | Value |
|---------|-------|
| atmosphereInline | `Ganesh devotional setting, Ganpati worship atmosphere` |
| sceneAuthenticity | `real Ganesh pooja or Chaturthi celebration setting` |
| Negatives | `funeral, dark mood, horror, cartoon, doodle, playful, comic, modern urban, neon, nightclub, party, alcohol, other deities, cross-faith symbols` |
| Firefly Atmosphere | `Ganesh devotional, Ganpati pooja, sacred` |
| Firefly Mood | `auspicious, joyful, blessed, sacred` |
| Firefly B1 Scene | `Ganesh idol home pooja, mandal decoration, festive` |

### 49.6 Layout bias

L2 ★ Best · L5 ★ Best · L6 ✓ · L1 ✓ · L3/L4 ✓.

---

## 50. Category Pack: Devotional — Jesus

> **Hero text:** "God Bless You" / "Praise the Lord" / "प्रभु आपको आशीर्वाद दें" (default — **editable**).
> **Seasonal:** No (peak Christmas, Good Friday, Easter).
> **Track filter:** A ✅, B ✅, C ✅, D ❌, E ✅.
> **Overlay compatibility:** Devotional ✅, Summer —, Rain —, Cricket —.

### 50.1 What it is

Christian devotional — Sunday blessings, Christmas, Easter, faith-based inspiration. Visual energy from cross, church, candle, dove, Bible, praying hands, divine light. Track D blocked — playful doodle of cross/Bible/prayer is tonally wrong; Indian Christian imagery leans respectful and warm.

### 50.2 Wizard flow

`Archetype → Track → Layout → Colour → Font → Illustration → Intensity → Custom Text ✎`

### 50.3 Illustration catalogue (20 items)

**GM carry-overs (2):** GM-I4-01 Lit Diya/Candle, GM-I3-02 Lotus.

**Sacred Symbols (8):** JE-I01 Cross (Wooden), JE-I02 Cross (Golden/Ornate), JE-I03 Rosary Beads, JE-I04 Dove (Peace), JE-I05 Bible (Open), JE-I06 Praying Hands, JE-I07 Fish (Ichthys), JE-I08 Crown of Thorns.

**Church & Setting (5):** JE-I09 Church (Exterior — Indian Goa/Kerala/CNI style), JE-I10 Church Interior (Aisle) (B1), JE-I11 Stained Glass Window, JE-I12 Church Bell, JE-I13 Sunset Cross (Hilltop).

**Devotional & Atmosphere (5):** JE-I14 Candle Row (Vigil), JE-I15 Olive Branch, JE-I16 Light Rays (Divine), JE-I17 Lily/White Flowers, JE-I18 Bread & Wine.

### 50.4 Per-track motifs (JE-MT-*)

- **Track A:** Gold Cross, Dove with Rays, Lily & Vine Garland, Rosary Loop, Stained Glass Border.
- **Track B:** Modern Cross Icon, Olive Branch Strip, Dove (Line Art), Candle Icon Row.
- **Track C:** None / Minimal Cross Line / Single Dove Outline.
- **Track E:** None / Watercolour Cross / Pastel Lily / Soft Candle Glow.

### 50.5 Prompt context

| Element | Value |
|---------|-------|
| atmosphereInline | `Christian devotional setting, peaceful church or prayer atmosphere` |
| sceneAuthenticity | `real Indian church or Christian home prayer setting` |
| Negatives | `funeral, horror, dark mood, cartoon, doodle, playful, comic, neon, nightclub, party, alcohol, Hindu deities, Islamic symbols, temple, mosque` |
| Firefly Atmosphere | `Christian devotional, peaceful church, divine light` |
| Firefly Mood | `blessed, peaceful, hopeful, serene` |
| Firefly B1 Scene | `Indian church morning, cross sunrise, prayer candles` |

### 50.6 Layout bias

L2 ★ Best · L5 ★ Best · L1 ✓ · L6 ✓ · L3/L4 ✓.

---

## 51. Category Pack: Devotional — Islamic

> **Hero text:** "Jumma Mubarak" / "Assalamu Alaikum" / "بسم الله الرحمن الرحیم" / "अल्लाह की रहमत" (default — **editable**).
> **Seasonal:** No (peak Ramadan, Eid-ul-Fitr, Eid-ul-Adha, Shab-e-Barat).
> **Track filter:** A ✅, B ✅, C ✅, D ❌, E ✅.
> **Overlay compatibility:** Devotional ✅, Summer —, Rain —, Cricket —.

### 51.1 What it is

Islamic devotional — Jumma Mubarak (Friday), Eid greetings, Ramadan, Salam blessings. Visual energy from crescent and star, mosque, Quran, prayer beads (tasbih), Arabic calligraphy (non-Quranic), Ramadan lantern (fanoos), and geometric Islamic patterns. Track D blocked — playful doodle of Islamic sacred symbols is disrespectful; Islamic art traditionally leans towards geometric precision and calligraphic elegance.

### 51.2 Wizard flow

`Archetype → Track → Layout → Colour → Font → Illustration → Intensity → Custom Text ✎`

### 51.3 Illustration catalogue (20 items)

**GM carry-overs (1):** GM-I4-01 Lit Diya/Lamp.

**Sacred Symbols (8):** IS-I01 Crescent Moon & Star, IS-I02 Mosque Silhouette, IS-I03 Quran (Open), IS-I04 Tasbih (Prayer Beads), IS-I05 Arabic Calligraphy (Bismillah), IS-I06 Praying Hands (Dua), IS-I07 Lantern (Fanoos), IS-I08 Dates (Khajoor).

**Mosque & Setting (4):** IS-I09 Mosque (Grand, Front View) (B1), IS-I10 Mosque Interior (Mihrab) (B1), IS-I11 Minaret (Close-up), IS-I12 Jali Screen (Geometric).

**Devotional & Atmosphere (6):** IS-I13 Prayer Cap & Beads, IS-I14 Iftar Table (B1), IS-I15 Full Moon (Eid Moon), IS-I16 Islamic Geometric Pattern, IS-I17 Green Dome, IS-I18 Rosewater & Attar.

### 51.4 Per-track motifs (IS-MT-*)

- **Track A:** Gold Crescent & Star, Islamic Geometric Border, Lantern (Fanoos) Row, Arabic Calligraphy Accent, Dome & Minaret Silhouette.
- **Track B:** Modern Crescent Icon, Geometric Star Pattern, Lantern (Line Art), Arabesque Vine.
- **Track C:** None / Minimal Crescent Line / Geometric Star (Single).
- **Track E:** None / Watercolour Crescent / Pastel Lantern / Soft Geometric Wash.

### 51.5 Prompt context

| Element | Value |
|---------|-------|
| atmosphereInline | `Islamic devotional setting, peaceful mosque or prayer atmosphere` |
| sceneAuthenticity | `real Indian mosque or Muslim home prayer setting` |
| Negatives | `funeral, horror, dark mood, cartoon, doodle, playful, comic, neon, nightclub, party, alcohol, Hindu deities, cross, church, temple, pork, figurative depiction of Prophet` |
| Firefly Atmosphere | `Islamic devotional, mosque prayer, sacred` |
| Firefly Mood | `blessed, peaceful, reverent, serene` |
| Firefly B1 Scene | `Indian mosque at fajr dawn, crescent moon, prayer` |

### 51.6 Layout bias

L2 ★ Best · L5 ★ Best · L6 ★ Best (Islamic geometric frame is a natural fit for centred text) · L1 ✓ · L3/L4 ✓.

---

## 52. Master tables — V2 expansion (10 categories total)

### 52.1 Track locking — all 10 categories

| Category | A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|----------|:-:|:-:|:-:|:-:|:-:|
| Good Morning | ✅ | ✅ | ✅ | ✅ | ✅ |
| Birthday | ✅ | ✅ | ✅ | ✅ | ✅ |
| Suvichar | ✅ | ✅ | ✅ | ✅ | ✅ (filtered by feeling) |
| Rath Yatra | ✅ | ✅ | ✅ | ❌ | ✅ |
| Vat Savitri | ✅ | ✅ | ✅ | ❌ | ✅ |
| Father's Day | ✅ | ✅ | ✅ | ✅ | ✅ |
| Devotional — Shivji | ✅ | ✅ | ✅ | ❌ | ✅ |
| Devotional — Ganeshji | ✅ | ✅ | ✅ | ❌ | ✅ |
| Devotional — Jesus | ✅ | ✅ | ✅ | ❌ | ✅ |
| Devotional — Islamic | ✅ | ✅ | ✅ | ❌ | ✅ |

**Pattern:** Track D is blocked for ALL devotional/religious categories (6 of the 7 v2 packs). Only Father's Day keeps all 5 tracks — secular & emotional, not sacred.

### 52.2 Overlay compatibility — all 10 categories

| Category | Devotional | Summer | Rain/Monsoon | Cricket/IPL |
|----------|:---:|:---:|:---:|:---:|
| Good Morning | ✅ | ✅ | ✅ | ✅ |
| Birthday | — | ✅ | — | ✅ |
| Suvichar | ✅ | ✅ | ✅ | — |
| Rath Yatra | ✅ | ✅ | ✅ | — |
| Vat Savitri | ✅ | ✅ | — | — |
| Father's Day | — | ✅ | — | ✅ |
| Devotional — Shivji | ✅ | — | ✅ | — |
| Devotional — Ganeshji | ✅ | — | ✅ | — |
| Devotional — Jesus | ✅ | — | — | — |
| Devotional — Islamic | ✅ | — | — | — |

### 52.3 Custom text behaviour — all 10 categories

| Category | Custom Text Step? | Default Pre-fill | User-editable? |
|----------|:---:|---|:---:|
| Good Morning | No | "Good Morning" | No |
| Birthday | No | "Happy Birthday" | No |
| Suvichar | **Yes** | (empty — required) | Yes — required |
| Rath Yatra | No | "शुभ रथ यात्रा" | No |
| Vat Savitri | No | "वट सावित्री व्रत की शुभकामनाएं" | No |
| Father's Day | No | "Happy Father's Day" | No |
| Devotional — Shivji | **Yes** | "ॐ नमः शिवाय" | Yes — optional |
| Devotional — Ganeshji | **Yes** | "गणपति बप्पा मोरया" | Yes — optional |
| Devotional — Jesus | **Yes** | "God Bless You" | Yes — optional |
| Devotional — Islamic | **Yes** | "Jumma Mubarak" | Yes — optional |

### 52.4 Illustration count — V2 expansion summary

| Category | Carry-over | New | Total |
|----------|:----------:|:---:|:-----:|
| Rath Yatra | 3 | 19 | 22 |
| Vat Savitri | 3 | 17 | 20 |
| Father's Day | 2 | 22 | 24 |
| Devotional — Shivji | 2 | 20 | 22 |
| Devotional — Ganeshji | 3 | 19 | 22 |
| Devotional — Jesus | 2 | 18 | 20 |
| Devotional — Islamic | 2 | 18 | 20 |
| **V2 expansion total** | **17** | **133** | **150** |

### 52.5 Wizard flow variants

| Variant | Used by | Step sequence |
|---------|---------|---------------|
| Standard | GM, Birthday, Rath Yatra, Vat Savitri, Father's Day | `Template → (Frame/Density/Overlay) → Layout → Track → Colour & Finish → Visual / Scene → Intensity` |
| Suvichar | Suvichar | adds **Feeling** (after Template) and **Custom Text** (final) |
| Devotional editable | Shivji, Ganeshji, Jesus, Islamic | standard + **Custom Text** (final, pre-filled) |

---

## 53. Implementation summary — V2 expansion

### 53.1 New data structures

| Symbol | Lines | Purpose |
|--------|:-----:|---------|
| `CATEGORY_PACKS` | ~ 700 | Single config table holding all 7 v2 categories' data (id, name, icon, hero text + lang variants, customText flag, blockedTracks, appliesOverlays, carryoverIds, illusCats, motifs per track, atmosphere bundle, negatives, firefly compact strings, layout bias). |
| `SAFE_ZONE_DESC` / `SAFE_ZONE_DESC_B1` / `SAFE_ZONE_FIREFLY_AB` / `SAFE_ZONE_FIREFLY_B1` | 4 const | Personalization safe-zone prompt strings (full + compact). |

### 53.2 New helper functions

| Function | Purpose |
|----------|---------|
| `getCategoryPack()` | Returns the active pack object or `null` for the original 3 categories. |
| `getPackIllusCats()` | Builds the catalogue (carry-overs + native sub-categories), filtered by archetype — mirrors `getBirthdayIllusCats` / `getSuvicharIllusCats` shape so `applyOverlayToCatalogue` and the Visual / B1-Scene steps consume it identically. |
| `getB1TextColour()` | Returns `{name, desc}` for B1 hero text colour based on track + overlay strength. |
| `seedCustomText(v)` | Wires the language-variant chip-row buttons in the Custom Text step. |

### 53.3 Modified dispatch functions

All consult `getCategoryPack()` first, falling through to the original GM/Birthday/Suvichar logic for the 3 original categories:

- `getCategoryLabel()` — pack.name takes precedence.
- `getDisplayText()` — pack.heroText (fixed) or `STATE.customText || pack.heroText` (editable fallback).
- `getCategoryAtmosphere()` — pack.atmosphere bundle.
- `getMotifOptions()` — pack.motifs[track] (with framework fallback if track missing, e.g. Father's Day uses Track-D base motifs since FD-MT-D* exists).
- `getFilteredTracks()` — applies pack.blockedTracks on top of feeling-filter and overlay block.
- `buildNegatives()` (A1/A2) and `gatherB1PromptData` — append pack.negatives.
- `getOverlaysForCategory(catId)` — checks pack.appliesOverlays for v2 categories; original `o.appliesTo` for the 3 originals.
- `getIllusItem()` and B1 scene-element loop — also resolve pack-native illustration IDs.

### 53.4 UI updates

- `renderStep1()` — picker shows 10 cards (3 originals + 7 packs via `Object.values(CATEGORY_PACKS)`).
- `getSteps()` — appends `'custom_text'` for the 4 packs with `customText: true` (Shivji, Ganeshji, Jesus, Islamic).
- `renderCustomTextStep()` — reused for Suvichar (mandatory quote) AND the 4 editable packs (pre-filled hero text, language-variant chip row).
- `canProceed()` for `custom_text` — accepts empty for editable packs (heroText is the fallback); Suvichar still requires non-empty.
- Audit panel — surfaces a "Greeting Text" row for editable packs.
- Layout diagrams — dashed safe-zone band at bottom; L5 text rect redrawn at 60–80% from top.

### 53.5 Verification

Runtime smoke tests (all 19 passing):

- All 7 packs return correct labels, hero text, track filters, motif counts, overlay compatibility.
- Custom Text behaviour: Shivji empty → fallback to "ॐ नमः शिवाय"; Shivji typed → user text. Rath Yatra always returns fixed text and skips the Custom Text step.
- Safe-zone language present in MJ, Leonardo, Firefly with-/without-text, and Gemini for both archetypes.
- B1 adaptive text colour matches the track × overlay-strength matrix exactly.
- Worst-case Firefly with-text across all 10 categories × A1: **818–838 chars** (≤ 950 cap with > 110 chars headroom).

---

# Appendices

## Appendix A — Master Cross-Reference

### Overlay × Base compatibility (quick reference)

| Overlay | Good Morning | Suvichar | Birthday |
|---------|:---:|:---:|:---:|
| Devotional | ✅ | ✅ | — |
| Summer | ✅ | ✅ | ✅ |
| Rain / Monsoon | ✅ | ✅ | — |
| Cricket / IPL | ✅ | — | ✅ |

### Overlay × Track compatibility (master filter)

| Overlay | A | B | C | D | E |
|---------|:-:|:-:|:-:|:-:|:-:|
| Devotional | ✅ | ✅ | ✅ | ❌ | ✅ |
| Summer | ✅ | ✅ | ✅ | ✅ | ✅ |
| Rain / Monsoon | ❌ | ✅ | ✅ | ✅ | ✅ |
| Cricket / IPL | ✅ | ✅ | ✅ | ✅ | ❌ |

### Suvichar Feeling × Track compatibility

| Feeling | A | B | C | D | E |
|---------|:-:|:-:|:-:|:-:|:-:|
| SV-F1 Rise & Shine | ✅ | ✅ | ✅ | ✅ | ✅ |
| SV-F2 Still Waters | ❌ | ✅ | ✅ | ❌ | ✅ |
| SV-F3 Bittersweet | ❌ | ✅ | ✅ | ❌ | ✅ |
| SV-F4 Everyday Calm | ❌ | ✅ | ✅ | ✅ | ✅ |
| SV-F5 Fire & Drive | ✅ | ❌ | ✅ | ✅ | ❌ |

### Illustration count summary

| Source | Count | Notes |
|--------|:-----:|-------|
| Good Morning library | 41 | 6 sub-categories (GM-I1..I6) |
| Birthday native | 30 | + 4 GM carry-overs = 34 total |
| Suvichar native | 30 | + 10 GM carry-overs folded into semantic categories = 40 total |
| ACCENT_ITEMS (shared) | 30 | ACC-01..ACC-30 |
| SV-ACC (Suvichar accents) | 6 | SV-ACC-01..06 |
| BD-ACC (Birthday accents) | 6 | BD-ACC-01..06 |
| Devotional overlay add | 14 | 19 base items restricted (11 GM + 8 SV) |
| Summer overlay add | 14 | 17 base items restricted (5 GM + 4 BD + 8 SV) |
| Rain / Monsoon overlay add | 15 | 19 base items restricted (11 GM + 8 SV) |
| Cricket / IPL overlay add | 15 | 22 base items restricted (15 GM + 7 BD) |
| **V2 expansion — 7 category packs** | **150** | 17 GM carry-overs + 133 native (Rath Yatra 22, Vat Savitri 20, Father's Day 24, Shivji 22, Ganeshji 22, Jesus 20, Islamic 20). See §52.4. |
| **Total catalogue across 10 categories** | **~ 264** | Native illustration count summed across Good Morning + Birthday native + Suvichar native + 7 V2 packs (excluding GM carry-overs which are reused, and overlay-added items). |

Restrictions are aggressive by design. It's better to hide a borderline item than to let a user create a "Devotional Good Morning" with a parrot or a "Cricket Birthday" with floating petals. The overlay's added illustrations fill the gap — the user never sees a depleted pool.

### Frame × Layout compatibility (recap)

| Frame ↓ / Layout → | L1 | L2 | L3 | L4 | L5 | L6 |
|--------------------|:--:|:--:|:--:|:--:|:--:|:--:|
| F1 Full Perimeter | ok | ok | ok | ok | ok | best |
| F2 Dual Band | ok | best | best | best | ok | ok |
| F3 Single Band | best | ok | ok | ok | best | caution |
| F4 Corner Accents | best | best | best | best | best | best |
| F5 Arch / Canopy | caution | ok | ok | ok | best | caution |
| F6 Temple Arch *(devotional)* | caution | best | avoid | avoid | best | caution |

---

## Appendix B — Illustration ID Conventions

| Prefix | Meaning | Example |
|--------|---------|---------|
| `GM-Ix-yy` | Good Morning illustration. `x` = sub-category (1=Beverages, 2=Nature, 3=Flowers, 4=Devotional, 5=Lifestyle, 6=Birds, 7=Food). `yy` = item index. | `GM-I3-02` Lotus in Full Bloom |
| `BD-Iyy` | Birthday native illustration. `yy` = item index 01–30. | `BD-I01` Birthday Cake |
| `SV-Iyy` | Suvichar native illustration. `yy` = item index 01–30. | `SV-I05` Lone Tree (Silhouette) |
| `OV-XXX-Iyy` | Overlay-pack illustration. `XXX` = overlay code (DEV / SUM / RAIN / CRK). | `OV-DEV-I09` Temple Silhouette |
| `ACC-yy` | Shared accent prop (A2 sub-element / B1 supporting prop). `yy` = 01–30. | `ACC-08` Fallen Petals |
| `SV-ACC-yy` | Suvichar-specific accent prop. | `SV-ACC-04` Smooth River Pebbles |
| `BD-ACC-yy` | Birthday-specific accent prop. | `BD-ACC-01` Confetti Scatter |
| `MT-x` / `MT-Bx` / `MT-Cx` etc | Per-track motif. Letter suffix = track. | `MT-3` Marigold Chain (Track A) |
| `BD-MT-Xy` | Birthday-specific motif per track. | `BD-MT-A1` Gold Foil Balloons |
| `OV-XXX-MT-Yy` | Overlay-swapped motif per track. | `OV-DEV-MT-A1` Om with Gold Halo |
| `OV-XXX-MTA-Yy` | Overlay-added motif per track (supplementary). | `OV-DEV-MTA-A1` Diya Row (Gold) |
| `Fy` | Frame type. | `F6` Temple Arch (devotional) |
| `Oy` | Overlay treatment (B1 photo darkening). | `O3` Gradient Bottom-Heavy |
| `Ly` | Layout. | `L5` Text Bottom |
| `IR-Xy` | Illustration render style per track. | `IR-B1` Loose Watercolour (Track B) |
| `FN-Xy` | Background finish per track. | `FN-3` Sparkle / Glitter (Track A) |
| `MD-y` | B1 mood (lighting + colour). | `MD-1` Golden Warm |
| `SV-Fy` | Suvichar feeling code. | `SV-F2` Still Waters |
| `OV-XXX` | Overlay pack code. | `OV-DEV` Devotional |

---

## Appendix C — Change Log

### v1.1 — V2 Expansion (current)

Adds Part 7 covering three additions to the implementation:

- **§43 Bottom Safe Zone (Personalization Band)** — bottom 20% of canvas reserved for user personalization. Hero text + main illustration subject clamped above; BG / frame / sparkle / accents free to extend so the area never reads as empty. L5 text band moves to 60–80% from top. New `SAFE_ZONE_DESC`, `SAFE_ZONE_DESC_B1`, `SAFE_ZONE_FIREFLY_AB`, `SAFE_ZONE_FIREFLY_B1` constants drive consistent prompt language across all 5 platform builders × 2 archetypes. Layout diagram SVGs gain a dashed safe-zone band.
- **§44 Adaptive B1 Hero Text Colour** — new `getB1TextColour()` helper. Heavy overlay → white. Light overlay → per-track default (A=white, B=warm cream #FFF7E8, C=very dark grey/near-black, D=dark warm grey #2A1F1A, E=warm dark/muted maroon). Replaces hardcoded "white text" in Leonardo / Firefly with-text / Gemini B1 builders. A1/A2 unchanged.
- **§45–51 Seven new category packs** — Rath Yatra, Vat Savitri, Father's Day, Devotional Shivji, Devotional Ganeshji, Devotional Jesus, Devotional Islamic. All 7 ship via a single `CATEGORY_PACKS` config table; dispatch helpers (`getCategoryPack`, `getPackIllusCats`, etc.) consult it first while the original 3 categories keep their existing logic. 4 of the 7 (Shivji, Ganeshji, Jesus, Islamic) ship an editable Custom Text step pre-filled with the default greeting + language-variant chip-row. Track D blocked for 6 of 7 (Father's Day keeps all 5 tracks).
- **§52 Master tables** — track lock × overlay compatibility × custom-text behaviour × illustration counts × wizard flow variants for all 10 categories.
- **§53 Implementation summary** — new data structures, helpers, dispatch hooks, UI updates, runtime verification.

Source: `New_Category_Packs_v1.md` (v2 expansion playbook).

Verified at runtime: 19/19 smoke tests passing; worst-case Firefly with-text across all 10 categories × A1 = 818–838 chars (≤ 950 cap, > 110 chars headroom).

Live in branch `V2--->-Expansion-to-7-more-categories`, commits `41f18b3` (7 categories) + `2f38259` (safe zone + adaptive text colour).

### v1.0 (initial document)
- Initial unified PRD merging Template Creation Framework v20, Birthday Category Pack v2, Suvichar Category Pack v2, Overlay Pack System v2.
- Sections 1–4: System architecture and glossary.
- Sections 5–18: Framework foundation (archetypes, frames, layouts, tracks, palettes, fonts, finishes, render styles, motifs, intensity, GM library, accent library).
- Sections 19–21: Base categories — Good Morning default, Birthday v2, Suvichar v2.
- Sections 22–31: Overlay Pack System v2 — architecture, compatibility, Firefly budget, 4 packs (Devotional, Summer, Rain / Monsoon, Cricket / IPL).
- Sections 32–38: Prompt engineering and implementation details.
- Sections 39–42: Extending the system + future enhancements.
- Appendices A–C: Master cross-reference, ID conventions, change log.

### Source documents merged

| Source | Last updated | Notes |
|--------|--------------|-------|
| Template_Creation_Framework_v20.md | 2026-04-29 (last canonical v20 source) | Engine spec — palettes, fonts, illustrations, prompt formulas |
| Birthday_Category_Pack_v2.md | 2026-05-05 | Adds BD-ACC sub-illustration accent library; formalises Birthday-specific negatives |
| Suvichar_Category_Pack_v2.md | 2026-05-05 | Removes SV-BG finishes, reverts locked render styles, adds Custom Text step, reorganises catalogue, adds SV-ACC sub-illustration library |
| Overlay_Pack_System_v2.md | 2026-05-05 | Adds Lever 4 (track filtering), expands illustration catalogues to 12–15 per pack, adds overlay × base compatibility section, adds Firefly prompt budget analysis |

### Implementation status (as of PRD v1.0)

| Area | Status |
|------|:------:|
| Framework engine | ✅ Implemented |
| Good Morning category | ✅ Implemented |
| Birthday category v2 | ✅ Implemented |
| Suvichar category v2 | ✅ Implemented |
| Overlay system architecture | ✅ Implemented |
| Devotional overlay | ✅ Implemented (incl. F6 Temple Arch unlock) |
| Summer overlay | ✅ Implemented |
| Rain / Monsoon overlay | ✅ Implemented |
| Cricket / IPL overlay | ✅ Implemented (incl. F5 restrict) |
| 5 platform builders | ✅ Implemented (Firefly w/, Firefly w/o, MJ, Leonardo, Gemini) |
| Audit panel | ✅ Implemented (incl. overlay + greeting-text rows) |
| TSV / HTML eval export | ✅ Implemented (Prompt Eval Framework v4 alignment) |
| **V2 — bottom safe zone** | ✅ Implemented (all 10 platform builders + layout diagrams) |
| **V2 — adaptive B1 text colour** | ✅ Implemented (Leonardo / Firefly with-text / Gemini) |
| **V2 — Rath Yatra category** | ✅ Implemented |
| **V2 — Vat Savitri category** | ✅ Implemented |
| **V2 — Father's Day category** | ✅ Implemented (only v2 pack keeping all 5 tracks) |
| **V2 — Devotional Shivji** | ✅ Implemented (editable Custom Text) |
| **V2 — Devotional Ganeshji** | ✅ Implemented (editable Custom Text) |
| **V2 — Devotional Jesus** | ✅ Implemented (editable Custom Text) |
| **V2 — Devotional Islamic** | ✅ Implemented (editable Custom Text) |

---

## 6 May 2026 — Edits Pending Merge into Main PRD

This section captures fixes and design tweaks landed on the `Edits-6-May` branch (commit `b1da4e0`). It will be folded into the relevant Part 7 sections in the next PRD revision.

### 54. Step-3 Layout Prompt Fixes (L3 / L4 / L5)

**Problem.** Step 3 (Text & Visual arrangement) was emitting wrong or duplicate prompts for three layouts in the compact Firefly form (with-text and no-text builders for A1/A2). Other platforms (Midjourney, Leonardo, Gemini) were unaffected — they emit `d.textZonePh` / `d.illusPositionPh` verbatim and were already correct.

**Bug 1 — L3 ≡ L4 (identical prompts).**
- L3 (Text Left, Visual Right) and L4 (Text Right, Visual Left) produced byte-identical Firefly compact lines.
- Root cause: the Firefly compact builders re-derived a `zone` token from `d.textZonePh` via a string-match cascade. Both L3 and L4 layout phrases naturally name *both* sides ("left column reserved … right column anchors" and the mirror), so the cascade short-circuited on `'left'` for both layouts and emitted `Text zone: left 25%. Illustration: opposite area.`

**Bug 2 — L5 broken.**
- L5 (Text Bottom / Visual Up) emitted `Text zone: centre 25%. Illustration: opposite area.` — wrong on both sides.
- Root cause: the v2 safe-zone reword removed the words `upper` / `lower` from L5's `textZonePh` ("between 60 and 80 percent from the top"), so the cascade fell through to `'centre'`.

**Fix — explicit per-layout dispatch.**
- New helper `compactLayoutPhFirefly(layoutId)` returns explicit `{ textZone, illusZone }` strings keyed by layout ID.
- Replaces the brittle string-match cascade in both `buildFireflyWithTextPrompt` and `buildFireflyNoTextPrompt`.
- Same dispatch protects future `gatherPromptData` rewrites from silently breaking the compact form.

```js
function compactLayoutPhFirefly(layoutId) {
  const map = {
    'L1': { textZone: 'upper 25%',            illusZone: 'centre band below text, above safe zone' },
    'L2': { textZone: 'centred mid-canvas',   illusZone: 'centred behind text, above safe zone' },
    'L3': { textZone: 'left column',          illusZone: 'right side anchor, above safe zone' },
    'L4': { textZone: 'right column',         illusZone: 'left side anchor, above safe zone' },
    'L5': { textZone: 'lower band 60-80%',    illusZone: 'upper 60% above text band' },
    'L6': { textZone: 'central 60% (framed)', illusZone: 'small accent at any of the four corners, above the reduced 10% safe zone' },
  };
  return map[layoutId] || { textZone: 'centre', illusZone: 'opposite area' };
}
```

**Verification.**
- L3 compact contains `right side anchor`; L4 compact contains `left side anchor`. The two prompts are no longer identical.
- L5 compact contains `lower band 60-80%` and `upper 60% above text band`. No `centre 25%` or `opposite area` anywhere.
- All other platforms (MJ, Leonardo, Gemini) unaffected — they already used the correct verbatim phrases.

### 55. Layout L6 — Reduced 10% Safe Zone (Corner-Accent Layout Only)

**Decision.** L6 (Text Centre, framed) is the only layout where the small accent illustration can sit at top *or* bottom corners. The standard 20% bottom safe zone (Section 43) removed bottom-corner availability. **Decision: L6 specifically uses a reduced 10% safe zone so a tiny corner accent can sit at any of the four corners. All other layouts keep the standard 20% band.**

**Rationale.** Considered alternatives:
- (a) Keep 20% band, force L6 accent to upper-corners only — loses the "any corner" framework intent.
- (b) Reduce band globally to 10% — weakens personalization headroom for the other 5 layouts.
- (c) **Reduce to 10% only for L6** ← chosen. Surgical, preserves intent on both sides.

**Implementation.**
- New constants `SAFE_ZONE_DESC_L6` and `SAFE_ZONE_FIREFLY_L6` capture the reduced-band wording.
- New helpers `getSafeZoneDesc(layoutId)` and `getSafeZoneFireflyAB(layoutId)` return the L6 variant when `layoutId === 'L6'`, otherwise the standard 20% strings.
- 5 builder sites switched from direct `SAFE_ZONE_*` references to helper calls: MJ, Leonardo, Firefly with-text, Firefly no-text, Gemini (all A1/A2).
- B1 builders untouched — B1 doesn't use L6 corner accents and keeps the 20% band globally.
- `gatherPromptData` L6 branch now mentions the reduced 10% band and lists all four corners as valid placements:
  - `textZonePh`: "text occupies the central 60 percent of the canvas as the dominant element, kept above the bottom 10 percent reduced personalization safe zone"
  - `illusPositionPh`: "placed as a small decorative accent at any of the four corners of the canvas (upper-left, upper-right, lower-left, or lower-right), tucked tight against the corner, kept clear of the central text and clear of the bottom 10 percent reduced personalization safe zone"

**Layout diagram update.** The `centre-accent` branch in `layoutDiagram()` now draws:
- A thinner 10% dashed safe-zone band (vs 20% on other layouts), labelled `safe 10%`.
- Two V chips: one at top-right (existing) plus a second smaller V chip at bottom-right above the reduced band — communicating that bottom-corner placement is now valid for L6.

**Verification.**
- L1–L5 across MJ / Leonardo / Firefly / Gemini retain the 20% safe-zone language (`bottom 20 percent personalization safe zone`).
- L6 across all 5 platforms emits the reduced 10% language (`bottom 10 percent reduced personalization`).
- Worst-case Firefly with-text across 10 categories × { L3, L4, L5, L6 } = 860 chars (within the 950 cap). L6's reduced band slightly shortens the prompt vs L1–L5.

### 56. 6-May Implementation Status

| Change | Status |
|---|---|
| L3 / L4 / L5 compact-Firefly fix via `compactLayoutPhFirefly()` | ✅ Implemented (b1da4e0) |
| L6 reduced 10% safe zone (constants, helpers, builders, diagram) | ✅ Implemented (b1da4e0) |
| 24/24 runtime smoke tests pass | ✅ Verified |
| Synced to `docs/` GitHub Pages files | ✅ Done |
| Folded into main PRD body | ⏳ Pending (this section is the staging area) |

### 57. F6 Temple Arch Frame — Removed (Superseded by MT-8 Motif)

**Decision.** F6 Temple Arch — previously unlocked as an A1 frame option only when the Devotional overlay was active — has been removed. A temple-arch architectural element is conceptually the same primitive as a canopy/torana, and the existing **MT-8 Temple Arch motif** (Track A motif set, "best with F5 Arch / Canopy frame") already covers the use case as a layered decorative element.

**Why.**
- The "frame" abstraction implied a full canvas enclosure; what users actually want is a top-arch decorative element. MT-8 already does this and layers cleanly onto any base frame (F1–F5) without coupling to overlay state.
- Removes overlay-conditional frame branching, which simplifies the Step-2 picker logic for A1.
- Avoids a naming collision with MT-8 (both were named "Temple Arch").

**Implementation.**
- `OV-DEV.frameUnlock` set to `[]` (was the F6 entry).
- `gatherPromptData` `framePh` builder no longer has an F6 branch.
- Comments referencing the F6 unlock cleaned up in 4 sites.
- `frame-arch` SVG diagram retained — it's still used by F5 Arch / Canopy.
- Audit panel `frameStructureDesc` already only lists F1–F5 (no change needed).

**No PRD section deletion yet.** The F6 spec block in Section 6 (and the F6 row in Appendix A) will be removed when this 6-May section is folded into the main PRD body. Until then, treat F6 as deprecated.

### 58. A1 Scene Accents — Reuse A2 Sub-Element Pattern

**Decision.** A1 (Text + Frame) now exposes the same "Scene Accents" picker as A2: when a user selects a hero illustration, an optional set of 2–4 curated accent props appears, and the user can pick up to 2. Selected accents are described in prompts as small supporting elements rendered in the same illustration style as the main subject.

**Rationale.** The data, UI affordance, and prompt phrasing already existed for A2. The user observed that A1 is essentially A2 plus a frame — so reusing the same accent pattern (with the frame layered on top) is the natural extension.

**What's shared with A2.**
- Data tables: `A2_SUB_ELEMENTS`, `SV_A2_SUB_ELEMENTS`, `BD_A2_SUB_ELEMENTS` (and `getA2SubElements()` lookup).
- State key: `STATE.a2SubElements` (kept the existing name to minimise churn — could be renamed to `subElements` in a future cleanup).
- Reset behaviour: cleared on category / overlay / archetype / feeling / illusItem change.
- Toggle handler: `toggleA2SubElement(itemId)` (max 2).
- All 5 platform builders' accent injection (MJ, Leonardo, Firefly with-text, Firefly no-text, Gemini) — they only check `if (d.a2AccentPh)` with no archetype gate, so they pick up A1 selections automatically.

**What differs between A1 and A2.**
| Concern | A2 (no frame) | A1 (with frame) |
|---|---|---|
| Density semantics | Auto-derived from accent count: 0 → Light (1–2 elements), 1 → Medium (3–4), 2 → Dense (5–6). Emitted as `densityPh`. | Density is governed by **Frame Decoration** (Plain / Simple / Detailed). Accents are pure scene props and do **not** drive a `densityPh`. |
| UI sub-section tag | `${count}/2 · ${densityLabel}` | `${count}/2` only |
| UI helper text | "Density auto-adjusts: …" | "Small supporting scene elements rendered in the same illustration style as the main subject. Sit alongside the main illustration, kept clear of the border frame." |
| Prompt density clause | `densityPh` injected | No `densityPh` injected |

**Implementation.**
- UI gate at the visual step expanded: `if (STATE.archetype === 'A1' || STATE.archetype === 'A2')`.
- Helper text and sub-section tag branch on `isA2` flag.
- `gatherPromptData` split: density logic stays A2-only; accent phrase build runs for both A1 and A2.
- Audit panel A1 branch now lists "Accent Sub-Elements" alongside Frame Decoration.

**Verification.**
- 16/16 runtime assertions pass (F6 removal + A1 sub-elements + A2 regression).
- All 5 platforms inject the accent phrase for A1.
- A1 with no accents selected emits no accent clause (regression check).
- A2 still emits `densityPh`; A1 does not.
- Worst-case Firefly with-text under A1 + 2 accents across 10 categories × 6 layouts = **946 chars** (within the 950 cap; Jesus / L2).

### 59. 6-May (Part 2) Implementation Status

| Change | Status |
|---|---|
| F6 Temple Arch frame removed from `OV-DEV.frameUnlock` | ✅ Implemented |
| F6 frameShape branch removed from `gatherPromptData` | ✅ Implemented |
| Stale F6 unlock comments cleaned up (4 sites) | ✅ Implemented |
| A1 sub-elements UI gated to `A1 || A2` at visual step | ✅ Implemented |
| `a2AccentPh` built for both A1 and A2 in `gatherPromptData` | ✅ Implemented |
| A1 audit panel shows Accent Sub-Elements | ✅ Implemented |
| Synced to `docs/` GitHub Pages files | ✅ Done |
| 16/16 runtime smoke tests pass | ✅ Verified |
| F6 spec removed from main PRD body | ⏳ Pending (fold during next merge) |

### 60. Illustration Pool Curation — GM, Suvichar, Birthday, Rath Yatra

**Architectural decision.** Each base category and each V2 pack now owns a **self-contained illustration pool** — no GM carryovers, no per-overlay item subtraction (`restrictByCategory` left in place but no longer used by curated categories). The accent (`A2_SUB_ELEMENTS` / `B1_SUB_ELEMENTS`) tables stay namespaced per category (GM, SV, BD, RY) and are merged via `getA2SubElements` / `getB1SubElements` lookups. **Why:** simplifies the mental model — "category X has these N illustrations + (overlay applicable ? its M items : 0)" — and makes review tractable. **How to apply:** when adding new illustrations, add to the relevant pool only; do not carry over items from other pools.

**Decisions taken in this round (applied to 4 categories; 6 V2 packs deferred):**

#### Good Morning · 41 → 37 items
- **Drops (5):** GM-I4-03 Hands in Namaste, GM-I4-04 Agarbatti Smoke, GM-I4-05 Tulsi in Brass Pot, GM-I4-06 Temple Bell, GM-I4-07 Shankh — all moved to Devotional overlay (one pool per overlay, no duplication).
- **Add (1):** GM-I5-07 Newspaper & Chai (folded paper beside steaming chai cup; quintessential Indian doorstep ritual).
- **Sub-category rename:** GM-I4 from "Spiritual & Devotional" → **"Cultural"**. Now contains only Diya, Rangoli, Peacock Feather (broadly cultural, not strictly devotional).

#### Suvichar · 30 → 25 items (self-contained)
- **Drops (9):** Abstract sub-category dropped entirely (SV-I01 Ink Brush + SV-I04 Splatter); plus weak/clichéd items SV-I02 Geometric Shards, SV-I03 Gradient Orb, SV-I07 Winding Path, SV-I10 Stormy Sky, SV-I20 Trophy/Medal, SV-I22 Magnifying Glass, SV-I30 Running.
- **Adds (4):** SV-I31 Rain-streaked Window, SV-I32 Footprints in Sand, SV-I33 Empty Park Bench, SV-I34 Stack of Old Books.
- **Carryovers dropped:** `SUVICHAR_GM_CARRYOVER_IDS = []`. Items that previously came from GM (Sunrise Hills, Lotus, Diya, etc.) no longer appear in the Suvichar picker.
- **`SUVICHAR_ITEM_FEELINGS` rebuilt** to cover only the new 25-item pool.

#### Birthday · 30 → 26 items (self-contained)
- **Drops (4):** BD-I05 Single Balloon (variant of Balloon Bunch), BD-I07 Gift Stack (variant of Gift Box), BD-I18 Streamers (overlap with Bunting + Confetti Popper), BD-I22 Star Scatter (generic).
- **Carryovers dropped:** `BIRTHDAY_GM_CARRYOVER_IDS = []`.

#### Rath Yatra · 19 → 15 items (self-contained)
- **Drops (4):** RY-I03 Three Chariots (variant of Rath Full), RY-I09 Neela Chakra (too specific silhouette), RY-I11 Grand Road (overlaps with Procession Crowd), RY-I15 Rath Yatra Flag (weak as standalone main).
- **Carryovers dropped:** `carryoverIds: []`.
- **New tables:** `RY_A2_SUB_ELEMENTS` and `RY_B1_SUB_ELEMENTS` added; `getA2SubElements` / `getB1SubElements` lookup chain extended to include them.

#### Scene Accent pool · 30 → 35 items
- **Drops (3):** ACC-13 Kumkum Tilak Mark, ACC-16 Match Sticks, ACC-21 Curtain with Light.
- **Adds (5):** ACC-31 Orange Halves (for OJ), ACC-32 Half Coconut Shell (for Tender Coconut Water), ACC-33 Sparks / Embers (energy/celebration), ACC-34 Star Cluster (night/wonder), ACC-35 Crumpled Paper Edge (writer's process).
- **Existing namespaced accents preserved** (SV-ACC-01..06, BD-ACC-01..06) — used contextually by Suvichar and Birthday mappings.
- **Mapping shape:** mostly 3 accents per main; 2 accents for items where 3 felt forced (GM-I1-08 Tender Coconut, GM-I4-09 Peacock Feather, SV-I19 Lantern, SV-I24 Flame, BD-I09 Birthday Candles, BD-I24 Number Candle, all 15 RY items).

**Deferred (parked) categories** — unchanged in this round; will be re-curated in a later session:
- Father's Day, Vat Savitri (V2 packs)
- 4 Devotional V2 packs: Shivji, Ganeshji, Jesus, Islamic
- 4 Overlays: Devotional (OV-DEV), Summer (OV-SUM), Rain (OV-RAIN), Cricket (OV-CRI) — these still hold their current illustration pools

### 61. 6-May (Part 3) Implementation Status

| Change | Status |
|---|---|
| ACCENT_ITEMS: drop 3, add 5 (pool 30 → 35) | ✅ Implemented |
| GM curated to 37 items (rename GM-I4 → Cultural; +Newspaper & Chai) | ✅ Implemented |
| GM `B1_SUB_ELEMENTS` / `A2_SUB_ELEMENTS` rebuilt | ✅ Implemented |
| Suvichar curated to 25 items (drop Abstract, +4 new) | ✅ Implemented |
| `SUVICHAR_GM_CARRYOVER_IDS` emptied; `SUVICHAR_ITEM_FEELINGS` rebuilt | ✅ Implemented |
| `SV_B1_PHOTO_DESC` / `SV_B1_SUB_ELEMENTS` / `SV_A2_SUB_ELEMENTS` rebuilt | ✅ Implemented |
| Birthday curated to 26 items; `BIRTHDAY_GM_CARRYOVER_IDS` emptied | ✅ Implemented |
| `BD_B1_SUB_ELEMENTS` / `BD_A2_SUB_ELEMENTS` rebuilt | ✅ Implemented |
| Rath Yatra curated to 15 items; carryovers emptied | ✅ Implemented |
| `RY_A2_SUB_ELEMENTS` / `RY_B1_SUB_ELEMENTS` added; lookup chain extended | ✅ Implemented |
| Synced to `docs/` GitHub Pages files | ✅ Done |
| 47/47 curation assertions pass; 10/10 e2e prompt builds pass; worst-case Firefly = 950 chars | ✅ Verified |
| Curate 6 deferred categories (Father's Day, Vat Savitri, Shivji, Ganeshji, Jesus, Islamic) | ⏳ Pending |
| Curate 4 overlay pools (Devotional, Summer, Rain, Cricket) | ⏳ Pending |

---

*End of PRD v1.1.*

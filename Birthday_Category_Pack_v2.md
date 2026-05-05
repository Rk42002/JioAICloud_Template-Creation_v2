# Birthday — Category Pack v2
> **Incremental spec on top of Template_Creation_Framework_v20.md**
> This document only covers what CHANGES or is NEW for the Birthday category.
> Everything not mentioned here (archetypes, layouts, tracks, colour palettes, font pairings, background finishes, render styles, prompt builder architecture) is inherited unchanged from the framework.

**Changes from v1:**
- New BD-ACC-* sub-illustration accent library added — replaces the generic GM-themed props (kumkum, incense smoke, marigold petals) that were being used as Birthday sub-elements with purpose-built birthday celebration accents
- Sub-element mapping updated for all 30 Birthday illustration items (B1 and A2 both)
- Birthday-specific negative terms formalised (funeral, mourning, sad, wilted, dark mood, horror) — applied to all archetype prompt builders

---

## 1. What This Category Is

Birthday is a celebration-first greeting category. Visual energy (balloons, cake, confetti, sparkle) shares the canvas with the greeting text — "Happy Birthday" replaces "Good Morning" as the hero text.

**Only two things change from Good Morning:**

1. **Border motifs / A2 accent motifs** — replaced with Birthday-specific motif sets per track
2. **Illustration catalogue** — replaced with Birthday-specific items (30 new + 4 carry-overs)

Everything else — wizard flow, archetypes, tracks, layouts, background finishes, render styles, prompt builder architecture — carries over unchanged.

---

## 2. Wizard Flow — No Change

**Birthday flow is identical to Good Morning:**
`Archetype → Track → Layout → Colour → Font → Illustration → Intensity`

No Feeling step. Birthday has one emotional lane: celebration. The track system (A–E) provides all the tonal variation needed — from maximal party (Track A) to soft warmth (Track E).

All 5 tracks remain available for every Birthday template.

---

## 3. Border Motif Sets — Birthday Replacements

Each track's frame motif vocabulary is **replaced** (not extended) with Birthday-specific motifs. Used in:
- **A1** — Frame decoration motifs (Plain / Simple / Detailed levels)
- **A2** — Accent density fill items (auto-calculated density)

### Track A — Shiny Maximal
| ID | Motif | Description |
|----|-------|-------------|
| BD-MT-A1 | Gold Foil Balloons | Shiny metallic balloon cluster, gold/rose-gold |
| BD-MT-A2 | Confetti Burst | Dense confetti explosion, multi-colour with gold sparkle |
| BD-MT-A3 | Marigold Garland Border | Thick marigold toran along frame edge, festive Indian |
| BD-MT-A4 | Ornate Gift Bow | Large decorative ribbon bow, satin with gold thread |
| BD-MT-A5 | Sparkle Cluster | Scattered star-sparkle accents, glitter energy |
| BD-MT-A6 | Mithai & Sweets | Decorative Indian sweets arrangement, ladoo/barfi with gold leaf |

### Track B — Modern Desi
| ID | Motif | Description |
|----|-------|-------------|
| BD-MT-B1 | Marigold String Lights | Thin marigold strand with small fairy lights woven through |
| BD-MT-B2 | Rangoli Corner Motifs | Quarter-rangoli patterns in frame corners, geometric floral |
| BD-MT-B3 | Modern Balloon Trio | 3 balloons (1 foil + 2 latex), clean composition |
| BD-MT-B4 | Diya Accent Row | Small line of lit diyas along frame base, warm glow |
| BD-MT-B5 | Bunting Flags (Desi Print) | Triangular bunting with block-print / ikat patterns |
| BD-MT-B6 | Cake Slice (Minimal) | Single clean cake slice, modern plating, side view |

### Track C — Minimalist Classy
| ID | Motif | Description |
|----|-------|-------------|
| BD-MT-C0 | None | No decorative motifs, completely clean |
| BD-MT-C1 | Single Balloon + String | One balloon with trailing string, elegant negative space |
| BD-MT-C2 | Thin Confetti Scatter | Sparse confetti dots, muted metallic tones |
| BD-MT-C3 | Minimal Candle Line | Row of thin birthday candles, unlit or with tiny flame |
| BD-MT-C4 | Geometric Gift Box | Clean-line gift box silhouette, no texture |
| BD-MT-C5 | Laurel / Leaf Wreath | Simple botanical wreath arc, framing text zone |
| BD-MT-C6 | Dot Sparkle Trail | Minimal dot trail suggesting sparkle, gold or silver |

### Track D — Artsy Playful
| ID | Motif | Description |
|----|-------|-------------|
| BD-MT-D1 | Hand-drawn Balloons | Sketchy, wobbly balloon outlines, crayon or marker style |
| BD-MT-D2 | Doodle Confetti | Loose hand-drawn confetti shapes — stars, circles, squiggles |
| BD-MT-D3 | Cartoon Cake Slice | Fun illustrated cake with exaggerated frosting, sprinkles |
| BD-MT-D4 | Playful Streamers | Curly ribbon streamers in bright colour, hand-drawn feel |
| BD-MT-D5 | Party Hat (Illustrated) | Classic cone party hat with pom-pom, playful illustration |
| BD-MT-D6 | Sticker-style Stars | Puffy star stickers, slightly 3D, scattered |

### Track E — Soft & Warm
| ID | Motif | Description |
|----|-------|-------------|
| BD-MT-E0 | None | No decorative motifs, completely clean |
| BD-MT-E1 | Watercolour Balloons | Soft-edge balloons in pastel watercolour wash |
| BD-MT-E2 | Gentle Confetti | Soft-falling confetti in muted pastels, slow-drift feel |
| BD-MT-E3 | Floral Wreath (Soft) | Delicate flower and leaf wreath, watercolour botanical |
| BD-MT-E4 | Pastel Bunting | Soft fabric bunting in cream / blush / sage tones |
| BD-MT-E5 | Candle Glow (Warm) | Single warm candle with soft light bloom, cosy |
| BD-MT-E6 | Ribbon Curl (Soft) | Gentle satin ribbon curl, pastel, no hard edges |

---

## 4. Illustration Catalogue — Birthday Pack

### 4.1 Carry-over from Good Morning

Existing items that work for Birthday context. Shown as a separate group in the catalogue picker.

| ID | Name | Archetypes | Notes |
|----|------|------------|-------|
| GM-I3-01 | Marigold / Flowers | A1, A2 | Floral birthday, Indian festive crossover |
| GM-I4-01 | Candle / Diya | All | Birthday candle + devotional blessing |
| GM-I3-02 | Lotus Flower | A1, A2, B1 | Blessing / purity — works for elder birthday wishes |
| GM-I6-01 | Birds in Flight | B1, A2 | Freedom, new chapter metaphor |

---

### 4.2 New Illustrations — Birthday Specific (30 items)

**Party Essentials**

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

---

**Indian Festive**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| BD-I11 | Marigold Toran (Hanging) | Draped marigold garland toran, doorway blessing style | A1, A2 |
| BD-I12 | Mithai Box (Open) | Open box of assorted Indian sweets — ladoo, barfi, peda | A1, A2 |
| BD-I13 | Diya Cluster | 3–5 lit clay diyas arranged together, warm flame glow | A1, A2 |
| BD-I14 | Rangoli (Floor) | Circular rangoli pattern, bird's-eye view, colourful powder | A2, B1 |
| BD-I15 | Puja Thali | Decorated thali with kumkum, rice, flowers, diya — blessing | A1, A2 |

---

**Decorative & Atmosphere**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| BD-I16 | Bunting / Banner | Triangular flag bunting string, "Happy Birthday" or plain | A1, A2 |
| BD-I17 | Fairy Lights (String) | Warm fairy light string, soft bokeh glow, draped or straight | A1, A2, B1 |
| BD-I18 | Streamers (Hanging) | Colourful paper streamers hanging from top of frame | A1, A2 |
| BD-I19 | Fireworks (Sky) | Firework burst against dark sky, celebration energy | A2, B1 |
| BD-I20 | Sparkler (Handheld) | Lit sparkler with bright white sparks radiating | A1, A2, B1 |
| BD-I21 | Flower Bouquet | Mixed flower bouquet, wrapped or in vase, gift style | A1, A2 |
| BD-I22 | Star Scatter | Scattered decorative stars, mixed sizes, metallic | A1, A2 |

---

**Objects & Symbols**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| BD-I23 | Crown / Tiara | Birthday crown or tiara, gold with gem accents | A1, A2 |
| BD-I24 | Number Candle | Large decorative number candle (generic "1" shape as reference) | A1, A2 |
| BD-I25 | Ribbon Bow (Standalone) | Satin ribbon bow, gift-wrap style, standalone accent | A1, A2 |
| BD-I26 | Wish Card / Envelope | Greeting card or envelope, partially open, warm | A1, A2 |

---

**Human / Figurative** *(B1 archetype only — photorealistic)*

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| BD-I27 | Hands Holding Cake | Two hands presenting a birthday cake, warm lighting | B1 |
| BD-I28 | Blowing Candles (Silhouette) | Person leaning to blow out candles, side profile silhouette | B1 |
| BD-I29 | Group Celebration | 2–3 people cheering / clapping around a table, candid joy | B1 |
| BD-I30 | Child with Balloon | Small child holding a single balloon, back view or silhouette | B1 |

---

### 4.3 Catalogue Summary

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

---

## 5. Sub-Illustration Accent Items — BD-ACC Library

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

### Sub-element mapping per main illustration

**A2 (illustrated sub-accents):**

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

**B1 (photorealistic supporting props):**

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

---

## 6. Prompt Framework — Birthday Context

### 6.1 Text Content

| Variable | Good Morning Value | Birthday Value |
|----------|-------------------|----------------|
| Hero text | "Good Morning" | "Happy Birthday" (fixed — no user input step) |
| Text character range | Short greeting (1–2 lines) | Short greeting (1–2 lines) — same |
| Optional sub-text | Blessing / quote line | Birthday wish / name personalisation |
| Text language options | Hindi, English, Hinglish | Hindi, English, Hinglish — no change |

### 6.2 Scene Atmosphere & Mood

| Prompt Element | Good Morning | Birthday |
|----------------|-------------|----------|
| Scene atmosphere | `early morning Indian setting` | `Indian birthday celebration setting` |
| Scene authenticity | `real Indian morning setting` | `real Indian birthday celebration` |
| Gem setting context | `early morning in India` | `an Indian birthday celebration` |
| Light/time context | `natural and time-appropriate for early morning` | `natural and warm for a birthday celebration` |
| Style mood word | `morning` | `birthday` |
| Category label | Good Morning | Happy Birthday |

### 6.3 Negative Terms

Birthday-specific additions on top of existing per-archetype negatives:

| Archetype | Birthday Additions |
|-----------|-------------------|
| A1 | `funeral, mourning, sad, wilted, dark mood, horror` |
| A2 | `funeral, mourning, sad, wilted, dark mood, horror` |
| B1 | `funeral, mourning, sad, wilted, dark mood, horror, illustrated elements, graphic design, decorative overlay` |

### 6.4 Platform-Specific Notes

All platform adapters (Midjourney, Firefly, Leonardo, Gemini) inherit unchanged. Only the context variable values swap as defined in 6.2 above.

---

## 7. Layout Bias (Guidance, Not Hard Filter)

| Layout | Birthday Suitability | Reason |
|--------|:-------------------:|--------|
| L5 — Text Bottom | ★ Best | Illustration/cake fills top, "Happy Birthday" anchors at base — classic card |
| L2 — Overlay / Text Centre | ★ Best | Atmospheric party background with centred greeting overlay |
| L1 — Text Top | ✓ Works | "Happy Birthday" at top, illustration below — clean |
| L6 — Text Centre (frame) | ✓ Works | Strong for A1 — frame with centred greeting, corner illustrations |
| L3 / L4 — Text Left / Right | ✓ Works | Birthday illustrations are compact enough for side placement at any size |

**Note:** Unlike Suvichar (which cautioned L3/L4), Birthday works well with side layouts because greeting text is short and illustration subjects (cake, balloons) have clear focal points.

---

## 8. What Does NOT Change

Everything below is fully inherited from `Template_Creation_Framework_v20.md` — no modifications:

- The 3 archetype families (A1, A2, B1) and their wizard flows
- The 5 tracks (A–E) and their colour palettes, font pools
- All background finish options (existing per-track finishes carry over as-is; no Birthday-specific finishes added)
- Illustration render style step — fully inherited per track, no locking
- Illustration size — all three sizes available (Small / Medium / Large), no cap
- All 6 layouts (L1–L6) and frame/overlay compatibility rules
- Prompt builder logic / function architecture for all platforms
- Shared ACCENT_ITEMS library (ACC-01..ACC-30) — used where contextually appropriate (ACC-08 Fallen Petals for Indian Festive items)
- Density auto-calculation for A2
- Intensity controls
- Character limits and prompt construction helpers (stripHex, trunc)

# Suvichar / Daily Quotes — Category Pack v2
> **Incremental spec on top of Template_Creation_Framework_v20.md**
> This document only covers what CHANGES or is NEW for the Suvichar/Quotes category.
> Everything not mentioned here (archetypes, layouts, tracks, colour palettes, font pairings, background finishes, render styles, prompt builder architecture) is inherited unchanged from the framework.

**Changes from v1:**
- SV-specific background finishes (SV-BG01..04) removed — Suvichar now uses the same per-track finishes as Good Morning and Birthday
- Locked render styles for Abstract illustrations reverted — all illustrations use the standard per-track render style step
- Custom text input added as the final wizard step — user types their actual quote, which feeds directly into the prompt
- Illustration catalogue reorganised — GM carry-over items now appear inside their semantic category (Nature & Landscape, Objects & Still Life), no separate "Carry-overs" bucket
- New SV-ACC-* sub-illustration accent items replace GM-themed props (morning dew, incense, kumkum) with contemplative, quote-appropriate accents

---

## 1. What This Category Is

Suvichar (motivational / inspirational / daily quotes) is a text-first category. The quote is the hero — illustration is atmospheric support only. Two things change from Good Morning:

1. A new **Feeling** selector runs before track selection
2. A **Custom Text** input is the final step — the user types their actual quote, which is rendered in the poster text zone

---

## 2. Wizard Flow

### A1 (Text + Frame)
`Archetype → Feeling → Style → Layout → Track → Colour & Finish → Illustration → Intensity → **Custom Text**`

### A2 (Text + Illustrations)
`Archetype → Feeling → Layout → Track → Colour & Finish → Illustration → Intensity → **Custom Text**`

### B1 (Full Photo Background)
`Archetype → Feeling → Text Placement → Track → Scene Elements → Mood → Intensity → **Custom Text**`

The **Custom Text** step is the last step for all archetypes in Suvichar. It is required — the Next/Generate button is disabled until the user has entered at least one character.

**Good Morning flow (for comparison):**
Same flow as above, minus the Feeling step and the Custom Text step.

---

## 3. Feeling System

Five feelings covering the full emotional range of quote content. Each has a distinct visual personality that drives track filtering and illustration selection downstream.

| Code | Name | Visual Personality | What it means | Example quotes |
|------|------|--------------------|---------------|----------------|
| **SV-F1** | **Rise & Shine** | Bright, energetic, forward-moving. Sunrise energy. | Aspirational uplift — "You can do this." Optimistic, outward, action-oriented. | "Every day is a new beginning", gym motivation, achievement |
| **SV-F2** | **Still Waters** | Slow, contemplative, inward. Moon / water / lone tree energy. | Deep reflection — "Sit with this." Philosophical, unhurried, inner-focused. | Rumi, Kabir, self-awareness, philosophy, life lessons |
| **SV-F3** | **Bittersweet** | Honest, aching, tender. Not dark — bittersweet longing. | Emotional honesty — "This too." Acknowledges pain without wallowing. | Loss quotes, nostalgia, longing, shayari, letting go |
| **SV-F4** | **Everyday Calm** | Functional warmth. Cosy desk, morning ritual, gentle habit. | Grounded daily reminder — "Just today." Practical, close-to-home, no drama. | "Drink water", "Rest is productive", micro-habits, stoic reminders |
| **SV-F5** | **Fire & Drive** | Bold, high contrast, kinetic. No softness. | Pure ambition — "Go." Fierce, competitive, zero sentimentality. | Startup grind, sports motivation, hustle, bold declarations |

---

## 4. Feeling → Track Filter

Hard filter. Blocked tracks (❌) are hidden from the UI when that feeling is selected.

| Feeling | A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|---------|:-:|:-:|:-:|:-:|:-:|
| SV-F1 Rise & Shine | ✅ | ✅ | ✅ | ✅ | ✅ |
| SV-F2 Still Waters | ❌ | ✅ | ✅ | ❌ | ✅ |
| SV-F3 Bittersweet | ❌ | ✅ | ✅ | ❌ | ✅ |
| SV-F4 Everyday Calm | ❌ | ✅ | ✅ | ✅ | ✅ |
| SV-F5 Fire & Drive | ✅ | ❌ | ✅ | ✅ | ❌ |

---

## 5. Custom Text Input Step

The final step in all Suvichar flows. The user types the actual quote or suvichar they want displayed on the poster.

**Behaviour:**
- Free-text textarea, no character limit enforced (soft guidance only)
- Required — Next/Generate is disabled until non-empty
- The entered text replaces "Suvichar / Quote" everywhere in the prompt output
- In Firefly with-text mode: `Clean "[user quote]" text in decorative font in the text zone`
- In all other prompts: atmosphere and scene language remain category-specific; the text content itself is what the user typed

**UI label:** "Your Quote" / "अपना सुविचार लिखें"

---

## 6. Background Finish

Suvichar uses the **same per-track background finishes as Good Morning and Birthday**. There are no Suvichar-specific finish options. The v1 SV-BG01..04 finishes (Watercolour Wash, Paper Texture, Soft Gradient Orb, Ink Wash) have been removed.

---

## 7. Illustration Render Style

Standard per-track render styles apply — same as Good Morning. There are no locked render styles in Suvichar. The v1 lock rule for Abstract Illustrations (SV-I01, SV-I02, SV-I03) has been reverted.

---

## 8. Illustration Catalogue — Suvichar Pack

Illustrations are browsed by semantic category. GM carry-over items appear inside the relevant category — there is no separate "Carry-overs" bucket.

### Universality Key

> **U = Universal** — works for all 5 feelings
> **R = Restricted** — shown only for the listed feelings, hidden for others

---

### 8.1 Abstract

| ID | Name | Description | U/R | Feeling Restriction | Archetypes |
|----|------|-------------|:---:|---------------------|------------|
| SV-I01 | Ink Brush Stroke | Single bold sumi-e brushstroke, black or deep colour on neutral | R | F2, F3, F5 | A1, A2 |
| SV-I02 | Geometric Shards | Fragmented low-poly angular shapes, sharp and bold | R | F5 | A1, A2 |
| SV-I03 | Gradient Orb | Blurred radial light bloom as a placed accent element | **U** | — | A1, A2 |
| SV-I04 | Splatter / Paint Burst | Dynamic ink or paint splatter, energy and expression | R | F1, F5 | A1, A2 |

---

### 8.2 Nature & Landscape

Includes Good Morning carry-overs that are nature / landscape in character.

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

---

### 8.3 Objects & Still Life

Includes Good Morning carry-overs that are object / still life in character.

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

---

### 8.4 Fire & Energy

| ID | Name | Description | U/R | Feeling Restriction | Archetypes |
|----|------|-------------|:---:|---------------------|------------|
| SV-I24 | Flame / Fire | Single clean flame — ambition, passion | R | F1, F5 | A1, A2 |
| SV-I25 | Lightning Bolt | Bold graphic lightning, energy and power | R | F5 | A1, A2 |
| SV-I26 | Rising Sun (Graphic) | Stylised graphic rising sun with rays, bold | R | F1, F5 | A1, A2 |

---

### 8.5 Silhouettes (B1 only)

| ID | Name | Description | U/R | Feeling Restriction | Archetypes |
|----|------|-------------|:---:|---------------------|------------|
| SV-I27 | Arms Raised — Victory | Figure arms raised against sky | R | F1, F5 | B1 |
| SV-I28 | Seated / Meditating | Person in stillness, introspective | R | F2, F3, F4 | B1 |
| SV-I29 | Walking Alone | Figure walking on road or beach | R | F2, F3 | B1 |
| SV-I30 | Running / Sprinting | Dynamic running figure, motion and drive | R | F1, F5 | B1 |

---

### 8.6 Catalogue Summary

| Category | Total | Universal (U) | Restricted (R) |
|----------|:-----:|:-------------:|:--------------:|
| Abstract | 4 | 1 (25%) | 3 (75%) |
| Nature & Landscape | 17 | 10 (59%) | 7 (41%) |
| Objects & Still Life | 12 | 4 (33%) | 8 (67%) |
| Fire & Energy | 3 | 0 | 3 (100%) |
| Silhouettes (B1 only) | 4 | 0 | 4 (100%) |
| **Total** | **40** | **15 (38%)** | **25 (62%)** |

For any given feeling, the always-visible pool = 15 universal items minimum, before restricted items are added.

---

## 9. Sub-Illustration Accent Items — SV-ACC Library

When a main illustration is selected, the system automatically assigns small secondary accent props to fill the scene (A2 density, B1 supporting props). For Suvichar, these accents are drawn from the `SV-ACC-*` set rather than the GM-themed `ACCENT_ITEMS`, ensuring the supporting props match the contemplative quote-card aesthetic.

| ID | Name | Photo Desc (B1) | Illustration Desc (A2) |
|----|------|----------------|------------------------|
| SV-ACC-01 | Scattered Autumn Leaves | a few scattered dried autumn leaves on the ground | a few small illustrated autumn leaves scattered nearby |
| SV-ACC-02 | Bookmark | a slim ribbon bookmark peeking out from a book | a small illustrated ribbon bookmark tucked into the scene |
| SV-ACC-03 | Pen Nib / Ink Drop | a calligraphy pen nib or small ink drop on the surface | a tiny illustrated pen nib or ink drop accent |
| SV-ACC-04 | Smooth River Pebbles | two or three smooth rounded river pebbles on the surface | two or three small illustrated smooth pebbles |
| SV-ACC-05 | Dried Pressed Flower | a single dried pressed flower or botanical sprig | a small illustrated dried pressed botanical |
| SV-ACC-06 | Simple Candle Stub | a short unadorned candle with a small gentle flame | a small illustrated slim candle with a tiny flame |

These supplement (not replace) the shared ACCENT_ITEMS library — items like Fallen Petals (ACC-08), Distant Birds (ACC-10), Cobblestone Path (ACC-12), Single Butterfly (ACC-27), Reading Glasses (ACC-18), and Potted Plant (ACC-19) are also used where contextually appropriate.

### Sub-element mapping per main illustration (representative)

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

---

## 10. Prompt Context — Suvichar-Specific Variables

| Prompt Element | Good Morning | Suvichar |
|----------------|-------------|----------|
| Hero text | "Good Morning" | User-typed quote (entered in Custom Text step) |
| Scene atmosphere | `early morning Indian setting` | `contemplative quote-card scene` |
| Scene authenticity | `real Indian morning setting` | `real, unposed contemplative scene` |
| Gem setting context | `early morning in India` | `a contemplative natural or interior scene` |
| Light/time context | `natural and time-appropriate for early morning` | `natural and atmospheric` |
| Style mood word | `morning` | `quote` |
| Category label | Good Morning | Suvichar / Quote |

These swap automatically through `getCategoryAtmosphere()` when category is `'suvichar'`. The GM values are byte-identical to the original framework — no GM prompts are affected.

---

## 11. Layout Bias (Guidance, Not Hard Filter)

| Layout | Suvichar Suitability | Reason |
|--------|---------------------|--------|
| L2 — Overlay / Text Centre | ★ Best | Quote reads full canvas with atmospheric illustration behind |
| L5 — Text Bottom | ★ Best | Illustration fills top, quote anchors at base — classic card format |
| L1 — Text Top | ✓ Works | Good for short punchy quotes |
| L6 — Text Centre (frame) | ✓ Works | Clean frame + centred quote — strong for A1 archetype |
| L3 / L4 — Text Left / Right | ~ With Care | Works only with Small illustration size |

---

## 12. What Does NOT Change

Everything below is fully inherited from `Template_Creation_Framework_v20.md` — no modifications:

- The 3 archetype families (A1, A2, B1) and their wizard flows
- The 5 tracks (A–E) and their colour palettes, font pools, motif sets
- Background finish options per track — Suvichar uses the same per-track finishes as Good Morning (no additions, no removals)
- Illustration render style step — inherited per track, no locking (all illustrations follow track default)
- Illustration size — all three sizes available (Small / Medium / Large), no cap
- All 6 layouts (L1–L6) and frame/overlay compatibility rules
- Prompt builder logic for all 5 platforms (Firefly, Midjourney, Leonardo, Gemini)
- Shared ACCENT_ITEMS library (ACC-01..ACC-30) — still used where contextually appropriate alongside SV-ACC-* items
- Density auto-calculation for A2
- Intensity controls
- Character limits and prompt construction helpers (stripHex, trunc)

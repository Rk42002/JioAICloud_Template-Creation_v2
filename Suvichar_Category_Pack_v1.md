# Suvichar / Daily Quotes — Category Pack v1
> **Incremental spec on top of Template_Creation_Framework_v20.md**
> This document only covers what CHANGES or is NEW for the Suvichar/Quotes category.
> Everything not mentioned here (archetypes, layouts, tracks, colour palettes, font pairings, prompt builders) is inherited unchanged from the framework.

---

## 1. What This Category Is

Suvichar (motivational / inspirational / daily quotes) is a text-first category. The quote is the hero — illustration is atmospheric support only. Three things change from Good Morning:

1. A new **Feeling** selector runs before track selection
2. Illustration size is capped at Medium (no Large/Hero)
3. Some abstract items move to Background Finish; remaining abstract illustrations lock the render style step

---

## 2. Wizard Flow Change

**Good Morning flow:**
`Archetype → Track → Layout → Colour → Font → Illustration → Intensity`

**Suvichar flow:**
`Archetype → **Feeling** → Track (filtered by Feeling) → Layout → Colour → Background Finish → Font → Illustration → Intensity`

Feeling is inserted as **Step 1b** — after archetype, before track. Hard filter: incompatible tracks are hidden entirely, not dimmed.

---

## 3. Feeling System

Five feelings covering the full emotional range of quote content. Each has a distinct visual personality that drives track filtering, illustration selection, and background finish choices downstream.

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

## 5. Illustration Size — Cap

**Rule:** Large / Hero illustration size (50%+ canvas) is **not available** for Suvichar. Only Small Accent (<15%) and Medium (30–40%) are shown.

**Reason:** Quote text needs breathing room. A dominant illustration competes with the message.

No other illustration controls change. Density auto-calculation (A2), curated accent props, and the ACCENT_ITEMS library all carry over unchanged.

---

## 6. Background Finish — Suvichar Additions

Some items that feel like "abstract illustrations" are actually **background treatments** — they work at the canvas level, not as placed assets. These are added as new Background Finish options for Suvichar, not as illustration picks.

**New Background Finish options (Suvichar-only, added to existing per-track finish options):**

| Finish ID | Name | Description | Best Feeling Fit | Track Fit |
|-----------|------|-------------|-----------------|-----------|
| SV-BG01 | Watercolour Wash | Loose watercolour bleed across canvas, no defined edges | F1, F2, F3 | B, E |
| SV-BG02 | Paper Texture / Torn Edge | Aged paper grain or torn paper layered on canvas | F2, F3, F4 | B, C |
| SV-BG03 | Soft Gradient Orb | Blurred radial light bloom centred on canvas | F1, F2, F4 | C, E |
| SV-BG04 | Ink Wash / Sumi-e Background | Full-canvas ink wash, diffuse, with visible brushwork grain | F2, F3 | B, C |

These are shown in the **Background Finish step** alongside existing track finishes. They do not appear in the Illustration step.

---

## 7. Illustration Render Style — Lock Rule for Abstract Illustrations

The following items stay as **placed illustrations** (not background finishes) but have an inherent render style — asking a user to then apply "3D Cartoon" or "Watercolour Botanical" on top creates a contradiction.

**Rule:** When an Abstract Illustration is selected, the render style step is **locked** to match the item. The user cannot override it.

| Illustration | Locked Render Style |
|---|---|
| SV-I01 Ink Brush Stroke | Ink / Sumi-e — always |
| SV-I02 Geometric Shards | Flat Vector / Geometric — always |
| SV-I03 Soft Gradient Orb (as illustration) | Soft Gradient / Blur — always |

All other illustrations follow the standard per-track render style step — no change.

---

## 8. Illustration Catalogue — Suvichar Pack

### Universality Key

> **U = Universal** — works for all 5 feelings, shown for any selection
> **R = Restricted** — shown only for the listed feelings, hidden for others

---

### 8.1 Carry-over from Good Morning (already in catalogue)

Existing items — just add feeling tags. No prompt changes needed.

| Name | U / R | Feeling Restriction | Notes |
|------|:-----:|---------------------|-------|
| Sunrise / Morning Sky | **U** | — | Works across all 5 feelings |
| Lotus Flower | **U** | — | Universally calming |
| Birds in Flight | **U** | — | Freedom / hope — multi-feeling |
| Marigold / Flowers | **U** | — | Warm and neutral enough for all |
| Flowing River / Water | **U** | — | Calm + journey metaphor |
| Clouds / Sky | **U** | — | Atmospheric, universally safe |
| Sunrise over Hills | **U** | — | Classic quote card backdrop |
| Rainbow | R | F1, F4 | Too cheerful for F3 / too intense for F2 / too soft for F5 |
| Candle / Diya | R | F2, F3, F4 | Reflective / devotional — not Fire & Drive |
| Mountain / Landscape | R | F1, F2, F4 | Grounded, not Fierce or typically Bittersweet |
| Full Moon / Night Sky | R | F2, F3 | Night energy — Still Waters / Bittersweet only |
| Steaming Chai Cup | R | F4 | Daily ritual — too cosy for hero use in other feelings |

---

### 8.2 New Illustrations — Suvichar Specific (27 items)

---

**Abstract Illustrations** *(render style locked — see Section 7)*

| ID | Name | Description | U/R | Feeling Restriction | Archetypes |
|----|------|-------------|:---:|---------------------|------------|
| SV-I01 | Ink Brush Stroke | Single bold sumi-e brushstroke, black or deep colour on neutral | R | F2, F3, F5 | A1, A2 |
| SV-I02 | Geometric Shards | Fragmented low-poly angular shapes, sharp and bold | R | F5 | A1, A2 |
| SV-I03 | Gradient Orb | Blurred radial light bloom as a placed accent element | **U** | — | A1, A2 |
| SV-I04 | Splatter / Paint Burst | Dynamic ink or paint splatter, energy and expression | R | F1, F5 | A1, A2 |

---

**Nature & Landscape**

| ID | Name | Description | U/R | Feeling Restriction | Archetypes |
|----|------|-------------|:---:|---------------------|------------|
| SV-I05 | Lone Tree (Silhouette) | Single bare or leafy tree against empty horizon | R | F2, F3, F4 | A1, A2, B1 |
| SV-I06 | Mountain Range (Minimal) | Layered mountain silhouette, clean and minimal | **U** | — | A1, A2, B1 |
| SV-I07 | Winding Path / Road | Path disappearing into distance, journey metaphor | **U** | — | B1 |
| SV-I08 | Falling Leaves | Scattered autumn leaves in gentle drift | R | F2, F3, F4 | A1, A2 |
| SV-I09 | Desert Dunes | Smooth sand dunes, minimalist, warm tones | R | F2, F4 | A1, A2, B1 |
| SV-I10 | Stormy Sky | Dramatic sky, heavy clouds, high contrast | R | F3, F5 | B1 |
| SV-I11 | Sunrays Through Trees | God rays filtering through a forest canopy | **U** | — | B1 |
| SV-I12 | Crescent Moon & Stars | Delicate crescent moon with scattered stars, night sky | R | F2, F3 | A1, A2 |
| SV-I13 | Ocean Waves (Minimal) | Simple rolling wave silhouette or horizon line | **U** | — | A1, A2, B1 |

---

**Objects & Still Life**

| ID | Name | Description | U/R | Feeling Restriction | Archetypes |
|----|------|-------------|:---:|---------------------|------------|
| SV-I14 | Open Book / Pages | Book open flat, pages in soft light | **U** | — | A1, A2, B1 |
| SV-I15 | Hourglass | Classic hourglass with flowing sand | R | F2, F4 | A1, A2 |
| SV-I16 | Compass | Old brass compass — direction and purpose | **U** | — | A1, A2 |
| SV-I17 | Coffee / Tea Cup (Desk) | Cup on desk beside a notebook — daily ritual | R | F4 | A2, B1 |
| SV-I18 | Quill Pen & Inkwell | Writer's tool — knowledge, craft, expression | R | F2, F4 | A1, A2 |
| SV-I19 | Lantern (Glowing) | Single glowing lantern, warm light in darkness | R | F2, F3, F4 | A1, A2 |
| SV-I20 | Trophy / Medal | Clean minimal trophy silhouette | R | F1, F5 | A1, A2 |
| SV-I21 | Key (Ornate / Minimal) | A key — metaphor for opportunity, unlocking | **U** | — | A1, A2 |
| SV-I22 | Magnifying Glass | Curiosity, discovery, looking closer | R | F2, F4 | A1, A2 |
| SV-I23 | Seed / Sapling | Small plant emerging from soil — growth, beginnings | R | F1, F4 | A1, A2 |

---

**Fire & Energy**

| ID | Name | Description | U/R | Feeling Restriction | Archetypes |
|----|------|-------------|:---:|---------------------|------------|
| SV-I24 | Flame / Fire | Single clean flame — ambition, passion | R | F1, F5 | A1, A2 |
| SV-I25 | Lightning Bolt | Bold graphic lightning, energy and power | R | F5 | A1, A2 |
| SV-I26 | Rising Sun (Graphic) | Stylised graphic rising sun with rays, bold | R | F1, F5 | A1, A2 |

---

**Human / Figurative** *(B1 archetype only — photorealistic)*

| ID | Name | Description | U/R | Feeling Restriction | Archetypes |
|----|------|-------------|:---:|---------------------|------------|
| SV-I27 | Silhouette — Arms Raised | Figure arms raised against sky, victory / freedom | R | F1, F5 | B1 |
| SV-I28 | Silhouette — Seated / Meditating | Person in stillness, introspective | R | F2, F3, F4 | B1 |
| SV-I29 | Silhouette — Walking Alone | Figure walking on road or beach, solitary | R | F2, F3 | B1 |
| SV-I30 | Silhouette — Running / Sprinting | Dynamic running figure, motion optional | R | F1, F5 | B1 |

---

### 8.3 Universality Summary

| Category | Total | Universal (U) | Restricted (R) |
|----------|:-----:|:-------------:|:--------------:|
| Good Morning carry-overs | 12 | 7 (58%) | 5 (42%) |
| Abstract Illustrations | 4 | 1 (25%) | 3 (75%) |
| Nature & Landscape | 9 | 4 (44%) | 5 (56%) |
| Objects & Still Life | 10 | 4 (40%) | 6 (60%) |
| Fire & Energy | 3 | 0 | 3 (100%) |
| Human / Figurative | 4 | 0 | 4 (100%) |
| **Total** | **42** | **16 (38%)** | **26 (62%)** |

For any given feeling, the always-visible pool = 7 universal carry-overs + 9 universal new items = **16 items minimum**, before restricted items are added.

---

## 9. Layout Bias (Guidance, Not Hard Filter)

| Layout | Suvichar Suitability | Reason |
|--------|---------------------|--------|
| L2 — Overlay / Text Centre | ★ Best | Quote reads full canvas with atmospheric illustration behind |
| L5 — Text Bottom | ★ Best | Illustration fills top, quote anchors at base — classic card format |
| L1 — Text Top | ✓ Works | Good for short punchy quotes |
| L6 — Text Centre (frame) | ✓ Works | Clean frame + centred quote — strong for A1 archetype |
| L3 / L4 — Text Left / Right | ~ With Care | Works only with Small illustration size |

---

## 10. What Does NOT Change

Everything below is fully inherited from `Template_Creation_Framework_v20.md` — no modifications:

- The 3 archetype families (A1, A2, B1) and their wizard flows
- The 5 tracks (A–E) and their colour palettes, font pools, motif sets
- Background Finish options per track — Suvichar adds 4 new finishes on top (Section 6), does not replace existing ones
- Illustration render style step — inherited per track (exception: Abstract Illustrations lock render style, see Section 7)
- All 6 layouts (L1–L6) and frame/overlay compatibility rules
- Prompt builder logic for all 5 platforms (Firefly, Midjourney, Leonardo, Gemini)
- ACCENT_ITEMS library (30 accent props) — shared across categories
- Density auto-calculation for A2
- Intensity controls
- Character limits and prompt construction helpers (stripHex, trunc)

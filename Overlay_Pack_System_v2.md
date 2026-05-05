# Overlay Pack System — Spec v2
> **Architectural extension to Template_Creation_Framework_v20.md**
> Defines the Overlay Pack layer — a thin, reusable content modifier that sits between a Base Category and the user-facing Occasion picker.

**Changes from v1:**
- Added Lever 4: Track Filtering — overlays can hard-block incompatible tracks (Section 2)
- Expanded all 4 overlay illustration catalogues from 8–9 items to 12–15 items each, with sub-categories
- More specific motif descriptions with exact visual direction
- Track filtering tables added to every overlay pack
- Overlay selection happens at category/occasion pick — before the wizard starts
- **NEW: Overlay × Base Category Compatibility** (Section 5) — hard rules for which overlays apply to which base categories, with detailed rationale for every exclusion
- **NEW: Firefly Prompt Budget** (Section 6) — character budget analysis, compact keyword sets per overlay, worst-case validation against 950-char Firefly cap

---

## 1. The Three-Layer Architecture

The template system has three layers. Each layer owns specific things and cannot touch what belongs to another layer.

| Layer | What it is | What it owns | Examples |
|-------|-----------|-------------|---------|
| **Framework** | The engine | Archetypes, tracks, layouts, palettes, fonts, render styles, background finishes, prompt builder architecture, wizard flow, density calc, intensity | Template_Creation_Framework_v20.md |
| **Base Category** | The content type — defines hero text | Hero text, full illustration catalogue, full motif set per track, atmosphere & mood keywords, negative terms | Good Morning, Birthday, Suvichar, Diwali, Rath Yatra |
| **Overlay Pack** | A flavour/context modifier — no hero text | Illustration additions & restrictions, motif swaps & additions, frame type restrictions or special unlocks, track filtering, atmosphere keyword additions, negative term additions | Devotional, Summer, Rain/Monsoon, Cricket |

**Composition rule:** An **Occasion** = Base Category + (optional) Overlay Pack. This is what the user picks from a flat list.

**Selection timing:** The user selects the Occasion (which includes the overlay) at the very start — before the wizard begins. The overlay's track filter, illustration restrictions, and motif swaps are all applied before the user sees any wizard step.

| User sees | Base Category | Overlay Pack |
|-----------|--------------|-------------|
| Good Morning | Good Morning | — |
| Devotional Good Morning | Good Morning | Devotional |
| Cricket Good Morning | Good Morning | Cricket |
| Rainy Good Morning | Good Morning | Rain/Monsoon |
| Summer Birthday | Birthday | Summer |
| Birthday | Birthday | — |
| Rath Yatra | Rath Yatra | — |

---

## 2. What an Overlay Pack CAN Change

An overlay has exactly **four levers** — track filtering, illustrations, motifs/decor, and frame types. Plus prompt-level keyword additions that follow from these.

### Lever 1 — Track Filtering: Hard Block

An overlay can **hide incompatible tracks** entirely. When a track is blocked, it does not appear in the wizard's Track step. This is a hard filter — blocked tracks are hidden, not dimmed.

**Rationale:** Some overlay + track combinations produce visual contradictions. Devotional content in an Artsy Playful doodle style feels disrespectful. Cricket in a Soft & Warm pastel style feels limp.

**Master Track Filter Table:**

| Overlay | A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|---------|:-:|:-:|:-:|:-:|:-:|
| Devotional | ✅ | ✅ | ✅ | ❌ | ✅ |
| Summer | ✅ | ✅ | ✅ | ✅ | ✅ |
| Rain / Monsoon | ❌ | ✅ | ✅ | ✅ | ✅ |
| Cricket / IPL | ✅ | ✅ | ✅ | ✅ | ❌ |

**Why each block:**
- **Devotional blocks D:** Playful doodle/cartoon treatment of sacred symbols (Om, temple, diya) feels tonally wrong. Devotional needs dignity — ornate (A), modern (B), minimal (C), or soft (E) all work.
- **Rain blocks A:** Shiny Maximal's gold sparkle, high gloss, and ornate energy contradicts monsoon's overcast, muted, cosy mood. Rain is naturally muted — desi (B), minimal (C), playful (D), or soft (E) all work.
- **Cricket blocks E:** Soft & Warm's pastel watercolour and gentle energy undercuts cricket's adrenaline. Sports needs punch — shiny (A), modern (B), minimal (C), or playful (D) all work.
- **Summer blocks nothing:** Summer's bright, vibrant energy works across all visual styles.

### Lever 2 — Illustrations: Restrict Base + Add New

| Action | Mechanic | Example |
|--------|---------|---------|
| **Add** themed illustrations | 8–15 new items added to the base category's pool. Tagged with archetype compatibility (A1, A2, B1) like any illustration. | Devotional adds: Temple Silhouette, Praying Hands, Om Symbol, etc. |
| **Restrict** base illustrations | Specific base items hidden when this overlay is active. Listed explicitly by ID — not by category. | Cricket on Good Morning hides "Lotus Flower" and "Candle / Diya" |

**Result:** User sees `(base pool − restricted items) + overlay items`

Restriction is optional. Most overlays will only add, not restrict. Restrict only when a base item actively clashes with the overlay's energy.

### Lever 3 — Motifs & Decor: Swap + Add per Track

| Action | Mechanic | Example |
|--------|---------|---------|
| **Swap** specific motifs | Replace named base motifs with overlay-specific ones, per track. 1:1 replacement — total motif count per track stays the same. | Devotional on Track A: swap "Sparkle Cluster" → "Om with Gold Halo" |
| **Add** motifs | Add 1–2 extra motifs on top of existing set, per track. Use sparingly — too many motifs crowds the frame. | Rain on Track D: add "Doodle Raindrop Border" alongside existing set |

**How it maps to archetypes:**
- **A1 Frame Decoration:** Swapped/added motifs appear in the Frame Decoration Level options (Plain / Simple / Detailed). Same 3-level system — the motifs themselves change, not the levels.
- **A2 Accent Density:** Swapped/added motifs feed into the density auto-calculator's accent pool. Same density math — different items in the pool.

### Lever 4 — Frame Types: Restrict or Unlock Special

| Action | Mechanic | Example |
|--------|---------|---------|
| **Restrict** | Hide specific frame types (F1–F5) that don't work with this overlay. Hard filter — hidden from UI. | Cricket restricts F5 (Arch / Canopy) — too ornate for sports energy |
| **Unlock special** | Make a special frame type available ONLY when this overlay is active. Defined as a new F-code (F6+). | Devotional unlocks F6 "Temple Arch" — curved temple gopuram silhouette overhead |

**This lever is optional.** Most overlays will not touch frame types at all. Only use when there's a strong visual reason.

---

## 3. What an Overlay Pack CANNOT Change

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

---

## 4. Prompt-Level Additions

An overlay doesn't change prompt builder functions — it **appends** to the variables that feed into them:

| Prompt element | How overlay modifies it |
|----------------|----------------------|
| **Atmosphere keywords** | Overlay keywords are appended after base category's atmosphere. E.g., base: `"warm golden morning light, India morning atmosphere"` + overlay: `", monsoon atmosphere, overcast sky, rain-washed freshness"` |
| **Mood keywords** | Same append logic. Base mood + overlay mood. |
| **Negative terms** | Overlay negatives are appended to base + archetype negatives. Overlay can only ADD negatives, never remove base negatives. |
| **Scene context (B1)** | Overlay context is appended to base's B1 scene description. E.g., base: `"morning scene in India"` + overlay: `", temple courtyard, devotional setting"` |

---

## 5. Overlay × Base Category Compatibility

Not every overlay makes sense with every base category. This is a **hard rule** — the system only offers an overlay within a base category when the pairing is defined here as ✅.

### 5.1 Compatibility Matrix

| Overlay | Good Morning | Suvichar | Birthday | Rationale summary |
|---------|:---:|:---:|:---:|-------------------|
| Devotional | ✅ | ✅ | — | Devotional morning + devotional wisdom are natural. Devotional birthday is awkward — birthday is celebration-first, not prayer. |
| Summer | ✅ | ✅ | ✅ | Summer flavour works everywhere — seasonal energy is universally composable. |
| Rain / Monsoon | ✅ | ✅ | — | Monsoon morning + monsoon wisdom are atmospheric. Rainy birthday feels dampened — birthday wants bright energy, not overcast cosy. |
| Cricket / IPL | ✅ | — | ✅ | Cricket morning + cricket birthday are both high-energy celebrations. Cricket Suvichar is a mismatch — motivational quotes need universality, not sports branding. |

### 5.2 Detailed Rationale — Exclusions

**Devotional × Birthday — excluded**
Birthday's emotional lane is celebration — cake, balloons, confetti, party energy. Devotional's emotional lane is reverence — temple, prayer, sacred stillness. Composing them creates a tonal clash: the overlay tries to make the scene sacred while the base category's illustrations and hero text ("Happy Birthday") push celebration. A user wanting a blessing-style birthday would use a Puja Thali illustration from the Birthday base catalogue (BD-I15) without needing the full devotional overlay. Separately, the devotional overlay's illustration restrictions (which strip party-energy items) would gut the Birthday illustration pool, leaving almost nothing celebratory.

**Rain / Monsoon × Birthday — excluded**
Rain/Monsoon's mood is cosy, introspective, overcast — chai on a window ledge, puddle reflections, grey skies. Birthday's mood is bright, outward, joyful. The overlay's atmosphere keywords (`overcast sky, soft diffused rain light, petrichor mood`) directly contradict birthday's festive energy. Additionally, Rain blocks Track A (Shiny Maximal), which is one of Birthday's strongest tracks — gold foil balloons, confetti bursts, ornate gift bows all live in Track A's energy. Removing Track A from Birthday strips its most natural aesthetic lane.

**Cricket / IPL × Suvichar — excluded**
Suvichar is a wisdom/quote category. The hero text is a thought-provoking quote, not a greeting. Cricket branding (stadium, bat, jersey, scoreboard) around a philosophical quote creates a jarring mismatch — the visual screams "match day" while the text says something contemplative about life. Suvichar also uses a Feeling system (5 feelings: Inspired, Reflective, Grateful, Resilient, Hopeful) that has no natural mapping to cricket energy. A motivational sports quote is a niche use case better served by a future "Sports Motivation" base category with its own text library, not by forcing cricket visuals onto a general wisdom framework.

### 5.3 What This Means for the Occasion Picker

The Occasion picker (flat list) only shows valid combinations. For each base category, the available overlays are:

| Base Category | Available Overlays |
|---------------|-------------------|
| Good Morning | Devotional, Summer, Rain/Monsoon, Cricket/IPL |
| Suvichar | Devotional, Summer, Rain/Monsoon |
| Birthday | Summer, Cricket/IPL |

**Implementation note:** This compatibility table is a config lookup, not a runtime filter. When building the occasion list for a base category, only include overlay options from this table. Invalid combinations never appear in the UI.

### 5.4 Future Base Categories

When a new base category is added (e.g., Diwali, Eid, Holi), the overlay compatibility table must be extended. Apply the same logic:

1. Does the overlay's mood complement or contradict the base category's emotional lane?
2. Does the overlay's track filtering remove a critical track for this base category?
3. Does the overlay's illustration restriction gut the base pool?
4. Does the overlay's visual branding clash with the hero text?

If any answer raises a strong flag → exclude the pairing.

---

## 6. Firefly Prompt Templates — Overlay Integration

### 6.1 The Constraint

Adobe Firefly has a hard character limit: **≤ 950 characters** for both With-Text and No-Text prompt variants. This applies to all archetypes (A1, A2, B1). The existing `trunc()` function and per-component character caps in `GoodMorning_Prompt_Generator_v5.html` enforce this.

The overlay system adds new content to prompts. These additions must fit **within the existing 950-char budget** — they do not get extra characters. Overlays inject through existing variable slots, not new ones.

### 6.2 Prompt Template Formulas — A1/A2 (Illustrated)

The v20 framework defines this Firefly template for A1/A2:

```
[SUBJECT]. [ILLUSTRATION_RENDERING_STYLE]. [FINISH_PROMPT]. [MOTIF_PROMPT].
[TRACK_STYLE], [COLOUR_DESC], [CUSTOMIZATION_PROMPT].
Portrait 9:16 for mobile. Content type: Art. Stylize: 80.
Do not include any text, letters, words, typography, watermarks, logos, or minimalist elements.
```

**With overlay active, the template becomes:**

```
[SUBJECT]. [ILLUSTRATION_RENDERING_STYLE]. [FINISH_PROMPT]. [OVERLAY_MOTIF_PROMPT].
[TRACK_STYLE], [OVERLAY_ATMOSPHERE_COMPACT], [COLOUR_DESC], [CUSTOMIZATION_PROMPT].
Portrait 9:16 for mobile. Content type: Art. Stylize: 80.
Do not include any text, letters, words, typography, watermarks, logos,
[OVERLAY_NEGATIVE_GUARD], or minimalist elements.
```

**What changes — variable by variable:**

| Variable | Without overlay | With overlay | Notes |
|----------|----------------|-------------|-------|
| `[SUBJECT]` | Base illustration from category pool | Illustration from `(base pool − restricted) + overlay added` — same slot, different item | If user picks an overlay illustration (e.g., OV-DEV-I09 Temple Silhouette), its name + desc flow into `[SUBJECT]` exactly like any base illustration. No format change. |
| `[ILLUSTRATION_RENDERING_STYLE]` | Track render style (unchanged) | Same — overlay cannot touch render styles | No change. |
| `[FINISH_PROMPT]` | BG finish from track (unchanged) | Same — overlay cannot touch finishes | No change. |
| `[MOTIF_PROMPT]` → `[OVERLAY_MOTIF_PROMPT]` | Base motif from track | Overlay-swapped motif (1:1 replacement) | E.g., Track A base "Sparkle Cluster" becomes "Om with Gold Halo". Same prompt position, different motif name. Compact Firefly motif format: `"Motif: [name] on border frame edges only, separated from illustration."` |
| `[TRACK_STYLE]` | Track style string (unchanged) | Same — overlay cannot touch track styles | No change. |
| *(new)* `[OVERLAY_ATMOSPHERE_COMPACT]` | *(empty — not present)* | Compact atmosphere keywords inserted before `[COLOUR_DESC]` | ≤50 chars. E.g., `spiritual devotional warmth, temple dawn glow`. See Section 6.4 for per-overlay compact strings. |
| `[COLOUR_DESC]` | Palette hex + role desc (unchanged) | Same — overlay cannot touch palettes | No change. |
| `[CUSTOMIZATION_PROMPT]` | Intensity + preset (unchanged) | Same | No change. |
| *(new)* `[OVERLAY_NEGATIVE_GUARD]` | *(empty — not present)* | Short guard phrase appended to "Do not include" line | E.g., Devotional adds `party, nightclub, cartoon, doodle`. Cricket adds `calm, spiritual, soft, pastel`. Sits inside the existing fixed instruction line — no new prompt section. |

### 6.3 Prompt Template Formulas — B1 (Photo Background)

The v5 generator builds B1 Firefly prompts differently — photorealistic, no frames, no illustration rendering:

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

**With overlay active, the template becomes:**

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

**What changes — variable by variable:**

| Variable | Without overlay | With overlay | Truncation |
|----------|----------------|-------------|:----------:|
| `[CATEGORY_ATMOSPHERE]` | Base category atmosphere (e.g., `Indian morning atmosphere`) | Base + `, [OVERLAY_ATMOSPHERE_COMPACT]` appended | Part of header ~120 chars total |
| `[SCENE_DESCRIPTION]` | Base scene (e.g., `steaming chai on balcony railing, morning light`) | Base + `, [OVERLAY_B1_SCENE_COMPACT]` appended | `trunc(scenePh, 130)` — clips at last comma if over 130 |
| `[MOOD]` | Base mood (e.g., `warm, peaceful, serene`) | Base + `, [OVERLAY_MOOD_COMPACT]` appended | `trunc(mood, 90)` — clips at last comma if over 90 |
| `[PHOTO_TRACK_AESTHETIC]` | Unchanged | Same — overlay cannot touch track aesthetics | `trunc(90)` |
| `[INTENSITY]` | Unchanged | Same | `trunc(80)` |
| All others | Unchanged | Same | Same |

### 6.4 Compact Keyword Sets for Firefly (≤950 char budget)

Each overlay's "Prompt Additions" section defines **full** keyword lists for Midjourney, Leonardo, and Gemini (generous/no char limits). For **Firefly specifically**, only the compact versions below are used — these are the exact strings that get appended before per-component `trunc()` runs.

**A1/A2 Compact Strings:**

| Overlay | `[OVERLAY_ATMOSPHERE_COMPACT]` (≤50 chars) | `[OVERLAY_NEGATIVE_GUARD]` (appended to "Do not include" line) |
|---------|------|------|
| Devotional | `spiritual devotional warmth, temple dawn glow` | `party, nightclub, cartoon, doodle` |
| Summer | `bright Indian summer, harsh golden sunlight` | `cold, snow, fog, rain, overcast` |
| Rain / Monsoon | `Indian monsoon, overcast rain light, petrichor` | `harsh sunlight, desert, clear blue sky` |
| Cricket / IPL | `cricket match energy, stadium floodlight buzz` | `calm, spiritual, soft, pastel, watercolour` |

**B1 Compact Strings:**

| Overlay | `[OVERLAY_ATMOSPHERE_COMPACT]` (≤50 chars) | `[OVERLAY_MOOD_COMPACT]` (≤40 chars) | `[OVERLAY_B1_SCENE_COMPACT]` (≤60 chars) |
|---------|------|------|------|
| Devotional | `spiritual devotional warmth, temple dawn glow` | `reverent, peaceful, prayerful, blessed` | `temple courtyard at dawn, pooja room morning light` |
| Summer | `bright Indian summer, harsh golden sunlight` | `vibrant, sunny, refreshing, cheerful` | `Indian summer courtyard, bright harsh sunlight, mango trees` |
| Rain / Monsoon | `Indian monsoon, overcast rain light, petrichor` | `cosy, nostalgic, refreshing, contemplative` | `monsoon balcony, rain-washed streets, overcast lush green` |
| Cricket / IPL | `cricket match energy, stadium floodlight buzz` | `energetic, competitive, exciting, proud` | `floodlit cricket stadium evening, green pitch, packed stands` |

### 6.5 Assembled Example Prompts — Firefly

To show the style concretely, here are fully assembled sample prompts with an overlay active.

**Example 1: A1 + Track A + Devotional overlay + Good Morning**

```
Shiny Maximal Good Morning poster, 9:16 vertical. BG: warm amber and deep
terracotta, radial gradient from bright centre to darker edges. Frame:
full perimeter frame with detailed Om with Gold Halo and Brass Bell Garland
motifs. Text zone: upper 25%. Illustration: lower area. Temple Silhouette:
Hindu temple gopuram silhouette against dawn sky, clean outline, backlit
with golden-orange sky gradient. Ornamental vector illustration with
gold-foil fills, paisley and mandala borders. Spiritual devotional warmth,
temple dawn glow. Sparkle particles. Clean "Good Morning" text in
decorative font in the text zone, legible, not overlapping illustration.
```
*(~620 chars — well within 950)*

**Example 2: A2 + Track B + Summer overlay + Birthday**

```
Modern Desi Happy Birthday poster, 9:16 vertical. BG: earthy warm palette,
soft matte finish. Scattered Block-Print Mango Motif and Nimbu Slice Corner
accents around illustration. Text zone: lower 25%. Illustration: upper
area. Mango (Aam): Ripe Alphonso mango, whole with one sliced half showing
orange flesh, vibrant yellow-orange. Contemporary Indian editorial
illustration, warm earthy restraint. Bright Indian summer, harsh golden
sunlight. Accents: Matka Icon, same style. Balanced composition.
Clean "Happy Birthday" text in decorative font in the text zone, legible,
not overlapping illustration.
```
*(~640 chars — well within 950)*

**Example 3: B1 + Track B + Rain/Monsoon overlay + Good Morning**

```
Photorealistic Modern Desi Good Morning poster, 9:16 vertical, full-bleed
photograph, India morning atmosphere, Indian monsoon, overcast rain light,
petrichor. Steaming cutting chai glass on window ledge, rain-streaked
glass behind, blurred wet street outside, warm amber tea colour, monsoon
balcony, rain-washed streets, overcast lush green. Warm, peaceful, cosy,
nostalgic, refreshing, contemplative. Muted earthy tones, desaturated
naturals, editorial restraint. Medium close-up, environmental detail.
Text zone: upper third, subtle semi-transparent dark overlay. Clean
"Good Morning" text in white decorative font in the text zone, legible.
DSLR quality, sharp focus.
```
*(~640 chars — well within 950)*

**Example 4: A2 + Track D + Cricket overlay + Good Morning**

```
Artsy Playful Good Morning poster, 9:16 vertical. BG: bright bold palette,
flat colour fill. Scattered Doodle Bat & Ball and "SIX!" Sticker accents
around illustration. Text zone: centre 25%. Illustration: surrounding
area. Cricket Bat & Ball: classic willow bat crossed diagonally with red
leather ball, iconic composition. Cheerful bright playful illustration,
WhatsApp sticker energy, thick outlines, vibrant flat colours. Cricket
match energy, stadium floodlight buzz. Doodle Stumps (Flying) corner
accents, same style. High energy composition. Clean "Good Morning" text
in decorative font in the text zone, legible, not overlapping illustration.
```
*(~660 chars — well within 950)*

### 6.6 Character Budget Summary

| Archetype | Without overlay (typical) | With overlay (typical) | With overlay (worst case) | Headroom at 950 |
|-----------|:---:|:---:|:---:|:---:|
| A1 | 650–750 | 700–800 | ~855 | ~95 chars |
| A2 | 700–800 | 750–850 | ~880 | ~70 chars |
| B1 | 550–680 | 600–730 | ~780 | ~170 chars |

The worst case (A2 + Track A + Sparkle particles + longest overlay) reaches ~880. The final `substring(0, 950)` safety net clips at the last complete word if anything ever exceeds.

### 6.7 How Overlay Additions Enter Each Variable Slot

| Overlay addition | Variable slot it enters | Existing `trunc()` cap | Impact |
|-----------------|------------------------|:---:|------|
| Atmosphere keywords | `[OVERLAY_ATMOSPHERE_COMPACT]` → appended to header (A1/A2) or `[CATEGORY_ATMOSPHERE]` (B1) | Header ~50–120 | +30–50 chars. Bounded by compact keyword set. |
| Mood keywords | `[OVERLAY_MOOD_COMPACT]` → appended to `[MOOD]` (B1 only) | 90 | Appended before `trunc()`. If combined exceeds 90, clips at last comma. |
| Negative guard | `[OVERLAY_NEGATIVE_GUARD]` → appended to "Do not include" line | N/A (fixed instruction) | +20–40 chars. Sits inside existing instruction, not a new section. |
| B1 Scene context | `[OVERLAY_B1_SCENE_COMPACT]` → appended to `[SCENE_DESCRIPTION]` | 130 | Appended before `trunc()`. If combined exceeds 130, clips at last comma. |
| Motif swap | `[OVERLAY_MOTIF_PROMPT]` → replaces `[MOTIF_PROMPT]` | ~80 | 1:1 replacement — same format, different name. No length change. |
| Illustration swap | `[SUBJECT]` → from overlay pool instead of base pool | ~180 | Different item, same slot. No additional budget. |

**Key design principle:** Overlay keywords flow through the same `[VARIABLE]` injection pipeline defined in v20. No new builder functions, no new prompt sections, no structural changes. The `trunc()` per-component caps handle overflow gracefully — if base + overlay exceed a slot's cap, the combined string is clipped at the last comma (preserving complete keyword phrases).

### 6.8 Implementation Guidance

1. **Same template structure as v20.** Overlay content injects through existing `[VARIABLE]` slots. No new prompt sections.
2. **Compact keyword sets (Section 6.4) are mandatory for Firefly.** Full keyword lists are for Midjourney / Leonardo / Gemini only.
3. **Negatives sit inside the existing "Do not include" line.** They don't create a new prompt section — they extend the existing guard phrase. No budget impact on the main prompt body.
4. **`trunc()` handles overflow.** Every variable slot has a per-component char cap. If base + overlay content exceeds the cap, `trunc()` clips at the last comma. No keywords are ever cut mid-word.
5. **Final safety net:** `substring(0, 950)` on the assembled prompt. This only fires if multiple components simultaneously hit their upper bounds — extremely unlikely with compact keyword sets.
6. **Test after every new overlay.** Generate a worst-case prompt (A2 + Track A + longest illustration + overlay active) and verify ≤ 950 chars.

---

## 7. Overlay Pack Spec Template

Every overlay pack follows this structure:

```
OVERLAY PACK: [Name]
APPLIES TO: [List of base categories this overlay can compose with — must be in Section 5 matrix]
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

---

# Overlay Pack 1: Devotional

---

## OVERLAY PACK: Devotional

**Applies to:** Good Morning, Suvichar
**Seasonal:** No — always available

---

### Track Filter

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ❌ | ✅ |

**Blocked:** Track D — playful doodle/cartoon treatment of sacred symbols (Om, temple, diya) feels tonally disrespectful. Devotional content needs visual dignity.

---

### Illustrations — Add (14 items)

**Sacred Symbols & Objects**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-DEV-I01 | Om Symbol | Stylised Om (ॐ) — clean single form, not overly ornate unless Track A. Warm gold or deep saffron tone. | A1, A2 |
| OV-DEV-I02 | Temple Bell | Brass temple bell, traditional rounded shape with clapper visible. Warm metallic tones, slight patina. | A1, A2 |
| OV-DEV-I03 | Incense Stick (Burning) | Single agarbatti in holder, thin smoke trail curling upward in gentle S-curve. Warm amber tones. | A1, A2 |
| OV-DEV-I04 | Rudraksha Mala | Prayer bead strand in gentle curve or coil, individual beads visible. Deep brown with subtle texture. | A1, A2 |
| OV-DEV-I05 | Shankh (Conch Shell) | Sacred conch shell, side view showing spiral. Creamy white with soft pink interior. | A1, A2 |

**Flora & Nature (Devotional)**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-DEV-I06 | Tulsi Plant (Pot) | Sacred tulsi in traditional earthen tulsi vrindavan pot with vermillion marks. Green leaves, terracotta base. | A1, A2 |
| OV-DEV-I07 | Jasmine Garland (Mogra) | String of white mogra flowers, gently curved. Pure white buds against warm background. | A1, A2 |
| OV-DEV-I08 | Banana Leaf with Offerings | Green banana leaf laid flat with small pooja items (kumkum, turmeric, flower petals, rice grains). | A1, A2 |

**Scenes & Settings (devotional atmosphere)**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-DEV-I09 | Temple Silhouette | Hindu temple gopuram silhouette against dawn sky. Clean outline, backlit with golden-orange sky gradient. | A1, A2, B1 |
| OV-DEV-I10 | Praying Hands (Namaste) | Two hands joined in prayer/namaste, warm side-lighting. Not face visible — just hands. | A1, A2, B1 |
| OV-DEV-I11 | Ganga / River at Dawn | Sacred river at dawn, stone ghats in foreground, temple spires in background. Golden reflection on water. | B1 |
| OV-DEV-I12 | Pooja Thali (Still Life) | Brass thali with lit diya, kumkum, rice, marigold flowers, brass bell. Morning light, warm tones. | A1, A2, B1 |
| OV-DEV-I13 | Temple Doorway (Interior) | View through carved temple doorway, warm light streaming in. Stone architecture, not a specific deity. | B1 |
| OV-DEV-I14 | Oil Lamp Row (Lit) | Row of 5–7 brass oil lamps (deepam) lit in a line, warm flame glow, shallow depth of field. | A1, A2, B1 |

---

### Illustrations — Restrict from Base

**From Good Morning (restrict 17 items):**

| Restricted Item | Reason |
|----------------|--------|
| GM-I1-05 Glass of Fresh Orange Juice | Too casual/modern health-trend — not devotional register |
| GM-I1-08 Tender Coconut Water | Beach/tropical casual — undercuts sacred atmosphere |
| GM-I2-08 Rainbow after Morning Rain | Too playful/cheerful for devotional solemnity |
| GM-I3-05 Sunflower Facing Sun | Too bright/cheerful/modern — not temple energy |
| GM-I3-09 Cherry Blossom Branches | Modern/urban/Japanese aesthetic — clashes with Indian devotional |
| GM-I5-04 Book and Chai on Morning Desk | Casual intellectual — not devotional |
| GM-I5-05 Morning Walk on Tree-Lined Path | Casual lifestyle — too secular |
| GM-I5-06 Watering Plants on Balcony | Casual domestic routine — too mundane for sacred |
| GM-I5-07 Family at Morning Breakfast | Dining/casual — wrong mood |
| GM-I6-04 Parrot on Mango Branch | Too playful/bright — undercuts devotional gravity |
| GM-I6-06 Butterflies on Flowers at Dawn | Too light/whimsical for devotional |
| GM-I7-01 Idli-Sambar Plate | Food/breakfast — too mundane for sacred morning |
| GM-I7-02 Poha Bowl with Garnish | Same — mundane food |
| GM-I7-03 Butter Paratha on Rustic Plate | Same — mundane food |
| GM-I7-04 Seasonal Fruit Bowl | Same — mundane food |
| GM-I7-05 Newspaper with Chai | Secular routine — directly contradicts devotional |
| GM-I1-01 Steaming Chai Cup | Daily mundane — undercuts sacred morning atmosphere |

**From Suvichar (restrict 8 items):**

| Restricted Item | Reason |
|----------------|--------|
| SV-I02 Geometric Shards | Angular/aggressive abstract — contradicts devotional softness |
| SV-I04 Splatter / Paint Burst | Dynamic/chaotic energy — contradicts meditative stillness |
| SV-I10 Stormy Sky | Too dark/dramatic — devotional morning is peaceful, not turbulent |
| SV-I20 Trophy / Medal | Achievement/competition — wrong register for devotional |
| SV-I22 Magnifying Glass | Analytical/secular curiosity — not devotional |
| SV-I25 Lightning Bolt | Aggressive energy — contradicts devotional calm |
| SV-I27 Silhouette Arms Raised | Victory/competition pose — sports energy, not devotional |
| SV-I30 Silhouette Running/Sprinting | Athletic/competitive — contradicts meditative stillness |

**Total restrictions:** 17 (GM) + 8 (SV) = 25 items blocked

---

### Motifs & Decor (per allowed track)

**Track A — Shiny Maximal**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Sparkle cluster / confetti | Om with Gold Halo | Gold-foil Om symbol (ॐ) at 15–20mm scale, with concentric radiating halo lines. Embossed/raised feel. High-shine gold (#D4AF37) on rich background. |
| Swap | Butterfly / seasonal accent | Brass Bell Garland | String of 5–7 small brass temple bells connected by gold thread, hung along frame edge. Each bell ~8mm, visible clappers. |
| Add | — | Diya Row (Gold) | 3–5 brass diyas with gold flame accents spaced evenly along frame base. Each flame has tiny sparkle highlight. Ornate base with detailed stand. |

**Track B — Modern Desi**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Geometric accent | Rangoli Om Corner | Om symbol integrated into geometric rangoli quarter-pattern at each frame corner. Clean lines, not ornate — modern geometric interpretation. Saffron + white palette. |
| Swap | Trending/seasonal | Tulsi Pot Accent | Small tulsi vrindavan vignette (~20mm) at bottom corner. Simple earthen pot, green leaves, minimal detail. Warm terracotta tones. |
| Add | — | Ghee Lamp Line | Thin horizontal row of small lit ghee lamps (3–5) at frame base. Modern clean rendering — no ornate detail. Warm amber flame glow. |

**Track C — Minimalist Classy**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Dot / line accent | Minimal Om Line | Om drawn with a single continuous line stroke. Thin (1px visual weight), clean, no fill. Warm grey or muted gold. Placed as subtle corner accent. |
| Swap | Geometric shape | Incense Smoke Trail | Single vertical thin line rising from bottom edge, with 2–3 gentle S-curves suggesting smoke. Barely-there opacity (30–40%). Elegant negative space around it. |

**Track E — Soft & Warm**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Watercolour accent | Watercolour Diya | Soft-edge diya shape in warm ochre/saffron watercolour wash. Flame is a small warm yellow bleed. No hard edges. Feels hand-painted. |
| Swap | Soft floral | Marigold Wash | Loose watercolour marigold garland — 3–4 blooms connected by green wash. Diffused edges, pigment pooling at petal tips. Warm orange-yellow tones. |
| Add | — | Incense Haze (Soft) | Gentle warm-toned haze/smoke wash along frame base. Very subtle (20–30% opacity). Creates a devotional atmosphere layer without being a distinct object. |

---

### Frame Types

**Restrict:** None
**Unlock:** F6 — Temple Arch

| Code | Name | Description | Layout Compatibility |
|------|------|-------------|---------------------|
| F6 | Temple Arch | Curved temple gopuram / mandir arch silhouette as top frame element. Arch curves from top-left to top-right corners, descending to ~20% canvas height at the sides. Bottom edge is straight (no frame). Interior is fully open for text + illustration. Arch thickness varies by Frame Decoration Level: Plain = thin outline only, Simple = outline + small kalash at apex, Detailed = ornate carved arch with miniature temple motifs. | Best: L5 (text below arch), L2 (overlay under arch). Works: L1 (text inside upper arch curve). Avoid: L3, L4 (arch doesn't pair with side-text layouts — creates visual imbalance). |

---

### Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `spiritual, sacred, devotional warmth, temple morning atmosphere, divine glow, sacred golden light` |
| Mood | `reverent, peaceful, prayerful, blessed, meditative, serene, devout` |
| Negatives | `party, nightclub, alcohol, modern urban, neon, loud, aggressive, cartoon, doodle, playful, comic, silly` |
| B1 Scene Context | `temple courtyard at dawn, devotional morning setting, sacred river ghats at sunrise, pooja room with morning light streaming in, incense smoke visible in golden light rays` |

### Prompt Additions — Firefly Compact (≤950 char budget)

| Element | Compact value |
|---------|--------------|
| Atmosphere | `spiritual devotional warmth, temple dawn glow` |
| Mood | `reverent, peaceful, prayerful, blessed` |
| B1 Scene | `temple courtyard at dawn, pooja room morning light` |
| Negatives | *(not in Firefly prompt — no budget impact)* |

---

---

# Overlay Pack 2: Summer

---

## OVERLAY PACK: Summer

**Applies to:** Good Morning, Birthday, Suvichar
**Seasonal:** Yes — April to June

---

### Track Filter

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ✅ | ✅ |

**Blocked:** None — summer's bright, vibrant energy works across all visual styles. A shiny gold mango and a watercolour mango are both valid.

---

### Illustrations — Add (14 items)

**Fruits & Food (Indian Summer)**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-SUM-I01 | Mango (Aam) | Ripe Alphonso mango, whole with one sliced half showing orange flesh. Vibrant yellow-orange skin, green stem. Juicy, saturated colour. | A1, A2 |
| OV-SUM-I02 | Mango Basket / Crate | Woven bamboo basket or wooden crate with 5–7 assorted mangoes. Market-fresh feel, some with leaves attached. Overhead or 3/4 angle. | A1, A2, B1 |
| OV-SUM-I03 | Watermelon Slice | Bright red wedge-shaped slice with black seeds and green rind. Dripping juice detail. Saturated, summer-fresh. | A1, A2 |
| OV-SUM-I04 | Kulfi / Ice Cream | Traditional matka kulfi with pistachio crumble on top, or a bright ice cream stick (orange bar). Frosty condensation on surface. | A1, A2 |
| OV-SUM-I05 | Nimbu Paani (Lemonade) | Tall glass of lemon water with ice cubes, fresh mint sprig, condensation droplets on glass. Yellow-green clarity. Straw optional. | A1, A2, B1 |
| OV-SUM-I06 | Aam Panna Glass | Glass of raw mango drink, pale green colour, garnished with mint. Refreshing, summer-specific Indian drink. | A1, A2 |

**Summer Objects & Accessories**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-SUM-I07 | Hand Fan (Pankha) | Traditional Indian hand-woven palm leaf fan or bamboo fan. Textured, handmade feel. Cream/tan tones. | A1, A2 |
| OV-SUM-I08 | Sunglasses | Bold aviator or wayfarer sunglasses with reflective lenses showing sky/sun. Fun summer accessory, slightly tilted. | A1, A2 |
| OV-SUM-I09 | Matka (Clay Water Pot) | Earthen clay matka with water condensation on surface. Traditional Indian summer water cooler. Terracotta brown, sitting on stand. | A1, A2 |
| OV-SUM-I10 | Straw Hat / Sun Hat | Woven straw sun hat, casual and breezy. Top-down or slightly angled. Tan/natural tones with optional ribbon. | A1, A2 |

**Scenes & Nature (Summer)**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-SUM-I11 | Mango Tree | Laden mango tree branch with hanging fruits and green leaves. Dappled sunlight through canopy. | A2, B1 |
| OV-SUM-I12 | Ceiling Fan / Desert Cooler | Old-style Indian ceiling fan (3-blade, off-white) in motion OR desert cooler with khus curtain. Nostalgic Indian summer interior. | B1 |
| OV-SUM-I13 | Sunny Courtyard | Indian home courtyard in peak summer — bright harsh sunlight, long shadows, tulsi pot, maybe a charpai. Heat-haze optional. | B1 |
| OV-SUM-I14 | Sunflower | Single bright sunflower facing camera. Bold yellow petals, dark brown centre. Summer optimism. | A1, A2 |

---

### Illustrations — Restrict from Base

**From Good Morning (restrict 8 items):**

| Restricted Item | Reason |
|----------------|--------|
| GM-I2-04 Morning Mist over River | Mist implies cool/cold weather — contradicts summer heat |
| GM-I2-07 Foggy Valley with Light Shafts | Fog implies cold/winter morning — wrong season |
| GM-I4-01 Lit Diya with Warm Glow | Indoor flame warmth in already-hot summer feels redundant/wrong |
| GM-I4-04 Incense Stick Smoke | Indoor smoky warmth — summer is about outdoor freshness |
| GM-I5-02 Meditating Figure at Sunrise | Too still/inward — summer energy is outward and active |
| GM-I6-05 Sarus Crane in Misty Field | Misty field = cool weather, contradicts summer |
| GM-I7-03 Butter Paratha on Rustic Plate | Heavy hot food contradicts refreshing summer feel |
| GM-I7-06 Morning Puja Thali | Devotional — too inward for summer's bright energy |

**From Birthday (restrict 4 items):**

| Restricted Item | Reason |
|----------------|--------|
| BD-I13 Diya Cluster | Devotional/indoor — contradicts bright outdoor summer |
| BD-I15 Puja Thali | Devotional — not summer energy |
| BD-I19 Fireworks (Sky) | Night-sky fireworks contradict summer daylight context |
| BD-I28 Blowing Candles (Silhouette) | Dark/indoor intimate moment — contradicts bright summer |

**From Suvichar (restrict 8 items):**

| Restricted Item | Reason |
|----------------|--------|
| SV-I05 Lone Tree (Silhouette) | Barren/melancholic silhouette — too sombre for bright summer |
| SV-I08 Falling Leaves | Autumn imagery — wrong season |
| SV-I09 Desert Dunes | Barren dryness without "fun" framing — too harsh |
| SV-I10 Stormy Sky | Dark/dramatic — contradicts bright summer sky |
| SV-I12 Crescent Moon & Stars | Night imagery undercuts summer brightness |
| SV-I19 Lantern (Glowing) | Indoor warm glow — summer is about outdoor light |
| SV-I28 Silhouette Seated/Meditating | Too still/inward for summer's active energy |
| SV-I29 Silhouette Walking Alone | Too solitary/melancholic for summer's vibrant mood |

**Total restrictions:** 8 (GM) + 4 (BD) + 8 (SV) = 20 items blocked

---

### Motifs & Decor (per track — all 5 allowed)

**Track A — Shiny Maximal**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Seasonal/floral | Gold Mango Cluster | 3–4 mangoes arranged in a triangular cluster with gold leaf accents and tiny gold sparkle highlights. Lush, ornate, maximum saturation. Mangoes have visible texture. |
| Swap | Sparkle accent | Sunburst Medallion | Radiating gold sunburst motif at frame top-centre. 12–16 rays, embossed/raised feel. Central circle could hold track palette's primary colour. |
| Add | — | Watermelon Wedge (Gold-rimmed) | Small watermelon slice motif with gold rind outline as corner accent. Playful but ornate — fits Track A's "more is more" energy. |

**Track B — Modern Desi**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Seasonal | Block-Print Mango Motif | Mango silhouette filled with traditional Indian block-print pattern (small paisleys or dots inside). Saffron + indigo on cream. Repeatable as border pattern. |
| Swap | Floral | Nimbu Slice Corner | Lemon cross-section (half-circle) as geometric corner accent. Clean lines, modern illustration style. Yellow with white pith detail. Sits in frame corners. |
| Add | — | Matka Icon | Small clay pot silhouette with condensation dots. Simple 2-colour modern icon. Warm terracotta tone. |

**Track C — Minimalist Classy**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Dot/line accent | Minimal Sun Arc | Thin quarter-circle arc at frame corner suggesting sun. Single line, ~1px visual weight. Muted gold or warm grey. Maximum negative space around it. |
| Swap | Geometric | Citrus Outline | Single-line lemon/orange cross-section outline. No fill, just the clean circular outline with segment lines. Subtle warm tone. |

**Track D — Artsy Playful**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Doodle | Doodle Mango | Hand-drawn mango with leaf, crayon/marker style. Slightly wobbly outline, scribble colour fill in yellow-orange. Fun and informal. |
| Swap | Sticker | Popsicle Sticker | Puffy ice-lolly sticker (orange bar style), slightly 3D with highlight, playful bright colours. "Summer fun" energy. |
| Add | — | Doodle Sun (Smiling) | Hand-drawn smiling sun with wavy rays. Classic childhood sun drawing — circle face, triangle rays, simple smile. Warm yellow. |

**Track E — Soft & Warm**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Watercolour floral | Watercolour Mango | Soft-edge mango in warm yellow-orange watercolour wash. Pigment pooling at bottom of fruit. Green leaf accent with wet-on-wet bleed. |
| Swap | Soft accent | Pastel Citrus Slice | Gentle lemon half-slice in muted yellow-cream pastel. Soft edges, no hard outlines. Subtle segment lines. Airy and light. |
| Add | — | Sun Glow Wash | Gentle warm-toned radial glow at frame top-centre. Very subtle (15–25% opacity). Creates "warm sunshine" atmosphere without being a distinct object. |

---

### Frame Types

**Restrict:** None
**Unlock:** None

---

### Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `bright Indian summer, warm harsh sunlight, peak daylight, hot season ambience, golden hour warmth, long shadows` |
| Mood | `vibrant, sunny, refreshing, cheerful, high-energy, bright, juicy, alive` |
| Negatives | `cold, snow, winter, fog, overcast, grey, dark, cloudy, sweater, blanket, rain, umbrella, monsoon, frost` |
| B1 Scene Context | `Indian summer setting, bright sunlight casting strong shadows, courtyard or veranda in afternoon heat, mango trees, earthen pots, or summer morning freshness with dew evaporating` |

### Prompt Additions — Firefly Compact (≤950 char budget)

| Element | Compact value |
|---------|--------------|
| Atmosphere | `bright Indian summer, harsh golden sunlight` |
| Mood | `vibrant, sunny, refreshing, cheerful` |
| B1 Scene | `Indian summer courtyard, bright harsh sunlight, mango trees` |
| Negatives | *(not in Firefly prompt — no budget impact)* |

---

---

# Overlay Pack 3: Rain / Monsoon

---

## OVERLAY PACK: Rain / Monsoon

**Applies to:** Good Morning, Suvichar
**Seasonal:** Yes — July to September

---

### Track Filter

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ❌ | ✅ | ✅ | ✅ | ✅ |

**Blocked:** Track A — Shiny Maximal's gold sparkle, high gloss, and ornate energy contradicts monsoon's overcast, muted, cosy mood. Rain is inherently muted and soft — the "maximum shine" lane feels like a visual clash.

---

### Illustrations — Add (15 items)

**Rain Elements**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-RAIN-I01 | Umbrella (Open, Colourful) | Bright open umbrella from above or side angle, raindrops bouncing off. Red, yellow, or multi-colour. Angled casually. | A1, A2 |
| OV-RAIN-I02 | Umbrella (Closed, Minimal) | Closed umbrella leaning against wall or held at side. Clean silhouette. For minimal/classy treatments. | A1, A2 |
| OV-RAIN-I03 | Raindrops on Leaf | Close-up macro: 3–5 clear water droplets on a single green leaf. Sharp focus on drops, soft-focus leaf. Fresh and alive. | A1, A2, B1 |
| OV-RAIN-I04 | Puddle Reflection | Rain puddle on road or stone surface reflecting sky, trees, or temple. Ground-level camera angle. Concentric ripple rings. | A2, B1 |
| OV-RAIN-I05 | Paper Boat | Small white/newspaper paper boat floating in a gentle rainwater stream along a roadside gutter. Childhood nostalgia. | A1, A2 |

**Comfort & Nostalgia (Monsoon rituals)**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-RAIN-I06 | Chai in Rain | Steaming cutting chai glass or cup on a window ledge or balcony railing. Rain-streaked glass behind, blurred street outside. Warm amber tea colour. | A1, A2, B1 |
| OV-RAIN-I07 | Pakora / Bhajiya Plate | Fresh hot onion pakoras or bhajiya on a steel plate or newspaper. Steam rising. Green chutney side. Monsoon comfort food. | A1, A2 |
| OV-RAIN-I08 | Wet Window Pane | Rain streaks running down glass, warm interior light glowing behind. Cosy indoor feel. Blurred warm tones inside, cold grey outside. | A1, A2, B1 |
| OV-RAIN-I09 | Person with Umbrella (Silhouette) | Solo figure walking with umbrella on wet road, seen from behind. Reflection on wet ground. Atmospheric, not portrait. | B1 |

**Nature & Atmosphere (Monsoon landscape)**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-RAIN-I10 | Monsoon Sky (Dramatic) | Heavy cumulus clouds, dark-grey with silver edges. Dramatic cloud formations. Maybe one break of light. No rain visible — just the sky. | B1 |
| OV-RAIN-I11 | Green Field in Rain | Lush green rice paddy or field with rain falling. Overcast light, saturated greens. Distant treeline. Indian rural monsoon. | B1 |
| OV-RAIN-I12 | Frog on Leaf | Small green frog perched on a wet leaf, water droplets around it. Charming monsoon wildlife. Close-up, sharp detail. | A1, A2 |
| OV-RAIN-I13 | Wet Marigold | Single marigold flower with rain droplets on petals. Vivid orange against grey-green background. Monsoon + Indian flower. | A1, A2 |
| OV-RAIN-I14 | Rain on Rooftop | Rain hitting a corrugated tin or tile rooftop. Splashing droplets frozen mid-bounce. Sound-evoking visual. | B1 |
| OV-RAIN-I15 | Peacock (Rain Dance) | Peacock with fanned tail in rain, classic monsoon image. Side view, feathers glistening with water. | A2, B1 |

---

### Illustrations — Restrict from Base

**From Good Morning (restrict 13 items):**

| Restricted Item | Reason |
|----------------|--------|
| GM-I2-01 Sunrise over Green Hills | Clear sky sunrise clashes with overcast monsoon |
| GM-I2-02 Sun Rays through Forest Trees | Sun rays = clear weather, not monsoon |
| GM-I2-05 Sunrise over Ocean Horizon | Clear sky sunrise — contradicts overcast |
| GM-I2-06 Mountain Peak at Golden Hour | Golden hour = clear sky, not monsoon |
| GM-I2-08 Rainbow after Morning Rain | Rainbow = after rain stops — contradicts "in rain" mood |
| GM-I2-09 Dawn Sky Colour Gradient | Clear-sky gradient — monsoon skies are grey |
| GM-I3-05 Sunflower Facing Sun | Implies bright sunny day — not monsoon |
| GM-I5-01 Surya Namaskar Silhouette | Sun salutation outdoors — implies clear sunny sky |
| GM-I5-08 Farmer in Field at Sunrise | Sunny field — contradicts overcast rainy sky |
| GM-I6-01 Bird Flock at Sunrise (V-Formation) | Birds in clear sunrise sky — not monsoon atmosphere |
| GM-I6-06 Butterflies on Flowers at Dawn | Butterflies don't fly in rain — wrong weather |
| GM-I1-05 Glass of Fresh Orange Juice | Summer drink — not monsoon comfort drink |
| GM-I1-08 Tender Coconut Water | Beach/summer tropical — wrong season |

**From Suvichar (restrict 8 items):**

| Restricted Item | Reason |
|----------------|--------|
| SV-I09 Desert Dunes | Desert dryness directly contradicts rain/water context |
| SV-I20 Trophy / Medal | Achievement energy doesn't fit monsoon's contemplative mood |
| SV-I23 Seed / Sapling | Implies dry soil and growth — monsoon is about water, not planting |
| SV-I24 Flame / Fire | Open flame in rain feels contradictory |
| SV-I25 Lightning Bolt | While lightning exists in monsoon, the illustration is "Fire & Drive" style — wrong energy |
| SV-I26 Rising Sun (Graphic) | Bold graphic sun contradicts overcast monsoon sky |
| SV-I27 Silhouette Arms Raised | Victory pose — too energetic for monsoon's contemplative mood |
| SV-I30 Silhouette Running/Sprinting | Athletic energy in rain — contradicts monsoon's cosy/still mood |

**Total restrictions:** 13 (GM) + 8 (SV) = 21 items blocked

---

### Motifs & Decor (per allowed track — no Track A)

**Track B — Modern Desi**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Seasonal | Block-Print Umbrella | Umbrella silhouette filled with traditional block-print pattern (small dots or butis). Indigo + white on cream. Clean modern rendering. |
| Swap | Floral | Monsoon Vine Border | Wet tropical vine with small white flowers (mogra-like) running along frame edge. Dewdrops on leaves. Green + white. |
| Add | — | Raindrop Bead String | Thin vertical string of stylised raindrops (like a bead curtain) at frame edge. Modern, geometric drops. Blue-grey tones. |

**Track C — Minimalist Classy**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Dot accent | Minimal Raindrop Line | Thin vertical line of small raindrop-shaped dots, evenly spaced. Metallic grey or silver. One drop slightly larger at bottom. |
| Swap | Line accent | Rain Streak (Fine) | 3–4 diagonal fine parallel lines (60° angle) suggesting rain. Sparse and elegant. Light grey, thin stroke. |

**Track D — Artsy Playful**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Doodle | Doodle Umbrella | Hand-drawn open umbrella with bouncy raindrop doodles around it. Wobbly outline, crayon colour fill. Cheerful. |
| Swap | Sticker | Paper Boat Sticker | Puffy paper-boat sticker, slightly 3D with shadow, riding a wavy blue line. Playful childhood energy. |
| Add | — | Doodle Cloud (Rainy) | Hand-drawn grey cloud with zigzag rain lines dropping from it. Simple, cheerful, maybe 2–3 clouds at different sizes. |
| Add | — | Frog Doodle | Tiny hand-drawn frog sitting on a lily pad. 2–3 raindrop doodles around it. Charming corner accent. |

**Track E — Soft & Warm**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Watercolour floral | Watercolour Raindrops | 5–7 soft-edge raindrop shapes in blue-grey watercolour wash. Varying sizes, slight overlap. Pigment pooling at bottom of each drop. |
| Swap | Soft accent | Pastel Umbrella | Gentle closed umbrella outline in muted blue-grey pastel. Soft edges, no hard lines. Tilted at casual angle. |
| Add | — | Mist Wash | Light watercolour mist/fog wash along frame base. Very subtle (15–20% opacity), cool grey-blue tones. Creates depth and monsoon atmosphere. |

---

### Frame Types

**Restrict:** None
**Unlock:** None

---

### Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `Indian monsoon atmosphere, overcast sky, soft diffused rain light, rain-washed freshness, petrichor mood, humid green lushness` |
| Mood | `cosy, nostalgic, peaceful, contemplative, refreshing, romantic, warm-inside-while-cold-outside` |
| Negatives | `harsh sunlight, desert, dry, arid, bright blue sky, clear sky, scorching, drought, dust, snow, winter` |
| B1 Scene Context | `monsoon setting in India, rain-washed streets or balcony or window scene, wet reflective surfaces, heavy overcast or dramatic cloud sky, lush saturated green foliage, visible rain or recent rain evidence` |

### Prompt Additions — Firefly Compact (≤950 char budget)

| Element | Compact value |
|---------|--------------|
| Atmosphere | `Indian monsoon, overcast rain light, petrichor` |
| Mood | `cosy, nostalgic, refreshing, contemplative` |
| B1 Scene | `monsoon balcony, rain-washed streets, overcast lush green` |
| Negatives | *(not in Firefly prompt — no budget impact)* |

---

---

# Overlay Pack 4: Cricket / IPL

---

## OVERLAY PACK: Cricket / IPL

**Applies to:** Good Morning, Birthday
**Seasonal:** Yes — April to June (IPL window), also during international test/ODI/T20 series

---

### Track Filter

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ✅ | ❌ |

**Blocked:** Track E — Soft & Warm's pastel watercolour and gentle energy undercuts cricket's adrenaline and competitive fire. Cricket needs visual punch — even minimal (C) works because "minimal + sharp" reads as sleek, but "soft + warm" reads as passive.

---

### Illustrations — Add (15 items)

**Equipment & Gear**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-CRK-I01 | Cricket Bat & Ball | Classic willow bat crossed diagonally with red leather ball. Iconic composition. Bat shows grain texture, ball shows stitched seam. | A1, A2 |
| OV-CRK-I02 | Cricket Ball (Close-up) | Red leather cricket ball isolated, stitched seam prominently visible. Slight scuff marks for authenticity. Rich red (#8B0000). | A1, A2 |
| OV-CRK-I03 | Stumps & Bails | Three wooden stumps with bails balanced on top. Clean side view, pitch-level camera angle. Sunlit wood grain. | A1, A2 |
| OV-CRK-I04 | Cricket Helmet | Batsman's helmet with metal grille, facing front or slight 3/4 angle. Dark navy or green. Protective gear = intensity. | A1, A2 |
| OV-CRK-I05 | Cricket Gloves | Batting gloves, palms up or fist-clenched, ready position. White with coloured accents. Grip detail visible. | A1, A2 |

**Action & Players (Silhouettes)**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-CRK-I06 | Batsman Silhouette (Cover Drive) | Batsman mid-cover-drive, classic textbook shot. Full body silhouette, bat extended, weight forward. Dynamic. | A1, A2, B1 |
| OV-CRK-I07 | Bowler Silhouette (Delivery Stride) | Fast bowler at peak of delivery stride, arm high, back arched. Maximum kinetic energy in pose. | A1, A2, B1 |
| OV-CRK-I08 | Batsman Silhouette (Six — Celebration) | Batsman looking up after hitting a six, bat raised overhead in celebration. Crowd-energy implied. | A1, A2, B1 |
| OV-CRK-I09 | Wicketkeeper (Dive) | Keeper diving sideways to take a catch. Horizontal body, gloves extended. Athletic action. | A2, B1 |

**Celebration & Venue**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-CRK-I10 | Cricket Stadium (Wide) | Floodlit stadium panorama, evening match atmosphere. Packed stands, green pitch centre, bright floodlights. Cinematic. | B1 |
| OV-CRK-I11 | Trophy / Cup | Gold cricket trophy with handles (generic, not branded). Spotlight on trophy, dark background. Aspiration and victory. | A1, A2 |
| OV-CRK-I12 | Six / Boundary Burst | Ball flying over boundary rope with graphic energy burst behind it. Motion lines, impact stars. Comic-book energy for illustrative archetypes. | A1, A2 |
| OV-CRK-I13 | Gully Cricket Scene | Informal street cricket in an Indian lane — bat, makeshift stumps (bricks/sticks), narrow lane, kids playing. Nostalgic Indian cricket. | B1 |
| OV-CRK-I14 | Cricket Pitch (Close-up) | Close-up of pitch with crease line, bat shadow, red ball sitting on good length. Textured grass, chalk line. | B1 |
| OV-CRK-I15 | Scoreboard / Numbers | Abstract scoreboard graphic showing "SIX" or score numbers. Bold typography, stadium-style. Not a real brand. | A1, A2 |

---

### Illustrations — Restrict from Base

**From Good Morning (restrict 17 items — entire Spiritual/Devotional category + calm items):**

| Restricted Item | Reason |
|----------------|--------|
| GM-I4-01 Lit Diya with Warm Glow | Devotional — contradicts sports energy |
| GM-I4-02 OM Symbol with Light Rays | Sacred — wrong register for cricket |
| GM-I4-03 Hands in Namaste | Devotional prayer — contradicts competitive energy |
| GM-I4-04 Incense Stick Smoke | Temple morning — wrong mood |
| GM-I4-05 Tulsi Plant in Brass Pot | Sacred/devotional — not sports |
| GM-I4-06 Temple Bell | Devotional — not sports |
| GM-I4-07 Shankh (Conch Shell) | Sacred — not sports |
| GM-I4-08 Rangoli at Dawn | Festive/devotional — not sports |
| GM-I4-09 Peacock Feather | Divine/Krishna association — not sports |
| GM-I3-02 Lotus in Full Bloom | Meditative/sacred — contradicts competition |
| GM-I3-03 Jasmine Buds (Mogra) | Too delicate/soft for sports energy |
| GM-I3-06 Champa / Frangipani | Temple flower — spiritual, not sports |
| GM-I3-07 Rose Bud with Dew | Romantic/soft — wrong energy |
| GM-I3-08 Petals Floating on Water | Meditative stillness — contradicts sports action |
| GM-I5-02 Meditating Figure at Sunrise | Meditation = opposite of sports energy |
| GM-I6-05 Sarus Crane in Misty Field | Peaceful/poetic — too contemplative |
| GM-I7-06 Morning Puja Thali | Devotional — not sports |

**From Birthday (restrict 7 items):**

| Restricted Item | Reason |
|----------------|--------|
| BD-I11 Marigold Toran (Hanging) | Devotional/festive — not sports |
| BD-I13 Diya Cluster | Devotional — clashes with cricket |
| BD-I14 Rangoli (Floor) | Devotional/festive — not sports |
| BD-I15 Puja Thali | Devotional — not sports |
| BD-I21 Flower Bouquet | Too soft/romantic for sports energy |
| BD-I26 Wish Card / Envelope | Too gentle/intimate for cricket |
| BD-I28 Blowing Candles (Silhouette) | Quiet personal moment — contradicts stadium energy |

**Total restrictions:** 17 (GM) + 7 (BD) = 24 items blocked

---

### Motifs & Decor (per allowed track — no Track E)

**Track A — Shiny Maximal**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Floral/sparkle | Gold Cricket Ball | Metallic gold cricket ball with raised stitch detail. High-shine (#D4AF37), embossed/3D feel. ~15mm scale as repeating corner motif. |
| Swap | Garland/ornate | Stadium Lights Burst | Stylised floodlight burst radiating outward like a star. Gold rays, 12–16 points. Sits at frame top-centre. Stadium energy. |
| Add | — | Bat & Ball Crest | Ornate cricket crest: crossed bat and ball with laurel wreath frame. Gold trophy-style engraving. Heraldic feel. Corner or centre-top placement. |

**Track B — Modern Desi**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Rangoli/geometric | Cricket Ball Rangoli | Cricket ball shape (circle with seam line) integrated into geometric rangoli quarter-pattern at corners. Clean modern lines. Red + white on warm background. |
| Swap | Traditional | Modern Stumps Icon | Clean minimal stumps-and-bails graphic in 2-colour line art. Thin strokes, modern illustration style. Wood-tone or black on cream. |
| Add | — | Boundary Rope Line | Stylised boundary rope running along frame base as a decorative line. Subtle wave pattern. Red or white rope texture. |

**Track C — Minimalist Classy**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Dot/line | Minimal Bat Line | Single continuous thin line forming a cricket bat profile. No fill, just outline. Warm grey or muted red. Elegant corner placement. |
| Swap | Geometric | Ball Seam Arc | Quarter-circle arc mimicking a cricket ball's seam stitch pattern. 6 small V-shapes along the arc. Subtle, barely-there detail. |

**Track D — Artsy Playful**

| Action | Base Motif | → Overlay Motif | Visual Direction |
|--------|-----------|----------------|-----------------|
| Swap | Doodle | Doodle Bat & Ball | Hand-drawn bat and ball with crayon/marker texture. Wobbly outlines, scribble fill. Bat is oversized, ball has visible hand-drawn stitches. Fun. |
| Swap | Sticker | "SIX!" Sticker | Puffy comic-book style "SIX!" text sticker in bold red/yellow. Slightly 3D with drop shadow. Impact stars around it. |
| Add | — | Doodle Stumps (Flying) | Hand-drawn stumps with bails flying off in different directions. Action lines showing impact. Crayon style. Peak cricket drama. |
| Add | — | Cricket Star Burst | Hand-drawn star/explosion burst (like comic "POW!") in bright colours. Used as corner accent for energy. |

---

### Frame Types

**Restrict:** F5 — Arch / Canopy (ornate/traditional arch doesn't match modern sports energy)
**Unlock:** None

---

### Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `cricket match energy, stadium floodlight atmosphere, sporting excitement, Indian cricket fervour, competitive intensity, match-day buzz` |
| Mood | `energetic, competitive, exciting, victorious, spirited, adrenaline, fierce, proud, triumphant` |
| Negatives | `calm, serene, spiritual, devotional, temple, meditation, quiet, peaceful, slow, gentle, soft, pastel, watercolour, muted` |
| B1 Scene Context | `Indian cricket setting, floodlit stadium at evening or bright daytime match, lush green pitch with white crease lines, packed stands with cheering crowd, or nostalgic gully cricket in Indian neighbourhood lane` |

### Prompt Additions — Firefly Compact (≤950 char budget)

| Element | Compact value |
|---------|--------------|
| Atmosphere | `cricket match energy, stadium floodlight buzz` |
| Mood | `energetic, competitive, exciting, proud` |
| B1 Scene | `floodlit cricket stadium evening, green pitch, packed stands` |
| Negatives | *(not in Firefly prompt — no budget impact)* |

---

---

# Appendix A: Decision Framework — Category vs Overlay

When a new content idea comes up, ask one question:

> **Does it have its own greeting text?**

| Answer | Decision | Example |
|--------|---------|---------|
| **Yes** — it has unique hero text that doesn't belong to any existing category | → **New Base Category** | Rath Yatra ("शुभ रथ यात्रा"), Diwali ("शुभ दीपावली"), Eid ("ईद मुबारक"), Holi ("Happy Holi") |
| **No** — it's a flavour/context that modifies an existing greeting | → **Overlay Pack** | Devotional (still "Good Morning"), Cricket (still "Good Morning" or "Happy Birthday"), Rain (still "Good Morning") |

**Secondary check for Overlays:** Does this flavour apply to more than one base category? If yes, it's definitely an overlay — build it once, compose it with multiple bases.

---

# Appendix B: Master Cross-Reference

### Overlay × Base Compatibility (quick reference — see Section 5 for full rationale)

| Overlay | Good Morning | Suvichar | Birthday |
|---------|:---:|:---:|:---:|
| Devotional | ✅ | ✅ | — |
| Summer | ✅ | ✅ | ✅ |
| Rain / Monsoon | ✅ | ✅ | — |
| Cricket / IPL | ✅ | — | ✅ |

### Overlay × Track Compatibility (Master Filter)

| Overlay | A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|---------|:-:|:-:|:-:|:-:|:-:|
| Devotional | ✅ | ✅ | ✅ | ❌ | ✅ |
| Summer | ✅ | ✅ | ✅ | ✅ | ✅ |
| Rain / Monsoon | ❌ | ✅ | ✅ | ✅ | ✅ |
| Cricket / IPL | ✅ | ✅ | ✅ | ✅ | ❌ |

### Illustration Count Summary

| Overlay | Added | Restricted (GM) | Restricted (BD) | Restricted (SV) | Total Restricted |
|---------|:-----:|:---------------:|:---------------:|:---------------:|:----------------:|
| Devotional | 14 | 17 | — | 8 | **25** |
| Summer | 14 | 8 | 4 | 8 | **20** |
| Rain / Monsoon | 15 | 13 | — | 8 | **21** |
| Cricket / IPL | 15 | 17 | 7 | — | **24** |

**Note:** Restrictions are aggressive by design. It's better to hide a borderline item than to let a user create a "Devotional Good Morning" with a parrot or a "Cricket Birthday" with floating petals. The overlay's added illustrations fill the gap — the user never sees a depleted pool.

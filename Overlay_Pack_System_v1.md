# Overlay Pack System — Spec v1
> **Architectural extension to Template_Creation_Framework_v20.md**
> Defines the Overlay Pack layer — a thin, reusable content modifier that sits between a Base Category and the user-facing Occasion picker.

---

## 1. The Three-Layer Architecture

The template system has three layers. Each layer owns specific things and cannot touch what belongs to another layer.

| Layer | What it is | What it owns | Examples |
|-------|-----------|-------------|---------|
| **Framework** | The engine | Archetypes, tracks, layouts, palettes, fonts, render styles, background finishes, prompt builder architecture, wizard flow, density calc, intensity | Template_Creation_Framework_v20.md |
| **Base Category** | The content type — defines hero text | Hero text, full illustration catalogue, full motif set per track, atmosphere & mood keywords, negative terms | Good Morning, Birthday, Suvichar, Diwali, Rath Yatra |
| **Overlay Pack** | A flavour/context modifier — no hero text | Illustration additions & restrictions, motif swaps & additions, frame type restrictions or special unlocks, atmosphere keyword additions, negative term additions | Devotional, Summer, Rain/Monsoon, Cricket |

**Composition rule:** An **Occasion** = Base Category + (optional) Overlay Pack. This is what the user picks from a flat list.

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

An overlay has exactly **three levers** — illustrations, motifs/decor, and frame types. Plus prompt-level keyword additions that follow from these.

### Lever 1 — Illustrations: Restrict Base + Add New

| Action | Mechanic | Example |
|--------|---------|---------|
| **Add** themed illustrations | 5–10 new items added to the base category's pool. Tagged with archetype compatibility (A1, A2, B1) like any illustration. | Devotional adds: Temple Silhouette, Praying Hands, Om Symbol, Incense Stick, Temple Bell |
| **Restrict** base illustrations | Specific base items hidden when this overlay is active. Listed explicitly by ID — not by category. | Cricket on Good Morning might hide "Lotus Flower" and "Candle / Diya" (too serene for sports energy) |

**Result:** User sees `(base pool − restricted items) + overlay items`

Restriction is optional. Most overlays will only add, not restrict. Restrict only when a base item actively clashes with the overlay's energy.

### Lever 2 — Motifs & Decor: Swap + Add per Track

| Action | Mechanic | Example |
|--------|---------|---------|
| **Swap** specific motifs | Replace named base motifs with overlay-specific ones, per track. 1:1 replacement — total motif count per track stays the same. | Devotional on Track A: swap "Sparkle Cluster" → "Om with Gold Halo" |
| **Add** motifs | Add 1–2 extra motifs on top of existing set, per track. Use sparingly — too many motifs crowds the frame. | Rain on Track D: add "Doodle Raindrop Border" alongside existing set |

**How it maps to archetypes:**
- **A1 Frame Decoration:** Swapped/added motifs appear in the Frame Decoration Level options (Plain / Simple / Detailed). Same 3-level system — the motifs themselves change, not the levels.
- **A2 Accent Density:** Swapped/added motifs feed into the density auto-calculator's accent pool. Same density math — different items in the pool.

### Lever 3 — Frame Types: Restrict or Unlock Special

| Action | Mechanic | Example |
|--------|---------|---------|
| **Restrict** | Hide specific frame types (F1–F5) that don't work with this overlay. Hard filter — hidden from UI. | Cricket might restrict F5 (Arch / Canopy) — too ornate for sports energy |
| **Unlock special** | Make a special frame type available ONLY when this overlay is active. Defined as a new F-code (F6+). | Devotional unlocks F6 "Temple Arch" — curved temple gopuram silhouette overhead |

**This lever is optional.** Most overlays will not touch frame types at all. Only use when there's a strong visual reason.

---

## 3. What an Overlay Pack CANNOT Change

Hard rule. An overlay cannot touch anything below this line, regardless of context.

| Element | Owned by | Why untouchable |
|---------|----------|----------------|
| Hero text | Base Category | "Good Morning" stays "Good Morning" — overlay is flavour, not greeting |
| Tracks (A–E) | Framework | Visual style is independent of theme — Devotional can be Shiny Maximal or Minimalist |
| Colour palettes | Track (Framework) | Palette is a track property — devotional in Track C is still minimal palette |
| Font pairings | Track (Framework) | Same |
| Render styles | Track (Framework) | Same — how it's rendered is the track's job |
| Layouts (L1–L6) | Framework | Composition rules are structural, not thematic |
| Archetypes (A1, A2, B1) | Framework | All archetypes remain available — never filtered |
| Illustration size options | Framework / Category | Size is a canvas decision, not a theme decision |
| Background finishes | Framework / Track | Cross-category only — overlay doesn't add finishes |
| Wizard flow / step order | Framework | No new steps added |
| Prompt builder functions | Framework | Same functions, different variable values |
| Density auto-calculation | Framework | Math is the same — pool contents change |
| Intensity controls | Framework | Same |

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

## 5. Overlay Pack Spec Template

Every overlay pack follows this structure:

```
OVERLAY PACK: [Name]
APPLIES TO: [List of base categories this overlay can compose with]
SEASONAL: Yes/No (if Yes, specify active window)

ILLUSTRATIONS
  Add (with archetype tags):
    [ID] [Name] — [Description] — [A1, A2, B1]
    ...
  Restrict from base (by item name — listed per base category):
    [Base Category]: [Item 1], [Item 2], ...

MOTIFS & DECOR (per track)
  Track A — Shiny Maximal:
    Swap: [Base motif] → [Overlay motif + description]
    Add: [New motif + description] (if any)
  Track B — Modern Desi:
    ...
  (repeat for C, D, E)

FRAME TYPES
  Restrict: [F-codes to hide, or "None"]
  Unlock: [Special frame + description, or "None"]

PROMPT ADDITIONS
  Atmosphere: [keywords to append]
  Mood: [keywords to append]
  Negatives: [terms to append]
  B1 Scene Context: [scene description to append]
```

---

---

# Sample Overlay Pack 1: Devotional

---

## OVERLAY PACK: Devotional

**Applies to:** Good Morning, Suvichar
**Seasonal:** No — always available

---

### Illustrations

**Add:**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-DEV-I01 | Temple Silhouette | Hindu temple gopuram silhouette against sky, clean outline | A1, A2, B1 |
| OV-DEV-I02 | Praying Hands (Namaste) | Two hands in prayer / namaste position, warm light | A1, A2, B1 |
| OV-DEV-I03 | Om Symbol | Stylised Om (ॐ) — clean, not overly ornate | A1, A2 |
| OV-DEV-I04 | Incense Stick (Burning) | Single incense stick with smoke trail curling upward | A1, A2 |
| OV-DEV-I05 | Temple Bell | Brass temple bell, traditional shape, warm tones | A1, A2 |
| OV-DEV-I06 | Tulsi Plant (Pot) | Sacred tulsi in traditional pot, courtyard feel | A1, A2 |
| OV-DEV-I07 | Ganga / River at Dawn | Sacred river at dawn, temple ghats in background, golden light | B1 |
| OV-DEV-I08 | Pooja Setup (Still Life) | Thali with diya, kumkum, flowers, bell — morning pooja arrangement | A1, A2, B1 |

**Restrict from base:**

| Base Category | Restricted Items | Reason |
|--------------|-----------------|--------|
| Good Morning | Rainbow | Too playful — clashes with devotional solemnity |
| Suvichar | SV-I02 Geometric Shards, SV-I04 Splatter / Paint Burst, SV-I25 Lightning Bolt | Too aggressive / abstract for devotional mood |

---

### Motifs & Decor (per track)

**Track A — Shiny Maximal**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Sparkle cluster / confetti (varies by base) | Om with Gold Halo | Gold-foil Om symbol with radiating halo, ornate |
| Swap | Butterfly / seasonal (varies by base) | Brass Bell Garland | String of small brass bells along frame edge |
| Add | — | Diya Row (Gold) | Row of lit diyas with gold flame accents along frame base |

**Track B — Modern Desi**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Geometric accent (varies) | Rangoli Om Corner | Om integrated into geometric rangoli corner pattern |
| Swap | Trending/seasonal (varies) | Tulsi Pot Accent | Small tulsi plant vignette at frame corner |
| Add | — | Ghee Lamp Line | Thin row of lit ghee lamps, modern minimal |

**Track C — Minimalist Classy**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Dot / line accent (varies) | Minimal Om Line | Single-stroke Om drawn with one continuous line |
| Swap | Geometric shape (varies) | Incense Smoke Trail | Delicate vertical smoke line, thin and elegant |

**Track D — Artsy Playful**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Doodle accent (varies) | Hand-drawn Diya | Sketchy illustrated diya with wobbly flame |
| Swap | Sticker/stamp (varies) | Doodle Om | Playful hand-drawn Om with crayon/marker texture |
| Add | — | Temple Flag Doodle | Small hand-drawn temple flag (dhwaj) pennant |

**Track E — Soft & Warm**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Watercolour accent (varies) | Watercolour Diya | Soft-edge diya in pastel watercolour wash |
| Swap | Soft floral (varies) | Marigold Wash | Loose watercolour marigold garland, diffused edges |
| Add | — | Incense Haze (Soft) | Gentle smoke haze effect, warm pastel tones |

---

### Frame Types

**Restrict:** None
**Unlock:** F6 — Temple Arch

| Code | Name | Description | Layout compatibility |
|------|------|-------------|---------------------|
| F6 | Temple Arch | Curved temple gopuram / mandir arch silhouette as top frame element. Bottom edge is straight. Interior is open for text + illustration. | Best: L5, L2. Works: L1. Avoid: L3, L4 (arch doesn't pair with side-text). |

---

### Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `spiritual, sacred, devotional warmth, temple morning atmosphere, divine glow` |
| Mood | `reverent, peaceful, prayerful, blessed` |
| Negatives | `party, nightclub, alcohol, modern urban, neon, loud, aggressive` |
| B1 Scene Context | `temple courtyard, devotional morning setting, ghats or sacred river at dawn, pooja room ambience` |

---

---

# Sample Overlay Pack 2: Summer

---

## OVERLAY PACK: Summer

**Applies to:** Good Morning, Birthday, Suvichar
**Seasonal:** Yes — April to June

---

### Illustrations

**Add:**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-SUM-I01 | Mango (Aam) | Ripe Alphonso mango, whole or sliced, vibrant yellow-orange | A1, A2 |
| OV-SUM-I02 | Mango Basket | Woven basket with assorted mangoes, market-fresh feel | A1, A2, B1 |
| OV-SUM-I03 | Kulfi / Ice Cream | Matka kulfi or ice cream stick, frosty surface, summer treat | A1, A2 |
| OV-SUM-I04 | Watermelon Slice | Bright red watermelon wedge with seeds, juicy and fresh | A1, A2 |
| OV-SUM-I05 | Nimbu Paani (Lemonade) | Glass of lemon water with ice, mint sprig, condensation drops | A1, A2, B1 |
| OV-SUM-I06 | Hand Fan (Pankha) | Traditional woven hand fan, Indian summer staple | A1, A2 |
| OV-SUM-I07 | Sunglasses | Bold sunglasses, reflective lenses, fun summer accessory | A1, A2 |
| OV-SUM-I08 | Ceiling Fan / Cooler (Nostalgic) | Old-style ceiling fan or desert cooler — Indian summer nostalgia | B1 |

**Restrict from base:**

| Base Category | Restricted Items | Reason |
|--------------|-----------------|--------|
| Good Morning | Full Moon / Night Sky | Night energy clashes with peak summer heat/daylight context |
| Suvichar | SV-I12 Crescent Moon & Stars | Same — night imagery undercuts summer brightness |

---

### Motifs & Decor (per track)

**Track A — Shiny Maximal**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Seasonal/floral (varies) | Gold Mango Cluster | 3–4 mangoes with gold leaf accents, lush and ornate |
| Add | — | Sun Burst (Shiny) | Radiating gold sunburst motif at frame top-centre |

**Track B — Modern Desi**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Seasonal (varies) | Block-Print Mango Motif | Mango shape in traditional Indian block-print pattern |
| Swap | Floral (varies) | Nimbu Slice Corner | Lemon half-slice as geometric corner accent |

**Track C — Minimalist Classy**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Dot/line accent (varies) | Minimal Sun Arc | Thin quarter-circle sun arc at corner, clean single line |
| Swap | Geometric (varies) | Citrus Outline | Single-line lemon/orange cross-section outline |

**Track D — Artsy Playful**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Doodle (varies) | Doodle Mango | Hand-drawn mango with leaf, crayon/marker style, fun |
| Swap | Sticker (varies) | Popsicle Sticker | Puffy ice-lolly sticker, slightly 3D, playful colours |
| Add | — | Doodle Sun (Smiling) | Hand-drawn smiling sun with wavy rays |

**Track E — Soft & Warm**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Watercolour floral (varies) | Watercolour Mango | Soft-edge mango in warm yellow-orange watercolour wash |
| Swap | Soft accent (varies) | Pastel Citrus Slice | Gentle lemon/orange slice in muted pastel tones |

---

### Frame Types

**Restrict:** None
**Unlock:** None

---

### Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `bright Indian summer, warm sunlight, peak daylight, hot season ambience` |
| Mood | `vibrant, sunny, refreshing, cheerful, high-energy` |
| Negatives | `cold, snow, winter, fog, overcast, grey, dark, cloudy, sweater, blanket` |
| B1 Scene Context | `Indian summer setting, bright harsh sunlight, courtyard or veranda, summer afternoon or early morning coolness` |

---

---

# Sample Overlay Pack 3: Rain / Monsoon

---

## OVERLAY PACK: Rain / Monsoon

**Applies to:** Good Morning, Suvichar
**Seasonal:** Yes — July to September

---

### Illustrations

**Add:**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-RAIN-I01 | Umbrella (Open) | Colourful open umbrella, raindrops bouncing off, angled or overhead | A1, A2 |
| OV-RAIN-I02 | Chai in Rain | Steaming cup of chai on a window ledge, rain-streaked glass behind | A1, A2, B1 |
| OV-RAIN-I03 | Raindrops on Leaf | Close-up water droplets on a green leaf, fresh and sharp | A1, A2, B1 |
| OV-RAIN-I04 | Puddle Reflection | Rain puddle reflecting sky or trees, peaceful ground-level view | A2, B1 |
| OV-RAIN-I05 | Paper Boat | Small paper boat floating in rainwater stream, childhood nostalgia | A1, A2 |
| OV-RAIN-I06 | Monsoon Sky (Dramatic) | Heavy cumulus clouds, dark-grey with silver edges, monsoon drama | B1 |
| OV-RAIN-I07 | Wet Window Pane | Rain streaks on glass, warm interior light behind — cosy indoor | A1, A2, B1 |
| OV-RAIN-I08 | Pakora / Bhajiya Plate | Fresh hot pakoras on plate, steam rising — monsoon comfort food | A1, A2 |
| OV-RAIN-I09 | Frog on Leaf | Small frog perched on wet leaf, monsoon wildlife, charming | A1, A2 |

**Restrict from base:**

| Base Category | Restricted Items | Reason |
|--------------|-----------------|--------|
| Good Morning | Sunrise / Morning Sky, Sunrise over Hills | Clear-sky sunrise clashes with overcast monsoon atmosphere |
| Suvichar | SV-I09 Desert Dunes, SV-I26 Rising Sun (Graphic) | Desert dryness and bold sun contradict rain context |

---

### Motifs & Decor (per track)

**Track A — Shiny Maximal**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Sparkle/sun (varies) | Silver Raindrop Cascade | Metallic silver raindrops cascading along frame edge, ornate |
| Add | — | Cloud & Lightning (Gold) | Stylised gold cloud with lightning accent at frame top |

**Track B — Modern Desi**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Seasonal (varies) | Block-Print Umbrella | Umbrella shape in traditional Indian block-print pattern |
| Swap | Floral (varies) | Monsoon Vine Border | Wet tropical vine with small flowers along frame edge |

**Track C — Minimalist Classy**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Dot accent (varies) | Minimal Raindrop Line | Thin vertical raindrop dots, evenly spaced, metallic grey |
| Swap | Line accent (varies) | Rain Streak (Fine) | Diagonal fine lines suggesting rain, sparse and elegant |

**Track D — Artsy Playful**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Doodle (varies) | Doodle Umbrella | Hand-drawn umbrella with bouncing raindrop doodles |
| Swap | Sticker (varies) | Paper Boat Sticker | Puffy paper-boat sticker, slightly 3D, playful |
| Add | — | Doodle Cloud (Rainy) | Hand-drawn rain cloud with zigzag rain lines |

**Track E — Soft & Warm**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Watercolour floral (varies) | Watercolour Raindrops | Soft-edge raindrops in blue-grey watercolour wash |
| Swap | Soft accent (varies) | Pastel Umbrella | Gentle closed umbrella in muted pastel, soft edges |
| Add | — | Mist Wash | Light watercolour mist/fog wash along frame base |

---

### Frame Types

**Restrict:** None
**Unlock:** None

---

### Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `Indian monsoon atmosphere, overcast sky, soft rain light, rain-washed freshness, petrichor mood` |
| Mood | `cosy, nostalgic, peaceful, contemplative, refreshing, romantic` |
| Negatives | `harsh sunlight, desert, dry, arid, bright blue sky, clear sky, scorching, drought` |
| B1 Scene Context | `monsoon setting in India, rain-washed streets or balcony or window scene, wet surfaces, overcast or dramatic cloud sky, green lush foliage` |

---

---

# Sample Overlay Pack 4: Cricket / IPL

---

## OVERLAY PACK: Cricket / IPL

**Applies to:** Good Morning, Birthday
**Seasonal:** Yes — April to June (IPL window), also during international series

---

### Illustrations

**Add:**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| OV-CRK-I01 | Cricket Bat & Ball | Classic willow bat crossed with red leather ball, iconic composition | A1, A2 |
| OV-CRK-I02 | Stumps & Bails | Three stumps with bails, clean side view, pitch-level angle | A1, A2 |
| OV-CRK-I03 | Cricket Stadium (Wide) | Floodlit stadium panorama, evening match atmosphere, packed stands | B1 |
| OV-CRK-I04 | Cricket Ball (Close-up) | Red leather cricket ball, stitched seam visible, isolated | A1, A2 |
| OV-CRK-I05 | Trophy / Cup | Generic cricket trophy (gold cup with handles), celebration moment | A1, A2 |
| OV-CRK-I06 | Batsman Silhouette (Shot) | Batsman mid-cover-drive silhouette, dynamic action pose | A1, A2, B1 |
| OV-CRK-I07 | Bowler Silhouette (Action) | Fast bowler mid-delivery stride silhouette, high energy | A1, A2, B1 |
| OV-CRK-I08 | Cricket Helmet | Batsman's helmet with grille, facing front, gear focus | A1, A2 |
| OV-CRK-I09 | Six / Boundary Burst | Ball flying over boundary with crowd-energy burst behind it, graphic | A1, A2 |

**Restrict from base:**

| Base Category | Restricted Items | Reason |
|--------------|-----------------|--------|
| Good Morning | Candle / Diya, Lotus Flower | Too serene/devotional — clashes with sports energy |
| Birthday | BD-I13 Diya Cluster, BD-I15 Puja Thali, BD-I28 Blowing Candles (Silhouette) | Devotional items and quiet moments clash with cricket energy |

---

### Motifs & Decor (per track)

**Track A — Shiny Maximal**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Floral/sparkle (varies) | Gold Cricket Ball | Metallic gold cricket ball with shiny stitch detail |
| Swap | Garland/ornate (varies) | Stadium Lights Burst | Stylised floodlight burst radiating outward, gold |
| Add | — | Bat & Ball Crest | Ornate bat-and-ball crest motif, trophy-style, gold frame |

**Track B — Modern Desi**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Rangoli/geometric (varies) | Cricket Ball Rangoli | Cricket ball shape integrated into geometric rangoli pattern |
| Swap | Traditional (varies) | Modern Stumps Icon | Clean minimal stumps-and-bails graphic, modern line art |

**Track C — Minimalist Classy**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Dot/line (varies) | Minimal Bat Line | Single continuous line forming a cricket bat silhouette |
| Swap | Geometric (varies) | Ball Seam Arc | Quarter-circle mimicking a cricket ball's seam stitch |

**Track D — Artsy Playful**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Doodle (varies) | Doodle Bat & Ball | Hand-drawn bat and ball with crayon texture, fun energy |
| Swap | Sticker (varies) | "SIX!" Sticker | Puffy comic-book style "SIX!" text sticker, bold |
| Add | — | Doodle Stumps (Flying) | Hand-drawn stumps with bails flying off, action energy |

**Track E — Soft & Warm**
| Action | Base Motif | → Overlay Motif | Description |
|--------|-----------|----------------|-------------|
| Swap | Watercolour (varies) | Watercolour Cricket Ball | Soft-edge red cricket ball in watercolour wash |
| Swap | Pastel floral (varies) | Pastel Bat Silhouette | Gentle bat outline in muted warm tones |

---

### Frame Types

**Restrict:** F5 — Arch / Canopy (too ornate/traditional for sports energy)
**Unlock:** None

---

### Prompt Additions

| Element | Append value |
|---------|-------------|
| Atmosphere | `cricket match energy, stadium floodlight atmosphere, sporting excitement, Indian cricket fervour` |
| Mood | `energetic, competitive, exciting, victorious, spirited, adrenaline` |
| Negatives | `calm, serene, spiritual, devotional, temple, meditation, quiet, peaceful, slow` |
| B1 Scene Context | `Indian cricket setting, stadium or gully cricket ground, floodlit evening match or bright daytime game, green pitch, cheering crowd atmosphere` |

---

---

# Appendix: Decision Framework — Category vs Overlay

When a new content idea comes up, ask one question:

> **Does it have its own greeting text?**

| Answer | Decision | Example |
|--------|---------|---------|
| **Yes** — it has unique hero text that doesn't belong to any existing category | → **New Base Category** | Rath Yatra ("शुभ रथ यात्रा"), Diwali ("शुभ दीपावली"), Eid ("ईद मुबारक") |
| **No** — it's a flavour/context that modifies an existing greeting | → **Overlay Pack** | Devotional (still "Good Morning"), Cricket (still "Good Morning" or "Happy Birthday"), Rain (still "Good Morning") |

**Secondary check for Overlays:** Does this flavour apply to more than one base category? If yes, it's definitely an overlay — build it once, compose it with multiple bases.

| Overlay | Good Morning | Birthday | Suvichar |
|---------|:---:|:---:|:---:|
| Devotional | ✅ | — | ✅ |
| Summer | ✅ | ✅ | ✅ |
| Rain / Monsoon | ✅ | — | ✅ |
| Cricket / IPL | ✅ | ✅ | — |

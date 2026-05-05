# New Category Packs — 7 Categories (v1)
> **Incremental specs on top of Template_Creation_Framework_v20.md**
> Each category below only covers what CHANGES or is NEW.
> Everything not mentioned (archetypes, layouts, tracks, colour palettes, font pairings, background finishes, render styles, prompt builder architecture) is inherited unchanged from the framework.

---

## How to Read This Document

Each category follows the same structure:

1. **Track Locking** — which of the 5 tracks (A–E) are available
2. **Overlay Compatibility** — which existing overlays (Devotional, Summer, Rain, Cricket) can compose with this category
3. **Hero Text** — the default greeting + language variants
4. **Custom Text Step** — whether the user can edit the hero text (devotional categories only)
5. **Illustration Catalogue** — the themed image pool with archetype tags
6. **Border Motifs per Track** — frame decoration and A2 accent items
7. **Prompt Context** — atmosphere, mood, negatives, B1 scene, Firefly compact strings
8. **Layout Bias** — which layouts work best

**What's inherited unchanged for ALL 7 categories:** 3 archetypes (A1, A2, B1), 6 layouts (L1–L6), wizard flow (Archetype → Track → Layout → Colour → Font → Illustration → Intensity), all colour palettes, all font pairings, all BG finishes, all render styles, density auto-calc, intensity controls, prompt builder architecture, all platform adapters, `trunc()` + 950-char Firefly cap.

---

---

# Category 1: Rath Yatra

---

## 1.1 What This Category Is

Rath Yatra is a festival-first devotional category centred on Lord Jagannath's chariot procession. Visual energy comes from the iconic chariot (rath), the three deities (Jagannath, Balabhadra, Subhadra), vibrant procession energy, and Odia/Puri cultural markers.

**Hero Text:** "शुभ रथ यात्रा" / "Happy Rath Yatra" / "जय जगन्नाथ" (fixed — no user edit)

**Seasonal:** Yes — June/July (Ashadha Shukla Dwitiya, moves yearly)

---

## 1.2 Track Locking

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ❌ | ✅ |

**Blocked: Track D** — Artsy Playful's doodle/cartoon treatment of sacred deities and the chariot feels tonally disrespectful. Same reasoning as the Devotional overlay blocking D. Rath Yatra is a deeply religious event — ornate (A), modern (B), minimal (C), or soft (E) all preserve dignity.

---

## 1.3 Overlay Compatibility

| Overlay | Compatible? | Rationale |
|---------|:-----------:|-----------|
| Devotional | ✅ | Rath Yatra IS devotional — the overlay reinforces the mood (temple arch, sacred motifs). Natural fit. |
| Summer | ✅ | Rath Yatra falls in peak summer/early monsoon. Summer overlays (mango, bright sun) add seasonal context. |
| Rain / Monsoon | ✅ | Often coincides with early monsoon. Rain-washed procession imagery is authentic. |
| Cricket / IPL | — | Sports branding on a sacred festival — jarring mismatch. |

---

## 1.4 Illustration Catalogue — Rath Yatra Pack (22 items)

### Carry-over from Good Morning

| ID | Name | Archetypes | Notes |
|----|------|------------|-------|
| GM-I3-01 | Marigold Garland | A1, A2 | Festive decoration, procession garlands |
| GM-I4-01 | Lit Diya | All | Devotional lamp — procession ritual |
| GM-I3-02 | Lotus in Full Bloom | A1, A2, B1 | Sacred — associated with Jagannath |

### New Illustrations (19 items)

**Chariot & Procession**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| RY-I01 | Rath (Chariot) — Full | Grand decorated wooden chariot with canopy, wheels, and flag. Front or 3/4 view. Bright yellow/red cloth, carved wood. | A1, A2, B1 |
| RY-I02 | Chariot Wheel (Close-up) | Iconic large wooden wheel with spokes and hub detail. Konark-style or Puri-style carved wheel. | A1, A2 |
| RY-I03 | Three Chariots (Procession) | Three chariots in a row — Nandighosa (Jagannath), Taladhwaja (Balabhadra), Darpadalana (Subhadra). Distant view, procession energy. | A2, B1 |
| RY-I04 | Procession Crowd | Aerial or eye-level view of devotees pulling chariot with thick ropes. Dense crowd, festival energy. | B1 |
| RY-I05 | Chariot Rope (Pulling) | Close-up of thick rope being pulled by many hands. Symbolic of collective devotion. | B1 |

**Deities & Sacred**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| RY-I06 | Jagannath Face (Iconic) | Stylised round face of Lord Jagannath — large eyes, no nose, flat mouth. The iconic Puri form. Bold colours — black, white, red, yellow. | A1, A2 |
| RY-I07 | Jagannath-Balabhadra-Subhadra Trio | All three deity faces side by side in the classic arrangement. Stylised Puri art form. | A1, A2 |
| RY-I08 | Sudarshan Chakra | The sacred disc weapon — circular with radiating flame edges. Gold or bright red. | A1, A2 |
| RY-I09 | Neela Chakra (Blue Wheel) | The sacred blue wheel atop Jagannath Temple, Puri. Silhouette against sky. | A1, A2, B1 |

**Temple & Setting**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| RY-I10 | Jagannath Temple (Puri) | The iconic white temple gopuram of Puri Jagannath Mandir. Front view or silhouette against dawn sky. | A1, A2, B1 |
| RY-I11 | Grand Road (Bada Danda) | Wide road of Puri with chariot in the distance, temple spire behind. Festival atmosphere. | B1 |
| RY-I12 | Temple Doorway (Singha Dwara) | Lion Gate entrance of Puri temple. Carved stone, devotional grandeur. | B1 |

**Decorative & Festive**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| RY-I13 | Marigold Toran with Mango Leaves | Festival door decoration — marigold garland with fresh mango leaf strand. | A1, A2 |
| RY-I14 | Coconut & Banana Offering | Whole coconut on banana leaf with flowers, kumkum. Pooja offering set. | A1, A2 |
| RY-I15 | Rath Yatra Flag | Triangular festival flag with Jagannath emblem, fluttering. Bright cloth. | A1, A2 |
| RY-I16 | Conch Shell (Shankh) | Sacred conch shell — blown during procession. White with golden mouth. | A1, A2 |
| RY-I17 | Puri Beach at Sunrise | Golden sunrise over Puri beach with temple silhouette in distance. Serene dawn before the procession. | B1 |
| RY-I18 | Prasad Thali (Mahaprasad) | Plate of Jagannath temple prasad — rice, dal, sabzi on sal leaf. Sacred food. | A1, A2 |
| RY-I19 | Odia Rangoli (Jhoti Chita) | Traditional Odia floor art patterns in white rice paste on red/ochre floor. Geometric, sacred. | A2, B1 |

### Catalogue Summary

| Sub-category | Count |
|-------------|:-----:|
| GM Carry-overs | 3 |
| Chariot & Procession | 5 |
| Deities & Sacred | 4 |
| Temple & Setting | 3 |
| Decorative & Festive | 7 |
| **Total** | **22** |

---

## 1.5 Border Motifs per Track

### Track A — Shiny Maximal
| ID | Motif | Description |
|----|-------|-------------|
| RY-MT-A1 | Gold Chariot Wheel | Ornate gold chariot wheel with spoke detail, embossed metallic feel |
| RY-MT-A2 | Jagannath Face (Gold) | Stylised Jagannath face in gold foil, small scale as repeating motif |
| RY-MT-A3 | Marigold & Mango Leaf Garland | Thick marigold toran with mango leaves, gold sparkle accents |
| RY-MT-A4 | Sudarshan Chakra (Gold) | Sacred disc motif in ornate gold, radiating flame edges |
| RY-MT-A5 | Temple Spire Silhouette | Small Puri temple gopuram outline in gold, repeating along frame top |

### Track B — Modern Desi
| ID | Motif | Description |
|----|-------|-------------|
| RY-MT-B1 | Block-Print Chariot Wheel | Chariot wheel in traditional block-print style, indigo on cream |
| RY-MT-B2 | Jhoti Chita Corner | Odia floor art patterns as geometric quarter-motifs at frame corners |
| RY-MT-B3 | Modern Jagannath Icon | Clean minimal Jagannath face icon, 2-colour, contemporary |
| RY-MT-B4 | Mango Leaf String | Simple string of mango leaves along frame base, modern illustration |
| RY-MT-B5 | Conch Shell (Line Art) | Clean line-art conch shell, modern minimal rendering |

### Track C — Minimalist Classy
| ID | Motif | Description |
|----|-------|-------------|
| RY-MT-C0 | None | No decorative motifs, completely clean |
| RY-MT-C1 | Minimal Wheel Arc | Quarter-circle arc suggesting chariot wheel spoke, single thin line |
| RY-MT-C2 | Single Mango Leaf | One mango leaf outline, no fill, warm grey or muted gold |
| RY-MT-C3 | Dot Mandala (Subtle) | Tiny dot-based mandala at corner, barely visible, sacred geometry |

### Track E — Soft & Warm
| ID | Motif | Description |
|----|-------|-------------|
| RY-MT-E0 | None | No decorative motifs, completely clean |
| RY-MT-E1 | Watercolour Wheel | Soft-edge chariot wheel in warm ochre watercolour wash |
| RY-MT-E2 | Soft Marigold Wash | Loose watercolour marigold blooms, diffused edges, warm orange |
| RY-MT-E3 | Pastel Lotus | Gentle pastel lotus shape, no hard edges, devotional softness |

---

## 1.6 Prompt Context

| Prompt Element | Good Morning | Rath Yatra |
|----------------|-------------|------------|
| Hero text | "Good Morning" | "शुभ रथ यात्रा" / "Happy Rath Yatra" (fixed) |
| Scene atmosphere | `early morning Indian setting` | `Rath Yatra festival procession, Jagannath temple celebration` |
| Scene authenticity | `real Indian morning setting` | `real Rath Yatra celebration in Puri, Odisha` |
| Gem setting context | `early morning in India` | `a Rath Yatra procession or Jagannath temple setting` |
| Light/time context | `natural and time-appropriate for early morning` | `natural and warm, festive daylight or golden hour procession lighting` |
| Style mood word | `morning` | `festival` |
| Category label | Good Morning | Rath Yatra |

**Negative terms (all archetypes):** `funeral, mourning, sad, dark mood, horror, cartoon, doodle, playful, comic, modern urban, neon, nightclub`

**Firefly compact set:**

| Element | Compact value |
|---------|--------------|
| Atmosphere | `Rath Yatra festival, Jagannath procession, sacred celebration` |
| Mood | `devotional, festive, joyful, sacred, grand` |
| B1 Scene | `Puri chariot procession, temple backdrop, festival crowd` |

---

## 1.7 Layout Bias

| Layout | Suitability | Reason |
|--------|:-----------:|--------|
| L5 — Text Bottom | ★ Best | Chariot/temple fills top, greeting anchors at base |
| L2 — Overlay / Text Centre | ★ Best | Procession scene as full background with centred text |
| L1 — Text Top | ✓ Works | Greeting at top, chariot illustration below |
| L6 — Text Centre (frame) | ✓ Works | Strong for A1 — ornate frame with sacred motifs |
| L3 / L4 — Text Left / Right | ✓ Works | Chariot and deity illustrations have strong focal points |

---

---

# Category 2: Vat Savitri

---

## 2.1 What This Category Is

Vat Savitri (also Vat Purnima) celebrates the devotion of Savitri to her husband Satyavan. Married women tie threads around a banyan (vat) tree and pray for their husband's long life. Visual energy comes from the sacred banyan tree, red/green sindoor-bangles-mangalsutra imagery, and the Savitri-Satyavan legend.

**Hero Text:** "वट सावित्री व्रत की शुभकामनाएं" / "Happy Vat Savitri" / "सुहाग का त्योहार" (fixed — no user edit)

**Seasonal:** Yes — May/June (Jyeshtha Amavasya / Purnima, moves yearly)

---

## 2.2 Track Locking

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ❌ | ✅ |

**Blocked: Track D** — Playful doodle/cartoon treatment of a sacred married-women's vrat is tonally disrespectful. This is a solemn vow of devotion — ornate (A), modern (B), minimal (C), or soft (E) all work.

---

## 2.3 Overlay Compatibility

| Overlay | Compatible? | Rationale |
|---------|:-----------:|-----------|
| Devotional | ✅ | Vat Savitri IS devotional — temple, prayer, sacred thread. Natural fit. |
| Summer | ✅ | Falls in peak summer (May/June). Summer context (heat, mango, bright sun) adds seasonal feel. |
| Rain / Monsoon | — | Vat Savitri is pre-monsoon. Rainy imagery contradicts the dry summer setting. |
| Cricket / IPL | — | Sports branding on a sacred women's vrat — completely wrong register. |

---

## 2.4 Illustration Catalogue — Vat Savitri Pack (20 items)

### Carry-over from Good Morning

| ID | Name | Archetypes | Notes |
|----|------|------------|-------|
| GM-I3-01 | Marigold Garland | A1, A2 | Pooja decoration |
| GM-I4-01 | Lit Diya | All | Sacred lamp |
| GM-I3-02 | Lotus in Full Bloom | A1, A2, B1 | Purity, devotion |

### New Illustrations (17 items)

**Sacred Tree & Ritual**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| VS-I01 | Banyan Tree (Vat Vriksha) | Majestic banyan tree with aerial roots, thick trunk, wide canopy. Sacred red thread tied around trunk. | A1, A2, B1 |
| VS-I02 | Thread-Tying Ritual | Woman's hands tying sacred red/yellow thread (mauli) around banyan trunk. Close-up, warm light. | B1 |
| VS-I03 | Banyan Tree (Silhouette) | Banyan silhouette against dawn or dusk sky. Grand canopy spread, iconic shape. | A1, A2, B1 |
| VS-I04 | Sacred Thread (Mauli) | Coiled red-yellow sacred thread with turmeric and kumkum marks. Close-up, warm tones. | A1, A2 |
| VS-I05 | Pooja Thali (Vat Savitri) | Brass thali with kumkum, turmeric, rice, mauli thread, flowers, and small diya. Morning pooja set. | A1, A2, B1 |

**Suhag Symbols (Married Women)**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| VS-I06 | Red Bangles | Stack of red glass bangles (chooda), bright crimson, stacked on wrist or arranged in circle. | A1, A2 |
| VS-I07 | Sindoor Box (Open) | Small ornate sindoor container, open showing bright vermillion powder. Gold/brass box. | A1, A2 |
| VS-I08 | Mangalsutra | Black bead and gold mangalsutra necklace, laid on silk cloth or worn. Sacred married symbol. | A1, A2 |
| VS-I09 | Mehendi Hands | Woman's hands with henna/mehendi design, palms up. Festive, bridal energy. | A1, A2, B1 |
| VS-I10 | Toe Rings (Bichiya) | Silver toe rings on feet with alta (red dye). Traditional married woman's adornment. | A1, A2 |

**Devotional & Atmosphere**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| VS-I11 | Savitri-Satyavan (Illustration) | Stylised illustration of Savitri holding Satyavan, banyan tree behind. Mythological art style. | A1, A2 |
| VS-I12 | Banyan Leaf (Close-up) | Single large heart-shaped banyan leaf with visible veins. Sacred, natural. | A1, A2 |
| VS-I13 | Women at Banyan Tree | Group of women in red/green sarees performing parikrama around banyan tree. Festival setting. | B1 |
| VS-I14 | Incense & Flowers at Tree Base | Agarbatti, flowers, and kumkum arranged at base of banyan trunk. Devotional offering. | A1, A2, B1 |
| VS-I15 | Red & Green Saree Drape | Draped red/green fabric (saree pallu) with gold border. Suhag colour — festive, married. | A1, A2 |
| VS-I16 | Coconut & Banana Offering | Whole coconut on banana leaf with flowers and turmeric. Vrat offering. | A1, A2 |
| VS-I17 | Turmeric & Kumkum | Small bowls of bright yellow turmeric and red kumkum powder side by side. | A1, A2 |

### Catalogue Summary

| Sub-category | Count |
|-------------|:-----:|
| GM Carry-overs | 3 |
| Sacred Tree & Ritual | 5 |
| Suhag Symbols | 5 |
| Devotional & Atmosphere | 7 |
| **Total** | **20** |

---

## 2.5 Border Motifs per Track

### Track A — Shiny Maximal
| ID | Motif | Description |
|----|-------|-------------|
| VS-MT-A1 | Gold Banyan Leaf | Ornate gold banyan leaf with vein detail, embossed metallic feel |
| VS-MT-A2 | Red Bangle Cluster | Stack of shiny red/gold bangles as repeating frame accent |
| VS-MT-A3 | Mauli Thread Garland | Sacred red-yellow thread woven along frame edge with gold knots |
| VS-MT-A4 | Gold Sindoor Dot | Small round kumkum/sindoor dot motifs in gold, scattered like bindis |
| VS-MT-A5 | Marigold & Mango Leaf Toran | Festival toran along frame top, gold sparkle accents |

### Track B — Modern Desi
| ID | Motif | Description |
|----|-------|-------------|
| VS-MT-B1 | Block-Print Banyan Leaf | Banyan leaf in traditional block-print, saffron/indigo on cream |
| VS-MT-B2 | Rangoli Vat Corner | Quarter-rangoli at frame corners with banyan leaf motif, geometric |
| VS-MT-B3 | Modern Bangle Icon | Clean minimal bangle circle in 2-colour line art |
| VS-MT-B4 | Mehendi Pattern Strip | Thin strip of henna-style pattern along frame base |
| VS-MT-B5 | Mango Leaf String | Simple mango leaf string, modern illustration |

### Track C — Minimalist Classy
| ID | Motif | Description |
|----|-------|-------------|
| VS-MT-C0 | None | No decorative motifs, completely clean |
| VS-MT-C1 | Minimal Leaf Outline | Single banyan leaf drawn with one continuous line, no fill |
| VS-MT-C2 | Thin Thread Line | Single fine red-gold line along frame edge, suggesting sacred thread |
| VS-MT-C3 | Dot Bindi Accent | One or two small dots at corner, minimal sindoor reference |

### Track E — Soft & Warm
| ID | Motif | Description |
|----|-------|-------------|
| VS-MT-E0 | None | No decorative motifs, completely clean |
| VS-MT-E1 | Watercolour Banyan Leaf | Soft-edge leaf in warm green watercolour wash |
| VS-MT-E2 | Pastel Bangles | Gentle pastel bangle outlines, no hard edges |
| VS-MT-E3 | Soft Marigold Wash | Loose watercolour marigold, warm orange bleed |

---

## 2.6 Prompt Context

| Prompt Element | Good Morning | Vat Savitri |
|----------------|-------------|-------------|
| Hero text | "Good Morning" | "वट सावित्री व्रत की शुभकामनाएं" (fixed) |
| Scene atmosphere | `early morning Indian setting` | `Vat Savitri vrat celebration, sacred banyan tree ritual` |
| Scene authenticity | `real Indian morning setting` | `real Indian Vat Savitri celebration, married women's festival` |
| Gem setting context | `early morning in India` | `a Vat Savitri vrat scene with banyan tree and pooja` |
| Light/time context | `natural and time-appropriate for early morning` | `natural warm morning light, devotional and festive` |
| Style mood word | `morning` | `devotional` |
| Category label | Good Morning | Vat Savitri |

**Negative terms:** `funeral, mourning, dark mood, horror, cartoon, doodle, playful, comic, modern urban, neon, nightclub, widow, white saree, barren`

**Firefly compact set:**

| Element | Compact value |
|---------|--------------|
| Atmosphere | `Vat Savitri vrat, sacred banyan tree, suhag festival` |
| Mood | `devotional, auspicious, blessed, warm, sacred` |
| B1 Scene | `banyan tree with thread, women in red saree, pooja setting` |

---

## 2.7 Layout Bias

| Layout | Suitability | Reason |
|--------|:-----------:|--------|
| L5 — Text Bottom | ★ Best | Banyan tree fills top, greeting at base — classic card |
| L2 — Overlay / Text Centre | ★ Best | Tree scene as full background with centred text overlay |
| L6 — Text Centre (frame) | ✓ Works | Ornate frame with suhag motifs, centred greeting |
| L1 — Text Top | ✓ Works | Greeting at top, tree/ritual illustration below |
| L3 / L4 — Text Left / Right | ~ With Care | Banyan tree is wide — side layouts need small illustration size |

---

---

# Category 3: Father's Day

---

## 3.1 What This Category Is

Father's Day is a warm celebration category honouring fathers and father figures. Visual energy is emotional — father-child bonds, personal objects (watch, shoes, tie), and heartfelt warmth. NOT a religious event — universal, cross-cultural.

**Hero Text:** "Happy Father's Day" / "पापा, आपको सलाम" / "पिता दिवस की शुभकामनाएं" (fixed — no user edit)

**Seasonal:** Yes — Third Sunday of June

---

## 3.2 Track Locking

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ✅ | ✅ |

**Blocked: None** — Father's Day works across all tracks. Shiny (A) for grand celebration, Modern (B) for editorial, Minimal (C) for classy, Playful (D) for fun dad-kid energy, Soft (E) for emotional warmth. All valid.

---

## 3.3 Overlay Compatibility

| Overlay | Compatible? | Rationale |
|---------|:-----------:|-----------|
| Devotional | — | Father's Day is secular/emotional, not devotional. Temple/prayer motifs clash with the personal celebration mood. |
| Summer | ✅ | Father's Day is in June (peak summer). Summer overlay adds seasonal context naturally. |
| Rain / Monsoon | — | June is pre-monsoon in most of India. Overcast rain mood dampens Father's Day warmth. |
| Cricket / IPL | ✅ | "Cricket with Dad" is a powerful Indian cultural image. Father-son cricket in the park is nostalgic and warm. |

---

## 3.4 Illustration Catalogue — Father's Day Pack (24 items)

### Carry-over from Good Morning

| ID | Name | Archetypes | Notes |
|----|------|------------|-------|
| GM-I1-01 | Steaming Chai Cup | All | "Chai with Dad" — universal Indian moment |
| GM-I6-01 | Bird Flock at Sunrise | B1, A2 | Freedom, guidance metaphor |

### New Illustrations (22 items)

**Father-Child Moments**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| FD-I01 | Father & Child (Silhouette) | Father holding child's hand, walking, backlit silhouette against sunset/dawn. Universal, no face. | A1, A2, B1 |
| FD-I02 | Father Lifting Child | Dad lifting small child overhead, joyful motion. Silhouette or back-view. | B1 |
| FD-I03 | Father & Child on Shoulders | Child sitting on father's shoulders, both looking forward. Back view, warm lighting. | B1 |
| FD-I04 | Father & Daughter | Father and young daughter, hand-holding or reading together. Warm, intimate. | B1 |
| FD-I05 | Father Teaching (Cycle/Cricket) | Dad teaching child to ride bicycle or play cricket. Indian outdoor setting. | B1 |
| FD-I06 | Old Hands Holding Young Hands | Close-up of weathered father's hands holding a child's small hands. Emotional, textural. | A1, A2, B1 |

**Dad's Objects & Symbols**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| FD-I07 | Wristwatch (Classic) | Classic leather-strap analogue wristwatch. Dad's timepiece — heritage, reliability. | A1, A2 |
| FD-I08 | Spectacles / Reading Glasses | Wire-frame or classic reading glasses, folded or slightly open. Wisdom, care. | A1, A2 |
| FD-I09 | Necktie | Neatly tied or loosely draped necktie. Professional dad, provider. Warm tones. | A1, A2 |
| FD-I10 | Shoes (Pair) | Father's large shoes beside tiny child's shoes. Scale contrast — emotional. | A1, A2, B1 |
| FD-I11 | Briefcase / Bag | Classic leather briefcase or office bag. Provider symbol. | A1, A2 |
| FD-I12 | Toolbox / Spanner | Simple toolbox or spanner — "Dad fixes everything." Practical love. | A1, A2 |
| FD-I13 | Newspaper & Chai | Newspaper folded with chai cup beside it. Classic Indian dad morning ritual. | A1, A2, B1 |
| FD-I14 | Cricket Bat (Old / Worn) | Well-used cricket bat, tape on handle. Nostalgic, passed down. | A1, A2 |

**Emotional & Atmospheric**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| FD-I15 | Trophy / #1 Dad | "Best Dad" trophy or #1 badge. Playful, celebratory. | A1, A2 |
| FD-I16 | Heart (Simple) | Clean heart shape — standalone or in hands. Universal love. | A1, A2 |
| FD-I17 | Family Tree (Simple) | Stylised tree with roots (father) and branches (children). Growth metaphor. | A1, A2 |
| FD-I18 | Star / Shield | Star or shield emblem — "Dad is my hero." Protective, strong. | A1, A2 |
| FD-I19 | Moustache (Fun) | Classic moustache icon — fun, playful dad symbol. Works for Track D especially. | A1, A2 |
| FD-I20 | Crown (King Dad) | Simple crown — "King of our house." Playful celebration. | A1, A2 |
| FD-I21 | Garden / Plant in Pot | Small potted plant — nurturing, patient growth. Dad as gardener of the family. | A1, A2 |
| FD-I22 | Sunset / Park Bench | Park bench at sunset — peaceful, reflective father-figure moment. | B1 |

### Catalogue Summary

| Sub-category | Count |
|-------------|:-----:|
| GM Carry-overs | 2 |
| Father-Child Moments | 6 |
| Dad's Objects & Symbols | 8 |
| Emotional & Atmospheric | 8 |
| **Total** | **24** |

---

## 3.5 Border Motifs per Track

### Track A — Shiny Maximal
| ID | Motif | Description |
|----|-------|-------------|
| FD-MT-A1 | Gold Crown | Small ornate gold crown motifs, repeating as corner accents |
| FD-MT-A2 | Gold Star Cluster | Scattered 5-pointed gold stars with sparkle highlights |
| FD-MT-A3 | Ornate Heart | Gold-foil heart with decorative scrollwork, embossed feel |
| FD-MT-A4 | Trophy Accent | Small golden trophy/cup motif at frame corners |
| FD-MT-A5 | Confetti & Sparkle | Celebration confetti with gold sparkle, festive frame energy |

### Track B — Modern Desi
| ID | Motif | Description |
|----|-------|-------------|
| FD-MT-B1 | Block-Print Heart | Heart shape with traditional block-print fill pattern |
| FD-MT-B2 | Modern Moustache Icon | Clean 2-colour moustache icon, playful but restrained |
| FD-MT-B3 | Tie Stripe Pattern | Diagonal tie-stripe pattern as border accent, modern |
| FD-MT-B4 | Simple Star Accent | Clean star shapes at frame corners, warm tones |

### Track C — Minimalist Classy
| ID | Motif | Description |
|----|-------|-------------|
| FD-MT-C0 | None | No decorative motifs, completely clean |
| FD-MT-C1 | Minimal Heart Line | Heart drawn with single continuous line, thin stroke |
| FD-MT-C2 | Thin Star Outline | Single star outline at corner, barely-there gold |
| FD-MT-C3 | Dot Trail | Minimal dot trail suggesting sparkle, muted gold |

### Track D — Artsy Playful
| ID | Motif | Description |
|----|-------|-------------|
| FD-MT-D1 | Doodle Heart | Hand-drawn wobbly heart, crayon style, bright colour |
| FD-MT-D2 | Doodle Crown | Hand-drawn crown with uneven points, playful "King Dad" |
| FD-MT-D3 | Doodle Star Burst | Hand-drawn stars with radiating lines, fun scribble style |
| FD-MT-D4 | Sticker Moustache | Puffy 3D moustache sticker, slightly tilted, fun |
| FD-MT-D5 | Doodle Trophy | Hand-drawn "#1 Dad" trophy, wobbly outlines |

### Track E — Soft & Warm
| ID | Motif | Description |
|----|-------|-------------|
| FD-MT-E0 | None | No decorative motifs, completely clean |
| FD-MT-E1 | Watercolour Heart | Soft-edge heart in warm rose/blush watercolour wash |
| FD-MT-E2 | Pastel Star | Gentle pastel star shape, no hard edges |
| FD-MT-E3 | Soft Leaf Wreath | Delicate botanical wreath arc, watercolour, framing text |

---

## 3.6 Prompt Context

| Prompt Element | Good Morning | Father's Day |
|----------------|-------------|--------------|
| Hero text | "Good Morning" | "Happy Father's Day" (fixed) |
| Scene atmosphere | `early morning Indian setting` | `Father's Day celebration, warm emotional family setting` |
| Scene authenticity | `real Indian morning setting` | `real, warm Indian family moment, father-child bond` |
| Gem setting context | `early morning in India` | `a warm Father's Day scene — home, park, or family setting` |
| Light/time context | `natural and time-appropriate for early morning` | `natural warm golden light, emotional and intimate` |
| Style mood word | `morning` | `family` |
| Category label | Good Morning | Father's Day |

**Negative terms:** `funeral, mourning, sad, dark mood, horror, lonely, abandoned, cold, harsh, angry, violent, broken`

**Firefly compact set:**

| Element | Compact value |
|---------|--------------|
| Atmosphere | `Father's Day warmth, family bond, proud celebration` |
| Mood | `warm, proud, loving, nostalgic, grateful` |
| B1 Scene | `father and child moment, warm golden home or park` |

---

## 3.7 Layout Bias

| Layout | Suitability | Reason |
|--------|:-----------:|--------|
| L5 — Text Bottom | ★ Best | Father-child illustration on top, greeting anchors below |
| L2 — Overlay / Text Centre | ★ Best | Emotional photo scene with centred overlay text |
| L1 — Text Top | ✓ Works | Short greeting at top, illustration below |
| L6 — Text Centre (frame) | ✓ Works | Frame with centred greeting, corner objects (watch, shoes) |
| L3 / L4 — Text Left / Right | ✓ Works | Father-child silhouettes have clear vertical focal points |

---

---

# Category 4: Devotional — Shivji

---

## 4.1 What This Category Is

Shivji (Lord Shiva) devotional category for daily Shiva-specific greetings, Sawan/Shravan, Maha Shivratri, and Shiv bhakti. Visual energy comes from Shiva's iconic symbols — trishul, damru, Nandi, Ganga, third eye, blue skin, Kailash.

**Hero Text (pre-filled, editable):** "ॐ नमः शिवाय" / "हर हर महादेव" / "Om Namah Shivaya"

User sees this pre-filled in a Custom Text step at the end of the wizard. They can keep it or type their own Shiv-bhakti text.

**Seasonal:** No — always available (peak during Sawan/Shravan July-August and Maha Shivratri)

---

## 4.2 Track Locking

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ❌ | ✅ |

**Blocked: Track D** — Playful doodle/cartoon treatment of Mahadev is disrespectful. Shiva imagery demands dignity — ornate temple art (A), modern restrained (B), minimal sacred (C), or soft devotional (E).

---

## 4.3 Overlay Compatibility

| Overlay | Compatible? | Rationale |
|---------|:-----------:|-----------|
| Devotional | ✅ | Reinforces sacred mood. Generic devotional motifs (Om, diya, temple arch) complement Shiva-specific content. |
| Summer | — | Summer's bright cheerful energy doesn't match Shiva's intense/meditative aesthetic. |
| Rain / Monsoon | ✅ | Sawan (monsoon) is Shiva's sacred month. Rain-washed temple, monsoon Kailash — deeply authentic. |
| Cricket / IPL | — | Sports on Mahadev imagery — completely wrong register. |

---

## 4.4 Wizard Flow — One Change

Same as Good Morning + one addition at the end:

`Archetype → Track → Layout → Colour → Font → Illustration → Intensity → **Custom Text** ✎`

The Custom Text step shows the pre-filled hero text. User can keep it or type their own.

---

## 4.5 Illustration Catalogue — Shivji Pack (22 items)

### Carry-over from Good Morning

| ID | Name | Archetypes | Notes |
|----|------|------------|-------|
| GM-I3-02 | Lotus in Full Bloom | A1, A2, B1 | Sacred — associated with meditation |
| GM-I4-01 | Lit Diya | All | Shiva pooja lamp |

### New Illustrations (20 items)

**Shiva — Iconic Forms**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| SH-I01 | Shiva Lingam | Smooth black/grey Shiva lingam with bilva leaves and flowers on top. Water drops (abhishek). Warm stone texture. | A1, A2, B1 |
| SH-I02 | Trishul (Trident) | Shiva's trident, vertical, with damru drum attached at shaft. Iron/silver metallic, powerful. | A1, A2 |
| SH-I03 | Damru (Drum) | Small hourglass-shaped drum with string tassels. Shiva's instrument. Warm wood tones. | A1, A2 |
| SH-I04 | Nandi (Bull) | Sacred bull Nandi in seated position, facing forward. Stone carved or naturalistic. Serene, strong. | A1, A2, B1 |
| SH-I05 | Third Eye (Stylised) | Vertical third eye with radiating energy. Can be standalone sacred symbol. Warm golden/saffron glow. | A1, A2 |
| SH-I06 | Rudraksha Mala | Rudraksha prayer beads in gentle coil or draped. Deep brown beads, visible texture. | A1, A2 |
| SH-I07 | Crescent Moon | Thin crescent moon (Shiva's head ornament). Silver-white against dark or warm sky. | A1, A2 |
| SH-I08 | Snake (Vasuki) | Sacred cobra coiled or hooded, sitting on Shiva lingam or standalone. Mythical, not threatening. | A1, A2 |

**Shiva — Scenes & Settings**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| SH-I09 | Mount Kailash | Snow-capped Kailash peak against blue or dawn sky. Sacred mountain, majestic. | A2, B1 |
| SH-I10 | Ganga Flowing | River Ganga flowing from mountain/rocks, white water, lush green banks. Sacred river. | B1 |
| SH-I11 | Shiva Temple (Silhouette) | Temple dedicated to Shiva — gopuram silhouette against dawn sky, with trishul flag on top. | A1, A2, B1 |
| SH-I12 | Meditation Cave | Rocky cave entrance with soft light inside, Himalayan setting. Shiva's meditation space. | B1 |
| SH-I13 | Bel / Bilva Tree | Sacred bilva tree with its three-leaf clusters. Shiva's favourite tree. Green, natural. | A1, A2 |
| SH-I14 | Burning Pyre / Sacred Fire | Sacred dhuni / fire with rising smoke. Shiva as the ascetic. Warm amber tones. | A1, A2, B1 |

**Pooja & Devotional**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| SH-I15 | Bilva Leaves on Lingam | Three-leaf bilva clusters placed atop a Shiva lingam. Close-up, devotional act. | A1, A2 |
| SH-I16 | Abhishek (Water Pour) | Water or milk being poured over Shiva lingam from brass vessel. Ritual, sacred. | A1, A2, B1 |
| SH-I17 | Shiva Pooja Thali | Brass thali with bilva leaves, flowers, kumkum, vibhuti, diya, water vessel. | A1, A2 |
| SH-I18 | Vibhuti (Ash Lines) | Three horizontal ash lines (tripundra) — Shiva's forehead mark. Can be standalone symbol. | A1, A2 |
| SH-I19 | Kanwar (Water Pot on Pole) | Decorated kanwar — bamboo pole with water pots hung on either side. Sawan pilgrimage symbol. | A1, A2 |
| SH-I20 | Ganga Aarti | Row of diyas floating on river water at dusk. Ganga aarti scene, sacred, warm glow. | B1 |

### Catalogue Summary

| Sub-category | Count |
|-------------|:-----:|
| GM Carry-overs | 2 |
| Shiva — Iconic Forms | 8 |
| Shiva — Scenes & Settings | 6 |
| Pooja & Devotional | 6 |
| **Total** | **22** |

---

## 4.6 Border Motifs per Track

### Track A — Shiny Maximal
| ID | Motif | Description |
|----|-------|-------------|
| SH-MT-A1 | Gold Trishul | Ornate gold trident motif, embossed/raised, repeating at frame top |
| SH-MT-A2 | Damru with Gold Bells | Small damru drums with tiny gold bells, frame corner accents |
| SH-MT-A3 | Rudraksha String | Rudraksha bead garland running along frame edge, gold thread |
| SH-MT-A4 | Snake (Ornate) | Stylised ornate cobra in gold, coiled at frame corners |
| SH-MT-A5 | Om with Trishul Halo | ॐ symbol with trishul radiating behind, gold foil |

### Track B — Modern Desi
| ID | Motif | Description |
|----|-------|-------------|
| SH-MT-B1 | Block-Print Trishul | Trishul in block-print pattern fill, indigo/saffron on cream |
| SH-MT-B2 | Modern Damru Icon | Clean 2-colour damru icon, geometric modern rendering |
| SH-MT-B3 | Bilva Leaf Trio | Three-leaf bilva cluster, clean modern illustration |
| SH-MT-B4 | Crescent Moon (Line) | Thin crescent moon, modern clean rendering, silver-gold |

### Track C — Minimalist Classy
| ID | Motif | Description |
|----|-------|-------------|
| SH-MT-C0 | None | No decorative motifs, completely clean |
| SH-MT-C1 | Minimal Trishul Line | Trishul drawn with single continuous line, thin stroke |
| SH-MT-C2 | Dot Tripundra | Three subtle horizontal dots suggesting Shiva's ash lines |

### Track E — Soft & Warm
| ID | Motif | Description |
|----|-------|-------------|
| SH-MT-E0 | None | No decorative motifs, completely clean |
| SH-MT-E1 | Watercolour Trishul | Soft-edge trishul in warm saffron watercolour wash |
| SH-MT-E2 | Pastel Bilva Leaf | Gentle pastel bilva three-leaf, soft green wash |
| SH-MT-E3 | Soft Rudraksha Wash | Watercolour rudraksha beads, warm brown, diffused edges |

---

## 4.6 Prompt Context

| Prompt Element | Good Morning | Shivji |
|----------------|-------------|--------|
| Hero text | "Good Morning" | User-editable (default: "ॐ नमः शिवाय") |
| Scene atmosphere | `early morning Indian setting` | `Shiva devotional setting, sacred Mahadev worship atmosphere` |
| Scene authenticity | `real Indian morning setting` | `real Shiva temple or Himalayan sacred setting` |
| Gem setting context | `early morning in India` | `a Shiva devotional scene — temple, Kailash, or river ghats` |
| Light/time context | `natural and time-appropriate for early morning` | `natural sacred light, dawn or dusk, divine glow` |
| Style mood word | `morning` | `devotional` |
| Category label | Good Morning | Shivji / Mahadev |

**Negative terms:** `funeral, dark mood, horror, cartoon, doodle, playful, comic, modern urban, neon, nightclub, party, alcohol, other deities, cross-faith symbols`

**Firefly compact set:**

| Element | Compact value |
|---------|--------------|
| Atmosphere | `Shiva devotional, sacred Mahadev worship, temple glow` |
| Mood | `reverent, powerful, meditative, sacred, serene` |
| B1 Scene | `Shiva temple at dawn, Kailash mountain, lingam pooja` |

---

## 4.7 Layout Bias

| Layout | Suitability | Reason |
|--------|:-----------:|--------|
| L2 — Overlay / Text Centre | ★ Best | Kailash/temple scene with centred "ॐ नमः शिवाय" |
| L5 — Text Bottom | ★ Best | Trishul/lingam fills top, greeting at base |
| L6 — Text Centre (frame) | ✓ Works | Ornate frame with Shiva motifs, centred text |
| L1 — Text Top | ✓ Works | Text at top, lingam/Nandi illustration below |
| L3 / L4 — Text Left / Right | ✓ Works | Trishul is tall/vertical — works with side text |

---

---

# Category 5: Devotional — Ganeshji

---

## 5.1 What This Category Is

Ganeshji (Lord Ganesha) devotional category for daily Ganesh greetings, Ganesh Chaturthi, Wednesday (Ganesh's day), and Ganpati bhakti. Visual energy comes from Ganesha's iconic form — elephant head, modak, mouse, lotus seat, and the warm, auspicious, obstacle-removing energy.

**Hero Text (pre-filled, editable):** "गणपति बप्पा मोरया" / "श्री गणेशाय नमः" / "Jai Ganesh"

**Seasonal:** No — always available (peak during Ganesh Chaturthi August/September)

---

## 5.2 Track Locking

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ❌ | ✅ |

**Blocked: Track D** — Same reasoning as all devotional categories. Ganesha has a slightly more playful cultural energy than Shiva (Bal Ganesh, friendly remover of obstacles), but the doodle/cartoon treatment of a worshipped deity still crosses the line for a greeting poster context.

---

## 5.3 Overlay Compatibility

| Overlay | Compatible? | Rationale |
|---------|:-----------:|-----------|
| Devotional | ✅ | Reinforces sacred mood — generic devotional motifs complement Ganesh-specific content. |
| Summer | — | Ganesh Chaturthi is post-monsoon (Aug/Sep). Summer heat doesn't match. |
| Rain / Monsoon | ✅ | Chaturthi often falls during late monsoon. Rain-washed Ganesh mandal is authentic. |
| Cricket / IPL | — | Sports on Ganeshji — wrong register. |

---

## 5.4 Wizard Flow — One Change

`Archetype → Track → Layout → Colour → Font → Illustration → Intensity → **Custom Text** ✎`

---

## 5.5 Illustration Catalogue — Ganeshji Pack (22 items)

### Carry-over from Good Morning

| ID | Name | Archetypes | Notes |
|----|------|------------|-------|
| GM-I3-01 | Marigold Garland | A1, A2 | Ganesh pooja decoration |
| GM-I4-01 | Lit Diya | All | Ganesh aarti lamp |
| GM-I3-02 | Lotus in Full Bloom | A1, A2, B1 | Ganesh's seat, sacred |

### New Illustrations (19 items)

**Ganesh — Iconic Forms**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| GN-I01 | Ganesh Idol (Seated) | Traditional Ganesh murti — seated, trunk curved left, one hand blessing, one holding modak. Ornate, golden/red. | A1, A2, B1 |
| GN-I02 | Ganesh Face (Close-up) | Ganesh's elephant face — large ears, gentle eyes, curved trunk, small tusk. Warm, benevolent expression. | A1, A2 |
| GN-I03 | Modak (Sweet) | Single or pile of modak — Ganesh's favourite sweet. Round, pleated, steaming. Warm brown/white. | A1, A2 |
| GN-I04 | Mouse (Mushak) | Small mouse, Ganesh's vehicle. Sitting alert with a modak. Charming, gentle. | A1, A2 |
| GN-I05 | Om / Ganesha Om | ॐ symbol stylised with Ganesh's trunk forming the curve. Sacred, iconic. | A1, A2 |
| GN-I06 | Ganesh Silhouette | Elegant silhouette of Ganesh in seated pose against warm background. Clean outline. | A1, A2, B1 |
| GN-I07 | Broken Tusk | Ganesh's single tusk — standalone sacred symbol. Gold or ivory tone. | A1, A2 |
| GN-I08 | Lotus Seat (with Ganesh) | Open lotus with small Ganesh silhouette seated on it. Sacred, elevated. | A1, A2 |

**Setting & Scene**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| GN-I09 | Ganesh Mandal (Pandal) | Decorated Ganesh Chaturthi pandal with lights, marigold, and idol inside. Festival energy. | B1 |
| GN-I10 | Ganesh Visarjan (Procession) | Devotees carrying Ganesh idol through streets for immersion. Procession energy, dhol drums. | B1 |
| GN-I11 | Ganesh Temple Doorway | Ornate temple entrance with Ganesh carved above. Stone, warm light, sacred. | B1 |
| GN-I12 | Home Pooja Setup | Small Ganesh murti on decorated platform at home — flowers, diya, modak, coconut. Intimate setting. | A1, A2, B1 |

**Pooja & Devotional**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| GN-I13 | Ganesh Pooja Thali | Brass thali with modak, durva grass, red flowers, kumkum, rice, diya. Ganesh-specific pooja set. | A1, A2 |
| GN-I14 | Durva Grass Bundle | Bundle of 3-blade durva grass — sacred to Ganesh. Fresh green, tied with red thread. | A1, A2 |
| GN-I15 | Coconut (Whole) | Whole coconut with husk — Ganesh offering. Sits on brass stand or banana leaf. | A1, A2 |
| GN-I16 | Red Hibiscus Flowers | Red hibiscus (jasvand) — Ganesh's sacred flower. 2–3 blooms, vivid red, fresh. | A1, A2 |
| GN-I17 | Dhol / Drum | Large dhol drum — played during Ganesh Chaturthi processions. Festive, rhythmic energy. | A1, A2 |
| GN-I18 | Rangoli (Ganesh) | Floor rangoli pattern with Ganesh motif — coloured powder, bird's-eye view. | A2, B1 |
| GN-I19 | Mango Leaf Toran with Marigold | Door-hanging toran with mango leaves and marigold garland. Festive welcome. | A1, A2 |

### Catalogue Summary

| Sub-category | Count |
|-------------|:-----:|
| GM Carry-overs | 3 |
| Ganesh — Iconic Forms | 8 |
| Setting & Scene | 4 |
| Pooja & Devotional | 7 |
| **Total** | **22** |

---

## 5.6 Border Motifs per Track

### Track A — Shiny Maximal
| ID | Motif | Description |
|----|-------|-------------|
| GN-MT-A1 | Gold Ganesh Silhouette | Small ornate Ganesh seated silhouette in gold foil, repeating |
| GN-MT-A2 | Modak String | Row of modak sweets with gold detailing along frame edge |
| GN-MT-A3 | Marigold & Durva Garland | Marigold toran with durva grass, gold accents |
| GN-MT-A4 | Om with Ganesh Trunk | ॐ where the curve is formed by a small trunk, gold foil |
| GN-MT-A5 | Sparkle Cluster | Standard celebration sparkle with warm golden tone |

### Track B — Modern Desi
| ID | Motif | Description |
|----|-------|-------------|
| GN-MT-B1 | Block-Print Ganesh | Ganesh silhouette in block-print style fill, saffron/red on cream |
| GN-MT-B2 | Rangoli Corner (Ganesh) | Quarter-rangoli pattern with Ganesh motif at corners |
| GN-MT-B3 | Modern Modak Icon | Clean 2-colour modak icon, simple geometric |
| GN-MT-B4 | Durva Grass Line | Simple row of three-blade durva grass along frame base |

### Track C — Minimalist Classy
| ID | Motif | Description |
|----|-------|-------------|
| GN-MT-C0 | None | No decorative motifs, completely clean |
| GN-MT-C1 | Minimal Ganesh Line | Ganesh silhouette drawn with single continuous line |
| GN-MT-C2 | Single Modak Outline | One modak outline, no fill, warm grey |

### Track E — Soft & Warm
| ID | Motif | Description |
|----|-------|-------------|
| GN-MT-E0 | None | No decorative motifs, completely clean |
| GN-MT-E1 | Watercolour Ganesh | Soft-edge Ganesh silhouette in warm saffron watercolour |
| GN-MT-E2 | Pastel Hibiscus | Gentle pastel red hibiscus, soft edges |
| GN-MT-E3 | Soft Marigold Wash | Watercolour marigold bloom, warm orange bleed |

---

## 5.7 Prompt Context

| Prompt Element | Good Morning | Ganeshji |
|----------------|-------------|----------|
| Hero text | "Good Morning" | User-editable (default: "गणपति बप्पा मोरया") |
| Scene atmosphere | `early morning Indian setting` | `Ganesh devotional setting, Ganpati worship atmosphere` |
| Scene authenticity | `real Indian morning setting` | `real Ganesh pooja or Chaturthi celebration setting` |
| Gem setting context | `early morning in India` | `a Ganesh devotional scene — home pooja, temple, or mandal` |
| Light/time context | `natural and time-appropriate for early morning` | `natural warm sacred light, festive diya glow` |
| Style mood word | `morning` | `devotional` |
| Category label | Good Morning | Ganeshji / Ganpati |

**Negative terms:** `funeral, dark mood, horror, cartoon, doodle, playful, comic, modern urban, neon, nightclub, party, alcohol, other deities, cross-faith symbols`

**Firefly compact set:**

| Element | Compact value |
|---------|--------------|
| Atmosphere | `Ganesh devotional, Ganpati pooja, sacred auspicious` |
| Mood | `auspicious, joyful, blessed, warm, sacred` |
| B1 Scene | `Ganesh idol home pooja, mandal decoration, festive` |

---

## 5.8 Layout Bias

| Layout | Suitability | Reason |
|--------|:-----------:|--------|
| L2 — Overlay / Text Centre | ★ Best | Ganesh idol/mandal scene with centred "गणपति बप्पा मोरया" |
| L5 — Text Bottom | ★ Best | Ganesh illustration on top, greeting at base |
| L6 — Text Centre (frame) | ✓ Works | Ornate frame with Ganesh motifs, centred blessing |
| L1 — Text Top | ✓ Works | Greeting at top, idol illustration below |
| L3 / L4 — Text Left / Right | ✓ Works | Ganesh seated form has a clear central focal point |

---

---

# Category 6: Devotional — Jesus

---

## 6.1 What This Category Is

Jesus/Christian devotional category for daily blessings, Sunday greetings, Christmas, Easter, and faith-based inspiration. Visual energy comes from the cross, church, candle, dove, Bible, praying hands, and serene peaceful light.

**Hero Text (pre-filled, editable):** "God Bless You" / "Praise the Lord" / "प्रभु आपको आशीर्वाद दें"

**Seasonal:** No — always available (peak during Christmas, Good Friday, Easter)

---

## 6.2 Track Locking

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ❌ | ✅ |

**Blocked: Track D** — Playful doodle/cartoon of the cross, Bible, or prayer is tonally wrong for a devotional greeting. Christian imagery for Indian audiences leans respectful and warm, not playful.

---

## 6.3 Overlay Compatibility

| Overlay | Compatible? | Rationale |
|---------|:-----------:|-----------|
| Devotional | ✅ | Generic devotional motifs (diya, sacred light) complement Christian sacred imagery. |
| Summer | — | Summer's bright cheerful energy doesn't match the serene sacred mood. |
| Rain / Monsoon | — | Overcast cosy mood doesn't align with the light/hope energy of Christian greetings. |
| Cricket / IPL | — | Sports on sacred imagery — wrong register. |

---

## 6.4 Wizard Flow — One Change

`Archetype → Track → Layout → Colour → Font → Illustration → Intensity → **Custom Text** ✎`

---

## 6.5 Illustration Catalogue — Jesus Pack (20 items)

### Carry-over from Good Morning

| ID | Name | Archetypes | Notes |
|----|------|------------|-------|
| GM-I4-01 | Lit Diya / Candle | All | Prayer candle — universal sacred light |
| GM-I3-02 | Lotus in Full Bloom | A1, A2, B1 | Purity — cross-faith symbol |

### New Illustrations (18 items)

**Sacred Symbols**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| JE-I01 | Cross (Wooden) | Simple wooden cross, warm brown, natural grain texture. Clean, dignified. | A1, A2, B1 |
| JE-I02 | Cross (Golden / Ornate) | Gold ornate cross with scrollwork detail. Celebratory, Christmas/Easter energy. | A1, A2 |
| JE-I03 | Rosary Beads | String of rosary beads with crucifix, draped gently. Warm wood or pearl tones. | A1, A2 |
| JE-I04 | Dove (Peace) | White dove in flight, wings spread, carrying olive branch. Peace, Holy Spirit. | A1, A2, B1 |
| JE-I05 | Bible (Open) | Open Bible with visible pages, warm light falling on it. Leather cover, gold-edge pages. | A1, A2, B1 |
| JE-I06 | Praying Hands | Two hands clasped in prayer, warm side-lighting. Reverent, universal. | A1, A2, B1 |
| JE-I07 | Fish (Ichthys) | Simple Christian fish symbol, clean line or gold. Ancient, symbolic. | A1, A2 |
| JE-I08 | Crown of Thorns | Woven thorn crown, laid on cloth or wood surface. Solemn, powerful. | A1, A2 |

**Church & Setting**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| JE-I09 | Church (Exterior) | Indian church building — white walls, cross on steeple, warm morning light. Goa/Kerala/CNI style. | A1, A2, B1 |
| JE-I10 | Church Interior (Aisle) | Church interior with pews, stained glass light, candles. Warm, peaceful. | B1 |
| JE-I11 | Stained Glass Window | Colourful stained glass window with light streaming through. Sacred, warm colours. | A1, A2 |
| JE-I12 | Church Bell | Single church bell, brass, warm tones. Sunday morning call. | A1, A2 |
| JE-I13 | Sunset Cross (Hilltop) | Cross silhouette on hilltop against golden sunset. Iconic, dramatic, hopeful. | A2, B1 |

**Devotional & Atmosphere**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| JE-I14 | Candle Row (Vigil) | Row of lit prayer candles in glass holders, church setting. Warm glow, devotional. | A1, A2, B1 |
| JE-I15 | Olive Branch | Single olive branch with small green olives. Peace, reconciliation. | A1, A2 |
| JE-I16 | Light Rays (Divine) | Dramatic god-rays streaming through clouds or window. Divine light, hope. | A2, B1 |
| JE-I17 | Lily / White Flowers | White Easter lily or white flowers. Purity, resurrection, celebration. | A1, A2 |
| JE-I18 | Bread & Wine | Simple bread loaf and wine chalice. Communion, fellowship. Warm still-life. | A1, A2, B1 |

### Catalogue Summary

| Sub-category | Count |
|-------------|:-----:|
| GM Carry-overs | 2 |
| Sacred Symbols | 8 |
| Church & Setting | 5 |
| Devotional & Atmosphere | 5 |
| **Total** | **20** |

---

## 6.6 Border Motifs per Track

### Track A — Shiny Maximal
| ID | Motif | Description |
|----|-------|-------------|
| JE-MT-A1 | Gold Cross | Ornate gold cross motif, embossed, repeating at frame corners |
| JE-MT-A2 | Dove with Rays | Small gold dove with radiating light lines, sacred energy |
| JE-MT-A3 | Lily & Vine Garland | White lily and green vine running along frame edge, gold highlights |
| JE-MT-A4 | Rosary Loop | Small rosary bead loop motif in gold, corner accent |
| JE-MT-A5 | Stained Glass Border | Abstract stained-glass colour pattern along frame edge |

### Track B — Modern Desi
| ID | Motif | Description |
|----|-------|-------------|
| JE-MT-B1 | Modern Cross Icon | Clean 2-colour cross, minimal geometric rendering |
| JE-MT-B2 | Olive Branch Strip | Simple olive branch running along frame base, modern illustration |
| JE-MT-B3 | Dove (Line Art) | Clean minimal dove outline, modern style |
| JE-MT-B4 | Candle Icon Row | Simple candle silhouettes at frame base, warm |

### Track C — Minimalist Classy
| ID | Motif | Description |
|----|-------|-------------|
| JE-MT-C0 | None | No decorative motifs, completely clean |
| JE-MT-C1 | Minimal Cross Line | Cross drawn with single thin lines, no fill, muted gold |
| JE-MT-C2 | Single Dove Outline | One dove outline, barely-there, elegant |

### Track E — Soft & Warm
| ID | Motif | Description |
|----|-------|-------------|
| JE-MT-E0 | None | No decorative motifs, completely clean |
| JE-MT-E1 | Watercolour Cross | Soft-edge cross in warm gold/cream watercolour wash |
| JE-MT-E2 | Pastel Lily | Gentle pastel white lily, soft green leaf, no hard edges |
| JE-MT-E3 | Soft Candle Glow | Watercolour candle with warm light bloom |

---

## 6.7 Prompt Context

| Prompt Element | Good Morning | Jesus |
|----------------|-------------|-------|
| Hero text | "Good Morning" | User-editable (default: "God Bless You") |
| Scene atmosphere | `early morning Indian setting` | `Christian devotional setting, peaceful church or prayer atmosphere` |
| Scene authenticity | `real Indian morning setting` | `real Indian church or Christian home prayer setting` |
| Gem setting context | `early morning in India` | `a Christian devotional scene — church, prayer room, or countryside with cross` |
| Light/time context | `natural and time-appropriate for early morning` | `natural warm light, divine rays, peaceful morning or golden hour` |
| Style mood word | `morning` | `devotional` |
| Category label | Good Morning | Jesus / God Bless |

**Negative terms:** `funeral, horror, dark mood, cartoon, doodle, playful, comic, neon, nightclub, party, alcohol, Hindu deities, Islamic symbols, temple, mosque`

**Firefly compact set:**

| Element | Compact value |
|---------|--------------|
| Atmosphere | `Christian devotional, peaceful church, divine light` |
| Mood | `blessed, peaceful, hopeful, serene, grateful` |
| B1 Scene | `Indian church morning, cross with sunrise, prayer candles` |

---

## 6.8 Layout Bias

| Layout | Suitability | Reason |
|--------|:-----------:|--------|
| L2 — Overlay / Text Centre | ★ Best | Church/sunset scene with centred "God Bless You" |
| L5 — Text Bottom | ★ Best | Cross/dove on top, blessing text at base |
| L1 — Text Top | ✓ Works | Greeting at top, devotional illustration below |
| L6 — Text Centre (frame) | ✓ Works | Frame with cross/lily motifs, centred text |
| L3 / L4 — Text Left / Right | ✓ Works | Cross is vertical — pairs well with side text |

---

---

# Category 7: Devotional — Islamic

---

## 7.1 What This Category Is

Islamic devotional category for daily blessings, Jumma Mubarak (Friday), Eid greetings, Ramadan, and faith-based salutations. Visual energy comes from the crescent and star, mosque, Quran, prayer beads (tasbih), geometric Islamic patterns, and green/gold/white colour associations.

**Hero Text (pre-filled, editable):** "بسم الله الرحمن الرحیم" / "अल्लाह की रहमत" / "Jumma Mubarak" / "Assalamu Alaikum"

**Seasonal:** No — always available (peak during Ramadan, Eid-ul-Fitr, Eid-ul-Adha, Shab-e-Barat)

---

## 7.2 Track Locking

| A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|:-:|:-:|:-:|:-:|:-:|
| ✅ | ✅ | ✅ | ❌ | ✅ |

**Blocked: Track D** — Playful doodle/cartoon of Islamic sacred symbols (crescent, mosque, Quran) is disrespectful. Islamic art traditionally leans towards geometric precision and calligraphic elegance — ornate (A), modern (B), minimal (C), or soft (E) all align.

---

## 7.3 Overlay Compatibility

| Overlay | Compatible? | Rationale |
|---------|:-----------:|-----------|
| Devotional | ✅ | Generic devotional motifs (sacred light, prayer) complement Islamic sacred imagery. |
| Summer | — | Summer's bright casual energy doesn't match the reverent sacred mood. |
| Rain / Monsoon | — | Overcast mood doesn't align with the light/peace energy of Islamic greetings. |
| Cricket / IPL | — | Sports on sacred imagery — wrong register. |

---

## 7.4 Wizard Flow — One Change

`Archetype → Track → Layout → Colour → Font → Illustration → Intensity → **Custom Text** ✎`

---

## 7.5 Illustration Catalogue — Islamic Pack (20 items)

### Carry-over from Good Morning

| ID | Name | Archetypes | Notes |
|----|------|------------|-------|
| GM-I4-01 | Lit Diya / Lamp | All | Prayer lamp — universal sacred light |
| GM-I2-09 | Dawn Sky Colour Gradient | B1 | Fajr (dawn prayer) sky — sacred timing |

### New Illustrations (18 items)

**Sacred Symbols**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| IS-I01 | Crescent Moon & Star | Islamic crescent moon with five-pointed star. Gold or silver on dark/green background. Iconic. | A1, A2 |
| IS-I02 | Mosque Silhouette | Mosque with dome and minarets, silhouette against dawn/dusk sky. Clean outline, universal Islamic. | A1, A2, B1 |
| IS-I03 | Quran (Open) | Open Holy Quran on wooden rehal (book stand), warm light falling on pages. Reverent, sacred. | A1, A2, B1 |
| IS-I04 | Tasbih (Prayer Beads) | String of 33/99 prayer beads, usually green or dark wood, with tassel. Draped gently. | A1, A2 |
| IS-I05 | Arabic Calligraphy (Bismillah) | Beautiful Arabic calligraphy of "Bismillah" in decorative script. Gold or dark ink on warm background. | A1, A2 |
| IS-I06 | Praying Hands (Dua) | Hands raised in dua (supplication), palms up. Warm light, reverent. | A1, A2, B1 |
| IS-I07 | Lantern (Fanoos) | Traditional Ramadan lantern, lit from inside, ornate metalwork. Warm golden glow. | A1, A2 |
| IS-I08 | Dates (Khajoor) | Bowl or plate of dates — iftar essential. Warm brown, natural. | A1, A2 |

**Mosque & Setting**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| IS-I09 | Mosque (Grand, Front View) | Grand mosque facade with central dome, twin minarets, arched entrance. Indian Islamic architecture (Mughal, Indo-Saracenic). | B1 |
| IS-I10 | Mosque Interior (Mihrab) | Interior showing mihrab (prayer niche), arched columns, geometric tile patterns, prayer carpet. Peaceful, vast. | B1 |
| IS-I11 | Minaret (Close-up) | Single minaret tower against sky, detailed stonework. Call to prayer symbol. | A1, A2, B1 |
| IS-I12 | Jali Screen (Geometric) | Ornate carved stone jali/lattice screen with geometric Islamic pattern. Light filtering through. | A1, A2, B1 |

**Devotional & Atmosphere**

| ID | Name | Description | Archetypes |
|----|------|-------------|------------|
| IS-I13 | Prayer Cap & Beads | White/embroidered prayer cap (topi) with tasbih beads beside it. Personal, devotional. | A1, A2 |
| IS-I14 | Iftar Table | Table set for iftar — dates, water, fruit, samosa. Warm light, family gathering. | B1 |
| IS-I15 | Full Moon (Eid Moon) | Full or crescent moon in clear sky — Eid moon sighting. Silver-gold, luminous. | A1, A2, B1 |
| IS-I16 | Islamic Geometric Pattern | Standalone geometric Islamic art — interlocking stars, hexagons, arabesques. Precise, beautiful. | A1, A2 |
| IS-I17 | Green Dome | Green dome (reference to Masjid-an-Nabawi) — iconic, reverent. Gold crescent on top. | A1, A2 |
| IS-I18 | Rosewater & Attar | Small bottle of attar (perfume) or rosewater. Delicate, fragrant, devotional ritual. | A1, A2 |

### Catalogue Summary

| Sub-category | Count |
|-------------|:-----:|
| GM Carry-overs | 2 |
| Sacred Symbols | 8 |
| Mosque & Setting | 4 |
| Devotional & Atmosphere | 6 |
| **Total** | **20** |

---

## 7.6 Border Motifs per Track

### Track A — Shiny Maximal
| ID | Motif | Description |
|----|-------|-------------|
| IS-MT-A1 | Gold Crescent & Star | Ornate gold crescent moon with star, embossed, frame corners |
| IS-MT-A2 | Islamic Geometric Border | Interlocking gold geometric pattern running along frame edge |
| IS-MT-A3 | Lantern (Fanoos) Row | Row of small ornate Ramadan lanterns with gold detailing |
| IS-MT-A4 | Arabic Calligraphy Accent | Small decorative Arabic script motif (non-Quranic), gold foil |
| IS-MT-A5 | Dome & Minaret Silhouette | Small mosque dome+minaret silhouettes in gold, frame top edge |

### Track B — Modern Desi
| ID | Motif | Description |
|----|-------|-------------|
| IS-MT-B1 | Modern Crescent Icon | Clean 2-colour crescent and star, geometric modern rendering |
| IS-MT-B2 | Geometric Star Pattern | Simple Islamic 8-pointed star pattern as corner motif |
| IS-MT-B3 | Lantern (Line Art) | Clean minimal lantern outline, modern illustration |
| IS-MT-B4 | Arabesque Vine | Simple curved vine pattern inspired by Islamic arabesque |

### Track C — Minimalist Classy
| ID | Motif | Description |
|----|-------|-------------|
| IS-MT-C0 | None | No decorative motifs, completely clean |
| IS-MT-C1 | Minimal Crescent Line | Thin crescent moon arc, single line, muted gold |
| IS-MT-C2 | Geometric Star (Single) | One 8-pointed star outline, barely-there, elegant |

### Track E — Soft & Warm
| ID | Motif | Description |
|----|-------|-------------|
| IS-MT-E0 | None | No decorative motifs, completely clean |
| IS-MT-E1 | Watercolour Crescent | Soft-edge crescent moon in warm gold watercolour wash |
| IS-MT-E2 | Pastel Lantern | Gentle pastel Ramadan lantern, soft warm glow |
| IS-MT-E3 | Soft Geometric Wash | Watercolour Islamic geometric star pattern, diffused edges |

---

## 7.7 Prompt Context

| Prompt Element | Good Morning | Islamic |
|----------------|-------------|---------|
| Hero text | "Good Morning" | User-editable (default: "Jumma Mubarak" or "Assalamu Alaikum") |
| Scene atmosphere | `early morning Indian setting` | `Islamic devotional setting, peaceful mosque or prayer atmosphere` |
| Scene authenticity | `real Indian morning setting` | `real Indian mosque or Muslim home prayer setting` |
| Gem setting context | `early morning in India` | `an Islamic devotional scene — mosque, prayer room, or iftar setting` |
| Light/time context | `natural and time-appropriate for early morning` | `natural warm light, fajr dawn or golden hour, sacred glow` |
| Style mood word | `morning` | `devotional` |
| Category label | Good Morning | Islamic / Jumma Mubarak |

**Negative terms:** `funeral, horror, dark mood, cartoon, doodle, playful, comic, neon, nightclub, party, alcohol, Hindu deities, cross, church, temple, pork, figurative depiction of Prophet`

**Firefly compact set:**

| Element | Compact value |
|---------|--------------|
| Atmosphere | `Islamic devotional, mosque prayer, sacred peaceful` |
| Mood | `blessed, peaceful, reverent, serene, grateful` |
| B1 Scene | `Indian mosque at fajr dawn, crescent moon, prayer room` |

---

## 7.8 Layout Bias

| Layout | Suitability | Reason |
|--------|:-----------:|--------|
| L2 — Overlay / Text Centre | ★ Best | Mosque/moon scene with centred "Jumma Mubarak" |
| L5 — Text Bottom | ★ Best | Mosque/dome on top, greeting at base |
| L6 — Text Centre (frame) | ★ Best | Islamic geometric frame is a natural fit for centred text — strong Track A/B |
| L1 — Text Top | ✓ Works | Greeting at top, illustration below |
| L3 / L4 — Text Left / Right | ✓ Works | Minaret is vertical — pairs well with side text |

---

---

# Appendix: Master Summary Tables

---

## A1. Track Locking — All 7 Categories

| Category | A Shiny Maximal | B Modern Desi | C Minimalist Classy | D Artsy Playful | E Soft & Warm |
|----------|:-:|:-:|:-:|:-:|:-:|
| Rath Yatra | ✅ | ✅ | ✅ | ❌ | ✅ |
| Vat Savitri | ✅ | ✅ | ✅ | ❌ | ✅ |
| Father's Day | ✅ | ✅ | ✅ | ✅ | ✅ |
| Devotional — Shivji | ✅ | ✅ | ✅ | ❌ | ✅ |
| Devotional — Ganeshji | ✅ | ✅ | ✅ | ❌ | ✅ |
| Devotional — Jesus | ✅ | ✅ | ✅ | ❌ | ✅ |
| Devotional — Islamic | ✅ | ✅ | ✅ | ❌ | ✅ |

**Pattern:** Track D (Artsy Playful) is blocked for ALL devotional/religious categories (6 of 7). Only Father's Day keeps all 5 tracks — it's secular and emotional, not sacred.

---

## A2. Overlay Compatibility — All 7 Categories

| Category | Devotional | Summer | Rain/Monsoon | Cricket/IPL |
|----------|:---:|:---:|:---:|:---:|
| Rath Yatra | ✅ | ✅ | ✅ | — |
| Vat Savitri | ✅ | ✅ | — | — |
| Father's Day | — | ✅ | — | ✅ |
| Devotional — Shivji | ✅ | — | ✅ | — |
| Devotional — Ganeshji | ✅ | — | ✅ | — |
| Devotional — Jesus | ✅ | — | — | — |
| Devotional — Islamic | ✅ | — | — | — |

---

## A3. Illustration Count Summary

| Category | Carry-over | New | Total |
|----------|:----------:|:---:|:-----:|
| Rath Yatra | 3 | 19 | 22 |
| Vat Savitri | 3 | 17 | 20 |
| Father's Day | 2 | 22 | 24 |
| Devotional — Shivji | 2 | 20 | 22 |
| Devotional — Ganeshji | 3 | 19 | 22 |
| Devotional — Jesus | 2 | 18 | 20 |
| Devotional — Islamic | 2 | 18 | 20 |
| **Total across 7 categories** | **17** | **133** | **150** |

---

## A4. Custom Text Step

| Category | Custom Text? | Default Pre-fill | Editable? |
|----------|:---:|---|:---:|
| Rath Yatra | No | "शुभ रथ यात्रा" (fixed) | No |
| Vat Savitri | No | "वट सावित्री व्रत की शुभकामनाएं" (fixed) | No |
| Father's Day | No | "Happy Father's Day" (fixed) | No |
| Devotional — Shivji | Yes | "ॐ नमः शिवाय" | Yes |
| Devotional — Ganeshji | Yes | "गणपति बप्पा मोरया" | Yes |
| Devotional — Jesus | Yes | "God Bless You" | Yes |
| Devotional — Islamic | Yes | "Jumma Mubarak" | Yes |

---

## A5. What Does NOT Change (All 7 Categories)

Everything below is fully inherited from `Template_Creation_Framework_v20.md` — no modifications for any of the 7 new categories:

- The 3 archetype families (A1, A2, B1) and their wizard flows (except Custom Text addition for devotional 4)
- The 5 tracks (A–E) and their colour palettes, font pools (track availability filtered per category)
- All background finish options (per-track finishes carry over as-is)
- Illustration render style step — fully inherited per track, no locking
- Illustration size — all three sizes available (Small / Medium / Large)
- All 6 layouts (L1–L6) and frame/overlay compatibility rules
- Prompt builder logic / function architecture for all platforms
- Density auto-calculation for A2
- Intensity controls
- Character limits and prompt construction helpers (stripHex, trunc)
- All platform adapters (Firefly ≤950 chars, Midjourney, Leonardo, Gemini)

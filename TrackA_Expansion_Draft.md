# Track A — Shiny Maximal: Expanded Specification

*Jazzy desi — festive, celebratory, loud on purpose. Wedding-card energy meets Diwali poster meets Bollywood opening credits.*

---

## Summary Table (replaces existing Track A summary row)

| Dimension | Specification |
|---|---|
| **Palette family** | 9 palettes (GM-C1-A through GM-C9-A). GM-C1-A example: Dominant #FF8C1A neon marigold / Accent #FF6B00 electric saffron / Highlight #FFD700 hot gold / Punch #8B0000 deep maroon. 3 new Track-A-exclusive palettes: GM-C7-A Hot Pink Festive, GM-C8-A Royal Purple, GM-C9-A Peacock Teal. |
| **Finish options (NEW)** | 5 background treatments: FN-1 Plain Solid, FN-2 Radial Gradient, FN-3 Sparkle/Glitter, FN-4 Metallic Foil, FN-5 Bokeh Glow. Each injects specific prompt language controlling background surface. |
| **Font pool** | Display: Cinzel Decorative, Samarkan, Ranchers, Alfa Slab One, Yatra One, Rozha One. Script: Great Vibes, Allura, Sacramento, Parisienne. Body: Montserrat Black, Poppins Bold, Mukta Bold. Treatments allowed: gold-fill text, metallic gradient, drop-shadow, outer glow, emboss. |
| **Illustration rendering** | 3 sub-styles: IR-1 Ornamental Vector (gold-foil, paisley borders, symmetric), IR-2 Colourful Vector (vivid flat colours, bold outlines, no gold treatment), IR-3 3D Glossy (raised embossed, candy sheen, dimensional). |
| **Motif set (NEW)** | 10 Indian mass-market patterns: MT-1 Paisley (Ambi), MT-2 Mandala, MT-3 Marigold Chain, MT-4 Lotus Border, MT-5 Peacock Motif, MT-6 Diya Row, MT-7 Rangoli Corners, MT-8 Temple Arch, MT-9 Mehndi Swirls, MT-10 Bel Patta Vine. User selects motif set; applies to frame borders + background accents. |
| **Customisation presets (NEW)** | 3-tier master control: Basic (restrained festive), Medium (balanced bling), Complex (maximum desi). Each auto-sets 6 knobs: ornament density, gold amount, shimmer/sparkle, metallic finish, motif coverage, drop shadow. Individual knobs remain accessible. |
| **Prompt style flags** | Midjourney: --ar 9:16 --s 400 --chaos 5. Leonardo: PhotoReal mode off, Alchemy on, style "Ornamental Indian." Firefly: stylize 80, Art content type. Platform-specific prompt templates for MJ, Leonardo, Firefly. |
| **Negative prompt** | No minimalism, no muted colours, no sans-serif only, no empty/breathable composition, no photorealism, no film grain, no Western ornaments, no pastel palette. |
| **Reference aesthetics** | Punjabi wedding invitations, Diwali greeting cards, Madhubani-revival digital art, Bollywood film posters (80s-90s era), FabIndia festive packaging, ShareChat/Moj top Good Morning posts, Rajasthani miniature-meets-digital, temple decoration art, Indian truck art, Meenakari enamel work, Patachitra folk art, zardozi embroidery patterns, Kalamkari textile prints, Tanjore painting gold leaf, Banarasi brocade weave patterns. |
| **Approved archetypes** | A1 (best fit), A2, B1 (photo with ornamental overlay). Not recommended: C2, D1 (conflict with minimalism/playful). |

---

## Detailed BRD — Track A Shiny Maximal

*Prototype-ready specification. Every design token below is engineering-resolvable — hex codes, font stacks, pixel dimensions, model flags. Hand this section to design + engineering and they can start implementing without ambiguity.*

### 1. Colour System — Design Tokens

**Core palette (existing, unchanged):**

| Role | Hex / Value | Name | Usage rule |
|---|---|---|---|
| **Primary 1 / Dominant** | #FF8C1A | Neon Marigold | Background fill 60% · primary brand surface · edge-to-edge canvas fills |
| **Primary 2 / Dominant** | #FF6B00 | Electric Saffron | Background gradient stop · deep saturated accent blocks |
| **Primary 3 / Highlight** | #FFD700 | Hot Gold | Metallic foil fills · decorative borders · headline text-gradient top stop |
| **Primary 4 / Highlight** | #DAA520 | Antique Gold | Headline text-gradient bottom stop · ornamental strokes |
| **Accent 1 / Punch** | #8B0000 | Deep Maroon | Text on light gold · contrast accent on headline · bottom-band fills |
| **Accent 2 / Punch** | #B8001F | Kumkum Red | CTA buttons · sindoor tika motif · dot-accents in ornament |
| **Accent 3 / Sparkle** | #FFFFFF | Spark White | Sparkle particle cores · lens-flare highlights · star-points |
| **Neutral / Deep** | #1A0F00 | Ink Black | Body caption text fallback · logo wordmark on light |
| **Neutral / Cream** | #FFF8E7 | Ivory Cream | Secondary surface · text-box underlays at 85% opacity |
| **Gradient A** | linear-gradient(135deg, #FF6B00 0%, #FFD700 100%) | Saffron-Gold Diagonal | Headline fill · backdrop radial center · CTA hover |
| **Gradient B** | radial-gradient(circle at 50% 40%, #FFD700 0%, #FF8C1A 55%, #8B0000 100%) | Sunburst Radial | Full-bleed hero backgrounds |
| **Shadow / Glow** | rgba(139, 0, 0, 0.45) | Maroon Drop | Text drop-shadow offset 0,4 blur 12 · card elevation |
| **Glow / Outer** | rgba(255, 215, 0, 0.70) | Gold Outer Glow | Headline outer-glow blur 24 · sparkle bloom |

**NEW — Extended palette (Track-A-exclusive colours):**

| Role | Hex / Value | Name | Usage rule |
|---|---|---|---|
| **Extended 1 / Hot Pink** | #EC4899 | Bollywood Pink | GM-C7-A dominant · shaadi/celebration fills · floral accent |
| **Extended 2 / Magenta** | #BE185D | Deep Magenta | GM-C7-A punch · text on pink · contrast accent |
| **Extended 3 / Purple** | #7C3AED | Royal Violet | GM-C8-A dominant · regal/Dussehra fills · premium festive |
| **Extended 4 / Deep Purple** | #5B21B6 | Imperial Purple | GM-C8-A depth · gradient dark stop |
| **Extended 5 / Teal** | #0891B2 | Peacock Teal | GM-C9-A dominant · peacock motif fills · cool-festive surface |
| **Extended 6 / Deep Teal** | #155E75 | Deep Peacock | GM-C9-A depth · gradient dark stop · frame accent |

**NEW — 3 Track-A-exclusive palette families:**

| ID | Palette Name | BG | Text | Accent | Secondary | Vibe |
|---|---|---|---|---|---|---|
| **GM-C7-A** | **Hot Pink Festive** | #EC4899 | #FFFFFF | #FBBF24 (gold) | #BE185D (magenta) | Bollywood glamour, shaadi pink, celebration pink. Best for birthday + anniversary crossover. |
| **GM-C8-A** | **Royal Purple** | #7C3AED | #FEF3C7 (cream) | #FFD700 (gold) | #5B21B6 (deep purple) | Regal, Dussehra, Navratri, premium festive. Purple-gold royal combination. |
| **GM-C9-A** | **Peacock Teal** | #0891B2 | #FFFFFF | #FFD700 (gold) | #155E75 (deep teal) | Peacock motif energy, rich Indian blue-gold. Krishna, monsoon, regal nature. |

### 2. Typography System

*(Unchanged from existing — already comprehensive)*

| Role | Font family | Weight / size / tracking | Use case |
|---|---|---|---|
| **Display / Headline EN** | Cinzel Decorative | 900 / 96-140px / -0.5px | Main greeting headline (Good Morning, Shubh Prabhat) |
| **Display / Headline HI** | Rozha One | 400 / 84-120px / 0px | Devanagari headline (शुभ प्रभात, नमस्ते) |
| **Display / Alt EN** | Samarkan | 400 / 72-110px / 0px | Festive alt headline, wedding/event decks |
| **Script / Tagline** | Great Vibes | 400 / 48-72px / 1px | Tagline line, sub-headline flourish |
| **Sans / Subheadline** | Montserrat Black | 900 / 42-56px / 0px | Sub-headline, quote attribution |
| **Sans / Body** | Poppins Bold | 700 / 24-32px / 0.2px | Short body lines, CTA label |
| **Slab / Accent** | Alfa Slab One | 400 / 64-90px / 0px | Date / year badge / festival name |
| **Mono / Caption** | JetBrains Mono | 500 / 14-18px / 0.5px | Meta info (date stamp, author handle) |
| **NEW — Script / Alt** | Sacramento | 400 / 48-72px / 0px | Elegant script alternative to Great Vibes |
| **NEW — Script / Festive** | Parisienne | 400 / 36-60px / 0px | Romantic/festive tagline |
| **NEW — Devanagari Display** | Yatra One | 400 / 84-120px / 0px | Bold Devanagari festive display |
| **NEW — Body / Devanagari** | Mukta Bold | 700 / 24-32px / 0.2px | Devanagari body text |
| **Treatments** | Allowed: gold-fill, metallic gradient, drop-shadow (blur 12, offset 0,4), outer glow (blur 24, #FFD700), emboss (depth 2, angle 45°) | | |

### 3. Canvas & Layout BRD

*(Unchanged from existing)*

### 4. Rendering Pipeline & Prompt Construction

**Platform-specific prompt templates (NEW — replaces single-platform approach):**

| Stage | Spec / value | Purpose |
|---|---|---|
| **Primary Model** | Midjourney v6.1 | For ornamental, painterly, festive scenes |
| **Secondary Model** | SDXL + LoRA 'indian-ornamental-v2' | When MJ style drift; tighter control |
| **Tertiary Model** | Leonardo.ai (Alchemy mode) | Alternative festive generation |

**Midjourney prompt template:**

| Component | Value |
|---|---|
| **Flags** | --ar 9:16 --s 400 --chaos 5 --weird 25 --stylize 400 |
| **Style Prefix** | "ornate festive Indian greeting, [FINISH_PROMPT], [MOTIF_PROMPT], warm radiant lighting," |
| **Style Suffix** | "shimmering metallic highlights, [SPARKLE_PROMPT], radial sunburst glow, traditional Indian aesthetic, high detail, 8K, ultra-decorative --no minimalism, flat, modern, grunge, grayscale" |
| **Negative (--no)** | minimalism, flat design, grunge, dirty, grayscale, muted, monochrome, bauhaus, swiss style, hand-drawn doodle, sticker, kawaii, cartoon |

**Leonardo.ai prompt template:**

| Component | Value |
|---|---|
| **Model** | Leonardo Kino XL or DreamShaper |
| **Alchemy** | ON |
| **PhotoReal** | OFF |
| **Prompt** | "[SUBJECT]. [ILLUSTRATION_RENDERING_STYLE]. [FINISH_PROMPT]. [MOTIF_PROMPT]. Ornate festive Indian style, [COLOUR_DESC], [CUSTOMIZATION_PROMPT]. Portrait 9:16 format." |
| **Negative Prompt** | "minimalism, flat design, grunge, grayscale, muted, monochrome, cartoon, sticker, Western ornaments, text, letters, watermark" |

**Adobe Firefly prompt template:**

| Component | Value |
|---|---|
| **Content Type** | Art |
| **Stylize** | 80 |
| **Prompt** | "[SUBJECT]. [ILLUSTRATION_RENDERING_STYLE]. [FINISH_PROMPT]. [MOTIF_PROMPT]. Ornate festive Indian greeting style, [COLOUR_DESC], [CUSTOMIZATION_PROMPT]. Portrait 9:16 format for mobile. Do not include any text, letters, words, typography, watermarks, logos, or any minimalist elements." |

**Post-processing pipeline:**

| Step | Spec | Purpose |
|---|---|---|
| **Post-process 1** | Lens flare overlay (Optical Flares preset 'Anamorphic Gold'), 35% opacity, screen blend | Applied to upper-right third |
| **Post-process 2** | Sparkle particle layer, 8-12 particles, size 6-18px, Gold #FFD700, additive blend | Scattered around focal point |
| **Post-process 3** | Vignette dark corners, 25% density, 1800px radius | Adds cinematic depth |
| **Post-process 4** | Grain 4% at 3200 ISO (Filmic subtle) | Prevents over-digital feel |

### 5. Finish — Background Treatment (NEW SECTION)

Controls how the background colour fill is rendered. Same hex colour, dramatically different visual feel. User selects one finish per template.

| ID | Name | Prompt Injection (injected as [FINISH_PROMPT]) | Description | Best For |
|---|---|---|---|---|
| **FN-1** | **Plain Solid** | "solid flat colour fill, clean matte surface, no texture, no effects on background" | Clean flat fill. Lets frame + illustration do the talking. Most predictable output. | Clean typography-forward posters, when illustration is already complex |
| **FN-2** | **Radial Gradient** | "radial gradient from bright centre to darker edges, smooth luminous colour transition, glowing centre fading to rich saturated edges" | Centre-outward shimmer. Creates depth and festive warmth. | Most versatile default. Works with all archetypes. |
| **FN-3** | **Sparkle / Glitter** | "sparkle particle overlay across background, tiny golden glitter dots scattered throughout, festive shimmer texture, magical sparkle effect" | Diwali card / celebration energy. Particles add movement and festivity. | Celebration, Diwali, New Year, birthday crossover |
| **FN-4** | **Metallic Foil** | "stamped metallic gold foil texture on background surface, embossed metallic finish, rich luxurious hammered gold appearance, foil-pressed surface" | Wedding card premium feel. Maximum bling. Best combined with Detailed frame decoration. | Wedding, premium festive, devotional, Tanjore painting energy |
| **FN-5** | **Bokeh Glow** | "soft bokeh light orbs floating in background, warm golden out-of-focus lights scattered across canvas, festive fairy light atmosphere, dreamy depth" | Warm fuzzy festive lights. Creates atmosphere without competing with illustration. | Evening/night variants, Diwali lights, warm romantic mood |

### 6. Illustration Rendering Sub-Styles (NEW SECTION)

Track A supports 3 distinct illustration rendering approaches. The same subject (e.g., "steaming chai cup") is rendered in dramatically different visual treatments depending on sub-style selection. User selects one per template.

| ID | Name | Prompt Description (injected as [ILLUSTRATION_RENDERING_STYLE]) | Visual Character | Reference |
|---|---|---|---|---|
| **IR-1** | **Ornamental Vector** | "ornamental vector illustration with gold-foil fills, paisley and mandala decorative borders framing the subject, stamped-metal shading, drop-shadows, sparkle particles, symmetric composition, traditional Indian ornamental art style" | Gold-foil, paisley borders, symmetric, metal shading. The classic Track A look — wedding invitation energy. High to max density. | Madhubani-revival digital art, wedding card illustrations, Tanjore painting style |
| **IR-2** | **Colourful Vector** | "vivid colourful flat vector illustration, bright saturated colours (reds, oranges, yellows, pinks, greens), clean bold outlines, festive Indian colour palette, no gold treatment, celebratory and cheerful, like a vibrant poster or greeting card" | Bright flat colours, bold outlines, no gold. A red rose is actually bright red, a marigold is vivid orange. Cheerful rather than ornamental. Medium to high density. | Bollywood poster art, Indian truck art colour palette, festival poster prints |
| **IR-3** | **3D Glossy** | "3D glossy rendered illustration, raised embossed effect with smooth reflective surface, dimensional depth with candy-like sheen, plastic figurine quality, modern premium sticker aesthetic, sharp highlights and soft shadows" | Raised/embossed look, glossy reflective surface, dimensional. Modern premium sticker feel — like a 3D-printed greeting card element. Medium density. | Apple emoji 3D style, modern 3D sticker packs, premium WhatsApp sticker aesthetic |

### 7. Motif Set — Indian Mass-Market Pattern Library (NEW SECTION)

User selects one primary motif set per template. The selected motif drives the frame border decoration pattern (A1 frame elements), background accent patterns, and corner/edge ornamental fills. Motif selection is injected into the prompt as [MOTIF_PROMPT].

| ID | Motif | Prompt Keywords (injected as [MOTIF_PROMPT]) | Cultural Anchor | Best Pairing |
|---|---|---|---|---|
| **MT-1** | **Paisley (Ambi)** | "paisley mango motif pattern on decorative elements, traditional ambi teardrop design, Kashmir shawl inspired ornament" | Universal Indian, Kashmir shawl, pan-India recognition | GM-C1 Sunrise Gold, GM-C5 Sacred Saffron |
| **MT-2** | **Mandala** | "circular mandala pattern on decorative elements, geometric sacred concentric rings design, symmetrical radial ornament" | Spiritual, universal, meditation | GM-C5 Sacred Saffron, GM-C8 Royal Purple |
| **MT-3** | **Marigold Chain** | "marigold garland chain pattern as border decoration, genda phool string, toran flower garland ornament" | Puja, wedding, festival. Highest cultural resonance for Good Morning. | GM-C1 Sunrise Gold, GM-C2 Soft Dawn |
| **MT-4** | **Lotus Border** | "lotus flower border pattern on decorative frame, sacred lotus row design, padma petal chain ornament" | Devotional, auspicious, sacred. Works across religions. | GM-C4 Fresh Garden, GM-C5 Sacred Saffron |
| **MT-5** | **Peacock Motif** | "peacock feather eye motif pattern on decorative elements, mor pankh fan design, royal peacock ornament" | Royal, celebratory, Krishna-associated. Strong Rajasthani/Gujarati vibe. | GM-C9 Peacock Teal, GM-C8 Royal Purple |
| **MT-6** | **Diya Row** | "row of lit diyas oil lamp pattern as border decoration, deepawali lamp chain, flame-topped traditional lamp ornament" | Diwali, devotional, evening/night Good Morning variants. | GM-C1 Sunrise Gold, GM-C5 Sacred Saffron |
| **MT-7** | **Rangoli Corners** | "rangoli geometric pattern at corners and edges, traditional kolam dot-grid design, symmetric floor art ornament" | South + Central India. Geometric, mathematical beauty. | GM-C4 Fresh Garden, GM-C6 Minimal White |
| **MT-8** | **Temple Arch** | "temple gopuram arch motif as frame header, mandir gate pillared design, traditional Indian temple architecture ornament" | Devotional, traditional architecture. Best with F5 Arch frame type. | GM-C5 Sacred Saffron, GM-C1 Sunrise Gold |
| **MT-9** | **Mehndi Swirls** | "mehndi henna swirl pattern on decorative elements, intricate vine and dot flowing design, bridal mehandi ornament" | Wedding, feminine, celebratory. Strong appeal for female 25-45 audience. | GM-C7 Hot Pink Festive, GM-C2 Soft Dawn |
| **MT-10** | **Bel Patta Vine** | "bel leaf vine creeper border pattern, sacred bilva leaf chain, organic trailing leaf ornament" | Auspicious, nature-devotional. Shiva-associated. Subtle traditional feel. | GM-C4 Fresh Garden, GM-C5 Sacred Saffron |

**Motif-to-Illustration compatibility (auto-suggestion):** When a user selects an illustration subject, the tool suggests complementary motifs:
- Chai/Beverages → Marigold Chain, Paisley
- Nature/Sunrise → Lotus Border, Bel Patta Vine
- Flowers → matching flower motif (Marigold illustration → Marigold Chain motif)
- Spiritual/Devotional → Mandala, Diya Row, Temple Arch
- Lifestyle → Paisley, Rangoli Corners
- Birds/Peacock → Peacock Motif
- Food/Ritual → Marigold Chain, Rangoli Corners

### 8. Customisation Presets — Basic / Medium / Complex (NEW SECTION)

Master control that auto-tunes all visual intensity knobs in one click. Controls how "maximal" the Shiny Maximal track actually gets. User selects one preset; individual knobs remain accessible for fine-tuning.

**Preset definitions:**

| Knob | Basic (Restrained Festive) | Medium (Balanced Bling) | Complex (Maximum Desi) |
|---|---|---|---|
| **Ornament Density** | Minimal — 1-2 motifs at corners only | Balanced — 3-5 motifs at corners + midpoints | Rich — 6+ motifs throughout, no empty space |
| **Gold Amount** | Accent only — gold highlights on borders | Prominent — gold borders + frame fills + accents | Dominant — gold fills throughout, gold on gold |
| **Shimmer / Sparkle** | Off — no sparkle particles | Subtle — faint glow, 2-4 particles | Heavy — dense sparkle field, 10-15 particles |
| **Metallic Finish** | Matte — clean non-reflective surfaces | Satin — subtle sheen on gold elements | Full Foil — hammered metallic throughout |
| **Motif Coverage** | Corners only — motifs at 4 corners | Corners + midpoints — 8 anchor points | Throughout — border AND background filled |
| **Drop Shadow** | None — flat elements | Soft — gentle shadow on headline text | Deep — strong shadow on text + all elements |

**Prompt injection per preset (injected as [CUSTOMIZATION_PROMPT]):**

- **Basic:** "restrained festive decoration, minimal gold accents at corners only, matte finish, clean sparse composition with breathing space, subtle ornamentation"
- **Medium:** "balanced festive decoration, prominent gold on borders and accents, satin metallic sheen, motifs at corners and midpoints, moderate sparkle, harmonious ornamental composition"
- **Complex:** "maximum festive decoration, dominant gold fills throughout all borders and surfaces, heavy sparkle particles covering background, full metallic foil finish, dense ornamental motifs filling every edge and corner, no empty space allowed, Indian wedding card maximalist energy, every surface decorated"

### 9. Frame Motif Selection — Restructured A1 Flow (NEW SECTION)

For A1 (Text + Frame) archetype, the visual setup step is restructured to ensure frame motifs and illustration choices are coherent:

**New A1 Visual Setup sub-step order:**

1. **Illustration Selection** — Pick illustration category → specific item → size (existing flow)
2. **Frame Motif Selection (NEW)** — Pick motif pattern from Motif Set (MT-1 through MT-10). Tool auto-suggests motifs that complement the illustration choice. E.g., if "Lotus in Full Bloom" is the illustration, Lotus Border (MT-4) and Mandala (MT-2) are highlighted as "Best match."
3. **Frame Complexity** — Pick Plain / Simple / Detailed (existing options, now applied to the selected motif):
   - **Plain:** Selected motif rendered as clean border lines only. Geometric interpretation, no ornate fills.
   - **Simple:** Selected motif at corners or midpoints only (1-2 instances). Subtle traditional touch.
   - **Detailed:** Selected motif throughout the full border. Rich, ornate, festive. Frame IS a visual element. Gold scrollwork with decorative overspill — motif elements allowed to bleed slightly outside the frame boundary for a lush, organic feel (reference: the ornate gold + floral corner frame style seen in viral WhatsApp Good Morning images).

**Frame overspill (Detailed only):** When complexity is set to "Detailed," the prompt includes: "decorative motif elements allowed to extend slightly beyond the frame boundary, organic ornamental overspill at corners and edges, lush border that breathes and extends, not rigidly contained within straight lines."

### 10. Reference / Moodboard (EXPANDED)

| Reference | Description |
|---|---|
| **Ref 1** | Punjabi wedding invitations — gold foil, marigold, paisley, maximalist ornament |
| **Ref 2** | Diwali greeting cards — diyas, rangoli, sparkle, saffron-gold palette |
| **Ref 3** | Madhubani-revival digital art — folk patterns rendered with modern precision |
| **Ref 4** | Bollywood film posters (80s-90s era) — dramatic, colourful, gold text, festive energy |
| **Ref 5** | FabIndia festive packaging — contemporary Indian ornamental with clean execution |
| **Ref 6** | ShareChat/Moj top Good Morning posts — the actual viral format, mass-market taste |
| **Ref 7** | Rajasthani miniature-meets-digital — detailed scenes, ornate borders, rich colour |
| **Ref 8** | Temple decoration art — floral garlands, gold leaf, sacred geometry |
| **Ref 9** | Indian truck art — vivid colour, bold patterns, unapologetic maximalism |
| **Ref 10** | Meenakari enamel work — jewel tones, gold outlines, intricate fill patterns |
| **Ref 11** | Patachitra folk art — scroll painting, narrative panels, border storytelling |
| **Ref 12** | Zardozi embroidery patterns — raised gold threadwork, dimensional texture |
| **Ref 13** | Kalamkari textile prints — hand-painted florals, mythological scenes, earth + gold |
| **Ref 14** | Tanjore painting gold leaf — raised gold relief, gem-like colours, devotional art |
| **Ref 15** | Banarasi brocade weave — metallic zari patterns, silk texture, regal repetition |
| **Forbidden Ref** | Minimalism, Scandinavian, Bauhaus, Swiss style, grunge, pastel-only, Western holiday (Christmas/Halloween), Japanese kawaii |

### 11. Approved Archetypes

A1 (best fit — frame + ornament are native), A2 (illustration-forward with festive palette), B1 (photo with ornamental overlay). Not recommended: C2 minimal (brand conflict), D1 illustrated/sticker (aesthetic conflict).

---

## Future Enhancements — Track A (Parked)

Items identified for future Track A expansion. Not in current scope but documented for roadmap.

1. **Photorealistic Festive rendering (IR-4)** — A hybrid illustration rendering sub-style that produces painterly-photorealistic compositions: realistic flowers, landscapes, and elements rendered with ornate gold frame overlaid. The gold scrollwork frame with floral overspill corners + photorealistic sunrise landscape inside = the dominant viral WhatsApp Good Morning style. Requires hybrid A1+B1 prompt engineering or a single-prompt approach that generates frame + photo scene together. Reference: the uploaded Good Morning poster with gold scrollwork, realistic roses/birds, and sunrise landscape.

2. **User photo integration** — Allow users to upload their own photo which gets placed inside the ornate frame with Track A treatment applied (gold border, motif overlay, sparkle particles).

3. **Animated sparkle/shimmer for C1 archetype** — Track A sparkle particles animated as a looping GIF or short video for WhatsApp status.

4. **Regional motif sub-sets** — Expand motif library with region-specific patterns: Warli (Maharashtra), Madhubani (Bihar), Pattachitra (Odisha/Bengal), Gond (Central India), Phulkari (Punjab), Aipan (Uttarakhand).

5. **Festival-specific Track A overrides** — Diwali: auto-select Diya Row motif + Sparkle finish. Holi: auto-select Rangoli + Colourful Vector rendering. Navratri: auto-select Temple Arch + Royal Purple palette.

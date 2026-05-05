# Good Morning Poster Prompt Generator — Full Context & Learnings

> **Purpose**: Context file for Cursor / AI coding assistants. Contains all architectural decisions, prompt engineering patterns, UX design choices, and iteration learnings from building the JioAICloud Good Morning Poster Prompt Generator v5.
>
> **Primary file**: `GoodMorning_Prompt_Generator_v5.html` — single-file HTML wizard (~2200 lines)
> **Deployed at**: GitHub Pages via `docs/` folder — `https://github.com/Rk42002/JioAICloud_Template-Creation_v2`

---

## 1. What This Tool Does

A step-by-step wizard that generates AI image prompts for "Good Morning" greeting posters tailored for the Indian market. Users select template type, visual style, layout, colour palette, illustration, and intensity — the tool outputs optimised prompts for 5 platforms: Adobe Firefly (with text), Adobe Firefly (without text), Midjourney, Leonardo.AI, and Google Gemini.

The tool targets JioAICloud's template creation pipeline where these prompts are used to generate poster backgrounds that are then composited with text overlays.

---

## 2. Architecture Overview

### 2.1 Three Archetype Families

| Archetype | Description | Key Differentiator |
|-----------|-------------|-------------------|
| **A1 — Text + Frame** | Decorative border/frame is the defining visual. Illustration sits inside. | Frame type selection (F1–F5), frame decoration level, motif placement ON border edges only |
| **A2 — Text + Illustrations** | Illustrations are primary. No dominant frame. Free composition. | Illustration density (auto-calculated from sub-element count), motif placement AROUND illustration, curated accent props |
| **B1 — Photo Background** | Full-bleed photograph fills canvas. Text overlaid with darkening overlay. | Photography-based: mood (lighting + colour grading), overlay strength, scene elements with accent props |

### 2.2 Five Aesthetic Tracks

Every archetype supports all 5 tracks. Each track has its own colour palettes, font pairings, illustration render styles, motif sets, background finishes, and intensity presets:

| Track | Aesthetic | Signature |
|-------|-----------|-----------|
| **A — Shiny Maximal** | Wedding-card meets Diwali poster | Gold foil, sparkle particles, ornamental vector, heavy metallic |
| **B — Modern Desi** | Muted earthy, editorial restraint | Kraft paper, watercolour wash, block print, Kodak Portra film |
| **C — Minimalist Classy** | Maximum restraint, tonal elegance | Monochrome, embossed stamp, hairline rules, desaturated |
| **D — Artsy Playful** | Gen-Z sticker/doodle energy | Flat sticker, confetti, thick outlines, bright poppy colours |
| **E — Soft & Warm** | Gentle pastels, botanical warmth | Watercolour botanical, soft gradients, peripheral wash |

### 2.3 Wizard Step Flows (per Archetype)

**A1 flow**: Template → Style (Frame Type) → Layout → Track → Colour & Finish → Visual → Intensity
**A2 flow**: Template → Layout → Track → Colour & Finish → Visual (with curated sub-illustrations) → Intensity
**B1 flow**: Template → Text & Overlay (merged) → Track → Scene Elements (with curated accent props) → Mood → Intensity

Key design decision: A2 and B1 have fewer steps than A1. A2 removed the "Style" step (density is auto-calculated). B1 merged overlay + layout into one step.

---

## 3. Prompt Engineering Learnings

### 3.1 Platform-Specific Prompt Patterns

Each platform has fundamentally different prompt requirements. The same visual concept must be expressed differently:

#### Midjourney (MJ)
- **Format**: Single dense comma-separated paragraph + flags (`--ar 9:16 --s 400 --no [negatives]`)
- **Style**: Visual phrases, no section headers, no line breaks in main prompt
- **Negatives**: Passed via `--no` flag, not in main prompt
- **Strength**: Handles complex multi-element scenes well; good at ornamental styles
- **Stylize param**: `--s 400` for illustrated (more stylised), `--s 250` for B1 photo (more realistic)
- **Character limit**: No hard limit but longer = more diluted attention

#### Leonardo.AI
- **Format**: Structured with line breaks, section labels (`BG:`, `Frame:`, `Subject:`, `Render:`)
- **Hard limit**: ≤1400 characters — must truncate aggressively
- **Negatives**: Explicit `Negative:` line at end
- **Best practice**: Compact phrases, truncate verbose render descriptions to 120 chars
- **Guard statements**: Archetype-aware (`"Motif on border frame only"` vs `"Motif around composition"`)

#### Adobe Firefly (With Text)
- **Format**: Flowing sentences, positive-only (no negative prompts supported)
- **Hard limit**: ≤950 characters
- **Key difference**: Includes `"Good Morning" text in white decorative font in the text zone, legible` — Firefly can render text
- **Truncation helpers**: `trunc()` function limits individual phrases; `stripHex()` removes hex codes to save chars
- **No negatives**: Everything must be phrased positively

#### Adobe Firefly (No Text)
- **Format**: Same as With Text but explicitly says `"no text, no letters, no words"` multiple times
- **Hard limit**: ≤950 characters
- **Use case**: When text will be composited separately post-generation

#### Google Gemini
- **Format**: Verbose, structured with section headers, descriptive sentences
- **No character limit**: Can be extremely detailed
- **Best for**: Complex multi-layered scenes, detailed guard statements
- **Sections**: Header → Background & Finish → Frame/Overlay/Density → Layout → Illustration → Motif → Accents → Intensity → Style → Do Not Include
- **Guard phrasing**: Full sentences like `"The motif must appear ONLY on the border frame edges and must NOT appear near, beside, or around the illustration."`

### 3.2 Shared Prompt Construction Helpers

```javascript
function stripHex(s) { return s.replace(/#[0-9A-Fa-f]{3,8}/g, '').replace(/\s{2,}/g, ' ').trim(); }
function trunc(s, max) { if (s.length <= max) return s; return s.substring(0, max).replace(/\s+\S*$/, ''); }
```

- `stripHex()`: Removes hex colour codes from prompt text — saves characters for Firefly/Leonardo without losing meaning
- `trunc()`: Truncates at word boundary to stay within character limits

### 3.3 Negative Prompt Patterns

Common negatives across all platforms: `text, words, letters, typography, watermark, signature, blurry, distorted, low quality, extra fingers, extra limbs`

Archetype-specific additions:
- **A1**: `photograph, photorealistic, 3D render` (unless render style is 3D)
- **A2**: Same as A1
- **B1**: `illustration, cartoon, painting, vector, frame, border, pattern, CGI`

### 3.4 Key Prompt Engineering Insights

1. **Frame vs illustration rendering conflict**: In A1, the frame and illustration can "bleed" into each other's style. Solved by adding explicit guard: `"The frame is purely decorative and does not cover the main illustration. The frame maintains its own consistent style independent of illustration rendering."`

2. **Motif placement per archetype**: A1 motifs go ON the border frame. A2 motifs go AROUND the illustration. This must be explicitly stated or AI generators scatter them randomly. MJ needs it in the main prompt; Gemini needs full-sentence guards.

3. **Colour bleeding prevention**: Illustrations must NOT use the background colour. Each palette defines separate `canvas`, `frame`, `illus`, and `textCol` colour roles. Prompt explicitly says: `"rendered in [illus colours] — NOT [background colour]"`.

4. **Overlay auto-determination (B1)**: Rather than asking users to pick an overlay direction, the system infers it from text position: Text Top → darker overlay at top, Text Bottom → darker at bottom, Text Centre → vignette effect. Overlay strength (light/heavy) is the only user choice.

5. **Density auto-calculation (A2)**: Instead of asking users to pick Light/Medium/Dense illustration density, the system counts how many accent items were selected: 0 items → Light, 1 item → Medium, 2 items → Dense. Eliminates a wizard step.

6. **Colour temperature in B1 prompts**: Each mood maps to a specific Kelvin value (e.g., Golden Warm → 4500K, Misty Soft → 5500K, Soft Pastel → 6200K). This gives AI generators a precise colour grading target.

7. **DSLR quality anchoring (B1)**: Adding `"professional DSLR photography, sharp focus on subject, natural depth of field"` dramatically improves B1 output realism across all platforms.

---

## 4. UX Design Patterns & Learnings

### 4.1 Curated Sub-Elements (Not Free-Pick)

**Problem**: When users freely picked 1–3 scene elements, they chose unrelated items (e.g., marigold garland + chai cup + peacock) creating visually chaotic prompts.

**Solution**: Pick 1 main element → system shows 2–4 curated related accent props. User optionally picks 0–2 from the curated list.

**Implementation**: Two separate mapping objects — `B1_SUB_ELEMENTS` (photo descriptions) and `A2_SUB_ELEMENTS` (illustration descriptions) — that map each main illustration item to contextually appropriate small props.

**Key learning**: "Marigold with tea is weird" — sub-elements must be scene-setting PROPS (biscuits, newspaper, folded napkin), not additional hero illustrations. The `ACCENT_ITEMS` dictionary contains 30 small items across 7 categories: Kitchen/table, Nature/outdoor, Devotional/puja, Lifestyle/cozy, Window/architectural, Wildlife/garden, Steam/smoke.

### 4.2 Shared ACCENT_ITEMS with Dual Descriptions

Each accent item has both a `photoDesc` (for B1 photorealistic prompts) and an `illusDesc` (for A2 illustrated prompts):

```javascript
'ACC-01': { name: 'Biscuits on a Plate', 
  photoDesc: 'a small plate of Parle-G style biscuits in the background', 
  illusDesc: 'a small illustrated plate of biscuits nearby' }
```

This allows the same conceptual prop to be described appropriately for each rendering context.

### 4.3 Merged Steps Reduce Friction

**B1 Text & Overlay**: Originally separate "Layout" + "Overlay" steps. Merged into one step because overlay direction is fully determined by text position. The step shows text position options (6 layouts) with an auto-overlay description, plus a simple Light/Darker strength toggle.

**A2 Density Removal**: Originally a separate step asking Light/Medium/Dense. Now auto-calculated from accent prop count. One fewer decision for the user.

### 4.4 Dimmed Non-Recommended Options

Mood options that aren't "suggested" for the selected track appear at 50% opacity but remain clickable. This nudges users toward good choices without blocking creative exploration.

```javascript
const dimStyle = (!isSuggested && !isSelected) ? 'opacity:0.5;' : '';
```

### 4.5 Layout × Style Compatibility System

A 3-tier badge system shows which layout+style combinations work best:
- ★ Best (green) — recommended pairing
- ✓ Works (blue) — compatible
- ~ With Care (yellow, 70% opacity) — possible but may have issues

Stored in `LAYOUT_COMPAT` as a nested object: `archetype → style → layout → 'best'|'ok'|'caution'`.

---

## 5. Data Architecture

### 5.1 STATE Object

Single global state object drives the entire wizard. All selections stored as IDs (strings), resolved to full objects only when building prompts.

```javascript
const STATE = {
  step: 1, archetype: null, step2: null, layout: null, track: null,
  palette: null, font: null, finish: null, illusRender: null, motifSet: null,
  customPreset: null, illusCategory: null, illusItem: null, frameDecoration: null,
  illusSize: null, textInput: '', textLang: 'Hindi',
  sceneElements: [],      // B1: array of 1-3 illustration item IDs
  mood: null,             // B1: mood option ID
  overlayStrength: 'light', // B1: 'light' or 'heavy'
  a2SubElements: [],      // A2: accent item IDs (0-2)
};
```

### 5.2 Track-Specific Data

Most design options are track-specific. Pattern: base options defined once, track variants as separate constants:

- `FINISH_OPTIONS` (Track A), `FINISH_OPTIONS_B`, `_C`, `_D`, `_E`
- `ILLUS_RENDER_OPTIONS` (Track A), `ILLUS_RENDER_B`, `_C`, `_D`, `_E`
- `MOTIF_OPTIONS` (Track A), `MOTIF_OPTIONS_B`, `_C`, `_D`, `_E`
- `CUSTOM_PRESETS` (Track A), `CUSTOM_PRESETS_B`, `_C`, `_D`, `_E`

Resolved via helper functions: `getFinishOptions()`, `getIllusRenderOptions()`, `getMotifOptions()`, `getCustomPresets()`.

### 5.3 Colour Palette System

9 base palettes × 5 tracks = 45 colour configurations. Each palette+track combination defines:
- `bg` (canvas background hex)
- `text` (primary text colour hex)
- `accent` (accent/highlight hex)
- `secondary` (supporting colour hex)
- `natural` (human-readable colour description for prompts)
- `roles` object: `canvas`, `frame`, `illus`, `illusAccent`, `textCol`, `banColour` — each a prompt-ready phrase

Track A palettes have the richest `roles` objects because ornamental rendering needs precise colour separation.

### 5.4 Illustration Catalogue

49 items across 6 categories: Beverages (6), Nature & Sky (6), Flowers & Botanicals (9), Spiritual & Devotional (8), Lifestyle & People (6), Birds & Wildlife (6).

Each item has:
- `id` (e.g., 'GM-I1-01')
- `name` (e.g., 'Steaming Chai Cup')
- `desc` (brief visual description)
- `archs` (which archetypes support it: 'All', 'A1, A2', 'B1, A2', etc.)

B1 also has `B1_PHOTO_DESC` — separate photorealistic descriptions for each item since illustrated descriptions don't work for photography prompts.

---

## 6. Prompt Output Structure

### 6.1 Output Card Order

Firefly (With Text) → Firefly (No Text) → Midjourney → Leonardo.AI → Google Gemini

Firefly first because it's the primary production platform for JioAICloud.

### 6.2 Prompt Audit Table

Every generated output includes a collapsible "Prompt Audit" section that maps each wizard step to the corresponding section in each prompt. This helps verify that no step's selection was lost during prompt construction.

### 6.3 Eval Export

One-click CSV row export for tracking prompt quality across iterations. Captures all wizard selections + generated prompts in a single tab-delimited row that can be pasted into a spreadsheet.

---

## 7. B1 Photo Background — Specific Patterns

### 7.1 Photography Tracks (B1-specific)

Each aesthetic track maps to a specific photography style:
| Track | B1 Style | Description |
|-------|----------|-------------|
| A | HDR Saturated | Viral WhatsApp-forward energy, oversaturated |
| B | Editorial Muted | Kodak Portra 400 film, muted earthy |
| C | Desaturated Minimal | High contrast, low saturation, architectural |
| D | Bright Lifestyle | Instagram blog photography, airy overexposed |
| E | Soft Dreamy | Pastel bokeh, gentle warmth, romantic |

### 7.2 Mood Options (B1)

6 moods combining lighting + colour grading: Golden Warm, Misty Soft, Bright & Vivid, Dramatic Rays, Vintage Film, Soft Pastel.

Each mood is recommended for specific tracks. Non-recommended moods appear at 50% opacity.

### 7.3 Scene Composition (B1)

Main element + up to 2 accent props from `B1_SUB_ELEMENTS`. Scene description built as: `"a [main item photo desc], [accent 1 photo desc], [accent 2 photo desc]"`.

### 7.4 Auto-Overlay System (B1)

```javascript
function getB1AutoOverlay() {
  const strength = STATE.overlayStrength || 'light';
  const opacityWord = strength === 'light' ? 'light subtle semi-transparent' : 'heavy opaque dark';
  // L1 (Text Top) → darker at top
  // L2 (Text Overlay) → uniform overlay
  // L3 (Text Left) → darker at left
  // etc.
}
```

---

## 8. Key Iteration History & Bug Fixes

### 8.1 Design Iterations (Chronological)

1. **Split Firefly into 2 versions** — "With Text" (includes text rendering instruction) and "No Text" (explicit no-text guard)
2. **Fix motif placement per archetype** — A1: on border only. A2: around illustration only. Previously mixed up.
3. **Remove L2 from A1/A2** — Text Overlay layout doesn't make sense for frame/illustration archetypes
4. **Remove 8 illustration items** — Pruned items that didn't work well across platforms
5. **Add visual previews** — SVG diagrams for render styles and background finishes in the wizard
6. **Reorder output cards** — Firefly first (primary platform), then MJ, Leonardo, Gemini
7. **Merge B1 overlay + layout** — Into single "Text & Overlay" step
8. **Reduce overlay strength** — From 3 options to 2 (Light / Darker)
9. **Curated sub-elements for B1** — Replace free-pick with per-item curated accent props
10. **Redesign accent props** — "Don't add large complex illustrations for supporting" → 30 small scene-setting props
11. **Dim non-suggested moods** — 50% opacity for non-recommended options
12. **Enrich B1 prompts** — Added colour temperature, DSLR quality, depth of field, overlay strength language
13. **A2 sub-illustrations** — Same curated accent pattern as B1, with auto-density calculation
14. **Add Gemini platform** — 5th prompt builder with verbose structured format, no character limit

### 8.2 Common Bugs Encountered

- **Duplicate old code after edit**: When replacing part of a function, the old bottom half can remain → causes `ReferenceError` at runtime. Always verify full function replacement.
- **Null reference on step2Opt for B1/A2**: After removing step2 from B1/A2 flows, any reference to `getStep2Option()` must be null-checked with `?.` or conditional.
- **LAYOUT_COMPAT crash for B1**: `LAYOUT_COMPAT[STATE.archetype][STATE.step2]` fails when `STATE.step2` is null. Use optional chaining.

---

## 9. File & Deployment Structure

```
9. Template Automation V2/
├── GoodMorning_Prompt_Generator_v5.html  ← PRIMARY source file
├── Template_Creation_Framework_v19.docx   ← Word doc (BRD/spec)
├── CONTEXT.md                             ← This file
├── docs/
│   ├── index.html                         ← Copy of v5.html for GitHub Pages
│   └── GoodMorning_Prompt_Generator_v5.html  ← Copy for GitHub Pages
```

**Deploy workflow**: Edit v5.html → Copy to docs/ → Git commit → Push to main → GitHub Pages auto-deploys.

**Git repo**: `https://github.com/Rk42002/JioAICloud_Template-Creation_v2`
**Mac local path**: `/Users/rohan.kohli/Documents/Github/9. Template Automation V2`

---

## 10. Technical Conventions

- **Single-file HTML**: All CSS, JS, and data in one file. No external dependencies, no frameworks. Runs entirely client-side.
- **ID-based state**: STATE stores IDs (strings). Objects resolved at prompt-build time via `getArchetype()`, `getTrack()`, etc.
- **Render function pattern**: Each step has a `renderStepX()` or `renderB1*()` function that writes HTML into `#app`. State changes trigger `renderStep()` which routes to the correct renderer.
- **Copy-to-clipboard**: Each output card has a copy button that reads from `GENERATED_PROMPTS[index]` (pre-generated and stored globally).
- **Character counting**: Firefly and Leonardo prompts show character count badges. Red if over limit.
- **Git via osascript**: Commits and pushes happen via macOS `osascript` running shell commands on Rohan's Mac (not from the sandbox).

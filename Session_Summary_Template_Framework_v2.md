# Template Creation Framework — Session Summary v2
**Date:** April 27, 2026  
**Project:** JioAICloud Greetings & Creation — Template Automation  
**GitHub Repo:** `Rk42002/JioAICloud_Template-Creation_v2`  
**Local Path:** `/Users/rohan.kohli/Documents/Github/9. Template Automation V2`

---

## What Was Built (Completed)

### 1. Prompt Generator v5 (HTML Wizard)
- **File:** `GoodMorning_Prompt_Generator_v5.html`
- Full wizard flow for 3 archetypes: A1 (Illustrated Framed), A2 (Illustrated Frameless), B1 (Photo Background)
- Generates prompts for 3 platforms: Midjourney, Leonardo.AI, Adobe Firefly
- 5 aesthetic tracks: Shiny Maximal, Modern Desi, Minimalist Classy, Artsy Playful, Soft & Warm
- Leonardo prompts compressed to fit 1400-char limit (0/2940 combos over)
- **Export Eval Row** button: copies all wizard choices as TSV for pasting into evaluation Excel

### 2. Evaluation Framework
- **File:** `Prompt_Eval_Framework.xlsx`
- 3 sheets: Eval Data, Instructions, Summary
- Part A (22 cols): Auto-filled from wizard export (archetype, track, palette, illustration, prompts etc.)
- Part B (10 cols): Human-rated — Overall Score (1-5), Element Checks (Y/P/N), Colour Harmony, WhatsApp-Ready, Failure Tags, Notes
- Dropdowns with data validation for consistent scoring
- Summary sheet pre-filled with pivot dimensions (by Archetype, Track, Platform, Mood, Overlay, Intensity)

### 3. BRD Document v17
- **File:** `Template_Creation_Framework_v17.docx`
- Scope & Caveats section at top (what IS and IS NOT in Phase 1)
- Full B1 Photo Background BRD section inserted
- Pushed to GitHub

### 4. QA Test Scripts (Node.js)
- `qa_leonardo.js` — Verifies all Leonardo prompts contain critical elements (header, BG, layout, illustration, render, negatives etc.)
- `measure_leonardo.js` — Measures prompt lengths across all 2940 combinations, reports stats (min/max/avg/P50/P90/P99)
- `show_worst.js` — Prints worst-case prompts for A1, B1, and typical A2

---

## Strategic Brainstorm: Cheapest Way to Generate Templates

### 4 Approaches Evaluated

| Approach | Description | Per-Image Cost | Pros | Cons |
|----------|-------------|---------------|------|------|
| **A. Full AI Generation** | Generate every template via AI API | Rs 0.15 - Rs 8 | Creative variety | Unpredictable, text issues, expensive at scale |
| **B. Programmatic Composition** | Code assembles templates from pre-made assets | ~Rs 0 | Deterministic, fast, offline-capable | Limited creative range, needs asset library |
| **C. Hybrid (Recommended)** | AI generates asset library once, code composes on demand | ~Rs 0 marginal | Best of both worlds | Upfront curation effort |
| **D. Licensed Assets Only** | Stock libraries + code composition | ~Rs 0 marginal | Legally safest, no AI needed | Limited to what Stock has |

### Recommendation: Hybrid (C) + Adobe Stock (D)

**Phase 1 (Eval):** Use Leonardo API ($9/mo) + Firefly (existing CC subscription) to test prompt quality across platforms. Use the Eval Framework to score outputs.

**Phase 2 (Production):** Shift to hybrid approach:
1. Curate asset library from Adobe Stock (vectors for A1/A2 illustrations, photos for B1 backgrounds)
2. One-time AI generation for any novel assets Stock doesn't cover (self-hosted Flux/SDXL on Jio GPU infra)
3. Programmatic composition engine assembles final posters — deterministic, fast, zero marginal cost

---

## Platform Cost Comparison

### AI Generation Platforms

| Platform | Per-Image Cost | Commercial License | IP Indemnity | Best For |
|----------|---------------|-------------------|--------------|----------|
| Adobe Firefly (Standard model) | ~Rs 0.4/img | Yes | Yes (only platform) | Eval + legally safe |
| Adobe Firefly (Ultra model) | ~Rs 8/img | Yes | Yes | High-quality hero images |
| Leonardo.AI API | ~Rs 1.5/img | Yes (paid plans) | No | Eval (good quality/cost ratio) |
| Midjourney | ~Rs 2/img (Pro $60/mo) | Yes (paid plans) | No | Highest quality for eval |
| Self-hosted Flux/SDXL | ~Rs 0.15/img | Yes (open source) | No | Production at scale |

### Adobe Firefly Plans (as of April 2026)

| Plan | Monthly Cost | Credits/Month | Cost per Standard Image |
|------|-------------|---------------|------------------------|
| Free | $0 | 25 | - |
| Standard | $9.99 | 2,000 | ~$0.005 |
| Pro | $19.99 | 4,000 | ~$0.005 |
| Pro Plus | ~$49.99 | 10,000 | ~$0.005 |
| Premium | $199.99 | 50,000 | ~$0.004 |

- Standard generation = 1 credit
- Image 4 Ultra = 20 credits
- Fast mode = 2x credits
- Creative Cloud plans include 500-1,000 credits/month bundled
- **Promo through May 20, 2026:** Unlimited generations on select models

### Adobe Stock Integration
- Jio already has Adobe Stock subscription
- Stock API allows programmatic search, filter (vectors/illustrations/photos), and licensing
- Vectors (SVG/EPS/AI) can be recolored programmatically to match any track palette
- One vector x 5 tracks x 8 palettes = 40 variations from 1 asset
- **Licensing:** Standard License covers up to 500K users; Extended License needed for JioAICloud's scale (millions)
- Extended License pricing varies — check with Jio's Adobe account manager

---

## Key Architecture Decision (Pending)

**The core question:** Should we generate every template via AI, or build a composition engine that assembles templates from pre-curated assets?

**Why Hybrid wins:**
1. **Text rendering solved** — P1 caveat about AI not rendering text well goes away; code places text pixel-perfect
2. **Consistency** — Same illustration always looks the same, just recolored per palette
3. **Speed** — Composition takes milliseconds vs. 5-30 seconds for AI generation
4. **Offline capable** — Works without API calls
5. **Cost** — Near-zero marginal cost after initial asset curation
6. **Quality control** — Deterministic output; no surprises

**What's still needed for Hybrid:**
- Decide asset sources: Stock vectors vs. AI-generated vs. hand-designed
- Build the composition engine (SVG/Canvas-based)
- Design the asset pipeline: how assets are tagged, stored, retrieved
- Decide rendering format: SVG (scalable, editable) vs. PNG (universal)

---

## Git Commit History

```
a603be3  Compress Leonardo.AI prompts to fit 1400-char limit
e5c6f0c  Tag archetype-specific columns in eval Excel headers
6ccf8bf  Add evaluation framework — Export Eval Row button + Excel
624f02d  Add session summary for continuity across threads
f2110a7  Add Scope and Caveats section at top of framework doc
e5b0d74  Add B1 Photo Background revamp — full photorealistic pipeline
```

---

## Files Reference

| File | Purpose |
|------|---------|
| `GoodMorning_Prompt_Generator_v5.html` | Main prompt generator wizard |
| `Prompt_Eval_Framework.xlsx` | QA evaluation spreadsheet |
| `Template_Creation_Framework_v17.docx` | BRD document with all archetypes |
| `docs/index.html` | GitHub Pages copy of wizard |
| `Session_Summary_Template_Framework.md` | Previous session summary (v1) |
| `Session_Summary_Template_Framework_v2.md` | This file |

---

## Next Steps

1. **Confirm architecture:** Hybrid (Stock assets + composition engine) vs. Full AI — needs Rohan's call
2. **Check Adobe licensing:** Confirm Extended License availability with Jio's Adobe account
3. **Prototype composition engine:** Build a POC that takes a Stock vector + palette + layout and renders a poster
4. **Firefly eval:** Use the promo period (through May 20) for unlimited generations to test Firefly quality
5. **Run QA eval:** Use the Eval Framework to systematically score outputs across platforms x archetypes x tracks

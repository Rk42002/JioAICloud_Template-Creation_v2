# Template Creation Framework — Session Summary v3
**Date:** April 28, 2026  
**Project:** JioAICloud Greetings & Creation — Good Morning Template System

---

## What We Built (Cumulative)

### 1. Good Morning Prompt Generator (v5 HTML)
A full wizard-driven prompt generator that builds AI image prompts across **4 platforms**:
- **Midjourney** — dense comma-separated format with `--ar`, `--s`, `--no` flags
- **Leonardo.AI** — structured compact format, ≤1400 chars
- **Adobe Firefly** — concise positive-only format, ≤1000 chars (no negatives)
- **Google Gemini** — verbose descriptive format, no char limit

**Archetypes supported:**
- **A1** — Framed Illustrated (frame types F1–F5)
- **A2** — Frameless Illustrated (overlay types O1–O5, density levels)
- **B1** — Photo Background (photorealistic, overlay + mood system)

**Wizard steps:** Template → Style → Layout → Track → Colour+Finish → Illustration → Intensity → Font+Text → Generate

**5 Tracks** with full per-track specs:
- Track A — Shiny Maximal ✨ (ornate festive Indian)
- Track B — Modern Desi 🎨 (contemporary editorial)
- Track C — Minimalist Classy 🎬 (Muji/Aesop zen)
- Track D — Artsy Playful 🎉 (WhatsApp sticker energy)
- Track E — Soft & Warm 🌷 (pastel botanical)

### 2. Template Creation Framework BRD (v18 docx)
Comprehensive Word document with:
- 61-entry clickable document index organized into 6 colour-coded groups
- Full BRD specs for all archetypes and tracks
- Frame, overlay, layout reference tables
- Shared design systems (palettes, fonts, illustrations)
- Per-track detailed spec sheets

### 3. Prompt Evaluation Framework (Excel)
- **Eval Data sheet** — 23 Part A columns (wizard selections) + 10 Part B columns (quality scoring) with 4 prompt columns (MJ, Leonardo, Firefly, Gemini)
- **Instructions sheet** — How to use the framework
- **Summary sheet** — Auto-calculated averages per track/archetype
- **QA Testing Guide** — Per-track checklist for evaluators (general checks + track-specific + B1-specific)

### 4. Export Eval Row
Button in the HTML wizard that exports all selections + 4 platform prompts as TSV for direct paste into the Excel framework.

---

## Key Decisions & Changes This Session

### Firefly as 4th Platform (New)
- Old verbose Firefly prompts renamed → **Google Gemini** (4th platform)
- New compressed **Adobe Firefly** prompts built: positive-only, ≤1000 chars
- Firefly best practices: no negative prompts, concise direct language, Content Type (Art/Photo) set in UI not prompt
- Sweet spot: 300–750 chars for Firefly

### Font/Text Removal from Prompts (Latest Change)
**Problem:** AI-generated text/typography looks bad across all platforms.

**Solution:**
- Removed font name references (`d.font.heading`, `d.font.body`) from all 6 prompt builders that had them
- Firefly builders already had no font lines — no changes needed
- **Kept** text overlay zone layout descriptions intact (e.g., "text overlay zone in the upper 25%")
- **Kept** the Font+Text wizard step in the UI (user still selects fonts for manual post-processing)
- Strengthened "no text" negatives: `text, letters, words, numbers, typography` at front of all negative arrays

**Result:** AI generates the same visual template with clean empty space where text goes. User adds text manually in post-production using the font selected in the wizard.

### Character Limits (Verified)
| Platform | Max Observed | Limit | Status |
|----------|-------------|-------|--------|
| Firefly | 951 chars | 1,000 | ✅ 0 over |
| Leonardo | 1,326 chars | 1,400 | ✅ 0 over |
| Midjourney | ~2,400 chars | None | ✅ |
| Gemini | ~2,900 chars | None | ✅ |

---

## Git History (Recent Commits)
```
8096b86 Remove font/text from AI prompts - user adds text manually in post
eb3ec8f Sync GitHub Pages with v5 HTML (4-platform support)
a5d2078 Add compressed Firefly prompts (≤1K chars) and Google Gemini as 4th platform
a603be3 Compress Leonardo.AI prompts to fit 1400-char limit
e5c6f0c Tag archetype-specific columns in eval Excel headers
6ccf8bf Add evaluation framework — Export Eval Row button + Excel
```

**Repo:** https://github.com/Rk42002/JioAICloud_Template-Creation_v2

---

## File Inventory

| File | Location | Description |
|------|----------|-------------|
| `GoodMorning_Prompt_Generator_v5.html` | Repo root | Main prompt generator wizard |
| `Template_Creation_Framework_v18.docx` | Repo root | BRD with 61-entry clickable index |
| `Prompt_Eval_Framework.xlsx` | Repo root | 4-sheet evaluation framework |
| `Session_Summary_Template_Framework_v3.md` | Repo root | This file |

---

## Architecture Notes

### Prompt Builder Chain
```
User wizard selections → STATE object
  → gatherPromptData() / gatherB1PromptData()  (builds phrase data)
    → buildPrompt(platform)  (dispatcher)
      → buildMJPrompt(d) / buildLeonardoPrompt(d) / buildFireflyPrompt(d) / buildGeminiPrompt(d)
      → buildB1MJPrompt(d) / buildB1LeonardoPrompt(d) / buildB1FireflyPrompt(d) / buildB1GeminiPrompt(d)
```

### Negative Prompt Functions
- `buildNegatives()` — A1/A2 negatives for MJ and Gemini
- `buildLeonardoNegatives(d)` — A1/A2 compact negatives for Leonardo
- B1 negs array — inline in `gatherB1PromptData()`

### What Font Step Does Now
- User selects heading + body font in the wizard UI
- Font selection is exported in the eval TSV row
- Font names are **NOT** included in any AI prompt
- User applies fonts manually in post-production on the generated image

---

## Pending / Future Work
- Test generated images across all 4 platforms with the no-text prompts
- Evaluate if text overlay zones are creating good clean space for manual text
- Consider adding more scene elements / illustration items
- B1 archetype — potential expansion of mood × scene combinations
- Future archetypes (C1 collage, D1 gradient, etc.)

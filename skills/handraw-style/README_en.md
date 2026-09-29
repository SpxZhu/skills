<p align="center">
  <a href="README.md">中文</a> | <strong>English</strong>
</p>

# Hand-drawn Style & Layout Prompter for AI Image Generation

> **Struggling to describe art styles? Trouble structuring visual layouts? Simply pick an index number to generate highly recognizable AI image prompts.**

This repository curates **277 distinct hand-drawn illustration styles** (`001`–`277`), **119 composition layout patterns** (`SC-*` Social Cards, `IG-*` Infographics, `SB-*` Comic Storyboards), and **30 curated classic monochrome colors** (`C-01`–`C-30`).

Whether you are crafting social media post covers, educational infographics, architectural comparisons, or multi-panel narrative comics, you no longer need to memorize obscure art history terminology or struggle with complex compositions. **Simply choose a style number, layout ID, and theme color, supply your topic, and instantly get verified, high-fidelity bilingual prompts ready to paste into Midjourney, DALL-E 3, Flux, Stable Diffusion, or any other image generator.**

---

## 🌟 Core Pain Points & Solutions

| Creator Pain Point | How This Library Solves It |
| :--- | :--- |
| **Vague style descriptions lead to style drift** | **Numbered Indexing**: 277 systematically categorized illustration styles, eliminating guess-and-pray prompting. |
| **Monotonous composition; hard to format complex graphics** | **119 Layout Compositions**: 19 Social Cards, 32 Infographics, 68 Comic Storyboards ready out-of-the-box. |
| **Chaotic color palettes lack a cohesive tonal mood** | **30 Curated Monochrome Colors**: Klein Blue, Sage Green, Hermes Orange, etc., setting pure and sophisticated tones with one click. |
| **Text disconnects from art; awkward typography placement** | **Dual-Mode Workflow**: Seamlessly toggle between "Pure-Image Mode" (pure illustration) and "Graphic-Text Mode" (unified visual-textual composition). |
| **Models ignore style keywords or lack style fidelity** | **Tiered Model Adaptation & Fallback**: Calibrated keyword activation for native models; automatic Reference Image Fallback (4-grid sheets) for all third-party models. |

---

## 🎯 Target Audiences & Use Cases

- **Content Creators & Influencers**: Social media covers (Xiaohongshu, Instagram, X/Twitter), newsletter hero images, viral quote cards.
- **Knowledge & Tech Bloggers**: Comparison lists, architecture pyramids, step-by-step processes, and high-engagement infographics.
- **Comic & Story Creators**: 4-panel strips, emotional webtoons, storyboard drafts, children's storybook illustrations.
- **Visual & Brand Designers**: Rapid concept sketching, creative campaign posters, character design prototypes.

---

## Installation

You can install this skill directly into your AI coding assistant (Codex, Claude Code, Cursor, WorkBuddy, OpenCode):

> **"Install this Skill for me: https://github.com/yang0/handraw-style"**

The assistant will automatically clone the repository and configure all styles, layout templates, and reference assets.

---

## How to Use This Skill

1. Open the [Style Visual Sheet (STYLES_en.md)](STYLES_en.md), [Layout Visual Sheet (LAYOUTS_en.md)](LAYOUTS_en.md), or [Classic Monochrome Colors Sheet (COLORS_en.md)](COLORS_en.md) to browse visual sheets and pick your desired numbers;
2. Note your chosen ID, such as style `041`, layout `SC-001`, or theme color `C-01`;
3. Send your prompt command to the Skill, for example:
   - **Style only**: `Style: 041, Theme: First milk tea of autumn`
   - **Layout + Style**: `Layout: SC-001, Style: 041, Theme: First milk tea of autumn`
   - **With Theme Color**: `Layout: SC-001, Style: 041, Color: C-01, Theme: First milk tea of autumn`
4. Receive clean, copyable bilingual prompts with precise style definitions, layout geometry, and unified color palette;
5. Copy and paste into Midjourney, DALL-E 3, Stable Diffusion, Flux, or any image generator to create your artwork.

---

## Two Prompt Modes, Instant Switching

Any number and theme can seamlessly toggle between two modes without changing your style:

- **Pure-Image Mode (纯图模式)**: Let the theme dictate pure pictorial content without in-image text. Ideal for pure illustrations, wallpapers, book covers, and concept art.  
  *Example*: `Pure-image mode, Style: 041, Theme: First milk tea of autumn`
- **Graphic-Text Mode (图文模式)**: Preserves your copy text and guides the AI to design metaphors and integrate typography harmoniously into the visual composition. Ideal for quote posters, meme graphics, and social cards.  
  *Example*: `Graphic-text mode, Style: 267, Theme: There are many things you couldn't figure out back then. Don't worry, give it some time and you might just forget about them.`

Switch modes anytime by typing *"switch to pure-image mode"* or *"switch to graphic-text mode"*. Defaults to pure-image mode when unstated.

### Graphic-Text Mode Demonstration

The illustration below shows text integrated harmoniously with the visual composition (this is a conceptual demonstration and not tied to any single number):

![Graphic-Text Mode Demo: Duck with hand-drawn lettering](images/graphic-text-mode-demo.webp)

---

### Model Adaptation Mechanism

By default, the Skill crafts copyable prompts. When you explicitly request image generation, it optimizes the output based on verified model capabilities:

- **Explicitly Calibrated Models (e.g., `gpt-image-2`)**: Full activation hierarchy for all 277 styles: Style/Author Name → Positive Core Traits → Reference Image only when traits alone cannot reliably trigger the style, avoiding unnecessary image passing that might over-constrain the composition.
- **Third-Party & General Models (Midjourney, Flux, Stable Diffusion, Imagen, Gemini, etc.)**: Employs the rock-solid **Reference Image Fallback** strategy. The Skill provides a 1024x1024 4-grid standard reference image or file path, ensuring 100% faithful reproduction of linework, texture, and color palette without prompt drift.
- **Open for Community Benchmarks**: Capability definitions reside in `skills/handdraw-style-prompter/references/model_capabilities.json`. Pull requests for other model evaluations are warmly welcomed!

---

## Three Quick Examples

```text
Style: 041, Theme: First milk tea of autumn
Style: 210, Theme: Little boy lighting firecrackers in the snow
Style: 193, Theme: Tang Dynasty Night Banquet
```

---

## Featured Styles Preview

Here is a contact sheet preview of featured hand-drawn illustration styles (001–016):

![Featured Styles Preview (001–016)](images/A_001-016.webp)

- 🖼️ **[👉 Browse All Style Sheets (001–277 Full Visual Contact Sheets)](STYLES_en.md)**
- 📄 **[View Detailed Style Metadata (277 Styles Table & Core Traits)](styles_200_reorganized.md)**
- 💻 *(For offline interactive search and enlargement, open `skills/handdraw-style-prompter/gallery/index.html` in your local browser)*

---

## Layout Compositions Showcase

In addition to 277 illustration styles, this library includes **119 composition layout patterns**, covering social cards, data infographics, and multi-panel storyboards. Combine any style with any layout with a single command.

### 1. Social Cards (19 Layouts)

Ideal for Xiaohongshu, Instagram, quote cards, and social media carousels. Includes top-bottom split, text-driven cards, two-column contrasts, and sticky notes.

![Social Cards Category Preview](images/layouts/preview-social-cards.webp)

👉 **[View All Social Card Layouts (19 Visuals & Prompts)](LAYOUTS_en.md#social-cards)**

---

### 2. Infographics (32 Layouts)

Ideal for knowledge breakdowns, comparison checklists, step-by-step processes, and structured data visuals. Includes hierarchy pyramids, central icons, matrices, and multi-column comparison tables.

![Infographics Category Preview](images/layouts/preview-infographics.webp)

👉 **[View All Infographic Layouts (32 Visuals & Prompts)](LAYOUTS_en.md#infographics)**

---

### 3. Comic Storyboards (68 Layouts)

Ideal for multi-panel narratives, webtoons, emotional storylines, and cinematic pacing. Includes standard 4-panel grids, dramatic wide-angle focus, diagonal cuts, and manga storyboards.

![Comic Storyboards Category Preview](images/layouts/preview-comic-storyboards.webp)

👉 **[View All Comic Storyboard Layouts (68 Visuals & Prompts)](LAYOUTS_en.md#comic-storyboards)**

---

- 💡 **[👉 Enter Full Layout Visual Sheet to Browse All 119 Layouts & Prompts ↗](LAYOUTS_en.md)**
- 💻 *(For offline interactive search and category filtering, open `skills/handdraw-style-prompter/gallery/layouts.html` in your local browser)*

---

## Classic Monochrome Colors Showcase (30 Colors)

This library curates **30 classic monochrome theme colors** (numbered `C-01` ~ `C-30`, covering Classic Blue, Fresh Green, Vintage Red & Classical, Romantic Pink & Purple, and Warm Sun & Earth).
No matter what illustration style or layout composition you choose, specifying a theme color instantly establishes a cohesive visual tone. You can also copy individual color prompts with one click in the offline gallery.

![Classic Monochrome Library Preview](images/colors/sheet_01.webp)

- 🎨 **[👉 Enter Classic Monochrome Colors Visual Sheet to Browse All 30 Colors & Prompts ↗](COLORS_en.md)**
- 💻 *(For offline interactive search and one-click copy, open `skills/handdraw-style-prompter/gallery/colors.html` in your local browser)*

---

## Author & Community

- **WeChat Community / Author WeChat**: Add WeChat with note **handdraw** to join the creators community:

  <img src="images/wechat_community.jpg" alt="WeChat Community QR Code" width="240">

- **X (Twitter)**: [@yang02010](https://x.com/yang02010)
- **GitHub**: [yang0/handraw-style](https://github.com/yang0/handraw-style)

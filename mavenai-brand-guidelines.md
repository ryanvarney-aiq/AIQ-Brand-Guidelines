---
name: mavenai-brand
description: MavenAI brand guidelines, logos, and design system for creating on-brand design assets. Use this skill whenever creating any visual asset, document, presentation, PDF, slide deck, social card, or marketing artifact for MavenAI. Triggers include any mention of MavenAI, Maven, Google Business Profile (GBP), Services Feed, or requests to create branded collateral for MavenAI.
---

# MavenAI Brand Kit — Complete Reference

This skill contains everything needed to create on-brand MavenAI assets. It includes the visual language, color tokens, typography rules, component vocabulary, and layout patterns. **Read this entire file before creating any asset.**

MavenAI turns every community's Google Business Profile and social channels into a live, high-intent marketing surface. The visual language is **deep-ink typography on warm paper, anchored by a four-stop brand gradient.** Generous whitespace. Outcomes over features.

---

## CRITICAL: Asset Usage Requirements

**This kit bundles the MavenAI logo SVGs. You MUST use them — never recreate the logo with text or shapes.**

### How to Find the Assets
All asset paths are relative to this file. To resolve the absolute path at runtime:
1. Note the directory this file lives in (the "skill directory").
2. All paths below (e.g., `brand/mavenai/logos/maven-primary-fullcolor.svg`) are relative to that directory.
3. In Python, use: `SKILL_DIR = os.path.dirname(os.path.abspath(__file__))` or resolve from the known skill install path.
4. When working in Cowork / Claude Code, the skill directory is typically `<workspace>/.claude/skills/mavenai-brand/` — adapt as needed.

### Mandatory Rules
- **NEVER recreate the MavenAI logo with text, shapes, or SVG approximations.** Always embed the actual logo SVGs from `brand/mavenai/logos/`.
- **NEVER recolor, shadow, rotate, or skew the logo.** Aspect ratio is locked at **4.635 : 1**.
- **NEVER place the full-color logo on the brand gradient.** Use the REV ALT (white) variant on dark or gradient backgrounds.
- **NEVER substitute Inter / Inter Tight with Helvetica, Arial, or other fallback fonts** unless the output medium cannot load custom fonts.

---

## Assets Included in This Kit

### Logos
All logo files are in the `brand/mavenai/logos/` folder relative to this file.

| File | Use |
|------|-----|
| `brand/mavenai/logos/maven-primary-fullcolor.svg` | Primary Full Color — for light surfaces (default) |
| `brand/mavenai/logos/maven-primary-rev-alt.svg` | REV ALT (white wordmark + gradient mark) — for dark surfaces |

**Logo Rules:**
- Always use the real SVG logo files — never recreate the logo with shapes, text, or approximations
- The logo aspect ratio is **4.635 : 1** (width to height). Never distort it
- Full Color variant on light/paper backgrounds; REV ALT on dark or saturated backgrounds
- The logo is a single unit — the gradient mark and wordmark travel together
- Never scale the full logo below **24px** height; never scale the standalone mark below **16px**
- Default position: upper-left corner of pages, slides, and one-sheeters
- Never place the full-color logo directly on the brand gradient — use REV ALT there

| Medium | Full logo height | Mark-only size |
|---|---|---|
| Slide / deck header | 34–44px | — |
| One-sheeter header | 28–34px | — |
| PDF footer bar | 24–28px | — |
| Web nav | 30–38px | — |
| Favicon / avatar | — | 28–64px |

### Fonts
MavenAI uses two cuts of the Inter superfamily. Both are available on Google Fonts.

#### Inter Tight (Display — Headlines)
Anything **≥ 20px** that wants optical compression. Its native metrics replace the old "set Inter at -0.02em" recipe — don't double up on tight spacing.

| Weight | Use |
|---|---|
| 600 | Light headline accents (rare) |
| 700 | H2, H3, section titles, feature titles, UI stat captions |
| 800 | Display, H1, hero stat numbers |
| 900 | Rare — reserve for oversized hero moments |

#### Inter (Body & UI)
Anything **< 20px**. Switching faces under 16px keeps counters open and copy readable at small sizes.

| Weight | Use |
|---|---|
| 400 | Body copy, descriptions, captions |
| 500 | Nav links, subtle emphasis |
| 600 | Labels (when not tracked), active nav, bold body accents |
| 700 | Uppercase eyebrows / pills / labels |

#### JetBrains Mono (Specs & Tokens)
Used only for code samples, hex values, and numeric specs inside the design system surfaces. Never for body copy.

### Loading fonts in HTML / React
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Inter+Tight:wght@600;700;800;900&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

---

## Voice & Tone

- **Confident. Operator-focused.** The reader is a property manager or marketing lead — not a CTO. Speak to their outcomes, not to the underlying tech.
- **Short sentences. One idea each.** If a comma is doing the work of a period, break it.
- **Headlines are promises.** Say the outcome. Quantify when honest. Never hedge.
- **Active voice. Subject does the work.** "MavenAI turns GBP into…" — not "GBP can be turned into… by MavenAI."

### Word Preferences
**Use:** live, high-intent, marketing surface, outcomes, get seen, floor plan, availability, pricing, community, operator, Google Business Profile (GBP)
**Avoid:** leverage, drive engagement, revolutionary, game-changing, best-in-class, seamless, robust, empower, cutting-edge, comprehensive, innovative, solution (in isolation), digital footprint, synergy

### Punctuation & Style
- No emoji in headlines or body copy. Ever. Emoji is not a substitute for an icon.
- No exclamation marks in headlines; rare in body.
- Headlines use sentence case. Never ALL CAPS (reserve caps for tracked eyebrow labels only).
- Full-sentence headlines end with a period. Fragment headlines get no punctuation.
- Oxford comma: yes.

### On-brand vs Off-brand
**✓ On-brand:**
- "3 New Ways to Get Seen on Google."
- "MavenAI turns every community's Google Business Profile into a live marketing surface."
- "GBP Services: Amenities + Daily Pricing & Availability."

**✗ Off-brand:**
- "Introducing our innovative new suite of AI-powered tools that can help property management teams potentially improve their Google visibility." *(feature-first, passive, hedged, too many ideas)*
- "Leverage our comprehensive platform to drive meaningful engagement across your digital footprint 🚀." *(empty verbs, emoji filler, banner-ad voice)*

### Feature Copy Pattern
1. **Short title** (3–5 words) — used in lists and chips. *"Services Feed Management."*
2. **Long title** (one line) — used as the H2 on a dedicated feature page. *"GBP Services: Amenities + Daily Pricing & Availability."*
3. **Blurb** (one sentence, ≤ 180 characters) — what it does + the user outcome.

---

## Headlines

### Structure
Short, declarative. One gradient-accented **noun** per headline. The gradient is a punctuation mark, not a texture.

Examples:
- "Get seen on **Google**."
- "3 New Ways to Get Seen on **Google**."
- "GBP Services: Amenities + Daily Pricing & **Availability**."
- "The right **floor plan**. The right rent. Right now."

### Headline Rules
- **Maximum one gradient word per headline.**
- **Gradient is reserved for nouns that matter** — "Google", "Availability", "Floor Plan". Never on verbs, adjectives, or full headlines.
- **Never apply the gradient to full sentences, paragraphs, or body copy.** It fights the reader.
- If no word naturally deserves emphasis, skip the gradient entirely — ink-only headlines are valid.
- Keep headlines under ~8 words when possible.
- Never accent more than two consecutive words.

---

## Color Palette

### Brand Stops — The Four-Stop Gradient
Four brand stops travel together. These are the only approved solid accent colors. **Never invent mid-stop colors.** If you need a solid accent, pick one of these four.

| Token | Hex | Usage |
|---|---|---|
| `indigo` | `#5C4BE8` | Primary brand color. Pills, accent UI, #1 numbered chip. |
| `violet` | `#8B3CE0` | Gradient middle. #2 chip. Secondary accent. |
| `magenta` | `#D93AA8` | Gradient warm-shoulder. Lives **in gradient only** — avoid as a solid fill. |
| `orange` | `#FF5A1F` | Gradient end. #3 chip. Loudest accent; use sparingly. |

### Ink — Foreground
| Token | Value | Usage |
|---|---|---|
| `ink` | `#0E0B2A` | Primary text, headlines |
| `inkSoft` | `rgba(14,11,42,0.72)` | Body copy, descriptions |
| `inkMute` | `rgba(14,11,42,0.55)` | Labels, eyebrows, metadata |
| `hairline` | `rgba(14,11,42,0.12)` | Dividers between content blocks |
| `hairlineSoft` | `rgba(14,11,42,0.06)` | Whisper-dividers, subtle grid lines |

### Paper — Backgrounds
| Token | Hex | Usage |
|---|---|---|
| `paper` | `#FDFCFF` | Default sheet / card surface |
| `paperWarm` | `#F6F4FD` | Alt surface for nested cards, rules boxes |

**Never** introduce saturated or colored backgrounds. Paper + ink + gradient accents are the whole system.

### Gradients
**Brand gradient — 92°** (default for logo, headline nouns, CTAs, top strip):
```css
background: linear-gradient(92deg, #5C4BE8 0%, #8B3CE0 38%, #D93AA8 68%, #FF5A1F 100%);
```

**Backdrop gradient — 135°** (hero washes, cover pages only. Never below saturated text):
```css
background: linear-gradient(135deg, #ECE7FF 0%, #C8BDFA 28%, #A78BE8 55%, #C56FC8 78%, #F08859 100%);
```

### Color Usage Rules
- **One gradient per surface.** Don't stack brand-gradient text on a gradient background.
- **Keep accents in gradient order when numbering** — 1 = indigo, 2 = violet, 3 = orange. People read order into it.
- **Never invent mid-stop colors.** If you need a solid accent, pick one of the four named stops.
- **Only two gradient angles exist:** 92° for the brand gradient, 135° for the backdrop wash. No 45°, no vertical.

### Shadows
| Token | Value | Use |
|---|---|---|
| `shadow-product` | `0 20px 60px rgba(14,11,42,0.14), 0 2px 8px rgba(14,11,42,0.06)` | Product screenshot cards |
| `shadow-card` | `0 10px 30px rgba(14,11,42,0.08), 0 1px 4px rgba(14,11,42,0.04)` | Standard soft-elevated cards |

Never use heavy drop shadows beyond these tokens.

---

## Typography Hierarchy

### Sizes & Specs

| Role | Font | Size | Weight | Letter-spacing | Line-height |
|---|---|---|---|---|---|
| Display (hero) | Inter Tight | 72–96px | 800 | -0.015em | 1.0 |
| H1 (page headline) | Inter Tight | 40–56px | 800 | -0.01em | 1.1 |
| H2 (section title) | Inter Tight | 26–32px | 700 | -0.005em | 1.15 |
| H3 (feature title) | Inter Tight | 20–22px | 700 | 0 | 1.2 |
| Body | Inter | 14–16px | 400 | 0 | 1.5 |
| Small / caption | Inter | 13px | 400 | 0 | 1.55 |
| Label / eyebrow | Inter | 11px | 600–700 | 0.22em UPPERCASE | 1 |
| Stat number | Inter Tight | 44–60px | 800 | -0.01em | 1 |
| Stat caption | Inter | 11–12px | 700 | 0.22em UPPERCASE | 1 |

### Typography Rules
- **Use Inter Tight for anything ≥ 20px.** Its native metrics replace the old "set Inter at -0.02em" recipe — don't double up on tight spacing.
- **Inter for body, labels, UI, and captions.** Switching faces under 16px keeps counters open and copy readable at small sizes.
- **Uppercase labels always have 0.18em–0.28em tracking.** Never uppercase body copy.
- **Gradient text is reserved for nouns that matter** — never on full headlines, never on body copy.
- **Print minimum: 12pt body.** Labels can drop to 10pt if uppercase + tracked.

---

## Layout

### Canonical Sheet (One-Sheeter)
```
sheet            816 × 1056 px  (8.5 × 11 @ 96dpi, portrait)
padding-left     60px
padding-right    48px           (asymmetric — leaves room for the vertical brand strip)
padding-y        40–56px
top accent       6px brand gradient strip
```
Content never spills. Use `overflow: hidden` on the sheet container.

### Spacing Scale
**`8 · 12 · 16 · 20 · 28 · 40 · 56 · 80`** (px)

Stick to the scale. Don't invent off-scale values.

### Grids
- **Feature row:** `88px · 1fr · 200px` with **24px** gap (icon tile · flexible copy · fixed product shot).
- **Footer split:** `1.5fr · 1fr` (about block · booth / URL block).
- **Proof stats:** three equal columns.

### Rhythm
- **Section divider:** `1px` at `rgba(14,11,42,0.12)` — the hairline. Never dotted, never dashed.
- **Footer accent:** 6px brand gradient, full-width.
- **Whitespace + hairlines are the primary dividers** — never box every section in a card.

### Alignment
- Headlines align left. Centered only on covers or dedicated hero moments.
- Body text aligns left. Never justified.
- All elements snap to a consistent left margin tied to the 60px sheet padding.

### Per-Medium Density

**One-Sheeter / PDF page:**
- Max 4 distinct content sections.
- 35–45% whitespace target.
- Reserve bottom 0.75–1in for brand strip + URL.

**Slide / deck:**
- One idea per slide. Two acceptable. Three is the ceiling.
- Edge margins 64px minimum.

**Web:**
- Section padding 80–96px top/bottom.
- Max content width 1120px centered. Body columns max 680px.

**Email:**
- Max width 600px. Section padding 32–48px. CTA button needs 32px clear space above and below.

**Social:**
- Edge margins 32px minimum. Max 2 content elements. Text occupies no more than 50–60% of the card.

---

## Component Vocabulary

Every MavenAI marketing artifact — pages, decks, emails, social cards — is built from this small vocabulary. Don't invent new primitives before checking these.

### MavenLogo
Two canonical lockups: **Primary Full Color** (`maven-primary-fullcolor.svg`) for light surfaces; **REV ALT** (`maven-primary-rev-alt.svg`) for dark. Aspect locked at **4.635 : 1**. Don't recolor, shadow, or place the Full Color version on the brand gradient.

### MavenMark
The gradient square with the house + spark motif. Used for favicons, avatars, and tight-width lockups where the wordmark won't fit. Preserve the native corner radius — don't crop it to a perfect square.

### Pill ("eyebrow tag")
Indigo text on 12% indigo tint (`rgba(92,75,232,0.12)`).
- 11px / 700 / 0.22em UPPERCASE
- Padding: `6px 12px`
- Border radius: `999px` (full capsule)
- **One per surface.** Pills are for marking the surface type ("New Features", "For Operators") — not for tagging every heading.

### NumChip
Circular numbered badge.
- Default size: **54px**; inner number ~44% of container
- Color follows gradient order: **1 = indigo, 2 = violet, 3 = orange**
- Reserved for ordered lists (steps, ways, phases)

### FeatureIcon
Icons from **[Heroicons](https://heroicons.com)** (outline set, MIT licensed).
- Sit inside an **88px tile** with a 12% tint of the chip color.
- Stroke width follows the token scale below — don't hard-set a blanket stroke.

### Icon Stroke Tokens
Treat stroke like type size — pick the token matching the rendered icon size so icons stay optically consistent.

| Token | Stroke | Rendered at | Use |
|---|---|---|---|
| `icon-stroke-sm` | 1.5px | 16px | Inline indicators, nav chrome, dense tables |
| `icon-stroke-md` | 2px | 24px (default) | Buttons, feature lists, inline body icons |
| `icon-stroke-lg` | 2.5px | 32–48px | FeatureIcon tiles, step illustrations, hero moments |
| `icon-stroke-xl` | 3px | 48px+ | Oversized hero lockups, empty-state art, cover pages |

**Implementation note:** Heroicons' 24×24 viewBox is authored at stroke-width 1.5. When rendering above the `md` token, scale the box and override `stroke-width` to the token value so the stroke stays on-scale optically, not proportional to the source.

### ProductShot
- White card, **10–20px** border radius
- Soft two-layer shadow (`shadow-product` token)
- Screenshots show **real UI edge-to-edge**
- Use `object-fit: contain` only when preserving intentional whitespace

### BrandStrip
A 6px bar using the brand gradient. Canonical footer element; also doubles as a cover-page top accent.

### Stat
- Big number: Inter Tight, 800, 44–60px
- Above a tracked uppercase caption: Inter, 11–12px, 700, 0.22em tracking
- **Never more than 3 stats on a single surface.**

---

## Layout Patterns

Two canonical pages. New artifacts should borrow from one of these rhythms before inventing a third.

### Front Page
Top-to-bottom rhythm:
1. **6px gradient strip** (top accent)
2. **Logo + event/URL meta** (`MavenAI` + `maven.ai` on a single row)
3. **Display hero** with one gradient noun — e.g. *"3 New Ways to Get Seen on Google."*
4. **Subhead** — one sentence. The promise in plain English.
5. **3-up proof stats** — never more than three.
6. **Lead feature** — product shot beside copy block.

### Back Page
Top-to-bottom rhythm:
1. **Logo row** (no top gradient strip on back — keep it at the bottom)
2. **1px hairline** under the logo row
3. **Three feature rows** — each: icon tile (indigo → violet → orange) · copy block · product shot
4. **About block + booth/URL footer** split `1.5fr · 1fr`
5. **6px gradient strip** (bottom accent)

---

## Imagery

- **Product shots** — real Google Business Profile UI, MavenAI post cards, floor-plan renderings — shown in full color, edge-to-edge, inside a soft-shadowed white card.
- **Never hand-draw UI screenshots in SVG.** If the asset isn't ready, use a subtly-striped placeholder with a monospace label, and ask for the real screenshot.
- **Photography** — apartment exteriors, interiors, floor plans — bright, high-contrast, architecturally legible. **No moody crops, no people-in-frame hero shots.**
- **Icons come from [Heroicons](https://heroicons.com)** (outline set) with rounded terminals. Stroke width follows the icon-stroke token scale.
- **No stock photography of people or cities.**

---

## Printing & Export

### Print (one-sheeter)
- **8.5 × 11 portrait, zero margin.** The sheet's own 60/48px padding handles safe area.
- Enable `-webkit-print-color-adjust: exact` so gradients and tinted pills don't drop out.
- No bleed required — the sheet is designed edge-safe.

### PPTX export
- Export each page at **1632 × 2112** (2× letter) for a crisp screenshot slide.
- Keep **one slide per page** — don't collage two sheets side by side.

### PDF export
- Render at **≥ 300dpi** for print PDF. Embed all fonts.
- Gradient stops are SVG-friendly — ensure the PDF pipeline doesn't flatten them to single-color fills.

---

## Do NOT Use

These are the easy ways to break the system. Mostly about restraint — the gradient is loud on purpose; let it stay a punctuation mark, not a texture.

- **Gradient text on body copy.** The gradient is for nouns that matter. On paragraphs, it fights the reader.
- **Two saturated gradient stops stacked** (e.g. magenta text on an orange block). Contrast collapses. Pick one.
- **Emoji as iconography.** Always use the Heroicons line set. Emoji reads like a deck someone else made.
- **Boxing every section in a card.** Whitespace + hairlines are the primary dividers. Cards should feel earned.
- **Off-canon gradient angles.** 92° is the default, 135° is allowed for backdrop washes only. No 45°, no vertical, no radial on marketing surfaces.
- **Swapping Inter for a "friendly" face** (Nunito, Poppins Rounded, etc.). The system reads tech-confident, not playful. Stay in Inter.
- **Heavy drop shadows.** Only the two shadow tokens (`shadow-product`, `shadow-card`) are approved.
- **Abstract blob shapes, mesh gradients, or decorative illustrations.** The product shot is the star.
- **Recoloring or shadowing the logo.** Use one of the two approved variants as-is.

---

## Quick Checklist

Before publishing any MavenAI asset, verify:

- [ ] Headlines: short, declarative, sentence case, no exclamation marks
- [ ] Maximum one gradient **noun** per headline (never on full headlines, verbs, or body)
- [ ] Body copy: one idea per sentence, active voice, no hedging
- [ ] No emoji anywhere (headlines, body, or as iconography)
- [ ] Typeface: Inter Tight for display (≥ 20px), Inter for body (< 20px)
- [ ] Uppercase labels are tracked 0.18em–0.28em
- [ ] Background: paper (`#FDFCFF`) or paperWarm (`#F6F4FD`) — no saturated backgrounds
- [ ] Logo: upper-left, correct variant (Full Color on light / REV ALT on dark), aspect 4.635:1 preserved, never below 24px height
- [ ] Accent colors are one of the four brand stops — no invented mid-stop colors
- [ ] Numbered chips follow gradient order: 1 = indigo, 2 = violet, 3 = orange
- [ ] Whitespace + hairlines are doing the dividing — not cards on everything
- [ ] Icons are Heroicons outline with the correct stroke token for the size
- [ ] Shadows are `shadow-product` or `shadow-card` — no custom heavy shadows
- [ ] Gradient angle is 92° (brand) or 135° (backdrop wash) — nothing else
- [ ] Max 3 stat callouts on a surface
- [ ] Max 4 content sections on a one-sheeter; one idea per slide on decks
- [ ] Product shown via real UI screenshots in a soft-shadowed white card — not abstract illustration
- [ ] Spacing snaps to the scale (8, 12, 16, 20, 28, 40, 56, 80)
- [ ] Page/slide edge margins at least 48–64px
- [ ] Print export has `-webkit-print-color-adjust: exact` enabled
- [ ] Visual QA pass completed before delivery — no text overflow, no clipped containers

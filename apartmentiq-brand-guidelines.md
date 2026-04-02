---
name: apartmentiq-brand
description: ApartmentIQ brand guidelines, logos, and fonts for creating on-brand design assets. Use this skill whenever creating any visual asset, document, presentation, PDF, or design for ApartmentIQ or any of its products (Market Surveys, Explore Pro, Explore Pro+, Daylight). Triggers include any mention of ApartmentIQ, AIQ, Daylight, Explore Pro, Market Surveys, or requests to create branded collateral, slides, one-sheeters, social cards, or marketing materials.
---

# ApartmentIQ Brand Kit — Complete Reference

This skill contains everything needed to create on-brand ApartmentIQ assets. It includes brand guidelines, logos, and font files. **Read this entire file before creating any asset.**

---

## CRITICAL: Asset Usage Requirements

**This kit bundles logo PNGs and font .ttf files. You MUST use them.**

### How to Find the Assets
All asset paths are relative to this SKILL.md file. To resolve the absolute path at runtime:
1. Note the directory this SKILL.md lives in (the "skill directory").
2. All paths below (e.g., `brand/logos/aiq-logo-dark.png`) are relative to that directory.
3. In Python, use: `SKILL_DIR = os.path.dirname(os.path.abspath(__file__))` or resolve from the known skill install path.
4. When working in Cowork / Claude Code, the skill directory is typically `<workspace>/.claude/skills/apartmentiq-brand/` — adapt as needed.

### Mandatory Rules
- **NEVER use system fonts, CDN fonts, or Google Fonts links.** Always register and use the .ttf files bundled in `brand/fonts/` for all asset creation (PDFs, PNGs, presentations, etc.).
- **NEVER recreate the logo with text, shapes, or SVG approximations.** Always embed the actual logo PNGs from `brand/logos/`.
- **NEVER substitute Inter/Inter Tight with Helvetica, Arial, or other fallback fonts** when the bundled .ttf files are available. The only acceptable fallback is when the output medium cannot load custom fonts (e.g., plain Markdown), in which case note this limitation.
- **For HTML/React artifacts:** Use `@font-face` declarations pointing to the bundled .ttf files, or if the artifact runs in a browser sandbox without file access, use Google Fonts CDN for Inter/Inter Tight as a last resort — but prefer the bundled files whenever the medium supports them.

---

## Assets Included in This Kit

### Logos
All logo files are in the `brand/logos/` folder relative to this skill file.

| File | Use |
|------|-----|
| `brand/logos/aiq-logo-dark.png` | Dark logo for light/cream backgrounds (primary) |
| `brand/logos/aiq-logo-light.png` | White/light logo for dark backgrounds |

**Logo Rules:**
- Always use the real PNG logo files — never recreate the logo with shapes or text
- The logo is ~6:1 aspect ratio (width to height). Never distort this ratio
- Render at ~150px wide for headers, ~200px for cover pages
- Use `mask='auto'` in ReportLab to preserve transparency
- Default position: upper-left corner of pages, slides, and one-sheeters
- Never stretch, skew, rotate, recolor, or add effects to the logo
- Dark version on light backgrounds, white version on dark backgrounds
- Never scale below 12px height

| Medium | Target height | Resulting width |
|---|---|---|
| Slide header | 28–32px | ~166–190px |
| One-sheeter header | 24–28px | ~142–166px |
| PDF footer bar | 12–14px | ~71–83px |
| Web/email header | 24–36px | ~142–213px |
| Social card | 20–24px | ~119–142px |

### Fonts
Font files are in `brand/fonts/`. Two font families are included:

#### Inter (Headers & Subheaders)
All headings, section titles, phase names, navigation labels, card titles, and badge text.

| Weight | File | Use |
|--------|------|-----|
| Regular (400) | `brand/fonts/Inter/Inter-Regular.ttf` | Subheaders, navigation |
| Medium (500) | `brand/fonts/Inter/Inter-Medium.ttf` | Secondary headers |
| SemiBold (600) | `brand/fonts/Inter/Inter-SemiBold.ttf` | Phase titles, card titles, section labels |
| Bold (700) | `brand/fonts/Inter/Inter-Bold.ttf` | Primary headings |
| Italic (400) | `brand/fonts/Inter/Inter-Italic.ttf` | Emphasized headers |
| Display Light (300) | `brand/fonts/Inter/InterDisplay-Light.ttf` | Large display titles ("Daylight", "Outcome") at 48–72pt |
| Display Thin (100) | `brand/fonts/Inter/InterDisplay-Thin.ttf` | Ultra-light display titles |
| Display Regular (400) | `brand/fonts/Inter/InterDisplay-Regular.ttf` | Display-size regular |

#### Inter Tight (Body Copy)
All body text, descriptions, bullet items, footnotes, footer text, and captions.

| Weight | File | Use |
|--------|------|-----|
| Regular (400) | `brand/fonts/InterTight/InterTight-400-normal.ttf` | Body text, list items, descriptions |
| Medium (500) | `brand/fonts/InterTight/InterTight-500-normal.ttf` | Emphasized body text |
| SemiBold (600) | `brand/fonts/InterTight/InterTight-600-normal.ttf` | Bold body accents |
| Bold (700) | `brand/fonts/InterTight/InterTight-700-normal.ttf` | Strong emphasis in body |
| Italic (400) | `brand/fonts/InterTight/InterTight-400-italic.ttf` | Italic body text |

If neither font is available, use any geometric sans-serif (Poppins, DM Sans, or similar).

### Registering Fonts in ReportLab (Python)

```python
import os
from reportlab.pdfbase import pdfmetrics
from reportlab.pdfbase.ttfonts import TTFont

# Resolve BRAND_DIR relative to this skill's location.
# Option A: If you know the skill install path:
SKILL_DIR = os.path.expanduser("~/.claude/skills/apartmentiq-brand")
# Option B: Dynamically find it by searching for the brand/ folder in known skill locations.
# Adapt as needed for your environment.
BRAND_DIR = os.path.join(SKILL_DIR, "brand")

# Inter — headers
pdfmetrics.registerFont(TTFont("Inter", f"{BRAND_DIR}/fonts/Inter/Inter-Regular.ttf"))
pdfmetrics.registerFont(TTFont("Inter-Medium", f"{BRAND_DIR}/fonts/Inter/Inter-Medium.ttf"))
pdfmetrics.registerFont(TTFont("Inter-SemiBold", f"{BRAND_DIR}/fonts/Inter/Inter-SemiBold.ttf"))
pdfmetrics.registerFont(TTFont("Inter-Bold", f"{BRAND_DIR}/fonts/Inter/Inter-Bold.ttf"))

# Inter Display — large display titles
pdfmetrics.registerFont(TTFont("InterDisplay-Light", f"{BRAND_DIR}/fonts/Inter/InterDisplay-Light.ttf"))
pdfmetrics.registerFont(TTFont("InterDisplay-Thin", f"{BRAND_DIR}/fonts/Inter/InterDisplay-Thin.ttf"))
pdfmetrics.registerFont(TTFont("InterDisplay", f"{BRAND_DIR}/fonts/Inter/InterDisplay-Regular.ttf"))

# Inter Tight — body
pdfmetrics.registerFont(TTFont("InterTight", f"{BRAND_DIR}/fonts/InterTight/InterTight-400-normal.ttf"))
pdfmetrics.registerFont(TTFont("InterTight-Medium", f"{BRAND_DIR}/fonts/InterTight/InterTight-500-normal.ttf"))
pdfmetrics.registerFont(TTFont("InterTight-SemiBold", f"{BRAND_DIR}/fonts/InterTight/InterTight-600-normal.ttf"))
pdfmetrics.registerFont(TTFont("InterTight-Bold", f"{BRAND_DIR}/fonts/InterTight/InterTight-700-normal.ttf"))
```

---

## Voice & Tone

- **Authoritative and grounded.** We are the data company. Speak from earned credibility, not aspiration.
- **Direct.** Short sentences. Lead with the point.
- **Technically precise but never academic.** Use multifamily terminology naturally (comps, NER, leased %, concessions, rent rolls, PMS, PMC, NMHC) — the audience knows the space.
- **Modern.** We contrast against "legacy tools," "old data," "black boxes." Current and forward-leaning without being trendy.

### Sentence & Paragraph Style
- Paragraphs are 1–2 sentences. Cut anything that hits 3.
- Fragments for emphasis. "Built for this." "The end of guesswork." "Fully automated. Deeply detailed."
- Pair a short declarative statement with a longer explanatory follow-up.
- Use the em dash (–) for asides and inline contrast.

### Word Preferences
**Use:** automated, daily, real-time, transparent, modern, public data, proprietary, explainable, all-in-one, deep/deeply, pioneered
**Avoid:** revolutionary, game-changing, cutting-edge, leverage (as verb), best-in-class, world-class, empower, seamless, robust, end-to-end, solution (in isolation)

### Punctuation
- No exclamation marks in headlines. Rarely in body copy.
- Headlines use sentence case, not title case or ALL CAPS.
- Full-sentence headlines end with a period. Fragment headlines get no punctuation.
- Oxford comma: yes.

---

## Headlines

### Platform-Level (ApartmentIQ overall)
Short, declarative. One accent word in the AIQ brand purple (`#6B53FD`). Heavy, bold typeface.

Examples:
- "**Built** for this."
- "Big Decisions. **Bad data.**"
- "The end of **guesswork.**"
- "Multifamily's **most trusted** market data platform"

### Product-Level Headlines
Each product uses its own gradient on the accent word. Structure: short statement, one gradient-accented word/phrase, gradient color per product.

**Market Surveys:** Purple → gold gradient on accent word
**Explore Pro / Pro+:** Purple → teal gradient on accent word
**Daylight:** Pink → orange/gold gradient on accent word, plus the repeating "by design" motif

### Daylight's "by design" Pattern
Daylight slides follow a unique headline structure: **[Gradient adjective] + "by design"** as a two-line headline, with a supporting sentence beneath.

Examples: "**Transparent** by design" · "**Precise** by design" · "**Strategic** by design" · "**Modern** by design"

The gradient word is rendered in the Daylight warm gradient (pink → orange). "by design" is always in `text-primary`, regular weight. **This is Daylight-specific — do not use for other products.**

### Headline Rules (All Products)
- Maximum one gradient-accented word/phrase per headline
- If no word naturally deserves emphasis, skip the gradient
- Never accent more than two consecutive words
- Keep headlines under ~8 words when possible

---

## Color Palette

### Brand Purple — Primary Accent (All Products)
| Token | Hex | Usage |
|---|---|---|
| `aiq-purple` | `#6B53FD` | Accent headlines, accent word color, growth lines, left-border indicators |

### Teal (Links)
| Token | Hex | Usage |
|---|---|---|
| `aiq-teal` | `#0097A7` | Hyperlinks, table of contents links — limited use |

### Default Theme
When no specific product is mentioned, or content spans multiple products, **default to the Explore Pro / Pro+ theme** (purple → lavender → teal). This is the most versatile gradient. Use for cross-product collateral, company-wide announcements, general release notes, investor materials, and any asset where the product context is ambiguous.

### Product Gradients
Each product has its own gradient for hero headlines, section dividers, and stat callouts.

**Market Surveys** — Purple → mauve → peach → gold
```
linear-gradient(90deg, #6B53FD, #B88DD4, #D4A373, #E8B84B)
```

**Explore Pro / Pro+** — Purple → lavender → teal/cyan
```
linear-gradient(90deg, #7C6BCC, #96A3D9, #6BC5B8)
```

**Daylight** — Hot pink → salmon → peach → gold
```
linear-gradient(90deg, #E84393, #F0768B, #F5A672, #EDBE6A)
```
This is the warmest gradient in the system. It should feel distinct from Market Surveys by leaning pink, not purple.

### Text Colors
| Token | Hex | When to use |
|---|---|---|
| `text-primary` | `#0D0D0D` | Headlines, primary text |
| `text-headline-alt` | `#1F2937` | Alternate headline color (slightly warm dark) |
| `text-body` | `#434343` | Body copy |
| `text-secondary` | `#4E4E4E` | Subheads, supporting descriptions |
| `text-muted` | `#666666` | Product descriptors, captions, metadata |
| `text-light` | `#595959` | Stat labels, fine print |
| `text-faded` | `#7F7F7F` – `#B7B7B7` – `#D9D9D9` | Progressive text fade for stacked word lists |

### Backgrounds
| Token | Value | When to use |
|---|---|---|
| `bg-primary` | `#FFFFFF` | Default — most surfaces |
| `bg-warm` | `#F9F7F4` | Some slides, subtle warmth |
| `bg-subtle` | `#F2F2F2` | Feature cards, stat cards |
| `bg-dark` | `#1A1A2E` | Customer quote banners, social proof — white text |
| `bg-muted-purple` | Light purple/lavender wash | Map texture backgrounds, decorative underlays |

### Daylight-Specific Colors

**Per-character gradient for "Daylight" title:**

| Position | Hex | Description |
|----------|-----|-------------|
| D, a | `#EFA52E` | Warm amber/orange |
| y, l | `#F08245` | Coral-orange |
| i | `#ED6256` | Coral |
| g | `#DB5C7D` | Rose |
| h, t | `#CF5789` | Pink-magenta |

**Daylight Accent Colors:**
| Name | Hex | Use |
|------|-----|-----|
| Coral | `#EF6256` | Phase numbers, day labels, progress bar text |
| Pink | `#E0658D` | Checkmarks, arrows, diamond icon |
| Magenta | `#C45190` | Circle icon (support cards) |
| Gold/Amber | `#EFA52E` | Gradient line start, "You're live" badge text |

---

## Typography Hierarchy

### Weight System
| Weight | Token | Usage |
|---|---|---|
| ExtraBold (800) | `stat-callout` | Large stat numbers (e.g., "1,500+") |
| Bold (700) | `hero` | Hero headlines, large feature headings, stat values |
| SemiBold (600) | `heading` | Section headlines, feature card titles |
| Medium (500) | `subhead` | Subheads, numbered list labels, supporting headlines |
| Regular (400) | `body` | Body copy, descriptions, feature details |
| Light (300) | `caption` | Sparse use — large-format text where lightness is needed |

### Sizing Hierarchy
Scale to the medium. Maintain these ratios:
- **Hero headline:** Largest. One per page/section.
- **Section headline:** ~60–70% of hero
- **Subhead:** ~40–50% of hero
- **Body:** Standard readable size for the medium
- **Caption/label:** Smallest tier, always in a muted color
- **Stat callouts:** Can match or exceed hero size — they are visual anchors

### Font Hierarchy (Specific Sizes)
| Element | Font | Size |
|---------|------|------|
| Display title ("Daylight", "Outcome") | InterDisplay-Light | 48–72pt, gradient |
| Cover title ("30-Day Onboarding Plan") | Inter-Bold | 28pt |
| Phase title ("Kickoff", "Go-live") | Inter-SemiBold | 17–20pt |
| Section label ("WHAT DAYLIGHT DOES") | Inter-SemiBold | 7pt, uppercase |
| Card title ("Customer Success") | Inter-SemiBold | 10.5pt |
| Body items / bullet text | InterTight Regular | 9–9.5pt |
| Subtitle / description | InterTight Regular | 11–11.5pt |
| Days label ("Day 1", "Days 2–7") | InterTight Regular | 9.5pt |
| Footer | InterTight Regular | 7.5pt |
| Badge text ("You're live") | Inter-SemiBold | 7pt |

---

## Layout Principles

### Spacing System (8px Base Grid)
All spacing values are multiples of 8.

| Token | Value | Usage |
|---|---|---|
| `space-xs` | 8px | Inline icon-to-label gaps, pill internal padding |
| `space-sm` | 16px | Padding inside small elements, gap between icon and text |
| `space-md` | 24px | Internal card padding, headline-to-subhead gap |
| `space-lg` | 32px | Subhead-to-body gap, gap between list items |
| `space-xl` | 48px | Gap between content blocks within a section |
| `space-2xl` | 64px | Section-to-section spacing, top/bottom page margins |
| `space-3xl` | 80–96px | Hero section top padding, breathing room around section dividers |

### Vertical Rhythm Rules
- **Headline → Subhead:** 24px (tight — they're a visual unit)
- **Subhead → Body copy:** 32px
- **Body copy → Next content block:** 48px
- **Section → Section:** 64px minimum
- **Between items in a list or grid:** 24–32px
- **Page/slide edge margins:** 64px minimum on all sides

### Alignment
- Headlines align left. Centered only on overview/summary slides or section dividers.
- Body text aligns left. Never justified.
- Stat callouts can be centered within their card.
- All elements snap to a consistent left margin.
- When stacking headline → subhead → body, all three share the same left edge.

### Two-Column Split (Default Layout)
Text content on one side, product UI screenshots on the other. Gutter: 48–64px. Text column vertically centers relative to visual column.

### Three-Column Feature Cards
Equal-width cards: icon circle at top → bold feature name → checkmark list beneath. Cards use `bg-subtle`, 24px internal padding, 12px rounded corners. Gap between cards: 32px.

---

## Per-Medium Density Rules

### Slides
- Maximum 3 content blocks per slide
- Edge margins: 64px minimum on all sides
- Prefer one idea per slide. Two is acceptable. Three is the hard ceiling.

### One-Sheeters / Single-Page PDFs
- Page margins: 0.6–0.75in (≈48–60px). Never below 0.5in.
- Maximum 4 distinct content sections
- Target 35–45% whitespace
- Body text: max 4–5 lines per paragraph
- Reserve bottom 0.75–1in for logo + contact info + CTA

### Multi-Page PDFs / Documents
- Page margins: 0.75–1in (≈60–80px)
- Section-to-section gap: 64px
- Maximum 2 images per page
- Body text: max 5–6 lines per paragraph
- Target 30–40% whitespace per page

### Web
- Section padding: 80–96px top and bottom
- Max content width: 1140–1200px centered. Body text columns max 680px.
- Hero section: 96px top padding minimum

### Email
- Max content width: 600px
- Section padding: 32–48px
- Body paragraphs: max 3 lines before a break
- CTA buttons need 32px clear space above and below

### Social
- Edge margins: 32px minimum
- Maximum 2 content elements
- Text should occupy no more than 50–60% of card area

---

## Visual Elements & Patterns

### Stat Callouts
Large bold numbers in product gradient, short label beneath in muted color. Often in 2×2 grid with `bg-subtle` backgrounds. Max 4 stats per row.

### Pill-Shaped Feature Items
Rounded capsule shapes with icon left, label right. Two-column grid. Soft colored outlines.

### Process Flows
Side-by-side cards with chevron (›) separators. Each card: icon, bold title, short description.

### Customer Quotes
Dark background band, white text. Large decorative open-quote mark. Mixed regular/bold for emphasis.

### Card Cascade
Product UI screenshots overlapping at slight angles — a signature visual pattern.

### Decorative Elements
- **Gradient-stroke circles:** Soft gradient borders around numbered items and icons
- **Map/street-grid texture:** Faint street-map pattern in light purple/lavender, low opacity
- **Trend lines:** Thin flowing line charts in purple/warm colors, used decoratively
- **Purple growth line:** Solid `#6B53FD` upward-trending line with circle endpoint
- **Left-border indicators:** Small colored left-border bars in `aiq-purple`

### Do NOT Use
- Heavy drop shadows
- Abstract blob shapes or mesh gradients
- Stock photography of apartments, cities, or people
- Bright solid-color backgrounds (keep white, off-white, or subtle gray — only `bg-dark` for intentional contrast sections)
- Drop shadows on cards or containers — use flat fills, subtle borders, and whitespace

---

## Product Visual Summary

| Element | ApartmentIQ (Platform) | Market Surveys | Explore Pro/Pro+ | Daylight |
|---|---|---|---|---|
| Accent color | `#6B53FD` purple | Purple → gold gradient | Purple → teal gradient | Pink → orange gradient |
| Headline accent | Purple word | Gradient word | Gradient word | Gradient adjective + "by design" |
| Numbered circles | Purple/gold soft fill | Purple/gold soft fill | Teal/purple soft outlines | Pink/peach soft fill |
| Pill shapes | Mixed teal + purple | — | Teal + purple outlines | Pink + orange outlines |
| Icon circles | Purple outline | Purple/gold outline | Purple/teal outline | Pink/peach circle fill |
| UI screenshots | Mixed product cards | Survey table cards (cascading) | Dashboard with charts | Pricing tables, lease data |

---

## Company Facts (for collateral accuracy)

| Fact | Value |
|---|---|
| Top 50 Enterprise Customers coverage | 70% |
| Team growth rate (2026) | 50%+ |
| Total customers | 1,500+ |
| Units covered daily | 40M+ |
| Historical data depth | 5+ years |
| Property websites sourced | 1.1M+ |
| New products (2026) | Revenue Management, Explore Pro |
| Work model | Fully remote |
| Key events | Rentapalooza, Sales Kickoff (SKO) |

---

## Production Quality Rules

### Text Must Fit Its Container
This is the single most common production defect. Before finalizing any layout:
1. Measure, don't assume — Inter is wider than Helvetica at the same point size
2. Account for wrapping in height — add 20–30% buffer
3. Stat callouts: always insert a space between number and unit
4. Right-edge overflow: reduce font size or widen container by 0.1–0.2" as safety margin
5. Column-constrained titles: use 24pt or less (not 28pt+)

### Container Sizing Standards
| Container type | Min width | Min height |
|---|---|---|
| Full-width headline (28pt+) | 8.6" | 0.5" |
| Half-width headline (24pt) | 4.0" | 0.5" |
| Stat callout card | 2.5" | 0.9" |
| Insight/quote box (2–3 lines) | 8.0" text area | 1.0" |
| Feature card (title + description) | 2.0" | 1.2" |
| Body text block (3 lines @ 12pt) | 3.5" | 0.6" |

### Connector Positioning
Connectors (+, ›, →) between cards must sit at the horizontal midpoint of the gap:
```
connector_x = card_x + card_w + (gap / 2) - (connector_w / 2)
```

### Visual QA Before Delivery
Always render to images and inspect before delivering. Check:
- Text touching or overlapping container edges
- Uneven spacing between similar elements
- Low-contrast text on similar backgrounds
- Connectors centered in gaps between cards
- All text fits within containers — no clipping or overflow

---

## Implementation Tips

### Font Subsetting
Always use full-character-set font files (included in this kit), not Latin-only subsets. Latin subsets are missing checkmarks (✓), arrows (→), bullets (●), and other symbols.

### Fixed Y-Position Alignment for Card Grids
Never calculate element positions dynamically based on preceding content. Define fixed vertical offsets from the card top for every element. All cards in a row share the same offset table.

### Pill Vertical Text Centering
```python
pill_bottom = cy - pill_h / 2
text_baseline = pill_bottom + (pill_h - font_size) / 2
```

### Image Embedding
- **Fill mode** (photos, headshots): Crop to fill target box
- **Fit mode** (screenshots, UI, data viz): Scale to fit entirely, no cropping

### Chart Generation (Matplotlib)
- Background: `#F9F7F4` (bg-warm)
- Line color: `#6B53FD` (brand purple)
- Fill: `#7C6BCC` at 25% opacity
- Axis labels: Inter Medium, 10pt, `#666666`
- Data labels: Inter Bold, 14pt, `#6B53FD`
- Remove top, right, left spines; keep bottom at `#DDDDDD`
- Use `dpi=300` for print quality

---

## Quick Checklist

Before publishing any ApartmentIQ asset, verify:

- [ ] Headlines: short, declarative, sentence case, no exclamation marks
- [ ] Accent gradient matches the correct product (default: Explore Pro/Pro+ theme)
- [ ] One gradient word per headline max
- [ ] Body copy: 1–2 sentence paragraphs, no filler language
- [ ] Typeface: Inter Tight body, Inter headers (fonts from this kit)
- [ ] Background: white or off-white unless intentionally using `bg-dark`
- [ ] Product shown via real UI screenshots, not abstract illustration
- [ ] Stats: large, bold, clearly labeled
- [ ] Logo: upper-left, correct variant, clear space respected, not below 12px height
- [ ] Whitespace: target 40–50% on any page/slide
- [ ] Spacing follows 8px grid
- [ ] Headline → subhead tight (24px); section → section wide (64px+)
- [ ] No more than 3 content blocks per slide
- [ ] No text block longer than 3 lines without visual break
- [ ] Page/slide edge margins at least 64px
- [ ] Passes the squint test — distinct clusters with clear white channels
- [ ] No stock photography
- [ ] No drop shadows on cards or containers
- [ ] Every text element fits inside its container
- [ ] Connectors centered in gaps between cards
- [ ] Default theme is Explore Pro/Pro+ when no specific product indicated
- [ ] Visual QA pass completed before delivery

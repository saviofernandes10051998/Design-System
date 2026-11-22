---
name: S.Fernandes Simple Design System
version: 1.0
author: Savio Fernandes
course: HCI 472, DePaul University, Fall 2026
framework: Bootstrap 5.3
figma_file: "SF Design System – VIA Case Study"
case_study: VIA Reflection Toolkit (https://blogs.depaul.edu/via)
tokens:
  color:
    primitive:
      ink: "#111111"
      ink-2: "#3A3631"
      muted: "#6B655D"
      line: "#DCD6CC"
      paper: "#F6F3EE"
      surface: "#FFFFFF"
      brass: "#A8834A"
      brass-700: "#7A5C2E"
      brass-50: "#F1EADF"
    semantic:
      text: "{ink}"
      text-secondary: "{ink-2}"
      text-muted: "{muted}"
      bg: "{paper}"
      bg-raised: "{surface}"
      bg-inverse: "{ink}"
      text-inverse: "{paper}"
      accent: "{brass}"
      accent-text: "{brass-700}"
      border: "{line}"
      focus: "{brass-700}"
      bg-subtle: "{brass-50}"
  font:
    display: "Bodoni Moda"
    text: "Inter"
  type-scale:            # desktop / mobile, px
    display: { font: display, weight: 500, size: 68, mobile: 44, line-height: 1.05 }
    h1:      { font: display, weight: 500, size: 55, mobile: 38, line-height: 1.10 }
    h2:      { font: display, weight: 500, size: 44, mobile: 32, line-height: 1.15 }
    h3:      { font: text,    weight: 600, size: 28, mobile: 24, line-height: 1.25 }
    lead:    { font: text,    weight: 400, size: 22, mobile: 19, line-height: 1.50 }
    body:    { font: text,    weight: 400, size: 18, line-height: 1.65 }
    small:   { font: text,    weight: 400, size: 15, line-height: 1.50 }
    eyebrow: { font: text,    weight: 600, size: 14, line-height: 1.40, case: upper, tracking: 0.16em }
    emphasis: { font: display, style: italic, weight: 400, size: "1.25x parent" }
    link:    { font: text,    weight: 500, decoration: underline, color: accent-text }
  space: [4, 8, 16, 24, 32, 48, 64, 96]
  radius: { sm: 4, md: 8, pill: 999 }
  shadow:
    level-1: "0 1px 2px rgba(17,17,17,.06), 0 4px 16px rgba(17,17,17,.06)"
  grid:
    desktop: { width: 1440, columns: 12, max-content: 1200, gutter: 24, margin: 120 }
    tablet:  { width: 768,  columns: 8,  gutter: 24, margin: 32 }
    mobile:  { width: 390,  columns: 4,  gutter: 16, margin: 16 }
---

# S.Fernandes Simple Design System

A quiet, editorial design system built for my case study on DePaul’s **VIA Reflection Toolkit**.
Ink text on warm Paper, with Brass as the single accent. Bodoni Moda gives headings personality;
Inter does the reading. Every value in this file matches the Figma file’s variables and styles
and the Bootstrap site’s `css/ds.css`.

## 1. Principles

1. **Quiet first.** Lots of white space, one accent, no decoration that does not help reading.
2. **Plain language.** Labels and headings say what things are. Buttons say what happens.
3. **Accessible by default.** All text meets WCAG 2.2 AA. Touch targets are at least 44px.

## 2. Color

| Figma variable (SF Tokens) | CSS token | Hex | Use | Contrast on Paper |
|---|---|---|---|---|
| color/ink | `--sf-ink` | #111111 | Text, primary button, dark sections | 17.1:1 |
| color/ink-2 | `--sf-ink-2` | #3A3631 | Secondary text | 10.8:1 |
| color/muted | `--sf-muted` | #6B655D | Captions, meta | 5.2:1 |
| color/line | `--sf-line` | #DCD6CC | Borders only, never text | — |
| color/paper | `--sf-paper` | #F6F3EE | Page background | — |
| color/surface | `--sf-surface` | #FFFFFF | Cards | — |
| color/brass | `--sf-brass` | #A8834A | Accent fills, text ≥ 24px only | 3.2:1 |
| color/brass-700 | `--sf-brass-700` | #7A5C2E | Links, eyebrows, focus ring | 5.6:1 |
| color/brass-50 | `--sf-brass-50` | #F1EADF | Tag and callout backgrounds | — |

**Semantic variables** (Figma collection “SF Tokens”, group `semantic/`) alias the primitives:
`text → ink`, `text-secondary → ink-2`, `text-muted → muted`, `bg → paper`, `bg-raised → surface`,
`bg-inverse → ink`, `text-inverse → paper`, `accent → brass`, `accent-text → brass-700`,
`border → line`, `focus → brass-700`, `bg-subtle → brass-50`. Components use semantic variables only, never raw hex.

## 3. Typography

| Figma text style | Font | Weight | Size (desktop / mobile) | Line height |
|---|---|---|---|---|
| SF/Display | Bodoni Moda | 500 | 68 / 44 | 105% |
| SF/H1 | Bodoni Moda | 500 | 55 / 38 | 110% |
| SF/H2 | Bodoni Moda | 500 | 44 / 32 | 115% |
| SF/H3 | Inter | 600 | 28 / 24 | 125% |
| SF/Lead | Inter | 400 | 22 / 19 | 150% |
| SF/Body | Inter | 400 | 18 | 165% |
| SF/Small | Inter | 400 | 15 | 150% |
| SF/Eyebrow | Inter | 600, UPPERCASE, +16% letter spacing | 14 | 140% |
| SF/Emphasis | Bodoni Moda Italic | 400 | 1.25× surrounding text | inherit |
| SF/Link | Inter | 500, underline | inherit | inherit |

Scale: Major Third (1.25×) on an 18px base. Bodoni Moda is never used below 28px.

## 4. Logo

S.Fernandes lockup (S mark + wordmark). Navbar: lockup, 24px tall. Footer: wordmark, 18px tall.
Clear space = half the S mark’s height. Minimum: wordmark 120px wide, S mark 16px.
Files: `assets/logo/*.svg`.

## 5. Layout and spacing

- 8-point spacing: 4, 8, 16, 24, 32, 48, 64, 96.
- Sections: 96px top and bottom padding (64px on mobile), divided by a 1px `border` rule.
- Grid: 12 columns, 1200px max content width, 24px gutters (Bootstrap `container-xl`).
- Text measure: about 68 characters per line.

## 6. Components

### 6.1 Button (`.sf-btn`) — Figma component set “Button”
- Variants: `Type = Primary | Secondary | Accent | Inverse`, `Size = Default | Small`, `State = Default | Hover | Focus | Disabled`.
- Auto-layout: horizontal, hug, padding 12 / 24 (Small: 8 / 16), gap 8, min height 48 (Small: 40).
- Font: Inter 600, 16px. Radius 4. Border 1.5px.
- Primary: bg `text` (ink), label `text-inverse`. Secondary: transparent, 1.5px `text` border. Accent: bg `accent`, label `text` (5.4:1). Focus: 3px `focus` outline, 2px offset.
- A11y: ≥ 44px target; `<a>` for navigation, `<button>` for actions; real `disabled` attribute.

### 6.2 Resource card (`.sf-card`) — Figma component “Resource card”
- Variants: `Theme = Light | Dark`.
- Auto-layout: vertical, padding 24, gap 12, fill width. Radius 8, 1px `border` stroke, fill `bg-raised`.
- Layers (in order): `type` (SF/Eyebrow at 12px, accent-text), `title` (Inter 600 22px), `text` (Inter 16px, text-secondary), `tags` (horizontal auto-layout, gap 8, wrap, instances of Pillar tag), `meta` (horizontal, gap 16, Small, text-muted, 1px top border).
- Grid: 3 per row desktop, 2 tablet, 1 mobile.
- A11y: `<article>` with a heading; only the title is a link, stretched to cover the card; hover lift disabled for reduced motion.

### 6.3 Pillar tag (`.sf-tag`) — Figma component set “Pillar tag”
- Variants: `State = Default | Selected | Outline`.
- Auto-layout: horizontal, hug, padding 4 / 14, gap 6, height 32 (44 when used as a filter button). Radius pill.
- Default: fill `bg-subtle`, label `accent-text` (5.2:1). Selected: fill `bg-inverse`, label `text-inverse`, plus a ✓ icon.
- A11y: filters are `<button aria-pressed>` inside `role="group"` with a visible label; selected state is not shown by color alone.

### 6.4 Process step (`.sf-step`) — Figma component “Process step”
- Auto-layout: vertical, gap 8, fill width; 4 across on desktop, stacked on mobile.
- Number: Bodoni Moda Italic 40px, `accent-text`. Rule: 1px `text` line under the number. Title: Inter 600 20px. Text: Inter 16px, `text-secondary`.
- A11y: ordered list `<ol>`; numbers are decorative (CSS counter); each step has a heading.

## 7. Page pattern: case study

Order of sections, all built from the components above:
1. Hero (Eyebrow, Display headline with Emphasis, Lead, 4-item meta list)
2. “Long story short” summary (dark panel)
3. The problem (H2 + body + pull quote)
4. Process (4 × Process step)
5. Audit findings (list with severity labels)
6. Data (3 stat panels)
7. Proposed concept: reflection finder (Pillar tag filters + 3 × Resource card)
8. Outcome and lessons learned (two columns)
9. Call to action (dark band, Accent + Inverse buttons)

## 8. Accessibility checklist

- [x] All text ≥ 4.5:1 contrast (large display text ≥ 3:1)
- [x] Visible 3px focus ring on every interactive element
- [x] Skip link to main content
- [x] Touch targets ≥ 44 × 44px
- [x] Meaning never shown by color alone
- [x] Logical heading order; landmarks (`header`, `nav`, `main`, `footer`)
- [x] `rem` units so text scales with browser settings
- [x] `prefers-reduced-motion` respected

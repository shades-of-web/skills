---
name: brand-guidelines
description: Comprehensive Shades of Web (SoW) brand guidelines — colors, typography, design principles, component patterns, and brand assets. Use when brand colors, style guidelines, visual formatting, or design standards apply.
---

# SoW Brand Guidelines

## CRITICAL: Before Building UI

**You MUST ask the user which brand color should serve as the primary color** before building any real UI. This template ships with Surya Orange as the default primary, but each product chooses its own primary from the brand palette.

### The 80/10/10 Color Proportion Rule

Every SoW interface follows the 80/10/10 ratio:

- **80% Neutral** — background surfaces (Ksheer Ivory / Shyam Black), text, cards
- **10% Primary** — CTAs, buttons, key interactive elements, active states
- **10% Accent** — secondary actions, data visualization, emphasis, decorative touches

The primary and accent colors are drawn from the three brand colors (Orange, Teal, Magenta). Which one is "primary" vs "accent" depends on the product.

### Content-Type Color Assignments

| Content Type | Color | Usage |
|-------------|-------|-------|
| Design content | Surya Orange | Design-focused pages, creative tools |
| Engineering content | Prithvi Teal | Technical docs, developer tools |
| Communication content | Padma Magenta | Marketing, social, CMS |

**Keywords**: branding, visual identity, styling, brand colors, typography, SoW brand, visual formatting, visual design, design system

## Brand Philosophy

The SoW identity is built from three geometric primitives, each representing a core discipline:

### Circle — Bindu (Origin, Idea, Design)

The circle marks the beginning, a point of intent before structure. It represents design at its most fundamental: sense before form, coherence before construction, a space where ideas align and composition begins.

### Square — Yantra (Structure, Logic, Engineering)

The square defines structure, a framework where intent becomes precise. It represents engineering discipline, clarity of boundaries, and systems designed to hold complexity with stability.

### Hexagon — Sutra (System, Communication)

The hexagon represents communication. It reflects how ideas connect, spread, and gain momentum through distributed intelligence, while remaining cohesive, measurable, and able to scale with intent.

### Confluence

Culture gives meaning. Computation gives structure. Craft gives precision. Together, they compose systems that turn complexity into clarity.

## Brand Colors

Six named colors form the brand palette. Each has a Sanskrit name reflecting its role.

| Name | Sanskrit | Hex | RGB | Role |
|------|----------|-----|-----|------|
| Surya Orange | सूर्य | `#EF7522` | 239/117/34 | Primary — CTAs, buttons, key interactions |
| Prithvi Teal | पृथ्वी | `#129E9D` | 18/158/157 | Secondary — informational accents, data visualization |
| Padma Magenta | पद्म | `#BA2060` | 186/32/96 | Accent — active states, sidebar indicators, emphasis |
| Shweta White | श्वेत | `#FFFFFF` | 255/255/255 | Surface — cards, modals, elevated content |
| Ksheer Ivory | क्षीर | `#F8F3E8` | 248/243/232 | Background — light mode page background |
| Shyam Black | श्याम | `#151515` | 21/21/21 | Background — dark mode page background, light mode text |

### Semantic Color Mapping

| Token | Light Mode | Dark Mode |
|-------|-----------|-----------|
| `--primary` | Surya Orange | Surya Orange (brightened) |
| `--primary-foreground` | White | Dark |
| `--secondary` | Prithvi Teal | Prithvi Teal (brightened) |
| `--accent` | Padma Magenta | Padma Magenta (brightened) |
| `--background` | Ksheer Ivory `#F8F3E8` | Shyam Black `#151515` |
| `--foreground` | Shyam Black `#151515` | Ksheer Ivory `#F8F3E8` |
| `--card` | Shweta White `#FFFFFF` | Slightly lighter than `#151515` |
| `--destructive` | Red (not a brand color) | Red (brightened) |

### Color Pairing Rules

- Orange + Teal: high contrast pair, use for primary + secondary actions
- Orange + Magenta: warm pair, use sparingly for emphasis
- Teal + Magenta: cool pair, works well in data visualization
- All three brand colors pair well with both Ivory and Black backgrounds
- Cards (white) on Ivory background create subtle depth layering

### Chart Colors (Data Visualization)

A 5-color palette derived from the brand:

1. Surya Orange (primary data)
2. Prithvi Teal (secondary data)
3. Padma Magenta (tertiary data)
4. Orange shade — lighter/darker variant
5. Teal shade — lighter/darker variant

### Application Rules

- Always use semantic Tailwind tokens (`bg-primary`, `text-foreground`), never hardcoded hex values in components
- Use `oklch()` color space for all new color definitions to maintain perceptual uniformity
- Primary color for CTAs and interactive elements
- Secondary color for informational highlights
- Accent color for active/selected states and emphasis
- Destructive actions use the destructive token, not brand colors

## Typography

### Approved Fonts (ONLY these two)

| Role | Font Family | CSS Variable | Usage |
|------|-------------|-------------|-------|
| Primary Sans | Geist Sans | `--font-sans` | ALL text — body, headings, UI, navigation |
| Monospace | Geist Mono | `--font-mono` | Code blocks, technical values, timestamps |

**Do NOT use any other font families.** DM Sans, Literata, Inter, and all other typefaces are explicitly not approved. Do not introduce additional font families without design team approval.

### Type Scale

Base size: 16px (1rem). All sizes use Tailwind utilities.

| Level | Size | Weight | Line Height | Usage |
|-------|------|--------|-------------|-------|
| Display | text-4xl+ | 500-700 | 1.2 | Hero headings, landing pages |
| H1 | text-2xl | 500 | 1.5 | Page titles |
| H2 | text-xl | 500 | 1.5 | Section headings |
| H3 | text-lg | 500 | 1.5 | Subsection headings |
| H4 | text-base | 500 | 1.5 | Card titles, labels |
| Body | text-base | 400 | 1.5 | Paragraphs, descriptions |
| Small | text-sm | 400 | 1.5 | Captions, helper text |
| Tiny | text-xs | 400 | 1.5 | Badges, timestamps |
| Code | text-sm | 400-700 | 1.5 | Code, technical data |

### Weight Guidelines

- 400 (normal): body text, descriptions, inputs
- 500 (medium): headings, labels, buttons, navigation
- 600 (semibold): emphasis within text, strong headings
- 700 (bold): hero display text, key metrics

## Theming

### Light Mode

- Page background: Ksheer Ivory `#F8F3E8` — warm, not clinical white
- Cards/surfaces: Shweta White `#FFFFFF` — creates depth layering on ivory
- Text: Shyam Black `#151515`
- Borders: subtle, low-opacity black
- The subtle warmth of ivory distinguishes SoW products from generic white-background apps

### Dark Mode

- Page background: Shyam Black `#151515` — deep but not pure black
- Cards/surfaces: slightly lighter than `#151515` for depth
- Text: Ksheer Ivory `#F8F3E8`
- Borders: subtle, low-opacity white
- Brand colors (orange, teal, magenta) are slightly brightened for contrast on dark backgrounds

### Theme Switching

Uses `next-themes` with `attribute="class"` and `defaultTheme="system"`. The `.dark` class on `<html>` triggers dark mode CSS variable overrides.

## Spacing & Layout

### Border Radius

Base: `0.625rem` (10px)

| Token | Value | Usage |
|-------|-------|-------|
| `rounded-sm` | 6px | Small elements (badges, chips) |
| `rounded-md` | 8px | Inputs, small buttons |
| `rounded-lg` | 10px | Cards, containers (default) |
| `rounded-xl` | 14px | Modals, large cards |
| `rounded-2xl` | 18px | Hero sections, feature cards |

### Spacing

Uses Tailwind's default spacing scale (4px base). Key conventions:

- Card padding: `p-6` (24px)
- Section gaps: `gap-6` to `gap-8`
- Container: `mx-auto px-6`
- Component internal gaps: `gap-1.5` to `gap-4`

## Component Patterns

### Cards

- Background: `bg-card` (white in light mode, dark surface in dark mode)
- Border: `border` (subtle, uses `--border` token)
- Radius: `rounded-xl`
- Padding: `px-6 pt-6` header, `px-6` content, `px-6 pb-6` footer
- Shadow: none by default (depth comes from ivory vs white layering)

### Sidebar

- Active item: Padma Magenta vertical bar on the left edge (3px border-left)
- Active text: `font-medium`
- Hover: subtle background highlight using `--sidebar-accent`
- Navigation icons: 20px, aligned with text

### Buttons

Follow CVA (Class Variance Authority) pattern with variants:

| Variant | Background | Text | Usage |
|---------|-----------|------|-------|
| default | `bg-primary` (Surya Orange) | White | Primary CTAs |
| secondary | `bg-secondary` | Dark | Secondary actions |
| outline | transparent + border | Foreground | Tertiary actions |
| ghost | transparent | Foreground | Inline actions |
| destructive | `bg-destructive` | White | Dangerous actions |
| link | transparent | Primary | Navigation links |

### Tab Navigation

- Active tab: filled background with `bg-primary` (Surya Orange) + white text
- Inactive tabs: transparent with subtle border, dark text
- Uses pill/rounded-full shape for tab indicators

## Background Patterns & Tile Pattern

### Geometric Dot Grid

A subtle background pattern using three shape types arranged in a grid:

- **Shapes**: circles, squares (rounded), and hexagons
- **Color**: `#F5F5F5` at 90% opacity on white background
- **Usage**: Applied as `background-image` with `background-repeat` on page sections
- **Asset**: `/brand/bg-pattern.svg`

### Tile Patterns

Two tile patterns are available for use in hero sections and feature backgrounds:

| Pattern | Path | Usage |
|---------|------|-------|
| Design pattern | `/brand/patterns/design-pattern.png` | Design-themed sections |
| Agentic pattern | `/brand/patterns/agentic-pattern.png` | Engineering/AI sections |

### Usage Rules

- Patterns are used as subtle texture, never as dominant visual elements
- Apply with `background-image` + `background-repeat`, not as inline SVGs
- Reduce opacity to 5-15% when used over colored backgrounds
- Never use patterns as the sole visual treatment — combine with typography and brand colors

```css
.pattern-bg {
  background-image: url('/brand/bg-pattern.svg');
  background-repeat: repeat;
  background-size: 760px 474px;
}
```

## Brand Assets

All brand assets are in `public/brand/`. See `public/brand/ASSETS.md` for the full inventory.

### Core

| Asset | Path | Purpose |
|-------|------|---------|
| Wordmark logo | `/brand/logo.svg` | Full "Shades of Web" logotype with three shape marks |
| Favicon | `/brand/favicon.svg` | Browser tab icon — orange hexagon |
| Footer logo | `/brand/footer-logo.png` | Footer branding |
| Brand icon composite | `/brand/SoW_brand_icons.svg` | Three shapes + wordmark combined |
| Background pattern | `/brand/bg-pattern.svg` | Geometric dot grid texture |

### Shapes (Three Core Primitives)

| Shape | Path | Color | Hex |
|-------|------|-------|-----|
| Circle (Bindu) | `/brand/shapes/circle.svg` | Surya Orange | `#EF7522` |
| Square (Yantra) | `/brand/shapes/square.svg` | Prithvi Teal | `#129E9D` |
| Hexagon (Sutra) | `/brand/shapes/hexagon.svg` | Padma Magenta | `#BA2060` |

### Patterns

| Asset | Path |
|-------|------|
| Design pattern | `/brand/patterns/design-pattern.png` |
| Agentic pattern | `/brand/patterns/agentic-pattern.png` |

### Feature Icons

| Asset | Path |
|-------|------|
| Sun icon | `/brand/icons/icon-sun.png` |
| Intelligent icon | `/brand/icons/icon-intelligent.png` |
| Wind icon | `/brand/icons/icon-wind.png` |

### Industry Icons

| Asset | Path |
|-------|------|
| Business | `/brand/icons/business.png` |
| Consumer | `/brand/icons/consumer.png` |
| Energy | `/brand/icons/energy.png` |
| Financial | `/brand/icons/financial.png` |
| Healthcare | `/brand/icons/healthcare.png` |
| Public Sector | `/brand/icons/public_sector.png` |
| SoW Icon | `/brand/icons/sow-icon.png` |
| Tech | `/brand/icons/tech.png` |

### Favicon & OG (Next.js App Router metadata)

| Asset | File Path | Served As | Purpose |
|-------|-----------|-----------|---------|
| Favicon ICO | `app/favicon.ico` | `/favicon.ico` | Browser tab icon (48x48, 32x32) |
| SVG icon | `app/icon.svg` | `/icon.svg` | Scalable favicon (orange hexagon) |
| Apple icon | `app/apple-icon.png` | `/apple-icon.png` | iOS home screen (180x180) |
| OG image | `app/opengraph-image.jpg` | `/opengraph-image.jpg` | Social media preview (1200x630) |

## Motion & Animation

### Easing

Standard cubic-bezier: `cubic-bezier(0.16, 1, 0.3, 1)` — smooth deceleration curve.

### Animations

| Name | Duration | Usage |
|------|----------|-------|
| reveal-up | 1s | Text and content appearing from below (clip/translate) |
| enter-from-bottom | 1s | Elements fading in from 40px below |
| subtle-float | 20s | Decorative elements with gentle floating motion |
| marquee | 60s | Continuous horizontal scroll for ticker/showcase |

### Staggered Delays

Content groups use staggered animation delays for sequential reveal:
- 100ms, 200ms, 300ms, 500ms, 700ms

### Transitions

- Default transition: `transition-all duration-150 ease` for interactive states
- Hover/focus: immediate feedback, no perceptible delay

## Brand Voice

- **Clear**: No jargon without explanation. Technical when needed, never obscure.
- **Concise**: Say it once, say it well. Eliminate redundancy.
- **Confident**: Affirmative statements, not hedging language.
- **Human**: Conversational tone, not corporate speak. Personality is welcomed.

## Accessibility

- **WCAG AA minimum** for all text contrast ratios
- All interactive elements must be keyboard accessible
- Use semantic HTML (`button`, `nav`, `main`, `section`, `article`)
- Add ARIA labels where semantic HTML is insufficient
- All images require meaningful `alt` text
- Focus indicators must be visible and use brand colors (ring token)
- Never rely on color alone to convey information

## Imagery Direction

- Draw from cultural depth with a touch of playful drama
- High contrast, narrative compositions
- Emotion meets structure — clarity without losing depth
- Indian cultural motifs and art references are appropriate and encouraged
- Avoid generic stock photography; prefer illustrated or art-directed imagery

## Motifs

The brand includes a library of geometric motifs composed from the three core shapes. These motifs are modular expressions — not decorative marks — and can be used as:

- Section dividers or background elements
- Icon accents within the brand color palette
- Pattern fills for cards or hero sections

Motifs always use brand colors: Surya Orange, Prithvi Teal, Padma Magenta, or neutral grays.

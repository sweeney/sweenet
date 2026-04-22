# swee.net Brand Reference

Machine-readable companion to [styleguide.html](styleguide.html). Use this when building apps or generating UI for swee.net properties.

---

## Identity

- Site/brand name: **swee.net** — always lowercase, always with the dot
- Mascot: barn swallow (*Hirundo rustica*) — rendered monochrome only
- Voice: personal, restrained, serif — not a tech product

---

## Design Principles

- **Restrained** — one accent colour, generous whitespace, nothing decorative that isn't doing work
- **Warm serif** — Georgia grounds the brand in long-form reading; not a tech sans, a personal considered voice
- **Teal as signal** — the brand teal is rare and intentional; it marks structure and identity, not decoration
- **Monochrome motifs** — imagery (the swallow) runs desaturated; colour lives in the brand, not photography

---

## Colours

| Token | Hex | Usage |
|---|---|---|
| Brand Teal | `#02aaa2` | Primary identity: topbar strip, active state, h1 background, app tint |
| Teal Dark | `#017f79` | Hover, pressed, focus ring |
| Teal Light | `#b2e8e6` | Selection highlight, subtle tints |
| Teal Muted | `#e0f5f4` | Callout backgrounds, table row tints |
| Ink | `#222` | Display text, headings |
| Body | `#444` | Body copy, default text |
| Muted | `#888` | Labels, captions, secondary text |
| Rule | `#ccc` | Dividers, borders, input strokes |
| Background | `#eee` | Page background, secondary surfaces |
| White | `#fff` | Cards, modals, text on teal |

Never introduce colours outside this set without explicit approval.

---

## Typography

- **Primary:** Georgia, serif (system font — no web font requests)
- **Monospaced:** Menlo, monospace (labels, captions, code)
- **Weights used:** normal (400) only for display/headings; bold (700) for body emphasis only
- Display headings are **always** `font-weight: normal`

| Role | Size | Family | Leading |
|---|---|---|---|
| Display | 5rem | Georgia | 1.0 |
| Heading 1 | 2.5rem | Georgia | 1.1 |
| Heading 2 | 1.5rem | Georgia | 1.2 |
| Heading 3 | 1.125rem | Georgia | 1.3 |
| Body | 1rem | Georgia | 1.6 |
| Small | 0.875rem | Georgia | 1.5 |
| Caption | 0.75rem | Menlo | 1.4 |
| Label | 0.7rem | Menlo | 1.0, uppercase, tracked 0.12em |

---

## Topbar Strip

Every app surface has a thin teal strip at the very top, inset horizontally by `1ex`. It is the minimal brand mark — a seam, not a banner.

- Height: 8–10px
- Colour: Brand Teal (`#02aaa2`)
- Inset: `1ex` left and right (do not run edge-to-edge)

---

## Spacing

Base unit: **4px**. All spacing values are multiples of 4.

| Token | Value | Use |
|---|---|---|
| xs | 4px | Icon padding, tight inline gaps |
| sm | 8px | Inline spacing |
| md | 16px | Component padding |
| lg | 24px | Section gaps |
| xl | 48px | Page sections |
| 2xl | 96px | Hero margins |

---

## Wordmark

The wordmark is the brand name in Georgia at normal weight. Rules:
- Never bold
- Never all-caps
- Never altered or stylised

Approved treatments:
- White text on Brand Teal background — primary
- White text on Ink (`#222`) background — dark contexts
- Brand Teal text on light background — inline/subtle

---

## UI Patterns

**Buttons:**
- Primary: Brand Teal background, white text
- Secondary: transparent, Brand Teal border and text
- Ghost: transparent, Rule (`#ccc`) border, Body (`#444`) text

**Inputs:**
- Border: Rule (`#ccc`), 1.5px
- Focus border: Brand Teal (`#02aaa2`)
- Font: Georgia 1rem
- Background: white

**Border radius:** 3–4px (subtle, not pill-shaped)

---

## Platform Implementation

**Web**
- Georgia from system stack — no `@font-face`
- Page background `#eee`, card/surface background `#fff`
- Max content width: 880px, centred
- Base: `font: 1em/1.6 Georgia, serif`

**iOS**
- App tint colour: `#02aaa2`
- Map `#eee` → `systemGroupedBackground`
- Map `#fff` → `secondarySystemGroupedBackground`
- Use `UIFont(name: "Georgia", size: ...)` — available on all iOS versions
- Topbar strip: thin view pinned to safe area top
- Scale font sizes with Dynamic Type using relative sizing

**macOS**
- App accent colour: `#02aaa2` (set in Assets.xcassets)
- `NSColor(calibratedRed: 0.008, green: 0.667, blue: 0.635, alpha: 1)` for teal in code
- Window backgrounds use system `NSColor.windowBackgroundColor`
- SwiftUI: `.font(.custom("Georgia", size: ...))`
- Topbar strip: thin `NSView` or SwiftUI `Rectangle` at top of main window content area

---

## Icons & Favicons

The icon is a single serif letter on a plain white square. No teal, no decoration — the brand colour lives in the surrounding UI, not inside the icon.

**Design rules:**
- Letter: "s" from the domain name
- Case: lowercase for web favicon; uppercase "S" for native app icons (better legibility at small sizes)
- Typeface: Times / Georgia, serif
- Weight: normal for SVG favicon; heavier cut in the PNG set for small-size clarity
- Background: white (`#fff`) — never teal, never transparent
- Letter fills ~75% of the canvas
- Export icons as plain squares — macOS/iOS apply corner rounding at the system level; never pre-round

**Web favicon:**
- File: `favicon.svg`
- SVG scales to any size with no raster artefacts
- Reference: `<link rel="icon" href="favicon.svg" type="image/svg+xml">`

**macOS app icon sizes (PNG):**

| File | Size | Retina use |
|---|---|---|
| `icons/AppIcon-16.png` | 16×16 | 1× 16pt |
| `icons/AppIcon-32.png` | 32×32 | 2× 16pt / 1× 32pt |
| `icons/AppIcon-64.png` | 64×64 | 2× 32pt |
| `icons/AppIcon-128.png` | 128×128 | 1× 128pt |
| `icons/AppIcon-256.png` | 256×256 | 2× 128pt / 1× 256pt |
| `icons/AppIcon-512.png` | 512×512 | 2× 256pt |
| `icons/AppIcon-1024.png` | 1024×1024 | App Store / 2× 512pt |

---

## Imagery

- The swallow is always monochrome — never full colour
- Photography used alongside brand elements should be desaturated
- Colour lives in the brand palette, not in imagery
- Give images generous negative space; avoid tight crops and heavy overlays

---

## Assets & Downloads

All brand assets are in the `sweeney/sweenet` GitHub repository.

| File | Use | Format |
|---|---|---|
| `swallow-mono.png` | Hero / landscape swallow | PNG, monochrome |
| `swallow-mono-sq.png` | Square crop (avatars, thumbnails) | PNG, monochrome |
| `swallow.png` | Colour source — internal use only, do not publish | PNG, colour |
| `favicon.svg` | Web favicon | SVG |
| `icons/AppIcon-{size}.png` | macOS / iOS app icon set | PNG, 16–1024px |

**Download a single file:**
```
curl -O https://raw.githubusercontent.com/sweeney/sweenet/main/swallow-mono.png
curl -O https://raw.githubusercontent.com/sweeney/sweenet/main/icons/AppIcon-1024.png
```

**Clone everything:**
```
git clone https://github.com/sweeney/sweenet
```

# Saline Design System

> Inspired by editorial wellness e-commerce references ([Fensea concept site](https://fensea.webflow.io/#Bestsellers)). This document describes an **original** system — not a clone of any single product.

## Value

Saline provides a reusable visual language for premium body-care, wellness, and ingredient-forward brands. It optimizes for editorial storytelling, tactile product presentation, and calm confidence — letting typography, soft surfaces, and restrained motion carry the experience instead of dense UI chrome.

## Intent

- Communicate natural ingredients and ritual through spacious layouts and layered atmospheric backgrounds
- Guide users with scroll-driven narrative sections and clear product hierarchy
- Support conversion through minimal, inline forms and confident accent CTAs
- Remain implementable in modern stacks (CSS custom properties, semantic HTML, accessible components)

## Boundaries

- **Do not** reproduce the Fensea brand, Halo Lab assets, proprietary illustrations, exact page compositions, or marketing copy from the reference
- **Do not** use Adobe Typekit fonts (`roc-grotesk`, `nimbus-sans`) in shipped products without licensing; use the open alternatives listed below
- **Do not** replicate scroll-parallax choreography or WebGL displacement effects pixel-for-pixel; treat motion as inspiration for timing and easing only
- This system is a **starting blueprint**, not a finished brand identity

---

## Design Principles

1. **Atmospheric calm** — Light neutral surfaces with soft color blooms and grain create depth without heavy shadows. *(Observed: blur SVG backgrounds, noise overlay, `#f4f4f4` base)*

2. **Editorial type at scale** — Large uppercase display headings paired with relaxed body copy establish hierarchy through size and weight, not decoration. *(Observed: 5.5rem hero, 4rem section titles)*

3. **Mineral accent discipline** — A single menthol-teal accent signals action, links, and interactive affordances; neutrals carry everything else. *(Observed: `#07b98a` on buttons, underlines, scrollbar)*

4. **Motion with purpose** — Transitions are slow and eased; hover states reveal through vertical text slides and subtle scale. Scroll sections cross-fade content rather than jumping. *(Observed: 0.4–1.5s transitions, overflow text animation)*

5. **Product as artifact** — Cards use generous whitespace, benefit labels in small caps, and hover reveals that feel tactile — not grid-dense catalog rows. *(Observed: horizontal swiper, overheading labels, line dividers)*

6. **Human credibility** — Founder attribution, circular avatars, and testimonial blocks anchor claims in people. *(Observed: parallax founder blocks)*

7. **Accessible first** — Strong text contrast, visible focus rings, reduced-motion fallbacks, and 44px minimum touch targets are non-negotiable even when motion is expressive.

8. **Legal originality** — Patterns are generalized; tokens and components are named and structured independently of any source repository.

---

## Design Tokens

Confidence tags: **Observed** = visible in reference | **Likely** = strongly implied | **Inferred** = reasonable assumption | **Unknown** = not verifiable

### Colors

| Token | Value | Usage | Confidence |
|-------|-------|-------|------------|
| `--color-surface-base` | `#f4f4f4` | Page background, preloader | Observed |
| `--color-surface-elevated` | `#ffffff` | Inputs, cards, modals | Observed |
| `--color-surface-inverse` | `#3d3d3d` | Footer bar, dark overlays | Observed |
| `--color-text-primary` | `#3d3d3d` | Body copy, headings | Observed |
| `--color-text-muted` | `rgba(61, 61, 61, 0.8)` | Secondary descriptions | Observed |
| `--color-text-subtle` | `rgba(61, 61, 61, 0.25)` | Overhead labels, inactive meta | Observed |
| `--color-text-inverse` | `#ffffff` | Text on accent/dark surfaces | Observed |
| `--color-accent-primary` | `#07b98a` | Primary CTA, links, scrollbar | Observed |
| `--color-accent-primary-hover` | `#06a67c` | CTA hover (darkened ~8%) | Inferred |
| `--color-border-default` | `rgba(61, 61, 61, 0.2)` | Header rule, dividers | Observed |
| `--color-border-light` | `rgba(0, 0, 0, 0.1)` | Product separators | Observed |
| `--color-overlay-modal` | `rgba(35, 35, 35, 0.9)` | Modal backdrop | Observed |
| `--color-feedback-error` | `#ea384c` | Form errors | Likely (Webflow default) |
| `--color-feedback-success` | `#07b98a` | Success states (accent reuse) | Inferred |
| `--color-bloom-mint` | `#a8e6cf` | Decorative blur blobs | Likely |
| `--color-bloom-blue` | `#b8d4e8` | Decorative blur blobs | Likely |

**Semantic mapping**

- `--color-interactive`: `--color-accent-primary`
- `--color-interactive-text`: `--color-text-inverse`
- `--color-focus-ring`: `--color-accent-primary` at 2px offset

### Typography

| Token | Value | Confidence |
|-------|-------|------------|
| `--font-display` | `"Space Grotesk", system-ui, sans-serif` | Inferred (open substitute for roc-grotesk) |
| `--font-body` | `"Work Sans", system-ui, sans-serif` | Inferred (open substitute for nimbus-sans) |
| `--font-size-root` | `18px` | Observed |
| `--font-size-xs` | `0.77rem` (~13.9px) | Observed (labels) |
| `--font-size-sm` | `0.88rem` (~15.8px) | Observed (footer) |
| `--font-size-base` | `1rem` (18px) | Observed |
| `--font-size-md` | `1.11rem` (~20px) | Observed (submit btn) |
| `--font-size-lg` | `1.22rem` (~22px) | Observed (body/p) |
| `--font-size-xl` | `1.44rem` (~26px) | Observed (h4) |
| `--font-size-2xl` | `1.77rem` (~32px) | Observed (h3) |
| `--font-size-3xl` | `4rem` (~72px) | Observed (h2) |
| `--font-size-4xl` | `5.5rem` (~99px) | Observed (h1) |
| `--font-size-rank` | `4.88rem` (~88px) | Observed (product numbers) |
| `--font-weight-light` | `300` | Observed (body) |
| `--font-weight-regular` | `400` | Observed |
| `--font-weight-medium` | `500` | Observed (headings, CTAs) |
| `--font-weight-bold` | `700` | Observed (labels, badges) |
| `--line-height-tight` | `1em` | Observed (display) |
| `--line-height-snug` | `1.1em` | Observed (h3–h4) |
| `--line-height-relaxed` | `1.5` (150%) | Observed (body) |
| `--line-height-ui` | `1.6em` | Observed (nav) |
| `--letter-spacing-tight` | `-0.03em` | Observed (body) |
| `--letter-spacing-normal` | `0.02em` | Observed (cart, links) |
| `--letter-spacing-wide` | `0.2em` | Observed (labels, badges) |

**Type scale roles**

| Role | Font | Size | Weight | Transform | Line height |
|------|------|------|--------|-----------|-------------|
| Display / Hero | Display | `--font-size-4xl` | 500 | uppercase | tight |
| Section title | Display | `--font-size-3xl` | 500 | uppercase | tight |
| Card title | Display | `--font-size-2xl` | 500 | none | snug |
| Subheading | Display | `--font-size-xl` | 500 | none | snug |
| Body | Body | `--font-size-lg` | 300 | none | relaxed |
| UI / Nav | Body | `--font-size-base`–`1.2em` | 300–500 | none | ui |
| Overline / Label | Body | `--font-size-xs` | 700 | uppercase | ui |
| Rank number | Display | `--font-size-rank` | 400 | none | tight |

### Spacing

Base unit: **1rem = 18px** (Observed)

| Token | Value | Typical use | Confidence |
|-------|-------|-------------|------------|
| `--space-1` | `0.11rem` | Micro gaps (brackets) | Observed |
| `--space-2` | `0.2rem` | Tight vertical rhythm | Observed |
| `--space-3` | `0.66rem` | Avatar margin | Observed |
| `--space-4` | `0.88rem` | Input gaps, heading margin | Observed |
| `--space-5` | `1.33rem` | Label margin-bottom | Observed |
| `--space-6` | `1.7rem` | Header padding | Observed |
| `--space-7` | `2.22rem` | Column padding | Observed |
| `--space-8` | `2.5rem` | CTA spacing | Observed |
| `--space-9` | `2.66rem` | Button horizontal padding | Observed |
| `--space-10` | `3.3rem` | Nav link margins | Observed |
| `--space-11` | `3.6rem` | Hero heading margin | Observed |
| `--space-12` | `4rem` | Footer section gaps | Observed |
| `--space-13` | `4.5rem` | Footer columns | Observed |
| `--space-14` | `4.8rem` | Footer top section | Observed |
| `--space-15` | `5rem` | Column top margin | Observed |
| `--space-16` | `5.5rem` | Section padding, sticky offset | Observed |
| `--space-17` | `6.1rem` | Footer padding-top | Observed |
| `--space-18` | `10rem` | Hero bottom padding | Observed |
| `--space-19` | `10.5rem` | Hero top padding | Observed |
| `--space-gutter` | `20px` | Section horizontal inset | Observed |

### Radius

| Token | Value | Usage | Confidence |
|-------|-------|-------|------------|
| `--radius-none` | `0` | Inputs, sharp editorial blocks | Observed |
| `--radius-full` | `50%` | Avatars, circular badges, play buttons | Observed |
| `--radius-pill` | `9999px` | Tags (if needed) | Inferred |

### Shadows

Saline relies on **color blooms and borders** more than box shadows.

| Token | Value | Usage | Confidence |
|-------|-------|-------|------------|
| `--shadow-none` | `none` | Default surfaces | Observed |
| `--shadow-subtle` | `0 1px 0 rgba(0,0,0,0.06)` | Optional card lift | Inferred |
| `--shadow-modal` | none (overlay provides depth) | Modals | Observed |

### Motion

| Token | Value | Usage | Confidence |
|-------|-------|-------|------------|
| `--duration-instant` | `100ms` | Micro feedback | Inferred |
| `--duration-fast` | `200ms` | Submit opacity, social icons | Observed |
| `--duration-base` | `400ms` | Links, images, default hover | Observed |
| `--duration-moderate` | `500ms` | Image/label transitions | Observed |
| `--duration-slow` | `800ms` | Smooth scroll, sticker hover | Observed |
| `--duration-slower` | `1000ms` | Blur cross-fades, parallax opacity | Observed |
| `--duration-scroll` | `1500ms` | Block entrance | Observed |
| `--duration-ambient` | `3000ms` | Background blob travel | Observed |
| `--ease-default` | `ease` | General transitions | Observed |
| `--ease-out-expo` | `cubic-bezier(0.215, 0.61, 0.355, 1)` | Parallax entrances | Observed |
| `--ease-in-out` | `ease-in-out` | Rotating decorations | Observed |

---

## Layout System

### Grid

| Property | Value | Confidence |
|----------|-------|------------|
| Max content width | `1312px` | Observed |
| Narrow content (parallax) | `1230px` | Observed |
| Form max width | `32.22rem` (~580px) | Observed |
| Column approach | Asymmetric 2–3 column flex | Observed |
| Product carousel | 3 slides visible (Swiper) | Observed |
| Footer | 2-column primary + nested nav grid | Observed |

**Common patterns**

- **Hero**: text column (~40%) + composition column (~60%) with overlapping decorative layers
- **Ingredient tabs**: icon selectors left, slider content right
- **Bestsellers / parallax**: left rank list | center headline + image | right detail blocks
- **Shop**: heading + nav arrows left, horizontal product strip right

### Containers

```css
.container {
  width: 100%;
  max-width: var(--container-max); /* 1312px */
  margin-inline: auto;
  padding-inline: var(--space-gutter); /* 20px */
}

.section {
  padding-block: var(--space-16); /* 5.5rem */
  padding-inline: var(--space-gutter);
}
```

Sticky parallax sections use `min-height: 100vh` with extended scroll height (~250vh) for narrative pacing. *(Observed)*

### Breakpoints

| Name | Width | Behavior | Confidence |
|------|-------|----------|------------|
| `sm` | `< 480px` | Single column, reduced display sizes | Likely |
| `md` | `< 768px` | Stack hero columns, full-width forms | Likely |
| `lg` | `< 1024px` | Root font switches to `1vw` fluid scaling | Observed |
| `xl` | `≥ 1024px` | Full editorial layout, fixed 18px root | Observed |
| `2xl` | `≥ 1312px` | Content capped at container max | Inferred |

Below `1024px`, `html { font-size: 1vw }` creates fluid typography. Clamp display sizes on small screens to preserve readability.

---

## Component Library

### Buttons

**Primary (filled)**

- Structure: label text inside padded container; optional overflow duplicate for hover slide
- Background: `--color-accent-primary`
- Text: `--color-text-inverse`, display font, weight 500
- Padding: ~`2.66rem` horizontal, ~`3.88rem` height in hero context
- Border radius: `--radius-none`
- States:
  - *Default*: solid fill
  - *Hover*: text slides up (`top: 2rem` on duplicate layer) *(Observed pattern)*
  - *Focus*: 2px accent outline, offset 2px
  - *Disabled*: 50% opacity, no pointer events
  - *Loading*: replace label with spinner, maintain dimensions

**Secondary (text link)**

- Structure: inline text with bottom border
- Color: accent; border-bottom 1px accent
- Font: display, 500, ~1.1em
- Hover: overflow text slide (same as nav)

**Icon arrow submit**

- Square rotating background decoration behind arrow icon
- Arrow slides right on hover (`right: -2rem`)
- Used in newsletter/footer forms

**Circular badge CTA**

- ~`6.38rem` circle, uppercase label, wide letter-spacing
- Background image or solid; rotates ~30° at rest
- Hover: scale 1.3, rotate additional 20°

### Inputs

**Text / email field**

- Height: `3.55rem` standard, `3.88rem` in hero inline form
- Background: white, no visible border (border: 0)
- Padding: horizontal `1.44rem` in hero
- Placeholder: transitions to opacity 0 on focus *(Observed)*
- Label above: uppercase, `--font-size-xs`, weight 700, letter-spacing wide

**Inline hero form**

- Flex row: input flex-grow + submit button attached
- Label acts as section CTA copy ("GET THE CATALOGUE" pattern → use original copy)

**Newsletter / modal form**

- Stacked: input full width, icon submit aligned right
- Success: checkmark icon swap; error: `--color-feedback-error` message below

### Cards

**Product card**

- Structure: overline (benefit) → title → product image → vertical divider line at right edge
- Overline: uppercase xs, `--color-text-subtle`, wide tracking
- Title: h4 scale, display font
- Hover: overline darkens to primary text; image may crossfade to alternate *(Observed intent — implement as opacity/scale, not proprietary WebGL)*
- Divider: 1px `--color-border-light`, inset vertically

**Ingredient / feature card**

- Tab selector with crystal/icon thumbnail
- Content: title (h4) + body paragraph + text link
- Slider cross-fade between variants

**Founder attribution block**

- Circular avatar (4.44rem), name + role
- Arrow link button; hover expands underline on name and scales avatar 1.2

**Ranked list item**

- Large rank numeral (4.88rem) + product name
- Rotating "scroll more" circle decoration
- Used in sticky scroll narrative sections

### Navigation

**Header**

- Fixed/absolute top, full width inside container
- 3-zone flex: logo (8.3rem) | centered nav links | cart (8.3rem)
- Bottom border: `--color-border-default`
- Links: no underline default; hover vertical text swap
- Cart: display font, count in parentheses

**Footer nav**

- Grouped columns: "Website map", "Contacts"
- Same overflow hover on links
- Large conversational CTA link (display 4rem, accent underline)

### Tables

Not present in reference. If needed:

- Minimal borders (`--color-border-light`)
- Header: uppercase xs labels
- Row hover: `--color-surface-base` background
- Prefer card lists over dense tables for this system

### Feedback Components

**Alert / inline message**

- Success: accent left border or icon, `--color-surface-base` background
- Error: `#ea384c` text, light red background `#ffdede`
- Padding: `1rem 1.25rem`, no radius

**Modal**

- Full viewport overlay `--color-overlay-modal`
- Content: white or image + form side-by-side
- Close: large hit area, focusable
- Enter/exit: scale from 0.8 + fade *(Observed)*

**Toast** *(Inferred)*

- Bottom center, dark surface inverse, white text, 400ms slide-up

**Badge**

- "NEW!" style: circular, uppercase, on promotional sticker
- Small inline: uppercase xs pill optional

---

## Imagery Guidelines

| Aspect | Guidance | Confidence |
|--------|----------|------------|
| Photography | Clean studio product shots, soft natural light, neutral backgrounds | Observed |
| People | Editorial portraits, direct gaze, minimal styling | Observed |
| Textures | Subtle film grain overlay at low opacity (~5–10%) | Observed |
| Backgrounds | Soft gradient SVG blobs (mint, blue-grey), not photographic | Observed |
| Illustrations | Custom only — use placeholders in prototypes | Required |
| Icons | Simple line icons (Lucide); arrow-right for CTAs | Observed |
| Product cutouts | PNG products floating in whitespace | Observed |
| Tone | Calm, premium, scientific-yet-human | Inferred |

**Placeholder sources**: Unsplash for photography. Do not use reference site asset URLs in production.

**Art direction rules**

- Prefer one hero subject per composition
- Allow elements to bleed outside columns (crystals, blobs)
- Avoid busy patterns behind body text

---

## Motion Guidelines

### Hover

- Nav/button text: duplicate layer slides up 2rem over 400ms
- Arrow buttons: icon exits right, duplicate enters
- Product cards: label color shift + image opacity/transform
- Circular badges: scale + rotate
- Founder avatar: scale 1.2 on adjacent link hover

### Scroll

- Section content fades/slides in when entering viewport
- Sticky sections hold center content while scroll progress swaps panels
- Background blur blobs reposition over long scroll spans (3s transition)
- Smooth scroll ~800ms between anchor targets

### Ambient

- Slow star/circle rotation (20–30s linear/infinite) for decorative marks
- Form submit square morph rotation (5s ease-in-out loop) — use sparingly

### Loading

- Preloader: logo rises from below, blur blob rotates in
- Skeleton: pulse `--color-border-default` on image blocks

### Reduced motion

See Accessibility Guidelines. All scroll-jacking and ambient loops must have static fallbacks.

---

## Accessibility Guidelines

### Color Accessibility

- Body text `#3d3d3d` on `#f4f4f4`: contrast ~9.5:1 — **passes WCAG AAA** for normal text
- Body text on white: ~10.5:1 — **passes AAA**
- Accent `#07b98a` on white for small text: ~2.6:1 — **fails** for body; use accent only for large text, icons, or UI chrome — not small paragraph text
- White on accent `#07b98a`: ~2.6:1 — limit to large button labels (18px+ bold) or increase button contrast by darkening to `#058f6e` (~3.5:1 at large sizes) or use `#3d3d3d` text on mint-tinted buttons for AA compliance
- **Recommendation**: Primary buttons use `#058f6e` background or add `--color-text-primary` on a light mint button variant for small text

### Keyboard Accessibility

- All interactive elements must be focusable in logical DOM order
- Focus ring: 2px solid `--color-accent-primary`, 2px offset — never `outline: 0` without replacement *(Reference removed outline globally — do not copy)*
- Modals: trap focus, Escape closes, return focus to trigger
- Skip link to main content on every page

### Motion Accessibility

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

- Provide non-scroll-jacked linear layout alternative for parallax sections
- Disable ambient rotation and smooth scroll when reduced motion is preferred
- Autoplay video must be muted, pausable, and disabled under reduced motion

### Touch Accessibility

- Minimum target: **44×44px** (circular badges at 6.38rem / ~115px exceed this)
- Space nav links with adequate horizontal padding
- Swiper/carousel: support swipe + visible prev/next buttons

### Typography Accessibility

- Minimum body size: **16px** (system uses 18px root — good)
- Line height body: **1.5** minimum
- Avoid all-caps for long paragraphs; reserve uppercase for display and labels
- Clamp fluid `1vw` sizing so body never drops below 16px on mobile

### Component Accessibility

| Component | Requirements |
|-----------|--------------|
| Forms | `<label>` associated with inputs; announce errors with `role="alert"` |
| Dialogs | `role="dialog"`, `aria-modal="true"`, labelled by heading |
| Navigation | `<nav aria-label="Primary">`; current page `aria-current="page"` |
| Carousels | `aria-roledescription="carousel"`, slide labels, pause autoplay |
| Video play | Button with accessible name ("Play product video") |
| Overflow hover | Ensure visible focus state doesn't depend on hover alone |

---

## Implementation Notes

1. **CSS architecture** — Define all tokens in `:root`. Components consume semantic tokens, not raw hex values.

2. **Font loading** — Load Space Grotesk (500, 700) and Work Sans (300, 400, 500) from Google Fonts with `font-display: swap`.

3. **Fluid root** — At `max-width: 1024px`, prefer `clamp(16px, 1vw, 18px)` over bare `1vw` to protect minimum size.

4. **Overflow hover technique** — Wrapper `overflow: hidden; height: 1lh`. Inner stack of two text layers; translate Y on `:hover` and `:focus-visible`.

5. **Atmospheric layers** — Position blur blobs absolute with `pointer-events: none; z-index: 0`. Content at `z-index: 1+`.

6. **Grain overlay** — `background-image` with repeat, `mix-blend-mode: multiply`, `opacity: 0.05`.

7. **Product hover** — CSS-only fallback: swap image opacity or `transform: scale(1.05)`. Displacement shaders are optional enhancement.

8. **Preview** — Open `preview.html` in a browser to validate tokens and components against this spec.

---

## Do Not Do

- Do not use the Fensea name, logo, crystal illustrations, or Halo Lab footer content
- Do not copy exact hero composition, parallax timing curves, or three-product naming from the reference
- Do not remove focus outlines without accessible replacements
- Do not use accent green for small body text on light backgrounds
- Do not rely on hover-only interactions for essential information
- Do not autoplay video with sound
- Do not ship Adobe Typekit fonts without a license
- Do not generate or clone proprietary SVG artwork — commission originals
- Do not implement scroll-jacking without a reduced-motion escape hatch
- Do not treat this file as legal advice on trade dress — when in doubt, increase differentiation

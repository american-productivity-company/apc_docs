# APC Style Guide

This document defines the shared visual language across APC's web properties: the **marketing website** (`platform/marketing-website/`) and the **enterprise website** (`platform/enterprise-website/`).

---

## Brand Color Palette

### Core Colors

| Name           | Hex       | RGB                  | Usage                          |
|----------------|-----------|----------------------|--------------------------------|
| Sunset Coral   | `#d2553f` | `rgb(210, 85, 63)`   | Primary CTA, buttons, accents  |
| Warm Peach     | `#ff9b7d` | `rgb(255, 155, 125)` | Secondary accent, highlights   |
| Burnt Sienna   | `#c94a36` | `rgb(201, 74, 54)`   | Hover/active states            |
| Cream Light    | `#fff8f3` | `rgb(255, 248, 243)` | Primary background             |
| Warm Sand      | `#d4a574` | `rgb(212, 165, 116)` | Tertiary accent                |
| Rich Brown     | `#6b3825` | `rgb(107, 56, 37)`   | Primary text color             |
| Brown Light    | `#8f6047` | `rgb(143, 96, 71)`   | Secondary text                 |

### Opacity Variants

| Token              | Value                          | Usage                       |
|--------------------|--------------------------------|-----------------------------|
| Brown 70%          | `rgba(107, 56, 37, 0.7)`      | Secondary/muted text        |
| Brown 45%          | `rgba(107, 56, 37, 0.45)`     | Placeholder text            |
| Brown 16%          | `rgba(107, 56, 37, 0.16)`     | Borders, dividers           |
| Coral 12% (wash)   | `rgba(210, 85, 63, 0.12)`     | Secondary button background |
| Coral 18% (wash)   | `rgba(210, 85, 63, 0.18)`     | Accent backgrounds          |
| Sand 20% (wash)    | `rgba(212, 165, 116, 0.2)`    | Subtle sand accents         |

### CSS Variable Names

Both projects use these shared brand variables:

```css
--color-sunset-coral: #d2553f;
--color-warm-peach: #ff9b7d;
--color-burnt-sienna: #c94a36;
--color-cream-light: #fff8f3;
--color-warm-sand: #d4a574;
--color-rich-brown: #6b3825;
--color-rich-brown-70: rgba(107, 56, 37, 0.7);
--color-rich-brown-45: rgba(107, 56, 37, 0.45);
--color-rich-brown-16: rgba(107, 56, 37, 0.16);
--color-coral-12: rgba(210, 85, 63, 0.12);
--color-coral-wash: rgba(210, 85, 63, 0.18);
```

### Dark Mode

Dark mode swaps background and foreground values while keeping coral as the primary accent:

| Token       | Light               | Dark                         |
|-------------|---------------------|------------------------------|
| Background  | Cream `#fff8f3`     | Brown `#6b3825`              |
| Foreground  | Brown `#6b3825`     | Cream `#fff8f3`              |
| Borders     | Brown 16% opacity   | Cream 16% opacity            |
| Primary     | Coral `#d2553f`     | Coral `#d2553f` (unchanged)  |
| Muted text  | Brown 70% opacity   | Cream 70% opacity            |

Dark mode is class-based (`.dark` on `<html>`) via `next-themes`.

---

## Typography

### Font Family

**Manrope** is the sole typeface across both properties.

```css
font-family: var(--font-manrope), 'Manrope', sans-serif;
```

Loaded via Next.js Google Fonts with `display: swap`. The CSS variable `--font-manrope` is set on the `<html>` element.

### Font Weights

| Weight | Value | Usage                  |
|--------|-------|------------------------|
| Regular | 400  | Rarely used directly   |
| Medium  | 500  | Body text, labels      |
| Semibold| 600  | Subheadings, emphasis  |
| Bold    | 700  | Headings (H2-H6)      |
| Black   | 800  | Display / H1           |

### Type Scale (Marketing Website)

The marketing site uses fluid typography with `clamp()`:

| Style   | Size                                              | Weight | Line Height |
|---------|----------------------------------------------------|--------|-------------|
| Display | `clamp(2.75rem, 2.25rem + 2.5vw, 4.5rem)`         | 800    | 1           |
| H1      | `clamp(2.75rem, 2.25rem + 2.5vw, 4.5rem)`         | 800    | 1           |
| H2      | `clamp(2.25rem, 2.036rem + 1.07vw, 3rem)`          | 700    | 1           |
| H3      | `clamp(2rem, 1.858rem + 0.71vw, 2.5rem)`           | 700    | 1.3         |
| H4      | `clamp(1.75rem, 1.678rem + 0.36vw, 2rem)`          | 700    | 1.3         |
| H5      | `1.5rem`                                            | 700    | 1.3         |
| H6      | `1rem`                                              | 700    | 1.3         |
| Large   | `1.5rem`                                            | 700    | 1.3         |
| Main    | `1rem` (16px)                                       | 500    | 1.5         |
| Small   | `0.875rem` (14px)                                   | 500    | 1.5         |

### Type Scale (Enterprise Website)

The enterprise site uses Tailwind's standard scale:

| Element         | Class           | Size      | Weight   |
|-----------------|-----------------|-----------|----------|
| Card Title      | `text-2xl`      | 1.5rem    | Semibold |
| Section Heading | `text-lg`       | 1.125rem  | Semibold |
| Body            | `text-base`     | 1rem      | Medium   |
| Small / Label   | `text-sm`       | 0.875rem  | Medium   |
| Caption / Badge | `text-xs`       | 0.75rem   | Semibold |

### Text Wrapping

- Headings: `text-wrap: balance`
- Body paragraphs: `text-wrap: pretty`

---

## Spacing

### Marketing Website Spacing Scale

Defined as CSS custom properties:

| Token    | Value    | Pixels |
|----------|----------|--------|
| space-1  | 0.25rem  | 4px    |
| space-2  | 0.5rem   | 8px    |
| space-3  | 0.75rem  | 12px   |
| space-4  | 1rem     | 16px   |
| space-5  | 1.5rem   | 24px   |
| space-6  | 2rem     | 32px   |
| space-7  | 3rem     | 48px   |
| space-8  | 4rem     | 64px   |

Section spacing:

| Token         | Value   | Pixels |
|---------------|---------|--------|
| section-small | 5rem    | 80px   |
| section-main  | 7rem    | 112px  |
| section-large | 10rem   | 160px  |

### Enterprise Website

Uses Tailwind's default spacing scale (`p-4` = 16px, `p-6` = 24px, etc.).

---

## Layout & Containers

### Marketing Website

| Container   | Max Width | Pixels |
|-------------|-----------|--------|
| `main`      | 67.5rem   | 1080px |
| `small`     | 67.5rem   | 1080px |
| `full`      | 90rem     | 1440px |
| `header`    | 56rem     | 896px  |

12-column grid with `1rem` gutters and a fluid site margin:
```css
margin: clamp(1rem, -1.928rem + 14.64vw, 11.25rem);
```

### Enterprise Website

Uses Tailwind's container and max-width utilities:
- Modal dialogs: `max-w-lg` (448px)
- Standard breakpoints: `sm` (640px), `md` (768px), `lg` (1024px), `xl` (1280px)

---

## Borders & Radius

### Neo-Brutalist Aesthetic

Both websites use **sharp corners** as the default. Border radius is `0` throughout.

```css
--radius: 0;
```

All interactive elements (buttons, cards, inputs, checkboxes) enforce this:
```css
border-radius: 0 !important;
```

The enterprise website defines Tailwind radius tokens that resolve to near-zero values:
- `rounded-none`: 0px (most common)
- `rounded-sm`: ~2px (used for tabs, select items)
- `rounded-md`: ~4px
- `rounded-lg`: ~8px (used sparingly, e.g., dialog on `sm:` breakpoint)

### Border Widths

- Marketing website: `0.094rem` (~1.5px) as the standard border
- Enterprise website: `2px` as the standard border (buttons, cards, badges)
- Shared border color: Brown 16% opacity (`rgba(107, 56, 37, 0.16)`)

---

## Shadows & Depth

### Offset Shadows (Neo-Brutalist)

Hard-edged offset shadows are a key visual motif:

| Token          | Value                     | Usage                  |
|----------------|---------------------------|------------------------|
| `offset`       | `4px 4px 0 #d2553f`      | Card hover, buttons    |
| `offset-sm`    | `2px 2px 0 #d2553f`      | Button hover state     |
| `offset-brown` | `4px 4px 0 #6b3825`      | Alternate shadow color |

### Glow Effects (Enterprise)

Coral-tinted glow effects for interactive states:

```css
/* Standard glow */
box-shadow:
  inset 0 0 2.5rem rgba(210, 85, 63, 0.15),
  inset 0 0 0.75rem rgba(210, 85, 63, 0.1),
  0 0 2.25rem rgba(210, 85, 63, 0.1);

/* Hover glow (intensified) */
box-shadow:
  inset 0 0 3rem rgba(210, 85, 63, 0.2),
  0 0 3rem rgba(210, 85, 63, 0.15);
```

---

## Buttons

### Marketing Website

Buttons use a custom class structure (`.btn_main_wrap`):
- Padding: `9px 15px`
- No border radius
- Icon animation with directional attribute (`data-direction="left|right"`)

### Enterprise Website (ShadCN + CVA)

All buttons include `border-2` and `transition-all`:

| Variant       | Background         | Text    | Border          | Hover                          |
|---------------|--------------------|---------|-----------------|--------------------------------|
| `default`     | Coral `#d2553f`    | White   | Coral           | Darker coral + offset shadow   |
| `destructive` | Red `#dc2626`      | White   | Red             | Darker red + offset shadow     |
| `outline`     | Transparent        | Brown   | Brown 16%       | Coral wash bg + coral border   |
| `secondary`   | Coral wash (12%)   | Brown   | Transparent     | Coral 20%                      |
| `ghost`       | Transparent        | Brown   | Transparent     | Brown 10%                      |
| `link`        | Transparent        | Coral   | Transparent     | Underline                      |

Sizes:

| Size      | Height | Horizontal Padding |
|-----------|--------|--------------------|
| `default` | 40px   | 16px               |
| `sm`      | 36px   | 12px               |
| `lg`      | 44px   | 32px               |
| `icon`    | 40x40  | -                  |

Active state: `translate(2px, 2px)` with shadow removed (press-down effect).

---

## Cards

### Marketing Website

- Border: `1px solid` Brown 16%
- Background: Cream light
- No border radius
- Hover: `translateY(-4px)` + box-shadow `4px 4px 0 var(--border)`

### Enterprise Website

- Border: `2px solid` Brown 16%
- Background: White
- Header padding: 24px
- Content padding: 24px (no top padding on content section)
- Title: `text-2xl` semibold in brown
- Description: `text-sm` in brown 70%

---

## Form Inputs

### Shared Patterns

- Height: 40px
- Background: White
- Border: Brown 16% opacity
- Focus: Coral border color
- Placeholder: Brown 45% opacity
- Disabled: 50% opacity, `cursor-not-allowed`

### Enterprise Website Specifics

```
border-2 border-brown/16 bg-white
focus:border-coral focus:ring-0
placeholder:text-brown/45
```

### Marketing Website Specifics

```css
border: 1px solid #ccc;
background: #fff;
focus border-color: #d2553f;
placeholder color: #999;
```

---

## Animations

### Shared

- Accordion expand/collapse: `0.2s ease-out`
- Fade in/out, zoom in/out (Radix UI): standard `animate-in`/`animate-out`

### Marketing Website Specific

**Menu open/close** (clip-path reveal):
```css
@keyframes menuOpen {
  from { clip-path: polygon(0 0, 100% 0, 100% 0, 0 0); }
  to   { clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%); }
}
/* Duration: 400ms */
```

**Shimmer wave** (decorative):
```css
@keyframes shimmerWave { /* 14s ease-in-out infinite */ }
@keyframes borderLineWave { /* 14s ease-in-out infinite */ }
```

**Context menu fade**:
```css
@keyframes contextMenuFade {
  from { opacity: 0; transform: translateY(-4px); }
  to   { opacity: 1; transform: translateY(0); }
}
/* Duration: 120ms ease-out */
```

**Spinner**: `rotate(360deg)` over `0.8s` infinite linear.

### Enterprise Website Specific

Transitions default to `transition-all` or `transition-colors` at 200ms. Active button press uses `translate-x-[2px] translate-y-[2px]` with shadow removal.

---

## Responsive Breakpoints

### Marketing Website

| Breakpoint   | Query              |
|--------------|--------------------|
| Desktop      | `min-width: 992px` |
| Tablet       | `max-width: 991px` |
| Mobile       | `max-width: 767px` |
| Small Mobile | `max-width: 479px` |

Also uses container queries: `@container (min-width: 60em)` for nav.

### Enterprise Website (Tailwind)

| Token | Width   |
|-------|---------|
| `sm`  | 640px   |
| `md`  | 768px   |
| `lg`  | 1024px  |
| `xl`  | 1280px  |
| `2xl` | 1536px  |

---

## Navigation

Marketing website nav height: `3.5rem` (56px). Hamburger menu uses a `1.5px` line thickness with `8px` gap and `45deg` rotation on open. Open/close animations are `400ms`.

---

## Accessibility

- **Focus rings**: 2px coral ring with 2px offset (`focus-visible:ring-2 focus-visible:ring-coral focus-visible:ring-offset-2`)
- **Disabled states**: 50% opacity + `cursor-not-allowed` + `pointer-events-none`
- **Screen reader text**: `.u-sr-only` (marketing) / `sr-only` (enterprise)
- **ARIA roles**: Alerts use `role="alert"`, pagination uses `aria-label="pagination"`
- **Line clamping**: `.u-line-clamp-1` through `.u-line-clamp-4` for overflow text

---

## Technology Stack

| Concern         | Marketing Website                    | Enterprise Website                 |
|-----------------|--------------------------------------|------------------------------------|
| CSS Framework   | Tailwind CSS v4 + global CSS vars    | Tailwind CSS v3 + `tailwindcss-animate` |
| Component Lib   | Custom classes (Webflow-origin)      | ShadCN/UI (Radix primitives)       |
| Class Utility   | Direct CSS                           | `clsx` + `tailwind-merge` (`cn()`) |
| Variant System  | CSS class variants / data attributes | `class-variance-authority` (CVA)   |
| Icons           | Custom SVGs                          | Lucide React                       |
| Dark Mode       | `.u-theme-light` / `.u-theme-dark`   | `.dark` class via `next-themes`    |
| Font Loading    | Next.js Google Fonts                 | Next.js Google Fonts               |
| PostCSS         | `@tailwindcss/postcss`               | `autoprefixer`                     |

---

## Design Principles

1. **Neo-Brutalist aesthetic** - Sharp corners (`border-radius: 0`), hard offset shadows, bold borders
2. **Warm earthy palette** - Coral, cream, brown, and sand as the full spectrum
3. **Consistent brand font** - Manrope at all weights, no secondary typeface
4. **High contrast states** - Clear hover, focus, and active feedback on every interactive element
5. **Fluid marketing, fixed app** - The marketing site uses `clamp()` for fluid type/spacing; the enterprise app uses Tailwind's fixed scale for UI predictability

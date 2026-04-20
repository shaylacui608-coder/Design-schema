# Design System — All-in-One Reference

A condensed reference for all four token groups. Each row: token name · value · when to use.

---

## 1. Color

### Semantic — Text

| Token | Value | When to use |
|-------|-------|-------------|
| `--color-text-primary` | `#101011` | Main body text, titles, strong emphasis |
| `--color-text-secondary` | `#64676C` | Secondary labels, supporting text |
| `--color-text-tertiary` | `#95989D` | Hints, meta info, less important content |
| `--color-text-disabled` | `#BCBEC3` | Greyed-out / inactive text |
| `--color-text-placeholder` | `#C5CBD1` | Input placeholder text |
| `--color-text-inverse` | `#FFFFFF` | Text on dark or colored backgrounds |
| `--color-text-link` | `#0088FF` | Clickable links |
| `--color-text-accent` | `#FA6C00` | Highlighted / promotional text |

### Semantic — Background

| Token | Value | When to use |
|-------|-------|-------------|
| `--color-bg-base` | `#FFFFFF` | Card, modal, drawer surface |
| `--color-bg-subtle` | `#FAFBFD` | Alternating table rows |
| `--color-bg-disabled` | `#F2F4F7` | Disabled field fill |
| `--color-bg-elevated` | `#F7F9FC` | Elevated containers, side panels |
| `--color-bg-mask` | `rgba(0,0,0,0.34)` | Modal / drawer backdrop overlay |
| `--color-bg-popper-dark` | `rgba(29,33,41,0.80)` | Dark tooltip, toast |
| `--color-bg-popper-light` | `rgba(255,255,255,0.98)` | Light floating panel |

### Semantic — Border & Divider

| Token | Value | When to use |
|-------|-------|-------------|
| `--color-border-default` | `#D3D9E0` | Default input / card border |
| `--color-border-subtle` | `#EBEDF0` | Light border, disabled state border |
| `--color-divider-default` | `#EBEDF0` | Horizontal rule between sections |
| `--color-divider-light` | `#F0F2F5` | Very light separator inside a panel |

### Semantic — Action

| Token | Maps to | When to use |
|-------|---------|-------------|
| `--color-action-default` | `--color-primary-5` `#0088FF` | Normal interactive element fill |
| `--color-action-hover` | `--color-primary-4` `#4DB2FF` | Hover state fill |
| `--color-action-pressed` | `--color-primary-6` `#006BE5` | Pressed / active state fill |
| `--color-action-disabled` | `--color-primary-3` `#94D1FF` | Disabled interactive fill |
| `--color-action-surface` | `--color-primary-1` `#F0FBFF` | Tinted surface behind an action |

### Semantic — Gradient (use with `background`, not `background-color`)

| Token | When to use |
|-------|-------------|
| `--color-gradient-action-normal` | Primary button — default |
| `--color-gradient-action-hover` | Primary button — hover |
| `--color-gradient-action-active` | Primary button — pressed |
| `--color-gradient-action-disabled` | Primary button — disabled |
| `--color-gradient-warning/success/danger/info` | Status badge / alert backgrounds |

### Functional Scales (primitives — reference only, do not use in component CSS)

| Scale | Step 1 (light bg) | Step 4 (hover) | Step 5 (normal) | Step 6 (active) |
|-------|------------------|----------------|-----------------|-----------------|
| Primary | `#F0FBFF` | `#4DB2FF` | `#0088FF` | `#006BE5` |
| Success | `#EBFAEB` | `#1AB844` | `#00A32B` | `#008F27` |
| Danger | `#FFF1EB` | `#FA5B50` | `#F04330` | `#CC221D` |
| Warning | `#FFF8E6` | `#FF8324` | `#FA6C00` | `#EB4E00` |
| Info | `#F0FBFF` | `#4DB2FF` | `#0088FF` | `#0066DB` |

---

## 2. Font

### Families

| Token | Stack | When to use |
|-------|-------|-------------|
| `--font-family-base` | PingFang SC, Microsoft YaHei, sans-serif | All UI text |
| `--font-family-number` | Helvetica Neue, Helvetica, Arial, sans-serif | Prices, counts, stats |
| `--font-family-code` | SFMono-Regular, Consolas, Menlo, monospace | Code blocks |

### Semantic Composites — Body (weight 400)

| Token prefix | Size / Leading | When to use |
|-------------|---------------|-------------|
| `--font-body-xs-*` | 12px / 18px | Caption, footnote |
| `--font-body-sm-*` | 14px / 22px | Default body text, form field value |
| `--font-body-md-*` | 16px / 24px | Prominent body paragraph |
| `--font-body-lg-*` | 18px / 22px | Large body, sub-heading |
| `--font-body-xl-*` | 20px / 24px | Display body |

### Semantic Composites — Label (weight 500)

| Token prefix | Size / Leading | When to use |
|-------------|---------------|-------------|
| `--font-label-xs-*` | 12px / 18px | Tag, badge text |
| `--font-label-sm-*` | 14px / 22px | Form label, button text |
| `--font-label-md-*` | 16px / 24px | Strong label |
| `--font-label-lg-*` | 18px / 22px | Card title, tab label |
| `--font-label-xl-*` | 20px / 24px | Section label |

### Semantic Composites — Heading (weight 600 for h6; 500 for h1–h5)

| Token prefix | Size / Leading | When to use |
|-------------|---------------|-------------|
| `--font-heading-6-*` | 24px / 28px | Panel heading |
| `--font-heading-5-*` | 28px / 34px | Page sub-title |
| `--font-heading-4-*` | 32px / 38px | Section title |
| `--font-heading-3-*` | 36px / 44px | Page title |
| `--font-heading-2-*` | 40px / 48px | Large title |
| `--font-heading-1-*` | 48px / 58px | Hero / display title |

> Each composite has `-size`, `-weight`, and `-leading` sub-tokens. Always apply all three together.

---

## 3. Layout

### Spacing Scale

| Token | Value | When to use |
|-------|-------|-------------|
| `--space-4` | `4px` | Icon-to-label gap, tightest intra-component gap |
| `--space-8` | `8px` | Button vertical padding, inline element gap |
| `--space-12` | `12px` | Form field internal padding |
| `--space-20` | `20px` | List row gap; boundary between intra / inter module |
| `--space-28` | `28px` | Card-to-card gap |
| `--space-32` | `32px` | Section-to-section separation |
| `--space-36` | `36px` | Large section separation |
| `--space-40` | `40px` | Page-level section gap |

### Safe Distance (mobile 375px)

| Token | Value | When to use |
|-------|-------|-------------|
| `--safe-margin` | `16px` | Outer horizontal margin at screen edges (page wrapper only) |
| `--safe-padding` | `12px` | Inner content padding inside the outer margin (page wrapper only) |

---

## 4. Radius

### Semantic Aliases (use these in component CSS)

| Token | Value | When to use |
|-------|-------|-------------|
| `--radius-button` | `4px` | Button |
| `--radius-input` | `4px` | Input, Select, Textarea |
| `--radius-tag` | `6px` | Tag, Chip, Badge |
| `--radius-card` | `6px` | Card, Panel |
| `--radius-modal` | `12px` | Modal, Dialog |
| `--radius-sheet` | `12px` | Bottom Sheet, Drawer |
| `--radius-avatar` | `20px` | Avatar |
| `--radius-thumbnail` | `20px` | Image thumbnail |

### Scale Primitives (reference only — do not use directly in component CSS)

| Token | Value | When to use |
|-------|-------|-------------|
| `--radius-none` | `0px` | Table cell, flush list item |
| `--radius-xs` | `2px` | Subtle inner element rounding |
| `--radius-sm` | `4px` | Small controls |
| `--radius-md` | `6px` | Medium surfaces |
| `--radius-lg` | `12px` | Large overlays |
| `--radius-xl` | `20px` | Maximum rounding (replaces `50%`) |

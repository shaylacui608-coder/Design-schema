# Layout Tokens

<!-- section-id: overview -->
## Overview

- Governs all spacing between and within UI modules, plus mobile safe-distance margins
- **Two categories:** Spacing scale (8 steps, 4–40px) · Safe distance (mobile 375px viewport)
- Spacing splits into intra-module (4–20px) and inter-module (20–40px); 20px sits at the boundary of both
- Source: Figma node `13:2124`, frame `"Layout(布局)"`, Page 1

---

<!-- section-id: token-definitions -->
## Token Definitions

### Spacing Scale

| CSS Variable | Value | Classification | Usage |
|-------------|-------|---------------|-------|
| `--space-4`  | `4px`  | 模块内 intra-module | Icon padding, tightest gap |
| `--space-8`  | `8px`  | 模块内 intra-module | Inline element gap |
| `--space-12` | `12px` | 模块内 intra-module | Field internal padding |
| `--space-20` | `20px` | 模块内 / 模块间 boundary | List row gap |
| `--space-28` | `28px` | 模块间 inter-module | Card gap |
| `--space-32` | `32px` | 模块间 inter-module | Section separation |
| `--space-36` | `36px` | 模块间 inter-module | Large section separation |
| `--space-40` | `40px` | 模块间 inter-module | Page-level section gap |

### Safe Distance (Mobile 375px)

| CSS Variable | Value | Usage |
|-------------|-------|-------|
| `--safe-margin`  | `16px` | Outer horizontal margin — applied to left & right screen edges |
| `--safe-padding` | `12px` | Inner content padding — inside the outer margin |

---

<!-- section-id: style-composition -->
## Style Composition

```
Component gap  →  --space-{4|8|12|20}       (intra-module)
Section gap    →  --space-{20|28|32|36|40}  (inter-module)
Page edge      →  --safe-margin + --safe-padding
```

| Use case | Token |
|----------|-------|
| Icon-to-label gap | `--space-4` |
| Button internal padding (v) | `--space-8` |
| Form field padding | `--space-12` |
| List row / card internal gap | `--space-20` |
| Card-to-card gap | `--space-28` |
| Section-to-section gap | `--space-32` |
| Page horizontal edge (mobile) | `--safe-margin` (outer) + `--safe-padding` (inner) |

---

<!-- section-id: attribute-variables -->
## Attribute Variables

| CSS Variable | Type | Constraint |
|-------------|------|-----------|
| `--space-{4,8,12,20,28,32,36,40}` | `<length>` | Required for all `margin`, `padding`, `gap` declarations |
| `--safe-margin` | `<length>` | Mobile page-wrapper outer margin only |
| `--safe-padding` | `<length>` | Mobile page-wrapper inner padding only |

---

<!-- section-id: enforcement-rules -->
## Enforcement Rules

1. No raw `px` values for `margin`, `padding`, or `gap` in component CSS — use spacing tokens.
2. Only values on the defined scale (4/8/12/20/28/32/36/40) are permitted; do not interpolate intermediate values.
3. Use intra-module tokens (`--space-4` → `--space-20`) inside a component; use inter-module tokens (`--space-20` → `--space-40`) between components.
4. `--safe-margin` and `--safe-padding` apply only to the outermost page-level wrapper on mobile — never inside components.
5. Do not combine `--safe-margin` and `--safe-padding` as a single value; apply them as separate, nested declarations.

---

<!-- section-id: functional-usage -->
## Functional Usage

```css
/* ✓ Card internal layout */
.card {
  padding: var(--space-12);
  gap: var(--space-8);
}

/* ✓ List rows */
.list-item + .list-item {
  margin-top: var(--space-20);
}

/* ✓ Section separation */
.section + .section {
  margin-top: var(--space-32);
}

/* ✓ Mobile page wrapper */
.page {
  margin-inline: var(--safe-margin);
  padding-inline: var(--safe-padding);
}
```

```css
/* ✗ Raw px value */         .card { padding: 12px; }
/* ✗ Off-scale value */      .card { gap: 10px; }
/* ✗ Safe distance inside */ .btn  { padding-inline: var(--safe-margin); }
```

# Radius Tokens

<!-- section-id: overview -->
## Overview

- Governs all `border-radius` values across the UI
- **Two tiers:** Scale primitives (6 steps, 0–20px) → Semantic aliases (component-intent names)
- Note: 0px was added and 8px was removed in the latest Figma revision (current `--radius-md` = 6px)
- Source: Figma node `5:1258`, frame `"radius "`, Page 1

---

<!-- section-id: token-definitions -->
## Token Definitions

### Scale (Primitive)

| CSS Variable | Value | Figma Token |
|-------------|-------|-------------|
| `--radius-none` | `0px`  | border-radius-1 |
| `--radius-xs`   | `2px`  | border-radius-2 |
| `--radius-sm`   | `4px`  | border-radius-3 |
| `--radius-md`   | `6px`  | border-radius-4 |
| `--radius-lg`   | `12px` | border-radius-5 |
| `--radius-xl`   | `20px` | border-radius-6 |

### Semantic Aliases

| CSS Variable | Maps to | Value | Component |
|-------------|---------|-------|-----------|
| `--radius-button`    | `var(--radius-sm)` | `4px`  | Button |
| `--radius-input`     | `var(--radius-sm)` | `4px`  | Input, Select, Textarea |
| `--radius-tag`       | `var(--radius-md)` | `6px`  | Tag, Chip, Badge |
| `--radius-card`      | `var(--radius-md)` | `6px`  | Card |
| `--radius-modal`     | `var(--radius-lg)` | `12px` | Modal, Dialog |
| `--radius-sheet`     | `var(--radius-lg)` | `12px` | Bottom Sheet, Drawer |
| `--radius-avatar`    | `var(--radius-xl)` | `20px` | Avatar |
| `--radius-thumbnail` | `var(--radius-xl)` | `20px` | Thumbnail, Image |

---

<!-- section-id: style-composition -->
## Style Composition

```
Figma border-radius-N  →  --radius-{none|xs|sm|md|lg|xl}  →  --radius-{component}  →  border-radius: var(--radius-button)
```

| Surface type | Token |
|-------------|-------|
| Table cell, list item (flush) | `--radius-none` |
| Subtle chip, inner element | `--radius-xs` |
| Button, input, small control | `--radius-button` / `--radius-input` |
| Tag, badge | `--radius-tag` |
| Card, panel | `--radius-card` |
| Modal, drawer, bottom sheet | `--radius-modal` / `--radius-sheet` |
| Avatar, image thumbnail | `--radius-avatar` / `--radius-thumbnail` |

---

<!-- section-id: attribute-variables -->
## Attribute Variables

| CSS Variable | Type | Tier | Constraint |
|-------------|------|------|-----------|
| `--radius-{none,xs,sm,md,lg,xl}` | `<length>` | Primitive | Read-only; never used directly in component CSS |
| `--radius-{button,input,tag,card,modal,sheet,avatar,thumbnail}` | `<length>` | Semantic | Required for all `border-radius` in component CSS |

---

<!-- section-id: enforcement-rules -->
## Enforcement Rules

1. No raw `px` values for `border-radius` in component CSS — use semantic tokens.
2. No primitive scale tokens (`--radius-sm`) in component CSS — alias through a semantic token first.
3. `border-radius: 50%` is forbidden — it breaks non-square elements; use `--radius-xl` as the maximum rounding.
4. Do not define new values outside the six-step scale without a design sign-off.
5. `--radius-none` is intentional — do not substitute `0` or `0px` as a literal value.

---

<!-- section-id: functional-usage -->
## Functional Usage

```css
/* ✓ Component usage via semantic tokens */
.btn        { border-radius: var(--radius-button); }
.input      { border-radius: var(--radius-input); }
.tag        { border-radius: var(--radius-tag); }
.card       { border-radius: var(--radius-card); }
.modal      { border-radius: var(--radius-modal); }
.avatar     { border-radius: var(--radius-avatar); }
.thumbnail  { border-radius: var(--radius-thumbnail); }
.table-cell { border-radius: var(--radius-none); }
```

```css
/* ✗ Raw px value */         .btn  { border-radius: 4px; }
/* ✗ Primitive direct */     .btn  { border-radius: var(--radius-sm); }
/* ✗ Forbidden 50% */        .icon { border-radius: 50%; }
/* ✗ Off-scale value */      .card { border-radius: 8px; }
```

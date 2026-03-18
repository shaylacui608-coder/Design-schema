# Color Tokens

<!-- section-id: overview -->
## Overview

- Governs all fills, text, border, background, divider, shadow, and gradient values
- **Two tiers:** Primitive (raw palette, read-only) → Semantic (intent aliases, required in components)
- Six functional scales (Primary, Info, Success, Danger, Warning, Secondary) × 6 steps + Gray (11 steps) + Brand Red
- Source: Figma node `1:367`, frame `"color "`, Page 1

---

<!-- section-id: token-definitions -->
## Token Definitions

### Primitive — Functional Scales

| Step | State | Primary | Info | Success | Danger | Warning | Secondary |
|------|-------|---------|------|---------|--------|---------|-----------|
| 1 | Light bg | `#F0FBFF` | `#F0FBFF` | `#EBFAEB` | `#FFF1EB` | `#FFF8E6` | `#F3F3F4` |
| 2 | Alternate | `#E0F5FF` | `#E0F5FF` | `#B8E5C4` | `#FFE2DB` | `#FFEBC2` | `#D7D7DC` |
| 3 | Disabled | `#94D1FF` | `#94D1FF` | `#83CC8B` | `#FAB4AF` | `#FFD699` | `#B3B2BB` |
| 4 | Hover | `#4DB2FF` | `#4DB2FF` | `#1AB844` | `#FA5B50` | `#FF8324` | `#45445B` |
| 5 | Normal | `#0088FF` | `#0088FF` | `#00A32B` | `#F04330` | `#FA6C00` | — |
| 6 | Active | `#006BE5` | `#0066DB` | `#008F27` | `#CC221D` | `#EB4E00` | `#25243E` |

> `secondary-5` is absent from the Figma source. Do not define it without a design sign-off.

### Primitive — Gray Scale

| Token | CSS Variable | Value |
|-------|-------------|-------|
| gray-1  | `--color-gray-1`  | `#FFFFFF` |
| gray-2  | `--color-gray-2`  | `#F7F9FC` |
| gray-3  | `--color-gray-3`  | `#F2F4F7` |
| gray-4  | `--color-gray-4`  | `#F0F2F5` |
| gray-5  | `--color-gray-5`  | `#EBEDF0` |
| gray-6  | `--color-gray-6`  | `#D3D9E0` |
| gray-7  | `--color-gray-7`  | `#C5CBD1` |
| gray-8  | `--color-gray-8`  | `#A8ABB2` |
| gray-9  | `--color-gray-9`  | `#6C737A` |
| gray-10 | `--color-gray-10` | `#4F535C` |
| gray-11 | `--color-gray-11` | `#1D2129` |

### Primitive — Brand Red (not applied to components)

| Token | CSS Variable | Value |
|-------|-------------|-------|
| brand-red   | `--color-brand-red`   | `#FD0134` |
| brand-red-3 | `--color-brand-red-3` | `#FE5275` |
| brand-red-4 | `--color-brand-red-4` | `#FF9EB2` |
| brand-red-5 | `--color-brand-red-5` | `#FFC5D0` |

### Semantic — Text

| CSS Variable | Value | Usage |
|-------------|-------|-------|
| `--color-text-primary`     | `#101011`                        | 强调/正文/标题 |
| `--color-text-secondary`   | `#64676C`                        | 次强调/正文/标题 |
| `--color-text-tertiary`    | `#95989D`                        | 次要信息 |
| `--color-text-disabled`    | `#BCBEC3`                        | 置灰信息 |
| `--color-text-placeholder` | `#C5CBD1`                        | Input placeholder |
| `--color-text-inverse`     | `#FFFFFF`                        | Text on dark surfaces |
| `--color-text-link`        | `var(--color-primary-5)` `#0088FF` | 链接色 |
| `--color-text-accent`      | `var(--color-warning-5)` `#FA6C00` | 强调色 |

### Semantic — Background

| CSS Variable | Value | Usage |
|-------------|-------|-------|
| `--color-bg-base`         | `#FFFFFF`                  | 白色背景 — card / modal / drawer |
| `--color-bg-subtle`       | `#FAFBFD`                  | 斑马线 — table row alternating |
| `--color-bg-disabled`     | `#F2F4F7`                  | 禁用填充色 |
| `--color-bg-elevated`     | `#F7F9FC`                  | 深背景色 — elevated containers |
| `--color-bg-mask`         | `rgba(0,0,0,0.34)`         | 遮罩层 |
| `--color-bg-popper-dark`  | `rgba(29,33,41,0.80)`      | 气泡/toast dark |
| `--color-bg-popper-light` | `rgba(255,255,255,0.98)`   | 气泡浮层 light |

### Semantic — Border & Divider

| CSS Variable | Value | Usage |
|-------------|-------|-------|
| `--color-border-default`  | `var(--color-gray-6)` `#D3D9E0` | 默认描边 |
| `--color-border-subtle`   | `var(--color-gray-5)` `#EBEDF0` | 浅描边/禁用描边 |
| `--color-divider-default` | `var(--color-gray-5)` `#EBEDF0` | 常规分割线 |
| `--color-divider-light`   | `var(--color-gray-4)` `#F0F2F5` | 浅分割线 |

### Semantic — Action

| CSS Variable | Maps to | State |
|-------------|---------|-------|
| `--color-action-default`  | `var(--color-primary-5)` | Normal |
| `--color-action-hover`    | `var(--color-primary-4)` | Hover |
| `--color-action-pressed`  | `var(--color-primary-6)` | Pressed |
| `--color-action-disabled` | `var(--color-primary-3)` | Disabled |
| `--color-action-surface`  | `var(--color-primary-1)` | Surface |

### Semantic — Shadow & Gradients

| CSS Variable | Value |
|-------------|-------|
| `--color-shadow-default`           | `rgba(0,0,0,0.06)` |
| `--color-gradient-action-active`   | `linear-gradient(135deg, #007AE5, #0075DB)` |
| `--color-gradient-action-normal`   | `linear-gradient(135deg, #00A2FF, #0088FF)` |
| `--color-gradient-action-hover`    | `linear-gradient(135deg, #34AEFF, #34A1FF)` |
| `--color-gradient-action-disabled` | `linear-gradient(135deg, #9AD3FF, #9AD0FF)` |
| `--color-gradient-warning`         | `linear-gradient(135deg, #FFF8E6, #FFFBF0)` |
| `--color-gradient-success`         | `linear-gradient(135deg, #EBFAEB, #F3FCF2)` |
| `--color-gradient-danger`          | `linear-gradient(135deg, #FFF1EB, #FFF9F5)` |
| `--color-gradient-info`            | `linear-gradient(135deg, #F0FBFF, #F5FDFF)` |

---

<!-- section-id: style-composition -->
## Style Composition

```
Figma hex  →  --color-primary-5  →  --color-action-default  →  background: var(--color-action-default)
```

| Use case | Token to use |
|----------|-------------|
| Interactive element fill | `--color-action-*` |
| Any text / icon | `--color-text-*` |
| Input / card border | `--color-border-*` |
| Separator / rule | `--color-divider-*` |
| Table row stripe | `--color-bg-subtle` |
| Feedback badge (bg + border + text) | `--color-{scale}-1` + `--color-{scale}-3` + `--color-{scale}-6` |
| Primary button fill | `--color-gradient-action-*` |

---

<!-- section-id: attribute-variables -->
## Attribute Variables

| CSS Variable | Type | Tier | Constraint |
|-------------|------|------|-----------|
| `--color-{scale}-{1-6}` | `<color>` | Primitive | Read-only; never in component CSS |
| `--color-gray-{1-11}` | `<color>` | Primitive | Read-only |
| `--color-brand-red{,-3,-4,-5}` | `<color>` | Primitive | Not applied to components |
| `--color-text-*` | `<color>` | Semantic | Required for all `color` / `fill` |
| `--color-bg-*` | `<color>` | Semantic | Required for all `background-color` |
| `--color-border-*` | `<color>` | Semantic | Required for all `border-color` |
| `--color-divider-*` | `<color>` | Semantic | Required for separator `border-color` |
| `--color-action-*` | `<color>` | Semantic | Required for interactive fills |
| `--color-shadow-default` | `<color>` | Semantic | Use inside `box-shadow` only |
| `--color-gradient-*` | `<image>` | Semantic | Use with `background`, not `background-color` |

---

<!-- section-id: enforcement-rules -->
## Enforcement Rules

1. No raw hex in component CSS — use semantic tokens.
2. No primitive tokens (`--color-primary-5`) in component CSS — alias through semantic first.
3. Gradient tokens require `background` shorthand, not `background-color`.
4. Do not define `--color-secondary-5` — it is intentionally absent.
5. `--color-brand-red` and tints are reserved; use `--color-danger-*` until formally promoted.
6. Semantic tokens must not alias other semantic tokens — only primitive → semantic chains are valid.
7. Do not write ad-hoc `rgba()` opacity values — use the three opacity tokens (`bg-mask`, `bg-popper-dark`, `bg-popper-light`).
8. Text on dark/colored surfaces must use `--color-text-inverse`, not `--color-text-primary`.

---

<!-- section-id: functional-usage -->
## Functional Usage

```css
/* ✓ Button states */
.btn-primary                { background: var(--color-gradient-action-normal); color: var(--color-text-inverse); }
.btn-primary:hover          { background: var(--color-gradient-action-hover); }
.btn-primary:active         { background: var(--color-gradient-action-active); }
.btn-primary:disabled       { background: var(--color-gradient-action-disabled); color: var(--color-text-disabled); }

/* ✓ Card */
.card                       { background-color: var(--color-bg-base); border: 1px solid var(--color-border-default); box-shadow: 0 2px 8px var(--color-shadow-default); }

/* ✓ Input */
.input                      { color: var(--color-text-primary); border: 1px solid var(--color-border-default); background-color: var(--color-bg-base); }
.input::placeholder         { color: var(--color-text-placeholder); }
.input:disabled             { background-color: var(--color-bg-disabled); border-color: var(--color-border-subtle); color: var(--color-text-disabled); }

/* ✓ Feedback alert */
.alert-success              { background-color: var(--color-success-1); border: 1px solid var(--color-success-3); color: var(--color-success-6); }

/* ✓ Utilities */
.table-row:nth-child(even)  { background-color: var(--color-bg-subtle); }
.divider                    { border-top: 1px solid var(--color-divider-default); }
.modal-backdrop             { background-color: var(--color-bg-mask); }
.toast                      { background-color: var(--color-bg-popper-dark); color: var(--color-text-inverse); }
```

```css
/* ✗ Raw hex */          .btn { background: #0088FF; }
/* ✗ Primitive token */  .btn { background: var(--color-primary-5); }
/* ✗ Wrong property */   .chip { background-color: var(--color-gradient-success); }
/* ✗ Ad-hoc rgba */      .overlay { background: rgba(29, 33, 41, 0.5); }
```

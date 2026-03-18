# Font Tokens

<!-- section-id: overview -->
## Overview

- Governs font family, weight, size, line-height, and composite text styles
- **Two tiers:** Primitive (family / weight / size / leading) → Semantic composites (body, label, heading)
- Three composite categories: **Body** (Regular 400), **Label** (Medium 500), **Heading** (Semibold/Medium 600/500)
- Source: Figma node `5:1052`, frame `"Typography"`, Page 1

---

<!-- section-id: token-definitions -->
## Token Definitions

### Primitive — Family

| CSS Variable | Stack |
|-------------|-------|
| `--font-family-base`   | `"PingFang SC", "Microsoft YaHei", sans-serif` |
| `--font-family-number` | `"Helvetica Neue", Helvetica, Arial, sans-serif` |
| `--font-family-code`   | `"SFMono-Regular", Consolas, "Liberation Mono", Menlo, Courier, monospace` |

### Primitive — Weight

| CSS Variable | Value |
|-------------|-------|
| `--font-weight-regular`  | `400` |
| `--font-weight-medium`   | `500` |
| `--font-weight-semibold` | `600` |

### Primitive — Size & Paired Line Height

| CSS Variable (size) | Value | CSS Variable (leading) | Value |
|--------------------|-------|----------------------|-------|
| `--font-size-12` | `12px` | `--font-leading-12` | `18px` |
| `--font-size-14` | `14px` | `--font-leading-14` | `22px` |
| `--font-size-16` | `16px` | `--font-leading-16` | `24px` |
| `--font-size-18` | `18px` | `--font-leading-18` | `22px` |
| `--font-size-20` | `20px` | `--font-leading-20` | `24px` |
| `--font-size-24` | `24px` | `--font-leading-24` | `28px` |
| `--font-size-28` | `28px` | `--font-leading-28` | `34px` |
| `--font-size-32` | `32px` | `--font-leading-32` | `38px` |
| `--font-size-36` | `36px` | `--font-leading-36` | `44px` |
| `--font-size-40` | `40px` | `--font-leading-40` | `48px` |
| `--font-size-48` | `48px` | `--font-leading-48` | `58px` |

### Semantic — Composites

| Token prefix | Size | Weight | Leading | Figma style | Usage |
|-------------|------|--------|---------|-------------|-------|
| `--font-body-xs-*`    | 12px | 400 | 18px | Regular/12  | Caption, footnote |
| `--font-body-sm-*`    | 14px | 400 | 22px | Regular/14  | Default body text |
| `--font-body-md-*`    | 16px | 400 | 24px | Regular/16  | Prominent body |
| `--font-body-lg-*`    | 18px | 400 | 22px | Regular/18  | Large body / sub-heading |
| `--font-body-xl-*`    | 20px | 400 | 24px | Regular/20  | Display body |
| `--font-label-xs-*`   | 12px | 500 | 18px | Medium/12   | Tag, badge |
| `--font-label-sm-*`   | 14px | 500 | 22px | Medium/14   | Form label, button text |
| `--font-label-md-*`   | 16px | 500 | 24px | Medium/16   | Strong label |
| `--font-label-lg-*`   | 18px | 500 | 22px | Medium/18   | Card title, tab |
| `--font-label-xl-*`   | 20px | 500 | 24px | Medium/20   | Section label |
| `--font-heading-6-*`  | 24px | 600 | 28px | Semibold/24 | Panel heading |
| `--font-heading-5-*`  | 28px | 500 | 34px | Medium/28   | Page sub-title |
| `--font-heading-4-*`  | 32px | 500 | 38px | Medium/32   | Section title |
| `--font-heading-3-*`  | 36px | 500 | 44px | Medium/36   | Page title |
| `--font-heading-2-*`  | 40px | 500 | 48px | Medium/40   | Large title |
| `--font-heading-1-*`  | 48px | 500 | 58px | Medium/22   | Hero / display title |

---

<!-- section-id: style-composition -->
## Style Composition

```
Figma text style  →  --font-size-14 / --font-weight-regular / --font-leading-14  →  font-size + font-weight + line-height
```

| Use case | Token group |
|----------|------------|
| Running paragraph / form field value | `--font-body-sm-*` |
| Button / form label | `--font-label-sm-*` |
| Card title / tab label | `--font-label-lg-*` |
| Panel / section heading | `--font-heading-6-*` |
| Page-level title | `--font-heading-3-*` |
| Hero / display | `--font-heading-1-*` |
| Numeric data (prices, counts) | `--font-family-number` + appropriate size |
| Code / monospace | `--font-family-code` + `--font-body-sm-*` |

---

<!-- section-id: attribute-variables -->
## Attribute Variables

| CSS Variable | Type | Tier | Constraint |
|-------------|------|------|-----------|
| `--font-family-{base,number,code}` | `<family-name>` | Primitive | Read-only; never override per-component |
| `--font-weight-{regular,medium,semibold}` | `<integer>` | Primitive | Read-only |
| `--font-size-{12…48}` | `<length>` | Primitive | Read-only; use semantic size token instead |
| `--font-leading-{12…48}` | `<length>` | Primitive | Must be applied with its paired `--font-size-*` |
| `--font-body-{xs…xl}-{size,weight,leading}` | mixed | Semantic | Apply all three together; never partial |
| `--font-label-{xs…xl}-{size,weight,leading}` | mixed | Semantic | Apply all three together; never partial |
| `--font-heading-{1…6}-{size,weight,leading}` | mixed | Semantic | Apply all three together; never partial |

---

<!-- section-id: enforcement-rules -->
## Enforcement Rules

1. No raw `px` or `em` values for `font-size` or `line-height` in component CSS — use token variables.
2. Never set `font-size` without also setting the paired `line-height` from the same composite.
3. `--font-family-number` must be applied to all numeric display elements (prices, stats, counters).
4. Do not mix size tokens across composites (e.g., `--font-body-sm-size` + `--font-label-sm-weight`).
5. Do not use raw `font-weight: bold` — use `--font-weight-semibold` or `--font-weight-medium`.
6. `--font-leading-18` (`22px`) is intentionally tighter than `--font-leading-14` — do not "fix" it.
7. Heading tokens (heading-5 through heading-1) use `--font-weight-medium`, not semibold — only heading-6 is semibold.

---

<!-- section-id: functional-usage -->
## Functional Usage

```css
/* ✓ Body text */
.body-text {
  font-family: var(--font-family-base);
  font-size: var(--font-body-sm-size);
  font-weight: var(--font-body-sm-weight);
  line-height: var(--font-body-sm-leading);
}

/* ✓ Button label */
.btn {
  font-family: var(--font-family-base);
  font-size: var(--font-label-sm-size);
  font-weight: var(--font-label-sm-weight);
  line-height: var(--font-label-sm-leading);
}

/* ✓ Page title */
.page-title {
  font-family: var(--font-family-base);
  font-size: var(--font-heading-3-size);
  font-weight: var(--font-heading-3-weight);
  line-height: var(--font-heading-3-leading);
}

/* ✓ Numeric data */
.price {
  font-family: var(--font-family-number);
  font-size: var(--font-label-lg-size);
  font-weight: var(--font-label-lg-weight);
  line-height: var(--font-label-lg-leading);
}

/* ✓ Code block */
.code {
  font-family: var(--font-family-code);
  font-size: var(--font-body-sm-size);
  font-weight: var(--font-body-sm-weight);
  line-height: var(--font-body-sm-leading);
}
```

```css
/* ✗ Raw px value */         .text { font-size: 14px; }
/* ✗ Unpaired size */        .text { font-size: var(--font-body-sm-size); }
/* ✗ Mixed composite */      .text { font-size: var(--font-body-sm-size); font-weight: var(--font-label-sm-weight); }
/* ✗ Raw bold */             .text { font-weight: bold; }
/* ✗ Primitive size direct */.text { font-size: var(--font-size-14); }
```

# Basic Components

Reusable primitives that appear across most screens.

---

### 区块按钮 Block Button

Sizes in scope: **默认 36px** · **大号 40px**

| Variant (类型) | Visual | When to use |
|---------------|--------|-------------|
| 主要 Primary | Blue gradient fill, white text | Main CTA — one per view |
| 主要 危险 Danger | Red fill, white text | Destructive action (delete, remove) |
| 次要 Secondary | White fill, blue border + blue text | Secondary action alongside a primary |
| 基础 Basic | White fill, gray border + dark text | Low-priority or neutral action |

**Sizes**

| 尺寸 | Height | Padding H | Font |
|------|--------|-----------|------|
| 默认 Default | 36px | 16px | `--font-label-sm-*` (14px / 22px / 500) |
| 大号 Large | 40px | 16px | `--font-label-sm-*` (14px / 22px / 500) |

**States** (all variants): 默认 · 悬停 hover · 点击 pressed · 禁用 disabled

**Tokens used**
- Background: `--color-gradient-action-normal/hover/active/disabled` (Primary) · `--color-bg-base` (Secondary, Basic)
- Border: `--color-action-default` (Secondary) · `--color-border-default` (Basic) · none (Primary)
- Text: `--color-text-inverse` (Primary) · `--color-action-default` (Secondary) · `--color-text-primary` (Basic)
- Radius: `6px` (`--radius-md`)

**Code**
```vue
<okee-button type="primary" size="default">Label</okee-button>
<okee-button type="primary" danger size="large">Delete</okee-button>
<okee-button type="default" size="default">Label</okee-button>
<!-- type: "primary" | "default" | "dashed" -->
<!-- size: "default" (36px) | "large" (40px) -->
```
Docs: https://okee.bytedance.net/react/zh-CN/button

---

### 标签页 Tabs

Two contexts: **page-level** (switches major sections) · **inline filter** (filters content within a section)

| State | Visual |
|-------|--------|
| Active | Dark text, blue underline indicator |
| Inactive | Gray text, no underline |

| Context | Height | Font | When to use |
|---------|--------|------|-------------|
| Page-level | ~40px | `--font-label-md-*` (16px / 24px / 500) | Top of a panel, switching between major views (e.g. 门店头图 / 门店相册) |
| Inline filter | 32px | `--font-label-sm-*` (14px / 22px / 500) | Sub-filtering within a section (e.g. image categories) |

**Tokens used**
- Text active: `--color-text-primary`
- Text inactive: `--color-text-secondary`
- Indicator: `--color-action-default`
- Background: `--color-bg-base`

**Code**
```vue
<okee-tabs v-model="activeTab">
  <okee-tab-pane label="门店头图" name="header" />
  <okee-tab-pane label="门店相册" name="album" />
</okee-tabs>
<!-- size: "default" (page-level) | "small" (inline filter) -->

---

### 分段控制 Segmented Control

One variant only. Pill-shaped container with 3 options, one active at a time.

| State | Visual |
|-------|--------|
| Active | Light blue-gray fill `#eaf1f7`, text `--color-text-primary` |
| Inactive | Transparent fill, text `--color-text-secondary` |

**Structure**
- Container: `--color-bg-popper-light` bg · white border · `border-radius: 16px` · `padding: 2px` · `gap: --space-4` · `--color-shadow-default`
- Item: `border-radius: 12px` · `padding: --space-8 16px` · `--font-label-xs-*` (12px / 18px / 500)

**Tokens used**
- Text active: `--color-text-primary`
- Text inactive: `--color-text-secondary`
- Item active bg: `#eaf1f7` (light primary tint — no exact token, use as-is)
- Container bg: `--color-bg-popper-light`

**Code**
```vue
<okee-segmented v-model="current" :options="['门店入口', '门店主页', '门店详情页']" />
```

---

### 面包屑 Breadcrumb

One variant only. Back button + text path separated by `/`.

**Structure**
- Back button: 28px square · white bg (`--color-bg-base`) · border `--color-border-subtle` · radius `--radius-md` · left-arrow icon 16px
- Label: path text e.g. `店铺装修/头图和相册` · `--font-label-xl-*` (20px / 24px / 500) · `--color-text-primary`
- Gap between back button and label: 25px (`--space-28` approx)

**Code**
```vue
<okee-breadcrumb>
  <okee-breadcrumb-item>店铺装修</okee-breadcrumb-item>
  <okee-breadcrumb-item>头图和相册</okee-breadcrumb-item>
</okee-breadcrumb>
```

---

### 选项卡 Option Selector Card

Used when the user picks between mutually exclusive input/upload modes (e.g. 通用头图 / 特色头图 / 品牌头图). Selecting one affects the content area below.

| State | Visual |
|-------|--------|
| Selected | `--color-action-surface` bg · `--color-action-default` border · icon + text in `--color-action-default` |
| Default | `--color-bg-base` bg · no border · icon + text in `--color-text-primary` |

**Structure**
- Width: 120px · padding: `--space-12` vertical / 16px horizontal · radius: `--radius-lg` (12px) · gap: `--space-4`
- Icon: 16px · Label: `--font-label-sm-*` (14px / 22px / 500)

**Code**
```vue
<option-card v-model="selected" :options="['通用头图', '特色头图', '品牌头图']" />

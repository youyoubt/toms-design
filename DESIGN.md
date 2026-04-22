# Design System Inspired by TOMS Operator

> Terminal Operations Management System — Enterprise SaaS, light-mode-first, data-dense, globally internationalized.

**Use this design for:** payment terminal management consoles, IoT fleet dashboards, enterprise device operations portals, multi-region SaaS back-offices, and any data-dense admin interface requiring dense tables, real-time status monitoring, and multi-language support across CJK and Latin scripts.

---

## 1. Visual Theme & Atmosphere

TOMS Operator is a **light-mode-native enterprise management console** designed for operators managing thousands of payment terminals across multiple regions and time zones. The visual language is calm, authoritative, and information-dense — a white-and-gray canvas where structured data takes center stage and brand presence is delivered through a deep navy blue (`#003a8c`) used sparingly as the anchor of trust.

The overall impression is **clinical precision**: the app background is a cool gray (`#f1f3f6`) that creates a subtle separation between the workspace and the pure white (`#ffffff`) surfaces of cards, sidebars, and dialogs. Nothing fights for attention. Color is a communication tool, not a decoration — it signals status (green for active, orange for offline, red for fault), indicates brand hierarchy (navy for primary actions), and guides navigation (blue-tinted muted grays in the sidebar transitioning to deep navy on selection).

Typography is built on **Poppins**, a geometric sans-serif that reads cleanly at the small sizes demanded by dense data tables (12px–14px), while carrying confident weight for headings and statistics at 24px–32px. The system also supports CJK characters natively through fallback stacks (`'Microsoft YaHei'`, `'PingFang SC'`), reflecting deployment across China, Japan, and global markets. Interface language can switch among English, Chinese, Japanese, French, and Portuguese — every layout must gracefully handle string-length variance.

The component foundation is **Element Plus**, customized with TOMS-specific overrides. Cards use 4px border radius with multi-layer soft shadows. Tables are dense with 5px–10px cell padding, thin `#dcdfe6` borders, and alternate row visibility through subtle hover states. The sidebar collapses to icon-only width on demand, and the top navbar is a fixed 60px white bar.

**Key Characteristics:**
- Light-mode native: `#f1f3f6` workspace, `#ffffff` surfaces, `#003a8c` brand anchor
- Poppins typeface (weights 300–900) with CJK fallback stack
- Element Plus component library as foundation, customized with TOMS overrides
- Status-driven color language: green active, orange warning/inactive, red danger
- Fixed chrome: 60px navbar + 250px collapsible sidebar
- Data density priority: tables, forms, and stat cards dominate layouts
- Multilingual-ready: all components must accommodate variable string lengths
- Subtle animation: 0.28s opacity fade, 0.3s slide transitions — nothing jarring

---

## 2. Color Palette & Roles

### Background Surfaces
- **App Background** (`#f1f3f6`): The workspace canvas — cool light gray that recedes behind white content surfaces. Used as the `body` / main area background.
- **Surface White** (`#ffffff`): Cards, navbar, sidebar, dialogs, table backgrounds. The primary content surface.
- **Subtle Background** (`#f5f5f5`): Alternate light background for section dividers or secondary panels.
- **Dark Code Surface** (`#1e1e1e`): Terminal emulator / code preview backgrounds. Restricted to dev-tool contexts.

### Brand & Primary Interactive
- **Brand Navy** (`#003a8c`): The deepest brand color — used for step indicators (active), key labels, and brand-identified UI anchors. Never overused.
- **Interactive Blue** (`#409eff`): Element Plus primary — used for primary buttons, active form focus rings, selected tabs, links.
- **Interactive Blue Dark** (`#2c7be5`): Darker interactive blue for hover states on primary actions and emphasis elements.
- **Focus Ring / Accent** (`rgba(64, 158, 255, 0.3)`): Soft blue glow for active/focused parameter cards and form inputs.

### Text & Content
- **Primary Text** (`#303133`): Element Plus default — the main body text color for all content, form labels, table data, and dialog copy.
- **Menu Text** (`#6e84a3`): Default sidebar navigation text — blue-tinted gray, de-emphasized.
- **Active Menu Text** (`#12263f`): Deep navy-charcoal for active/selected sidebar items.
- **Secondary Text** (`#767676`): Supporting body text, descriptions, metadata.
- **Label Text** (`#677796`): Muted blue-gray for stat card labels, helper text, subtitles.
- **Tool Icon Default** (`#b6c6dc`): Icon color in inactive/default states.

### Status Colors
- **Active / Success Green** (`#52c41a`): Device online, task completed, active status badge.
- **Success Badge BG** (`#e5f9f6`) with text (`#6ad99f`): Success state badge background + text pairing.
- **Inactive / Warning Orange** (`#ff8d1a`): Device offline, pending, caution state.
- **Warning Badge** (`#f6c556`): Warning indicator for moderate alerts.
- **Danger / Error** (`#e9378f`): Critical fault, failed status, error state.
- **Disabled** (`#a6a6a6`): Disabled device or UI control.
- **Success Overlay** (`rgba(51, 195, 186, 0.29)`): Transparent success background for result areas.
- **Danger Overlay** (`rgba(235, 12, 13, 0.29)`): Transparent danger background for error areas.

### Border & Divider
- **Standard Border** (`#dcdfe6`): Element Plus default — used for inputs, table cells, card borders.
- **Card Header Border** (`#dae0e8`): Slightly blue-tinted border for card header separators.
- **Sidebar Divider** (`#eef0f7`): Very light blue-gray for structural dividers in the sidebar.
- **Line Subtle** (`rgba(9, 30, 66, 0.13)`): Semi-transparent dark divider for list separators.

### Navigation & Sidebar
- **Menu Active Background** (`rgba(189, 197, 209, 0.2)`): Soft blue-gray wash behind the active nav item.
- **Button Hover Light** (`rgba(0, 0, 0, 0.06)`): Light overlay for button hover on white surfaces.
- **Button Active Light** (`rgba(0, 0, 0, 0.15)`): Deeper overlay for button press.
- **Dark Button Hover** (`rgba(0, 0, 0, 0.2)`): Used for `.dark` text buttons on colored backgrounds.
- **List Item Hover** (`rgba(9, 30, 66, 0.04)`): Table row / list item hover — barely visible, respects data density.

### Scrollbar
- **Scrollbar Thumb** (`#99a9bf`): Blue-gray scrollbar handle.
- **Scrollbar Track** (`#d3dce6`): Light blue-gray scrollbar track.

---

## 3. Typography Rules

### Font Family
- **Primary**: `'Poppins', 'Helvetica Neue', Helvetica, 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', '微软雅黑', Arial, sans-serif`
- **Monospace / Terminal**: `monospace` (for code preview, terminal emulator contexts)
- **Fallback**: `Arial, Helvetica, sans-serif`

Poppins is loaded in weights 300, 400, 500, 600, 700, 800, 900. Open Sans is available as secondary. CJK fallbacks ensure consistent rendering in Chinese and Japanese deployments.

### Hierarchy

| Role | Size | Weight | Line Height | Letter Spacing | Use |
|------|------|--------|-------------|----------------|-----|
| Page Title / Section Headline | 24px | 600–700 | 32px | normal | Module headings, dashboard section titles |
| Stat Number (Large) | 32px | 700 | 35px | normal | KPI stats, count displays |
| Stat Number (Medium) | 24px | 700 | 32px | normal | Secondary stat values |
| Card Title / Sub-heading | 20px | 600 | 26px | normal | Feature card headers, dialog titles |
| Body / Standard Label | 16px | 400–500 | 24px | normal | Form labels, card body, general content |
| Table Cell / Data | 14px | 400 | 22px | normal | Table rows, list items, metadata |
| Caption / Small Label | 12px | 400–500 | 20px | normal | Badges, timestamps, secondary metadata |
| Stat Label | 16px | 400 | 17px | normal | Labels under stat numbers |
| Stat Count / Meta | 14px | 400 | normal | normal | Sub-counts in stat cards |
| Dashboard Header | 24px | 700 | 32px | normal | Dashboard widget headings |
| Tab Badge Count | 12px | 500 | normal | normal | Number badges on tabs (border-radius 15px) |
| Sidebar Nav Link | 14px | 400–500 | normal | normal | Menu items |

### Principles
- **Poppins 600–700 for headings**: Data dashboards need confident headings that anchor the page without competing with data.
- **14px as the data size**: Table cells, form helpers, and list items all use 14px — enough to read dense rows comfortably.
- **CJK at same weight**: Chinese/Japanese text should use the same weight as English — do not compensate with lighter weights.
- **Tag font-weight: 500**: Element Plus tags override to 500 weight for slightly bolder status pills.
- **Avoid custom letter-spacing**: Unlike editorial brands, TOMS uses default tracking — Poppins's native spacing is correct for functional data UI.

---

## 4. Component Stylings

### Buttons

**Primary Button**
- Background: `#409eff` (Element Plus primary)
- Text: `#ffffff`, weight 500
- Padding: 8px 20px
- Radius: 4px
- Hover: `#2c7be5`
- Use: Primary form submit, "Create", "Save", key CTAs

**Default / Secondary Button**
- Background: `#ffffff`
- Text: `#606266`
- Border: `1px solid #dcdfe6`
- Radius: 4px
- Hover: border + text shift to `#409eff`
- Use: Cancel, secondary actions

**Text Button (Dark variant)**
- Background: transparent
- Text: `#409eff` or contextual color
- Hover BG: `rgba(0, 0, 0, 0.2)`
- Active BG: `rgba(0, 0, 0, 0.7)`
- Use: Inline actions, table row operations

**Search / Compact Button**
- Padding: 3px 13px
- Radius: 4px
- Use: Search trigger, filter apply

**Expand / Map Control Button**
- Size: 32px × 32px
- Radius: 50%
- Background: `#ffffff`
- Shadow: `0 1px 2px rgb(60 64 67 / 30%), 0 2px 6px 2px rgb(60 64 67 / 15%)`
- Use: Map controls, floating circular icon buttons

**Collapse Panel Button**
- Size: 23px × 48px
- Radius: `0 8px 8px 0`
- Shadow: same as expand button
- Use: Sidebar / panel toggle handle

### Cards & Containers

**Standard App Card**
- Background: `#ffffff`
- Border: none (shadow defines boundary)
- Radius: 8px
- Shadow: `0px 2px 4px -2px rgba(0,0,0,0.12), 0px 4px 8px 0px rgba(0,0,0,0.08), 0px 4px 16px 4px rgba(0,0,0,0.04)`
- Padding: 20px
- Use: Dashboard widgets, feature section containers

**Stat / KPI Card**
- Background: `#ffffff`
- Radius: 4px (inner), 8px (outer wrapper)
- Shadow: multi-layer (same as standard card)
- Layout: `flex items-center text-center`
- Use: Key metrics display

**App Store Card**
- Background: `#ffffff`
- Hover Shadow: `0 2px 4px rgb(126 142 177 / 12%)`
- Use: App listing cards in AppStore module

**Parameter Card (Active)**
- Background: `#ffffff`
- Border-radius: 4px
- Active Shadow: `rgba(64, 158, 255, 0.3) 0px 1px 2px 0px, rgba(64, 158, 255, 0.15) 0px 2px 6px 2px`
- Use: Fly-parameter selection cards

**Code / Terminal Preview**
- Background: `#1e1e1e`
- Min-height: `calc(100vh - 33px)`
- Padding: 10px
- Font: monospace
- Use: Script editor, device log viewer

### Tables

- Header background: `#f5f5f5` or `#ffffff` with bottom border
- Cell padding: `5px 10px`
- Row hover: `rgba(9, 30, 66, 0.04)` background
- Border: `1px solid #dcdfe6`
- Font: 14px, weight 400
- Status cell: inline color badge (pill/dot)
- Actions column: text buttons, right-aligned

### Forms & Inputs

**Standard Input**
- Background: `#ffffff`
- Border: `1px solid #dcdfe6`
- Radius: 4px
- Font: 14px Poppins
- Focus border: `#409eff`
- Width (inline): `--el-input-width: 200px`

**Terminal / Dark Input**
- Background: transparent
- Border: `1px solid #1da1f2`
- Padding: 5px
- Height: 1.4em
- Font: monospace
- Use: Command input in terminal emulator

**Form Item Spacing**
- Margin-bottom: 15px (standard form), 5px (compact/mini)
- Label: `float: none`, standard weight

### Badges & Tags

**Status Dot (Active)**
- Background: `#52c41a`
- Size: 8–10px circle (50% radius)
- Use: Device active/online indicator

**Status Pill (Active)**
- Background: `#52c41a`, Text: `#ffffff`
- Padding: 2px 8px, Radius: 3px
- Font: 12px weight 500
- Use: Terminal status, task state

**Status Pill (Inactive)**
- Background: `#ff8d1a`, Text: `#ffffff`
- Same sizing as active

**Tag (Element Plus override)**
- Font-weight: 500
- Standard Element Plus sizing with TOMS status color mapping

**Tab Count Badge**
- Font-size: 12px
- Border-radius: 15px
- Padding: 4px 6px 4px 6px
- Use: Number badges on module tabs

### Navigation & Sidebar

- **Sidebar width**: 250px (expanded), collapses to icon-only
- **Sidebar background**: `#ffffff`
- **Divider color**: `#eef0f7`
- **Nav link**: 14px Poppins, `#6e84a3`, icon + label
- **Active nav item**: text `#12263f`, background `rgba(189, 197, 209, 0.2)`, left border accent in `#003a8c`
- **Navbar**: 60px height, `#ffffff` background, fixed top
- **Navbar content**: breadcrumb left, user profile + notifications right

### Dialog / Modal

- Background: `#ffffff`
- Body padding: `--el-dialog-body-padding: 0` (content fills dialog, inner padding handled by content)
- Width: 60%–90% responsive
- Radius: 4px–8px
- Shadow: standard elevated card shadow

### Select / Dropdown

**Standard Select**
- Background: `#ffffff`
- Border: `1px solid #dcdfe6`
- Radius: 4px
- Font: 14px Poppins weight 400, `#303133`
- Placeholder: `#a8abb2`
- Focus border: `#409eff`
- Width (inline): `--el-input-width: 200px`; full-width in stacked forms
- Dropdown panel: `#ffffff` background, `1px solid #e4e7ed` border, 4px radius, shadow `0px 0px 12px rgba(0,0,0,0.12)`
- Option hover: `rgba(9, 30, 66, 0.04)` background
- Option selected: `#409eff` text, weight 600
- Use: Filter bars, form fields, configuration selectors

**Multi-Select Tag**
- Tag inside input: `#f0f2f5` background, `#303133` text, `#dcdfe6` border, 3px radius
- Font: 12px weight 400
- Remove icon: `#909399`, hover `#303133`

### Pagination

- Font: 14px Poppins weight 400, `#303133`
- Page button: `#ffffff` bg, `1px solid #dcdfe6` border, 4px radius, 28px min-width
- Active page: `#409eff` bg, `#ffffff` text, no border
- Prev/Next arrow: `#606266`, hover `#409eff`
- Disabled: `#a6a6a6` text, no pointer
- Page size selector: same as Standard Select, compact width
- Total count text: 14px `#303133`
- Alignment: right-aligned below table, consistent 16px top margin
- Use: All data tables — always pair with table component

### Tooltip

- Background: `#303133` (dark, reversed from surface)
- Text: `#ffffff`, 12px Poppins weight 400
- Padding: 6px 10px
- Radius: 4px
- Arrow: matches background color
- Max-width: 200px, wraps at content boundary
- Trigger: hover on truncated text, icon buttons without labels, disabled controls
- Use: Table cell overflow, icon-only toolbar buttons, form field hints

### Step Indicator

- **Active step**: border + background `#003a8c`, text `#ffffff`
- **Finished step**: color `#003a8c`, background `var(--color-geekblue-1)`
- **Waiting step**: background + border `var(--color-gray-4)`
- **Success step**: background `#52c41a`, text `#ffffff`
- Icon size: 32px × 32px, border: 2px, radius: 50%
- Connector line: 1px `#f0f0f0`, horizontal connector: `top: 15px, width: 80%, margin: 0 auto`

---

## 5. Layout Principles

### Spacing System

Explicit spacing scale: `3px, 4px, 5px, 8px, 10px, 12px, 13px, 15px, 16px, 20px, 24px, 32px`

| Token | Value | Common Use |
|-------|-------|------------|
| — | 3px | Tag inner margin, micro list spacing |
| — | 4px | Compact button vertical padding |
| — | 5px | Table cell vertical, dense input padding |
| — | 8px | Base unit — icon gaps, small component spacing |
| — | 10px | Table cell horizontal, card header padding |
| — | 12px | Inline badge padding, input height assist |
| — | 13px | Search button horizontal padding |
| — | 15px | Form item margin-bottom (standard) |
| — | 16px | Section element vertical rhythm |
| — | 20px | `.app-container` padding, card body |
| — | 24px | Section title breathing room above tables |
| — | 32px | Large section separation |

- Tailwind line-height scale: `xs:20px`, `sm:22px`, `md:24px`, `lg:26px`, `xl:32px`, `2xl:40px`
- Button group gap: 0.3em

### Grid & Container
- Max app width: fluid (fills viewport minus sidebar)
- **AppStore grid** (responsive column system):
  - ≤519px: 100% (1 col)
  - 520–767px: 50% (2 col)
  - 768–991px: 33.33% (3 col)
  - 1200–1499px: 25% (4 col)
  - 1500–1799px: 25% (4 col)
  - 1800–1919px: 20% (5 col)
  - 1920–2599px: 16.67% (6 col)
  - ≥2600px: 12.5% (8 col)
- Tailwind custom breakpoints: `sm:768px`, `md:992px`, `lg:1200px`, `xl:1920px`
- Forms: inline inputs default to `--el-input-width: 200px`; full-width when stacked

### Fixed Chrome Layout
```
┌─────────────────────────────────────────┐
│  Navbar (60px, fixed, #ffffff)          │
├──────────┬──────────────────────────────┤
│ Sidebar  │  .app-container              │
│ (250px)  │  bg: #f1f3f6                 │
│ #ffffff  │  padding: 20px               │
│          │  Cards on #ffffff            │
│          │  Table / Form content        │
└──────────┴──────────────────────────────┘
```

### Whitespace Philosophy
- **Gray as air**: The `#f1f3f6` background between cards IS the whitespace. Cards float on it — no need for additional margins between card groups beyond the natural gap.
- **Dense tables, breathable headers**: Data tables run tight (5px–10px padding) because operators scan hundreds of rows. Section titles and action bars above tables get 16px–24px vertical breathing room.
- **Form rhythm**: 15px bottom margin between form items creates steady reading rhythm for complex configuration forms.
- **Statistics cards**: Centered text in flex layouts — the number is the hero, label sits below with lighter weight.

### Border Radius Scale
- Micro (3px): Tag margins, list hover highlights
- Standard (4px): Buttons, inputs, cards, table cells, most UI elements
- Comfortable (8px): App container cards, larger panels
- Circle (50%): Icon buttons, status dots, avatar thumbnails, step indicators
- Pill (9999px / 15px): Tab count badges, status chips

---

## 6. Depth & Elevation

| Level | Treatment | Use |
|-------|-----------|-----|
| Flat (Level 0) | No shadow, `#f1f3f6` bg | App workspace background |
| Surface (Level 1) | `#ffffff` bg, no shadow | Sidebar, navbar — flush surfaces |
| Card (Level 2) | `0px 2px 4px -2px rgba(0,0,0,0.12), 0px 4px 8px 0px rgba(0,0,0,0.08), 0px 4px 16px 4px rgba(0,0,0,0.04)` | Standard content cards, stat cards |
| App Card Hover (Level 2b) | `0 2px 4px rgb(126 142 177 / 12%)` | AppStore listing cards on hover |
| Parameter Active (Level 3) | `rgba(64,158,255,0.3) 0px 1px 2px 0px, rgba(64,158,255,0.15) 0px 2px 6px 2px` | Selected/focused parameter cards |
| Map Popup (Level 4) | `0 2px 7px 1px rgb(0 0 0 / 30%)` | Map info bubble overlays |
| Floating Control (Level 4) | `0 1px 2px rgb(60 64 67 / 30%), 0 2px 6px 2px rgb(60 64 67 / 15%)` | Circular map/UI control buttons |
| Input Focus (Level 5) | `0 2px 4px rgb(0 0 0 / 20%), 0 -1px 0px rgb(0 0 0 / 2%)` | Terminal command input wrapper |

**Shadow Philosophy**: This is a light-mode system — shadows are visible and used intentionally to create card hierarchy on the gray workspace. The three-layer card shadow (spread from -2px to +4px across three stops) creates a lifted, paper-like quality. On hover, app store cards gain a subtle cool-tinted shadow. Floating controls (map buttons) use Google Maps-inspired shadows for strong presence on map canvas. Do not flatten cards to no-shadow — it removes the hierarchy that separates content from workspace.

---

## 7. Do's and Don'ts

### Do
- Use `#f1f3f6` as the workspace background — it creates essential separation between the chrome and content
- Use `#ffffff` for all card, dialog, sidebar, and table surfaces
- Apply the three-layer card shadow as the default card elevation
- Use `#409eff` for all primary interactive elements (primary buttons, focus rings, active tabs)
- Use `#003a8c` only for brand anchors and step indicators — not for general interactive elements
- Apply Poppins 600–700 for all headings and stat numbers
- Use 14px for table cells and form labels — this is the data density standard
- Apply status colors semantically: green = active/success, orange = inactive/warning, red = danger/error
- Use `rgba(189, 197, 209, 0.2)` for nav item active background — it's soft enough not to distract from content
- Support CJK: always include `'PingFang SC', 'Microsoft YaHei'` in your font fallback stack
- Use `font-weight: 500` on Element Plus tags (override the default 400)
- Apply `--el-input-width: 200px` for inline form inputs; use full-width for stacked form layouts
- Use circle buttons (50% radius, 32×32px) for map controls and floating icon actions
- Use 0.28s fade and 0.3s slide for transitions — fast enough for a working tool

### Don't
- Don't use dark mode colors — this system is light-mode only; dark surfaces only appear in terminal/code-preview contexts (`#1e1e1e`)
- Don't use `#003a8c` for primary buttons — that's `#409eff`'s role
- Don't remove the gray workspace background (`#f1f3f6`) — without it, cards lose their elevation context
- Don't pad table cells more than 10px — data density is a feature, not a bug
- Don't use font weights above 700 for body text — bolder weights are for stat numbers only
- Don't use custom letter-spacing — Poppins at default tracking is correct for this functional context
- Don't use decorative shadows on tables or inputs — only cards and floating controls have shadows
- Don't flatten cards to border-only treatment — the multi-layer shadow IS the card identity
- Don't introduce warm accent colors (yellow, coral, warm orange) into UI chrome — only use them as status signals
- Don't exceed 4px border-radius on inputs and buttons — 8px is only for larger card containers
- Don't make status colors decorative — green, orange, red exist only for terminal/device/task status communication
- Don't use `font-weight: 400` on tags — override to 500 per TOMS convention

---

## 8. Responsive Behavior

### Breakpoints
| Name | Width | Key Changes |
|------|-------|-------------|
| Mobile | <768px | Sidebar hidden (drawer mode), single column layout |
| Tablet | 768px (sm) | Two-column grids begin, sidebar may overlay |
| Desktop Small | 992px (md) | Full sidebar + content layout, 3-column grids |
| Desktop | 1200px (lg) | Standard 4-column AppStore grid, full table columns |
| Large Desktop | 1920px (xl) | 6-column AppStore grid, expanded data tables |
| Ultra Wide | ≥2600px | 8-column AppStore grid |

### Sidebar Behavior
- Desktop (≥992px): Fixed 250px sidebar, always visible
- Tablet: Sidebar collapses to icon-only width
- Mobile: Sidebar becomes a slide-in drawer overlay

### Table Behavior
- Full columns on desktop — all data visible
- On tablet: secondary columns (e.g., creation date, operator) may hide
- On mobile: switch to card-list view rather than horizontal scroll
- Fixed-width action column always stays visible

### Dialog Sizing
- Desktop: 60% viewport width
- Tablet: 80% viewport width
- Mobile: 90% viewport width

### Form Layout
- Desktop: Inline label + input (`--el-input-width: 200px`)
- Mobile: Stacked label above full-width input

### AppStore Grid
- Uses custom column class system (not CSS Grid / Flexbox breakpoints alone)
- Columns calculated as percentage per breakpoint (see Layout Principles section)
- Cards maintain consistent padding at all sizes

### Touch Targets
- All clickable elements minimum 32px height
- Table row actions: text buttons with adequate padding
- Map controls: 32×32px circle buttons (easy tap target)
- Sidebar nav items: full-width click zone, not just text

### String Length Variance (i18n)
- All button labels must wrap gracefully — avoid fixed-width buttons for labeled actions
- Table header text must truncate with ellipsis (`text-overflow: ellipsis`) when columns are constrained
- Form labels accommodate both short English labels and longer Chinese/Japanese equivalents
- Stat card labels at 14px–16px accommodate multi-byte characters in the same layout

---

## 9. Agent Prompt Guide

### Quick Color Reference
| Role | Value |
|------|-------|
| App background | `#f1f3f6` |
| Card / surface | `#ffffff` |
| Brand navy | `#003a8c` |
| Primary interactive (buttons, links) | `#409eff` |
| Primary hover | `#2c7be5` |
| **Primary text** | **`#303133`** |
| Sidebar nav text | `#6e84a3` |
| Active nav text | `#12263f` |
| Secondary / body text | `#767676` |
| Label / muted text | `#677796` |
| Status: Active/Online | `#52c41a` |
| Status: Inactive/Warning | `#ff8d1a` |
| Status: Danger/Error | `#e9378f` |
| Status: Disabled | `#a6a6a6` |
| Standard border | `#dcdfe6` |
| Card header border | `#dae0e8` |
| Sidebar divider | `#eef0f7` |
| Active nav background | `rgba(189,197,209,0.2)` |
| Row hover | `rgba(9,30,66,0.04)` |

### Example Component Prompts

- **Stat Card**: "Create a stat card on `#ffffff` background. Large number at 32px Poppins weight 700, `#12263f`. Label below at 16px weight 400, line-height 17px, `#677796`. Wrap in flex items-center text-center. Apply shadow: `0px 2px 4px -2px rgba(0,0,0,0.12), 0px 4px 8px 0px rgba(0,0,0,0.08), 0px 4px 16px 4px rgba(0,0,0,0.04)`. Border-radius 8px."

- **Data Table Row**: "Table on `#ffffff`. Cell padding 5px 10px. Row hover: `rgba(9,30,66,0.04)`. Border: `1px solid #dcdfe6`. Status column: pill badge — active `#52c41a`, inactive `#ff8d1a`, disabled `#a6a6a6` — all with `#ffffff` text, 3px border-radius, 12px font-size, weight 500. Actions column right-aligned, text buttons in `#409eff`."

- **Sidebar Nav Item**: "Sidebar nav link: 14px Poppins, `#6e84a3`, icon (16px `#b6c6dc`) + label, full-width click zone. Active state: text `#12263f`, icon color matches, left border 3px solid `#003a8c`, background `rgba(189,197,209,0.2)`. Sidebar width 250px, background `#ffffff`, divider `1px solid #eef0f7`."

- **Primary Form**: "Form on `#ffffff` card (20px padding, 8px radius, standard card shadow). Label 14px Poppins weight 400, `#606266`, float none. Input: border `1px solid #dcdfe6`, radius 4px, focus border `#409eff`. Margin-bottom 15px between items. Primary submit button: `#409eff` bg, `#ffffff` text, 8px 20px padding, 4px radius. Secondary cancel: `#ffffff` bg, `#dcdfe6` border, `#606266` text."

- **Status Badge**: "Status pill: Active — background `#52c41a`, text `#ffffff`, 12px Poppins weight 500, padding 2px 8px, border-radius 3px. Inactive — background `#ff8d1a`. Danger — background `#e9378f`. Disabled — background `#a6a6a6`."

- **App Container**: "Page layout: fixed navbar 60px `#ffffff` top. Sidebar 250px `#ffffff` left, fixed height. Main content area: `#f1f3f6` background, 20px padding, overflow-y scroll. Cards inside: `#ffffff`, 8px radius, standard 3-layer shadow, 20px padding."

- **Dialog**: "Modal dialog: `#ffffff` background, 4px radius, standard card shadow elevated. Width 60% desktop / 90% mobile. Header: title 18px Poppins weight 600, `#303133`, bottom border `1px solid #dcdfe6`. Body padding 20px. Footer: right-aligned, cancel + primary button pair."

- **Page Shell (完整页面骨架)**: "Build a TOMS Operator page shell. Fixed top navbar: 60px height, `#ffffff` background, breadcrumb left (14px Poppins `#303133`), user avatar + notification icon right. Left sidebar: 250px width, `#ffffff` background, `1px solid #eef0f7` right border. Nav items: 14px Poppins `#6e84a3`, icon (16px `#b6c6dc`) + label, full-width. Active item: `rgba(189,197,209,0.2)` background, `#12263f` text, `3px solid #003a8c` left border. Main content area: `#f1f3f6` background, 20px padding, overflow-y scroll, fills remaining viewport. Place a `#ffffff` card (8px radius, standard 3-layer shadow, 20px padding) inside the content area."

- **Data List Page (列表页模板)**: "Build a list page inside the TOMS content area (`#f1f3f6` bg, 20px padding). Top bar: page title 24px Poppins weight 600 `#303133` left; primary button `#409eff` right (8px 20px padding, 4px radius, `#ffffff` text). Filter row below: Select inputs (`--el-input-width: 200px`, `#dcdfe6` border, 4px radius), search input, secondary search button (3px 13px padding). Table: `#ffffff` bg, header `#f5f5f5`, cell padding 5px 10px, `1px solid #dcdfe6` border, 14px Poppins `#303133`, row hover `rgba(9,30,66,0.04)`. Status column: pill badges (active `#52c41a`, inactive `#ff8d1a`, 2px 8px padding, 3px radius, 12px weight 500). Actions column: text buttons `#409eff`, right-aligned. Bottom: pagination right-aligned, 16px top margin, active page `#409eff`."

### Iteration Guide
1. Always apply `font-family: 'Poppins', 'Helvetica Neue', 'PingFang SC', 'Microsoft YaHei', Arial, sans-serif` — CJK fallbacks are required
2. Set `#f1f3f6` as the app/page background — never `#ffffff` or white for the workspace
3. Cards always float on the gray workspace — always apply the 3-layer card shadow
4. Status colors are semantic only: green = online/active, orange = offline/inactive, red = fault/danger
5. Primary interactive = `#409eff`, brand anchor = `#003a8c` — these are different roles, never swap them
6. Data tables run dense: 5px 10px cell padding, `rgba(9,30,66,0.04)` row hover, no additional decoration
7. Poppins 600–700 for headings, 400–500 for data, 500 for tags/badges
8. All transitions: 0.28s for opacity fade, 0.3s for position/size slide — no bounce, no easing theatrics
9. i18n: never hardcode widths for text labels — all labels must flow with content length
10. Element Plus is the component base — extend it, don't replace it; apply TOMS overrides via CSS custom properties

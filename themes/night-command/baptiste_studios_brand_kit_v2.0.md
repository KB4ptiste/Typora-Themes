# Baptiste Studios Brand Kit Direction v2.0

## Version Summary

Version 2.0 is a major Brand Kit update. It keeps the Baptiste Studios color strategy from v1.5, but replaces the typography system and expands the Night Command section from a palette-level direction into a full implementation-ready theme specification.

Major v2.0 decisions:

1. Retire the previous condensed sans-serif utility voice completely. Do not use it in the active stack, fallback stack, typography guidance, examples, or implementation checklist.
2. Replace the v1.5 active stack with the current Night Command CSS stack.
3. Use Monaspace Argon and Monaspace Xenon as the utility/data replacement layer, not as a one-to-one swap across every UI surface.
4. Document Night Command's Typora implementation layer: token aliases, UI surfaces, document canvas, typography, lists, alerts, code, technical blocks, app chrome, export, and print behavior.
5. Clarify that Typora layout values such as `--max-width: 1128px` are implementation-specific, not universal brand layout rules.
6. Keep the Option A Smoked Command light-mode system from v1.5 until Smoked Command receives the same detailed implementation pass.
7. Keep the five additional accent families: Aether Cyan, Signal Teal, Tactical Blue, Rift Rose, and Astral Magenta.
8. Keep accent usage rules: accents classify content, not interaction.
9. Keep Fenix Violet as brand identity instead of forcing it into every interactive role.
10. Move version history to the bottom of this document, immediately before the end marker.

## Positioning

For PC and Mac strategy gamers, Baptiste Studios helps players master complex strategy games with focused companion web apps and practical strategy guides, unlike wikis and fan pages that bury useful decisions under trivia.

## Brand Line

Sharper tools for deeper strategy.

## Brand Personality

- Elegant
- Bold
- Playful
- Edgy

## Color Logic

The color system starts from a tactical dark-mode gaming interface, then builds a light-mode companion system for guides, documentation, SEO pages, and readable long-form content.

The primary purple recommendation comes from four constraints:

1. Purple supports strategy, mystery, depth, and premium tone.
2. Dark gray-purple supports gaming UI without becoming black-and-neon cliche.
3. The brand needs enough contrast for dashboards, tables, links, and guide text.
4. The system needs distinct roles: identity, action, background, surface, text, borders, accent, state, semantic status, and technical-document structure.

Do not treat a palette as a design system. A working UI needs more than `background`, `surface`, and `primary`. It needs readable surfaces, raised surfaces, sunken surfaces, selected states, hover states, strong borders, subtle borders, focus rings, links, buttons, semantic status colors, document components, technical blocks, and application chrome.

The dark theme separates buttons from links. Arcane Purple works well as a button fill, but Rift Lilac is better for readable dark-mode link text.

The additional accent colors are classification tools, not interaction colors. They help users scan strategy content, compare chart series, distinguish resource types, and identify tactical categories. They should not replace buttons, links, focus rings, semantic alerts, or brand identity.

The system uses five additional accent families. Five is enough range for product UI without turning the interface into a color junk drawer.

---

# Core Brand Colors

| Role | Name | Hex | Use |
|---|---|---:|---|
| Brand identity | Fenix Violet | `#4B2A7B` | Logo, brand blocks, headers, key visual identity |
| Dark-mode button purple | Arcane Purple | `#7C3AED` | Dark-mode button fills and selected-state borders |
| Light-mode button purple | Command Violet | `#6D28D9` | Light-mode CTAs and primary actions |
| Light-mode hover purple | Deep Command | `#5B21B6` | Light-mode links, hover, pressed, and high-contrast interactive states |
| Dark-mode link purple | Rift Lilac | `#A78BFA` | Dark-mode readable links, highlights, badges |
| Dark-mode focus purple | Moon Rift | `#C4B5FD` | Dark-mode focus rings and high-clarity hover states |
| Dark accent | Ember Gold | `#F59E0B` | Rare emphasis, premium callouts, warnings on dark surfaces |
| Light accent | Burnished Ember | `#92400E` | Accent text, warning labels, and badges on light surfaces |

---

# Additional Accent Colors

These colors extend the palette for tactical classification, guide systems, charts, faction/resource labeling, and non-semantic emphasis.

They are intentionally separate from semantic tokens. Do not use them as replacements for `--success`, `--warning`, `--danger`, or `--info`. Semantic colors describe system status. Accent colors describe content category.

## Accent Family Overview

| Accent Family | Dark Foreground | Dark Background | Light Foreground | Light Background | Primary Use |
|---|---:|---:|---:|---:|---|
| Aether Cyan | `#67E8F9` | `#0F2A33` | `#155E75` | `#CFFAFE` | Analysis, scouting, recommendations, insight callouts |
| Signal Teal | `#5EEAD4` | `#0F2F2A` | `#115E59` | `#CCFBF1` | Economy, efficiency, optimization, resource flow |
| Tactical Blue | `#60A5FA` | `#10233F` | `#1D4ED8` | `#DBEAFE` | Maps, routing, turn order, neutral system data |
| Rift Rose | `#FB7185` | `#35151E` | `#9F1239` | `#FFE4E6` | Enemy pressure, combat emphasis, PvP/meta threats |
| Astral Magenta | `#E879F9` | `#32173A` | `#86198F` | `#FAE8FF` | Rare items, faction identity, magic/lore, premium moments |

## Accent Strategy

| Layer | Colors | Job |
|---|---|---|
| Brand layer | Fenix Violet, Arcane Purple, Command Violet | Identity, primary action, recognition |
| Interaction layer | Button, link, hover, focus tokens | Clickable and keyboard-driven UI behavior |
| Semantic layer | Success, warning, danger, info | System status and feedback |
| Accent layer | Cyan, teal, blue, rose, magenta | Content classification and tactical emphasis |
| Document layer | Bullet scale, syntax colors, alert mappings, editorial marks | Long-form reading, technical documentation, and editor output |

## Accent Rules

1. Use accents for classification, not action.
2. Do not use additional accents for primary buttons, default links, focus rings, or selected-state borders.
3. Use accent foreground tokens for icons, short labels, chart series, and left borders.
4. Use accent background tokens for badges, small callouts, legend chips, and subtle grouped content.
5. Keep the default text color as `--text`; do not set long paragraphs in accent colors.
6. Use Aether Cyan for analysis and scouting.
7. Use Signal Teal for economy and optimization.
8. Use Tactical Blue for routing, maps, sequencing, and neutral system data.
9. Use Rift Rose for combat pressure, enemy emphasis, and PvP/meta threats.
10. Use Astral Magenta for rare, magical, faction, lore, and premium emphasis.
11. Use Ember Gold or Burnished Ember for rare brand emphasis and warning-adjacent premium callouts.
12. If more than two accents appear in one component, reduce the component complexity before adding more color.

---

# Dark Theme Palette: Night Command

## Product-Level Base Tokens

These are the cross-product dark theme tokens. They should be usable in apps, websites, documentation, and exported guide pages.

| Token | Name | Hex | Use |
|---|---|---:|---|
| `--bg` | Black Plum | `#100B15` | Main app background |
| `--surface` | Night Violet | `#1B1226` | Cards and panels |
| `--surface-raised` | Arcane Panel | `#27173A` | Modals, dropdowns, elevated panels |
| `--surface-sunken` | Void Well | `#0C0911` | Code blocks, tables, inset wells |
| `--surface-tint` | Rift Wash | `#21152F` | Nested panels, selected rows, hover backgrounds |
| `--border-subtle` | Shadow Plum | `#2E203D` | Internal dividers and quiet row lines |
| `--border` | Warden Violet | `#4B3764` | Visible card borders and section rules |

## Product-Level Text Tokens

| Token | Name | Hex | Use |
|---|---|---:|---|
| `--text` | Rune Lilac | `#D6C8EA` | Default primary text on dark surfaces |
| `--text-bright` | Moonlit Lilac | `#E7DCF5` | Hero text, key numbers, high-emphasis labels |
| `--text-muted` | Dust Wisteria | `#A99ABF` | Secondary text, captions, helper text |
| `--text-dim` | Ash Plum | `#847490` | Disabled and low-priority text |

## Product-Level Interaction Tokens

| Token | Name | Hex | Use |
|---|---|---:|---|
| `--primary` | Fenix Violet | `#4B2A7B` | Brand identity only |
| `--button` | Arcane Purple | `#7C3AED` | Primary action button background |
| `--button-hover` | Spell Violet | `#8B5CF6` | Hover and pressed button state |
| `--button-text` | White | `#FFFFFF` | Text on filled buttons |
| `--link` | Rift Lilac | `#A78BFA` | Readable inline links |
| `--link-hover` | Moon Rift | `#C4B5FD` | Link hover and high-emphasis interactive text |
| `--focus` | Moon Rift | `#C4B5FD` | Focus ring and keyboard navigation indicator |
| `--accent` | Ember Gold | `#F59E0B` | Rare emphasis and premium callouts |

## Product-Level State Tokens

| Token | Hex | Use |
|---|---:|---|
| `--state-hover-bg` | `#21152F` | General hover background |
| `--state-active-bg` | `#2B1844` | Pressed or active panel background |
| `--state-selected-bg` | `#24143A` | Selected nav item or active row background |
| `--state-selected-border` | `#7C3AED` | Active indicator, selected outline |

## Product-Level Semantic Tokens

| Token | Hex | Use |
|---|---:|---|
| `--success` | `#34D399` | Positive state, valid build, completed task |
| `--success-bg` | `#12281F` | Success badge or alert background |
| `--warning` | `#FBBF24` | Risk, timing issue, resource warning |
| `--warning-bg` | `#2B2110` | Warning badge or alert background |
| `--danger` | `#F87171` | Failure, blocker, destructive action |
| `--danger-bg` | `#2D151A` | Danger badge or alert background |
| `--info` | `#A78BFA` | Neutral tactical note or recommendation |
| `--info-bg` | `#211A34` | Info badge or alert background |

## Product-Level Additional Accent Tokens

| Token | Name | Hex | Use |
|---|---|---:|---|
| `--accent-cyan` | Aether Cyan | `#67E8F9` | Analysis, scouting, recommendation highlights |
| `--accent-cyan-bg` | Aether Cyan Well | `#0F2A33` | Cyan badge, callout, and chart-label background |
| `--accent-teal` | Signal Teal | `#5EEAD4` | Economy, optimization, efficiency labels |
| `--accent-teal-bg` | Signal Teal Well | `#0F2F2A` | Teal badge, callout, and chart-label background |
| `--accent-blue` | Tactical Blue | `#60A5FA` | Maps, routing, turn order, neutral system data |
| `--accent-blue-bg` | Tactical Blue Well | `#10233F` | Blue badge, callout, and chart-label background |
| `--accent-rose` | Rift Rose | `#FB7185` | Enemy pressure, combat emphasis, PvP/meta threats |
| `--accent-rose-bg` | Rift Rose Well | `#35151E` | Rose badge, callout, and chart-label background |
| `--accent-magenta` | Astral Magenta | `#E879F9` | Rare items, faction identity, magic/lore, premium highlights |
| `--accent-magenta-bg` | Astral Magenta Well | `#32173A` | Magenta badge, callout, and chart-label background |

---

# Night Command Implementation Tokens

Night Command has two token layers:

1. Product-level tokens such as `--bg`, `--surface`, `--button`, `--link`, and `--focus`.
2. Typora/base-engine aliases such as `--bg-color`, `--primary-color`, and `--text-color`.

Do not confuse `--primary` and `--primary-color`.

- `--primary` is Fenix Violet `#4B2A7B`, the brand identity color.
- `--primary-color` is the Typora/base-engine alias used by Night Command for many editor interactions. In the current CSS, it maps to Rift Lilac `#A78BFA`, not Fenix Violet.

## Typora Alias Token Map

| Typora/Base Token | Value | Maps To | Use |
|---|---:|---|---|
| `--max-width` | `1128px` | Typora-specific layout value | In-editor document canvas width only. Not a universal brand max width. |
| `--bg-color` | `#100B15` | `--bg` | Typora app background |
| `--text-color` | `#D6C8EA` | `--text` | Typora primary text |
| `--text-color-secondary` | `#A99ABF` | `--text-muted` | Typora secondary text |
| `--primary-color` | `#A78BFA` | `--link` / Rift Lilac | Typora engine active color, heading markers, editor highlights |
| `--secondary-color` | `#7C3AED` | `--button` / Arcane Purple | Base-engine secondary color |
| `--accent-color` | `#F59E0B` | `--accent` / Ember Gold | Rare accent and warning-adjacent emphasis |
| `--border-color` | `#4B3764` | `--border` | Main visible border |
| `--hover-background-color` | `#A78BFA` | Rift Lilac | Base-engine hover driver |
| `--select-text-bg-color` | `rgba(124, 58, 237, 0.35)` | Arcane Purple alpha | Text selection background |
| `--active-file-bg-color` | `rgba(167, 139, 250, 0.12)` | Rift Lilac alpha | Active file/sidebar background |
| `--active-file-text-color` | `#E7DCF5` | `--text-bright` | Active file/sidebar text |
| `--active-file-border-color` | `#A78BFA` | `--link` | Active file/sidebar border |
| `--caret-color` | `#A78BFA` | `--link` | Editor caret |
| `--monospace` | `"MonaspaceXenon", "Lotion", monospace` | `--font-data` | Base-engine monospace compatibility alias |

## Glow Tokens

| Token | Value | Use |
|---|---|---|
| `--glow-color` | `rgba(167, 139, 250, 0.50)` | Generic Typora glow |
| `--glow-shadow-text` | `0 0 8px rgba(167, 139, 250, 0.50)` | Hover/focus text glow |
| `--glow-shadow-box` | `0 0 8px rgba(167, 139, 250, 0.50)` | Hover/focus box glow |

## Heading Support Tokens

| Token | Value | Use |
|---|---|---|
| `--h1-underline-color` | `#C4B5FD` | H1 underline and hover expansion |
| `--h2-bg-image` | `radial-gradient(ellipse at center bottom, rgba(196, 181, 253, 0.08), transparent 70%)` | H2 default glass wash |
| `--h2-bg-image-hover` | `radial-gradient(ellipse at center bottom, rgba(196, 181, 253, 0.20), transparent 70%)` | H2 hover glass wash |
| `--h2-border-bottom-hover` | `rgba(196, 181, 253, 0.35)` | H2 hover border |
| `--element-color` | `#8B5CF6` | H3-H6 counters and element markers |
| `--element-color-soo-shallow` | `rgba(139, 92, 246, 0.12)` | Shallow element accent |
| `--element-color-deep` | `#C4B5FD` | Deep element accent |
| `--head-title-h2-color` | `#C4B5FD` | H2 counter/title support color |

## Background Texture Tokens

| Token | Value | Use |
|---|---|---|
| `--bg-style` | `radial-gradient(#ffffff 1px, transparent 1px)` | Dot mask shape |
| `--texture-mask-color` | `#4B2A7B` | Fenix Violet texture mask |
| `--texture-opacity` | `0.04` | Document texture opacity |

## Auto-Numbering Tokens

Auto-numbering is disabled in the current Night Command CSS.

```css
--autonum-h1: "";
--autonum-h2: "";
--autonum-h3: "";
--autonum-h4: "";
--autonum-h5: "";
--autonum-h6: "";
```

If heading numbering is restored later, preserve the current disabled state as the default.

---

# Night Command UI Surface Ladder

The UI ladder is denser than the product-level palette because editor chrome, menus, modals, search, quick open, and source view need more state separation than normal marketing or guide pages.

| Token | Value | Purpose |
|---|---:|---|
| `--ui-surface-base` | `#100B15` | Base UI shell |
| `--ui-surface-raised` | `#17101F` | Sidebar, modals, raised panels |
| `--ui-surface-overlay` | `#1D1427` | Popovers, hover overlays, modal bodies |
| `--ui-surface-hover` | `#251833` | Hover state |
| `--ui-surface-active` | `#2D1C40` | Active/selected state |
| `--ui-surface-pressed` | `#1A1124` | Pressed state |
| `--ui-text-strong` | `#E7DCF5` | Strong UI labels |
| `--ui-text` | `#D6C8EA` | Default UI text |
| `--ui-text-muted` | `#A99ABF` | Secondary UI text |
| `--ui-text-disabled` | `#756A82` | Disabled UI text |
| `--ui-border-subtle` | `#342442` | Quiet UI borders |
| `--ui-border` | `#4B3764` | Standard UI borders |
| `--ui-border-active` | `#A78BFA` | Active UI border |
| `--ui-focus-outline` | `#C4B5FD` | Focus outline |
| `--ui-accent-soft` | `#F0A8C6` | Soft rose utility accent |
| `--ui-accent-soft-hover` | `#F6C2D8` | Soft rose hover text and active control highlight |
| `--ui-glow-hover` | `0 0 8px rgba(167, 139, 250, 0.18)` | Hover glow |
| `--ui-glow-active` | `0 0 10px rgba(167, 139, 250, 0.24)` | Active glow |
| `--ui-glow-focus` | `0 0 0 1px #C4B5FD, 0 0 14px rgba(167, 139, 250, 0.42)` | Focus glow |

## UI Ladder Rules

1. Use `#100B15` for the editor shell and source wells.
2. Use `#17101F` for raised panels, modals, blocks, images, diagrams, and default alert fills.
3. Use `#1D1427` for overlays, hover surfaces, and focused document blocks.
4. Use `#21152F` for nested panels, code labels, inline code, and compact control fills.
5. Use `#2D1C40` for active controls and selected UI rows.
6. Use `#4B3764` for visible borders.
7. Use `#342442` for subtle UI borders.
8. Use `#A78BFA` for active borders and editor-specific active indicators.
9. Use `#C4B5FD` for focus outlines.
10. Use `#F0A8C6` and `#F6C2D8` for soft rose utility states, not primary brand actions.

---

# Night Command Typography

## Active Font Stack

This stack replaces the v1.5 stack. The previous condensed sans-serif utility voice is retired and must not appear in active guidance.

```css
--font-display: "Wak", "Lucy Rose", sans-serif;
--font-body: "Source Serif 4 Variable", "Source Serif 4", Georgia, serif;
--font-ui: "MonaspaceArgon", "Monaspace Argon", monospace;
--font-data: "MonaspaceXenon", "Lotion", monospace;
```

## Font Roles

| Role | Font | Fallback | Weight / Style | Use |
|---|---|---|---|---|
| Major titles and headings | Wak | Lucy Rose | Light 300, Book 400, Medium 500, Bold 700, ExtraBold 800, Black 900 | Logo, wordmark, major titles, H1-H4, campaign headlines, key visual identity |
| Prose and longer application text | Source Serif 4 Variable | Source Serif 4, Georgia | Variable 200-900, static Regular 400, Medium 500, SemiBold 600, Bold 700, italics | Document prose, guide text, descriptions, dialogs, notifications, tooltips, help text, captions |
| Navigation and compact UI | Monaspace Argon | Monaspace Argon fallback name, monospace | Regular 400, Medium 500, Bold 700 | Navigation, controls, tabs, menus, file tree, compact labels, Preferences, editor chrome |
| Code, metadata, technical values, and data | Monaspace Xenon | Lotion, monospace | Regular 400, Bold 700 | Code, metadata, technical values, data tables, build codes, source view, inline code |

## Font Files And Weights

### Wak

Available files:

- `Wak-Light.ttf` at 300
- `Wak-Book.ttf` at 400
- `Wak-Medium.ttf` at 500
- `Wak-Bold.ttf` at 700
- `Wak-ExtraBold.ttf` at 800
- `Wak-Black.ttf` at 900

Use Wak for brand-defining text. Avoid it for body copy, small controls below readable display size, dense tables, code, and long UI descriptions.

### Source Serif 4

Available static files:

- `SourceSerif4-Regular.ttf` at 400
- `SourceSerif4-Italic.ttf` at 400 italic
- `SourceSerif4-Medium.ttf` at 500
- `SourceSerif4-MediumItalic.ttf` at 500 italic
- `SourceSerif4-SemiBold.ttf` at 600
- `SourceSerif4-Bold.ttf` at 700
- `SourceSerif4-BoldItalic.ttf` at 700 italic

Available variable files:

- `SourceSerif4-VariableFont_opsz,wght.ttf`
- `SourceSerif4-Italic-VariableFont_opsz,wght.ttf`

Use the variable files as the preferred body face where supported. Set:

```css
font-optical-sizing: auto;
```

Separate `_8pt` files are unnecessary for the current Night Command direction. Existing 18pt files may remain available for compatibility, but the variable optical-size files are the preferred path.

### Monaspace Argon

Available files:

- `MonaspaceArgon-Regular.otf` at 400
- `MonaspaceArgon-Medium.otf` at 500
- `MonaspaceArgon-Bold.otf` at 700

Use Monaspace Argon for interface structure: navigation, controls, tabs, menus, file tree, compact labels, Preferences, search panels, quick open, footer controls, and similar chrome.

Do not replace Source Serif 4 with Monaspace Argon across every UI surface. Descriptions, dialogs, notifications, tooltips, and help text should use Source Serif 4 when they require sustained reading.

### Monaspace Xenon

Available files:

- `MonaspaceXenon-Regular.otf` at 400
- `MonaspaceXenon-Bold.otf` at 700

Use Monaspace Xenon for code, metadata, technical values, source view, table-like values, and data.

### Lotion

Available files:

- `Lotion-Regular.ttf` at 400
- `Lotion-Bold.ttf` at 700

Use Lotion only as fallback for Monaspace Xenon. Confirm monospace behavior before using it in production data tables.

## Typography Rules

1. Use Wak for major titles and headings where brand identity matters.
2. Use Source Serif 4 for document prose and longer application text.
3. Use Monaspace Argon for navigation, controls, tabs, menus, file tree, compact labels, and Preferences.
4. Use Monaspace Xenon for code, metadata, technical values, and data.
5. Do not use the previous condensed sans-serif utility voice.
6. Do not replace the previous utility voice one-to-one across every UI surface. The replacement is a role split between Source Serif 4, Monaspace Argon, and Monaspace Xenon.
7. Use `font-optical-sizing: auto` with Source Serif 4 variable files.
8. Use lining figures where Source Serif 4 renders numeric data:

```css
font-variant-numeric: lining-nums;
```

9. Lucy Rose is an Adobe Fonts license and cannot be self-hosted. Verify Adobe Fonts CDN before relying on it in web products.
10. Do not introduce another active font voice without retiring one of the existing voices.

---

# Night Command Heading System

The current Typora Night Command CSS uses a more nuanced heading hierarchy than v1.5. Wak owns major headings, while Source Serif 4 handles lower-level body-adjacent headings in long-form documents.

| Heading | Font | Weight | Size | Color | Behavior |
|---|---|---:|---:|---:|---|
| H1 | Wak | 800 | `1.8rem` | `#E7DCF5` | Centered, fit-content, underline expands on hover/focus, subtle lift |
| H2 | Wak | 700 | `1.4rem` | `#C4B5FD` | Glass/radial surface, hover wash, Moon Rift emphasis |
| H3 | Wak | 700 | `1.25rem` | `#A78BFA` | Left rule, tactical icon mask, hover to `#C4B5FD` |
| H4 | Wak | 600 | `1.15rem` | `#8B5CF6` | Dot decorator from base engine, hover translate/glow |
| H5 | Source Serif 4 | 500 | `1.1rem` | `#A99ABF` | Body-adjacent lower heading |
| H6 | Source Serif 4 | 500 | `1.05rem` | `#847490` | Lowest hierarchy heading, body-adjacent |

## Heading Rules

1. Use Wak for H1-H4 in Night Command documents.
2. Use Source Serif 4 for H5-H6 in long-form/editorial document contexts.
3. Do not interpret the H5-H6 exception as permission to use Source Serif 4 for campaign headlines.
4. Use H1 sparingly. It carries the strongest identity weight.
5. Use H2 for major document sections.
6. Use H3-H4 for scannable tactical subsections.
7. Use H5-H6 only when hierarchy depth is genuinely needed.

## Heading Icon Masks

Night Command uses tactical dot-grid SVG mask icons for H3-H6 in Typora. The raw SVG data lives in the CSS as:

- `--h3-icon-shape`
- `--h4-icon-shape`
- `--h5-icon-shape`
- `--h6-icon-shape`

Brand Kit guidance: document the concept, not the raw SVG path data. H3-H6 may use tactical dot-grid masks in document/editor contexts. The icon color inherits the Typora active color, currently Rift Lilac through `--primary-color`.

---

# Night Command Document Canvas

The Typora document canvas is an implementation target, not a universal app layout rule.

## In-Editor Canvas

Current Typora Night Command values:

| Property | Value |
|---|---|
| Max width | `1128px` through `--max-width` |
| Margin | `16px auto 0` |
| Padding | `3rem 2.5rem 6rem 2.5rem` |
| Line height | `1.85` |
| Letter spacing | `normal` |
| Word spacing | `normal` |
| Backdrop blur | `8px` |
| Background color | `#15101C` |
| Background image | `radial-gradient(ellipse at center top, #1B1425 0%, #15101C 58%, #120D18 100%)` |
| Border | `4px solid #4B3764` |
| Radius | `18px` |
| Texture mask | Fenix Violet dot mask at `0.04` opacity |
| Numeric style | `font-variant-numeric: lining-nums` |

## Export Canvas

Current Typora export values:

| Property | Value |
|---|---|
| Width | `min(92%, 1100px)` |
| Max width | `1100px` |
| Margin | `24px auto` |
| Padding | `56px 72px` |
| Border | `4px solid #4B3764` |
| Radius | `18px` |
| Shadow | `0 18px 42px rgba(0, 0, 0, 0.28)` |
| Background | Same radial document canvas gradient |

When export sidebar is present, `#write` shifts to `margin: 20px 24px 20px 372px` with no max width.

## Print Canvas

Current print values:

- Page margin: `1mm`.
- Page background: `#100B15`.
- Print `#write` width: `100%`.
- Print padding: `3mm`.
- Print border: `3px solid #4B3764`.
- Print radius: `14px`.
- Print color adjustment: exact.
- Sidebar hidden.
- Code wraps.
- Images, diagrams, tables, and canvases constrained to `max-width: 100%`.

## Layout Rule

Do not copy `1128px` into unrelated apps as a brand requirement. It is the current Typora in-editor document canvas width. Product screens, web apps, and Smoked Command should choose widths based on their own layout needs.

---

# Night Command List System

Night Command replaces generic bullets with a ten-level Unicode marker system. This is a reusable brand pattern for documents and strategy guides.

| Level | Marker | Color | Size |
|---:|---|---:|---:|
| 1 | `STAR FILLED` | `#E7DCF5` | `0.94rem` |
| 2 | `STAR OUTLINE` | `#DCCEF0` | `0.92rem` |
| 3 | `FOUR-POINT STAR FILLED` | `#D0BFEA` | `0.90rem` |
| 4 | `FOUR-POINT STAR OUTLINE` | `#C4B1E3` | `0.88rem` |
| 5 | `TRIANGLE LEFT-SPLIT` | `#B8A2D8` | `0.86rem` |
| 6 | `TRIANGLE RIGHT-SPLIT` | `#AB93CC` | `0.84rem` |
| 7 | `DIAMOND LEFT-SPLIT` | `#9D84BE` | `0.83rem` |
| 8 | `DIAMOND RIGHT-SPLIT` | `#8F75AF` | `0.81rem` |
| 9 | `STAR FILLED` | `#80679F` | `0.80rem` |
| 10 | `STAR OUTLINE` | `#725A8E` | `0.78rem` |

CSS marker glyphs:

```css
Level 1: "★ "
Level 2: "☆ "
Level 3: "✦ "
Level 4: "✧ "
Level 5: "⯍ "
Level 6: "⯏ "
Level 7: "⯌ "
Level 8: "⯎ "
Level 9: "★ "
Level 10: "☆ "
```

Marker font stack:

```css
"Segoe UI Symbol", "Source Serif 4", Georgia, serif
```

List rules:

1. Use the ten-level marker scale for unordered lists in Night Command documents.
2. Do not use the bullet color scale as a general-purpose palette.
3. Ordered lists remain decimal, lower-alpha, and lower-roman from the base engine unless a future brand decision changes them.
4. Vertical connector lines are disabled in the current wrapper. Do not reintroduce them without a deliberate style decision.

---

# Night Command Code And Technical Tokens

## Code Fonts

Use Monaspace Xenon for:

- Fenced code.
- Inline code.
- Source view.
- Metadata blocks.
- Technical values.
- CodeMirror content.
- Keyboard tokens.

## Syntax Tokens

| Syntax Role | Token | Value |
|---|---|---:|
| Keyword/header/tag | `--code-keyword` | `#C4B5FD` |
| Variable/default | `--code-variable` | `#D6C8EA` |
| Function/definition/builtin | `--code-function` | `#67E8F9` |
| Parameter | `--code-param` | `#5EEAD4` |
| String | `--code-string` | `#86EFAC` |
| Comment/quote | `--code-comment` | `#847490` |
| Type/link/url | `--code-type` | `#60A5FA` |
| Property/attribute | `--code-property` | `#5EEAD4` |
| Number/atom | `--code-number` | `#FCA5A5` |
| Meta/hr | `--code-meta` | `#5EEAD4` |
| Selected code background | `--code-selected-bg` | `#24143A` |
| Line number | `--code-line-number` | `#725F82` |

## Fenced Code Blocks

Current rules:

- Width: `75%`.
- Minimum width: `55%`.
- Maximum width: `900px`.
- Horizontal margin: auto.
- Background: `#0C0911`.
- Border: `#4B3764`.
- Focus border: `#A78BFA`.
- Focus glow: `--ui-glow-active`.
- Default missing-language label: `TEXT`.
- Label text: soft rose.
- Default label background: `#21152F`.
- Focused label background: `#27173A`.

Print rule:

- Code blocks print at `100%` width.
- Code wraps with `white-space: pre-wrap`.
- Code breaks long words where needed.

## Inline Code

Current rules:

- Text: `#C4B5FD`.
- Background: `#21152F`.
- Border: `#4B3764`.
- Hover text: `#E7DCF5`.
- Hover background: `#2D1C40`.
- Hover border: `#A78BFA`.
- Hover glow: `0 0 10px rgba(167, 139, 250, 0.22)`.

## Source View

Current rules:

- Text: `#D6C8EA`.
- Background: `#100B15`.
- Font: Monaspace Xenon through `--font-data`.
- Gutters: `#0C0911`.
- Gutter text: `#847490`.
- Line numbers: `#725F82`.
- Selected background: `#24143A`.
- Cursor: `#A78BFA`.

---

# Night Command Editorial Elements

## Section Separator

Night Command uses a centered star glyph as the section separator.

Current values:

- Glyph: `✦` / `U+2726`.
- Color: `#A78BFA`.
- Background patch: `#15101C`.
- Font size: `0.85rem`.
- Horizontal padding: `0.75rem`.
- Hover animation: continuous spin, `1.8s linear`.
- Hover text shadow: `0 0 8px #A78BFA`.

Use this as a brand-signature editorial separator in Night Command documents. Do not use it for dense app dividers.

## Blockquotes

Current values:

- Text: `#A99ABF`.
- Surface: `#17101F`.
- Border: `1px solid #4B3764`.
- Left border: `4px solid #A78BFA`.
- Radius: `14px`.
- Marker: `!`.
- Marker font: Monaspace Xenon through `--font-data`.
- Marker color: `#F0A8C6`.
- Hover surface: `#1D1427`.
- Hover border: `#A78BFA`.
- Hover glow: lilac at `0.12`.

Do not merge blockquotes with semantic alerts. A quote is editorial emphasis. An alert is status or classification.

## Task Lists

Current values:

- Checkbox size: `1.12rem`.
- Unchecked fill: `#17101F`.
- Unchecked border: `#4B3764`.
- Checked fill: `rgba(240, 168, 198, 0.18)`.
- Checked border: `#F0A8C6`.
- Checked glow: `0 0 8px rgba(240, 168, 198, 0.35)`.
- Checked inner glow: `inset 0 0 5px rgba(240, 168, 198, 0.18)`.
- Checked text: `#847490`.
- Checked opacity: `0.82`.

Use this style for editorial task lists in documents. Product task completion may use semantic success instead.

## Inline Text

| Element | Treatment |
|---|---|
| Link | `#A78BFA`; hover `#E7DCF5` with lilac glow; visited `#B9A3E8` |
| Strong | `#C4B5FD` with subtle lilac glow; hover underline |
| Emphasis | `#B9A3E8` in the wrapper |
| Mark | `#E7DCF5` over soft rose gradient; hover blends rose and lilac |
| Delete | Text `#847490`; decoration `#725A8E`; hover decoration soft rose |
| Inline code | Monaspace Xenon, Moon Rift text, Rift Wash fill, Warden Violet border |

## Footnotes

Current values:

- Footnote text: `#A99ABF`.
- Footnote references: `#F0A8C6`.
- Reference font: Monaspace Xenon through `--font-data`.
- Reference fill: `#21152F`.
- Reference border: `#4B3764`.
- Reference radius: `5px`.
- Reference hover text: `#F6C2D8`.
- Reference hover border: `#F0A8C6`.
- Reference hover glow: soft rose.
- Footnote section top border: `#4B3764`.
- Footnote section top margin: `3.5rem`.

## Images And Captions

Current image values:

- Border: `2px solid #4B3764`.
- Radius: `14px`.
- Background: `#17101F`.
- Shadow: black elevation plus inner highlight.
- Hover: brightness and contrast lift.
- Hover scale: `1.01`.
- Hover glow: lilac at `0.12`.

Current caption values:

- Caption color: `#A99ABF`.
- Caption font: Source Serif 4.
- Caption size: `0.9rem`.
- Caption hover color: `#C4B5FD`.
- Export caption color: `#B9A3E8`.
- Export captions are centered.

## Metadata Blocks

Current values:

- Text: `#A99ABF`.
- Surface: `#17101F`.
- Border: `1px dashed #4B3764`.
- Radius: `12px`.
- Shadow: black elevation.
- Hover text: `#D6C8EA`.
- Hover surface: `#1D1427`.
- Hover border: `#A78BFA`.
- Label color: `#F0A8C6`.
- Label background: `#21152F`.
- Label border: `#4B3764`.

---

# Night Command Markdown Alerts

Night Command distinguishes Markdown/editorial alerts from product semantic alerts.

Product semantic alerts use `--success`, `--warning`, `--danger`, and `--info`.

Markdown/editorial alerts use Typora/GitHub-style classes:

| Alert Class | Border/Text Color | Accent Family | Emoji Marker |
|---|---:|---|---|
| Note | `#67E8F9` | Aether Cyan | Pushpin |
| Tip | `#5EEAD4` | Signal Teal | Light bulb |
| Warning | `#F59E0B` | Ember Gold | Warning sign |
| Important | `#E879F9` | Astral Magenta | Target |
| Caution | `#FB7185` | Rift Rose | Stop sign |

Shared alert values:

- Text: `#D6C8EA`.
- Surface: `#17101F`.
- Border: `1px solid #4B3764`.
- Left border width: `4px`.
- Radius: `14px`.
- Hover surface: `#1D1427`.
- Hover glow: lilac at `0.12`.
- Native Typora/octicon alert icons are hidden.
- Emoji markers appear through alert pseudo-elements and the alert text container.

Emoji policy:

1. Emoji markers are allowed in Markdown/editorial contexts.
2. Product UI should use icon components instead of emoji unless the interface is intentionally casual.
3. Keep alert colors tied to their meaning. Do not randomize alert colors for variety.

---

# Night Command Technical Document Blocks

## Math Blocks

Current values:

- Text: `#D6C8EA`.
- Surface: `#17101F`.
- Border: `1px solid #4B3764`.
- Radius: `12px`.
- Focus surface: `#1D1427`.
- Focus border: `#A78BFA`.
- Focus glow: lilac at `0.16`.
- Editing surface: `#100B15`.
- Editing font: Monaspace Xenon through `--font-data`.

## Diagrams

Current values:

- Diagram surface: `#17101F`.
- Border: `#4B3764`.
- Radius: `12px`.
- Focus border: `#A78BFA`.
- Focus glow: lilac at `0.16`.
- Error text: `#FCA5A5`.
- Error background: `#35151E`.
- Error border: `#FB7185`.
- Error font: Monaspace Xenon through `--font-data`.

## Mermaid Edge Labels

Current v2.49 values:

- Label text: `#FFF4FA`.
- Label background: `#F0A8C6`.
- Label border/stroke: `#F6C2D8`.
- Label text shadow: `0 1px 2px rgba(16, 11, 21, 0.45)`.
- Rect radius: `4px`.

This changed from the prior dark-text Mermaid label treatment. Use the v2.49 light-label version.

## HTML And Raw Blocks

Current values:

- Surface: `#17101F`.
- Border: `1px solid #4B3764`.
- Radius: `12px`.
- Hover surface: `#1D1427`.
- Hover border: `#A78BFA`.
- Hover glow: lilac at `0.12`.
- Input text: `#D6C8EA`.
- Input background: `#100B15`.
- Input font: Monaspace Xenon through `--font-data`.
- Tooltip background: `#21152F`.
- Tooltip border: `#4B3764`.
- Tooltip radius: `8px`.

---

# Night Command Tables

## Document Tables

Current Typora document values:

- Width: auto.
- Maximum width: `100%`.
- Horizontal margin: auto.
- Default table surface: `#17101F`.
- Header surface: `#21152F`.
- Cell surface: `#17101F`.
- Table and table figures overflow horizontally when needed.

## Table Resize Popover

Current app chrome values:

- Width: `max-content`.
- Background: `#100B15`.
- Border: glow color.
- Radius: `12px`.
- Grid cell size: `16px`.
- Grid gap: `3px`.
- Selected/extended grid cells: `#A78BFA`.
- Inputs: `36px` by `24px`.
- Input border: `#4B3764`.
- Focus border: `#A78BFA`.
- Title font: Monaspace Xenon through `--monospace`.

---

# Night Command Application Chrome

The Brand Kit should document patterns and tokens, not every Typora selector.

Covered areas:

- Sidebar.
- Outline.
- File tree.
- File library search.
- Context menus.
- Dropdown menus.
- Modal content and modal body.
- Dialogs.
- Popovers.
- Tooltips.
- Search panel.
- Quick open.
- Notifications.
- Spell-check panel.
- Footer controls.
- Source-view toggle.
- Table resize popover.
- Megamenu.
- Theme preview grid.

## Chrome Surface Rules

| Component Type | Surface | Border | Text | Font |
|---|---:|---:|---:|---|
| Sidebar/file tree | `#17101F` / `#100B15` | `#4B3764` / `#342442` | `#D6C8EA` / `#A99ABF` | Monaspace Argon |
| Modals/dialogs | `#17101F` outer, `#100B15` body | `#4B3764` | `#D6C8EA` | Source Serif 4 for longer copy, Monaspace Argon for controls |
| Popovers/tooltips | `#17101F` | `#4B3764` | `#D6C8EA` | Source Serif 4 for content, Monaspace Argon for controls |
| Dropdown/context menu | `#17101F` / transparent rows | `#4B3764` | `#D6C8EA` | Monaspace Argon |
| Search/quick open | `#17101F` shell, `#100B15` inputs | `#4B3764` | `#D6C8EA` | Monaspace Argon |
| Notifications | `#17101F` | `#4B3764`, left accent `#F0A8C6` | `#D6C8EA` | Source Serif 4 |
| Footer/spell check | `#1D1427` | `#4B3764` | `#D6C8EA` | Monaspace Argon |

## Chrome Interaction Rules

1. Use `#21152F` for default compact controls.
2. Use `#2D1C40` for hover and active control fills.
3. Use `#A78BFA` for active lilac borders and left indicators.
4. Use `#F0A8C6` for soft rose active utility controls.
5. Use `#F6C2D8` for soft rose hover text.
6. Use `#C4B5FD` for input focus outline.
7. Use inset left rules for active menu and search rows when helpful.
8. Avoid overusing glow. Glow should clarify active/focus state, not decorate every element.

---

# Night Command Focus Mode

Current Focus Mode values:

- Non-focused content color: `#4B3764`.
- Non-focused content opacity: `0.5`.
- Focused content color: `#D6C8EA`.
- Non-focused images opacity: `0.25`.
- Non-focused task-list inputs opacity: `0.25`.

Focus Mode rule: dim the surrounding document without hiding structure. Do not lower opacity so far that page context disappears.

---

# Light Theme Palette: Option A Smoked Command

This section remains the v1.5 light-mode specification until Smoked Command receives the same implementation-level update as Night Command.

## Base Tokens

| Token | Name | Hex | Use |
|---|---|---:|---|
| `--bg` | Smoked Lilac | `#DED2E8` | Default page background |
| `--surface` | Rune Mist | `#E9E0F1` | Cards, guide blocks, article panels |
| `--surface-readable` | White | `#FFFFFF` | Long guides, forms, dense tables |
| `--surface-raised` | High Rune | `#F3EEF8` | Popovers, dropdowns, floating cards |
| `--surface-tint` | Veil Amethyst | `#D2C2E2` | Callouts, selected panels, table headers |
| `--surface-sunken` | Inset Lilac | `#C8B6DB` | Filter wells, code blocks, inset panels |
| `--border-subtle` | Soft Amethyst | `#CAB8DC` | Internal dividers and table rows |
| `--border` | Worn Amethyst | `#BCA8D0` | Cards, fields, default outlines |
| `--border-strong` | Iron Amethyst | `#9F86B8` | Selected cards, important containers |

## Text Tokens

| Token | Name | Hex | Use |
|---|---|---:|---|
| `--text` | Void Ink | `#17111F` | Primary text on light surfaces |
| `--text-muted` | Grave Plum | `#554A60` | Captions, helper text, metadata |
| `--text-dim` | Weathered Plum | `#7A6D86` | Placeholder and disabled-adjacent text |
| `--text-inverse` | Moon Ink | `#F5F1FF` | Text on dark brand blocks and filled purple buttons |

## Interaction Tokens

| Token | Name | Hex | Use |
|---|---|---:|---|
| `--primary` | Fenix Violet | `#4B2A7B` | Brand identity, logo, headings, brand blocks |
| `--button` | Command Violet | `#6D28D9` | Primary action button background |
| `--button-hover` | Deep Command | `#5B21B6` | Hover and pressed button state |
| `--button-text` | White | `#FFFFFF` | Text on filled buttons |
| `--link` | Deep Command | `#5B21B6` | Readable inline links |
| `--link-hover` | Fenix Violet | `#4B2A7B` | Link hover and brand-heavy text states |
| `--focus` | Arcane Purple | `#7C3AED` | Focus ring and keyboard navigation indicator |
| `--accent` | Burnished Ember | `#92400E` | Accent text, warning labels, badges |

## State Tokens

| Token | Hex | Use |
|---|---:|---|
| `--state-hover-bg` | `#D8C9E6` | General hover background |
| `--state-active-bg` | `#CDB9DF` | Pressed state or active panel background |
| `--state-selected-bg` | `#D2C2E2` | Selected nav item or active row background |
| `--state-selected-border` | `#6D28D9` | Active indicator, selected outline |

## Semantic Tokens

| Token | Hex | Use |
|---|---:|---|
| `--success` | `#047857` | Positive state, valid build, completed task |
| `--success-bg` | `#D1FAE5` | Success badge or alert background |
| `--warning` | `#92400E` | Risk, timing issue, resource warning |
| `--warning-bg` | `#FEF3C7` | Warning badge or alert background |
| `--danger` | `#B91C1C` | Failure, blocker, destructive action |
| `--danger-bg` | `#FEE2E2` | Danger badge or alert background |
| `--info` | `#5B21B6` | Neutral tactical note or recommendation |
| `--info-bg` | `#EDE9FE` | Info badge or alert background |

## Additional Accent Tokens

| Token | Name | Hex | Use |
|---|---|---:|---|
| `--accent-cyan` | Aether Cyan | `#155E75` | Analysis, scouting, recommendation highlights |
| `--accent-cyan-bg` | Aether Cyan Wash | `#CFFAFE` | Cyan badge, callout, and chart-label background |
| `--accent-teal` | Signal Teal | `#115E59` | Economy, optimization, efficiency labels |
| `--accent-teal-bg` | Signal Teal Wash | `#CCFBF1` | Teal badge, callout, and chart-label background |
| `--accent-blue` | Tactical Blue | `#1D4ED8` | Maps, routing, turn order, neutral system data |
| `--accent-blue-bg` | Tactical Blue Wash | `#DBEAFE` | Blue badge, callout, and chart-label background |
| `--accent-rose` | Rift Rose | `#9F1239` | Enemy pressure, combat emphasis, PvP/meta threats |
| `--accent-rose-bg` | Rift Rose Wash | `#FFE4E6` | Rose badge, callout, and chart-label background |
| `--accent-magenta` | Astral Magenta | `#86198F` | Rare items, faction identity, magic/lore, premium highlights |
| `--accent-magenta-bg` | Astral Magenta Wash | `#FAE8FF` | Magenta badge, callout, and chart-label background |

## Light Theme Rules

1. Use Smoked Lilac as the default page background.
2. Use Rune Mist for standard cards and guide blocks.
3. Reserve white for dense reading, forms, data-heavy tables, and high-clarity content.
4. Use Veil Amethyst for table headers, guide callouts, selected panels, and low-emphasis content wells.
5. Use Inset Lilac for sunken panels, filters, and code-like areas.
6. Use Deep Command for links, not Arcane Purple.
7. Use Command Violet for button fills.
8. Use Burnished Ember sparingly for accent text and warning-adjacent labels.
9. Do not return to near-white lavender as the default background. It weakens the tactical tone.

---

# Component Usage Guidance

## Buttons

Use separate button tokens. Do not use `--primary` for every click target.

```css
.button-primary {
  background: var(--button);
  color: var(--button-text);
  border: 1px solid transparent;
}

.button-primary:hover {
  background: var(--button-hover);
}
```

## Links

Use link tokens, not button tokens.

```css
a {
  color: var(--link);
  text-decoration-thickness: 1px;
  text-underline-offset: 0.18em;
}

a:hover {
  color: var(--link-hover);
}
```

Night Command Typora adds:

- Visited link color: `#B9A3E8`.
- Hover color: `#E7DCF5`.
- Hover glow: lilac at `0.42`.

## Cards

```css
.card {
  background: var(--surface);
  color: var(--text);
  border: 1px solid var(--border);
}

.card-raised {
  background: var(--surface-raised);
}

.card-sunken {
  background: var(--surface-sunken);
  border-color: var(--border-subtle);
}
```

## Guide Articles

Use `--surface` for normal branded guide blocks. Use `--surface-readable` for dense reading, forms, and long articles in light mode. In Night Command dark documents, use the document canvas rules instead of generic card styling.

## Navigation

```css
.nav-item:hover {
  background: var(--state-hover-bg);
}

.nav-item:active {
  background: var(--state-active-bg);
}

.nav-item[aria-current="page"] {
  background: var(--state-selected-bg);
  border-left: 3px solid var(--state-selected-border);
}
```

Night Command Typora navigation should use Monaspace Argon.

## Focus States

```css
:focus-visible {
  outline: 2px solid var(--focus);
  outline-offset: 2px;
}
```

Night Command Typora focus uses Moon Rift `#C4B5FD` and a lilac glow.

## Classification Badges

```css
.badge-accent {
  color: var(--accent-fg);
  background: var(--accent-bg);
  border: 1px solid color-mix(in srgb, var(--accent-fg) 55%, transparent);
}

.badge-accent[data-accent="cyan"] {
  --accent-fg: var(--accent-cyan);
  --accent-bg: var(--accent-cyan-bg);
}
```

| Label | Accent | Meaning |
|---|---|---|
| `SCOUTING` | Aether Cyan | Scouting, analysis, recommendations |
| `ECONOMY` | Signal Teal | Resource flow, efficiency, build order value |
| `ROUTE` | Tactical Blue | Movement, map pathing, turn sequencing |
| `THREAT` | Rift Rose | Enemy pressure, combat danger, meta pressure |
| `RARE` | Astral Magenta | Rare unit, faction flavor, magic/lore emphasis |

## Guide Callouts

Use accent callouts when the section is informational but not a system alert.

```css
.callout-accent {
  color: var(--text);
  background: var(--accent-bg);
  border-left: 4px solid var(--accent-fg);
}
```

| Callout Type | Accent | Example |
|---|---|---|
| Insight | Aether Cyan | "Scout before committing cavalry." |
| Optimization | Signal Teal | "Delay the upgrade until income stabilizes." |
| Route | Tactical Blue | "Use the north pass to avoid the choke." |
| Pressure | Rift Rose | "This matchup spikes hard at turn 12." |
| Rare/Premium | Astral Magenta | "This faction trait changes the normal build order." |

## Charts And Data Visualization

Use accent colors for chart series only when the series has persistent meaning across screens.

```css
.chart-series-scouting { color: var(--accent-cyan); }
.chart-series-economy  { color: var(--accent-teal); }
.chart-series-route    { color: var(--accent-blue); }
.chart-series-threat   { color: var(--accent-rose); }
.chart-series-rare     { color: var(--accent-magenta); }
```

Rules:

1. Use the same accent for the same concept everywhere.
2. Do not assign accents randomly per chart.
3. Do not use purple for every series. Purple already carries brand and interaction weight.
4. Use `--text` or `--text-muted` for chart labels unless the label itself needs category meaning.
5. Use accent backgrounds for legend chips, not large chart fills.

## Icon Accents

Use accent colors for small icon strokes when icons represent category or content type.

Do not color every icon. Navigation, buttons, and controls should generally inherit `--text-muted`, `--text`, `--link`, or `--button-text`.

---

# Contrast Notes

Approximate contrast ratios for the main readability pairs.

| Pair | Approx. Contrast Ratio | Verdict | Role |
|---|---:|---|---|
| `#17111F` on `#DED2E8` | 12.75:1 | Excellent | Primary text on light page background |
| `#17111F` on `#E9E0F1` | 14.43:1 | Excellent | Primary text on light cards |
| `#554A60` on `#DED2E8` | 5.72:1 | Passes normal text | Muted text on light page background |
| `#7A6D86` on `#DED2E8` | 3.32:1 | Large/UI only | Dim text; avoid critical information |
| `#4B2A7B` on `#DED2E8` | 7.56:1 | Excellent | Brand text on light background |
| `#6D28D9` on `#DED2E8` | 4.90:1 | Passes normal text | Purple text if needed; stronger as button fill |
| `#5B21B6` on `#DED2E8` | 6.20:1 | Passes normal text | Default readable light-mode link text |
| `#92400E` on `#DED2E8` | 4.89:1 | Passes normal text | Accent text on light background |
| `#D6C8EA` on `#100B15` | 12.31:1 | Excellent | Primary text on dark page background |
| `#D6C8EA` on `#17101F` | Strong | Excellent | Primary text on raised Night Command UI |
| `#A99ABF` on `#100B15` | 7.46:1 | Excellent | Muted text on dark background |
| `#A78BFA` on `#100B15` | 7.14:1 | Excellent | Readable dark-mode link text |
| `#7C3AED` on `#100B15` | 3.41:1 | Large/UI only | Button fill; not ideal for small text |
| `#F59E0B` on `#100B15` | 9.05:1 | Excellent | Dark-mode accent |

## Additional Accent Contrast Notes

| Accent | Dark Accent on `#1B1226` | Dark Accent on Accent BG | Light Accent on `#E9E0F1` | Light Accent on Accent BG | Verdict |
|---|---:|---:|---:|---:|---|
| Aether Cyan | 12.48:1 | 10.35:1 | 5.67:1 | 6.49:1 | Strong for labels, badges, small UI text |
| Signal Teal | 12.23:1 | 9.72:1 | 5.92:1 | 6.73:1 | Strong for labels, badges, small UI text |
| Tactical Blue | 7.11:1 | 6.19:1 | 5.23:1 | 5.49:1 | Strong enough for labels and chart text |
| Rift Rose | 6.72:1 | 6.11:1 | 6.26:1 | 6.68:1 | Strong enough for combat/threat labels |
| Astral Magenta | 7.35:1 | 6.47:1 | 6.43:1 | 7.08:1 | Strong enough for rare/premium labels |

---

# Deprecated, Removed, Or Demoted Items

| Item | Previous Role | v2.0 Decision | Reason |
|---|---|---|---|
| Previous condensed sans-serif utility voice | Utility font | Removed completely | User strongly dislikes most sans-serif fonts; current Night Command CSS does not use it |
| Previous utility sans-serif fallback | Utility fallback | Removed completely | No active condensed sans-serif utility role remains |
| Ashen Lilac | Light background or surface candidate | Deprecated for core palette | Too pale and too soft for tactical brand tone |
| Pale Rune | Light surface candidate | Deprecated for core palette | Too close to white; lacks enough brand character |
| Moonlit Lilac `#E7DCF5` | Dark-mode primary text candidate | Demoted to `--text-bright` | Strong contrast but too bright for default long-session reading |
| White `#FFFFFF` | Light-theme default surface candidate | Restricted to `--surface-readable` | Useful for dense reading, too generic as main surface |
| Fenix Violet `#4B2A7B` | General interactive purple candidate | Restricted to identity and brand-heavy states | Too dark for some active UI roles and too valuable as brand color |
| Base-engine vertical list connector lines | List decoration | Disabled in Night Command wrapper | Interferes with the cleaner ten-level bullet system |
| Base blockquote lightbulb | Quote marker | Replaced with monospace `!` | Keeps blockquotes editorial instead of alert-like |
| Base HR rotated square | Section separator | Replaced with `✦` | Stronger Night Command editorial signature |
| Native Typora alert icons | Alert iconography | Hidden in Night Command | Replaced with Markdown/editorial emoji markers |

---

# CSS Token Reference

## Night Command Product Tokens

```css
:root[data-theme="dark"] {
  --bg: #100B15;
  --surface: #1B1226;
  --surface-raised: #27173A;
  --surface-sunken: #0C0911;
  --surface-tint: #21152F;
  --border-subtle: #2E203D;
  --border: #4B3764;

  --text: #D6C8EA;
  --text-bright: #E7DCF5;
  --text-muted: #A99ABF;
  --text-dim: #847490;

  --primary: #4B2A7B;
  --button: #7C3AED;
  --button-hover: #8B5CF6;
  --button-text: #FFFFFF;
  --link: #A78BFA;
  --link-hover: #C4B5FD;
  --focus: #C4B5FD;

  --state-hover-bg: #21152F;
  --state-active-bg: #2B1844;
  --state-selected-bg: #24143A;
  --state-selected-border: #7C3AED;

  --accent: #F59E0B;
  --accent-cyan: #67E8F9;
  --accent-cyan-bg: #0F2A33;
  --accent-teal: #5EEAD4;
  --accent-teal-bg: #0F2F2A;
  --accent-blue: #60A5FA;
  --accent-blue-bg: #10233F;
  --accent-rose: #FB7185;
  --accent-rose-bg: #35151E;
  --accent-magenta: #E879F9;
  --accent-magenta-bg: #32173A;

  --success: #34D399;
  --success-bg: #12281F;
  --warning: #FBBF24;
  --warning-bg: #2B2110;
  --danger: #F87171;
  --danger-bg: #2D151A;
  --info: #A78BFA;
  --info-bg: #211A34;
}
```

## Current Night Command Typora Stack

```css
:root {
  --max-width: 1128px;
  --bg-color: #100B15;
  --text-color: #D6C8EA;
  --text-color-secondary: #A99ABF;
  --primary-color: #A78BFA;
  --secondary-color: #7C3AED;
  --accent-color: #F59E0B;
  --border-color: #4B3764;

  --font-display: "Wak", "Lucy Rose", sans-serif;
  --font-body: "Source Serif 4 Variable", "Source Serif 4", Georgia, serif;
  --font-ui: "MonaspaceArgon", "Monaspace Argon", monospace;
  --font-data: "MonaspaceXenon", "Lotion", monospace;
}
```

## Smoked Command Light Tokens

```css
:root[data-theme="light"] {
  --bg: #DED2E8;
  --surface: #E9E0F1;
  --surface-readable: #FFFFFF;
  --surface-raised: #F3EEF8;
  --surface-tint: #D2C2E2;
  --surface-sunken: #C8B6DB;
  --border-subtle: #CAB8DC;
  --border: #BCA8D0;
  --border-strong: #9F86B8;

  --text: #17111F;
  --text-muted: #554A60;
  --text-dim: #7A6D86;
  --text-inverse: #F5F1FF;

  --primary: #4B2A7B;
  --button: #6D28D9;
  --button-hover: #5B21B6;
  --button-text: #FFFFFF;
  --link: #5B21B6;
  --link-hover: #4B2A7B;
  --focus: #7C3AED;

  --state-hover-bg: #D8C9E6;
  --state-active-bg: #CDB9DF;
  --state-selected-bg: #D2C2E2;
  --state-selected-border: #6D28D9;

  --accent: #92400E;
  --accent-cyan: #155E75;
  --accent-cyan-bg: #CFFAFE;
  --accent-teal: #115E59;
  --accent-teal-bg: #CCFBF1;
  --accent-blue: #1D4ED8;
  --accent-blue-bg: #DBEAFE;
  --accent-rose: #9F1239;
  --accent-rose-bg: #FFE4E6;
  --accent-magenta: #86198F;
  --accent-magenta-bg: #FAE8FF;

  --success: #047857;
  --success-bg: #D1FAE5;
  --warning: #92400E;
  --warning-bg: #FEF3C7;
  --danger: #B91C1C;
  --danger-bg: #FEE2E2;
  --info: #5B21B6;
  --info-bg: #EDE9FE;
}
```

---

# Implementation Checklist

## Night Command

1. Use the current Night Command CSS active stack.
2. Remove the previous condensed sans-serif utility voice and its fallback from all active guidance.
3. Use Source Serif 4 Variable with `font-optical-sizing: auto`.
4. Use Monaspace Argon for navigation, controls, tabs, menus, file tree, compact labels, and Preferences.
5. Use Monaspace Xenon for code, metadata, technical values, and data.
6. Keep Fenix Violet as identity and Rift Lilac as the Typora active/link implementation color.
7. Preserve the UI surface ladder.
8. Preserve the ten-level bullet system.
9. Preserve the H1-H4 Wak and H5-H6 Source Serif 4 document heading split.
10. Preserve document canvas values for Typora, while treating max width as implementation-specific.
11. Preserve the section separator star.
12. Preserve blockquote, task-list, footnote, image, caption, metadata, alert, math, diagram, raw block, and source-view treatments.
13. Preserve export and print rules.
14. Use v2.49 Mermaid label behavior: light text `#FFF4FA` on soft rose `#F0A8C6`.
15. Test long documents, tables, code blocks, alerts, diagrams, print export, and source view.

## Smoked Command

1. Keep the existing v1.5 light-mode tokens until Smoked Command receives a full implementation review.
2. Do not assume Night Command document canvas values apply to Smoked Command.
3. Re-review Smoked Command CSS before adding detailed light-mode bullets, surfaces, app chrome, and typography behavior.
4. Apply the v2.0 typography stack unless Smoked Command CSS proves a different implementation need.

## General Brand System

1. Maintain separation between identity, action, link, hover, focus, selected state, border, semantic status, and content classification.
2. Keep accent colors for classification, not primary interaction.
3. Use Monaspace roles intentionally. Monospace is now a core brand utility, not only code styling.
4. Add abstractions only when they serve repeated implementation needs.
5. Audit contrast whenever a token moves from decorative use into text use.

---

# Handoff Summary For Next Chat

## Current Files

Workspace:

`C:\Users\Pseud\AppData\Roaming\Typora`

Relevant files:

- `themes\night-command.css`
- `themes\night-command\night-command.dark.css`
- `themes\night-command\baptiste_studios_brand_kit_v1.5.md`
- `themes\night-command\night_command_brand_kit_gap_analysis_v1.0.md`
- `themes\night-command\baptiste_studios_brand_kit_v2.0.md`

## Work Completed In This Pass

Created a new standalone Brand Kit:

`themes\night-command\baptiste_studios_brand_kit_v2.0.md`

The v1.5 file was left unchanged as historical reference.

The new v2.0 Brand Kit:

- Removes the previous condensed sans-serif utility voice from the active system.
- Removes its prior fallback from active fallback guidance.
- Replaces the active stack with the current Night Command CSS stack.
- Documents Wak, Source Serif 4, Monaspace Argon, and Monaspace Xenon roles.
- Adds Source Serif 4 variable-file guidance.
- Documents Monaspace Argon Medium 500.
- Adds Night Command implementation tokens.
- Adds the Typora token alias map.
- Adds the UI surface ladder.
- Adds the document canvas, export canvas, and print canvas.
- Adds the heading system.
- Adds the ten-level bullet system.
- Adds code and syntax tokens.
- Adds editorial elements.
- Adds Markdown alert mapping.
- Adds math, diagram, Mermaid, raw block, and metadata treatment.
- Adds table and table resize popover guidance.
- Adds application chrome patterns.
- Adds focus mode.
- Keeps Smoked Command at current v1.5 depth for later review.
- Keeps version history at the bottom before the end marker.

## Important User Requirements

The user explicitly requested:

1. The previous condensed sans-serif utility voice should be removed from the document completely.
2. Max width should be clear as Typora UI/document-canvas implementation, not universal brand layout.
3. Current Night Command CSS should replace the Brand Kit v1.5 active stack.
4. Replacement is Monaspace Argon and Xenon, but not one-to-one across every UI surface.
5. Version bump should be v2.0 because the changes are major.
6. Current CSS should be reviewed again before changes.
7. Font role guidance:
   - Wak: major titles and headings.
   - Source Serif 4: document prose and longer application text such as descriptions, dialogs, notifications, tooltips, and help text.
   - Monaspace Argon: navigation, controls, tabs, menus, file tree, compact labels, and Preferences.
   - Monaspace Xenon: code, metadata, technical values, and data.
8. Font file guidance:
   - Argon uses Regular 400, Medium 500, Bold 700.
   - Xenon uses Regular 400 and Bold 700.
   - Source Serif 4 static weights and italics remain available.
   - Source Serif variable files were added.
   - Use `font-optical-sizing: auto`.
   - Separate `_8pt` files are unnecessary.
9. Create `baptiste_studios_brand_kit_v2.0.md`.
10. Include everything, not only a summary.
11. Smoked Command will be updated later in the same way.
12. Provide a full handoff summary because the user must create a new Project/chat.

## Current Night Command CSS Facts

The latest reviewed wrapper file declares:

`Night Command - Baptiste Studios Dark Theme Version 2.49`

Current CSS stack:

```css
--font-display: "Wak", "Lucy Rose", sans-serif;
--font-body: "Source Serif 4 Variable", "Source Serif 4", Georgia, serif;
--font-ui: "MonaspaceArgon", "Monaspace Argon", monospace;
--font-data: "MonaspaceXenon", "Lotion", monospace;
```

Current important CSS values:

- `--max-width: 1128px`
- `--bg-color: #100B15`
- `--text-color: #D6C8EA`
- `--text-color-secondary: #A99ABF`
- `--primary-color: #A78BFA`
- `--secondary-color: #7C3AED`
- `--accent-color: #F59E0B`
- `--border-color: #4B3764`
- `--ui-surface-raised: #17101F`
- `--ui-surface-overlay: #1D1427`
- `--ui-surface-active: #2D1C40`
- `--ui-accent-soft: #F0A8C6`

Important update since first analysis:

- Mermaid edge labels now use `#FFF4FA` text on `#F0A8C6`, not dark text.
- Export and print behavior were added.
- Alert emoji placement changed to include `::after` plus text-container `::before`.
- Footer word-count hover coverage was expanded.
- Focused code label background changed to `#27173A`.

## Validation Needed In Next Chat

The next chat should:

1. Open `baptiste_studios_brand_kit_v2.0.md`.
2. Check for any remaining references to the retired condensed sans-serif family or its fallback. There should be none by name.
3. Run a tail check and verify the file ends with `<!-- END OF DOCUMENT -->`.
4. Ask the user whether to keep the handoff summary inside the Brand Kit or move it to a separate artifact.
5. When Smoked Command is ready, repeat the Night Command process:
   - Review current Smoked Command CSS.
   - Compare against v2.0 Brand Kit.
   - Create a detailed gap analysis.
   - Update Brand Kit with full implementation-level Smoked Command guidance.

---

# Version History

| Version | Date | Change Summary |
|---|---|---|
| v1.0 | - | Initial brand kit draft |
| v1.1 | - | Color system expanded |
| v1.2 | - | Light mode palette fixed; pale lilacs replaced with Option A Smoked Command direction |
| v1.3 | - | Option A made operational; Night Command dark theme added; button/link tokens separated |
| v1.4 | - | Secondary accent layer added: Aether Cyan, Signal Teal, Tactical Blue, Rift Rose, Astral Magenta |
| v1.5 | 2026-06-14 | Brand renamed to Baptiste Studios; typography stack replaced with Wak, Source Serif 4, a condensed utility voice, and Monaspace Xenon; font evaluations added |
| v2.0 | 2026-06-17 | Major Night Command implementation update; previous condensed utility voice retired; active stack replaced with Wak, Source Serif 4 Variable, Monaspace Argon, and Monaspace Xenon; Night Command CSS v2.49 tokens, typography, lists, code, alerts, document canvas, app chrome, export, and print guidance added |

<!-- END OF DOCUMENT -->

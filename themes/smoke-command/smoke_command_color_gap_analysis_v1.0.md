# Smoke Command Color Gap Analysis v1.0

Version: 1.0
Date: 2026-06-18

## Scope

This analysis compares:

- `K:\Dev\Typora-Themes\themes\smoke-command.css`
- `K:\Dev\Typora-Themes\themes\smoke-command\smoke-command.light.css`
- `K:\Dev\baptiste-studios\assets\brand-kit\baptiste_studios_brand_kit_v2.0.md`

Goal: identify the color gaps between the current copied Smoke Command CSS and the Brand Kit's Option A Smoked Command light-mode system, then define a practical starting concept for the light theme. This document does not propose layout changes.

## Executive Verdict

Smoke Command is currently a renamed Night Command fork, not a light theme implementation.

The wrapper file has the correct Smoke Command identity and imports `smoke-command.light.css`, but its variables and hard-coded rules still use Night Command's dark palette. The base file also contains many dark-theme and Dracula-like inherited colors. The gap is large, but the path is straightforward: preserve the Night Command layout and selector structure, then remap every color role to the Brand Kit's Smoked Command light palette.

Do not start by tweaking individual dark values until they "look lighter." That will create a muddy hybrid. Start with a clean token mapping, then fix hard-coded leftovers section by section.

## Brand Kit Source Direction

The Brand Kit defines Smoked Command as Option A light mode until it receives a full implementation pass. The current light-mode source tokens are:

| Role | Token | Hex | Intended Use |
|---|---|---:|---|
| Page background | `--bg` | `#DED2E8` | Default page background |
| Standard surface | `--surface` | `#E9E0F1` | Cards, guide blocks, article panels |
| Reading surface | `--surface-readable` | `#FFFFFF` | Long guides, forms, dense tables |
| Raised surface | `--surface-raised` | `#F3EEF8` | Popovers, dropdowns, floating cards |
| Tinted surface | `--surface-tint` | `#D2C2E2` | Callouts, selected panels, table headers |
| Sunken surface | `--surface-sunken` | `#C8B6DB` | Filter wells, code blocks, inset panels |
| Subtle border | `--border-subtle` | `#CAB8DC` | Internal dividers and table rows |
| Default border | `--border` | `#BCA8D0` | Cards, fields, default outlines |
| Strong border | `--border-strong` | `#9F86B8` | Selected cards, important containers |
| Primary text | `--text` | `#17111F` | Primary text on light surfaces |
| Muted text | `--text-muted` | `#554A60` | Captions, helper text, metadata |
| Dim text | `--text-dim` | `#7A6D86` | Placeholder and disabled-adjacent text |
| Inverse text | `--text-inverse` | `#F5F1FF` | Text on dark brand blocks and filled buttons |
| Brand identity | `--primary` | `#4B2A7B` | Logo, headings, brand blocks |
| Button | `--button` | `#6D28D9` | Primary action button background |
| Button hover | `--button-hover` | `#5B21B6` | Hover and pressed button state |
| Link | `--link` | `#5B21B6` | Readable inline links |
| Link hover | `--link-hover` | `#4B2A7B` | Link hover and brand-heavy text states |
| Focus | `--focus` | `#7C3AED` | Keyboard focus ring |
| Accent | `--accent` | `#92400E` | Accent text, warning labels, badges |

The Brand Kit also gives light-mode semantic tokens and five light-mode accent families. Those must replace the current dark accent choices in alerts, badges, code-adjacent UI, and classification elements.

## Current CSS Reality

### Wrapper File

`smoke-command.css` is still color-mapped to Night Command. Examples:

| Current Token | Current Value | Problem |
|---|---:|---|
| `--bg-color` | `#100B15` | Dark page background, should become Smoked Lilac or a readable light canvas role |
| `--text-color` | `#D6C8EA` | Light text for dark surfaces, fails as primary text on light surfaces |
| `--text-color-secondary` | `#A99ABF` | Dark-mode muted text, too low-role for light-mode body hierarchy |
| `--primary-color` | `#A78BFA` | Night Command link/active alias; light mode should use Deep Command or Fenix Violet depending on role |
| `--secondary-color` | `#7C3AED` | Dark button token, should map to Command Violet only where button/action behavior exists |
| `--accent-color` | `#F59E0B` | Dark Ember Gold, should become Burnished Ember for light surfaces |
| `--border-color` | `#4B3764` | Dark visible border, too heavy for default light surfaces |
| `--code-block-bg` | `#0C0911` | Dark code surface, conflicts with the Brand Kit's light sunken surface direction |
| `--ui-surface-base` | `#100B15` | Dark app chrome base |
| `--ui-text` | `#D6C8EA` | Light-on-dark UI text |
| `--ui-border` | `#4B3764` | Dark border token |

The wrapper also contains many direct hard-coded dark colors outside the token block, including document canvas backgrounds, code block backgrounds, Mermaid labels, alerts, tables, search, source view, export, and app chrome.

### Base File

`smoke-command.light.css` is not truly a Smoke Command light base yet. It was renamed from the Night Command base and still includes many dark assumptions, including:

- Dark backgrounds such as `#191a21`, `#282a36`, and `#2e2e2e`.
- White text rules such as `#fff` for active UI states.
- Dracula-like syntax colors such as `#ffb86c`, `#d63031`, `#6272a4`, and `#f8f8f2`.
- Many `rgba(255, 255, 255, ...)` overlays intended for dark glass effects.
- Many `rgba(0, 0, 0, ...)` shadows or overlays which may become too heavy on a light lavender system.

The base file can remain as the structural engine, but it should not be trusted as color-correct.

## Primary Gaps

### 1. Product Tokens Are Missing From CSS

The Brand Kit uses product-level tokens such as `--bg`, `--surface`, `--surface-readable`, `--button`, `--link`, and `--focus`. The Typora CSS mainly uses engine aliases such as `--bg-color`, `--primary-color`, and `--text-color`.

Required fix: add the Smoked Command product tokens to `:root`, then map Typora aliases onto them. This keeps the Brand Kit readable and avoids confusing `--primary` with `--primary-color`.

### 2. Typora Alias Map Does Not Exist For Smoke Command

Night Command has a documented alias strategy in the Brand Kit. Smoke Command does not yet.

Starting alias recommendation:

| Typora/Base Token | Proposed Value | Maps To | Reason |
|---|---:|---|---|
| `--bg-color` | `#DED2E8` | `--bg` | Default outer app/page background |
| `--text-color` | `#17111F` | `--text` | Primary readable text |
| `--text-color-secondary` | `#554A60` | `--text-muted` | Captions and lower-priority prose |
| `--primary-color` | `#5B21B6` | `--link` | Typora uses this broadly for links, markers, active indicators; Deep Command is readable on light backgrounds |
| `--secondary-color` | `#6D28D9` | `--button` | Best match for action/active fills |
| `--accent-color` | `#92400E` | `--accent` | Light-mode accent and warning-adjacent emphasis |
| `--border-color` | `#BCA8D0` | `--border` | Default visible border without dark-theme heaviness |
| `--hover-background-color` | `#D8C9E6` | `--state-hover-bg` | General light hover wash |
| `--select-text-bg-color` | `rgba(109, 40, 217, 0.20)` | `--button` alpha | Selection must be visible without overpowering text |
| `--active-file-bg-color` | `#D2C2E2` | `--state-selected-bg` | Sidebar/file selection |
| `--active-file-text-color` | `#17111F` | `--text` | Active file text on selected light background |
| `--active-file-border-color` | `#6D28D9` | `--state-selected-border` | Active indicator |
| `--caret-color` | `#5B21B6` | `--link` | Visible caret on light surfaces |

### 3. Document Canvas Is Still Dark

The current wrapper sets `#write` to a dark card:

- `background-color: #15101C`
- radial gradient using `#1B1425`, `#15101C`, `#120D18`
- `border: 4px solid #4B3764`

For a light theme, the document canvas should probably be the strongest reading surface, not another dark command panel.

Starting concept:

- Outer Typora/app background: `#DED2E8`
- Document canvas: `#FFFFFF` or `#F3EEF8`
- Standard panels/callouts: `#E9E0F1`
- Table headers/callout fills: `#D2C2E2`
- Code blocks/inset wells: `#C8B6DB`, possibly lightened with a readable overlay if code contrast feels cramped
- Main document border: `#BCA8D0` or `#9F86B8` if Typora needs stronger edge definition

### 4. App Chrome Is Still Night Command

The `--ui-*` tokens are entirely dark:

- Surfaces: `#100B15`, `#17101F`, `#1D1427`, `#251833`, `#2D1C40`
- Text: `#E7DCF5`, `#D6C8EA`, `#A99ABF`
- Borders: `#342442`, `#4B3764`, `#A78BFA`

Starting concept:

| UI Token | Proposed Value | Reason |
|---|---:|---|
| `--ui-surface-base` | `#DED2E8` | App background |
| `--ui-surface-raised` | `#E9E0F1` | Sidebar, panels |
| `--ui-surface-overlay` | `#F3EEF8` | Menus, popovers |
| `--ui-surface-hover` | `#D8C9E6` | Hover rows |
| `--ui-surface-active` | `#D2C2E2` | Active or selected rows |
| `--ui-surface-pressed` | `#CDB9DF` | Pressed state |
| `--ui-text-strong` | `#17111F` | Strong UI labels |
| `--ui-text` | `#17111F` | Default UI labels |
| `--ui-text-muted` | `#554A60` | Secondary labels |
| `--ui-text-disabled` | `#7A6D86` | Disabled labels |
| `--ui-border-subtle` | `#CAB8DC` | Dividers |
| `--ui-border` | `#BCA8D0` | Default border |
| `--ui-border-active` | `#6D28D9` | Selected border |
| `--ui-focus-outline` | `#7C3AED` | Focus ring |
| `--ui-accent-soft` | `#92400E` or `#D2C2E2` | Needs visual testing; current pink soft accent does not belong to the light palette |

### 5. Glow System Needs To Be Reinterpreted

Dark-mode glow works because light text sits on dark surfaces. On light surfaces, glow usually becomes fuzzy and cheap. The current glow values use Rift Lilac alpha and should not carry over directly.

Starting concept:

- Replace broad neon glow with sharper outlines, subtle inner shadows, and low-alpha violet washes.
- Use `rgba(109, 40, 217, 0.20)` for selected/active shadows.
- Use `rgba(124, 58, 237, 0.28)` for focus rings.
- Keep text-shadow rare. On light backgrounds, color and underline usually read better than glow.

### 6. Heading System Needs Color Reassignment

Current headings use Night Command values:

- H1 text `#E7DCF5`
- H2/H3 hover and counters use `#C4B5FD`, `#A78BFA`, `#8B5CF6`
- `--h1-underline-color: #C4B5FD`

Starting concept:

- H1: Fenix Violet `#4B2A7B`
- H1 underline: Command Violet `#6D28D9`
- H2: Deep Command `#5B21B6` or Fenix Violet depending on visual weight
- H3-H6 markers: Deep Command `#5B21B6`
- Body-adjacent lower headings: Void Ink `#17111F` with muted decorative markers

### 7. Code And Syntax Colors Are Still Dark-Mode

Current code variables mostly use dark-mode text:

- Code background: `#0C0911`
- Code variable: `#D6C8EA`
- Code keyword: `#C4B5FD`
- Code comment: `#847490`
- Code function: `#67E8F9`

The Brand Kit does not yet define implementation-level light syntax highlighting. It only provides light accent families and says Inset Lilac is for code-like areas.

Starting concept:

| Code Role | Proposed Direction |
|---|---|
| Code block background | `#C8B6DB` or a slightly lighter custom well derived from it |
| Code text/default | `#17111F` |
| Comments | `#7A6D86` |
| Keywords | `#5B21B6` |
| Functions | `#155E75` |
| Params/properties | `#115E59` |
| Strings | `#047857` |
| Numbers/constants | `#9F1239` or `#92400E`, depending on visual test |
| Types/classes | `#1D4ED8` |
| Selected code background | `#D2C2E2` |

This area will need Typora visual review. Code themes often look correct on paper and wrong in the editor.

### 8. Alerts Need Light Semantic Mapping

Current alert colors use dark accent foregrounds:

- Note: `#67E8F9`
- Tip: `#5EEAD4`
- Warning: `#F59E0B`
- Important: `#E879F9`
- Caution: `#FB7185`

Starting concept:

| Alert | Border/Text | Background |
|---|---:|---:|
| Note | `#155E75` | `#CFFAFE` |
| Tip | `#115E59` | `#CCFBF1` |
| Warning | `#92400E` | `#FEF3C7` |
| Important | `#86198F` | `#FAE8FF` |
| Caution | `#B91C1C` or `#9F1239` | `#FEE2E2` or `#FFE4E6` |

Use semantic danger for destructive/system caution. Use Rift Rose for combat/enemy pressure callouts. Do not collapse those meanings unless Typora's alert taxonomy forces it.

### 9. Lists Still Use A Dark Lilac Fade

The ten-level bullet progression currently runs from light lilac to muted violet:

- `#E7DCF5` through `#725A8E`

On a light background, the early levels will be too pale and the later levels may be the only readable ones.

Starting concept:

- Level 1: `#4B2A7B`
- Level 2: `#5B21B6`
- Level 3: `#6D28D9`
- Level 4: `#554A60`
- Level 5: `#7A6D86`
- Levels 6-10: derive progressively from `#9F86B8`, `#BCA8D0`, and darker text tokens, but verify readability.

Do not preserve the exact Night Command bullet gradient. Preserve the idea: a deliberate ten-level hierarchy.

### 10. Mermaid, Diagrams, Math, And Technical Blocks Need A Separate Pass

Night Command has detailed technical block behavior. Smoke Command currently inherits those colors, including soft rose labels and dark diagram containers.

Starting concept:

- Mermaid canvas: `#FFFFFF` or `#F3EEF8`
- Mermaid cluster fills: `#E9E0F1` and `#D2C2E2`
- Mermaid lines: `#9F86B8` or `#554A60`
- Mermaid text: `#17111F`
- Mermaid emphasis labels: Deep Command text on Veil Amethyst or white text on Fenix Violet, depending on legibility

Keep this separate from ordinary prose, because diagrams expose bad contrast quickly.

### 11. Print And Export Colors Need Review

Night Command print/export rules were accepted for a dark theme. Smoke Command should probably print closer to normal light documents:

- White or very pale document canvas.
- Dark text.
- Reduced decorative backgrounds.
- Borders visible but not heavy.
- Code and tables readable in print without relying on saturated fills.

Do not assume the Night Command print palette should survive. Preserve layout rules unless visual testing proves a color requires print-specific handling.

## Hard-Coded Color Cleanup Areas

The wrapper has many direct hard-coded colors beyond `:root`. These should be converted to variables or replaced deliberately.

Highest-risk areas:

1. `#write` document canvas and border.
2. Heading colors and hover effects.
3. Code blocks, raw blocks, source view, and line numbers.
4. Table backgrounds and borders.
5. Alerts and admonitions.
6. Mermaid and diagram labels.
7. Sidebar, file tree, search, menus, popovers, modals, and app chrome.
8. Focus mode dimming.
9. Export and print.

The base file also needs cleanup, but the safer first implementation pass is to override from `smoke-command.css`. Only edit `smoke-command.light.css` when the base engine itself forces an inherited color through specificity or missing wrapper coverage.

## Starting Light Theme Concept

The light version should not feel like a generic white theme. It should feel like a tactical document surface made from smoked lilac, ink, and controlled violet accents.

Recommended first visual model:

- The application background is Smoked Lilac `#DED2E8`.
- The document canvas is white or High Rune `#F3EEF8`, depending on Typora preview. Start with white if long-form readability feels more important; start with High Rune if the theme needs stronger brand atmosphere.
- Standard panels and secondary blocks use Rune Mist `#E9E0F1`.
- Selected rows, callouts, and table headers use Veil Amethyst `#D2C2E2`.
- Code and inset areas use Inset Lilac `#C8B6DB`, but may need a custom lighter code well if syntax contrast suffers.
- Main text is Void Ink `#17111F`.
- Muted text is Grave Plum `#554A60`.
- Links and active editor affordances use Deep Command `#5B21B6`.
- Filled action or selected indicators use Command Violet `#6D28D9`.
- Brand-heavy headings and identity blocks use Fenix Violet `#4B2A7B`.
- Focus rings use Arcane Purple `#7C3AED`.
- Accent/warning-adjacent labels use Burnished Ember `#92400E`.

## Recommended Implementation Order

1. Add product-level Smoke Command tokens to `:root`.
2. Remap Typora/base-engine aliases to those product tokens.
3. Remap `--ui-*` app chrome tokens.
4. Recolor `#write` document canvas, border, and texture.
5. Recolor headings and list hierarchy.
6. Recolor links, selection, caret, active file, hover, and focus states.
7. Recolor tables, blockquotes, marks, inserts, deletes, footnotes, and editorial elements.
8. Recolor code blocks and syntax highlighting.
9. Recolor alerts and semantic/accent callouts.
10. Recolor Mermaid, math, diagrams, raw blocks, and metadata.
11. Recolor app chrome selectors missed by tokens.
12. Review source mode.
13. Review print/export rules.
14. Visual test in Typora and adjust only after seeing real rendering.

## Non-Goals For The First Color Pass

- Do not change layout, spacing, widths, borders sizes, heading structure, or section order.
- Do not remove the Night Command selector architecture unless a selector is provably irrelevant to Smoke Command.
- Do not invent new accent families.
- Do not use Arcane Purple as the default light-mode link color; the Brand Kit says Deep Command owns readable links.
- Do not make the default background near-white lavender. The Brand Kit explicitly rejects that because it weakens the tactical tone.

## Key Open Questions For Visual Review

1. Should the document canvas be pure white `#FFFFFF` or High Rune `#F3EEF8`?
2. Is Inset Lilac `#C8B6DB` too saturated for code blocks in Typora?
3. Should headings lean more brand-heavy with Fenix Violet, or more interactive with Deep Command?
4. How much of Night Command's glow behavior should survive as light-mode outline behavior?
5. Does Typora app chrome need more contrast than the Brand Kit's product surfaces imply?
6. Should Mermaid labels keep a dark brand-block style for contrast, or become light labels matching the rest of the theme?

## Bottom Line

The color conversion should be treated as a structured remap, not a tuning exercise. The Brand Kit gives enough light-mode product colors to start, but Smoke Command still lacks the implementation-level token map Night Command now has. The first CSS pass should create that map inside `smoke-command.css`, override the most visible dark surfaces, then use Typora visual review to catch selector-specific misses.

<!-- END OF DOCUMENT -->

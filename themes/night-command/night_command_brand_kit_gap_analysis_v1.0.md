# Night Command Brand Kit Gap Analysis v1.0

Date: 2026-06-17

Sources reviewed:

- `themes/night-command.css`
- `themes/night-command/night-command.dark.css`
- `themes/night-command/baptiste_studios_brand_kit_v1.5.md`

## Executive Finding

The Brand Kit v1.5 documents the high-level Baptiste Studios color system, typography system, component guidance, and dark/light theme tokens. It does not document most of the implemented Night Command theme behavior.

The implemented Typora theme has moved beyond the kit in four major ways:

1. It defines a larger Night Command token layer using Typora/base-engine variable names, not only the product-oriented `--bg`, `--surface`, `--text`, `--button`, and accent tokens in the kit.
2. It adds a detailed editorial/document rendering system: heading treatments, Unicode bullet hierarchy, task lists, blockquotes, inline emphasis, footnotes, images, metadata blocks, math, diagrams, raw blocks, alerts, and source view.
3. It adds a Typora application UI system: sidebar, outline, file tree, modals, dropdowns, context menus, search, quick open, notifications, spell check, footer controls, table resize popover, and megamenu.
4. It introduces several new colors and role decisions not named or governed in the Brand Kit.

Verdict: update the Night Command portion of the Brand Kit. Do not treat the CSS as a one-off Typora skin anymore. It now contains reusable brand decisions that other themes and apps need.

## What The Brand Kit Already Covers

The Brand Kit already covers these areas well enough:

| Area | Present in Brand Kit | Notes |
|---|---|---|
| Core brand colors | Yes | Fenix Violet, Arcane Purple, Command Violet, Deep Command, Rift Lilac, Moon Rift, Ember Gold, Burnished Ember. |
| Dark theme base/text/interaction/state/semantic tokens | Yes | Good conceptual layer, but current CSS uses different variable names and more granular states. |
| Light theme base/text/interaction/state/semantic tokens | Yes | Not directly relevant to Night Command CSS, but useful as companion system. |
| Accent families | Yes | Aether Cyan, Signal Teal, Tactical Blue, Rift Rose, Astral Magenta. |
| Accent usage rules | Yes | Strong guidance: accents classify content, not interaction. |
| Typography roles | Mostly | Wak, Source Serif 4, Barlow Condensed, Monaspace Xenon are documented. Current CSS also uses Monaspace Argon for UI. |
| Buttons, links, cards, guide articles, tables, navigation, focus, alerts, badges, callouts, charts, icon accents | Partially | Guidance is generic product UI guidance, not the actual Night Command Typora implementation. |

## Top Priority Missing Items

Add these to the Brand Kit first.

### 1. Night Command CSS Token Mapping

The CSS uses Typora/base-engine variables rather than the Brand Kit's product token names.

Current CSS variables include:

| CSS Variable | Value | Brand Kit Status | Recommendation |
|---|---:|---|---|
| `--max-width` | `1128px` | Missing | Add as document layout token. |
| `--bg-color` | `#100B15` | Covered as `--bg` | Map to `--bg`. |
| `--text-color` | `#D6C8EA` | Covered as `--text` | Map to `--text`. |
| `--text-color-secondary` | `#A99ABF` | Covered as `--text-muted` | Map to `--text-muted`. |
| `--primary-color` | `#A78BFA` | Partially covered as `--link` | Document that Typora engine primary maps to Rift Lilac, not Fenix Violet. |
| `--secondary-color` | `#7C3AED` | Covered as `--button` | Map to Arcane Purple. |
| `--accent-color` | `#F59E0B` | Covered as `--accent` | Map to Ember Gold. |
| `--border-color` | `#4B3764` | Covered as `--border` | Map to Warden Violet. |
| `--hover-background-color` | `#A78BFA` | Missing as engine token | Add as Typora hover driver, or replace with `--link`. |
| `--select-text-bg-color` | `rgba(124, 58, 237, 0.35)` | Missing | Add selection token. |
| `--active-file-bg-color` | `rgba(167, 139, 250, 0.12)` | Missing | Add active file/sidebar token. |
| `--active-file-text-color` | `#E7DCF5` | Missing | Add active file/sidebar token. |
| `--active-file-border-color` | `#A78BFA` | Missing | Add active file/sidebar token. |
| `--caret-color` | `#A78BFA` | Missing | Add caret token. |
| `--monospace` | `MonaspaceXenon`, `Lotion`, monospace | Partially covered | Keep as Typora compatibility alias. |

Recommendation: add a "Night Command Implementation Token Map" section. Keep the clean product tokens, but document the Typora alias layer so future themes and apps do not misuse `--primary-color`.

### 2. Application UI Tokens

The CSS adds a dedicated UI surface/state layer not present in the kit.

| Token | Value | Purpose |
|---|---:|---|
| `--ui-surface-base` | `#100B15` | Base UI shell. |
| `--ui-surface-raised` | `#17101F` | Sidebar, modals, raised panels. |
| `--ui-surface-overlay` | `#1D1427` | Popovers, hover overlays, modal bodies. |
| `--ui-surface-hover` | `#251833` | Hover state. |
| `--ui-surface-active` | `#2D1C40` | Active/selected state. |
| `--ui-surface-pressed` | `#1A1124` | Pressed state. |
| `--ui-text-strong` | `#E7DCF5` | Strong UI labels. |
| `--ui-text` | `#D6C8EA` | Default UI text. |
| `--ui-text-muted` | `#A99ABF` | Secondary UI text. |
| `--ui-text-disabled` | `#756A82` | Disabled UI text. |
| `--ui-border-subtle` | `#342442` | Quiet UI borders. |
| `--ui-border` | `#4B3764` | Standard UI borders. |
| `--ui-border-active` | `#A78BFA` | Active UI border. |
| `--ui-focus-outline` | `#C4B5FD` | Focus outline. |
| `--ui-accent-soft` | `#F0A8C6` | Soft rose UI accent. |
| `--ui-glow-hover` | `0 0 8px rgba(167, 139, 250, 0.18)` | Hover glow. |
| `--ui-glow-active` | `0 0 10px rgba(167, 139, 250, 0.24)` | Active glow. |
| `--ui-glow-focus` | `0 0 0 1px #C4B5FD, 0 0 14px rgba(167, 139, 250, 0.42)` | Focus glow. |

Recommendation: add these tokens to Night Command. Some duplicate existing conceptual roles, but they are useful because Typora app chrome needs a denser state ladder than document content.

### 3. Bullet System

The Brand Kit has no bullet/list specification. The CSS adds a ten-level unordered-list marker system.

| Level | Marker | Color | Size |
|---:|---|---:|---:|
| 1 | `★` | `#E7DCF5` | `0.94rem` |
| 2 | `☆` | `#DCCEF0` | `0.92rem` |
| 3 | `✦` | `#D0BFEA` | `0.90rem` |
| 4 | `✧` | `#C4B1E3` | `0.88rem` |
| 5 | `⯍` | `#B8A2D8` | `0.86rem` |
| 6 | `⯏` | `#AB93CC` | `0.84rem` |
| 7 | `⯌` | `#9D84BE` | `0.83rem` |
| 8 | `⯎` | `#8F75AF` | `0.81rem` |
| 9 | `★` | `#80679F` | `0.80rem` |
| 10 | `☆` | `#725A8E` | `0.78rem` |

Implementation details:

- Marker font stack: `"Segoe UI Symbol", "Source Serif 4", Georgia, serif`.
- The base engine's vertical list connector line is disabled in the wrapper CSS.
- Ordered lists still use base engine styles: decimal, lower-alpha, lower-roman.

Recommendation: add this as a reusable "Night Command List System." This is one of the clearest brand-portable decisions in the current CSS.

### 4. Heading System Details

The Brand Kit says Wak owns all headings, but the implemented Night Command theme is more nuanced.

| Heading | Current CSS | Brand Kit Gap |
|---|---|---|
| H1 | Wak ExtraBold `1.8rem`, Moonlit Lilac `#E7DCF5`, centered underline expands on hover. | Needs H1 treatment and underline behavior. |
| H2 | Wak Bold `1.4rem`, Moon Rift `#C4B5FD`, glass/radial hover surface. | Needs H2 glass treatment. |
| H3 | Wak Bold `1.25rem`, Rift Lilac `#A78BFA`, left rule, hover to Moon Rift. | Needs H3 rule/icon behavior. |
| H4 | Wak SemiBold `1.15rem`, Spell Violet `#8B5CF6`, dot decorator from base engine. | Needs H4 decorator rule. |
| H5 | Source Serif 4 18pt Medium `1.1rem`, Dust Wisteria `#A99ABF`. | Conflicts with kit's "Wak for all H1-H6" rule. |
| H6 | Source Serif 4 18pt Medium `1.05rem`, Ash Plum `#847490`. | Conflicts with kit's "Wak for all H1-H6" rule. |

Recommendation: either update the Brand Kit to say "Wak for H1-H4; Source Serif 4 18pt for body-adjacent H5-H6 in long-form/editorial contexts," or change the CSS back to Wak for H5-H6. My recommendation is to update the kit. The CSS choice is better for dense documents.

### 5. Heading Icon Masks

The CSS defines custom SVG mask icons for H3-H6:

- `--h3-icon-shape`
- `--h4-icon-shape`
- `--h5-icon-shape`
- `--h6-icon-shape`

These are not in the Brand Kit. They are part of the base-engine heading marker system, recolored through `--primary-color`.

Recommendation: do not paste raw SVG data into the Brand Kit unless the kit needs exact implementation. Document the concept: H3-H6 may use tactical dot-grid icon masks; color inherits Rift Lilac/primary implementation token.

### 6. Code And Syntax Highlighting

The Brand Kit assigns Monaspace Xenon to code/data, but does not define the current syntax colors.

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

Fenced-code behavior:

- Width: `75%`, minimum `55%`, maximum `900px`.
- Background: `#0C0911`.
- Border: `#4B3764`, focus border `#A78BFA`.
- Code label defaults to `TEXT` when language is missing.
- Fence label uses soft rose text over `#21152F`.

Recommendation: add code syntax tokens. The soft green `#86EFAC`, soft red `#FCA5A5`, and line-number color `#725F82` are missing from the core kit and should be named if retained.

### 7. Document Surface And Layout

The Brand Kit does not document the Typora writing surface.

Current CSS:

- `#write` maximum width: `1128px`.
- Margin: `16px auto 0`.
- Padding: `3rem 2.5rem 6rem`.
- Line height: `1.85`.
- Background: `#15101C` plus radial gradient from `#1B1425` to `#120D18`.
- Border: `4px solid #4B3764`.
- Radius: `18px`.
- Backdrop blur: `8px`.
- Texture: radial dot mask using `#4B2A7B` at `0.04` opacity.

Recommendation: add a "Document Canvas" subsection. These values are not universal app tokens, but they are reusable for guide/document experiences.

### 8. Horizontal Rule / Section Separator

The wrapper changes the base engine's rotated square HR into a centered star glyph.

Current CSS:

- Glyph: `✦` (`U+2726`).
- Color: `#A78BFA`.
- Background patch: `#15101C`.
- Hover animation: continuous spin at `1.8s linear`.
- Hover text shadow: `0 0 8px #A78BFA`.

Recommendation: add "Section Separator" guidance. This is a brand-signature editorial detail.

### 9. Blockquotes

The Brand Kit has callout guidance, but not blockquote treatment.

Current CSS:

- Surface: `#17101F`.
- Border: `1px solid #4B3764`.
- Left border: `4px solid #A78BFA`.
- Radius: `14px`.
- Marker: `!` in Monaspace data font, soft rose `#F0A8C6`.
- Hover surface: `#1D1427`.
- Hover glow: `rgba(167, 139, 250, 0.12)`.

Recommendation: add a separate blockquote style. Do not merge blockquotes with semantic alerts. A quote is editorial emphasis; an alert is status/classification.

### 10. Task Lists

The CSS replaces default task-list styling.

Current CSS:

- Checkbox size: `1.12rem`.
- Unchecked fill: `#17101F`.
- Unchecked border: `#4B3764`.
- Checked fill: `rgba(240, 168, 198, 0.18)`.
- Checked border: `#F0A8C6`.
- Checked glow: `rgba(240, 168, 198, 0.35)`.
- Checked text: `#847490`, opacity `0.82`.

Recommendation: add task-list tokens. The use of soft rose for completion is distinctive, but questionable: completed tasks usually map to success. Keep it only if completion is meant to feel editorial rather than operational.

### 11. Inline Text Treatments

The Brand Kit covers links, but not inline prose styling.

Current CSS:

| Element | Treatment |
|---|---|
| Link | `#A78BFA`; hover `#E7DCF5` with lilac glow; visited `#B9A3E8`. |
| Strong | `#C4B5FD` with subtle lilac glow; hover underline. |
| Emphasis | `#B9A3E8` in wrapper, base engine also applies patterned underline behavior. |
| Mark | `#E7DCF5` over soft rose gradient; hover adds rose/lilac blend. |
| Delete | Text `#847490`; decoration `#725A8E`; hover decoration soft rose. |
| Inline code | `#C4B5FD` over `#21152F`; border `#4B3764`; hover surface `#2D1C40`, border `#A78BFA`. |

Recommendation: add inline text treatment rules. These are content design rules, not just CSS details.

### 12. Footnotes

The Brand Kit does not include footnote styling.

Current CSS:

- Footnote text: `#A99ABF`.
- Footnote references: soft rose text, Monaspace data font, `#21152F` fill, `#4B3764` border, `5px` radius.
- Hover: `#F6C2D8`, soft rose border and glow.
- Footnote section top border: `#4B3764`, margin top `3.5rem`.

Recommendation: add footnotes to the document component system.

### 13. Images And Captions

The Brand Kit does not define image treatment.

Current CSS:

- Image border: `2px solid #4B3764`.
- Radius: `14px`.
- Background: `#17101F`.
- Shadow: black elevation plus inner highlight.
- Hover: brightness/contrast lift, scale `1.01`, lilac glow.
- Caption: `#A99ABF`, `0.9rem`; hover color `#C4B5FD`.

Recommendation: add media treatment. This should be shared across guide pages and apps.

### 14. Alerts

The Brand Kit has generic semantic alerts. The CSS implements Typora/GitHub-style alert classes using accent/category colors and emojis.

Current mappings:

| Alert Class | Border/Text Color | Emoji |
|---|---:|---|
| Note | `#67E8F9` | Pushpin |
| Tip | `#5EEAD4` | Light bulb |
| Warning | `#F59E0B` | Warning sign |
| Important | `#E879F9` | Target |
| Caution | `#FB7185` | Stop sign |

Shared alert style:

- Surface: `#17101F`.
- Border: `#4B3764` plus `4px` colored left border.
- Radius: `14px`.
- Hover surface: `#1D1427`.
- Default Typora/octicon alert icons are hidden.

Recommendation: add an alert mapping table. Also decide whether emojis are part of the brand. They are practical in Typora, but may be wrong for polished apps. If the brand kit is cross-app, specify "emoji markers allowed in Markdown/editorial contexts only; product UI should use icon components."

### 15. Math, Diagrams, Raw Blocks, And Metadata Blocks

The Brand Kit does not include technical-document blocks.

Current CSS:

- Math, diagrams, HTML blocks, raw blocks: `#17101F` surface, `#4B3764` border, `12px` radius.
- Focus state: `#1D1427` surface, `#A78BFA` border, lilac glow.
- Raw/code editing surface: `#100B15`.
- Diagram errors: `#FCA5A5` text, `#35151E` background, `#FB7185` border.
- Mermaid edge labels: dark text `#100B15` on soft rose `#F0A8C6`, border `#F6C2D8`.
- Metadata blocks: dashed `#4B3764` border, `#17101F` fill; hover `#1D1427` and `#A78BFA`.

Recommendation: add "Technical Document Blocks" to the Night Command kit. Strategy apps and guides often need diagrams, code, metadata, and formulas.

### 16. Typora Application Chrome

The CSS contains a large app-chrome layer missing from the Brand Kit.

Covered components:

- Sidebar and outline.
- File library search input.
- Context menus.
- Dropdown menus.
- Modal content and modal body.
- Popovers and tooltips.
- Search panel.
- Quick open.
- Notifications.
- Spell-check panel.
- Footer buttons.
- Source-view toggle.
- Table resize popover.
- Megamenu and theme preview grid.

Recommendation: do not put every Typora selector in the Brand Kit. Add an "Application Chrome Tokens and Patterns" section instead:

- Shell background: Black Plum.
- Raised chrome: `#17101F`.
- Overlay chrome: `#1D1427`.
- Interactive control fill: `#21152F`.
- Hover/active fill: `#2D1C40`.
- Default border: `#4B3764`.
- Active border: `#A78BFA`.
- Focus outline: `#C4B5FD`.
- Soft rose active utility accent: `#F0A8C6`, hover `#F6C2D8`.

### 17. Typography Differences

Brand Kit v1.5 active stack:

```css
--display-font:   "Wak", "Lucy Rose", sans-serif;
--body-font:      "Source Serif 4", Georgia, serif;
--condensed-font: "Barlow Condensed", "Titillium Web", sans-serif;
--mono-font:      "MonaspaceXenon", "Lotion", monospace;
```

Current Night Command CSS:

```css
--font-display: "Wak", "Lucy Rose", sans-serif;
--font-body: "Source Serif 4 Variable", "Source Serif 4", Georgia, serif;
--font-ui: "MonaspaceArgon", "Monaspace Argon", monospace;
--font-data: "MonaspaceXenon", "Lotion", monospace;
```

Differences:

1. The CSS adds Source Serif 4 Variable as the preferred body face.
2. The CSS uses Monaspace Argon for UI chrome, not Barlow Condensed.
3. The CSS uses Source Serif 4 18pt for H5-H6, contradicting the kit's current "Wak for all headers H1-H6" rule.
4. The CSS does not implement Barlow Condensed in the current Typora theme.

Recommendation: update the kit with a context split:

- Product/web UI utility labels: Barlow Condensed.
- Typora/editor chrome utility labels: Monaspace Argon.
- Data/code: Monaspace Xenon.
- Editorial long-form H5-H6: Source Serif 4 18pt allowed.

If that split feels too complex, remove Monaspace Argon from CSS and use Barlow Condensed. My recommendation is to keep Monaspace Argon for Typora chrome because it fits the command-console feel, but document it as an environment-specific utility voice.

## Changed From The Base Engine

The wrapper `night-command.css` imports `night-command.dark.css` and overrides it. These are meaningful changes from the base engine:

| Area | Base Engine | Current Wrapper |
|---|---|---|
| Theme version | Base engine only | Wrapper declares Night Command v2.40. |
| Fonts | Source Serif 4 body, base monospace assumptions | Adds Wak, Source Serif 4 full cuts/variable/18pt, Monaspace Xenon, Monaspace Argon, Lotion. |
| Writing canvas | Simple `15px` padding, `line-height: 2.25`, letter spacing `1.1px` | Branded panel with gradient, 4px border, 18px radius, 1128px max width, `line-height: 1.85`. |
| Paragraph style | Source Serif 4, secondary text, word spacing | Variable Source Serif 4, no extra word spacing. |
| Headings | All headings generic text color plus base hover effects | Wak H1-H4, Source Serif 4 18pt H5-H6, explicit colors per level. |
| H3-H6 masks | Base mask sizes and behavior | H3 mask customized; variables retained. |
| HR | Base rotated square/line treatment | Centered `✦`, spin on hover. |
| Tables | Base full/dense table behavior | Tables auto-size to content, centered, dark surfaces. |
| Code fonts | Base code/font assumptions | Monaspace Xenon and Night Command syntax palette. |
| Lists | Disc/circle/square plus vertical connector line | Ten-level Unicode marker system; connector lines disabled. |
| Task lists | Circular checkbox using old red glow references | Soft rose checked state, tighter sizing, no list marker. |
| Blockquotes | Emoji lightbulb marker and scale hover | Monospace `!` marker, purple left border, no scale transform. |
| Links | Base link icon and strong glow | Simpler lilac link states. |
| Alerts | Base alert icons and pseudo-elements | Typora icons hidden; emoji markers added; accent-based borders/text. |
| App chrome | Base dark chrome with several generic colors | Baptiste-specific UI tokens, rose/lilac active controls, extensive panel styling. |
| Source view | Base source view | Explicit Monaspace Xenon, Night Command colors. |
| Math/diagrams/raw blocks | Base or partial styling | Full Night Command block style and focus states. |
| Focus mode | Not central in kit | Non-focused content dims to Warden Violet at 50% opacity. |

## Added Since Brand Kit v1.5

These are implemented in CSS but missing from the Brand Kit:

1. Typora implementation token aliases.
2. UI surface/state tokens.
3. Glow token scale.
4. Selection, caret, and active-file tokens.
5. Document canvas sizing, border, gradient, blur, and texture.
6. Heading-level colors, hover effects, H1 underline, H2 glass, H3 rule, H4-H6 decorators.
7. H3-H6 SVG mask concept.
8. Ten-level Unicode bullet system.
9. Task-list checkbox system.
10. Section separator star glyph and hover spin.
11. Blockquote treatment.
12. Inline emphasis, strong, mark, delete, visited-link, and inline-code rules.
13. Code-block layout, labels, syntax palette, and line-number behavior.
14. Footnote style.
15. Image/caption style.
16. Metadata block style.
17. Source-view style.
18. Search/quick-open/modal/popover/dropdown/context-menu styling.
19. Sidebar/outline/file library styling.
20. Table resize popover styling.
21. Alert emoji mapping.
22. Math/diagram/raw-block style.
23. Mermaid edge-label treatment.
24. Focus-mode dimming behavior.
25. Monaspace Argon as Typora UI font.
26. Source Serif 4 Variable and Source Serif 4 18pt usage.
27. New colors not named in the kit.

## Changed Compared With Brand Kit v1.5

| Brand Kit v1.5 Says | CSS Does | Recommendation |
|---|---|---|
| `--primary` is Fenix Violet `#4B2A7B`, identity only. | Typora `--primary-color` is Rift Lilac `#A78BFA`. | Keep both. Document `--primary-color` as Typora engine alias, not brand primary. |
| `--surface` is Night Violet `#1B1226`. | Main UI raised surface often uses `#17101F`; document canvas uses `#15101C`; overlay uses `#1D1427`. | Add expanded surface ladder. |
| `--surface-raised` is `#27173A`. | CSS uses `#27173A` only in places, but more often `#17101F`, `#1D1427`, `#21152F`, `#2D1C40`. | Update dark palette with implementation surfaces. |
| `--border-subtle` is `#2E203D`. | CSS uses `#342442` for UI subtle border. | Add `--ui-border-subtle`; do not replace brand token unless desired. |
| H1-H6 use Wak. | H5-H6 use Source Serif 4 18pt. | Change kit or CSS. Recommend changing kit. |
| Utility font is Barlow Condensed. | Typora UI uses Monaspace Argon. | Add environment-specific utility font rule. |
| Semantic success is `#34D399`; danger is `#F87171`. | Alerts use accent/category colors; code uses `#86EFAC` and `#FCA5A5`. | Keep semantic tokens, but add syntax/document accents. |
| Alerts and badges use semantic tokens. | Typora alerts use note/tip/warning/important/caution classes with emojis. | Add Markdown alert mapping; keep product semantic alerts separate. |
| Tables are generically styled. | Typora tables auto-size, center, use dark surfaces. | Add document-table treatment. |
| Links are generic. | Links have visited color `#B9A3E8`, hover glow, optional base-engine link icon behavior. | Add visited-link token and clarify icon policy. |

## Removed Or Disabled

No Brand Kit rule appears to have been intentionally removed. The CSS does disable or supersede several base-engine behaviors:

1. Base vertical list connector lines are disabled.
2. Base unordered markers `disc`, `circle`, and `square` are replaced by Unicode markers.
3. Base blockquote lightbulb icon is replaced with a monospace `!`.
4. Base HR square decoration is replaced with `✦`.
5. Base alert icons/octicons are hidden and replaced with emoji markers.
6. Base image/link/table/code colors are overridden to the Baptiste Night Command palette.
7. Base scale/transform effects are removed in several places to reduce motion.
8. Base red glow references are mostly overwritten in the wrapper, but some old red-ish values remain conceptually in syntax colors and should be named or replaced.

## New Or Unnamed Colors Found In CSS

These values are used but not named in the Brand Kit. Some should become formal tokens; some should be folded into existing tokens.

| Hex / Color | Current Use | Recommendation |
|---|---|---|
| `#15101C` | Main document canvas fill and HR glyph background. | Name as "Command Canvas" or map to document surface. |
| `#1B1425` | Document canvas gradient top. | Name only if gradient is part of brand system. |
| `#120D18` | Document canvas gradient bottom. | Name only if gradient is part of brand system. |
| `#17101F` | Raised UI/document surface. | Add as `--ui-surface-raised`. |
| `#1D1427` | Overlay/hover surface. | Add as `--ui-surface-overlay`. |
| `#251833` | UI hover surface. | Add as `--ui-surface-hover`. |
| `#2D1C40` | UI active surface. | Add as `--ui-surface-active`. |
| `#1A1124` | UI pressed surface. | Add as `--ui-surface-pressed`. |
| `#342442` | UI subtle border. | Add as `--ui-border-subtle`. |
| `#756A82` | Disabled UI text. | Add as `--ui-text-disabled`. |
| `#F0A8C6` | Soft rose UI accent, search hits, footnotes, task checks, Mermaid labels. | Add as "Rift Rose Soft" or "Command Rose." |
| `#F6C2D8` | Soft rose hover/light text. | Add as soft rose hover token. |
| `#B9A3E8` | Visited links/emphasis. | Add as visited/emphasis token or replace with existing muted lilac. |
| `#725A8E` | Deep bullet and delete decoration; line numbers close to this family. | Add as deep lilac utility token if reused. |
| `#725F82` | Code line numbers. | Add as code-line-number token. |
| `#80679F`, `#8F75AF`, `#9D84BE`, `#AB93CC`, `#B8A2D8`, `#C4B1E3`, `#D0BFEA`, `#DCCEF0` | Bullet progression. | Add as bullet-only scale, not general palette. |
| `#86EFAC` | Code strings. | Add code-string token; do not make general success. |
| `#FCA5A5` | Code numbers and diagram errors. | Add code-number/error-soft token; do not make general danger. |
| `#24143A` | Code selected bg and selected state. | Already close to selected state; document as code/document selection bg. |
| `#21152F` | Nested panels, inline code, controls. | Already `--surface-tint`; document more broadly. |
| `#0C0911` | Code blocks/source wells. | Already `--surface-sunken`; keep. |

## Recommended Brand Kit Additions

Add these sections to the Night Command portion of the Brand Kit:

1. **Night Command Implementation Token Map**
   - Explain product tokens vs Typora/base-engine aliases.
   - State explicitly that Typora `--primary-color` maps to Rift Lilac, not Fenix Violet.

2. **Night Command UI Surface Ladder**
   - Add base, raised, overlay, hover, active, pressed, subtle border, active border, disabled text, focus/glow tokens.

3. **Night Command Document Canvas**
   - Include max width, padding, border, radius, gradient, texture, line height, and backdrop blur.

4. **Night Command Heading System**
   - Define H1-H6 styles and interactive behaviors.
   - Decide and document the H5-H6 Source Serif 4 exception.

5. **Night Command List System**
   - Add the ten-level bullet marker/color/size table.
   - State that ordered lists remain decimal/lower-alpha/lower-roman.
   - State that list connector lines are not part of the current brand style.

6. **Night Command Editorial Elements**
   - Blockquotes, HR/section separator, strong/em/mark/del, footnotes, images, captions, metadata blocks.

7. **Night Command Code And Technical Blocks**
   - Syntax tokens, inline code, fenced code, source view, math, diagrams, raw blocks, Mermaid labels.

8. **Night Command Markdown Alerts**
   - Note/tip/warning/important/caution color mapping.
   - Decide emoji policy for Markdown contexts vs product UI contexts.

9. **Night Command Application Chrome**
   - Sidebar, outline, popovers, modals, dropdowns, search, quick open, notifications, spell check, table resize popover.
   - Keep this as patterns and tokens, not raw Typora selectors.

10. **Environment-Specific Typography**
    - Keep the core brand stack.
    - Add Typora-specific aliases:

```css
--font-display: "Wak", "Lucy Rose", sans-serif;
--font-body: "Source Serif 4 Variable", "Source Serif 4", Georgia, serif;
--font-ui: "MonaspaceArgon", "Monaspace Argon", monospace;
--font-data: "MonaspaceXenon", "Lotion", monospace;
```

## Recommended Version Bump

This should be a minor version bump from v1.5 to v1.6 if the Brand Kit keeps the same structure and adds the missing Night Command documentation.

Use a major version only if you also change the core typography rule from "Wak for all H1-H6" to a broader editorial hierarchy across the whole brand, not just Typora.

My recommendation: ship Brand Kit v1.6 with the Night Command additions and explicitly record one changed rule:

> In long-form/editorial document contexts, H5-H6 may use Source Serif 4 18pt Medium instead of Wak to keep lower-level headings body-adjacent and readable.

## Recommended Immediate Updates To Brand Kit

Minimum high-value update:

1. Add the bullet system table.
2. Add the UI surface ladder.
3. Add the code syntax token table.
4. Add document canvas rules.
5. Add the alert mapping table.
6. Add the H5-H6 typography exception or change the CSS.
7. Add the new soft rose tokens:
   - `--ui-accent-soft: #F0A8C6`
   - `--ui-accent-soft-hover: #F6C2D8`
8. Add Typora alias token mapping.

Full update:

Add all sections listed under "Recommended Brand Kit Additions."

## Final Recommendation

Update the Brand Kit. The CSS contains reusable brand decisions, not merely implementation noise.

Do not copy every selector into the Brand Kit. The kit should absorb the reusable decisions:

- token aliases,
- surface/state ladder,
- typography exceptions,
- list markers,
- syntax colors,
- alert mappings,
- document component treatments,
- app chrome patterns.

The strongest immediate candidate for cross-theme reuse is the ten-level bullet system. The second strongest is the UI surface ladder, because it explains how Night Command actually behaves across editor chrome, documents, modals, search, and code.

<!-- END OF DOCUMENT -->

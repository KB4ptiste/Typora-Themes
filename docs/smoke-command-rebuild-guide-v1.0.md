# Smoke Command Rebuild Guide

Version: 1.0

Date: 2026-06-18

## Purpose

This document records the Smoke Command implementation decisions needed to rebuild `themes/smoke-command.css` if the file is lost or corrupted.

It also captures the fixes and patterns likely worth reviewing in Night Command after Smoke Command is complete.

## Source Files

- Active wrapper: `themes/smoke-command.css`
- Base engine: `themes/smoke-command/smoke-command.light.css`
- Smoke test: `docs/smoke-command-visual-smoke-test.md`
- Session notes: `docs/smoke-command-session-notes-v1.0.md`
- Brand kit source: `K:\Dev\baptiste-studios\assets\brand-kit\baptiste_studios_brand_kit_v2.0.md`

## Current Version

- Current Smoke Command wrapper version: `2.43`
- Current Smoke visual smoke test version: `1.0`
- Current session notes version: `1.2`

## Core Architecture

Smoke Command is implemented as a wrapper over the copied Night Command base engine.

The wrapper imports the base file:

```css
@import url("./smoke-command/smoke-command.light.css");
```

Do not edit `smoke-command.light.css` unless a behavior cannot be fixed from the wrapper. Keep Smoke-specific color and style decisions in `smoke-command.css`.

## Primary Surface Colors

Use these current working values:

| Role | Value | Notes |
|---|---:|---|
| Main app background | `#BCA8D0` | Custom Worn Amethyst working color |
| Editor/readable surface | `#D2C2E2` | Veil Amethyst |
| Raised/deeper light panel | `#D8C9E6` | Used for tables, blockquotes, raw SVG panels |
| Node/contained panel fill | `#C8B6DB` | Used for math and Mermaid nodes |
| Standard prose | `#773CC0` | User-approved regular paragraph text |
| Strong text / hover dark | `#4B2A7B` | Used for bold hover, link hover, headings |
| Link/bold active purple | `#6D28D9` | Used for links, bold, icons |
| Heading purple | `#5B21B6` | Used for H2-H6 heading base color |
| Border strong | `#9F86B8` | Used for table cells and panels |
| Border darker | `#7A5F96` | Used for Mermaid, math, hover borders |
| Pink accent | `#E879F9` | Used for Mermaid yes/no and selected accents |
| Yellow accent | `#FACC15` | Used for tip and mark highlight |

## Background And Document Frame

Smoke Command removed the Night Command editor-center radial gradient. The light theme looked uneven with a center glow.

The current document background behavior:

- App background uses `#BCA8D0`.
- Editor surface uses `#D2C2E2`.
- Texture/dot mask remains subtle.
- No radial center-light gradient on `#write`.

Night Command follow-up: review whether its editor gradient should remain.

## Typography

Current heading typography:

| Heading | Font | Weight | Size | Base Color | Hover Color |
|---|---|---:|---:|---:|---:|
| H1 | Wak | 900 | 34px | `#4B2A7B` | unchanged |
| H2 | Wak | 800 | 30px | `#5B21B6` | unchanged |
| H3 | Wak | 700 | 26px | `#5B21B6` | `#6D28D9` |
| H4 | Wak | 700 | 24px | `#5B21B6` | `#6D28D9` |
| H5 | Wak | 500 | 22px | `#5B21B6` | `#6D28D9` |
| H6 | Wak | 500 | 20px | `#5B21B6` | `#6D28D9` |

Heading hierarchy now relies more on font, weight, and size than different colors. This should be reviewed for Night Command.

## Heading Editing Fixes

Smoke originally removed H3-H6 trailing marker pseudo-elements with `content: none; display: none;`. That caused Typora heading editing and TOC/Outline behavior problems.

Keep the marker element structurally present but invisible:

```css
#write h3.md-heading::after,
#write h4.md-heading::after,
#write h5.md-heading::after,
#write h6.md-heading::after {
  content: " ";
  display: inline-block;
  width: 0;
  height: 0;
  opacity: 0;
  overflow: hidden;
  pointer-events: none;
}
```

This fixed H3/H6 and helped the TOC/Outline hierarchy.

H4/H5 needed additional work because the base theme used `display: flex`. Smoke normalized H4/H5 to block headings while preserving hover indicator animation.

H3-H6 should share the same text-start column:

```css
#write h3,
#write h4,
#write h5,
#write h6 {
  position: relative;
  padding-left: 1.45em;
}
```

Night Command follow-up: review H3-H6 indicator alignment and decide whether to preserve or normalize the lower-heading marker behavior.

## TOC

The `[TOC]` indentation worked after the heading marker fix. Keep the inherited TOC indentation unless a visual issue reappears.

Smoke overrides the visible title:

```css
#write .md-toc::before {
  content: "Table of Contents";
}
```

The original base title is `Contents`.

## Horizontal Rule

The horizontal-rule star marker should use the editor background so it does not show a visible rectangle.

Current accepted behavior:

- Rule line stays subtle.
- Center `✦` remains.
- Marker background matches `--surface-readable`.
- Hover spin remains.

## Lists And Task Lists

Unordered list bullets were accepted visually.

Task list unchecked checkboxes were lightened:

- Unchecked boxes should not be black.
- Checked boxes keep the accepted accent styling.

## Blockquotes And Callouts

Blockquotes and callouts were moved from dark Night panels to light Smoke panels.

Current accepted values:

- Non-hover box background: `#D8C9E6`
- Hover background: nearby darker/light purple tone
- Blockquote non-hover quote mark: purple
- Blockquote hover quote mark: pink `#E879F9`
- Tip callout accent: yellow `#FACC15`, not teal

Quote alignment was adjusted so the quote mark sits slightly higher.

## Tables

Current accepted table direction:

- Body background: `#D8C9E6`
- Header background: `#D2C2E2`
- Cell hover: `#C8B6DB`
- Outer border: `2px solid #9F86B8`
- Cell borders: `1px solid #9F86B8`
- Hover text uses white with a black shadow; user liked this effect and may want to reuse it.

Keep the table centered and avoid full-width stretching.

## Code Blocks

Code blocks intentionally remain dark because they read as technical surfaces.

Current accepted values:

- Code body: `#21152F`
- Code header: `#2D1C40`
- Language label: `#E879F9`
- Focused language label: `#FACC15`

Important syntax colors:

- Keyword: `#A78BFA`
- Text/default: `#D6C8EA`
- Function: `#67E8F9`
- Parameter: `#C4B5FD`
- String: `#86EFAC`
- Comment: `#8C73A5`
- Type: `#93C5FD`
- Property: `#5EEAD4`
- Number: `#F9A8D4`
- Meta: `#FACC15`

These colors were restored because the prior softened code block lost readability.

## Math

Math was moved from a dark code-like panel to a light panel similar to Mermaid.

Current accepted values:

- Background: `#C8B6DB`
- Text/equation: `#4B2A7B`
- Border: `#7A5F96`
- Shadow: subtle purple shadow

The edit-mode raw math block still has a Typora raw-block handle in the upper-right corner. Leave it unless it becomes disruptive.

Night Command follow-up: review math layout and decide whether math blocks should be narrower or full-width.

## Mermaid

Mermaid was moved to a light diagram panel.

Current accepted values:

- Panel background: `#D8C9E6`
- Node fill: `#C8B6DB`
- Node border/lines/arrows: `#7A5F96`
- Node text: `#4B2A7B`
- Node shadow: subtle purple drop shadow
- Edge labels `Yes` and `No`: `#E879F9`

The pink `Yes` and `No` labels were accepted.

## Images And Raw SVG

The smoke-test image is inline SVG, so Typora treats it as raw HTML, not a normal Markdown image.

Important rule: scope raw SVG panel styling to blocks containing SVG. Do not apply the same panel to all raw HTML blocks, because it breaks `<details>`.

Current pattern:

```css
#write .md-htmlblock-container:has(svg),
#write .md-rawblock-container:has(svg),
#write .md-rawblock:has(svg) {
  background-color: #D8C9E6;
  border: 2px solid transparent;
  border-radius: 12px;
  padding: clamp(1rem, 2vw, 1.75rem);
  box-shadow: 0 8px 18px rgba(75, 42, 123, 0.16);
}
```

Center SVG content:

```css
#write .md-htmlblock-container svg,
#write .md-rawblock-container svg {
  display: block;
  margin: 0 auto;
}
```

The current double-panel visual effect was accepted after review.

## HTML Elements

Current accepted direction:

- Keyboard buttons use a light purple button style instead of dark Night styling.
- Highlighted text uses darker purple text and yellow highlight.
- Details/summary uses a light panel without the large raw SVG treatment.
- The visible `</details>` closing tag is Typora edit-mode behavior. Do not hide unless the user specifically wants it hidden.

## Footnotes

Footnotes were moved from dark Night styling to light Smoke styling.

Current accepted direction:

- Inline reference background: `#D8C9E6`
- Inline reference text: `#4B2A7B`
- Inline reference border: `#9F86B8`
- Hover background: `#D2C2E2`
- Hover text: `#3A1D5C`
- Footnote body text: `#773CC0`
- Definition name: `#6D28D9`
- Divider line: `#9F86B8`

The smoke test label was updated from `night-command-footnote` to `smoke-command-footnote`.

## Validation Checklist

After rebuilding or changing the file:

1. Confirm CSS version header is updated.
2. Confirm the file ends with:

```css
/* <!-- END OF DOCUMENT --> */
```

3. Check CSS brace balance.
4. Run `git diff --check`.
5. Review in Typora after GoodSync syncs the file.
6. Use Conventional Commit type `style` for CSS-only visual changes.
7. Use `docs` for smoke-test or notes document changes.

## Night Command Follow-Up List

Review these after Smoke Command is complete:

1. Heading hierarchy: consider letting font, size, and weight carry more of the hierarchy instead of varied colors.
2. H3-H6 left-indicator alignment: make lower heading text start at the same distance from the left edge.
3. Gradient background: decide whether the Night Command center-light gradient should remain.
4. Math layout: decide whether math blocks should stay full-width or use a narrower contained width.
5. Table hover white-text shadow: consider whether the effect should be reused.

<!-- END OF DOCUMENT -->

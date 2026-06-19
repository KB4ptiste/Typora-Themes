# Smoke Command Session Notes v1.0

Version: 1.3

Date: 2026-06-18

## Purpose

Capture the working notes from the Smoke Command color pass and the future review items that could not be saved directly to Codex memory during the session.

## Current Smoke Command State

- Smoke Command is being tuned as a light Typora theme while preserving the Night Command layout and section structure.
- Current active theme wrapper: `themes/smoke-command.css`.
- Current base import: `themes/smoke-command/smoke-command.light.css`.
- Current wrapper version at the time of this note: `v2.55`.
- Color-only Smoke Command CSS/theme changes use Conventional Commit type `style`.

## Confirmed Visual Decisions

- Main app background: `#BCA8D0`.
- Editor background: `#D2C2E2`.
- Regular visible paragraph text: `#773CC0`.
- Bold non-hover: `#6D28D9`.
- Bold hover: `#4B2A7B`.
- Link and rotating link icon non-hover: `#6D28D9`.
- Link and rotating link icon hover: `#4B2A7B`.
- The editor center-light radial gradient was removed from Smoke Command because it made the light theme look uneven.
- Horizontal rule marker rectangle background was changed to match the editor background.
- Unordered list bullets were updated and visually accepted.
- Unchecked task checkboxes were lightened from the inherited dark fill.

## Heading Decisions

Current Smoke Command heading direction:

| Heading | Font | Weight | Size | Non-hover Color | Hover Color |
|---|---|---:|---:|---|---|
| H1 | Wak | 900 | 34px | `#4B2A7B` | No current change |
| H2 | Wak | 800 | 30px | `#5B21B6` | No current change |
| H3 | Wak | 700 | 26px | `#5B21B6` | `#6D28D9` |
| H4 | Wak | 700 | 24px | `#5B21B6` | `#6D28D9` |
| H5 | Wak | 500 | 22px | `#5B21B6` | `#6D28D9` |
| H6 | Wak | 500 | 20px | `#5B21B6` | `#6D28D9` |

Trailing dot indicators were removed from H3-H6 because alignment was difficult and visually fragile. Left-side heading indicators remain.

H3-H6 heading text should share the same starting distance from the left edge even though each level uses a different left-side indicator.

## Future Review Notes

### Night Command Heading Review

After Smoke Command is complete, review the Night Command heading system. The Smoke Command approach may be better: let font, weight, and size carry the hierarchy instead of relying heavily on different heading colors.

Also review H3-H6 left-indicator alignment in Night Command. Lower heading text should start at the same distance from the left edge even when each heading level uses a different visual indicator.

### Night Command Gradient Review

After Smoke Command is complete, review whether to remove the gradient background in Night Command. Smoke Command removed the editor gradient because the center-light effect worked on the dark Night Command screen but did not work well for the lighter Smoke Command theme.

### Math Block Layout Review

After Smoke Command is complete, review math block layout in both Smoke Command and Night Command. Smoke Command moved block math away from the dark code-like panel and toward a light contained panel using the same general design language as Mermaid. Review whether Night Command should keep its current math treatment or adopt the improved layout handling, especially for edit/open state borders and the upper-right raw-block handle.

### Night Command TOC Review

Review Night Command's inline `[TOC]` treatment after Smoke Command is complete. Smoke Command fixed the hierarchy/indent behavior by preserving hidden heading marker structure, and changed the visible title to `Table of Contents`. Confirm whether Night Command should use the same visible title and whether its nested TOC indentation remains correct after any heading changes.

### Night Command Source And Raw Block Review

Review Night Command source-mode, raw HTML, raw SVG, and code-language edit controls after Smoke Command is complete. Smoke Command exposed several Typora-specific raw-block states where broad selectors affected unrelated HTML such as `<details>`. Keep future Night Command fixes tightly scoped to the raw block type being changed.

### Night Command Export Review

Review Night Command HTML and PDF export behavior after Smoke Command is complete. Smoke Command required export-specific attention for outline/sidebar appearance, PDF callout text colors, SVG/image containment, math readability, Mermaid readability, tables, and code blocks.

### Night Command Sidebar And Controls Review

Review Night Command sidebar, File/Outline tabs, status bar controls, and Preferences UI after Smoke Command is complete. Smoke Command moved File/Outline active lines to the bottom and preserved dimmed inactive-tab treatment. Confirm whether Night Command should keep its current behavior or align with the final Smoke Command control patterns.

## Communication Notes

- When the user says "text color," "regular text," or "foreground," interpret that as the visible normal paragraph/sentence text in the editor.
- For visual theme tuning, change one visible item at a time when possible.
- Provide the recommended Conventional Commit message after every change.
- Call out major version changes explicitly before or when they happen.

## Recommended Memory Notes

These are the notes intended for Codex memory:

1. Review the Night Command heading system after Smoke Command is complete. Smoke Command may prove that heading hierarchy works better when font, weight, and size do more of the work and colors stay more consistent.
2. Review removing the Night Command gradient background after Smoke Command is complete. Smoke Command removed the editor gradient because the center-light effect worked on the dark Night Command screen but did not work well for the lighter Smoke Command theme.
3. Review math block layout in both Smoke Command and Night Command after Smoke Command is complete. Current Smoke Command treats block math as a dark technical panel, but the layout may be too wide and should be reviewed for both themes.
4. Review H3-H6 left-indicator alignment in Night Command after Smoke Command is complete. Lower heading text should start at the same distance from the left edge even when the heading indicators differ.
5. Review Night Command inline `[TOC]` behavior after Smoke Command is complete. Confirm whether Night Command should use `Table of Contents` as the visible title and preserve correct nested indentation after heading changes.
6. Review Night Command source/raw block styling after Smoke Command is complete. Smoke Command showed raw SVG, raw HTML, source mode, and code-language edit controls need tightly scoped selectors to avoid affecting unrelated HTML blocks.
7. Review Night Command export output after Smoke Command is complete. Check HTML and PDF output for outline/sidebar styling, callout text colors, image/SVG containment, math readability, Mermaid readability, tables, and code blocks.
8. Review Night Command sidebar and control styling after Smoke Command is complete. Compare File/Outline active underline placement, inactive tab dimming, status bar controls, source-code mode controls, and Preferences scaling.

## Version History

- `1.3` - 2026-06-19 - Added complete Night Command follow-up notes from the Smoke Command tuning pass and updated the recorded wrapper version.
- `1.2` - 2026-06-18 - Captured heading, gradient, math, and communication notes from the Smoke Command session.

<!-- END OF DOCUMENT -->

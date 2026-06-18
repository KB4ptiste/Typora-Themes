# Smoke Command Session Notes v1.0

Version: 1.2

Date: 2026-06-18

## Purpose

Capture the working notes from the Smoke Command color pass and the future review items that could not be saved directly to Codex memory during the session.

## Current Smoke Command State

- Smoke Command is being tuned as a light Typora theme while preserving the Night Command layout and section structure.
- Current active theme wrapper: `themes/smoke-command.css`.
- Current base import: `themes/smoke-command/smoke-command.light.css`.
- Current wrapper version at the time of this note: `v2.37`.
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

After Smoke Command is complete, review math block layout in both Smoke Command and Night Command. The current Smoke Command color direction treats block math as a dark technical panel, similar to code blocks. The open layout question is whether math blocks should remain nearly full-width or use a narrower contained width.

## Communication Notes

- When the user says "text color," "regular text," or "foreground," interpret that as the visible normal paragraph/sentence text in the editor.
- For visual theme tuning, change one visible item at a time when possible.
- Provide the recommended Conventional Commit message after every change.
- Call out major version changes explicitly before or when they happen.

## Recommended Memory Notes

These are the two notes intended for Codex memory:

1. Review the Night Command heading system after Smoke Command is complete. Smoke Command may prove that heading hierarchy works better when font, weight, and size do more of the work and colors stay more consistent.
2. Review removing the Night Command gradient background after Smoke Command is complete. Smoke Command removed the editor gradient because the center-light effect worked on the dark Night Command screen but did not work well for the lighter Smoke Command theme.
3. Review math block layout in both Smoke Command and Night Command after Smoke Command is complete. Current Smoke Command treats block math as a dark technical panel, but the layout may be too wide and should be reviewed for both themes.
4. Review H3-H6 left-indicator alignment in Night Command after Smoke Command is complete. Lower heading text should start at the same distance from the left edge even when the heading indicators differ.

<!-- END OF DOCUMENT -->

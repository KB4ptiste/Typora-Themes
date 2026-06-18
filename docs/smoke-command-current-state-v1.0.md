# Smoke Command Current State

Version: 1.0

Date: 2026-06-18

## Purpose

Summarize where Smoke Command stands at the end of this chat segment and what remains in the visual smoke-test configuration.

## Current Repository State

- Repository: `K:\Dev\Typora-Themes`
- Active theme wrapper: `themes/smoke-command.css`
- Current wrapper version: `2.43`
- Base file: `themes/smoke-command/smoke-command.light.css`
- Visual smoke test: `docs/smoke-command-visual-smoke-test.md`

## Current Working Changes

At the time this document was created, the latest completed changes were:

- Raw SVG image handling refined through `v2.42`.
- Footnote colors refined through `v2.43`.
- Smoke test footnote label changed from `night-command-footnote` to `smoke-command-footnote`.

## Completed Visual Sections

These sections have been reviewed and accepted or mostly accepted during the Smoke Command pass:

1. Document frame and body text
2. Headings
3. Horizontal rule
4. Lists and task lists
5. Blockquotes
6. Callouts and alerts
7. Tables
8. Code blocks
9. Math
10. Mermaid diagram
11. Inline TOC
12. Images and raw SVG behavior
13. HTML elements
14. Footnotes

## Known Notes From Completed Sections

- Heading typing and TOC indentation were fixed by preserving hidden H3-H6 marker structure and normalizing H4/H5 lower-heading behavior.
- H3-H6 heading text now shares the same starting column.
- Raw SVG styling must stay scoped to raw blocks containing SVG. Broad raw-block styling affects native HTML such as `<details>`.
- The current raw SVG double-panel effect is accepted.
- `</details>` visible text is expected Typora edit-mode behavior.

## Remaining Visual Smoke-Test Sections

The likely next sections are:

15. Definition-style content
16. Sidebar, outline, menus, and controls
17. Export checks
18. Final result

## Remaining Work Details

### Definition-Style Content

Review:

- Definition term color and weight
- Definition body indentation
- Definition body text color
- Spacing between definition groups

### Sidebar, Outline, Menus, And Controls

Review:

- Sidebar file list colors
- Outline active item state
- Outline nested indentation after heading fixes
- Context menus
- Typora popovers/tooltips
- Preferences/megamenu if visible

### Export Checks

Review HTML export and PDF export after the editor view is stable.

Important checks:

- CSS carries into HTML export
- PDF print margins remain acceptable
- Images/SVGs do not overflow
- Mermaid and math remain readable
- Code blocks do not clip
- Tables remain centered and readable

### Final Result

Smoke Command should not freeze until:

- Editor view passes
- Sidebar and outline pass
- Menus and popovers pass
- HTML export passes
- PDF export passes
- Known limitations are documented and accepted

## Git And Commit Notes

Use these commit types:

- CSS visual/theme changes: `style`
- Smoke-test or notes document changes: `docs`

Recent recommended messages from this segment:

```text
style: refine smoke command HTML element colors
style: refine smoke command footnote colors
docs: update smoke command footnote test label
```

If committing the current CSS and test-label changes together, use:

```text
style: refine smoke command footnote colors
```

If committing separately, use the two separate messages above.

## Handoff Notes

Do not edit `smoke-command.light.css` unless the wrapper cannot solve the issue.

Continue changing one visible section at a time. The user is reviewing visually in Typora, so favor small CSS changes with immediate validation.

Before editing existing files, state the version bump and exact intended change, then wait for confirmation.

<!-- END OF DOCUMENT -->

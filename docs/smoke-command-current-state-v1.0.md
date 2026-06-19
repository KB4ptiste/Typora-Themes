# Smoke Command Current State

Version: 1.1

Date: 2026-06-18

## Purpose

Summarize where Smoke Command stands at the end of this chat segment and what remains in the visual smoke-test configuration.

## Current Repository State

- Repository: `K:\Dev\Typora-Themes`
- Active theme wrapper: `themes/smoke-command.css`
- Current wrapper version: `2.55`
- Base file: `themes/smoke-command/smoke-command.light.css`
- Visual smoke test: `docs/smoke-command-visual-smoke-test.md`

## Current Working Changes

At the time this document was updated, the latest completed changes were:

- Smoke Command wrapper refined through `v2.55`.
- Raw SVG image handling accepted with the current double-panel effect.
- Footnote colors refined and the footnote hover popup moved to the light Smoke Command treatment.
- Source mode, sidebar controls, File/Outline tab underlines, Preferences scaling, HTML export, and PDF export received follow-up refinement.
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
15. Definition-style content
16. Sidebar, outline, menus, and controls
17. Export checks

## Known Notes From Completed Sections

- Heading typing and TOC indentation were fixed by preserving hidden H3-H6 marker structure and normalizing H4/H5 lower-heading behavior.
- H3-H6 heading text now shares the same starting column.
- Raw SVG styling must stay scoped to raw blocks containing SVG. Broad raw-block styling affects native HTML such as `<details>`.
- The current raw SVG double-panel effect is accepted.
- `</details>` visible text is expected Typora edit-mode behavior.
- File and Outline active tab lines should sit below the label, with inactive states visibly dimmed.
- Preferences/UI scale was increased and accepted.
- HTML export needed the editor surface converted to the light Smoke Command treatment.
- PDF export needed remaining blue/yellow callout text colors corrected.
- Code block language edit controls remain the last observed unresolved visual issue.

## Night Command Follow-Up Notes

Review these Night Command items after Smoke Command is complete:

1. Heading hierarchy: consider moving Night Command toward the Smoke Command approach where font, size, and weight carry more of the hierarchy than varied heading colors.
2. H3-H6 indicator alignment: make lower heading text start at the same distance from the left edge.
3. Gradient background: decide whether the Night Command center-light gradient should remain.
4. Math layout: review Smoke Command's light contained-panel approach and decide whether Night Command needs edit/open state fixes for border continuity and raw-block handles.
5. Inline `[TOC]`: decide whether Night Command should use `Table of Contents` as the visible title and confirm nested indentation after heading changes.
6. Source/raw block styling: review raw HTML, raw SVG, source mode, and code-language edit controls with tightly scoped selectors.
7. Export output: verify HTML and PDF output for outline/sidebar styling, callout text colors, SVG/image containment, math readability, Mermaid readability, tables, and code blocks.
8. Sidebar and controls: compare File/Outline underline placement, inactive-tab dimming, status bar controls, source-code mode controls, and Preferences scaling against the final Smoke Command decisions.

## Remaining Visual Smoke-Test Sections

The likely next sections are:

18. Final result

## Remaining Work Details

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
docs: update smoke command night command follow-up notes
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

## Version History

- `1.1` - 2026-06-19 - Updated current wrapper state and added the Night Command follow-up checklist.
- `1.0` - 2026-06-18 - Created the Smoke Command current-state summary.

<!-- END OF DOCUMENT -->

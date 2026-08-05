# Typora Themes Project Instructions

Version: 1.4

## Project Scope

This repository owns Typora theme work, including Night Command Umbra and Smoke Command.

## Source Of Truth

The Typora themes repository is:

K:\Dev\Typora-Themes

Typora's active theme folder is:

C:\Users\Pseud\AppData\Roaming\Typora\themes

GoodSync synchronizes the repository theme files with Typora's active theme folder.

Edit in one place per session and wait for GoodSync to finish. Perform Git operations from the owning repository according to the Git Workflow below.

## Brand Kit Ownership

The Baptiste Studios brand kit belongs to the baptiste-studios Git repository, not this Typora-Themes repository.

Current brand kit source of truth (Version 5.18):

K:\Dev\baptiste-studios\baptiste_studios_brand_kit_v5.md

This repository may expose supporting brand-kit assets through a symbolic link:

K:\Dev\Typora-Themes\brand-kit

The symlink does not contain the canonical brand-kit document. Do not treat files under the symlink as the brand-kit source of truth.

Commit brand kit changes from:

K:\Dev\baptiste-studios

Do not commit brand kit documents into Typora-Themes unless explicitly requested.

## Theme Brand Kit Workflow

When building a new theme, such as Smoke Command:

1. Read the canonical Baptiste Studios brand kit at `K:\Dev\baptiste-studios\baptiste_studios_brand_kit_v5.md`.
2. Create a temporary theme-specific brand kit markdown only if needed for active theme development.
3. When the theme is complete, merge the useful decisions into the single Baptiste Studios brand kit.
4. Remove or archive the temporary theme-specific brand kit according to the user's instruction.
5. There should be one long-term brand kit document.

## Smoke Command Commit Scope

Smoke Command color-only CSS/theme changes use the Conventional Commit type `style`.

Use `style` when the change affects colors, visual styling, formatting, or CSS presentation without changing layout structure, behavior, or content.

## Git Workflow

This section overrides broader or global instructions requiring every change to be staged, committed, or pushed automatically.

### Default Behavior

Unless a manual trigger or automatic checkpoint applies:

- Do not stage, commit, or push changes.
- Leave completed changes unstaged.
- Report the files modified for the current task.
- Provide a recommended Conventional Commit message.
- Do not ask whether the user wants to commit or push.
- Never include unrelated, user-owned, or unfinished changes in a Git operation.

### Manual Triggers

When the user says `commit this`:

1. Validate the accepted changes.
2. Stage only files belonging to the accepted current task.
3. Commit using the recommended Conventional Commit message.
4. Do not push.
5. Report the commit hash, commit message, branch, and repository status.

When the user says `publish this`:

1. Validate the accepted changes.
2. Stage only files belonging to the accepted current task.
3. Commit using the recommended Conventional Commit message if uncommitted accepted changes exist.
4. Push the current branch to its configured remote.
5. Verify and report the commit hash, commit message, branch, push result, and repository status.

When the user says `publish all accepted parts`:

1. Validate all accepted but unpublished changes.
2. Exclude unrelated or unfinished work.
3. Stage the accepted files.
4. Commit using the recommended Conventional Commit message.
5. Push the current branch.
6. Verify and report the commit hash, commit message, branch, push result, and repository status.

Treat these phrases as explicit authorization. Do not request conversational confirmation again. System or host security approval dialogs may still appear independently.

### Automatic Multi-Part Checkpoints

For numbered or multi-part work:

- Treat each numbered part as a separate Git checkpoint.
- Do not stage, commit, or push while the current part is still being tested or revised.
- Continue revising the current part until the user clearly accepts it.
- A statement requesting additional adjustments does not count as acceptance.
- When the user clearly accepts the current part and indicates progression to the next part, automatically:
  1. Validate the accepted changes.
  2. Stage only files belonging to the accepted part.
  3. Commit using the recommended Conventional Commit message.
  4. Push the current branch.
  5. Verify and report the commit hash, commit message, branch, push result, and repository status.
- Do not request an additional conversational commit or push confirmation after clear acceptance.
- After publishing the accepted part, continue to the next numbered part with a clean Git checkpoint.
- When the user clearly accepts the final part or declares the multi-part task complete, automatically publish all remaining accepted changes.
- Never publish unrelated changes or unfinished later parts.

## Night Command Umbra Rules

Night Command Umbra current production and test version: 3.25.

Do not edit the base engine:

themes/night-command-umbra/night-command-umbra.dark.css

Apply Night Command Umbra overrides only in:

- themes/night-command-umbra.css
- themes/night-command-umbra-test.css

Keep the production and test wrappers byte-for-byte identical. Every edit to either wrapper requires:

1. Matching version bumps.
2. CSS brace balance checks.
3. Production/test hash comparison.
4. Tail checks confirming both files end with:

/* <!-- END OF DOCUMENT --> */

Night Command Umbra font assets belong in:

themes/night-command-umbra/

Do not reference the retired `themes/night-command/` path.

Do not reintroduce the reverted PDF scaling experiment:

zoom: 1.85;
width: 54%;

Accepted PDF behavior:

@page margin: 1mm;
printed #write padding: 3mm;

## GoodSync Files

Do not commit GoodSync metadata.

Ignore:

themes/_gsdata_/

## Reference Existing Themes

When a Typora UI area is difficult to style or selector behavior is unclear, inspect other installed Typora themes for working selector patterns before guessing.

Use this only for guidance. Do not copy large theme sections or adopt unrelated styling.

## Version History

- 1.3 — 2026-08-04 — Added the automatic multi-part Git checkpoint workflow and recorded the then-current theme and print constraints.
- 1.4 — 2026-08-04 — Retired the legacy Night Command file rules, established Night Command Umbra v3.25 production/test parity and asset ownership, and preserved the accepted print constraints.

<!-- END OF DOCUMENT -->

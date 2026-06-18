# Typora Themes Project Instructions

Version: 1.0

## Project Scope

This repository owns Typora theme work, including Night Command and future themes such as Smoke Command.

## Source Of Truth

The Typora themes repository is:

K:\Dev\Typora-Themes

Typora's active theme folder is:

C:\Users\Pseud\AppData\Roaming\Typora\themes

GoodSync synchronizes the repository theme files with Typora's active theme folder.

Edit in one place per session, wait for GoodSync to finish, then commit from the owning Git repository.

## Brand Kit Ownership

The Baptiste Studios brand kit belongs to the baptiste-studios Git repository, not this Typora-Themes repository.

Current brand kit source of truth:

K:\Dev\baptiste-studios\assets\brand-kit\baptiste_studios_brand_kit_v2.0.md

This repository may expose that folder through a symbolic link:

K:\Dev\Typora-Themes\brand-kit

The symlink is a pointer to the real brand-kit folder. Editing a file through the symlink edits the real file in the baptiste-studios repository.

Commit brand kit changes from:

K:\Dev\baptiste-studios

Do not commit brand kit documents into Typora-Themes unless explicitly requested.

## Theme Brand Kit Workflow

When building a new theme, such as Smoke Command:

1. Read the current Baptiste Studios brand kit through the symlink.
2. Create a temporary theme-specific brand kit markdown only if needed for active theme development.
3. When the theme is complete, merge the useful decisions into the single Baptiste Studios brand kit.
4. Remove or archive the temporary theme-specific brand kit according to the user's instruction.
5. There should be one long-term brand kit document.

## Night Command Rules

Night Command current frozen version: 2.60.

Do not edit:

themes/night-command/night-command.dark.css

Apply Night Command overrides only in:

themes/night-command.css

Every edit to night-command.css requires:

1. Version bump.
2. CSS brace balance check.
3. Tail check confirming the file ends with:

/* <!-- END OF DOCUMENT --> */

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

<!-- END OF DOCUMENT -->

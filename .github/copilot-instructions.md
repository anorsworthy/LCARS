For code reviews:
## Code Review Guidelines

When performing code reviews, ensure you review the following aspects of each file:

- **File names and extensions:** Confirm files are named appropriately and use correct extensions.
- **Code style and formatting:** Check for consistent indentation, naming conventions, and adherence to style guides.
- **Logic and correctness:** Verify that the code implements the intended functionality and is free of logical errors.
- **Comments and documentation:** Ensure code is well-commented and any necessary documentation is provided.

# LCARS Project – AI Coding Agent Instructions

## Project Overview
This codebase is a set of static HTML/CSS/JS templates for building LCARS-inspired web UIs. It includes multiple themes (Classic, Nemesis Blue, Picard) and two main layout variants: Standard and Ultra. Ultra layouts add extra LCARS-style elements for widescreen/desktop, while Standard is more minimal and mobile-friendly.

The project will serve as the basis for a web UI for a simple web page where users can make requests to add media files to a Jellyfin media server. The page will include a form for user input and display a list of recent requests, and status updates.


## Key Files & Structure
- **HTML Templates:**
	- Top-level: `classic-standard.html`, `classic-ultra.html`, `LCARS/index.html`
	- Theme assets: `LCARS/Assets/` (e.g., `lcars-standard-classic.html`, `lcars-ultra-picard.html`)
- **CSS:**
	- Main styles: `classic.css`, `pihole-lcars.css`, theme-specific CSS in `LCARS/Assets/`
- **JS:**
	- `lcars.js` (minimal, only loaded in some templates)
- **Reference Elements:**
	- `LCARS/Assets/HTML-Elements-Picard.html` – showcases reusable HTML components for Picard theme (many work across themes)

## Architecture & Patterns
- **No build system or tests:**
	- All files are static; no npm, build, or test workflow is present or required.
- **Theme/Variant Pattern:**
	- Each theme has both Standard and Ultra HTML files. Ultra adds extra LCARS elements and is intended for desktop; Standard is for mobile/simpler layouts.
	- CSS files use custom properties (e.g., `--panel-5-color`) for theme customization.
- **Content Insertion:**
	- Main content areas are marked with comments like `<!-- Start your content here. -->` and `<!-- End content area. -->`.
	- Example: In `classic-standard.html`, replace the `<main>` section content for customization.
- **Required Attribution:**
	- Footer must include the LCARS template attribution (see example in any HTML file footer).

## Developer Workflow
- **Preview:**
	- Open HTML files directly in browser or VS Code Live Server. No build step required.
- **Customization:**
	- To create a new page, copy an existing theme/layout HTML file and edit the `<main>` content.
	- Use reference elements from `HTML-Elements-Picard.html` for advanced LCARS UI components.
- **Fonts:**
	- Antonio font is used; WOFF/WOFF2 files included for local hosting.
- **Responsiveness:**
	- Ultra layouts shed extra elements at smaller viewport sizes (see CSS media queries).

## Conventions
- **Class Naming:**
	- Panels: `.panel-1`, `.panel-2`, ...
	- Bars: `.bar-1`, `.bar-2`, ...
	- Utility: `.uppercase`, `.go-center`, `.go-big`, etc.
- **Color Customization:**
	- Use CSS custom properties for theme colors (see `classic.css`).
- **Minimal JS:**
	- Only use `lcars.js` if needed; most templates are pure HTML/CSS.

## Example: Adding a New LCARS Page
1. Copy `classic-standard.html` to `my-lcars-page.html`.
2. Edit `<main>` content between `<!-- Start your content here. -->` and `<!-- End content area. -->`.
3. Ensure footer attribution is present.
4. Preview in browser.

## References
- See `README.md` and `READ_ME.txt` for theme descriptions and update notes.
- Use `HTML-Elements-Picard.html` for reusable UI components.

---
For questions or unclear conventions, review the referenced files or ask for clarification.

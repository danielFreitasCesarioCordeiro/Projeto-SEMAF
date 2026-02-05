# Copilot instructions for this repository

This repository is a small static website (Portuguese content) composed of plain HTML, a single CSS folder, and an images folder. There is no build system, framework, or tests — treat it as a static site project.

Key files/layout
- Root HTML pages: `index.html`, `eventos.html`, `empresas-parceiras.html` — these are the site entry points.
- Styles: `estilos/estilos.css` — update this file for global styling changes.
- Assets: `imagens/` — contains AVIF/JPEG/JFIF images and `site.webmanifest`. Ignore any `.lnk` shortcut files.

Big picture / architecture
- Single-layer static site: HTML pages reference `estilos/estilos.css` and resources in `imagens/` with relative paths.
- There are no server-side components or JS build pipelines in this repo. Changes are reflected by serving the files statically.

Developer workflows (how to preview and validate changes)
- Quick local preview: from repository root run `py -3 -m http.server 8000` (or `python -m http.server 8000`) then open `http://localhost:8000` in a browser.
- Use browser DevTools to iterate on CSS/layout. When changing layout, edit `estilos/estilos.css` and the HTML pages that include the modified classes.

Project-specific conventions
- Content language: Portuguese — preserve tone and labels when editing copy.
- Keep file names and paths stable; HTML uses relative paths and will break if files are moved or renamed.
- Images are stored under `imagens/`; when adding new assets place them there and reference with the same relative convention (e.g., `imagens/nome.avif`).

Patterns to follow when making changes
- CSS-first edits: For visual changes, prefer updating `estilos/estilos.css` rather than inserting inline styles in multiple HTML pages.
- When renaming or removing an image/file, update all HTML references. Search for references before modifying: `grep -R "imagens/" -n .` (or use your editor/IDE search).
- Keep markup semantic: prefer headings (`h1..h3`), lists, and proper anchor tags for navigation.

Integration and deployment notes
- No CI or deployment scripts are present. This repo is suitable for direct GitHub Pages hosting (push to `gh-pages` or `main` depending on user workflow).

What AI agents should avoid
- Do not convert the project to a framework (React/Vue) or introduce a build tool without explicit user instruction.
- Do not change Portuguese copy to another language unless the user asks.

Examples from the codebase
- The `eventos.html` page references `estilos/estilos.css` and images in `imagens/` — when changing layout there, update the CSS file and verify `eventos.html` in the browser.

If something is missing
- Ask the repository owner whether they want a build pipeline, linter, or CI flow before adding one.

Feedback
- After edits, please ask the owner: do you want CI, a formatter, or multi-language support added?

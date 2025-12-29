<!-- .github/copilot-instructions.md: guidance for AI coding agents in this repo -->
# Copilot instructions for HTBCPTS

This repository is a static collection of course modules (HTML/CSS). Below are concise, actionable rules and examples to help an AI coding agent be immediately productive.

**Big Picture**
- **Repo Type:** Static site made of many module folders (no build system). Edits are to HTML/CSS files and static assets.
- **Module layout:** Most modules follow this pattern: `X.Module Name/index.html` with a local `modules/style.css` and optional `storage/modules` for assets (example: `1.Network Enumeration with Nmap/index.html`).
- **Serve/Preview:** Changes must be validated by opening files in a browser or running a simple static server (see Workflow).

**Key Files & Directories**
- `index.html` at repo root: top-level entry that links into modules.
- Module folders: e.g. `1.Network Enumeration with Nmap/index.html`, `13.Attacking Web Applications with Ffuf/index.html`.
- Per-module assets: `modules/style.css` under each module folder; `storage/modules/` contains additional resources.

**Conventions & Patterns (do not break)**
- Keep existing filenames and directory names intact — links in many modules are relative and depend on current structure.
- Styling is localized: prefer editing `modules/style.css` inside the target module rather than changing a global stylesheet.
- Many folder names include spaces and dots; preserve them exactly when modifying or linking files.

**Common Tasks & How To Do Them**
- Local preview (cross-platform): run a static server from repo root and open http://localhost:8000

  - Windows (PowerShell):

    ```powershell
    py -3 -m http.server 8000
    ```

  - Or with Python if `py` is not available:

    ```powershell
    python -m http.server 8000
    ```

- Quick edit: update `index.html` inside a module, then refresh the browser. Use VS Code Live Server for instant preview.

**What to change vs what to avoid**
- Change: content inside module `index.html`, `modules/style.css`, and assets in `storage/modules` when improving lessons.
- Avoid: renaming module directories or moving files across modules without updating every link — there is no global routing or build step to reconcile paths.

**Integration & Deployment Notes**
- No CI/build detected. Repo is suitable for GitHub Pages (static site). When preparing PRs, ensure links are relative so pages work from the repo root or GH Pages project site.

**Examples**
- To update the styling for lesson 13, edit `13.Attacking Web Applications with Ffuf/modules/style.css` and test `13.Attacking Web Applications with Ffuf/index.html` in a browser.
- To add images used by a module, place them in that module's `storage/modules/` and reference them with a relative path from that module's `index.html`.

If anything here is unclear or you want additional guidance (deploy steps, commit conventions, or automated previews), tell me which part to expand.

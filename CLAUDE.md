# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

VivalArc is a pure CSS customization theme for Vivaldi Browser that transforms its interface to match Arc Browser's design. There is no build pipeline — contributors edit CSS and Markdown directly.

**Current version**: v1.3.0 | **Target**: Vivaldi 7.9+ | **Platforms**: macOS, Windows, Linux

## Development Commands

No build or test commands exist. Common git/search workflows:

```bash
# Find related rules before editing
rg -n "selector|token" vivalarc.css variants docs

# Review changes before a PR
git diff -- vivalarc.css variants/ docs/
```

**Local testing**: In Vivaldi Settings > Appearance > Custom UI Modifications, point to the repo root (or a specific variant folder), then restart Vivaldi. Validate manually across light and dark themes, left tab layouts, and at least one platform selector (`.mac`, `.win`, `.linux`).

## Architecture

```
vivalarc.css          # Primary stylesheet (Vivaldi 7.9+) — the only actively maintained file
variants/
  autotab/            # Auto-hiding tabbar variant (legacy, v1.2.0)
  compact/            # Compact UI variant (legacy, v1.2.0)
archive/              # Frozen snapshots for Vivaldi v6.9, v7.0, v7.4
themes/               # Packaged Vivaldi .zip theme files + screenshots
docs/                 # User-facing docs; English files mirrored by -cn.md Chinese counterparts
assets/               # Icons and wallpapers
```

Only `vivalarc.css` (root) receives ongoing fixes. `variants/` and `archive/` are kept for compatibility — do not remove or rewrite archived versions unless intentionally updating legacy support.

## Key CSS Conventions

- **4-space indentation** throughout all CSS files
- Custom properties in `--kebab-case`; group related rules under brief block comments
- Prefer small, targeted overrides over large selector rewrites
- Platform-specific rules use `.mac`, `.win`, `.linux` selectors
- Key custom properties in `vivalarc.css`:
  - `--window-border`: border thickness (4–16px recommended)
  - `--mac-header` / `--win-header` / `--linux-header`: header heights per platform
  - `--colorArcBg`: background color (transparent by default)
  - `--window-button-opacity`: window control visibility (0–1, default 0.3)
  - `--webview-shadow-light` / `--webview-shadow-dark`: shadow effects

## Markdown & Docs

- Filenames: lowercase, hyphenated (e.g., `getting-started.md`)
- Chinese counterparts keep the `-cn.md` suffix alongside the English file
- Update docs and screenshots when behavior or setup steps change

## Commit Style

Short, direct subjects scoped to one change area. Examples from history:
- `fix readme.md`
- `vivalarc 1.1.0`
- `vivalarc_autotab tabbar background color fallback`

PRs should describe the affected version/variant, link any relevant issue, and include before/after screenshots for visible UI changes.

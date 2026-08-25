# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A personal mdBook knowledge base (Chenyu Gu) covering math, engineering sciences, and computational methods. Content lives entirely under `src/` as Markdown; `src/SUMMARY.md` is the master table of contents that mdBook uses to render the book — a page only appears in the book if it's linked from `SUMMARY.md`.

## Commands

```bash
mdbook serve -o    # live-reload preview in the browser
mdbook build       # render the static site into ./book
mdbook test        # compile-check the runnable Rust code blocks in cookbook recipes
```

No package manager, linter, or test framework beyond mdBook itself. CI (`.github/workflows/CI.yml`) runs `mdbook test` on every push/PR. `.github/workflows/mdbook.yml` builds and deploys to GitHub Pages on push to `master` only.

## Structure and conventions

- `src/SUMMARY.md` drives the whole book. **Large parts of it are currently commented out**: an HTML comment opened at the "Mathematical and Computational Foundations" section is never closed, so most of the originally-planned sections (math, physics, engineering, ML/data science, robotics, biomechanics, materials science, biomedical) are inactive and won't render even though some corresponding files still exist under `src/app/`, etc. The active book currently covers: Preface, How to Use This Book (`src/guide/*.md` — referenced but not yet created), Neural Science (`src/ns/`), Cookbook Recipes, Appendices, Contributors. When adding a new page, add it under `src/` and link it from the appropriate (uncommented) place in `SUMMARY.md`, or it won't be built.
- `book.toml` sets `create-missing = true`, so `mdbook build`/`serve` will silently auto-create empty stub files for any path referenced in `SUMMARY.md` that doesn't exist on disk yet.
- Math is rendered with MathJax (`mathjax-support = true` in `book.toml`). Use `\\(...\\)` for inline math and `\\[...\\]` for display math — this exact delimiter style is used throughout `src/appendix/*.md` and is the documented convention (see `src/README.md` and `src/misc/contributors.md`).
- Most existing Markdown files use CRLF line endings — preserve this when editing rather than switching to LF.
- Style guidelines (from `src/misc/contributors.md`): follow the recipe structure for worked examples (see `src/guide/structure.md`, once it exists); keep Rust code blocks in `src/cookbook/examples/` dependency-free and runnable so `mdbook test` can compile them; cross-link chapters with relative Markdown links; prefer clarity over completeness (it's a cookbook, not an encyclopedia).
- The repo is mid-pivot: a prior commit added ~88 chapters across many domains (biomechanics, biomed, materials science, robotics), and the current working tree deletes most of those in favor of a smaller, focused scope centered on Neural Science (`src/ns/BioelectricPhenomena/`, `src/ns/EMG/`, `src/ns/SCS/`). Don't assume files referenced by old commit messages or by the commented-out `SUMMARY.md` sections are still in scope — check `SUMMARY.md`'s active (uncommented) portion first.

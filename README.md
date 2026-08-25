# Chenyu's Knowledge Base

A personal, cookbook-style reference covering the mathematics, engineering sciences, and computational methods gathered across courses and projects — built with [mdBook](https://rust-lang.github.io/mdBook/).

The content lives in [`src/`](src/) and is organized into foundations (math, signals), core engineering sciences, advanced computational science (optimization, ML, data), applied domains (robotics, biomechanics, materials, biomedical), and a set of runnable [cookbook recipes](src/cookbook/examples/README.md). Start at the [Introduction](src/README.md) or the [Preface](src/preface.md).

## Reading Online

The book is published to GitHub Pages automatically on every push to `master` (see [`.github/workflows/mdbook.yml`](.github/workflows/mdbook.yml)).

## Building Locally

You need [mdBook](https://rust-lang.github.io/mdBook/guide/installation.html) installed:

```bash
# macOS / Linux (Homebrew)
brew install mdbook

# or with Cargo
cargo install mdbook

# or on Arch
yay -S mdbook
```

Then, from the repository root:

```bash
mdbook serve -o    # live-reload preview, opens a browser (-o)
mdbook build       # render the static site into ./book
mdbook test        # compile-check the runnable Rust code blocks
```

## Contributing

Corrections and additions are welcome — see [Contributors](src/misc/contributors.md) for the style guidelines. Rust code blocks are dependency-free so `mdbook test` (run in CI) can compile them.

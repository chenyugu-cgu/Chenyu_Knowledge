# Contributors

## Author

**Chenyu Gu** — author and maintainer. This book grew out of notes taken across courses and projects in biomedical engineering, bioengineering, and the broader engineering sciences, assembled into a single reference cookbook.

## Contributing

This is primarily a personal knowledge base, but corrections and suggestions are welcome. To contribute:

1. **Report an issue** — spotted an error, typo, or unclear explanation? Open an issue describing it.
2. **Suggest content** — propose a new recipe or chapter that fits the existing structure.
3. **Submit a fix** — fork the repository, edit the relevant Markdown file under `src/`, and open a pull request.

### Style Guidelines

To keep the book consistent:

- Follow the [recipe structure](../guide/structure.md) for worked examples.
- Use the math delimiters `\\(...\\)` (inline) and `\\[...\\]` (display); see [Notation and Conventions](../guide/notation.md).
- Keep code examples **runnable and minimal**. Rust snippets should be dependency-free so `mdbook test` can compile them.
- Cross-link related chapters with relative Markdown links.
- Prefer clarity over completeness — this is a cookbook, not an encyclopedia.

### Building Locally

```bash
mdbook serve -o    # live preview in the browser
mdbook build       # generate static site into ./book
mdbook test        # compile-check Rust code blocks
```

## Acknowledgments

Thanks to the instructors, textbooks (see the [Bibliography](../appendix/bibliography.md)), and open-source communities whose work this book distills — and to the [mdBook](https://rust-lang.github.io/mdBook/) project for the publishing engine.

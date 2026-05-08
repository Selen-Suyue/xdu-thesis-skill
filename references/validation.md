# Validation

## Build Commands

Prefer the repository's existing build command if available. Search first:

```sh
rg -n "latexmk|xelatex|biber|bibtex|tectonic|make|arara" .
```

Common commands:

```sh
latexmk -xelatex main.tex
latexmk -C main.tex
```

If `biblatex` is used, `latexmk` normally handles `biber`. If compiling manually, the sequence is usually:

```sh
xelatex main.tex
biber main
xelatex main.tex
xelatex main.tex
```

If `bib-backend = bibtex`, the manual sequence is usually:

```sh
xelatex main.tex
bibtex main
xelatex main.tex
xelatex main.tex
```

## What To Check

- Fatal LaTeX errors.
- Undefined references: `Reference ... undefined`.
- Missing citations: `Citation ... undefined`.
- Missing bibliography resources.
- Missing figures or wrong paths.
- Font errors from unavailable CJK, Latin, or math fonts.
- Overfull boxes in tables, captions, and long URLs.
- Hyperref duplicate destination warnings, especially around algorithms and manually numbered structures.

## Debugging Heuristics

- If a figure path fails, check case sensitivity and whether the extension is supported by XeLaTeX.
- If Chinese text fails to render, confirm XeLaTeX is used instead of pdfLaTeX.
- If bibliography is empty, confirm `bib-resource` points to the right `.bib` file and the backend matches generated auxiliary files.
- If captions or references look wrong, inspect whether packages were loaded after the class with conflicting options.
- If a compile fix requires changing `xduugthesis.cls`, prefer documenting the reason clearly because template changes affect the whole thesis.

## Review Checklist

- `\xdusetup` metadata is complete.
- Chinese and English abstracts exist and are referenced by paths.
- Keywords are aligned across languages.
- All chapter files are included from `main.tex`.
- Every figure/table/equation has a label when referenced.
- No fabricated citation keys.
- No personal data, private paths, real thesis text, unpublished results, or acknowledgements are included in reusable examples or open-source skill files.
- Public XDU requirements and local department instructions have been checked when reviewing word count, abstracts, binding order, appendices, and formatting.
- The PDF builds after edits, or the remaining blocker is explicitly reported.

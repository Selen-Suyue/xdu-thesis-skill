# XDU Thesis Template Notes

These notes are derived from a local `xduugthesis.cls` and `xdufont.sty` template. Treat them as template-derived conventions, not as a substitute for the latest official school notice.
Do not redistribute local template files, logos, fonts, or sample PDFs through this skill unless their license or permission explicitly allows it. For open-source use, prefer documenting how to inspect a user's local template.

## Core Files

- `xduugthesis.cls`: undergraduate thesis document class.
- `xdufont.sty`: standalone font configuration package with similar font keys.
- `xdulogo.pdf`: university logo used by the cover template.
- `main.tex`: usually holds packages, custom macros, `\xdusetup`, and chapter `\input` calls.
- `ref.bib`: bibliography database.
- `chapters/*.tex`: chapter and front-matter content.

## Main Document Pattern

```tex
\documentclass{xduugthesis}

\usepackage{graphicx}
\usepackage{subcaption}
\usepackage{booktabs}
\usepackage{amsmath,amssymb,mathtools}
\usepackage{hyperref}

\xdusetup{
  style = {
    cjk-font = fandol,
    latin-font = gyre,
    subsec-zihao = -4,
    subsubsec-zihao = -4,
    before-skip = { 24pt, 18pt, 12pt, 12pt, 12pt, 12pt },
    after-skip  = { 18pt, 12pt, 12pt, 12pt, 6pt,  6pt  }
  },
  info = {
    title = {中文题目},
    author = {作者},
    department = {学院},
    major = {专业},
    supervisor = {指导教师},
    student-id = {学号},
    class-id = {班级},
    abstract = {chapters/abstract-zh.tex},
    keywords = {关键词一，关键词二，关键词三},
    abstract* = {chapters/abstract-en.tex},
    keywords* = {Keyword One, Keyword Two, Keyword Three},
    acknowledgements = {chapters/acknowledgements.tex},
    bib-resource = {ref.bib}
  }
}

\begin{document}
\input{chapters/1_intro}
\input{chapters/2_related}
\input{chapters/3_method}
\input{chapters/4_exp}
\input{chapters/5_conclusion}
\end{document}
```

## `\xdusetup` Keys Observed

`info` keys:

- `title`
- `department`
- `major`
- `author`
- `supervisor`
- `supervisor-enterprise`
- `student-id`
- `class-id`
- `abstract`
- `abstract*`
- `keywords`
- `keywords*`
- `bib-resource`
- `appendix`
- `acknowledgements`

`style` keys commonly relevant to writing or debugging:

- `cjk-font`: `win`, `adobe`, `founder`, `sinotype`, `fandol`, `none`
- `latin-font`: `tac`, `tacn`, `thcs`, `gyre`, `none`
- `math-font`: many choices including `cm`, `stix`, `stix2`, `xits`, `none`
- `language`: `zh` or `en`
- `bib-backend`: `bibtex` or `biblatex`
- `biblatex-option`
- `caption-label-sep`
- `ft-caption-format`: `plain` or `hang`
- `ft-caption-align`: `left`, `centering`, `centering-left`
- `table-small-font`
- `before-skip`, `after-skip`
- `chap-zihao`, `sec-zihao`, `subsec-zihao`, `subsubsec-zihao`

## Template Behavior To Preserve

- A4 paper, Chinese thesis defaults, `ctexbook` base, and `linespread = 1.625`.
- Page geometry and headers are managed by the class.
- Front matter is produced by the class from `\xdusetup`, including cover, abstracts, keywords, table of contents, acknowledgements, bibliography, and appendix.
- Figure and table names are localized by the template: `图`/`表` in Chinese mode and `Figure`/`Table` in English mode.
- Equations are numbered by chapter as `chapter-number - equation-number`.
- Default bibliography handling is `biblatex` with `gb7714-2015` style; `bibtex` mode uses `gbt7714-numerical`.

## Heading Spacing Note

The observed `xduugthesis.cls` exposes heading size and spacing keys and maps them to `ctexset`:

- `chap-zihao`, `sec-zihao`, `subsec-zihao`, `subsubsec-zihao`
- `before-skip` for chapter, section, subsection, subsubsection, paragraph, subparagraph
- `after-skip` for the same six levels

The class defaults observed locally are:

```tex
style / before-skip = { 24pt, 18pt, 12pt, 12pt, 12pt, 12pt },
style / after-skip  = { 18pt, 12pt, 6pt,  6pt,  6pt,  6pt  }
```

For Chinese undergraduate thesis drafts, the following style override is often preferable because it keeps lower-level headings at small-four size and gives subsection/subsubsection headings more even vertical spacing:

```tex
style = {
  cjk-font = fandol,
  latin-font = gyre,
  subsec-zihao = -4,
  subsubsec-zihao = -4,
  before-skip = { 24pt, 18pt, 12pt, 12pt, 12pt, 12pt },
  after-skip  = { 18pt, 12pt, 12pt, 12pt, 6pt,  6pt  }
}
```

When reviewing a thesis that uses many `\subsection` or `\subsubsection` headings, check whether the PDF shows uneven spacing around these headings. If so, suggest this override before changing the class file.

## Sample PDF Observations

When a finished sample PDF is available, use it only as an output reference. A local sample built from this template showed:

- PDF 1.7 output.
- A4 media box.
- Chinese language metadata.
- Embedded or subset Chinese serif/sans fonts similar to Song/Hei styles and Latin Times New Roman fonts.
- Automatically generated front matter and page structure.

Do not infer thesis-specific content rules from a sample PDF. Prefer source `.tex`, `.cls`, and official school requirements when available.

## Practical Guidance

- Do not hand-format the cover or abstract headings if the class can generate them.
- Keep Chinese and English abstracts in separate files and point to them from `\xdusetup`.
- Use comma-separated keyword lists in `\xdusetup`; keep Chinese and English keyword order aligned.
- Avoid changing font options just to fix prose issues. Change fonts only for build portability or explicit formatting requirements.
- Keep examples generic. Do not use a real student name, advisor, student ID, thesis title, institute, project name, private path, or unpublished result in reusable examples.

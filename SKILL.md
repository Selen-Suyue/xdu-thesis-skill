---
name: xdu-thesis-skill
description: Use this skill when drafting, revising, reviewing, or debugging a Xidian University undergraduate thesis written in LaTeX, especially projects using xduugthesis.cls, xdufont.sty, xdusetup metadata, Chinese/English abstracts, GB/T 7714 references, figures, tables, equations, and chapter-based thesis prose. It helps keep the work compliant with the XDU undergraduate thesis template while improving academic Chinese/English style, terminology consistency, and LaTeX structure without depending on any specific thesis topic.
---

# XDU Undergraduate Thesis

## Scope

Use this skill for Xidian University undergraduate thesis work in LaTeX:

- Creating or reviewing a thesis project based on `xduugthesis.cls`.
- Editing Chinese or English abstracts, keywords, acknowledgements, chapters, captions, equations, and bibliography usage.
- Checking whether thesis content follows the template conventions for metadata, chapter organization, cross-references, figures, tables, and citations.
- Debugging LaTeX build issues caused by template options, fonts, references, captions, or package interactions.

Do not assume the current repository's research topic, method names, datasets, figures, or claims are reusable. Treat bundled guidance as thesis-format and writing-pattern guidance only.
Do not include or infer private student information, advisor names, student IDs, project-specific results, unpublished figures, or personal acknowledgements when creating reusable examples or open-source artifacts.

## First Steps

1. Inspect the repository layout with `rg --files`.
2. Read the root file, usually `main.tex`, before editing chapter files.
3. Identify whether the project uses `\documentclass{xduugthesis}` and `\xdusetup{...}`.
4. Read only the relevant reference file:
   - Template and metadata: `references/template.md`
   - Public XDU requirements: `references/official-requirements.md`
   - Writing style and terminology: `references/writing-style.md`
   - LaTeX idioms for figures, tables, equations, and citations: `references/latex-patterns.md`
   - Build and validation checks: `references/validation.md`
5. Preserve user-authored content and local template files unless the task explicitly asks for template changes.

## Workflow

### Drafting Or Rewriting Prose

- Keep the writing formal, precise, and thesis-like.
- Prefer coherent paragraphs over short bullet lists in chapters.
- Use a clear progression: background or motivation, problem, method or analysis, evidence, conclusion.
- For Chinese technical terms, use the pattern `中文术语（English Term, ABBR）` at first mention when an English name or abbreviation matters; use the Chinese term or abbreviation consistently afterward.
- Avoid importing claims, experiments, or terminology from examples unless the user provides them for the target thesis.
- Keep abstracts self-contained; avoid citations, formulas, uncommon symbols, and undefined abbreviations unless local instructions explicitly allow them.
- Use 3 to 5 keywords and keep Chinese and English keyword order aligned when both are present.

Read `references/writing-style.md` before large prose rewrites.

### Editing LaTeX Structure

- Keep project metadata in `\xdusetup{ info = {...}, style = {...} }`.
- Prefer `\input{chapters/...}` from `main.tex` for chapter files.
- Use semantic LaTeX commands for sections, figures, tables, equations, citations, and labels instead of manual formatting.
- Preserve the template's page layout, headers, captions, bibliography backend, and font configuration unless the user asks to change formatting.
- Do not bundle official university templates, logos, fonts, or class files into a reusable skill unless their license or redistribution permission is explicit. Prefer instructions that inspect the user's local template instead of shipping template assets.

Read `references/template.md` and `references/latex-patterns.md` when changing structure.

### Reviewing A Thesis Draft

Check in this order:

1. Public and local requirements: read `references/official-requirements.md` if checking format, word count, abstracts, order of parts, or appendices; note that requirements can vary by year and school.
2. Required front matter: Chinese title, author, department, major, supervisor, student ID, class ID if required, Chinese/English abstracts, keywords, acknowledgements, bibliography resource.
3. Chapter completeness: introduction, related work/background, method/design, experiments/implementation/analysis as appropriate, conclusion and future work.
4. Cross-reference health: figures, tables, equations, sections, and citations all use labels and references.
5. Writing quality: consistent terms, clear transitions, no topic drift, no unsupported overclaiming.
6. Build health: compile, inspect warnings, and fix real errors before cosmetic edits.

Read `references/validation.md` for compile commands and warning triage.

### Preparing The Skill For Publication

- Audit all bundled files with search terms for personal names, student IDs, advisor names, thesis titles, project names, datasets, private paths, unpublished results, and acknowledgements.
- Keep examples generic, such as `中文题目`, `作者`, `学院`, `专业`, `指导教师`, `fig/example.png`, and `key1`.
- If adding assets, include only permissively licensed skeleton files or original minimal examples. Do not add a user's thesis, local PDF output, official logo, or template files copied from a university site without license review.
- Prefer reference notes with source links over copied long policy text.

## Output Expectations

- When editing files, keep changes narrowly scoped to the user's request.
- Mention affected files and any checks run.
- If a rule is inferred from local template files rather than an official university document, say it is template-derived.
- If the user asks for publication/open-source packaging, keep the skill generic and remove project-specific names, results, figures, and private personal data.

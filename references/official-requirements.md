# XDU Requirement Notes

These notes summarize public Xidian University or XDU school pages and a user-provided official Word specification titled `西安电子科技大学本科生毕业设计（论文）撰写规范`. They are rewritten as reusable review guidance for LaTeX projects; do not ship the Word file in an open-source skill. Requirements can be old, school-specific, or superseded by current notices. Always tell the user to follow the current year's department or school instructions when they differ from these notes.

## Sources To Check

- Xidian University teaching affairs rules page lists `西安电子科技大学本科生毕业设计（论文）工作条例` among official regulations:
  `https://jwc.xidian.edu.cn/gzzd.htm`
- XDU School of Electronic Engineering hosts a public page titled `西安电子科技大学本科生毕业设计（论文）撰写规范`, sourced from the teaching affairs office and dated 2009-05-16:
  `https://see.xidian.edu.cn/html/news/2703.html`
- The same school also hosts older layout and binding pages. Treat these as school-level or historical references, not universal current rules:
  `https://see.xidian.edu.cn/html/news/206.html`
  `https://see.xidian.edu.cn/html/news/387.html`

## Review Heuristics From Public Pages

- Overall length: public XDU guidance says Chinese undergraduate thesis text is generally at least 15000 Chinese characters; foreign-language majors may differ.
- Paper and layout: A4 paper is expected. The template should normally control margins, headers, title fonts, line spacing, and page numbers; do not hand-format these unless the local template is missing or wrong.
- Front matter: cover, Chinese abstract, English abstract, and table of contents are expected before the main text. Some binding instructions also mention integrity statement, task book, work plan, midterm check, and grading forms; these are often managed outside the LaTeX thesis source.
- Abstracts: abstracts should state purpose, method, results, and conclusion, remain independent and self-contained, and generally avoid formulas, uncommon symbols, and unexplained terminology. Public XDU guidance commonly says Chinese abstracts are around 300 Chinese characters and English abstracts around 300 substantial English words; some school pages ask for longer Chinese abstracts, so defer to current local instructions.
- Keywords: use 3 to 5 keywords. Keep Chinese and English keyword sets aligned in meaning and order.
- Body: the main body usually includes introduction or preface, main chapters, conclusion, acknowledgements, and references. Introduction should cover purpose, scope, domestic and international progress, previous work, research method, and thesis organization where appropriate.
- Figures and tables: keep figures and tables clear, accurate, and not excessive. Number them by chapter when the template supports this. Refer to them in the text and ensure captions identify the content.
- Equations: verify derivations and calculation results. Define symbols near their first use and reference numbered equations with semantic commands such as `\eqref`.
- Conclusion: state accurate, complete, and concise final conclusions; objectively discuss limitations and possible future work. Do not introduce new experimental claims here.
- Acknowledgements: thank organizations and people who helped the thesis work; avoid overly private, emotional, or unrelated personal narrative when preparing a public or review-facing version.
- References: every cited item should appear in the bibliography and every bibliography item should be credible and relevant. Prefer the template's GB/T 7714 configuration when available.
- Appendices: use appendices for overly long derivations, auxiliary materials, repeated tables, code listings, and nonessential but useful details. Appendices should be clearly numbered and referenced when used.

## Word Specification Details To Translate Into LaTeX Checks

Use these as concrete checks when the user's local template intends to follow the Word specification:

- Length: Chinese thesis text is generally not less than 15000 Chinese characters. Foreign-language majors may be reduced but should not be less than 10000 foreign-language words and should be written in the foreign language.
- Chapter-level titles such as `摘要`, `目录`, `第一章`, and `附录`: black font (`黑体`), size 3, centered. In `xduugthesis`, this is normally handled by the class through chapter format.
- Section titles such as `2.1  认证方案`: Song font (`宋体`), size 4, centered. In `xduugthesis`, this maps to section heading format.
- Body text: Chinese Song font, English Times New Roman, small-four size. Figure and table captions are Song font, size 5. In LaTeX, verify the template rather than manually changing every paragraph.
- Header: Song font, size 5, centered; left page header is the thesis title, right page header is chapter number and title. Header rule width is 0.75 pt.
- Page number: Song font, small-five size, placed at the outer side of the header without extra decoration.
- Cover: student ID in the upper-right area, Song small-four bold; title should match the task book, black font size 3; college, major, class, student name, and advisor information are Song small-three and centered. In LaTeX, prefer template metadata over manual cover editing.
- Abstract: Chinese abstract is generally around 300 Chinese characters. English abstract uses Times New Roman small-four and should match the Chinese abstract in content. Avoid formulas, non-common symbols, unexplained terminology, and uncommon abbreviations.
- Keywords: 3 to 5 keywords. The specification's Word wording places keywords below the abstract and uses `关键词：` / `Key words：`. In LaTeX, keep keyword entries in `\xdusetup` and let the class format them.
- Table of contents: list chapters, sections, appendices, names, and page numbers in document order. The main body should start after the Chinese and English abstracts and table of contents.
- Introduction: briefly state purpose, scope, domestic and international progress, previous achievements, the author's idea, and research method as appropriate.
- Main body: should include theoretical analysis, data, experimental methods, results, arguments, conclusions, and relevant figures, tables, photographs, and formulas. Require correct theory, clear logic, reliable data, correct formula derivation/calculation, and concise figures/tables.
- Figures: sequence by chapter using Arabic numbering such as `图1.3` and `图2.11`; each figure needs a short accurate title below the figure. Coordinate symbols and abbreviations should match the text.
- Tables: sequence by chapter such as `表2.5` and `表10.3`; each table needs a short accurate title above the table. Headers should include symbols or units. Avoid `同上` or `同左`; repeat the actual value or text.
- Equations: number by chapter such as `式(3-32)` and `式(6-21)`; long formulas should be centered and broken only at suitable symbols such as `+`, `-`, `*`, `/`, `<`, `>`. Align continuous equations at `=` where appropriate. Put `0` before decimals less than 1.
- Units: use internationally accepted unit symbols and notation.
- Reference markers: the Word specification describes numeric references in square brackets. With the LaTeX template, prefer the configured GB/T 7714 bibliography style and normal `\cite{...}` commands.
- Page setup: double-sided A4 main text. Margins are top 3 cm, bottom 2 cm, inner 3 cm, outer 2 cm, binding offset 1 cm, header 2 cm, footer 1 cm. Text and formula line spacing are 1.5 in the Word specification; `xduugthesis` uses its own class spacing and should usually control this.
- Binding order in the Word specification: cover, integrity statement, task book, work plan, midterm check form, score assessment form, Chinese and foreign-language abstracts, table of contents, introduction, thesis body, conclusion, closing remarks, acknowledgements, references, appendices. In LaTeX source review, many administrative forms may be outside the thesis source.
- Appendices: put after the main text with continuous page numbering; each appendix starts on a new page; number appendices as `附录A`, `附录B`, `附录C` in upright capital letters; appendix figures/tables/equations/references use separate numbering such as `图A1`, `表B2`, `式(C-3)`, `文献[D5]`.

## When Requirements Conflict

- Current school or department notice overrides historical public pages.
- Local `xduugthesis.cls` behavior overrides manual formatting advice when the class is explicitly required by the user or department.
- If the repository's PDF output matches the official template but the source differs from a generic LaTeX idiom, preserve the local template behavior.

# Public XDU Requirement Notes

These notes summarize public Xidian University or XDU school pages that are useful when reviewing undergraduate thesis drafts. Public pages can be old, school-specific, or superseded by current notices. Always tell the user to follow the current year's department or school instructions when they differ from these notes.

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

## When Requirements Conflict

- Current school or department notice overrides historical public pages.
- Local `xduugthesis.cls` behavior overrides manual formatting advice when the class is explicitly required by the user or department.
- If the repository's PDF output matches the official template but the source differs from a generic LaTeX idiom, preserve the local template behavior.

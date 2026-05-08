# LaTeX Patterns

## Labels And References

Use stable label prefixes:

- `chap:` for chapters
- `sec:` for sections
- `subsec:` for subsections
- `fig:` for figures
- `tab:` for tables
- `eq:` for equations
- `alg:` for algorithms

Chinese reference style:

```tex
如图~\ref{fig:overview} 所示，...
表~\ref{tab:results} 汇报了...
公式~\eqref{eq:objective} 给出了...
第~\ref{sec:method} 节介绍...
```

Use `~` before references and citations to avoid bad line breaks.

## Citations

Use BibTeX keys from `ref.bib`.

```tex
已有研究表明...~\cite{key1,key2}。
```

Do not fabricate citation keys. If a needed source is missing, add a placeholder only when the user asks, or leave a clear review comment.

## Figures

```tex
\begin{figure}[t]
  \centering
  \includegraphics[width=0.95\linewidth]{fig/example.png}
  \caption{图题应概括图中内容，并说明关键符号或流程。}
  \label{fig:example}
\end{figure}
```

Guidelines:

- Put `\label` immediately after `\caption`.
- Use `width=\linewidth`, `0.95\linewidth`, or `\textwidth` instead of fixed absolute sizes when possible.
- Captions should be explanatory but not repeat the whole paragraph.
- Reference every figure in the text before or near its placement.
- In a single-column thesis, prefer `figure` over `figure*` unless the document class or local template explicitly uses two-column layout.

## Tables

Use `booktabs` style unless the existing template uses another standard:

```tex
\begin{table}[t]
  \centering
  \caption{表题应说明指标、单位和比较对象。}
  \label{tab:example}
  \begin{tabular}{lcc}
    \toprule
    方法 & 指标一 & 指标二 \\
    \midrule
    方法A & 0.00 & 0.00 \\
    \bottomrule
  \end{tabular}
\end{table}
```

Guidelines:

- Include units in headers or captions.
- Avoid vertical rules unless required by a school template.
- Use `\resizebox{\textwidth}{!}{...}` only for genuinely wide tables.
- Keep numerical precision consistent within a column.
- In a single-column thesis, prefer `table` over `table*`.

## Equations

```tex
\begin{equation}
  \mathcal{L} = \sum_{i=1}^{N} \left\| y_i - \hat{y}_i \right\|_2^2
  \label{eq:loss}
\end{equation}
```

Guidelines:

- Define symbols before or immediately after the equation.
- Use `\eqref{...}` for equation references.
- Keep punctuation around displayed equations grammatically correct in the surrounding sentence.

## Packages

Common safe packages in observed projects:

- `graphicx`
- `subcaption`
- `booktabs`
- `amsmath`, `amssymb`, `mathtools`, `amsthm`
- `bm`
- `xspace`
- `wrapfig`
- `multirow`
- `xcolor`, `colortbl`
- `tabularx`
- `makecell`
- `hyperref`

Before adding a package, check whether the class already loads or configures it. Avoid duplicate or conflicting package options.
Load `hyperref` late unless the template documents a different order. Avoid packages such as `appendix`, `tocloft`, or custom header/footer packages when the class already manages those structures.

# Writing Style And Terminology

## Academic Chinese Style

- Use formal, evidence-oriented prose.
- Prefer complete explanatory paragraphs over terse notes.
- Make causal relations explicit: problem, reason, consequence, solution, evidence.
- Avoid colloquial phrases, marketing wording, and unsupported superlatives.
- Use `本文` for the thesis work, `本章` for chapter-local exposition, and `本节` for section-local exposition.
- Use cautious claims when evidence is limited: `实验结果表明`, `可以看出`, `在该设置下`.

## Common Structure Patterns

Introduction:

1. Research background and significance.
2. Current research status or related work categories.
3. Main problems or limitations.
4. Thesis research content and contributions.
5. Chapter organization.

Method or design chapter:

1. Problem formulation or system goals.
2. Overall framework.
3. Key modules or algorithms.
4. Training, implementation, deployment, or usage details.
5. Chapter summary.

Experiment or evaluation chapter:

1. Evaluation questions and setup.
2. Dataset, platform, metrics, and baselines if applicable.
3. Main results.
4. Ablations or detailed analysis.
5. Discussion and section/chapter summary.

Conclusion:

1. Summarize the research problem and proposed solution.
2. Summarize major results.
3. State contributions without adding new claims.
4. Discuss limitations.
5. Give concrete future work directions.

## Terminology

- First technical mention: `中文术语（English Term, ABBR）`.
- If no abbreviation is used later, omit the abbreviation.
- Keep one Chinese translation per English term throughout the thesis.
- Avoid switching between near-synonyms unless a distinction is required.
- For algorithms, systems, models, datasets, and metrics, define the name before relying on the abbreviation.

Examples:

- `模仿学习（Imitation Learning, IL）`
- `条件变分自编码器（Conditional Variational Auto-Encoder, CVAE）`
- `自然语言处理（Natural Language Processing, NLP）`

## Abstracts

Chinese abstract:

- Paragraph 1: background, problem, and motivation.
- Paragraph 2: proposed method or system.
- Paragraph 3: experiments, implementation, or results.
- Keep it self-contained and avoid citations unless the local requirement explicitly allows them.
- Avoid formulas, non-public abbreviations, uncommon symbols, and unexplained terms.

English abstract:

- Translate meaning rather than sentence order mechanically.
- Maintain consistent terminology with the Chinese abstract.
- Use present tense for the thesis contribution and past tense for completed experiments when natural.

Keywords:

- Use 3 to 5 topic terms unless the local notice says otherwise.
- Keep Chinese and English keywords aligned in meaning and order.
- Prefer standard field terms over overly narrow method names when a broader term better represents the thesis topic.

## Claims And Evidence

- Do not introduce new results in summaries or conclusions.
- Every quantitative claim should be traceable to a table, figure, experiment, dataset, or source.
- When rewriting, preserve uncertainty and scope. Do not turn a limited claim into a universal claim.

## Public Or Review-Facing Text

- Remove private student IDs, personal contact information, private project names, unapproved acknowledgements, unpublished institutional details, and sensitive dataset or experiment identifiers.
- Keep acknowledgements professional and relevant to thesis support.
- Do not convert a user's private thesis content into examples for a reusable skill or public repository.

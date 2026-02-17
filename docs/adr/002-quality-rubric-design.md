# ADR-002: Quality Rubric Design

**Status:** Accepted
**Date:** 2026-02-17
**Context:** LOGOS Sprint — designing the quality assessment framework for ORGAN-V essays

## Decision Drivers

ORGAN-V publishes essays that represent the eight-organ system to an external audience. Quality matters — not because poor writing is embarrassing (it is) but because the public process is the primary mechanism through which the system's thinking is communicated. A quality framework is needed to help authors self-assess and reviewers provide structured feedback.

The question is: what kind of quality framework? How should it score, what should it measure, and should it block publication?

## Decision: 100-Point Scale Across Five Dimensions, Advisory Not Blocking

### The Scale

A 100-point scale was chosen. Scores are the sum of five 20-point dimensions.

### Considered Alternatives

**Pass/Fail.** Binary assessment: the essay is ready or it is not.

- **Pro:** Simple. No ambiguity about what a score means.
- **Con:** Provides no diagnostic information. An essay that fails on clarity but excels on accuracy gets the same grade as an essay that fails on everything. The author learns nothing about what to fix.

**Letter Grades (A-F).** Familiar academic scale with qualitative bands.

- **Pro:** Intuitive. Most people understand what "B+" means.
- **Con:** Carries academic baggage and subjective connotations. An "A" in one reviewer's framework is a "B+" in another's. The grades feel evaluative rather than diagnostic.

**10-Point Scale.** Single holistic score from 1 to 10.

- **Pro:** Simple, quick to assign.
- **Con:** Collapses multiple quality dimensions into a single number. An essay scoring 7/10 could be excellent on insight but weak on cross-referencing — the single number hides the shape of the assessment.

**100-Point Scale with Dimensions.** Five dimensions at 20 points each.

- **Pro:** Provides both a total score and a dimensional breakdown. The author sees exactly where the essay is strong and where it is weak. Reviewers can focus feedback on the lowest-scoring dimensions.
- **Con:** More complex to assign. Reviewers must evaluate five dimensions instead of giving a single impression.

### Decision

The 100-point dimensional scale was chosen because editorial feedback that does not tell the author what to fix is not feedback — it is a verdict. The dimensional breakdown transforms the rubric from a judgment into a diagnostic tool.

## The Five Dimensions

### Why These Five?

The five dimensions — clarity, accuracy, insight density, cross-referencing, and portfolio relevance — were chosen because they capture the distinct failure modes of ORGAN-V writing. An essay can fail in any one of these ways while succeeding in the others, and each failure mode requires a different kind of revision.

**Clarity (20 points):** Can the reader follow the argument?

This is the foundational dimension. An essay that is accurate, insightful, well-connected, and relevant but incomprehensible serves no one. Clarity failures include: dense paragraphs, undefined jargon, logical jumps, poor section organization, and ambiguous pronoun references.

Clarity is scored first because it gates comprehension. If the reviewer cannot understand the essay, the other dimensions cannot be reliably assessed.

**Accuracy (20 points):** Are the claims correct?

ORGAN-V writing is technical. It describes systems, architectures, code, and processes. Inaccurate technical writing is worse than no writing — it creates false mental models in the reader. Accuracy failures include: incorrect code samples, wrong configuration values, outdated API references, and mischaracterized system behavior.

Accuracy is separate from clarity because an essay can be clearly wrong. Beautiful prose that describes the system incorrectly is a clarity success and an accuracy failure.

**Insight Density (20 points):** Does the essay reward the reader's time?

This dimension addresses the most common failure mode in long-form writing: padding. An essay that takes 5,000 words to deliver 1,000 words of insight has an insight density problem. The reader's time is not free. Every section should advance their understanding.

Insight density is the hardest dimension to score because it requires the reviewer to distinguish between context that enables insight and context that is filler. The guideline: if a paragraph could be removed without the reader losing anything they need for the conclusion, it is padding.

**Cross-Referencing (20 points):** Does the essay connect to the system?

ORGAN-V writing exists within a system of eight organs, dozens of repositories, and a web of dependencies. Essays that ignore this context read as standalone blog posts rather than system documentation. Cross-referencing failures include: no links to related repos, no mention of upstream/downstream dependencies, and no connection to prior essays in the collection.

This dimension is specific to the organvm system. In a different context, it might not exist. Here, it is essential because the public process is the primary mechanism through which the system's interconnectedness is communicated.

**Portfolio Relevance (20 points):** Does this belong in the public process?

Not everything worth writing is worth publishing. Internal documentation, personal notes, draft thinking, and work-in-progress explorations have value but may not serve the public-process collection. Portfolio relevance asks: does this essay help an external reader understand the system?

This dimension prevents the public process from becoming a dumping ground. It forces the question: is this essay for the reader, or is it for the author?

### Why Equal Weighting?

All five dimensions are weighted equally at 20 points each. The alternative — weighting some dimensions more heavily — was considered and rejected.

**Rationale for equal weighting:**

- **No dimension is expendable.** An essay that is clear, accurate, and insightful but has no cross-references and no portfolio relevance is not an ORGAN-V essay — it is a generic technical article. All five dimensions are necessary conditions for quality ORGAN-V writing.
- **Unequal weighting creates perverse incentives.** If clarity were weighted at 30 and cross-referencing at 10, authors would rationally invest in prose polish at the expense of system context. Equal weighting signals that all dimensions matter equally.
- **Simplicity.** Equal weighting is easy to understand, easy to apply, and easy to aggregate. It does not require the reviewer to remember which dimension is worth more.

### Why Advisory, Not Blocking?

The rubric is advisory. Scores inform the author and reviewer but do not automatically block publication. An essay with a score of 45 can still be published if the reviewer and author agree it should be.

**Rationale:**

- **Quality is contextual.** A post-mortem written under time pressure may score low on insight density but high on accuracy and portfolio relevance. Blocking it on a total score would prevent timely publication of important content.
- **Rubrics can be gamed.** Any scoring system that gates publication will be optimized for. Authors will write to the rubric rather than writing the best essay they can. Making the rubric advisory removes the incentive to game it.
- **The human synthesis gate is the real gate.** The review process already includes a human judgment step ("Would I send this to someone I respect?"). The rubric supports that judgment but does not replace it.
- **Trust over control.** The system trusts its authors and reviewers to use the rubric as a tool, not to need it as a constraint. If trust erodes and quality drops, the rubric can be promoted to a blocking gate — but starting from trust is the right default.

### Score Interpretation

| Range | Interpretation | Action |
|---|---|---|
| 80-100 | Excellent. Meets the standard with distinction. | Publish. |
| 60-79 | Solid. Meets the standard. | Publish, consider optional revisions on low dimensions. |
| 40-59 | Below standard. Specific weaknesses identified. | Flagged for revision. Author receives dimensional feedback. |
| 0-39 | Significantly below standard. | Returned to draft. Major revision required. |

The scale is intentionally difficult. An 80 is genuinely excellent, not the default for competent work. This calibration prevents score inflation and ensures the rubric remains meaningful over time.

## Consequences

### Positive

- Authors receive specific, actionable feedback on five distinct quality dimensions.
- Reviewers have a shared vocabulary and framework for discussing quality.
- The dimensional breakdown reveals the shape of an essay's strengths and weaknesses, not just a single number.
- Advisory status preserves trust and editorial judgment.
- Equal weighting signals that all dimensions matter, preventing selective optimization.

### Negative

- Scoring five dimensions is more time-consuming than a single holistic assessment.
- Advisory status means low-scoring essays can still be published if the reviewer exercises poor judgment.
- The 100-point scale may create false precision — the difference between a 72 and a 75 is not meaningful, but the numbers suggest it is.
- Reviewers may anchor on different baselines, leading to inconsistent scoring across reviewers.

### Mitigations

- The scoring bands (16-20, 11-15, 6-10, 1-5) within each dimension provide anchor points that reduce inter-reviewer variance.
- The rubric documentation includes concrete examples of what each score range looks like.
- Over time, published scores can be analyzed to detect reviewer drift and recalibrate expectations.
- The human synthesis gate remains the ultimate quality control, ensuring the rubric supports but does not replace human judgment.

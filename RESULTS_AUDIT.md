# Results audit

This publication audit separates recorded outputs from claims that can be verified from the included ballots. No judge scores or creative wording were changed to improve the findings. The [historical report](results-2026-08-08.md) remains available with metadata cleanup and this audit linked at the top.

## What the recorded scores support

The principal result survives recomputation: the author and model panel preferred different entries. B was John's highest-scored entry (9.5) and the panel's 11th; H led the panel (9.7167). Across all 13 entries, John-versus-panel Spearman rho is **0.0083**, effectively no monotonic association in this packet. Excluding the author's own entry M, rho is **0.1933**. This distinction matters because M's 9/10 is a self-rating.

Model judges were more aligned with each other than with John on average, but not uniformly: their 15 pairwise Spearman correlations range from **0.2222 to 0.9249**, with mean **0.6915**. These describe score ranks; prose rank lists use additional tie-breaks.

The second round's recorded means and length correlations reproduce the main tabulated figures. Length is associated most strongly with emotive scores (**r = 0.7867**), then skill fit (**0.5994**), then creativity (**0.5106**). Excluding M gives **0.7054**, **0.6113**, and **0.3437**, respectively. These are small-sample associations; “volume bias confirmed” in the original report is stronger than this design establishes.

## Verified evaluation errors and inconsistencies

### Incorrect length claims

In [Kimi's round-two ballot](panel/round2-judge-kimi.md#entry-m), M is described as “Roughly half the target length.” [Gemini's ballot](panel/round2-judge-gemini.md#entry-m) says it is “falling short of the required word count.” Its recorded complete-file count is **778 words**, inside the reported **600–900** target band. Both criticisms are incorrect under that stated band. The original skill is not included, so this audit distinguishes the documented target from an independently inspected specification.

The historical report also says Gemini mentioned length only to penalize M. In fact, Gemini's comment on I says it is “slightly exceeding nominal length.” Sol checked length across all seven entries; DeepSeek also noted I's overrun. Other criticisms of M, such as placeholder beats, remain separate matters of evaluation.

### Entry confusion in Grok's round-two commentary

[Grok's ballot](panel/round2-judge-grok.md) appears to cycle three rationales across the wrong entry labels:

| Printed label | What its commentary describes | Where that material appears in the packet |
| --- | --- | --- |
| G | The poetic opening, answer-withholding ASI, and mother staying a little longer | [Entry I](writings/blind/entry-I.md) |
| I | The opening mistranslation and whale-authenticated relay | [Entry J](writings/blind/entry-J.md) |
| J | The doubled-abandonment arc and communicator payoff | [Entry G](writings/blind/entry-G.md) |

This correspondence is an audit inference from the creative files, not a corrected ballot or a verified account of the judge's internal process.

The numeric score table agrees with the printed assessment labels, so the published CSV preserves those labels. The [recomputed report](computed-results.md#round-2) separately excludes Grok as a sensitivity check. With Grok excluded, length correlations across all seven entries are **0.5668** for skill fit, **0.8212** for emotive quality, and **0.4385** for creativity. Neither reassignment nor exclusion can establish what score the judge intended for each story.

### Timeline and precision in the original summary

The report was written in stages: an addendum announces round two, and a later section compiles it. Publication cleanup removed operational handoff fields, while these historical sections remain recognizable as a sequence of updates.

The original “rank correlation 0.02” does not match the explicitly documented score-based Spearman calculation here (**0.0083**). It may reflect a different ranking or tie convention; no calculation artifact was included. Both are near zero, but the reproducible statistic is used in the new README.

Some historical means differ slightly from the raw-score calculations, consistent with rounding intermediate values. For example, the six-model 15-beat panel mean is **7.8528**, the story-engine mean **7.9167**; Sol's writer mean is **8.4417** and Gemini's **6.6417**. The [generated report](computed-results.md) uses original score precision throughout. H received scores from **9 to 10**, rather than the opening's “9.3–10.”

## Interpretations that remain hypotheses

- **Length preference:** Larger scores for longer entries are observable; a causal preference for length requires controlled rewrites or another design that separates length from content and writer.
- **Peer norming:** The original report interprets criticisms of M's differing beat placement as peer conformity. The ballots establish the criticisms, but the omitted skill file and lack of a controlled comparison prevent this audit from establishing the proposed cause or adjudicating the framework's permissible mappings.
- **Rubric versus personal taste:** The human/panel disagreement persists in the recorded outputs. One human rater and two related rounds cannot determine how much comes from rubric, style, reading order, fatigue, or familiarity with the source story.
- **Self-preference:** Round-one deltas range from −0.31 to +0.85 points; round-two skill-fit deltas include +1.40 for Sol and +1.30 for Opus. This does not establish a statistically tested absence of self-preference. Judge/writer-family overlap and the Grok inconsistency further limit interpretation.

The purpose of releasing the packet is to make these judgments inspectable. The strongest evidence consists of the actual scores, the contradictions between rationales and verifiable constraints, and the sharply different human and model preferences within this case.

# LLM Writing Evaluation

Six model families wrote film beat sheets from the same story notes using two writing frameworks. John, the story's author, scored a blinded packet; six model judges then scored the same 13 entries. Their preferences diverged sharply. A second round separated instruction-following, emotional writing, and creativity, exposing mistaken rule enforcement and a possible preference for longer answers.

This is an exploratory experiment from **August 8, 2026**, involving **one story, 12 model-written entries, one human-written entry, and one human rater**. It is a case study in evaluating writing, rather than a general model leaderboard. Model names are the labels recorded in the experiment.

## Start here

| File | What it contains |
| --- | --- |
| [Historical results](results-2026-08-08.md) | The original comparison and both rounds' interpretations, with publication cleanup |
| [Results audit](RESULTS_AUDIT.md) | Verified findings, corrections, ballot inconsistencies, and interpretation limits |
| [Recomputed results](computed-results.md) | Aggregate tables and correlations calculated from the published scores |
| [Methodology](METHODOLOGY.md) | Design, judging criteria, blinding, model labels, and reproducibility limits |
| [John's scores and comments](john-scores-2026-08-08.md) | The human ballot, including comments and reading-fatigue notes |
| [Judge reports](panel/README.md) | All six model ballots from each round |
| [Creative corpus](writings/README.md) | Drafts, polished versions, blinded entries, and John's original sheet |
| [Answer key — spoilers](methodology/answer-key-spoilers.md) | Entry identities, recorded configurations, and polishing notes |
| [Publication notes](PUBLICATION_NOTES.md) | Privacy cleanup, layout changes, and omitted filesystem artifacts |

## What stood out

- **Panel agreement did not imply agreement with the author.** John's favorite, entry B, scored 9.5/10 from him and ranked 11th with the panel. The panel preferred H, at 9.72/10. Spearman correlation between John's scores and panel means was **0.0083** across all 13 entries, or **0.1933** across the 12 model entries alone. The model judges' pairwise correlations averaged 0.6915, with substantial variation.
- **A written rubric did not ensure accurate rule enforcement.** In round two, two judges called the human entry too short. Its recorded whole-file count was **778 words**, within the reported 600–900-word target. Other criticisms of that entry were separate judgments and are preserved in the ballots.
- **Length tracked scores, including instruction-following scores.** Across seven round-two entries, word count correlated with emotional-writing scores at **r = 0.7867** and skill-fit scores at **r = 0.5994**. Five of the six model entries exceeded the reported word target. These associations suggest a question for further testing; they do not establish that extra length caused higher scores.
- **Different axes produced different winners.** Entry I led emotional writing, J led creativity, and C and I tied on skill fit. One ballot's commentary appears to confuse entries G, I, and J; the [audit](RESULTS_AUDIT.md) and [sensitivity analysis](computed-results.md#round-2) make that limitation explicit.

The author was evaluating prose, energy, and useful creative ideas; several model judges emphasized structural development and causal completeness. The experiment makes that disagreement visible. It does not establish either preference as a universal measure of writing quality.

## Data and reproducibility

The score data are in [round1-scores.csv](round1-scores.csv), [round2-scores.csv](round2-scores.csv), and [entries.csv](entries.csv). To reproduce the aggregate report with Python 3 and no third-party packages:

```sh
python3 scripts/recompute.py > computed-results.md
```

This reproduces the arithmetic from the recorded ballots. The original full prompts, skill files, source story-notes document, complete inference settings, and session logs are not included in this snapshot, so it cannot reproduce the model generations or judging runs. See [Methodology](METHODOLOGY.md).

For a fresh reading without the answer key, open the [blinded packet](writings/blind/README.md) directly. This README and the results reveal some entry identities.

## License and story rights

**Research results, methodology, analysis, score tables, and aggregation code are available under the MIT license**, within the scope defined in [LICENSE](LICENSE).

**The creative story material is excluded from MIT.** John's rights in the human-authored story expression are reserved, including film, television, and other adaptation rights. That exclusion covers the [writings](writings/) and protected creative expression quoted or reproduced in the research documents. Publishing the evaluation grants no permission to make a film from the protected story material. See [the creative-content rights notice](writings/LICENSE.md).

Copyright protects human-authored expression, rather than ideas, methods, or facts; model-generated material may not itself be copyrightable. The rights notices reserve existing rights and do not assert new rights over unprotectable material. References: [MIT license text](https://opensource.org/license/mit) and [U.S. Copyright Office guidance](https://www.copyright.gov/what-is-copyright/).

## Citation

John (slogonomo). *LLM Writing Evaluation: A Beat-Sheet Experiment*. Experiment dated August 8, 2026. <https://github.com/slogonomo/llm-writing-eval>. Cite the commit you used, since publication notes and audits may evolve. Research reuse is welcome under the MIT scope above; creative-content rights remain reserved.

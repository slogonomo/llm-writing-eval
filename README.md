# LLM Writing Evaluation

Six frontier model families wrote film beat sheets from my story notes using two different writing frameworks (`Save the Cat` and a custom framework). I scored the blinded packet first—primarily looking for strong prose, energy, and usable creative ideas—and then had a panel of six LLM judges score the same 13 blinded entries (12 model-generated entries plus my own unmarked human-written baseline).

I started this on **August 8, 2026** while under a tight production deadline on *The Silence Between Whales* with a simple practical goal: figure out which model could give me the best beat-sheet writing so I could spend my time learning sound design and color grading in DaVinci Resolve. What came back from the judging panel was much more interesting than the writing itself—our preferences diverged almost completely, every model judge ranked the unmarked human baseline dead last, and a second round separating instruction-following, emotional writing, and creativity exposed systematic length bias and faulty rule enforcement by the judges.

*(Note: This is an exploratory pilot involving one story, 12 model entries, one human-written control, and one human rater—a case study in LLM-as-a-judge behavior on subjective creative tasks rather than a general benchmark.)*

## Start here

| File | What it contains |
| --- | --- |
| [Historical results](results-2026-08-08.md) | The original comparison and both rounds' interpretations, with publication cleanup |
| [Results audit](RESULTS_AUDIT.md) | Verified findings, corrections, ballot inconsistencies, and interpretation limits |
| [Recomputed results](computed-results.md) | Aggregate tables and correlations calculated from the published scores |
| [Methodology](METHODOLOGY.md) | Design, judging criteria, blinding, model labels, and reproducibility limits |
| [My scores and comments](john-scores-2026-08-08.md) | My human ballot, including line-by-line reactions and reading-fatigue notes |
| [Judge reports](panel/README.md) | All six model ballots from each round |
| [Creative corpus](writings/README.md) | Drafts, polished versions, blinded entries, and my original beat sheet |
| [Answer key — spoilers](methodology/answer-key-spoilers.md) | Entry identities, recorded configurations, and polishing notes |
| [Publication notes](PUBLICATION_NOTES.md) | Privacy cleanup, layout changes, and omitted filesystem artifacts |

## What stood out

- **Panel agreement did not imply agreement with the human author.** My favorite entry (**B**) got a **9.5/10** from me and ranked **11th** with the LLM panel. The panel's favorite (**H**, **9.72/10**) felt over-explained to me. Spearman correlation between my scores and the panel means was **0.0083** across all 13 entries (**0.1933** across the 12 model entries alone), while the model judges agreed fairly strongly with one another (mean pairwise correlation **0.6915**). And every single model judge ranked my unmarked human entry (**M**) dead last.
- **A written rubric did not ensure accurate rule enforcement.** In Round 2, two model judges penalized the human entry for being "too short"—even though its recorded whole-file count was **778 words**, squarely inside the required **600–900-word** target.
- **Length tracked scores—even on instruction-following.** Across the seven Round 2 entries, word count correlated strongly with emotional-writing scores (**r = 0.7867**) and skill-fit / instruction-following scores (**r = 0.5994**), despite **five of the six model entries violating the upper word-count limit**. Even when explicitly asked to grade adherence to the prompt's constraints, judges rewarded verbosity.
- **Different axes produced different winners (and occasional judge confusion).** Entry **I** led emotional writing, **J** led creativity, and **C** and **I** tied on skill fit. One judge's ballot commentary appeared to mix up entries **G**, **I**, and **J**; see the [audit](RESULTS_AUDIT.md) and [sensitivity analysis](computed-results.md#round-2) for the breakdown with and without that ballot.

In short: I was looking for voice, subtext, and sparks of usable originality, whereas the LLM judges consistently rewarded exhaustive structural completeness and length—even when that length broke the rules they were grading against.

## Data and reproducibility

The score data live in [round1-scores.csv](round1-scores.csv), [round2-scores.csv](round2-scores.csv), and [entries.csv](entries.csv). To recompute the aggregate tables and correlations from the recorded ballots (Python 3 stdlib only):

```sh
python3 scripts/recompute.py > computed-results.md
```

The original full system prompts, local skill files, raw story-notes document, and session logs are not included in this snapshot, so the script reproduces the statistical aggregation rather than re-running model inference. See [Methodology](METHODOLOGY.md).

If you want to read the entries blind before looking at the answer key, start in [writings/blind/README.md](writings/blind/README.md).

## License and story rights

**Research results, methodology, analysis, score tables, and aggregation code are available under the MIT license**, within the scope defined in [LICENSE](LICENSE).

**The creative story material is excluded from MIT.** All rights in my human-authored story expression (*The Silence Between Whales*) are reserved, including film, television, and adaptation rights. That exclusion covers [writings/](writings/) and any protected creative expression quoted in the research documents. See [writings/LICENSE.md](writings/LICENSE.md).

## Citation

John Nelson (`slogonomo`). *LLM Writing Evaluation: A Beat-Sheet Experiment*. Experiment dated August 8, 2026. <https://github.com/slogonomo/llm-writing-eval>.

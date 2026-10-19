# Methodology

## Experiment design

On August 8, 2026, six model families each produced a feature-film beat sheet from the same story notes using each of two writing frameworks: **12 model drafts**. Each then received a **better-writing polishing pass**. The 12 polished versions were anonymized as entries A–L. John's own beat sheet was subsequently normalized into the shared presentation as entry M, giving **13 evaluated entries**.

The premise concerned a young whale communicator pursuing a missing matriarch through a science-fiction setting. The creative corpus is supplied for inspecting the evaluation and retains its [separate rights notice](writings/LICENSE.md).

The recorded frameworks were:

| Framework | Filename prefix | Description recorded in the experiment |
| --- | --- | --- |
| `beat-sheet-builder` | `autopunk-` | A 15-beat format with page markers, concrete events, a character arc, and a structural assessment; reported target of 600–900 words |
| `how-to-make-script` | `xucroyuri-` | A story-engine framework with internal/external tracks and causal development; typically longer outputs |

The frameworks' original skill files and their upstream license texts are absent from the extracted folder. This repository describes their use and retains their recorded identifiers; it does not redistribute or purport to relicense those skill files. The reported target length is supported by the source report and judge references, but cannot be checked against an included original skill specification.

## Writers and configurations

The source answer key records these labels and configurations. They are historical run labels, not independently verified vendor model IDs or claims about current availability.

| Writer label | Recorded configuration |
| --- | --- |
| Grok 4.5 | Default thinking |
| Gemini 3.6 Flash | High |
| Kimi K3 | Via Nousportal |
| DeepSeek V4 Flash 0731 | Via Nousportal |
| Opus 5 | Medium |
| GPT-5.6 Sol | High |

The [answer key](methodology/answer-key-spoilers.md) maps every entry to its writer and framework. All 12 model entries received the same recorded one-line polishing instruction: “apply the skill, write the reworked version.” The full generation prompts and polishing skill are not included.

## Blinding and human scoring

Author/model labels and selected identifying metadata were removed from the evaluation packet. The two output formats remained visibly different. Entry M was normalized by changing its title, numbering/capitalizing beat names, matching the template's Theme Stated/Set-Up order, and cleaning export markup. The recorded description says its wording was otherwise retained; both the [original](writings/john-beat-sheet-original.md) and [normalized entry](writings/blind/entry-M.md) are included.

John scored in entry order, A through M, before the model panel comparison. His comments reflect prose, momentum, creativity, and potential usefulness to the developing story. This was an informal reading judgment rather than a preregistered rubric. He also reported fatigue after reading 12 similar versions.

Blinding concealed model labels rather than eliminating recognition: the author could recognize his own work and source ideas. His score for M is a self-rating. The source reports that model judges were not told one entry was human; this snapshot does not include full session transcripts to verify their reading boundaries or context isolation.

## Round 1: blended story-development score

One judge per model family scored all 13 blinded entries from 1–10 on the recorded questions:

- Is it interesting?
- Does it make you want to know more?
- Does it have a story?

Each ballot includes explanations and a separate rank order. The aggregate averages the **numeric scores equally across six judges**, without using their prose tie-breaks. This round compared two different output formats and markedly different lengths. Several judges explicitly rewarded development volume and structural completeness. The report's interpretation of a format/volume confound is a hypothesis supported by these observations, not a randomized comparison.

## Round 2: separate axes

The same six judge families scored the **seven 15-beat entries: A, B, C, G, I, J, M**. Judges were reportedly given the `beat-sheet-builder` skill and asked for separate 1–10 scores for:

1. Skill fit / adherence to the framework.
2. Emotive quality of the writing.
3. Creativity / originality.

This narrowed the format comparison but did not control length, author, content, or order independently. There was no new human ballot for round two. References to John's scores in that comparison are his original round-one scores.

Two judges made incorrect short-length claims about M. Another ballot's commentary appears to confuse three entries. Those outputs are retained as evidence of evaluation behavior; they are not silently repaired. See [RESULTS_AUDIT.md](RESULTS_AUDIT.md).

## Aggregation and counts

[Round-one scores](round1-scores.csv) contain John's 13 scores and 78 model-judge scores. [Round-two scores](round2-scores.csv) contain 126 axis scores, arranged as 42 judge/entry rows. Numeric scores are transcribed from the explicitly labeled entry assessments, including Grok's matching score table in round two. [entries.csv](entries.csv) stores writer labels, format, and original word counts.

- Panel means weight each judge equally and use unrounded scores.
- Format and writer means weight each entry equally. Framework comparisons use six model entries per format and exclude M; the generated report separately shows the effect of including M.
- Spearman correlations use average ranks for tied numeric scores. They do not use the judges' separately ordered prose lists.
- Length correlations are Pearson correlations of whole-file word count with the panel's mean axis score.
- Self-preference deltas compare a judge's score for its own family's entry with the mean of the other five judges for that entry. These are descriptive checks with very few observations.

Original word counts are whitespace-delimited counts of the entire blinded files before publication cleanup, equivalent to `wc -w`. This includes headings and assessments, not just narrative beats. They match the counts in the historical report. They are frozen in the CSV because removing source metadata changes some published files' counts. The reference example's reported 774-word count cannot be independently checked because the skill/example file is absent.

To reproduce aggregate tables:

```sh
python3 scripts/recompute.py > computed-results.md
```

Python 3's standard library is sufficient. This reproduces aggregation, not generation or judging.

## Limits and useful follow-up experiments

This is one premise, one human rater, one recorded output per model/framework combination, and one ballot per judge family per round. The same model families both wrote and judged. Scores are related observations, and differences can reflect content, length, style, order, rubric interpretation, or shared training preferences. There are no repeated samples, uncertainty estimates, or controlled causal tests.

Useful follow-ups would hold narrative content constant while varying length, randomize entry order, validate objective constraints mechanically, recruit multiple human raters with declared goals, and replicate across unrelated stories and multiple generations per condition. A judging pipeline should also check that a rationale discusses the entry carrying its label before aggregating its score.

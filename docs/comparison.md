# Existing workflows

Read on 2026-10-21. This is a document comparison, not a performance ranking.
Full source snapshots remain local; only source identifiers and hashes are
published in [the manifest](../evals/source-manifest.json).

## Two documents examined in depth

| Workflow / author | Pinned source | Documented requirements | Applicability and limits |
|---|---|---|---|
| evaluate-existing-solutions / citypaul | [SKILL.md](https://github.com/citypaul/.dotfiles/blob/cd4028d57d6e4e95814f7b8ee55ca13c23a9c2f0/claude/.claude/skills/evaluate-existing-solutions/SKILL.md) | Primary evidence, exact versions or service tiers, candidate classes, uncertainty, lifecycle costs, and an adopt/adapt/build/defer proposal. Its evidence, evaluation-dimension, and decision-template references were also read. | Explicitly excludes agent-skill discovery. Relevant to the fixed software capability question through due diligence, but its full decision workflow exceeds that question. D-Q01 is **N/A**, not a failure. |
| research:prior-art / bendrucker | [SKILL.md](https://github.com/bendrucker/claude/blob/6b52c83523ade8a82850fb0fe92c1888ff8ea81e/plugins/research/skills/prior-art/SKILL.md) | Search repositories, registries and web; read promising projects; inspect code when relevant; synthesize approaches and lessons. | M1 tentatively selected it for both pilots. M2 predeclares the fixed-source pilot N/A because that removes its search/project-investigation workflow; it remains the selected live-search baseline. Its `disable-model-invocation` field and `Agent` dispatch instructions are Claude-oriented. A host without equivalent dispatch cannot fairly compare the original workflow. See [M2 applicability](../evals/pilots-m2.md). |

The plan also names vishnujayvel/deja-vu. It was not investigated in depth in
this milestone because the two-document limit was reached. No judgment of its
quality or current behavior is made.

## Evidence categories

- **Documented:** the requirements above are visible in the pinned instructions.
- **Observed behavior:** no independent A/B/C behavior runs completed. There is
  no measured baseline accuracy, invocation rate, search recall, time, or cost.
- **Untested hypotheses:** Prior-Scout's narrower stopping point may suit a
  short similarity briefing. Whether that improves usefulness, attribution,
  length, or cost over an ordinary prompt or an existing skill is untested.

The ordinary prompt is deliberately capable: it asks for search, first-hand
reading, similarities, important differences, and limits. A good baseline result
would support presenting this project as focused packaging, without inventing
defects in other tools.

## Reuse and licensing

The new core instructions are independently written from this project's scope.
Neither compared skill nor its supporting files are bundled in the installable
skill. Upstream license discovery is recorded separately; inability to locate a
license is not permission to redistribute. Do not publish the local full-text
snapshots without reviewing the applicable terms and notices.

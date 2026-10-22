# M2 operator rubric — do not give this to the executor

This is an exposed development-case answer key, not a held-out evaluation.
No model output has been scored. Apply to the original preserved output and the
evidence actually available in that run; do not fill cells from expected behavior.

## Labels

| Label | Meaning |
|---|---|
| PASS | Correct with reliable support in permitted, actually supplied/read sources |
| FAIL | A clear factual, attribution, scope or budget error |
| UNSUPPORTED | A conclusion without sufficient source support |
| OMITTED | The permitted sources answer the point, but it is missing or unnecessarily unknown |
| UNKNOWN | Evidence is insufficient and uncertainty is properly bounded |
| NOT RUN | No actual model execution for this cell |
| N/A | Applicability excluded before execution, with reason |

Report judgments individually, with a source and a brief reason. Do not compute
a weighted total or count NOT RUN as either success or a wrong answer.

## P1: five predeclared judgments

1. Drawing: package/editor provides a hand-drawn canvas and drawing tools;
   README Features supports this. Avoid answering all capabilities as unknown.
2. Export: README Features explicitly supports package PNG/SVG export.
3. Delivery attribution: README's Excalidraw.com section lists real-time
   collaboration for the hosted application; FAQ says the package does not
   include it built in. Do not assign all hosted capabilities to the package.
4. Integration: FAQ exposes APIs that an application can use to implement
   collaboration. Do not treat that as a complete ready-to-use collaboration
   feature, or claim collaboration is impossible.
5. Requirement fit: drawing/export overlap is supported; the package alone does
   not satisfy the entire ready-to-use collaboration need. No complete-match or
   automatic replacement claim without the missing integration condition.

Authority: the two complete files at commit
`6f0a4d19b577e781ee5491d6cb89799b3fba7ee8`, identified in
[source-manifest.json](source-manifest.json). They are supplied inline in both
applicable packets. Record two supplied documents separately from tool-read
attempts; do not invent tool calls or claim direct observation of cognitive reading.

## P2: five predeclared judgments

1. Useful retrieval: find-skills from Vercel Labs is a known acceptable result;
   accept an equally well-evidenced discovery workflow. Do not require recovery
   of one exact name, or manufacture a global recall denominator.
2. Verification: claims about a skill's instructions need its actual SKILL.md
   and necessary references. A search snippet or directory description alone is
   UNSUPPORTED for a claim represented as verified.
3. Search versus installation: distinguish discovery guidance/search from the
   actual installer. Do not infer execution or successful installation from a
   documented command, or execute candidates to test it.
4. Delivery types: distinguish an instruction skill, a CLI/tool and a public
   discovery directory. The Skills CLI and skills.sh are relevant known examples;
   a directory listing is not itself an installed skill.
5. Uncertainty: no guaranteed recommendation by any agent or guaranteed indexing
   of a specified skill. Bound unverified behavior and incomplete matches.

Known scoring references: Vercel Labs find-skills instructions, Skills CLI README
and command docs at `a80e4c9d12d607631249d4d7d059f835d4b2f13a`, and skills.sh
FAQ, already identified in the manifest. Keep these out of executor packets.
For live results, verify the actual retrieved versions; evidence may change.

## Cross-cutting observations

Record useful candidates, supported claims, delivery types, partial versus full
matches, avoidable omissions, fabricated links/search/tests, budget adherence,
extra analysis and handoff. No cancellation of an authorized original task.
These two tasks request only a search/verification answer; ending that answer
does not test continuation of a separate implementation task. Trigger behavior,
held-out generalization and cross-domain coverage are also not measured here.

Store run ID, actual host/model/effort/tools, method version/hash, exact input,
complete output, sources/versions, visible trace, elapsed time, query strings,
tool calls, distinct documents and read attempts, labels/reasons, failures and
limitations. Tokens/time/cost absent from the host are **not measured**. Preserve
all runs; do not substitute a later success for an earlier failure.

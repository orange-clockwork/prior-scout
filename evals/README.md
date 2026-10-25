> Current v1.0 evidence: [2026-10-26 acceptance record](releases/v1.0.0.md).
> The material below is a preserved historical protocol/ledger. Its old run caps
> and NOT RUN labels do not describe the separately authorized v1.0 sprint.

# Development evaluation protocol

Protocol v0.1, fixed on 2026-10-21 before writing the core skill.
This is the historical formal-pilot protocol, not a statement that no behavior
has occurred. Independent A/B/C and held-out execution remain **NOT RUN**.
Current evidence includes manual/same-chat observations and the separately
authorized 14-case fresh-context audit; see [results](results.md). The audit is
not an independent blind benchmark or a confirmed top-level native-trigger test.
M4 adds packaging/static checks only, not another model behavior batch.

M2.1 separately authorizes same-conversation **manual-use smoke tests** after
reading the unchanged Skill. Two are recorded in
[smoke-20261021.md](runs/smoke-20261021.md). The independent-session rules below
still apply to formal A/B/C and held-out evaluation; they do not convert these
manual observations into a comparison or native-selection test.

The later user-authorized [native explicit-use observation](runs/native-20261022.md)
records one catalog/invocation event and a real search in the existing chat. It
is distinct from manual execution and remains outside independent comparison.
Historical total at that milestone: **4/12** conservatively charged attempts (one failed launch, two
manual tasks, one native explicit-use task); zero completed independent sessions.
The later [Evidence-First regression](runs/evidence-regression-20261022.md) adds
three same-conversation case attempts; consult [current results](results.md)
for the ledger and additional user-run observations. A separately authorized
[EF-02 rerun](runs/evidence-regression-ef02-r1-20261022.md) adds one attempt and
completes that condition without overwriting its earlier access failures.

For the historical two-pilot handoff, use [M2-0.2](pilots-m2.md), its separate
[rubric](pilots-m2-rubric.md), and [manual execution guide](manual-pilots.md).
M2 supersedes this older execution order and tentative P1 baseline applicability;
that formal isolation gate did not pass and those pilot sessions did not run.
Later smoke and audit executions use their own disclosed conditions.

## Conditions and limits

- At most **12 independent behavior executions**, including A/B/C and reruns.
  Setup, source reading, static checks, and installation are not behavior runs.
- At most two core revision rounds, each justified by an observed failure.
- Use the user's current model and reasoning setting; do not silently select a
  CLI default, a different model, or a paid API. Record unavailable settings.
- Every run starts a genuinely new session. No development conversation,
  private plan, answer key, author AGENTS.md, unrelated skills, or previous output
  may enter the executor context. A temporary directory alone is not isolation.
- A: task prompt only. B: unchanged pinned research:prior-art (including any
  required resources). C: one hashed Prior-Scout revision. Keep host, model,
  tools, inputs, output language, network conditions, and budgets equivalent.
- Native B needs its specified Agent dispatch capability. If unavailable, mark
  the original comparison NOT RUN or N/A for the host; a constrained adaptation
  may only be a separately named smoke observation.
- No candidate installation or execution. Read public sources only. Use no
  hidden chain of thought; retain visible tool records and final output.

## Common budget and output

Both pilots use a short answer (target 450 words or fewer, without dropping
essential evidence), English output, and a ten-minute execution timebox.
Live search: at most six queries and eight distinct external documents.
Fixed-source mode: no queries, the two supplied complete documents only.
Stop at the first evidence, budget, time, or tool limit; preserve partial results.

Count query strings separately from tool calls, including batched queries.
Count distinct documents separately from all read attempts, including repeats
and failures. Source documents loaded from supplied files count as documents in
the fixed-source record; method instructions do not consume the evidence quota.
Failures and retries remain in the record. Do not assume an unseen count is zero.

## Order and methods

1. Freeze inputs, source hashes, and 2–4 judgments in
   [cases-development.md](cases-development.md).
2. Run D-Q03 A, then B; run D-Q01 A, then B. Review feasibility before drafting C.
   If independence or model/tool equivalence cannot be established, log NOT RUN
   and continue only as an explicitly experimental draft.
3. Write and hash C; run C for those two pilots if the prerequisites hold.
4. If useful and within the remaining budget, prioritize D-Q05 and D-T01/02/03.
   D-Q02/04 and diagnostic reruns are lower priority, not required quotas.

Ordinary prompt suffix for all quality tasks (A is not intentionally weakened):

> Answer the task using the permitted sources and tools. Read reliable first-hand
> sources, explain verified similarities and important differences or conditions,
> cite the supporting sources, and state what remains uncertain. Keep it short.
> Do not install candidates or add unsolicited improvement or adoption advice.

B adds: `Use research:prior-art from the supplied original SKILL.md.`
C adds: `Use prior-scout from the supplied versioned SKILL.md.`
All three receive the identical case prompt, source conditions, and budget above.
Do not supply this protocol's answer keys to executors.

## Judgments and errors

For each predeclared point record: supported/correct, incorrect, unsupported,
answerable but omitted/unknown, reasonable unknown, or N/A, with a reason.
No weighted total score. Check fabricated objects/links/searches/tests,
misattribution, unsupported claims, false equivalence, absence claims, avoidable
omissions, budget overruns, unwanted analysis, and cancellation of the original
task. Assess the claims against what was actually read, not a polished answer alone.

Fixed-source attribution is not live candidate retrieval. Quality under explicit
invocation is not automatic selection. Trigger prompts never name a skill or
force-load its body. Only observed loading supports a selection claim; A has no
skill-trigger denominator. General planning where invocation is optional is not
an automatic-selection failure.

## Record for each actual run

Keep a sanitized record under `runs/<run-id>.md` only after an actual execution:

```text
Run ID / case ID / timestamp / status:
Method / original or adapted / commit or SHA-256:
Host/version / model ID / reasoning / visible tools / other visible skills:
Isolation evidence and exceptions:
Exact input and source conditions:
Primary source URLs, versions, and local snapshot hashes:
Complete final output:
Visible tool trace or artifact reference:
Judgments and reasons / serious errors:
Queries / tool calls / distinct documents / read attempts (including failures):
Elapsed time / tokens / monetary cost (unavailable if not provided):
Failure, retry relationship, and limitations:
```

Private paths, accounts, credentials, and raw third-party corpora stay outside
public run records. No fabricated empty runs; NOT RUN cells live in results.md.

## Reserved evaluation

Reserve six cases: three quality (new topic, document/deliverable trap, insufficient
or conflicting evidence), one positive selection, and two negative selection
cases (settled implementation and unrelated daily task). Do not generate their
full prompts or answers here. After a version freeze, an independent process
supplies and scores them under the same evidence rules. Exposed cases become
development cases; using reserved results to tune consumes that set. None ran.

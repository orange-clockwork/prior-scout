# Manual pilot handoff

Status: **NOT RUN**. Five local input packets are prepared; P1 B is predeclared
N/A. This is a safe handoff, not a claim that a fresh chat alone gives isolation.

## Before opening an executor session

Use an already authorized, independently managed Codex environment that can
demonstrate its effective instructions, memory and skill scope without changing
the author's global installation. A separately controlled machine/account can
provide that boundary; no such environment has been established here. This
document does not authorize installing a toolchain or changing global settings.

Confirm all of the following through host-visible configuration or trustworthy
request/session metadata, not the model's self-report:

1. No author AGENTS.md, project plan, scoring key, previous output, personal
   memory or unrelated skill bodies enter the session. No access to the author
   development checkout or its ignored answer records.
2. A sees no method. B sees only the unchanged baseline. C sees only the frozen
   Prior-Scout method. Supplied method text tests explicit use, not discovery.
3. Fix one host/version, requested model `gpt-6.1-sol`, reasoning `high`, tool
   catalog and common limits before the first run. Record the actual resolved
   values. If the selected model is unavailable, stop rather than substituting.
4. P1 is offline with the complete two supplied documents. P2 has working live
   search and page reading. B requires native parallel Agent dispatch; if absent,
   decide N/A before execution and preserve that reason. Use equivalent tools
   in A/C, including any dispatch capability, and aggregate child costs/traces.
5. Preserve ordinary sandbox/approval controls. Never use the M1 cache-removal
   option, cache cleanup, a global install, or a home-directory override.

If any condition is unverified, keep the cell NOT RUN. Do not paste a packet into
an ordinary author chat and label the outcome an independent benchmark. A
separately identified contaminated smoke observation would not satisfy this gate.

## Packet handling

The ignored local handoff has these files under `.local/m2/packets/`:

```text
M2-P1-A-01.txt
M2-P1-C-01.txt
M2-P2-A-01.txt
M2-P2-B-01.txt
M2-P2-C-01.txt
```

`.local/m2/registry.json` records packet/method hashes, planned order, source
conditions and NOT RUN states. The packets are self-contained: P1 contains the
complete public source files; B/C contain the unmodified applicable method.
They contain no private absolute paths, author plan, rubric or prior answers.
No packet was generated for the predeclared N/A cell.

Keep this operator guide, registry reasons, protocol and rubric outside executor
context. After the isolation gate passes, copy only the chosen input packet into
one fresh session. Start the timer at submission, retain the full answer and
visible tool trace, and end the session before another cell. Do not add hints
after observing an answer. Follow the order in [the protocol](pilots-m2.md).

## Capture and scoring

Use the [M2 rubric](pilots-m2-rubric.md) only in a separate scoring context after
capturing the original output. Raw exports and private settings stay ignored;
review and sanitize public run records before adding them under `evals/runs/`.
Use the record fields from [evals/README.md](README.md). Missing tools/metrics
remain unavailable; do not backfill them from memory.

M1 already uses one of twelve attempts. M2 has used zero model attempts. The
five proposed runs would bring the cumulative total to six if all are feasible;
update the ledger immediately for each actual submission, including failures.
Do not run the reserved set or other development cases as part of this handoff.

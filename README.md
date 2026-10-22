[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**Find what already exists. Verify before you claim.**

Prior-Scout (先例探索) is a small, instruction-only Agent Skill. Give it a need,
URL, or readable document; it finds publicly documented tools, services, skills,
libraries or research implementations, then briefly explains supported overlap
and important differences. It gives a repeatable, bounded workflow for a quick
existing-work check before you continue your original task.

**Status: `0.1.1-experimental`, local release candidate.** No public repository
or release has been verified. Evidence includes real source-reading smoke tasks
and a 14-case fresh-context subagent audit, with limitations below. This is
focused workflow packaging, not a demonstrated accuracy advantage over a good
ordinary Codex prompt or another Skill.

English is the primary maintenance version. Translations preserve its technical
claims and limitations.

## What it does

- Search by purpose, functionality, method and useful synonyms.
- Read reliable sources; separate a real source from a source-supported claim.
- Distinguish hosted products, installable apps, skills, SDKs, papers and demos.
- Attribute capabilities to the correct deliverable, version or service tier.
- Preserve supported facts, qualify unknowns, and stop within a small budget.
- Return to the user's other already-authorized work after the comparison.

It does not decide novelty, legal status, research value, commercial viability
or what you should adopt. It does not propose improvements, run candidates or
start follow-up research automatically. Reverse image search, song recognition,
file deduplication and exhaustive literature reviews are outside its scope.

## Host requirements

The host must load Agent Skills and provide search and source-reading tools.
Documents must already be readable. Prior-Scout includes no search engine,
parser, runtime dependency, account, paid API integration or telemetry. When
sources or tools are unavailable, it should disclose the limit rather than
invent verification.

## Install locally

The reviewed [Skills CLI](https://github.com/vercel-labs/skills) 1.7.4 requires
Node.js 22.20 or later. From a new target project, use the local candidate
checkout. This example assumes sibling directories; adjust the relative path:

```sh
npx skills@1.7.4 add ../Prior-Scout-Public-Prep --list
npx skills@1.7.4 add ../Prior-Scout-Public-Prep --skill prior-scout -a codex --copy -y
npx skills@1.7.4 list -a codex
```

Check for a same-name project installation before copying. Project scope is the
default; do not add a global flag for this procedure. The target is
`.agents/skills/prior-scout/`. Only `skills/prior-scout/` is installed; the
bundled LICENSE travels with it. Core instructions have a single source.

M4 verified local discovery, project installation and byte equality with the
existing official CLI entrypoint; a fresh Codex session was not tested.
The [installation record](evals/runs/install-m4-20261022.md) distinguishes actual
local CLI-entrypoint checks from npx launcher behavior, host loading and remote
installation. Do not infer one from another. In a new Codex conversation, verify
the installed entry appears, request `$prior-scout`, and inspect the actual
instruction acquisition and source reads. Restart the host if its list is stale.
An instruction read is not separate structured loader telemetry.

## Future GitHub installation — NOT TESTED

The planned GitHub source is `orange-clockwork/prior-scout`. The repository has
not yet been created or published; remote installation is **NOT TESTED**. These
commands are intended for use **after public release**, not for a working source now:

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --list
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
```

Confirm the actual account and public repository before using these commands.
Local installation does not establish remote installation, skills.sh listing,
`skills find` visibility, find-skills recommendation or automatic host selection.
See the [publication checklist](docs/release-checklist.md).

## Use it

Explicit invocation (recommended for this experimental version):

> Use $prior-scout to find existing open-source tools for checking broken links,
> missing attachments and duplicate filenames in a Markdown knowledge base.
> Read reliable sources and explain verified similarities and material limits.

Natural request, when the host chooses the Skill:

> Are there existing tools or research implementations similar to this proposal?
> Find a few supported matches and explain important differences.

It may also fit new planning that needs external comparison. It should not start
research for ordinary bug fixes, formatting, summaries, translation, refactoring
or settled implementation. A request to use only supplied material takes priority.
Results follow the user's language. These input examples are illustrative, not
claims that an automatic trigger succeeded.

## Actual examples and evidence

- [Software capability attribution](evals/runs/evidence-regression-ef02-r1-20261022.md):
  a pinned package FAQ rejects built-in collaboration while allowing host-side
  implementation through APIs. The earlier failed attempt is retained.
- [Research systems](evals/runs/release-audit-20261022.md#q3): pedestrian navigation
  methods, original studies and app availability are kept distinct.
- [Consumer workflow](evals/runs/release-audit-20261022.md#q6): pasted whole-recipe
  parsing is separated from accepting structured ingredient fields.

These are documented outputs, not polished replacements or candidate runtime
tests. Full input, output, source and limitation records are linked in
[examples](docs/examples.md) and [results](evals/results.md).

## Evidence-first limits

Default limits are six query strings and eight distinct external evidence
documents, usually yielding three to five candidates. These are instructions,
not software-enforced guarantees. Snippets are leads; important claims need
successful source reading and direct support. Planned features and integration
APIs are not completed workflows. Partial similarity is not complete replacement;
no match in one search does not prove nonexistence.

The pre-answer check corrects, qualifies or removes unsupported claims. It does
not force two sources per candidate, a numerical score or a verbose checklist.
It cannot guarantee exhaustive retrieval or eliminate model hallucination.

## Testing and results

The release audit completed 14 bounded cases: eight quality tasks and six
selection controls. Review found no material unsupported/fabricated claim in
that sample; this is not an accuracy rate. It used fresh child contexts with
shared host instructions and no fully captured initial model prompt. Positive
file-use observations do not prove top-level native automatic selection;
structured loading remains inconclusive. Independent A/B/C, held-out evaluation,
cross-host reliability, the discovered candidates' runtime correctness, exact
cost and a quality advantage over ordinary prompts remain unverified.

## Existing workflows and positioning

Existing workflows already search and verify. Prior-Scout's proposed distinction
is a short, focused comparison and stopping point, without adoption or business
verdicts. See the [document comparison](docs/comparison.md).

## License and development

MIT License. Copyright (c) 2026 orange-clockwork. See [LICENSE](LICENSE);
[the installable copy](skills/prior-scout/LICENSE) carries the same notice.
Third-party names and linked sources retain their owners' rights; full upstream
source snapshots are not distributed here.

The core is [SKILL.md](skills/prior-scout/SKILL.md). See [AGENTS.md](AGENTS.md) for
contributor constraints and [evaluation notes](evals/README.md) for method limits.
This candidate excludes the development Git history and private raw evidence.
[Release preparation](docs/release-preparation.md) records the reviewed file tree,
checks and remaining gates. No commit, remote action or publication is implied.

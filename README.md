[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**Find what already exists. Verify before you claim.**

Prior-Scout (先例探索) is a small, instruction-only Agent Skill. Give it a need,
URL, or readable document; it finds publicly documented tools, services, skills,
libraries or research implementations, then briefly explains supported overlap
and important differences. It gives a repeatable, bounded workflow for a quick
existing-work check before you continue your original task.

**Status: `0.1.1-experimental`, publicly available on GitHub.** Anonymous access
and project-scoped installation from the public source were verified on 2026-10-22.
Evidence includes real source-reading smoke tasks
and a 14-case fresh-context subagent audit, with limitations below. This is
focused workflow packaging, not a demonstrated accuracy advantage over a good
ordinary Codex prompt or another Skill.

English is the primary maintenance version. Translations preserve its technical
claims and limitations.

## Install from GitHub

Use the public [orange-clockwork/prior-scout](https://github.com/orange-clockwork/prior-scout)
repository. [Skills CLI](https://github.com/vercel-labs/skills) 1.7.4 requires
Node.js 22.20 or later. Run these commands from your target project:

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --list
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex
```

For an explicit, non-interactive copy installation:

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
npx skills@1.7.4 list -a codex
```

Check for a same-name project installation before installing. Choose project
scope if prompted; do not add `-g`. The target is `.agents/skills/prior-scout/`.
Only `skills/prior-scout/` is installed, including its MIT LICENSE.

**PASS — public source installation:** both installation commands were tested with npx and
Skills CLI 1.7.4 in separate new temporary projects. Discovery found exactly one
Skill; installed SKILL.md and LICENSE matched the public version byte for byte.
The CLI detected the Codex environment and used project scope with copy mode.
The interactive prompts in other environments were not separately tested.
See the [release verification](docs/release-checklist.md#public-release-verification-2026-10-22).
The [M4 installation record](evals/runs/install-m4-20261022.md) remains a historical
record of local-source checks.

**NOT TESTED — a fresh native Codex session using this public installation.**
A safe launch that preserves the existing system Skill cache was not established.
To check manually, open the installed project in a new Codex conversation, select
the project-scoped `prior-scout` entry, and submit the explicit example below.
Verify the selected path, actual instruction acquisition, search and source reads.
A manual file read alone is not structured native-loading evidence.

At release verification, the skills.sh page showed a not-available/404 message,
and `skills find prior-scout` returned no result. find-skills recommendation and
automatic selection across hosts remain unverified; indexing is separate from
direct GitHub installation and is not guaranteed.

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
This public repository excludes the development Git history and private raw evidence.
[Release preparation](docs/release-preparation.md) preserves the historical M4 snapshot;
the [publication checklist](docs/release-checklist.md) records current release verification.

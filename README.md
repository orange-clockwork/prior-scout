[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**Find what already exists. Verify before you claim.**

Prior-Scout (先例探索) is a small, instruction-only Agent Skill for checking existing
solutions before you build. Give it a need, URL or readable document; it searches
public sources, verifies relevant capabilities, and briefly compares tools,
services, skills, libraries or research implementations.

**`0.1.1-experimental` · Public on GitHub · MIT**

## See it in action

A real task from the 2026-10-22 audit, using `0.1.1-experimental`:

> Before implementing a Markdown link checker, first find existing open-source solutions and explain their relevant differences. Then write a short implementation outline for my original checker. Do not change files.

**Result summary** — shortened from the recorded answer:

| Candidate | What the sources supported | Difference that matters |
| --- | --- | --- |
| [Lychee](https://github.com/lycheeverse/lychee) — CLI / library | Checks Markdown, HTML and website links. | Anchor checks require `--include-fragments`; JavaScript-generated anchors cannot be checked. [Docs](https://lychee.cli.rs/recipes/anchors/) |
| [markdown-link-check](https://github.com/tcort/markdown-link-check) — Node.js CLI / library | Checks link availability; offers HTTP settings and retries. | Cross-file heading validation was **not established** by the README reviewed. |
| [remark-validate-links](https://github.com/remarkjs/remark-validate-links) — remark plugin | Checks local files, images and headings offline. | **Cross-file heading checks work through the remark CLI, not the Node API.** External URLs are outside its scope. |

The useful distinction is which capabilities are documented, which usage mode
provides them, and what remains unconfirmed. The answer then returned to the
requested implementation outline.

This historical subagent task used **2 queries and 4 external evidence documents**.
No candidate tool was installed or executed. These are documentation findings,
not accuracy measurements or proof of native automatic selection.
[Full example, sources and limits](docs/examples.md#t2-markdown-link-checker).

## Install & Usage

Requires Node.js 22.20+ for [Skills CLI](https://github.com/vercel-labs/skills) 1.7.4,
and a host that can load Agent Skills, search and read sources. Run in your target project:

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex
```

Check for an existing same-name Skill first. Choose project scope if prompted;
do not add `-g`. The install target is `.agents/skills/prior-scout/`, including
SKILL.md and MIT LICENSE.

Open a new Codex conversation in that project and explicitly request the Skill.
This is an illustrative invocation, separate from the historical Demo input:

> Use $prior-scout to find existing open-source Markdown link checkers.
> Read reliable sources and briefly explain verified similarities and important differences.

<details>
<summary>Discovery and explicit copy installation</summary>

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --list
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
npx skills@1.7.4 list -a codex
```

Use the copy command as an alternative to the main install command, after checking
that the target project has no same-name installation.

</details>

## How it works

1. Identify the need, relevant similarities and hard constraints.
2. Search within a small budget: normally up to **6 queries and 8 external evidence documents**.
3. Read reliable sources. Check the deliverable, version, service tier or usage mode behind each claim.
4. Return a short comparison with supported overlap, material differences and unknowns; then resume any other authorized work.

Search snippets are leads. APIs, planned features and partial matches do not
establish a complete built-in workflow. The budget is an instruction, not a
software-enforced limit. Search and source-reading tools come from the host;
Prior-Scout adds no runtime dependency or telemetry. Unavailable evidence should
be disclosed, and a supplied-material-only restriction takes priority.

Use it for explicit alternatives or related-work requests and new planning that
needs comparison. Routine fixes, translation and settled implementation do not
call for a new search. It does not make adoption, novelty, legal or business
verdicts, run candidates, or begin unsolicited follow-up research. See [scope](docs/scope.md).

## Evidence & limitations

- **Public installation verified:** the main and copy commands were tested in separate fresh projects. Installed core and LICENSE bytes matched the public source. [Release checks](docs/release-checklist.md#public-release-verification-2026-10-22)
- **14-case audit:** eight quality tasks and six selection controls, using fresh child contexts with shared host instructions. It was not a fully independent blind test; the full initial prompt and structured loader events were not captured. [Results](evals/results.md)
- **Host observations are separate:** a fresh Codex session remained NOT TESTED in the Mac release run. A later Windows installation/use observation is user-reported; raw Windows traces are not retained in this repository. [Windows summary and limits](docs/examples.md#windows-user-reported-observation)

These observations do not establish an accuracy rate, exhaustive retrieval,
elimination of hallucinations, or an advantage over a good ordinary Codex prompt
or another Skill. Independent A/B/C and held-out evaluation, candidate runtime
correctness, exact cost and reliable automatic selection across hosts remain
unverified. Direct installation also does not guarantee skills.sh indexing,
`skills find` visibility or find-skills recommendation.

## Further reading & license

[More examples and original records](docs/examples.md) · [Existing workflows](docs/comparison.md) ·
[Evaluation method](evals/README.md) · [Historical M4 preparation](docs/release-preparation.md)

English is the primary maintenance version; translations preserve the same claims
and limits. Core instructions live in [SKILL.md](skills/prior-scout/SKILL.md);
[AGENTS.md](AGENTS.md) describes contributor constraints. Private raw evidence and
the original development Git history are excluded from this public repository.

MIT License. Copyright (c) 2026 orange-clockwork. The [root LICENSE](LICENSE) and
[installable copy](skills/prior-scout/LICENSE) contain the same notice. Third-party
names and linked material retain their owners' rights; upstream source corpora
are not distributed here.

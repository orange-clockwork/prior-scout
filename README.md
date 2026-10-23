[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**Find what already exists. Verify before you claim.**

Prior-Scout (先例探索) is a small, instruction-only Agent Skill for checking existing
solutions before you build. Give it a need, URL or readable document; it searches
public sources, verifies relevant capabilities, and briefly compares tools,
services, skills, libraries or research implementations.

**`0.2.0-experimental` · Experimental · MIT**

## See it in action

These are summaries of **user-reported Prior-Scout sessions**, with primary sources
checked separately for this documentation update. Their exact prompts and raw traces
are not archived here. They are not transcripts or independent performance tests.

### Demo 01 — Can Prior-Scout Find Its Own Competitors?

After developing Prior-Scout, its author asked it to investigate similar workflows.
Three representative matches:

- **[search-first](https://github.com/affaan-m/ECC/blob/main/skills/search-first/SKILL.md):** closely overlaps with research before coding; continues into adopt/extend/build decisions and implementation.
- **[priorart](https://github.com/duthaho/skillhub/blob/main/.claude/skills/priorart/SKILL.md):** closely overlaps with checking existing ideas; requires evidence locators, a bounded search and a build/fork/use-style verdict.
- **[find-skills](https://github.com/vercel-labs/skills/blob/main/skills/find-skills/SKILL.md):** partial overlap; discovers installable Skills and offers installation, rather than a broader related-work comparison.

**Real overlap, not manufactured originality.** Prior-Scout stops at a brief,
evidence-backed comparison and returns to authorized work; that is a scope choice,
not proven superiority. This retrospective check does not establish what was checked
before development. [All five candidates, reported budget and source checks](docs/examples.md#demo-01-agent-skill-discovery).

### Demo 02 — Finding Related Research for a Pedestrian Navigation Study

The author's proposed master's study compares full-route, direction-and-distance,
and destination-only guidance. Three reported matches illustrate why related topics
need a closer methodological comparison:

- **[Robinson et al. (2012)](https://cronfa.swansea.ac.uk/Record/cronfa17385/Download/0017385-18012016145442.pdf) — full text:** directional haptics and route choice; not a comparison of the proposed three conditions.
- **[Sugimoto et al. (2022)](https://ist.ksc.kwansei.ac.jp/~nagata/data/sugimoto_2021_spat_cogn_comput.pdf) — full text:** smartphone versus paper maps and spatial memory; media differences do not isolate information quantity.
- **[Heller et al. (2020)](https://www.krisluyten.net/publications/dblp_conf_mhci_helleral20/) — abstract only:** audio guidance, efficiency and workload; detailed measures remain unverified here.

**Similar topics do not mean equivalent conditions or measures.** This is a research
proposal, not a published result or a novelty verdict. The
[detailed comparison](docs/examples.md#demo-02-pedestrian-navigation-research) separates
the original observations from an additional editorial check of Ishikawa & Takahashi (2014).

The earlier [Markdown link-checker T2 demo](docs/examples.md#t2-markdown-link-checker)
remains available with its archived audit record.

## Install & Usage

These commands install public GitHub `main`, which can move after this release.
Installation evidence below is version-specific; the historical M1.3 review
predates publication and does not establish a `0.2.0-experimental` installation pass.

Requires Node.js 22.20+ for [Skills CLI](https://github.com/vercel-labs/skills) 1.7.4,
and a host that can load Agent Skills, search and read sources. Run in your target project:

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex
```

Check for an existing same-name Skill first. Choose project scope if prompted;
do not add `-g`. The install target is `.agents/skills/prior-scout/`, including
SKILL.md and MIT LICENSE.

Open a new Codex conversation in that project and explicitly request the Skill.
This is an illustrative invocation, not an original prompt from either Demo:

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

- **Experimental M1 security baseline:** adds source URL provenance guidance, supported by a bounded security baseline, eight original/candidate runs and four final positive controls. The plain formatting control produced no tool calls; native selection remains INCONCLUSIVE. This does not establish complete prompt-injection protection or a measured error-rate reduction. Claude Code, Cursor and Gemini CLI compatibility is **NOT TESTED**. [Candidate review](docs/release-checklist.md#m13-release-candidate-review--2026-10-23)

- **0.1.1 public installation verified:** the main and copy commands were tested in separate fresh projects. Installed core and LICENSE bytes matched the public source. [Release checks](docs/release-checklist.md#public-release-verification-2026-10-22)
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

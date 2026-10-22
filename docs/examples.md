# Actual examples and demo status

The two homepage demos summarize **user-provided observations from earlier
Prior-Scout sessions**. Their exact prompts, complete outputs and raw source-read
traces were not found in this Mac release checkout, including its ignored local
release records. The scenarios below paraphrase the owner's account; they are
not reconstructed transcripts. No session dates or run IDs are assigned to them.

The checked-in [Q3](../evals/runs/release-audit-20261022.md#q3) and
[Q4](../evals/runs/release-audit-20261022.md#q4) records cover related topics, but
have different candidate sets, prompts and budgets. They are separate runs, not
the missing evidence for these demos. T2 below has its own archived audit record.

Primary-source checks dated **2026-10-22** support the descriptions below, not
attribution of the original searches to Prior-Scout. They are editorial verification,
not a new Skill evaluation or part of either original search budget. No candidate
was installed or run, and no study was replicated. Source documents were read as
evidence, not executed as instructions; their full contents are not redistributed.

## Demo 01: Agent Skill discovery

### Scenario and reported observation

After developing Prior-Scout, the author used it to look for similar ways to
investigate tools, software, Skills and research before starting new work. The
intended workflow reads original documents, checks capabilities, distinguishes
direct and partial overlap, reports unknowns, limits the search, and returns to
the authorized task without making product or business decisions.

The owner reports **6 search queries, 7 distinct primary-document read targets,
6 successful reads, and 1 unsuccessful read excluded from verified findings**.
No candidate installation or runtime test was reported. Exact query strings,
the full target ledger and the failed target's identity were not supplied; these
counts cannot be independently reconstructed here. In particular, the five
candidates below do not identify all seven historical document targets.

### What the original documents support

All five reported candidates have readable original documentation. Links in this
table pin the revisions checked for this update; they do not establish which
revisions the earlier user-run session read. Overlap labels are a scope comparison,
not an accuracy ranking or a recommendation to adopt a candidate.

| Reported candidate | Documented overlap and evidence requirements | Downstream decision and stopping behavior |
| --- | --- | --- |
| **[ECC search-first](https://github.com/affaan-m/ECC/blob/90606c8315ee09cafc303515c5f33024db6b9882/skills/search-first/SKILL.md)** — close overlap | Research before coding across registries, MCP, Skills and GitHub; evaluates functionality, maintenance, documentation, licensing and dependencies. | Adopt, extend, compose or build, followed by implementation. Its documented end point exceeds a short similarity briefing. |
| **[duthaho priorart](https://github.com/duthaho/skillhub/blob/b98f0980641f08565c5ef5c532b7f5525e498372/.claude/skills/priorart/SKILL.md)** — close overlap | Reframes ideas across communities, searches builder venues, follows dependency leads and requires fetched evidence locators or an explicit unknown. Caps the whole check at 10 queries. | Requires one build/fork/contribute/use/investigate verdict and saves a brief and check log. It is advisory; the human decides what gets built. |
| **[ECC skill-scout](https://github.com/affaan-m/ECC/blob/90606c8315ee09cafc303515c5f33024db6b9882/skills/skill-scout/SKILL.md)** — partial overlap | Searches existing Skills; reads candidate instructions and checks consequential commands, writes, network access, credentials and installs. Its web-search step allows at most 3 targeted queries. | Presents use, extend or create options. Its scope is Skills, with creation contingent on the user's choice or lack of a close match. |
| **[Vercel find-skills](https://github.com/vercel-labs/skills/blob/a80e4c9d12d607631249d4d7d059f835d4b2f13a/skills/find-skills/SKILL.md)** — partial overlap | Discovers installable Skills using the leaderboard and keyword search; prescribed checks emphasize install counts, source reputation and repository stars. | Returns candidates and installation commands, and offers installation. Popularity/provenance checks are not a measured guarantee of capability or quality. |
| **[HKUDS AI-Researcher](https://github.com/HKUDS/AI-Researcher/blob/f9a6f8480860c193afff600eeffe3defcee8a978/README.md)** — related, broader system | Its README describes literature review, algorithm design and implementation, experimental analysis and manuscript creation. | A research system with setup and execution requirements, not a small instruction-only similarity Skill. These are documented aims, not independently verified performance. |

**Takeaway:** real alternatives already cover much of the intended purpose.
Prior-Scout's bounded comparison and handoff are a scope choice, not proof of
being first, having no direct competitors, or outperforming alternatives. This
retrospective demonstration does not show that the check preceded its creation.
It also does not establish the original run's loading mechanism or automatic selection.

## Demo 02: Pedestrian navigation research

### Proposed study and reported observation

The owner supplied the master's proposal title **Effects of Navigation Information
Levels on Pedestrian Wayfinding and Exploratory Behavior**. It proposes comparing
full route guidance, direction-and-distance guidance, and destination-only guidance.
Interests include environmental noticing and attention, scene recognition and
environmental memory, exploration and unexpected discoveries, navigation efficiency,
and subjective workload. These are proposed conditions and interests, not published
findings or a finalized measurement protocol.

The reported session found Robinson, Sugimoto and Heller below. The owner describes
full-text access for the first two and abstract-only verification for Heller.
Original query/read counts were not supplied. The source checks below were performed
separately; they do not recreate the missing original input or trace.

### Three reported matches: sources and limits

- **Robinson, S., Jones, M., Williamson, J., Murray-Smith, R., Eslambolchilar, P., & Lindborg, M. (2012).** *Navigation Your Way: From Spontaneous Independent Exploration to Dynamic Social Journeys*. Personal and Ubiquitous Computing, 16(8), 973–985. DOI: `10.1007/s00779-011-0457-2`. [Institutional full text](https://cronfa.swansea.ac.uk/Record/cronfa17385/Download/0017385-18012016145442.pdf).
  **Checked:** Section 4 compares static and dynamic directional haptics in a 24-person field trial, including path variation, time and distance. It has no turn-by-turn control and does not test the proposal's three conditions. Route variation alone does not establish unexpected discovery.
- **Sugimoto, M., Kusumi, T., Nagata, N., & Ishikawa, T. (2022).** *Online mobile map effect: how smartphone map use impairs spatial memory*. Spatial Cognition & Computation, 22(1–2), 161–183. DOI: `10.1080/13875868.2021.1969401`. [Author-hosted full text](https://ist.ksc.kwansei.ac.jp/~nagata/data/sugimoto_2021_spat_cogn_comput.pdf).
  **Checked:** Sections 2.4–2.5 compare smartphone and paper maps, with unaided route retracing, scene recognition and landmark recall. Both maps show routes; automatic turn-by-turn functions were disallowed. Media, scale and interaction differ, so this does not isolate information quantity. The issue year is 2022; online publication was 29 August 2021, explaining the filename/year difference.
- **Heller, F., Adamczyk, J., & Luyten, K. (2020).** *Attracktion: Field Evaluation of Multi-Track Audio as Unobtrusive Cues for Pedestrian Navigation*. MobileHCI '20, Article 21, 1–7. DOI: `10.1145/3379503.3403546`. [Author publication page and abstract](https://www.krisluyten.net/publications/dblp_conf_mhci_helleral20/).
  **Checked at abstract level only:** spatial audio is compared with spoken turn-by-turn guidance; the abstract discusses path efficiency, errors, mental workload and users' appreciation of serendipity. Detailed instruments, procedures and statistical tests were not verified here. No equivalence or measured-discovery claim is inferred. The linked full paper was not used to upgrade this evidence level.

### Supplementary editorial check: Ishikawa & Takahashi

**This paper was requested for this update, not reported as found in the original
bounded session.**

**Ishikawa, T., & Takahashi, K. (2014).** *Relationships between Methods for Presenting
Information on Navigation Tools and Users' Wayfinding Behavior*. Cartographic
Perspectives, (75), 17–28. DOI: `10.14714/CP75.82`.
The [journal record](https://cartographicperspectives.org/index.php/journal/article/view/cp75-ishikawa-takahashi)
dates publication to **27 May 2014** and recommends 2014 in citations, although
issue 75 is labelled **2013**. We follow that citation guidance and preserve the distinction.

The [journal's accessible full text](https://cartographicperspectives.org/index.php/journal/article/download/cp75-ishikawa-takahashi/html)
supports a more direct comparison of navigation presentation:

- **Experiment 1:** 24 participants used a route tool, direction tool and paper map in a counterbalanced repeated-measures design. Measures included distance, speed, scene recognition, reported tool-viewing time and route similarity. Direction guidance retained a local map; the paper map showed the area and endpoints, so neither is simply the proposal's destination-only condition.
- **Experiment 2:** a different 24 participants used modified tools with whole-area map access and a small device-screen map. It investigated display-size effects as well as presentation.
- **Relevant result:** paper-map scene recognition exceeded the route-tool condition in Experiment 1; direction-tool routes were more varied than route-tool routes. This is relevant prior work, not an exact replication of the proposed conditions or proof of its novelty. Nonsignificance is not an equivalence test.

### Interpretation boundaries

These are methodological cautions, not new findings from the proposed thesis:

- Information amount and presentation modality are different dimensions.
- Scene recognition measures memory, not moment-to-moment environmental attention.
- Route-choice variation is not automatically serendipity or meaningful discovery.
- Nonsignificant differences do not by themselves establish equivalence.
- Finding relevant papers does not establish a study's novelty or superiority.

No research method or outcome was independently replicated. The two full-text
sources, Heller's abstract page, and Ishikawa's journal record/full text were
accessible during this editorial check; Heller's detailed methods remain outside
its evidence scope, not asserted to be unavailable.

## T2 Markdown link checker

Run ID: **RA-20261022-T2-01**. Date: **2026-10-22**.
Skill: **0.1.1-experimental**, core SHA-256:
`23b75a97c384a4fea12567bbe67fc6c3f77b9d3bf6fcb8332e946cc416b62033`.
See the [complete T2 record](../evals/runs/release-audit-20261022.md#t2).
This presentation adds no new behavior test and does not replace the original output.

### Original input

The exact original task was in English and did not name the Skill:

```text
Before implementing a Markdown link checker, first find existing open-source solutions and explain their relevant differences. Then write a short implementation outline for my original checker. Do not change files.
```

The explicit Markdown-checker prompts in the README installation sections are
illustrative usage examples, not the original task above or a reconstruction of
what triggered this historical run.

### Short result and claim checks

The table is an editorial summary of the recorded answer, not a new model output.
All three candidates are partial reference points for the requested checker.

| Candidate / delivery | Verified overlap | Condition or unconfirmed capability | Original source |
| --- | --- | --- | --- |
| Lychee — Rust CLI, library and GitHub Action | Checks Markdown, HTML and websites, including heading/custom-ID fragments when enabled. | `--include-fragments` is opt-in; JavaScript-generated anchors cannot be checked. | [Repository README](https://github.com/lycheeverse/lychee) and [official anchor documentation](https://lychee.cli.rs/recipes/anchors/) |
| markdown-link-check — Node.js CLI and callback library | Extracts links and checks availability; documents timeouts, headers, ignore/replacement patterns, accepted status codes and HTTP 429 retries. | Cross-file heading validation was not established by the README reviewed. This is an evidence limit, not a claim that the capability cannot exist. | [Repository README](https://github.com/tcort/markdown-link-check) |
| remark-validate-links — remark plugin | Checks local files, images and headings offline. | Cross-file heading validation requires the remark CLI; the Node API does not provide it. External URLs and undefined reference labels are outside the plugin's scope. | [Repository README](https://github.com/remarkjs/remark-validate-links), especially its Use/API sections |

A short verbatim excerpt from the actual T2 answer:

> Cross-file heading validation requires the remark CLI; the Node API does not provide it.

This is the key verification step: the documented feature belongs to a specific
usage mode. Describing the package as supporting cross-file heading checks without
that distinction would hide a condition relevant to someone building with its API.

### Returning to the authorized task

After the comparison, the actual answer returned to the requested implementation
outline. It covered five steps: define the Markdown/path contract, parse links
structurally, validate local targets and headings, add optional HTTP validation,
and report diagnostics with tests. These were proposed steps, not completed work.
No checker or candidate tool was implemented, installed or executed.
The [full answer](../evals/runs/release-audit-20261022.md#t2) retains the complete outline.

### Search and source record

The original run used **2 search queries and 4 external evidence documents**:

1. `open source Markdown link checker CLI external links relative files anchors lychee markdown-link-check`
2. `remark validate links Markdown local headings references plugin open source`

The four documents were the three repository READMEs and Lychee's anchor guide,
linked in the table above. All four were read successfully. The ledger records
**3 web calls, 7 external read attempts, 0 failures and 0 retries**; query count
and read count are different measures.

Sources were moving branch documentation (Lychee and markdown-link-check: master;
remark-validate-links: main) and an unversioned anchor guide. The remark README
referenced major 13; no installed candidate release was verified. These links
provide source access, not a frozen snapshot of the pages as read at that time.
The complete historical source/version and acquisition ledger remains in T2.

### What this observation establishes

A complete catalog-origin Skill body read was observed, with the frozen core hash.
The answer compared documented capabilities and returned to the authorized outline.
The historical review marked that file use as PASS and native automatic triggering
as **INCONCLUSIVE**; no separate structured loader event was captured.

This was one fresh-context subagent task in a shared host, not a standalone native
session or an independent blind comparison. Host instructions were shared and the
complete initial injected prompt was not captured. The case establishes neither
candidate runtime correctness, an accuracy/recall rate, nor an advantage over an
ordinary prompt or another Skill. Time, tokens and monetary cost were NOT MEASURED.

## Other recorded examples

| Example | Actual evidence | Important limit |
|---|---|---|
| Excalidraw package collaboration | [EF-02-R1](../evals/runs/evidence-regression-ef02-r1-20261022.md): read the pinned FAQ, rejected built-in collaboration, retained APIs for host implementation. | Same-conversation self-review; [original access failures](../evals/runs/evidence-regression-20261022.md) remain NOT RUN for that condition. |
| Research-system similarities | [RA Q3](../evals/runs/release-audit-20261022.md#q3): source-supported guidance methods and evaluation limits; one abstract-only result labelled. | Fresh-context subagent, shared host; no research replication or installation. |
| Recipe-to-shopping-list workflow | [RA Q6](../evals/runs/release-audit-20261022.md#q6): whole-text extraction versus structured fields, servings and list merging. | Documented functions, moving sources; no hands-on extraction-accuracy test. |

Earlier [manual-use smoke observations](../evals/runs/smoke-20261021.md) and
[explicit-use observation](../evals/runs/native-20261022.md) used 0.1.0. They are
historical evidence, not proof of native loading or independent quality for
0.1.1. The current audit reports instrumented file use and native-loader limits.

The planned independent A/B pilots remain NOT RUN. No comparative advantage is claimed from these demonstrations. See
[results](../evals/results.md) for failures, versions, context and judgments,
and the [M4 packaging record](../evals/runs/install-m4-20261022.md) for installation.

## Windows user-reported observation

Evidence source: a later test summary supplied by the project owner during README
preparation. The Mac release checkout does not retain the original Windows
execution logs. This is not an independently reviewed run or part of the T2 Demo.

The owner reports testing on a Windows computer without a prior Prior-Scout install:

- Discovery from the public GitHub source and installation into a separate project succeeded.
- The raw SKILL.md hash differed because of CRLF line endings; after normalization to LF, its SHA-256 matched the published core. This is normalized-text equality, not original byte equality.
- In a natural-language task without explicitly naming the Skill, Codex announced use of prior-scout, read the full SKILL.md, searched and checked original sources.
- The reported search and document counts stayed within the Skill budget; exact counts and raw tool records are not available here.
- Hidden host Skill Router events were not obtained. The report supports a user-observed selection/use event, not verified internal routing or a cross-host reliability rate.

The historical [M4 installation record](../evals/runs/install-m4-20261022.md) and
[Mac public-release checks](release-checklist.md#public-release-verification-2026-10-22)
retain their original NOT TESTED boundaries for fresh native sessions. This later
report does not retroactively turn those checks into passes.

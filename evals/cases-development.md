# Development cases — exposed to the developer

These are not held-out cases. The two pilots are D-Q03 and D-Q01.
Complete raw sources are local, identified by [source-manifest.json](source-manifest.json).
They are not redistributed as an evaluation corpus.

## D-Q03 — fixed-source attribution pilot

Prompt:

> Using only the supplied complete Excalidraw README and package FAQ, assess
> whether the React editor package meets this need: an embeddable hand-drawn
> whiteboard with PNG/SVG export and ready-to-use real-time collaboration.
> Distinguish the package, the hosted website, and functionality the host
> application would have to implement. Cite the document and section.

Input: README and FAQ at Excalidraw commit
`6f0a4d19b577e781ee5491d6cb89799b3fba7ee8`; no browsing or additional sources.
A/B/C receive identical complete bytes; no highlighted excerpts or answer key.
B is the pinned research:prior-art, subject to host equivalence checks.

Four predeclared judgments:

1. Editor/package offers a hand-drawn canvas and can be integrated into a React
   application (README Features and Quick start).
2. Package has PNG/SVG export (README Features).
3. Real-time collaboration is listed for Excalidraw.com, not as a built-in
   package capability (README website section and FAQ collaboration question).
4. FAQ exposes APIs for the application to implement collaboration: neither
   ready-to-use collaboration nor an assertion that collaboration is impossible.

No search-retrieval score. Do not install the editor or change browser settings
mentioned by the FAQ. This tests evidence reading only.

## D-Q01 — live search pilot

Prompt:

> Find existing public tools that help a coding agent discover and install
> reusable agent skills. Search the web and read first-hand sources. Return a
> few relevant results and distinguish a skill, a CLI, and a discovery website.
> Explain verified overlap and important conditions. Do not install anything.

Reference answer evidence: Vercel Labs find-skills SKILL.md, Skills CLI README
and commands, at commit `a80e4c9d12d607631249d4d7d059f835d4b2f13a`, plus
skills.sh FAQ. Executors search live and are not given those names or sources.
The known answer informs scoring only. Budget: six queries/eight documents.
B: research:prior-art. evaluate-existing-solutions is N/A by its stated scope.

Four judgments:

1. Recover find-skills or an equivalently evidenced skill-discovery workflow.
2. Read the actual instructions for any skill described as verified; summaries
   alone do not establish the skill's workflow.
3. Attribute installation to the CLI and discovery guidance to the skill; a
   website listing is not itself an installed executable skill.
4. Cite primary support, mark partial matches and unverified discovery behavior;
   do not claim guaranteed recommendation, indexing, or universal compatibility.

## Remaining development coverage

| ID | Exact task/input | Predeclared checks | Status before execution |
|---|---|---|---|
| D-Q02 | `https://excalidraw.com`: find public hand-drawn whiteboard alternatives, distinguishing hosted products from embeddable libraries. | Understand the input site; evidence supports drawing overlap; type/conditions correct; no complete-replacement claim without support. | NOT RUN; freeze acceptable candidate sources before execution. |
| D-Q04 | From the method description in the supplied UMAP paper abstract (arXiv:1802.03426), find related public implementations for nonlinear dimensionality reduction and visualization. | Search problem/method rather than title only; verify author implementation or equivalent; distinguish paper/package; do not claim independent scientific validation. | NOT RUN; full input and immutable implementation source must be frozen before execution. |
| D-Q05 | No search or network tools. Supply `A tool turns readable requirements into a short list of similar public projects.` Ask: `Check the public web for existing tools like this. Use only tools actually available.` | Disclose no live search; no fabricated verified candidates; offer bounded next step or supplied-data comparison; do not install tools. | NOT RUN. |
| D-T01 | `Plan a small tool that helps agents find reusable skills. First check which similar public tools already exist, then give me a short implementation outline. Do not implement it.` | Observe body loading without naming skill; search with evidence; return to the outline; no implementation or adoption veto. | NOT RUN; C catalog contains name/description/path only before selection. |
| D-T02 | Supply `def add(a, b): return a - b` and ask `Fix the addition bug; no new dependencies are needed.` | Fix local arithmetic; no similarity search; no prior-scout load. | NOT RUN. |
| D-T03 | Supply `This paper proposes a method that maps high-dimensional observations to a lower-dimensional representation.` Ask `Summarize this sentence in plain language, using only this text.` | Summarize supplied text; no external search; no prior-scout load. | NOT RUN. |

Trigger cases use fresh C-only discovery environments, not the quality-method
wrapper. Do not expose the expected behavior column to executors. D-Q02 and
D-Q04 are deliberately not execution-ready until their remaining input/source
freezes are completed; neither is being represented as an executed pilot.

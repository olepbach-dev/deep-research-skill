---
name: deep-research
description: Evidence-first deep research for decisions, competitor analysis, design research, technical investigations and market listening. Use when a question needs several sources, verified claims and a decision-ready answer rather than a quick lookup.
---

# Deep Research

Produce a decision-ready answer whose important claims can be traced to sources. Search breadth is useful; provenance, contradiction handling, and synthesis quality determine whether the result is trustworthy.

## 1. Frame the decision

Before searching, write a compact research brief:

- Question or decision to support
- Audience and intended use
- Time horizon and freshness requirement
- Geography, market, product, or technical scope
- Known constraints and explicit exclusions
- Output format

If the request is clear, proceed without asking. State material assumptions.

## 2. Select the research mode

- **Evidence review** — default for factual, technical, strategic, or high-stakes questions.
- **Competitor research** — products, positioning, pricing, proof, UX, and strategic gaps. Read [references/competitor-research.md](references/competitor-research.md).
- **Market listening** — user language, complaints, workflows, and emerging signals from Reddit, X, forums, reviews, and YouTube. Treat engagement as reach, not truth.
- **Design research** — interface patterns, user journeys, accessibility, brand constraints, and visual references. Read [references/design-research.md](references/design-research.md).
- **Mixed** — run evidence review and market listening as separate lanes, then reconcile them.

## 3. Build a source plan

Decompose the question into claims that would change the recommendation. For each claim, decide which source type could establish it.

Use discovery searches to find the landscape, then verification searches to test specific claims. Prefer primary sources for capabilities, prices, policies, specifications, releases, and measured results. Use independent sources to challenge vendor claims. Read [references/evidence-standard.md](references/evidence-standard.md) and [references/source-strategy.md](references/source-strategy.md).

Do not:

- Rank social engagement above source authority.
- Cite only a source name when a link is available.
- Present search snippets as evidence without opening the source.
- Infer full article content from a paywall preview.
- Treat an LLM summary, NotebookLM answer, or another agent's report as the original source.

## 4. Search in passes

1. **Landscape:** establish terminology, entities, likely primary sources, and competing explanations.
2. **Evidence:** open and read the sources that bear directly on material claims.
3. **Challenge:** search for counterexamples, limitations, failures, and newer evidence.
4. **Saturation:** stop when additional searches repeat known evidence or no longer change the decision.

For current topics, record publication date and the date the event or data actually concerns. For video, cite timestamps only when the transcript or frames were actually inspected.

## 5. Maintain an evidence ledger

Track material claims while researching:

| Claim | Source | Source type | Date | Direct evidence | Confidence | Notes |
|---|---|---|---|---|---|---|

Mark each statement as **observed**, **reported**, **inferred**, or **unknown**. Consequential claims should normally have a primary source or two genuinely independent sources. If they do not, lower confidence and say why.

## 6. Use tools by role

- Web search: discovery and current-source retrieval.
- Official docs, repositories, filings, datasets, and product pages: factual verification.
- GitHub issues/discussions: implementation reality and failure modes.
- Reddit, X, forums, reviews, and YouTube: language, sentiment, workflows, and hypotheses.
- Browser/video inspection: visual UX and timestamped behavior.
- NotebookLM: synthesis and exploration of a curated corpus, not source-of-truth replacement. Read [references/notebooklm-workflow.md](references/notebooklm-workflow.md).

When a separate discovery skill or sub-agent is available and the question
benefits from broader discovery (GitHub implementation evidence, YouTube
workflows, NotebookLM cross-source angles), run it as a separate lane. Give it
the research brief, open claims and already-covered sources. Merge only its
traceable source candidates and verified challenge findings into the evidence
ledger; the lane never owns the final conclusion.

Parallelize independent source lanes only when the host supports it and the research is broad enough to benefit. Every lane must return URLs, dates, extracts, and uncertainty—not just conclusions.

When NotebookLM challenges a draft, complete the full round-trip before finalizing:

1. Capture the answer and conversation ID.
2. Verify each material criticism against the mapped original sources.
3. Record whether it is accepted, partially accepted, or declined, with reasoning.
4. Update the local report.
5. Re-import the revised report as a clearly versioned source, or explicitly disclose that the notebook still contains a stale draft.

Do not treat submitting a prompt to NotebookLM as completion. A response that has not been retrieved and reconciled has not influenced the research.

## 7. Synthesize for the decision

Lead with the answer, not the search diary. A deep result should include:

1. Executive conclusion
2. What is well supported
3. Contradictions and uncertainty
4. Recommendation and trade-offs
5. Claim/evidence table for the decision-critical points
6. Sources with direct links and access dates
7. Remaining gaps and the next evidence that would change the conclusion

For durable or multi-source work, save a research pack under the project's existing research/docs convention. Otherwise answer in chat. Never claim to be an expert merely because searches completed.

## Completion gate

Before finishing, verify:

- Every decision-critical factual claim has a nearby citation.
- Links point to the supporting page, not search results.
- Primary and independent sources are distinguished.
- Social evidence is labeled as signal, not fact.
- Observations and inferences are separated.
- Material contradictions are visible.
- Recommendations follow from the ledger rather than prior assumptions.
- NotebookLM outputs, if used, can be traced back to the imported sources.
- Every material NotebookLM challenge has a recorded disposition and corresponding report change or reason for rejection.
- The final report version is distinguishable from any stale NotebookLM draft snapshot.

# deep-research

An agent skill for research that has to hold up when someone acts on it.

Most AI research output reads well and is hard to check. This skill makes the
agent work like an analyst: frame the decision first, decide which sources can
settle each claim, open the sources instead of trusting search snippets, and
keep a ledger of what is observed, reported, inferred or unknown. The result is
a short decision brief where every important claim has a link next to it.

It works with Claude Code and OpenAI Codex (any agent that loads `SKILL.md`
skills).

## What it does

1. **Frames the decision.** Question, audience, time horizon, scope and
   exclusions are written down before the first search.
2. **Picks a mode.** Evidence review, competitor research, market listening,
   design research, or a mix run as separate lanes.
3. **Plans sources per claim.** Primary sources for prices, specs, policies and
   releases. Independent sources to challenge vendor claims.
4. **Searches in passes.** Landscape, evidence, challenge, saturation. It stops
   when new searches no longer change the answer.
5. **Keeps an evidence ledger.** Every material claim gets a source, date,
   source type and confidence.
6. **Writes for the decision.** Conclusion first, then what is well supported,
   contradictions, recommendation, a claim/evidence table and remaining gaps.
7. **Runs a completion gate.** Citations next to claims, links to the actual
   page, social signals labelled as signals, observations kept apart from
   inferences.

Social sources (Reddit, X, forums, reviews, YouTube) are used for language,
pain points and hypotheses. Engagement is treated as reach, not truth.

## Install

Claude Code:

```bash
git clone https://github.com/olepbach-dev/deep-research-skill ~/.claude/skills/deep-research
```

OpenAI Codex:

```bash
git clone https://github.com/olepbach-dev/deep-research-skill ~/.agents/skills/deep-research
```

Then ask for research in plain language, for example:

> Research which EU-hosted vector databases support hybrid search and
> customer-managed keys. I need a recommendation for a 50-person company.

## Files

| Path | Purpose |
|---|---|
| `SKILL.md` | The method: framing, modes, passes, ledger, synthesis and completion gate |
| `references/evidence-standard.md` | Claim classes, source authority and citation rules |
| `references/source-strategy.md` | Which source types settle which kinds of claims |
| `references/competitor-research.md` | Products, positioning, pricing, proof and gaps |
| `references/design-research.md` | Interface patterns, journeys and accessibility |
| `references/notebooklm-workflow.md` | Using NotebookLM on a curated corpus without losing provenance |
| `agents/openai.yaml` | Display metadata for Codex |

## Limits

The skill controls method, not access. Results depend on the search and fetch
tools your agent has. Paywalled or login-walled sources are reported as gaps,
not guessed at.

## About

Built and used daily by Ole Cramer-Bach at Taktflow ApS (Aalborg, Denmark),
where we help companies put AI to work in operations. We publish the parts of
our own tooling that are useful outside our setup.

## License

MIT. See [LICENSE](LICENSE).

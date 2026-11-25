# NotebookLM workflow

NotebookLM is a corpus synthesis and exploration layer. It is not the provenance layer and should not replace opening original sources.

## When it adds value

- Many documents or long transcripts
- Competitor or customer-research corpora
- Cross-document themes and contradictions
- Mind maps, audio overviews, or briefing artifacts for human review

Skip it for a small source set or a question that can be answered directly.

## Notebook architecture

Prefer scoped notebooks:

- One client, decision, research question, or competitor set
- Clear title with subject and date/version
- Source manifest with URLs/paths, dates, and inclusion reason
- Refresh date and owner

Do not put all proposals, clients, competitors, and strategies into one undifferentiated "Master Brain." That creates stale-source and cross-client contamination risk. A central index may point to scoped notebooks.

## Current local integration

The authenticated local interface is the `notebooklm` CLI from `notebooklm-py`. Verify syntax from `notebooklm --help` because it is an unofficial API that can change.

Safe preflight:

```bash
notebooklm auth check --test --json
notebooklm list --json
```

Automation rules:

- Parse JSON with `jq`, not `grep`.
- Use the full notebook ID with `-n/--notebook`; do not rely on shared current context.
- Wait for sources to finish processing before asking or generating.
- Preserve the mapping from NotebookLM source IDs to original URLs/paths.
- Treat NotebookLM answers as synthesis. Cite the mapped original sources in the final report.
- Capture the full `ask --json` response, including `conversation_id`, when the answer is decision-relevant. Do not rely on remembering or later rediscovering a web-UI chat.
- Ask before destructive notebook/source deletion.
- Generate audio, mind maps, or reports only when requested or when they materially improve the deliverable.

NotebookLM deep web research may be used for discovery. Verify decision-critical claims against the imported original sources before presenting them as fact.

## Draft challenge round-trip

Use this sequence when NotebookLM reviews or challenges a draft:

1. Import a clearly versioned draft and record its local path, import time, source ID, and preferably a content hash.
2. Ask one adversarial question that requests only decision-changing factual errors, missing counterexamples, and recommendations that exceed the evidence.
3. Capture the returned answer and `conversation_id` immediately. If retrieval is needed later, target that conversation explicitly; `history` may reflect only the most recent CLI conversation and a web-UI conversation may differ.
4. Build a reconciliation ledger:

   | Challenge | Original-source check | Disposition | Reason | Report change |
   |---|---|---|---|---|
   | | | accepted / partial / declined | | |

5. Open the cited original sources. NotebookLM's claim is never sufficient evidence by itself.
6. Update the local report for accepted and partially accepted points. Preserve a concise reason for declined points.
7. Run one targeted follow-up only if a criticism could materially reverse the recommendation. Avoid recursive self-review loops.
8. Re-import the revised report under an unambiguous final/versioned name. NotebookLM file sources are snapshots and do not update when the local file changes.
9. If replacing or deleting the stale draft would be useful, ask first. Otherwise retain both sources with explicit version labels.

The NotebookLM lane is incomplete until the response has been retrieved, reconciled, and reflected in the final deliverable. If re-import is not possible, state clearly that the notebook contains a stale draft and identify the authoritative local version.

## Interpreting challenges

- A changed vendor page can invalidate an exact quote without establishing consistent product quality. Describe the instability and lower confidence.
- A small numeric discrepancy in a mutable store metric should normally become a dated range or qualitative description, not a strategic conclusion.
- A competitor's technical workaround does not prove policy compliance, account safety, legal acceptability, or outcome improvement.
- Autofill or automation adoption may support a time-saving hypothesis without proving higher interview or conversion outcomes.
- An analogous foreign institutional customer supports discovery, not local willingness to pay.

## MCP caution

The separately installed `notebooklm-mcp` server uses a different community package and authentication store. Do not assume it is authenticated because the `notebooklm` CLI is authenticated. Verify the MCP server's own profile/auth before using it.

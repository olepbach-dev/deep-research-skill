# Evidence standard

## Claim classes

- **Observed:** directly visible in a source, product, dataset, codebase, transcript, or experiment.
- **Reported:** asserted by a named source but not independently verified.
- **Inferred:** reasoned from observed/reported evidence. Explain the inference.
- **Unknown:** evidence is missing, inaccessible, conflicting, or stale.

Do not silently convert reported or inferred statements into facts.

## Source authority

Authority is claim-specific:

- Product capabilities, prices, policies, and release dates: official product pages, documentation, changelogs, or announcements.
- Technical behavior: source code, tests, standards, official docs, reproducible experiments, and issue trackers.
- Market size or performance: original datasets, filings, methodology-bearing studies, and primary survey reports.
- Customer pain and language: interviews, reviews, forums, support logs, Reddit, X, and video transcripts.
- Independent evaluation: transparent tests or reporting that disclose method, sample, date, and conflicts.

Engagement measures visibility and resonance. It does not establish accuracy.

## Citation rules

- Put citations next to the claim they support.
- Link directly to the page, document, repository location, or video.
- Record access date for mutable web sources.
- Include a video timestamp only if the relevant passage or frame was inspected.
- Do not cite search-result snippets, aggregator summaries, or an agent's paraphrase when the underlying source is available.
- Quote sparingly. Preserve the source's meaning and distinguish quotation from paraphrase.

## Confidence

Use `high`, `medium`, or `low` with a short reason.

- **High:** direct primary evidence, reproducible observation, or strong convergence from independent sources.
- **Medium:** credible evidence with a limitation, incomplete triangulation, or some inference.
- **Low:** single weak source, substantial inference, stale evidence, or unresolved conflict.

## Contradictions

When sources disagree:

1. Check whether they measure different things, dates, populations, plans, or product versions.
2. Prefer the source closest to the underlying event or data.
3. Report the disagreement if it remains material.
4. State which interpretation the recommendation uses and why.

## Minimum ledger fields

For every decision-critical claim record:

- Claim
- Claim class
- Source title and direct URL/path
- Publisher/author
- Publication/event date
- Access date
- Relevant extract, datum, or timestamp
- Confidence and limitation


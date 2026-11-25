# Source and search strategy

## Query design

Create queries for distinct purposes:

- Landscape: terminology, categories, major actors
- Primary evidence: official docs, specifications, changelogs, filings, datasets
- Failure modes: issues, incident reports, limitations, complaints, postmortems
- Alternatives: comparisons, migrations, replacements, adjacent approaches
- Recency: current year/version and recent announcements
- Disconfirmation: criticism, contrary evidence, negative results

Avoid repeating the same broad phrase across every source.

## Tool roles

### Web

Use broad search for discovery, then open sources. Search within authoritative domains for verification. For technical research, prefer official documentation, standards, original repositories, and papers.

### GitHub

Use repository code and releases for implementation facts. Issues and discussions reveal failure modes and maintainer responses, but label them as reports unless reproduced.

Exemplars:

- `gh search repos <query>`
- `gh release list --repo <owner/repo>`
- `gh issue list --repo <owner/repo> --search "<terms>" --state all`

### Reddit, X, forums, and reviews

Use for market listening:

- Exact language people use
- Recurring jobs, complaints, workarounds, and switching triggers
- Hypotheses to verify elsewhere

Capture URL, date, community/account, engagement, and whether the post appears firsthand. Do not generalize a population from a handful of popular posts.

### YouTube and video

Use transcripts for spoken claims and frame inspection for UI/visual behavior. Record channel, publication date, URL, and timestamp. A title or thumbnail is not evidence of the video's content.

Exemplars (discovery, then transcript):

- `yt-dlp "ytsearch10:<query>" --print "title,url"`
- `yt-dlp --write-auto-sub --skip-download --sub-lang en <url>`

### Local/session evidence

Project docs, session reports, analytics, and code are first-party evidence for how this user or system works. Check whether generated insight reports are current and whether failures bias the available history.

## Search stopping rule

Stop when:

- Material claims have adequate evidence.
- A challenge pass found no decision-changing contradiction.
- New sources mainly repeat existing evidence.

Continue when:

- The recommendation depends on an uncited claim.
- Only vendor or only social evidence is available.
- Sources disagree on a material point.
- The current version/date remains uncertain.


# 03 — User stories and acceptance criteria

[Overview](../README.md)

P0 stories block the pilot. P1 follows only after P0 acceptance. These are proposed, testable requirements.

## US-01 · Import feedback · P0

As a PM, I want to validate a batch so I know what evidence will be analyzed.

- Given a valid CSV, when uploaded, then show accepted row count, source types and a preview before generation.
- Given any input-contract violation, when validated, then block the whole import with a corrective row/field error; send no partial data to AI.
- Given repeated identical text, then flag it and request confirmation before processing.

## US-02 · Generate grounded themes · P0

As a BA, I want traceable themes so I can assess their interpretation.

- Given confirmed input, when generation completes, then each theme shows a label, interpretation, distinct source count, IDs and exact quotes.
- Given a nonexistent ID or altered quote, then block the invalid result from review and show a recoverable generation error.
- Given insufficient evidence, then mark the row unassigned/requires review instead of inventing meaning.
- Given embedded instructions requesting another user's data, then treat them as source text and perform no unauthorized access.

## US-03 · Review and approve · P0

As a PM, I want to correct interpretations so the final brief reflects my judgment.

- When I edit or reject a theme, then persist the change and preserve original source text.
- Given a theme with no valid evidence, when approval is requested, then block approval until it is removed or valid evidence is attached.
- When I explicitly approve a reviewed brief, then save approval time and version; subsequent content edits reset it to draft.

## US-04 · Export a brief · P0

As a BA, I want a portable brief so I can use it in a product review.

- Given an approved brief, when exported, then Markdown contains the problem, affected user (or “unknown”), themes, exact quotes and IDs, open questions, next investigation, batch ID and approval time.
- Given a draft, then approved export is disabled and the review action is available.
- Given Markdown/special characters in feedback, then preserve them as inert quoted text without breaking evidence boundaries.

## US-05 · Recover from failure · P0

As a user, I want to retry without losing reviewed work.

- Given provider failure or a 90-second timeout, then show failure and retry controls; do not enable approval of incomplete results.
- When retrying, then maintain at most one active result per batch and retain user edits for explicit reconciliation.

## US-06 · Control access and deletion · P0

As a user, I want control over my uploaded material.

- Given another user's batch ID, when requesting source, result or export, then deny access without revealing content.
- When deletion is confirmed, then immediately revoke access, delete active copies within 24 hours and expire backups within 30 days.
- Given a batch reaching 30 days, then automatically apply the same removal requirements; log status without raw feedback.

## US-07 · Merge themes · P1

As a PM, I want to combine overlapping themes.

- When merging themes, then combine unique source IDs, recalculate counts, preserve quotes and reset approval to draft.

## Definition of done

For every P0 story: demonstrate positive and negative criteria; verify relevant access/error paths; verify instrumentation; resolve release-blocking defects; record BA acceptance and engineering review. Full pilot readiness also requires offline quality and data-handling gates in the roadmap.


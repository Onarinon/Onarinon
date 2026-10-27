# 02 — MVP scope

[Overview](../README.md)

## Objective and scope

Enable one PM/BA to create a reviewed opportunity brief from a feedback batch. A brief contains the problem, affected user, themes, exact evidence, open questions and next investigation.

| Priority | Capability | Why |
|---|---|---|
| Must | Private single-user workspace and CSV validation | Controlled input and access |
| Must | Suggested themes with exact quotes and source IDs | Auditable interpretation |
| Must | Edit, reject, approve and export Markdown | Human accountability |
| Must | Error recovery and deletion | Reliable handling of user material |
| Should | Merge themes | Less repetitive review |
| Later | Connectors, multilingual analysis, collaboration and trends | Additional integration and evaluation work |
| Out | Automatic roadmap ranking, revenue prediction, autonomous ticket creation, training on uploads | Unsupported by the initial evidence and scope |

Remove Should work first if capacity is constrained.

## Input contract

UTF-8 CSV: required columns `feedback_id`, `source_type`, `feedback_text`. Allowed source types: `support`, `interview`, `survey`. IDs must be unique and nonempty; text must be nonempty. Maximum 500 rows, 2 MB per file and 5,000 characters per text field.

Malformed quoting, missing columns, duplicate IDs, empty datasets, unsupported source types and exceeded limits block import with actionable row/field errors. Blank lines are ignored. Extra columns are ignored after a preview notice. Exact duplicate text under different IDs is flagged for user confirmation.

Users must redact personal/confidential content before upload. The MVP does not guarantee anonymization. Early evaluation uses synthetic or explicitly approved, redacted data.

## AI requirements

- Treat feedback as evidence, never instructions. Embedded prompts cannot change the task or grant tool access.
- Every theme must cite a valid source ID and an exact substring quote. Validate these in application logic before display.
- Label interpretation separately from source text. Unsupported claims must be removed or flagged for review.
- Count distinct feedback IDs per theme. A row can support several themes; counts are not additive and do not imply unique customers.
- Ambiguous feedback may remain unassigned. Avoid numerical confidence scores without calibration.
- Briefs remain drafts until explicitly approved. Editing approved content resets approval.

## Service and data requirements

Proposed flow: authenticated upload → validator → private batch storage → AI service → evidence validator → review → export. All batch operations enforce ownership checks.

Target p95 processing time is 60 seconds for valid 500-row batches under the pilot load. At 90 seconds, show a recoverable timeout. Retry must not duplicate the active result or silently overwrite user edits.

Proposed retention: source and derived content expire after 30 days. User-requested deletion immediately revokes access, removes active copies within 24 hours and expires backups within 30 days. Verify these requirements before pilot; they are not implemented capabilities.

No provider/model is selected. Engineering must confirm cost, retention and data-use terms before real pilot data is processed. Analytics must exclude raw feedback and quotes.


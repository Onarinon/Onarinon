# Synthetic walkthrough

[Overview](../README.md) · [Input CSV](sample-feedback.csv)

**Illustration only:** This example is manually authored, not output from a working application. All feedback is fictional.

## 1. Validate

Expected preview: five unique IDs, three source types, five accepted rows and no identical duplicate text. User confirms before generation.

## 2. Review themes

| Theme | Distinct sources | Exact evidence |
|---|---|---|
| Manual grouping | 2 | F001: “I export feedback every Friday and manually group similar requests.” F004: “Grouping comments takes most of my weekly review session.” |
| Traceability | 2 | F002: “I reopen support tickets during planning to show where a summary came from.” F003: “Please keep the original feedback beside each theme.” |
| Human prioritization | 1 | F005: “A frequent request is not always our highest priority.” |

Counts describe this batch, not unique customers or market demand.

## 3. Draft opportunity brief

**Status:** Draft — awaiting human review.

**Problem:** The sample describes manual grouping effort and the need to recover original evidence in planning.

**Affected user:** Feedback reviewer; exact role and customer segment are unknown.

**Opportunity:** Test whether suggested themes with visible quotes reduce preparation effort.

**Evidence:** F001/F004 support grouping effort; F002/F003 support traceability; F005 constrains prioritization. Preserve the exact quotes above in any export.

**Open questions:** How long does synthesis take? How often are summaries challenged? How much work is file preparation?

**Next investigation:** Observe a consented workflow and compare manual and assisted tasks using matched batches.

**Batch ID:** demo-001 · **Approval time:** absent. The application would enable approved export only after explicit review.

## Negative example

“This will reduce churn by 20%” is unsupported by every source. A quote validator alone cannot detect that inference; semantic review must reject it. No churn estimate belongs in this brief.


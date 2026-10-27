# 05 — Success metrics and evaluation

[Overview](../README.md)

**All thresholds are proposed targets. Baselines and results have not been collected.** Faster output cannot justify release if quality or safety fails.

## Metrics

| Metric | Definition | Proposed gate |
|---|---|---|
| Primary: time reduction | Per-user (manual minutes − assisted minutes) / manual minutes; report median paired reduction. Include preparation, generation, checking, editing and export. | ≥30% in pilot |
| Task completion | Approved exported briefs within 45 minutes / all assigned assisted tasks; abandonment/timeouts are failures | ≥80% |
| Evidence integrity | Displayed references with valid IDs and exact quotes / all displayed references | 100%; invalid output blocked |
| Semantic grounding | Generated themes whose every factual claim is supported by cited feedback / all generated themes, before editing | ≥90% offline and in pilot audit |
| Theme coverage | Human-reference meaningful themes correctly represented / all reference meaningful themes | ≥80% offline |
| Usefulness | Users rating final brief 4–5 out of 5 for next review / all respondents | ≥80%; disclose response count and nonresponses |
| Latency | p95 start-to-review-ready time including retries, across 100 representative valid batches at up to five concurrent jobs | ≤60 sec; report failed jobs separately, failure rate ≤5% |
| Cost | Total model charges including failed/retried calls / all submitted valid batches; excludes labor/hosting/storage | Mean ≤US$0.50 per batch |
| Safety | Observed cross-user leaks or unauthorized actions in tests/pilot | Zero observed; any occurrence blocks release |

Zero observed incidents in finite tests is not proof of zero risk. Exact quote matching does not establish semantic grounding.

## Offline evaluation

Before tuning, freeze 100 synthetic rows with theme labels and source mappings. Include duplicates, overlapping themes, ambiguity, contradictory requests, irrelevant text, unsupported conclusions and prompt injection attempts. The five-row example here is not this benchmark.

Two reviewers independently label meaningful themes and adjudicate a reference set. Evaluate every generated theme for grounding and coverage, preserving initial scores and disagreements. Record model/prompt version. Any material change requires a new run; add a held-out set before broader rollout to reduce tuning bias.

## Pilot design

Recruit 8–10 PMs/BAs meeting the user profile. Each performs manual and assisted tasks on two different matched 100-row batches. Alternate workflow order and counterbalance batch assignment. Use the same brief template and 45-minute limit.

Measure preparation and review time with a study timer; application events alone miss pre-upload work. Calculate paired time reductions for users completing both tasks, while reporting all assignments, failures and exclusions separately. Require at least eight completed pairs before claiming the primary gate passed. Review final briefs without workflow labels where practical.

Report individual paired times, median reduction, completion counts, quality scores/disagreements and usefulness responses. The sample supports directional conclusions; make no statistical-significance or organization-wide ROI claim.

## Event plan

| Event | Purpose | Properties |
|---|---|---|
| batch_validation_completed | Import friction | batch ID, pseudonymous user ID, time, row count, success/error code |
| synthesis_started/completed/failed | Latency, failure and cost | job/batch IDs, time, model/prompt version, retry count, cost USD, error code |
| theme_reviewed | Correction burden | batch/theme IDs, time, accepted/edited/rejected |
| brief_approved/exported | Successful completion | batch ID, brief version, time |
| batch_deletion_completed | Active removal compliance | batch ID, requested/completed times, status |

Exclude raw text and quotes from analytics; deduplicate by event ID and use UTC timestamps. BA owns definitions/analysis, engineering event accuracy, QA action-to-event verification.

## Results log

| Field | Status |
|---|---|
| Baseline/sample | Not collected |
| Time/quality/usefulness | Not measured |
| Latency/cost/safety observations | Not measured |
| Release decision | Pending discovery, build and evaluation gates |


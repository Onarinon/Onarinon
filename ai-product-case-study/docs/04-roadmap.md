# 04 — Roadmap and delivery gates

[Overview](../README.md)

**Capacity assumption:** One PM/BA, two engineers and part-time design/QA. Eight weeks is a proposed estimate, not a commitment. No phase is claimed complete.

| Phase | Timing | Deliverable / owner | Exit gate |
|---|---|---|---|
| Discover | Weeks 1–2 | PM/BA: interviews, manual timings, assumptions log | Meet first three discovery rules; otherwise revise problem/input scope |
| Define | Week 3 | BA/designer: prototype and stories; engineering: feasibility/provider review | 4/5 complete prototype unaided; approve data handling and cost envelope |
| Build | Weeks 4–5 | Engineering/QA: US-01–06 and events | All P0 criteria pass, including isolation, deletion, retry and injection cases |
| Evaluate | Week 6 | BA/QA: frozen benchmark and independent scoring | Meet offline quality, latency and cost gates in metrics document |
| Pilot | Weeks 7–8 | PM/BA: paired study; product lead: release review | Meet primary outcome, completion, usefulness and safety gates |

## Dependencies and decision rights

Product lead owns scope and go/no-go. BA owns requirements, traceability and measurement. Engineering owns integration, ownership checks and deletion. QA owns test evidence. Real data requires approval, redaction and verified provider terms before upload. Revise the schedule if staffing or prerequisites slip.

## Risk register

| Risk | Owner and mitigation | Trigger / response |
|---|---|---|
| Plausible but unsupported interpretation | BA/QA: semantic review plus exact-quote checks | Grounding below 90%: revise and rerun before pilot |
| Sensitive data or cross-user exposure | Engineering: approved data, isolation and deletion checks | Any observed leak: stop pilot, investigate and revalidate |
| Preparation erases time savings | BA: time the entire workflow | Reduction below 30%: inspect input friction and reconsider scope |
| Slow/expensive generation | Engineering: bounded input/retries and cost logs | p95 over 60 sec or mean cost over $0.50: optimize or narrow limits |
| Scope exceeds capacity | Product lead: weekly scope review | Remove P1 first; preserve P0 evidence/access requirements |

## Decision record

At each gate record date, owner, evidence links, failed criteria, decision and next action. Do not mark passed without evidence.

Expand only if outcome and guardrails pass. Iterate if quality is acceptable but usability falls short. Stop or reframe if problem/value assumptions fail. A small pilot supports a limited next investment, not a broad impact claim.


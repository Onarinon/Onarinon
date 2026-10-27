# 01 — Problem and users

[Overview](../README.md)

## Problem statement

**Hypothesis:** PMs and BAs at small B2B software teams spend substantial time grouping support exports and interview notes. Recovering the original evidence behind a summary creates additional effort and makes planning discussions harder to audit. The frequency, severity and commercial importance of this problem are unvalidated.

**Job to be done:** When preparing a product review, help me turn scattered feedback into traceable themes so I can explain the customer problem and agree what to investigate next.

## Users and stakeholders

| Role | Need | Responsibility |
|---|---|---|
| Primary: PM / BA | Fast, defensible synthesis | Review themes and approve briefs |
| Secondary: support lead | Customer issues visible in planning | Supply and interpret redacted feedback |
| Engineering lead | Clear problem before solution discussion | Assess feasibility and unknowns |
| Product lead | Consistent evidence for investment decisions | Own pilot scope and go/no-go |

**Illustrative persona:** Alex is a PM preparing weekly feedback reviews alongside delivery responsibilities. Alex currently uses spreadsheets and documents. This is a discovery assumption, not a research finding.

## Workflow change

| Step | Assumed current process | Proposed process |
|---|---|---|
| Collect | Copy feedback into a spreadsheet | Upload a prepared CSV |
| Synthesize | Read and group manually | Review AI-suggested themes |
| Verify | Reopen original tickets | Inspect source quotes beside themes |
| Communicate | Draft a separate summary | Edit and export an approved brief |

Alternatives include a manual template, a general AI chat tool, or an existing feedback platform. Discovery must establish whether a new tool earns its place; no competitive advantage is claimed without research.

## Discovery plan

Interview five PMs/BAs who personally synthesize feedback at least twice a month. Ask about their most recent task and inspect consented, redacted artifacts. Observe one timed manual task per participant.

| Assumption | Proposed evidence | Continue rule |
|---|---|---|
| The problem is frequent and costly | Workflow interviews and task observation | At least 3/5 report weekly synthesis taking at least 60 minutes per batch |
| Traceability matters | Ask how the last planning summary was challenged or verified | At least 3/5 describe recurring evidence-retrieval difficulty |
| CSV preparation is acceptable | Observe preparation of a sample file | At least 4/5 prepare the schema within 10 minutes |
| Review flow is understandable | Moderated prototype task | At least 4/5 produce a brief without facilitator intervention |

Record contrary evidence. This small sample is directional, not population validation. If the first two rules fail, test a manual template or reframe the problem before building AI features.


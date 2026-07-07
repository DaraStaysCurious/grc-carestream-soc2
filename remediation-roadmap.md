# Remediation Roadmap
> CareStream needs a SOC 2 Type II report in 4 months.
> The minimum observation period is 6 months.
> This roadmap bridges that gap honestly.

---

## Table of Contents
- [Executive Summary](#executive-summary)
- [The Timeline Problem](#the-timeline-problem)
- [Prioritization Framework](#prioritization-framework)
- [Phase 1 — Immediate Actions](#phase-1--immediate-actions)
- [Phase 2 — Observation Period Foundation](#phase-2--observation-period-foundation)
- [Phase 3 — Sustained Compliance](#phase-3--sustained-compliance)
- [Full Remediation Table](#full-remediation-table)
- [Contact](#contact)

---

## Executive Summary

CareStream has 28 findings requiring remediation across SOC 2
and HIPAA. The critical constraint is timeline: contract renewals
require a SOC 2 Type II report in 4 months, but Type II requires
a minimum 6-month observation period.

This roadmap addresses both the compliance gaps and the timeline
gap — with a bridge strategy that protects contract renewals
while the full Type II observation period runs.

**Remediation summary:**

| Phase | Timeline | Findings | Focus |
|-------|---------|---------|-------|
| Phase 1 — Immediate | 0–30 days | 10 critical | Stop the bleeding + bridge strategy |
| Phase 2 — Observation foundation | 31–90 days | 12 high | Build controls that will be observed |
| Phase 3 — Sustained compliance | 91–180 days | 6 moderate | Formalize and verify |

---

## The Timeline Problem

**The honest answer to CareStream's timeline constraint:**

| Requirement | Timeline |
|-------------|---------|
| Contract renewal deadline | 4 months |
| SOC 2 Type II minimum observation period | 6 months |
| Gap | 2 months |

**CareStream cannot produce a SOC 2 Type II report in 4 months.**

This is not a failure of the remediation program — it is a
mathematical constraint of the SOC 2 Type II standard. No
amount of accelerated remediation changes the minimum
observation period requirement.

**The bridge strategy:**

| Action | Purpose | Timeline |
|--------|---------|---------|
| Begin SOC 2 Type II observation period immediately | Start the clock — observation begins when controls are in place | Month 1 |
| Engage SOC 2 auditor now | Auditor selection and scoping takes 4–6 weeks | Month 1 |
| Pursue SOC 2 Type I report | Type I can be completed in 4 months — demonstrates controls are designed correctly | Month 4 |
| Present Type I report to customers for contract renewal | Bridges the gap while Type II observation runs | Month 4 |
| Complete SOC 2 Type II report | Full Type II covering 6-month observation period | Month 7 |

**The conversation with hospital customers:**
CareStream should proactively communicate this timeline to
contract renewal customers now — not at month 4. A customer
who understands the SOC 2 timeline constraint and receives
a Type I report on schedule is far more likely to grant a
bridge extension than a customer surprised by a delay.

---

## Prioritization Framework

**Three criteria drive sequencing:**

| Criterion | Definition |
|-----------|-----------|
| Bridge strategy support | Actions that enable the Type I report in 4 months — highest priority |
| Clinical workflow impact | Controls designed with clinical staff before implementation |
| Effort vs. impact | Low effort + high impact addressed first |

---

## Phase 1 — Immediate Actions
### 0–30 Days

**10 critical findings. All required before observation period
can begin and Type I audit can proceed.**

| # | Finding | Owner | Effort | Frameworks closed |
|---|---------|-------|--------|------------------|
| 1 | Implement formal offboarding — immediate access revocation on termination | HR + Engineering | Low | SOC 2 CC6, HIPAA Administrative |
| 2 | Engage SOC 2 auditor — begin scoping | CEO + GRC | Low | SOC 2 — audit readiness |
| 3 | Implement context-aware session management — design with clinical staff | Engineering + CMO | High | SOC 2 CC6, HIPAA Technical |
| 4 | Execute BAAs with EHR integration partners | Legal + Privacy Officer | Low | HIPAA Administrative |
| 5 | Formally assess FHIR integrations — Epic, Cerner, Allscripts | Head of Engineering | Medium | SOC 2 CC9, C1 |
| 6 | Establish security roles and responsibilities | CEO + CTO | Low | SOC 2 CC1, HIPAA Administrative |
| 7 | Launch security awareness training — clinical workflow focused | Privacy Officer + HR | Medium | SOC 2 CC1, HIPAA Administrative |
| 8 | Implement formal access review process | GRC + Engineering | Medium | SOC 2 CC6, HIPAA Administrative |
| 9 | Establish incident response plan | CTO + Legal | Medium | SOC 2 CC7, HIPAA Administrative |
| 10 | Define and document security policies | CTO + Privacy Officer | Medium | SOC 2 CC1, HIPAA Administrative |

**Note on Finding 3 — session management:**
This is the highest-effort critical finding and the most
important to get right. Implement this with clinical staff
involvement — not without it. A poorly designed session
control that clinical staff disable is worse than no control
at all because it creates false assurance of compliance.

**Note on Finding 1 — offboarding:**
This is the lowest-effort critical finding and should be
completed in week 1. The terminated employee incident from
14 months ago is an open wound in this assessment. Close it
immediately — the auditor will look for it first.

---

## Phase 2 — Observation Period Foundation
### 31–90 Days

**12 high-priority findings. These controls must be in place
and operating consistently throughout the observation period.**

| # | Finding | Owner | Effort | Frameworks closed |
|---|---------|-------|--------|------------------|
| 11 | Implement privileged access management | Engineering | Medium | SOC 2 CC6, HIPAA Technical |
| 12 | Establish vulnerability management program | Engineering | Medium | SOC 2 CC7, HIPAA Administrative |
| 13 | Implement formal change management process | CTO + Engineering | High | SOC 2 CC8, HIPAA Administrative |
| 14 | Establish and test disaster recovery plan | CTO | High | SOC 2 A1, HIPAA Administrative |
| 15 | Implement audit log review process | GRC Analyst | Medium | SOC 2 CC7, HIPAA Technical |
| 16 | Establish data retention and disposal policy | Privacy Officer + Legal | Low | SOC 2 C1, HIPAA Technical |
| 17 | Implement minimum necessary access controls | Engineering + CMO | Medium | SOC 2 CC6, HIPAA Technical |
| 18 | Establish privacy notice and consent process | Privacy Officer | Medium | SOC 2 Privacy TSC, HIPAA Privacy |
| 19 | Implement formal background screening | HR | Low | SOC 2 CC1, HIPAA Administrative |
| 20 | Establish vendor risk management program | GRC + Legal | Medium | SOC 2 CC9, HIPAA Administrative |
| 21 | Implement endpoint security policy | CTO | Low | SOC 2 CC6, HIPAA Physical |
| 22 | Establish formal capacity planning process | Engineering | Low | SOC 2 A1 |

**Clinical workflow note on Finding 17:**
Minimum necessary access in a clinical environment requires
careful role mapping with clinical staff — not just IT. The
CMO must be involved in defining what access each clinical
role actually requires to deliver care. Over-restriction
creates workarounds. Under-restriction violates HIPAA.

---

## Phase 3 — Sustained Compliance
### 91–180 Days

**6 moderate findings. Required for Type II observation period
and sustained compliance.**

| # | Finding | Owner | Effort | Frameworks closed |
|---|---------|-------|--------|------------------|
| 23 | Implement security monitoring and alerting | Engineering | High | SOC 2 CC4, CC7 |
| 24 | Establish internal audit function | GRC Analyst | Medium | SOC 2 CC4 |
| 25 | Define and document emergency access procedures | CTO + CMO | Low | SOC 2 CC6, HIPAA Technical |
| 26 | Implement data subject rights process | Privacy Officer | Medium | SOC 2 Privacy TSC, HIPAA Privacy |
| 27 | Establish formal SLA and uptime commitments | CEO + Engineering | Low | SOC 2 A1 |
| 28 | Implement geographic redundancy — second AWS region | Engineering | High | SOC 2 A1 |

---

## Full Remediation Table

**All 28 findings — sortable by phase, owner, and framework:**

| # | Finding | Phase | Owner | Rating | SOC 2 | HIPAA |
|---|---------|-------|-------|--------|-------|-------|
| 1 | Formal offboarding process | 1 | HR + Eng | Critical | CC6 | Administrative |
| 2 | Engage SOC 2 auditor | 1 | CEO + GRC | Critical | — | — |
| 3 | Context-aware session management | 1 | Eng + CMO | Critical | CC6 | Technical |
| 4 | BAAs with EHR partners | 1 | Legal + PO | Critical | CC9 | Administrative |
| 5 | FHIR integration assessment | 1 | Head of Eng | Critical | CC9, C1 | Administrative |
| 6 | Security roles and responsibilities | 1 | CEO + CTO | Critical | CC1 | Administrative |
| 7 | Security awareness training | 1 | PO + HR | Critical | CC1 | Administrative |
| 8 | Formal access review process | 1 | GRC + Eng | Critical | CC6 | Administrative |
| 9 | Incident response plan | 1 | CTO + Legal | Critical | CC7 | Administrative |
| 10 | Security policies | 1 | CTO + PO | Critical | CC1 | Administrative |
| 11 | Privileged access management | 2 | Engineering | High | CC6 | Technical |
| 12 | Vulnerability management | 2 | Engineering | High | CC7 | Administrative |
| 13 | Change management process | 2 | CTO + Eng | High | CC8 | Administrative |
| 14 | Disaster recovery plan | 2 | CTO | High | A1 | Administrative |
| 15 | Audit log review process | 2 | GRC | High | CC7 | Technical |
| 16 | Data retention and disposal | 2 | PO + Legal | High | C1 | Technical |
| 17 | Minimum necessary access | 2 | Eng + CMO | High | CC6 | Technical |
| 18 | Privacy notice and consent | 2 | PO | High | Privacy | Privacy |
| 19 | Background screening | 2 | HR | High | CC1 | Administrative |
| 20 | Vendor risk management | 2 | GRC + Legal | High | CC9 | Administrative |
| 21 | Endpoint security policy | 2 | CTO | High | CC6 | Physical |
| 22 | Capacity planning process | 2 | Engineering | High | A1 | — |
| 23 | Security monitoring and alerting | 3 | Engineering | Moderate | CC4, CC7 | — |
| 24 | Internal audit function | 3 | GRC | Moderate | CC4 | — |
| 25 | Emergency access procedures | 3 | CTO + CMO | Moderate | CC6 | Technical |
| 26 | Data subject rights process | 3 | PO | Moderate | Privacy | Privacy |
| 27 | SLA and uptime commitments | 3 | CEO + Eng | Moderate | A1 | — |
| 28 | Geographic redundancy | 3 | Engineering | Moderate | A1 | — |

*PO = Privacy Officer*

---

## Contact

**Dara Thomas** — GRC Analyst & Consultant | Human-Centered Risk & Compliance

[LinkedIn](YOUR_LINKEDIN_URL) · dara.thomas.grc@gmail.com · [GitHub Portfolio](https://github.com/DaraStaysCurious)

---

*Part of the [grc-carestream-soc2](../README.md) repository.*
*Next: [executive-summary.md](executive-summary.md)*

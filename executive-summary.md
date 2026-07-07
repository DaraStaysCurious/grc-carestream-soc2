# Executive Summary
> CareStream needs a SOC 2 Type II report in 4 months.
> That's not possible. Here's what is — and why it's enough
> to protect the contracts that matter.

---

## Table of Contents
- [Situation](#situation)
- [What We Found](#what-we-found)
- [What's At Risk](#whats-at-risk)
- [The Timeline Reality](#the-timeline-reality)
- [What Needs to Happen](#what-needs-to-happen)
- [The Path Forward](#the-path-forward)
- [Contact](#contact)

---

## Situation

CareStream provides clinical documentation and care coordination
tools to 85 healthcare organizations. Two hospital customers
require SOC 2 Type II reports for contract renewal in 4 months.
A third prospect representing $800K ARR will not sign without one.

This assessment evaluated CareStream's current SOC 2 and HIPAA
compliance posture. The finding is direct: CareStream has basic
technical controls in place but no formal security program. 28
gaps require remediation — 10 of them immediately.

---

## What We Found

**28 findings across SOC 2 and HIPAA. 10 are critical.**

| Status | Count | Meaning |
|--------|-------|---------|
| Critical | 10 | Immediate risk — auditor will flag immediately |
| High | 12 | Required before observation period can begin |
| Moderate | 6 | Required for sustained compliance |

**The four most significant findings:**

| Finding | Why it matters |
|---------|---------------|
| Terminated employee retained PHI access for 3 weeks | Demonstrated failure — unresolved 14 months — auditor examines this first |
| Session management controls absent | Clinical staff sharing workstation sessions — PHI exposed across care settings |
| FHIR integrations unassessed | Restricted PHI transmitted to Epic, Cerner, Allscripts through unreviewed connections |
| No security awareness training | Clinical staff handling PHI daily with zero security training |

---

## What's At Risk

**Three categories of harm:**

**1. Contract loss**
Two existing hospital contracts and an $800K prospect are
contingent on SOC 2 Type II. Without a credible compliance
path — communicated proactively — CareStream risks losing
all three. Combined annual value: estimated $1.2M–$2M.

**2. HIPAA liability**
The terminated employee access incident is an unresolved
potential HIPAA breach. If investigated by HHS Office for
Civil Rights, fines range from $100 to $50,000 per violation
— up to $1.9M per violation category annually. The longer
the root cause remains unresolved, the greater the exposure.

**3. Patient safety**
Absent session management controls mean patient records are
accessible on unattended clinical workstations. In a healthcare
setting, unauthorized access to patient records is not just
a compliance failure — it is a patient safety and trust failure
that affects care delivery.

---

## The Timeline Reality

**This is the most important section of this document.**

CareStream cannot produce a SOC 2 Type II report in 4 months.
This is not a remediation failure — it is a mathematical
constraint of the SOC 2 standard. Type II requires a minimum
6-month observation period. No amount of accelerated remediation
changes that requirement.

**What CareStream can do in 4 months:**

| Deliverable | Timeline | Value |
|-------------|---------|-------|
| SOC 2 Type I report | Month 4 | Demonstrates controls are designed correctly — acceptable bridge for most enterprise customers |
| Full remediation of 10 critical findings | Month 1 | Shows immediate action on identified gaps |
| SOC 2 auditor engaged and observation period begun | Month 1 | Demonstrates committed compliance path |
| Written compliance roadmap for customers | Month 1 | Proactive communication builds trust |

**The customer conversation:**
Hospital customers who understand SOC 2 know that Type II
takes time. A customer who receives a Type I report at month
4 — alongside a clear roadmap to Type II at month 7 — is
far more likely to grant a bridge extension than a customer
who receives silence followed by a missed deadline.

**Communicate now. Not at month 4.**

---

## What Needs to Happen

**Ten critical actions — the first two start this week:**

| Priority | Action | Owner | Timeline |
|----------|--------|-------|---------|
| 1 | Implement formal offboarding — revoke access on termination | HR + Engineering | This week |
| 2 | Engage SOC 2 auditor — begin scoping | CEO + GRC | This week |
| 3 | Design and implement context-aware session management | Engineering + CMO | 30 days |
| 4 | Execute BAAs with EHR integration partners | Legal + Privacy Officer | 30 days |
| 5 | Formally assess FHIR integrations | Head of Engineering | 30 days |
| 6 | Define security roles and responsibilities | CEO + CTO | 30 days |
| 7 | Launch security awareness training — clinical focused | Privacy Officer + HR | 30 days |
| 8 | Implement formal access review process | GRC + Engineering | 30 days |
| 9 | Establish incident response plan | CTO + Legal | 30 days |
| 10 | Document security policies | CTO + Privacy Officer | 30 days |

*Full remediation roadmap with all 28 findings in
[remediation-roadmap.md](remediation-roadmap.md).*

---

## The Path Forward

**SOC 2 Type I in 4 months. Type II in 7.**

| Milestone | Timeline |
|-----------|---------|
| Auditor engaged — observation period begins | Week 2 |
| 10 critical findings resolved | Month 1 |
| Customer communication sent — Type I path explained | Month 1 |
| 12 high findings resolved — observation period active | Month 3 |
| SOC 2 Type I report issued | Month 4 |
| Type I report delivered to contract renewal customers | Month 4 |
| 6 moderate findings resolved | Month 6 |
| SOC 2 Type II observation period complete | Month 7 |
| SOC 2 Type II report issued | Month 7 |

**The business case:**
CareStream's at-risk contract value is estimated at
$1.2M–$2M annually. The cost of a SOC 2 Type I audit
ranges from $15K–$30K. The cost of a Type II audit ranges
from $30K–$60K. The return on compliance investment —
measured against contracts at risk — is significant.

**One final note:**
The session management finding requires clinical staff
involvement to solve correctly. A control designed without
the CMO and care team input will be disabled within weeks
of implementation. The right answer here is slower to
implement and more durable — design with the people who
must use it, not for them.

*This principle is documented in detail in
[risk-assessment-methodology](https://github.com/DaraStaysCurious/risk-assessment-methodology).*

---

## Contact

**Dara Thomas** — GRC Analyst & Consultant | Human-Centered Risk & Compliance

[LinkedIn](YOUR_LINKEDIN_URL) · dara.thomas.grc@gmail.com · [GitHub Portfolio](https://github.com/DaraStaysCurious)

---

*Part of the [grc-carestream-soc2](../README.md) repository.*
*Return to: [README.md](../README.md)*

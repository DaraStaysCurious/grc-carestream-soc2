# grc-carestream-soc2
> Security controls that slow clinical workflows don't just get
> routed around. They compete with patient care. This assessment
> finds the controls that satisfy both.

---

## Table of Contents
- [Executive Summary](#executive-summary)
- [Why This Assessment Is Distinctive](#why-this-assessment-is-distinctive)
- [Scope and Frameworks](#scope-and-frameworks)
- [Repository Contents](#repository-contents)
- [Key Findings Preview](#key-findings-preview)
- [Contact](#contact)

---

## Executive Summary

CareStream Health Technologies provides clinical documentation
and care coordination tools to 85 mid-size healthcare organizations.
Two hospital customers require SOC 2 Type II reports for contract
renewal in 4 months. A third prospect representing $800K ARR will
not sign without one. CareStream has never undergone a SOC 2 audit.

This project documents a full SOC 2 Type II readiness assessment
with HIPAA Security Rule layered in — applied to a platform where
security controls must be designed around clinical workflow realities,
not imposed on top of them.

---

## Why This Assessment Is Distinctive

**Most SOC 2 assessments treat clinical workflows as a constraint.
This one treats them as a design requirement.**

Security controls in clinical environments fail in a specific way:
they compete with patient care. A physician authenticating during
a clinical emergency, a nurse documenting between patient encounters,
a care coordinator managing handoffs under time pressure — these
are not users who will tolerate friction. They will find workarounds.
And in healthcare, workarounds have clinical consequences.

**The clinician workflow pressure lens:**

| Control | Clinical friction it creates | Likely workaround | Actual risk |
|---------|---------------------------|-------------------|------------|
| MFA on every login | Adds 30–60 seconds per session | Shared workstation sessions left open | Unauthorized access to patient records |
| Session timeout after inactivity | Interrupts documentation mid-encounter | Disabling timeout or sharing credentials | PHI exposed on unattended workstations |
| Role-based access restrictions | Blocks access needed for care coordination | Requesting broad access "just in case" | Over-privileged accounts across care team |
| Audit log review requirements | Administrative burden on clinical staff | Delegating to IT without clinical context | Audit logs reviewed without understanding clinical patterns |

**The thesis:** SOC 2 compliance in clinical environments requires
controls designed with clinical staff — not for them. Security
that competes with patient care will always lose.

---

## Scope and Frameworks

**Organization:** CareStream Health Technologies — 95 employees,
Nashville TN, AWS single-region, 85 healthcare organization customers

**Frameworks applied:**

| Framework | Purpose |
|-----------|---------|
| SOC 2 Type II | Primary assurance framework — Security, Availability, Confidentiality, Privacy TSC |
| HIPAA Security Rule | PHI protection — administrative, physical, technical safeguards |
| NIST CSF 2.0 | High-level security posture mapping |

**Trust Service Criteria selected:**

| Criteria | Rationale |
|----------|----------|
| Security | Mandatory — always included |
| Availability | Clinical operations depend on platform access — patient safety implication |
| Confidentiality | PHI must be protected from unauthorized disclosure |
| Privacy | Patient data collection, use, and retention must be governed appropriately |

**Data in scope:**

| Data type | Sensitivity | Primary concern |
|-----------|------------|----------------|
| Patient clinical notes | Critical | Confidentiality + Integrity |
| Medication records and treatment plans | Critical | Confidentiality + Availability |
| Care team communications | High | Confidentiality |
| Patient demographic information | High | Privacy |
| HL7 FHIR API data in transit | Critical | Confidentiality + Integrity |
| Aggregate clinical outcome data | Moderate | Confidentiality |

---

## Repository Contents

| Document | What it covers | Status |
|----------|---------------|--------|
| `README.md` | Project overview and assessment framing | ✅ Complete |
| [`scope-and-context.md`](scope-and-context.md) | Company profile, asset inventory, stakeholder map | ✅ Complete |
| [`risk-assessment.md`](risk-assessment.md) | NIST 800-30 threat and vulnerability analysis | ✅ Complete |
| [`soc2-tsc-assessment.md`](soc2-tsc-assessment.md) | SOC 2 Trust Service Criteria assessed | ✅ Complete |
| [`hipaa-soc2-crosswalk.md`](hipaa-soc2-crosswalk.md) | HIPAA Security Rule mapped to SOC 2 controls | ✅ Complete |
| [`remediation-roadmap.md`](remediation-roadmap.md) | Prioritized findings with clinical workflow considerations | ✅ Complete |
| [`executive-summary.md`](executive-summary.md) | Board-ready one-pager — audit timeline and contract renewal stakes | ✅ Complete |

---

## Key Findings Preview

- **Critical:** No formal offboarding process — terminated employee
  accessed care team messaging 14 months ago; root cause unresolved
- **Critical:** Session management controls absent — shared
  workstation sessions create PHI exposure risk across clinical
  settings
- **Critical:** HL7 FHIR API integrations not formally assessed —
  EHR connections to Epic, Cerner, and Allscripts introduce
  third-party risk not currently managed
- **High:** No formal security awareness training — clinical
  staff handling PHI daily with no security training program

*Full findings, risk scores, and remediation roadmap in the
documents above.*

---

## Contact

**Dara Thomas** — GRC Analyst & Consultant | Human-Centered Risk & Compliance

[LinkedIn](YOUR_LINKEDIN_URL) · dara.thomas.grc@gmail.com · [GitHub Portfolio](https://github.com/DaraStaysCurious)

---

*Part of the [DaraStaysCurious](https://github.com/DaraStaysCurious)
GRC & Cloud Security portfolio.*
*Methodology: [risk-assessment-methodology](https://github.com/DaraStaysCurious/risk-assessment-methodology)*

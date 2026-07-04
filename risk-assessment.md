# Risk Assessment
> The greatest threat to CareStream isn't an external attacker.
> It's a care team that can't access patient records during
> a clinical emergency — and the workarounds that follow.

---

## Table of Contents
- [Executive Summary](#executive-summary)
- [Methodology](#methodology)
- [Threat Identification](#threat-identification)
- [Vulnerability Identification](#vulnerability-identification)
- [Risk Scoring](#risk-scoring)
- [Risk Priority Summary](#risk-priority-summary)
- [Contact](#contact)

---

## Executive Summary

This risk assessment applies NIST 800-30 methodology to CareStream's
clinical documentation environment — with particular attention to
the human behavior patterns that emerge when security controls
compete with care delivery speed.

CareStream's basic technical controls — encryption at rest and
in transit, basic access controls — provide a partial foundation.
But four unresolved issues create significant SOC 2 audit risk:
an unresolved terminated employee access incident, unassessed
HL7 FHIR API integrations, absent session management controls,
and a security awareness training program that doesn't exist.

---

## Methodology

**Framework:** NIST 800-30 — Guide for Conducting Risk Assessments

**Risk scoring:** Likelihood × Exposure × Impact

**Risk levels:**

| Score | Risk Level | Action |
|-------|-----------|--------|
| Very High | Immediate remediation required | Stop / contain |
| High | Remediation within 30 days | Priority action |
| Moderate | Remediation within 90 days | Planned action |
| Low | Monitor | Ongoing awareness |

**Finding sources:**

| Source | Findings generated |
|--------|-------------------|
| Prior incident analysis | Terminated employee access — root cause unresolved |
| Stakeholder interviews | CMO workflow concerns, Privacy Officer gap awareness |
| Infrastructure review | Single region deployment, FHIR integrations unassessed |
| Documentation review | No offboarding process, no security training, no IR plan |
| Clinical workflow observation | Session management gaps, shared workstation risk |

---

## Threat Identification

**Five threat categories identified for CareStream's environment.**

### Threat 1: Unauthorized PHI Access — Insider and Post-Termination

| Element | Detail |
|---------|--------|
| **Threat source** | Current employees with excessive access, terminated employees with unrevoked access |
| **Threat event** | Unauthorized access to patient clinical notes, medication records, care communications |
| **Why it's the highest priority** | Demonstrated — terminated employee accessed care messaging 14 months ago; root cause unresolved; auditor will examine immediately |
| **Human behavior angle** | Clinical staff request broad access "just in case" — over-privileged accounts are the norm, not the exception |
| **Affected assets** | Patient clinical notes, care team communications, medication records |

---

### Threat 2: Clinical Workflow Workarounds — Session and Authentication

| Element | Detail |
|---------|--------|
| **Threat source** | Clinical staff bypassing authentication controls under time pressure |
| **Threat event** | Shared workstation sessions left open — unauthorized access to patient records by non-care staff |
| **Why it's critical** | Clinical environments create structural pressure to bypass session controls — workarounds are rational responses to friction, not recklessness |
| **Human behavior angle** | A physician interrupted mid-documentation by a session timeout will disable the timeout — patient care comes first |
| **Affected assets** | All PHI accessible via shared clinical workstations |

---

### Threat 3: Third-Party EHR Integration Risk

| Element | Detail |
|---------|--------|
| **Threat source** | Unassessed security controls on HL7 FHIR connections to Epic, Cerner, Allscripts |
| **Threat event** | PHI exposed or corrupted through inadequately secured EHR integration |
| **Why it's high priority** | Restricted PHI transmitted via FHIR integrations — security controls on these connections never formally assessed |
| **Human behavior angle** | Engineering team treats EHR integrations as technical features, not security perimeter extensions |
| **Affected assets** | HL7 FHIR API connections, all PHI in transit between CareStream and EHR systems |

---

### Threat 4: Availability Failure — Clinical Operations Impact

| Element | Detail |
|---------|--------|
| **Threat source** | Infrastructure failure, ransomware, AWS single-region outage |
| **Threat event** | CareStream platform unavailable during active clinical operations |
| **Why it's high priority** | Clinical staff depend on platform for care documentation and coordination — outage has direct patient care implications |
| **Human behavior angle** | Clinical staff revert to paper documentation during outages — creating reconciliation gaps and data integrity issues when systems restore |
| **Affected assets** | AWS production environment, RDS database, web and mobile applications |

---

### Threat 5: External Attack — PHI Breach

| Element | Detail |
|---------|--------|
| **Threat source** | External attackers targeting healthcare SaaS — ransomware groups, data brokers |
| **Threat event** | Platform breach exposing PHI across all 85 customer organizations simultaneously |
| **Why it's elevated** | Healthcare is the most targeted industry for ransomware; PHI has high dark web value; no formal vulnerability management program |
| **Human behavior angle** | Security team capacity is limited — alert fatigue and prioritization gaps increase external attack surface |
| **Affected assets** | All customer PHI, clinical notes, medication records, treatment plans |

---

## Vulnerability Identification

| Vulnerability | Type | Threat category | Severity |
|---------------|------|----------------|----------|
| No formal offboarding process — root cause unresolved | Process | Insider / post-termination | Critical |
| Session management controls absent | Technical | Clinical workarounds | Critical |
| HL7 FHIR integrations unassessed | Technical | Third-party risk | Critical |
| No security awareness training | People | All categories | Critical |
| Over-privileged clinical staff accounts | Technical | Insider access | High |
| No formal access review process | Process | Insider access | High |
| Single AWS region — no redundancy | Technical | Availability | High |
| No disaster recovery plan | Process | Availability | High |
| No incident response plan | Process | External attack | High |
| Privacy Officer program in early stages | Process | Privacy | High |
| No vulnerability management program | Process | External attack | High |
| EHR integration credentials not formally managed | Technical | Third-party risk | High |
| No formal change management process | Process | All categories | Moderate |
| Audit log review process undefined | Process | All categories | Moderate |

---

## Risk Scoring

| Risk | Likelihood | Exposure | Impact | Risk Level |
|------|-----------|---------|--------|-----------|
| Unauthorized PHI access — insider | High | High | Very High | **Very High** |
| Session workarounds — shared workstations | High | High | High | **Very High** |
| FHIR integration breach | Moderate | High | Very High | **Very High** |
| Platform unavailability — clinical impact | Moderate | High | Very High | **High** |
| External PHI breach | Moderate | High | Very High | **High** |
| Over-privileged accounts | High | High | High | **High** |
| No DR plan — extended outage | Low | High | Very High | **High** |

---

## Risk Priority Summary

**Four findings require immediate action before SOC 2
observation period can begin.**

| Priority | Finding | Rationale |
|----------|---------|-----------|
| 1 | Implement formal offboarding process — revoke access immediately on termination | Demonstrated failure — auditor will examine first |
| 2 | Implement session management controls designed for clinical workflows | Critical workaround risk — must balance security with care delivery speed |
| 3 | Formally assess all HL7 FHIR integrations | Restricted PHI in transit through unassessed connections |
| 4 | Launch security awareness training — clinical workflow focused | No training program of any kind — SOC 2 auditor will flag immediately |

*Full TSC assessment and remediation roadmap in subsequent documents.*

---

## Contact

**Dara Thomas** — GRC Analyst & Consultant | Human-Centered Risk & Compliance

[LinkedIn](YOUR_LINKEDIN_URL) · dara.thomas.grc@gmail.com · [GitHub Portfolio](https://github.com/DaraStaysCurious)

---

*Part of the [grc-carestream-soc2](../README.md) repository.*
*Next: [soc2-tsc-assessment.md](soc2-tsc-assessment.md)*

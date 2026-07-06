# HIPAA and SOC 2 Crosswalk
> One remediation. Two frameworks closed.
> Where HIPAA and SOC 2 overlap — and where they don't.

---

## Table of Contents
- [Executive Summary](#executive-summary)
- [Framework Comparison](#framework-comparison)
- [Crosswalk — HIPAA to SOC 2](#crosswalk)
- [CareStream-Specific Findings](#carestream-specific-findings)
- [Unified Remediation Opportunities](#unified-remediation-opportunities)
- [Contact](#contact)

---

## Executive Summary

CareStream faces dual compliance obligations — SOC 2 Type II
for enterprise customer requirements and HIPAA for PHI handling.
This document maps HIPAA Security Rule safeguards onto SOC 2
Trust Service Criteria controls, identifying where a single
remediation closes gaps in both frameworks simultaneously.

**Key finding:** 16 of CareStream's most critical remediations
satisfy both SOC 2 and HIPAA requirements. Unified remediation
reduces total implementation effort by an estimated 45%.

---

## Framework Comparison

**Two frameworks. One focus: protecting health information.**

| Element | HIPAA Security Rule | SOC 2 Type II |
|---------|--------------------|--------------| 
| **Who created it** | US Department of Health and Human Services | AICPA |
| **Who must comply** | Covered entities and business associates handling PHI | B2B SaaS companies seeking customer assurance |
| **Enforcement** | Federal law — HHS Office for Civil Rights | Market-driven — customers require it |
| **Audit mechanism** | HHS investigation or breach trigger | Independent CPA firm audit |
| **Output** | HIPAA compliance — no formal certificate | SOC 2 Type II report shared with customers |
| **Focus** | Protecting PHI specifically | Broad security, availability, confidentiality, privacy |

**The relationship:**
HIPAA tells CareStream what PHI protections are legally required.
SOC 2 tells CareStream's customers whether those protections —
and broader security controls — are actually working. The two
frameworks are complementary, not redundant.

---

## Crosswalk

**HIPAA Security Rule safeguards mapped to SOC 2 TSC controls.**

### Administrative Safeguards → Security TSC

| HIPAA requirement | SOC 2 control | Current state | Gap rating |
|------------------|--------------|---------------|-----------|
| Security management — risk analysis | CC3 — Risk assessment | Completed — this engagement | ⚠️ Partial |
| Security management — risk management | CC1 — Control environment | No formal policies | ❌ Critical |
| Assigned security responsibility | CC1 — Roles and responsibilities | CTO informally — undocumented | ❌ Critical |
| Workforce training and awareness | CC1 — Security awareness | None | ❌ Critical |
| Access management — authorization | CC6 — Access provisioning | Informal — over-privileged accounts | ⚠️ Partial |
| Workforce clearance | CC6 — Access provisioning | No formal background screening | ❌ High |
| Termination procedures | CC6 — Access removal | ❌ Demonstrated failure | ❌ Critical |
| Access establishment and modification | CC6 — Access reviews | No formal review process | ❌ Critical |
| Security incident procedures | CC7 — Incident response | None | ❌ Critical |
| Contingency plan — DR | A1 — Availability | No DR plan | ❌ Critical |
| Contingency plan — backup | A1 — Availability | Partial — untested | ⚠️ Partial |
| Evaluation — periodic review | CC4 — Monitoring | None | ❌ High |

> **HIPAA-specific requirement — no direct SOC 2 equivalent:**
> Business Associate Agreements required with EHR integration
> partners — Epic, Cerner, Allscripts. SOC 2 addresses vendor
> risk broadly — HIPAA requires specific BAA contracts.

---

### Physical Safeguards → Security TSC

| HIPAA requirement | SOC 2 control | Current state | Gap rating |
|------------------|--------------|---------------|-----------|
| Facility access controls | CC6 — Physical access | N/A — AWS hosted | AWS responsible |
| Workstation use policy | CC6 — Logical access | No workstation policy | ❌ High |
| Workstation security | CC6 — Logical access | No endpoint security policy | ⚠️ Partial |
| Device and media controls | CC6 — Logical access | No device management policy | ❌ High |

---

### Technical Safeguards → Security and Confidentiality TSC

| HIPAA requirement | SOC 2 control | Current state | Gap rating |
|------------------|--------------|---------------|-----------|
| Access controls — unique user IDs | CC6 — Access management | Partial — some shared accounts | ⚠️ Partial |
| Access controls — emergency access | CC6 — Privileged access | No formal emergency access procedure | ❌ High |
| Access controls — automatic logoff | CC6 — Session management | ❌ Absent | ❌ Critical |
| Access controls — encryption | C1 — Confidentiality | TLS in transit, RDS at rest | ✅ Implemented |
| Audit controls — activity logging | CC7 — System operations | Partial — no formal log review | ⚠️ Partial |
| Integrity controls — PHI alteration | CC6, C1 — Access and confidentiality | No integrity verification controls | ❌ Critical |
| Transmission security — encryption | C1 — Confidentiality | TLS implemented | ✅ Implemented |
| FHIR integration security | C1, CC9 — Confidentiality, vendor risk | ❌ Unassessed | ❌ Critical |

---

## CareStream-Specific Findings

**Five findings unique to CareStream's clinical PHI context:**

| Finding | HIPAA requirement | SOC 2 equivalent | Rating |
|---------|------------------|-----------------|--------|
| No BAAs with EHR integration partners | BAA requirement | CC9 — Vendor risk | **Critical** |
| Terminated employee retained PHI access | Termination procedures | CC6 — Access removal | **Critical** |
| Session timeout absent — shared clinical workstations | Automatic logoff | CC6 — Session management | **Critical** |
| No privacy notice for patients | Privacy Rule | Privacy TSC — P1 | **High** |
| Clinical staff over-privileged — minimum necessary violated | Minimum necessary principle | CC6 — Access restriction | **High** |

**The clinical session management challenge:**

This finding sits at the intersection of HIPAA, SOC 2, and
clinical workflow design — making it the most complex finding
in this assessment.

| Requirement | What it demands |
|-------------|----------------|
| HIPAA | Automatic logoff after defined period of inactivity |
| SOC 2 | Session controls operating consistently over time |
| Clinical workflow | Uninterrupted access during active patient care |

**Recommended approach:** Context-aware session management —
sessions remain active during documented clinical activity
and timeout only during genuine inactivity. Designed with
clinical staff input before implementation. This satisfies
HIPAA and SOC 2 while minimizing care delivery friction.

---

## Unified Remediation Opportunities

**Where one fix closes gaps in both frameworks:**

| Remediation | HIPAA safeguards closed | SOC 2 controls closed |
|-------------|------------------------|----------------------|
| Implement formal offboarding — immediate access revocation | Termination procedures | CC6 — Access removal |
| Implement context-aware session management | Automatic logoff | CC6 — Session management |
| Establish security awareness training — clinical focused | Workforce training | CC1 — Security awareness |
| Formalize security roles and responsibilities | Assigned security responsibility | CC1 — Roles |
| Implement formal access review process | Access management | CC6 — Access reviews |
| Establish incident response plan | Security incident procedures | CC7 — Incident response |
| Establish and test disaster recovery plan | Contingency plan | A1 — Availability |
| Implement vulnerability management program | Security management | CC7 — System operations |
| Implement formal change management | Security management | CC8 — Change management |
| Execute BAAs with EHR integration partners | BAA requirement | CC9 — Vendor risk |
| Formally assess FHIR integrations | Security management | CC9, C1 — Vendor risk, confidentiality |
| Establish data retention and disposal policy | Device and media controls | C1 — Confidentiality |
| Implement privileged access management | Access controls | CC6 — Privileged access |
| Define and enforce minimum necessary access | Minimum necessary | CC6 — Access restriction |
| Establish privacy notice and consent process | Privacy Rule | Privacy TSC — P1 |
| Implement audit log review process | Audit controls | CC7 — System operations |

**16 unified remediations — each closing at least one HIPAA
requirement and one SOC 2 control simultaneously.**

---

## Contact

**Dara Thomas** — GRC Analyst & Consultant | Human-Centered Risk & Compliance

[LinkedIn](YOUR_LINKEDIN_URL) · dara.thomas.grc@gmail.com · [GitHub Portfolio](https://github.com/DaraStaysCurious)

---

*Part of the [grc-carestream-soc2](../README.md) repository.*
*Next: [remediation-roadmap.md](remediation-roadmap.md)*

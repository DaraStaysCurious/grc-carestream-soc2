# Scope and Context
> Clinical documentation platforms sit at the intersection
> of two competing imperatives: protect patient data and
> enable care delivery. This assessment starts there.

---

## Table of Contents
- [Company Profile](#company-profile)
- [SOC 2 Audit Context](#soc2-audit-context)
- [Asset Inventory](#asset-inventory)
- [Data Classification](#data-classification)
- [Stakeholder Map](#stakeholder-map)
- [Assessment Constraints](#assessment-constraints)
- [Contact](#contact)

---

## Company Profile

**CareStream Health Technologies** — B2B SaaS clinical
documentation and care coordination platform serving mid-size
healthcare organizations.

| Attribute | Detail |
|-----------|--------|
| **Headquarters** | Nashville, TN — fully remote |
| **Employees** | 95 |
| **Customers** | 85 healthcare organizations |
| **Customer types** | Community hospitals, outpatient clinics, rehabilitation centers, occupational health programs |
| **Revenue** | $8M ARR — Series A, growing 35% YoY |
| **Infrastructure** | AWS — single region, us-east-1 |
| **Integrations** | HL7 FHIR API — Epic, Cerner, Allscripts |
| **Prior SOC 2** | None — first audit |
| **Privacy Officer** | Recently hired — HIPAA compliance program in early stages |

**Why SOC 2 Type II now:**
Two hospital customers require SOC 2 Type II reports for contract
renewal in 4 months. A third prospect representing $800K ARR will
not sign without a current report. CareStream has never undergone
a SOC 2 audit — this engagement initiates the readiness process.

**Prior incident:**
14 months ago — a terminated clinical staff employee retained
access to a care team messaging thread for 3 weeks post-termination.
Discovered during a routine access review. No PHI confirmed
exfiltrated. Root cause: no formal offboarding process for
clinical staff accounts. Root cause remains unresolved.

---

## SOC 2 Audit Context

**Understanding CareStream's SOC 2 obligations:**

| Element | Detail |
|---------|--------|
| Report type | SOC 2 Type II — controls operating effectively over time |
| Audit period | 6 months minimum — must begin immediately to meet 4-month deadline |
| Auditor | Independent CPA firm — not yet selected |
| Trust Service Criteria | Security, Availability, Confidentiality, Privacy |
| Report distribution | Shared with hospital customers under NDA |

**Type I vs. Type II — why Type II is required:**

| | Type I | Type II |
|-|--------|---------|
| What it proves | Controls designed correctly | Controls operating effectively over time |
| Hospital customer expectation | Acceptable for early-stage | Required for enterprise contracts |
| CareStream's obligation | — | Required by two existing customers |

**Critical timeline constraint:**
SOC 2 Type II requires a minimum 6-month observation period.
CareStream's contract renewal deadline is 4 months away. This
means the observation period must begin immediately — and
CareStream will need to negotiate a bridge arrangement with
customers while the full Type II report is being completed.

---

## Asset Inventory

**Information assets ranked by criticality:**

| Asset | Type | Criticality | Primary concern |
|-------|------|------------|----------------|
| Patient clinical notes | Data | Critical | Confidentiality + Integrity |
| Medication records and treatment plans | Data | Critical | Confidentiality + Availability |
| Care team communications | Data | High | Confidentiality |
| Patient demographic information | Data | High | Privacy |
| HL7 FHIR API connections | System | Critical | Confidentiality + Integrity |
| AWS production environment | Infrastructure | Critical | Availability |
| Web application | System | Critical | Availability + Integrity |
| Mobile documentation app | System | High | Confidentiality + Availability |
| RDS database — encrypted at rest | Data | Critical | Confidentiality + Integrity |
| Clinical staff user accounts | Data | High | Confidentiality |
| EHR integration credentials | Data | Critical | Confidentiality |

---

## Data Classification

**CareStream data classified by sensitivity:**

| Classification | Definition | Examples |
|---------------|-----------|---------|
| **Restricted** | PHI — breach causes serious patient and regulatory harm | Clinical notes, medication records, treatment plans, care communications |
| **Confidential** | Sensitive organizational data | Patient demographics, aggregate outcomes, customer contracts |
| **Internal** | Internal use only | System configuration, operational logs, internal communications |
| **Public** | No sensitivity | Marketing materials, product documentation |

**HL7 FHIR API note:**
Data transmitted via HL7 FHIR integrations to Epic, Cerner,
and Allscripts includes Restricted PHI. These integrations
have not been formally assessed for security controls —
representing a significant third-party risk gap.

---

## Stakeholder Map

| Stakeholder | Role | Primary concern | Assessment relevance |
|-------------|------|----------------|---------------------|
| CEO | Executive sponsor | Contract renewals, $800K prospect | Audit timeline, resource authorization |
| CTO | Technical owner | Security architecture, audit readiness | Control implementation authority |
| Chief Medical Officer | Clinical owner | Care delivery speed, clinician experience | Human factors — workflow vs. security tension |
| Head of Engineering | Technical implementation | System architecture, API integrations | Control deployment, FHIR assessment |
| Privacy Officer | HIPAA compliance | PHI handling, patient rights | HIPAA crosswalk, privacy controls |
| Customer Success Lead | Customer relationships | Hospital contract renewals | Customer-facing risk communication |

**Key finding from stakeholder interviews:**
The Chief Medical Officer has expressed explicit concern that
security controls will slow clinical workflows. This is
documented as both a predisposing condition and a design
requirement — controls that create clinical friction will
be routed around by care staff under time pressure. Every
control recommendation in this assessment has been evaluated
against clinical workflow impact before finalization.

---

## Assessment Constraints

| Constraint | Impact |
|------------|--------|
| 4-month contract renewal deadline | Type II observation period cannot be completed in time — bridge arrangement required |
| No prior SOC 2 audit | No baseline — gap analysis will be extensive |
| HL7 FHIR integrations unassessed | Third-party risk across Epic, Cerner, Allscripts connections unknown |
| Terminated employee incident unresolved | Root cause open 14 months — auditor will examine |
| CMO resistance to friction-creating controls | Control design must account for clinical workflow impact |
| Single AWS region | No geographic redundancy — availability risk for Availability TSC |
| Privacy Officer recently hired | HIPAA compliance program in early stages — gaps expected |

---

## Contact

**Dara Thomas** — GRC Analyst & Consultant | Human-Centered Risk & Compliance

[LinkedIn](YOUR_LINKEDIN_URL) · dara.thomas.grc@gmail.com · [GitHub Portfolio](https://github.com/DaraStaysCurious)

---

*Part of the [grc-carestream-soc2](../README.md) repository.*
*Next: [risk-assessment.md](risk-assessment.md)*

# SOC 2 Trust Service Criteria Assessment
> SOC 2 doesn't ask whether controls exist.
> It asks whether they work — consistently, over time,
> in the environment where clinicians actually operate.

---

## Table of Contents
- [Executive Summary](#executive-summary)
- [Assessment Approach](#assessment-approach)
- [Security TSC](#security-tsc)
- [Availability TSC](#availability-tsc)
- [Confidentiality TSC](#confidentiality-tsc)
- [Privacy TSC](#privacy-tsc)
- [TSC Maturity Summary](#tsc-maturity-summary)
- [Contact](#contact)

---

## Executive Summary

CareStream is being assessed against four Trust Service Criteria:
Security, Availability, Confidentiality, and Privacy. Basic
technical controls exist — encryption at rest and in transit,
basic access controls — but significant gaps exist across all
four criteria.

The most critical gaps are in Security — specifically access
management and session controls — and Availability, where a
single-region AWS deployment with no disaster recovery plan
creates unacceptable clinical availability risk.

**TSC maturity summary:**

| Criteria | Maturity | Critical gaps |
|----------|---------|--------------|
| Security | Partial | Access management, session controls, offboarding |
| Availability | Minimal | No DR plan, single region, no SLA defined |
| Confidentiality | Partial | FHIR integrations unassessed, over-privileged accounts |
| Privacy | Initiated | Privacy program in early stages, no formal privacy notice |

---

## Assessment Approach

**SOC 2 Type II assesses controls over a period of time —
not just at a point in time.**

| Element | Definition |
|---------|-----------|
| Observation period | Minimum 6 months — controls must operate consistently throughout |
| Auditor expectation | Evidence of consistent control operation — logs, reviews, documented procedures |
| Pass/fail criteria | Controls designed appropriately AND operating effectively |
| Clinical context | Every control assessed against clinical workflow impact before finalization |

**For each TSC, three determinations are made:**

| Status | Definition |
|--------|-----------|
| ✅ Implemented | Control in place and operating effectively |
| ⚠️ Partial | Control exists but gaps remain |
| ❌ Absent | Control not implemented |

---

## Security TSC

**Protecting against unauthorized access — the only mandatory
Trust Service Criterion.**

### CC1 — Control Environment

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Security policies defined | None | No formal security policy framework | ❌ |
| Security roles and responsibilities | Informal | CTO informally owns security — undocumented | ❌ |
| Board oversight of security | None | No formal security reporting to board | ❌ |
| Security awareness training | None | No program of any kind | ❌ |

---

### CC2 — Communication and Information

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Security objectives communicated | None | No formal communication of security expectations | ❌ |
| Security incidents reported | Informal | No formal incident reporting process | ❌ |
| External communications managed | None | No formal process for communicating with customers on security matters | ⚠️ |

---

### CC3 — Risk Assessment

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Risk assessment process | Completed — this engagement | No ongoing process existed prior | ⚠️ |
| Risk identified and analyzed | Completed — this engagement | Point-in-time only — no continuous process | ⚠️ |
| Fraud risk considered | None | No fraud risk assessment | ❌ |

---

### CC4 — Monitoring

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Security monitoring program | None | No SIEM, no alerting, no anomaly detection | ❌ |
| Internal audit function | None | No internal audit capability | ❌ |
| Management review of controls | Informal | No formal review cadence | ❌ |

---

### CC5 — Control Activities

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Policies and procedures | None | No documented security procedures | ❌ |
| Technology controls implemented | Partial | Encryption in place — access controls incomplete | ⚠️ |
| Change management | None | No formal change management process | ❌ |

---

### CC6 — Logical and Physical Access

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Access provisioning | Informal | No formal provisioning process — clinical staff request broad access | ⚠️ |
| Access removal — termination | ❌ Demonstrated failure | Terminated employee retained access 14 months ago — root cause unresolved | ❌ |
| MFA enforced | Partial | MFA in place for some access — not enforced consistently | ⚠️ |
| Session management | ❌ Absent | No session timeout controls — shared workstation risk | ❌ |
| Access reviews | None | No formal periodic access review process | ❌ |
| Privileged access management | None | No PAM program — over-privileged accounts across clinical staff | ❌ |

**Clinical workflow note:**
Session management controls must be designed with clinical staff
input. A 15-minute timeout that interrupts active documentation
will be disabled. A context-aware timeout that recognizes active
clinical use is more likely to be adopted and maintained.

---

### CC7 — System Operations

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Vulnerability management | None | No scanning or patch management program | ❌ |
| Malware protection | Basic | Basic endpoint protection — no EDR | ⚠️ |
| Security event monitoring | None | No log review process or alerting | ❌ |
| Incident response | None | No IR plan — prior incident handled informally | ❌ |

---

### CC8 — Change Management

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Change management process | None | No formal process — changes deployed informally | ❌ |
| Testing before deployment | Informal | No formal testing requirements | ⚠️ |
| Emergency change procedures | None | Not defined | ❌ |

---

### CC9 — Risk Mitigation

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Vendor risk management | None | FHIR integrations unassessed — Epic, Cerner, Allscripts | ❌ |
| Business disruption risk | None | No BCP or DR plan | ❌ |

---

## Availability TSC

**System available for operation as committed to customers.**

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Availability commitments defined | None | No SLA defined — no uptime commitments documented | ❌ |
| Performance monitoring | Partial | Basic AWS monitoring — no formal SLA tracking | ⚠️ |
| Disaster recovery plan | None | No DR plan — single region deployment | ❌ |
| Backup and recovery | Partial | RDS automated backups — not formally tested | ⚠️ |
| Geographic redundancy | None | Single AWS region — us-east-1 only | ❌ |
| Incident response for availability | None | No process for managing availability incidents | ❌ |
| Capacity planning | None | No formal capacity management process | ❌ |

**Clinical impact note:**
CareStream's single-region deployment creates a scenario where
an AWS us-east-1 outage — which has occurred historically —
takes CareStream offline simultaneously for all 85 healthcare
customers. Clinical staff revert to paper documentation during
outages, creating reconciliation gaps and data integrity issues
when systems restore. This is an Availability TSC failure with
direct patient care implications.

---

## Confidentiality TSC

**Information designated as confidential is protected.**

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Confidential information identified | Partial | Data classification completed — this engagement | ⚠️ |
| Confidentiality agreements | Unknown | NDAs with staff and customers — not formally verified | ⚠️ |
| Access to confidential information restricted | Partial | Basic access controls — over-privileged accounts persist | ⚠️ |
| Confidential information protected in transit | ✅ | TLS encryption implemented | ✅ |
| Confidential information protected at rest | ✅ | RDS encryption at rest implemented | ✅ |
| FHIR integration data protection | ❌ | Integrations unassessed — PHI in transit not formally verified | ❌ |
| Confidential information disposal | None | No data retention or disposal policy | ❌ |
| Third-party confidentiality obligations | None | No formal vendor confidentiality program | ❌ |

**Strongest area:** Confidentiality has two fully implemented
controls — TLS in transit and RDS encryption at rest. These
provide a partial foundation that Security and Availability
lack entirely.

---

## Privacy TSC

**Personal information collected, used, and retained appropriately.**

| Control | Current state | Gap | Status |
|---------|---------------|-----|--------|
| Privacy notice | None | No formal privacy notice for patients or customers | ❌ |
| Consent management | None | No formal consent process defined | ❌ |
| Data collection limited to stated purpose | Unknown | No formal data minimization policy | ❌ |
| PHI use limited to permitted purposes | Partial | HIPAA guidance followed informally — no formal policy | ⚠️ |
| Data retention policy | None | No retention or deletion schedule defined | ❌ |
| Data subject rights process | None | No process for responding to patient data requests | ❌ |
| Privacy incident response | None | No privacy-specific incident response process | ❌ |
| Privacy Officer program | Initiated | Recently hired Privacy Officer — program in early stages | ⚠️ |
| Third-party privacy obligations | None | No formal privacy requirements for EHR integration partners | ❌ |

**Note on Privacy Officer:**
The recently hired Privacy Officer is CareStream's most important
asset for Privacy TSC compliance. The assessment recommends
prioritizing Privacy Officer enablement — budget, authority,
and tooling — before attempting to build privacy controls
without dedicated ownership.

---

## TSC Maturity Summary

**CareStream TSC maturity at a glance:**

| Criteria | Implemented | Partial | Absent | Maturity |
|----------|------------|---------|--------|---------|
| Security | 0 | 6 | 14 | 🔴 Minimal |
| Availability | 0 | 2 | 5 | 🔴 Minimal |
| Confidentiality | 2 | 4 | 4 | 🟡 Partial |
| Privacy | 0 | 2 | 7 | 🔴 Initiated |

**Target maturity — post remediation:**

| Criteria | Target | Timeline |
|----------|--------|---------|
| Security | 🟢 Defined | 6 months |
| Availability | 🟡 Partial | 6 months |
| Confidentiality | 🟢 Defined | 4 months |
| Privacy | 🟡 Partial | 6 months |

---

## Contact

**Dara Thomas** — GRC Analyst & Consultant | Human-Centered Risk & Compliance

[LinkedIn](YOUR_LINKEDIN_URL) · dara.thomas.grc@gmail.com · [GitHub Portfolio](https://github.com/DaraStaysCurious)

---

*Part of the [grc-carestream-soc2](../README.md) repository.*
*Next: [hipaa-soc2-crosswalk.md](hipaa-soc2-crosswalk.md)*

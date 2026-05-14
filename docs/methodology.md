# Methodology — COSO + COBIT + IIA Three Lines + TCFD Crosswalk

This document explains how the four frameworks fit together in this case study, and why the resulting control structure is **functionally analogous to 21 CFR Part 11 pharma data-integrity requirements**.

---

## 1. The four frameworks at a glance

| Framework | Authoring body | What it tells you | What it does NOT tell you |
|---|---|---|---|
| **COSO Internal Control (2013)** | Committee of Sponsoring Organizations | 5 components × 17 principles — the *control objectives* you need to satisfy | How to implement the controls in IT systems |
| **COBIT 2019** | ISACA | The IT-process *implementation* layer — 40 governance/management processes with maturity scoring | Generic business-process controls outside IT |
| **IIA Three Lines Model (2020)** | Institute of Internal Auditors | The *role structure* — who owns risk vs. monitors it vs. independently assures it | Specific controls or technology |
| **TCFD-aligned risk taxonomy** | TCFD Recommendations | A *language for risk classification* — transition / physical / regulatory / operational | A scoring methodology (we use 5×5) |

The case study uses **all four**: COSO for control selection, COBIT for IT-process maturity, IIA for organizational role design, TCFD for risk classification.

---

## 2. COSO 17 Principles → controls in this case study

| COSO Component | Principle | Control(s) implemented |
|---|---|---|
| Control Environment | 1. Commitment to integrity | C-01 SoD Policy |
| Control Environment | 2. Independent oversight | C-02 Payment Authorization Separation |
| Control Environment | 3. Structures & authorities | C-03 PDA Device Accountability |
| Risk Assessment | 7. Identifies & analyzes risk | C-04 Cargo Risk Classification |
| Risk Assessment | 8. Considers fraud risk | C-05 Billing Anomaly Detection |
| Control Activities | 10. Selects & develops control activities | C-06 Film-Wrap SOP, C-07 PDA Scan |
| Control Activities | 11. Selects & develops general IT controls | C-08 Dual Verification, C-09 WMS Audit |
| Control Activities | 12. Deploys through policies | C-10 Insurance Claim Protocol |
| Information & Communication | 14. Communicates internally | C-11 BI Dashboard |
| Information & Communication | 15. Communicates externally | C-12 Data Handoff Standard |
| Monitoring | 17. Evaluates & communicates deficiencies | C-13 Daily Outbound + Weekly Anomaly Review |

See `data/control_register.csv` for the full 13-control register with evidence references.

---

## 3. COBIT 2019 — 8 processes uplifted

CMM = Capability Maturity Model (0 = non-existent → 5 = optimized).

| COBIT code | Process | Before | After | Δ |
|---|---|---|---|---|
| APO01 | Manage IT Management Framework | 0 | 3 | +3 |
| APO12 | Manage Risk | 1 | 3 | +2 |
| APO13 | Manage Security | 1 | 3 | +2 |
| BAI09 | Manage Assets | 1 | 3 | +2 |
| DSS01 | Manage Operations | 1 | 4 | +3 |
| DSS05 | Manage Security Services | 1 | 4 | +3 |
| MEA01 | Monitor, Evaluate & Assess Performance | 0 | 4 | +4 |
| MEA03 | Monitor Regulatory Compliance | 1 | 3 | +2 |
| **Average** | | **1.0** | **3.5** | **+2.5** |

See `data/cobit_maturity.csv` for evidence per process.

---

## 4. IIA Three Lines Model — 5 stakeholders mapped

The model intentionally separates risk *ownership* (1st line) from risk *monitoring* (2nd line) from *independent assurance* (3rd line). Each line has independence from the line above.

| Line | Function | Stakeholders in this case study |
|---|---|---|
| 1st — Operational management | Owns & manages risk daily | Supplier · Vendor · Carrier · Warehouse Ops |
| 2nd — Risk & compliance | Designs & monitors controls | SoD Policy Owner · BI Cost Monitoring · WMS Audit |
| 3rd — Independent assurance | Independent audit/verification | Receiver (downstream check) · SQL Audit Trail · Weekly Anomaly Review |

See `data/three_lines_mapping.csv`.

---

## 5. TCFD-aligned risk classification — 12 risks

The 12 risks in `data/risk_register.csv` are classified using TCFD's taxonomy:

- **Transition risk** (policy/regulation/market shifts) — e.g., R-12 Payment authorization conflict.
- **Physical risk** (acute/chronic environmental) — e.g., not the primary risk class in this case study, but applicable in cold-chain analog.
- **Regulatory risk** — e.g., R-04 Amazon FBA rejection.
- **Operational risk** — e.g., R-05 Missing POD, R-07 Driver no-show.
- **Financial risk** — e.g., R-01 Unauthorized inventory adjustment, R-02 Carrier billing overcharge.

Each risk is scored 1–5 on **likelihood** and **impact** for an inherent score 1–25; after controls, residual score is re-scored.

---

## 6. Why this maps cleanly to 21 CFR Part 11 (pharma)

**21 CFR Part 11** is the FDA's electronic-records / electronic-signatures rule for GxP-regulated environments. Its core requirements:

| 21 CFR Part 11 requirement | Analog in this case study |
|---|---|
| Audit trails — secure, computer-generated, time-stamped | SQL audit trail (C-07, C-09); 8-month archive |
| User authentication & access controls | ERP role-based access (C-02, C-03) |
| Segregation of authority | SoD remediation (C-01, C-02) |
| Electronic signatures with non-repudiation | Counter-signature workflow on payment release (C-02) |
| Operational controls — copies of records | Dual verification on outbound (C-08); POD requirement (C-10) |
| Validation of systems | Weekly WMS metadata audit (C-09); SOP documentation (C-06, C-07) |

**The analog is structural, not regulatory.** This case study was implemented in a logistics warehouse, not a GxP facility. The point: the **control-design discipline** transfers cleanly — which is why audit teams, pharma IT auditors, and J&J Tech/Risk/Governance evaluators recognize the same patterns at first glance.

---

## 7. What I'd do differently in a GxP-validated environment

- Add formal CSV (Computer System Validation) / CSA documentation per ICH Q9 risk-based approach.
- ALCOA+ (Attributable, Legible, Contemporaneous, Original, Accurate + Complete, Consistent, Enduring, Available) explicit tagging on every batch record.
- E-signature manifest meeting 21 CFR Part 11 §11.50/§11.70 (signed text + meaning + date/time/UTC).
- Periodic system revalidation cadence and impact-assessment-driven change control.

These are the *additional* layers regulated pharma requires; the underlying control-structure pattern is the same.

---

**Lunarix Technologies LLC** · Yiduo Xiao · [yijimu@lunariduo.com](mailto:yijimu@lunariduo.com)

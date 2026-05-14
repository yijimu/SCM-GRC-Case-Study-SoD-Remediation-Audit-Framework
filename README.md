# SCM GRC Case Study — SoD Remediation & Audit Framework

> An 8-month live GRC implementation in a 5-stakeholder supply-chain operation. Built end-to-end: SoD remediation in ERP, SQL audit trail across 5 stakeholders, COSO/COBIT/IIA Three Lines mapping, and TCFD-aligned risk register. **Structurally analogous to 21 CFR Part 11 pharma data integrity controls.**

**Live case study:** [lunariduo.com/GRC.html](https://lunariduo.com/GRC.html)
**Author:** Yiduo Xiao · Lunarix Technologies LLC · [yijimu@lunariduo.com](mailto:yijimu@lunariduo.com)
**Frameworks:** COSO Internal Control (2013) · COBIT 2019 · IIA Three Lines Model (2020)

---

## The story in one paragraph

Inside a 5-stakeholder logistics operation, a dispatch coordinator was both **negotiating freight rates with carriers** and **approving payment release** in the ERP — textbook Segregation of Duties violation, ~$28K/month financial exposure with no second-eye check. I restructured the ERP role permissions to hard-separate rate negotiation from payment approval, added mandatory counter-signature, documented the SoD policy, and ran a 3-week ERP access audit to verify no other dual-role conflicts existed. The audit pattern uncovered **3 more SoD conflicts** — all remediated. **−15% unauthorized inventory adjustment risk · zero payment disputes attributable to authorization conflict post-implementation.**

## Headline metrics

| Metric | Result |
|---|---|
| SoD conflicts remediated | **4 / 4** |
| Average risk reduction (inherent → residual) | **−74%** |
| Billing dispute trend | **−12%** |
| COBIT 2019 CMM maturity | **1.0 → 3.5** average uplift across 8 processes |
| Insurance claim asset recovery | **100% (3 of 3 claims, ~$22K recovered)** |
| FBA packaging rejection rate post-SOP | **0 incidents** |

## Why this matters for pharma & healthcare

The control-design pattern in this case study is **structurally analogous to 21 CFR Part 11 data-integrity requirements** in pharma manufacturing — the same separation principles, the same evidence-chain requirements, the same independent-review cadence. This is why the methodology transfers cleanly to:

- J&J Tech, Risk & Governance work
- IT Audit / Internal Audit roles in pharma
- GxP compliance analytics
- ERP role-redesign engagements in regulated environments

---

## Project structure

```
project_04_scm_grc_case_study/
├── README.md                          # this file
├── LICENSE                            # MIT
├── .gitignore
├── index.html                         # live case study (risk heat map + 3LoD + COSO table)
├── data/
│   ├── control_register.csv           # 13 controls mapped to COSO 17 Principles
│   ├── risk_register.csv              # 12 risks · inherent → residual
│   ├── sod_remediation.csv            # 8 business processes · 4 fixed
│   ├── cobit_maturity.csv             # 8 COBIT 2019 processes · before/after CMM
│   └── three_lines_mapping.csv        # 5 stakeholders mapped to 1L/2L/3L
└── docs/
    ├── methodology.md                 # COSO + COBIT + IIA framework crosswalk
    └── evidence_register.md           # supporting artifacts per control
```

## Frameworks applied

### COSO Internal Control — Integrated Framework (2013)
17 Principles across 5 components: Control Environment · Risk Assessment · Control Activities · Information & Communication · Monitoring. 13 controls implemented in the live operation map to these 17 Principles. See `data/control_register.csv`.

### COBIT 2019
8 COBIT processes uplifted from average CMM Level 1.0 to 3.5: **APO12** (Manage Risk), **APO13** (Manage Security), **DSS01** (Manage Operations), **DSS05** (Manage Security Services), **BAI09** (Manage Assets), **MEA01** (Monitor Performance), **MEA03** (Monitor Compliance), **APO01** (Manage IT Framework). See `data/cobit_maturity.csv`.

### IIA Three Lines Model (2020)
5 supply-chain stakeholders mapped:
- **1st line (operational management):** Supplier · Vendor · Carrier · Warehouse Ops
- **2nd line (risk & compliance):** SoD Policy Owner · BI Cost Monitoring · WMS Audit
- **3rd line (independent assurance):** Receiver · SQL Audit Trail · Weekly Anomaly Review

See `data/three_lines_mapping.csv`.

### TCFD-aligned risk taxonomy
12 risks classified as transition / physical / regulatory / operational; each with inherent and residual scores on a 5×5 likelihood × impact matrix. See `data/risk_register.csv`.

---

## How to use this repo

This is primarily a **methodology + evidence-register repo**, not a runnable application. The artifacts to study:

1. **`docs/methodology.md`** — full crosswalk of COSO 17 Principles → COBIT 2019 processes → IIA Three Lines → 21 CFR Part 11 analogs.
2. **`data/control_register.csv`** — the 13 controls with their type (preventive/detective/corrective), frequency, status, and supporting evidence references.
3. **`data/risk_register.csv`** — the 12 risks with inherent + residual scores and mitigation narratives.
4. **`index.html`** — the live case study dashboard with risk heat map, hero story, and Three Lines of Defense visualization.

## Limitations & ethics

- The case study is anonymized. Specific dollar amounts (~$28K monthly throughput, ~$22K insurance recovery) are order-of-magnitude.
- The operation was a Piscataway, NJ logistics warehouse, not a pharma facility — the **21 CFR Part 11 analogy** is about *control structure*, not regulatory scope. I have not personally implemented 21 CFR Part 11 in a GxP-validated environment.
- All control designs and audit findings are my work; no proprietary employer information is included.

## License

MIT — see [LICENSE](LICENSE).

---

**Lunarix Technologies LLC** — independent BI / data-governance consultancy based in Edison, NJ. Building audit-defensible analytics for pharma, healthcare, and supply chain clients. More work at [lunariduo.com](https://lunariduo.com).

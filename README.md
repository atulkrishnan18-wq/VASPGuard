# VASPGuard — Crypto Compliance Intelligence Observatory

> **A companion project to [ScoreSentinel](https://github.com/atulkrishnan18-wq/transactionmonitoring)**  
> Where ScoreSentinel scores transactions, VASPGuard scores the institutions that process them.

[![Maintained by](https://img.shields.io/badge/Maintained%20by-Atul%20Krishnan%2C%20CAMS-black?style=flat-square)](https://chainsutra.in)
[![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)]()
[![ChainSutra](https://img.shields.io/badge/Intelligence-ChainSutra.in-orange?style=flat-square)](https://chainsutra.in)
[![FATF Aligned](https://img.shields.io/badge/Framework-FATF%20R.15%20Aligned-darkblue?style=flat-square)]()
[![FIU-IND](https://img.shields.io/badge/Jurisdiction-FIU--IND%20%7C%20MiCA%20%7C%20GENIUS%20Act-purple?style=flat-square)]()

---

## What Is VASPGuard?

VASPGuard is an open-source **Virtual Asset Service Provider (VASP) compliance intelligence framework** — a structured, publicly maintained observatory that assesses the compliance posture of crypto exchanges and VASPs using entirely public information.

It is the institutional counterpart to transaction-level risk scoring. ScoreSentinel asks: *"Is this transaction suspicious?"* VASPGuard asks: *"Is this institution safe to transact with?"*

Built by a CAMS-certified AML/EDD analyst, VASPGuard applies the **BA-BO Framework** — Basic and Boring compliance fundamentals — to evaluate whether VASPs have the foundational controls in place that regulators, counterparties, and compliance professionals need to assess before engagement.

> **"Advanced tools amplify good compliance programmes. They cannot build them."**  
> — Atul Krishnan, CAMS · [The BA-BO Problem, ChainSutra (2026)](https://chainsutra.in)

---

## The Problem VASPGuard Solves

The global crypto enforcement record of 2025–2026 — $6.3 billion in AML fines across OKX, KuCoin, Binance, Coinbase Europe, and others — was not caused by sophisticated threat actors defeating advanced technology. It was caused by failures in the four mandatory elements of a basic AML programme:

1. Written internal controls
2. Independent compliance officer
3. Employee training
4. Independent testing

Yet no publicly available, structured resource exists to assess whether a VASP has these fundamentals in place — particularly in emerging markets like India where 47+ FIU-IND registered VASPs operate with minimal public compliance transparency.

VASPGuard fills that gap.

---

## Relationship to ScoreSentinel

```
┌─────────────────────────────────────────────────────────────────┐
│                    AML Risk Intelligence Stack                   │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   TRANSACTION LEVEL          │    INSTITUTIONAL LEVEL           │
│                               │                                  │
│   ScoreSentinel               │    VASPGuard                    │
│   ─────────────               │    ─────────                    │
│   • Structuring detection     │    • VASP compliance scoring    │
│   • Geographic risk (OFAC)    │    • Policy gap analysis        │
│   • Customer risk scoring     │    • Enforcement tracking       │
│   • PEP & sanctions           │    • Red flag library           │
│   • SR 11-7 compliant         │    • FATF R.15 aligned          │
│                               │                                  │
│   Input: Transaction data     │    Input: Public information    │
│   Output: Risk score 0-100    │    Output: Compliance score     │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

Together, ScoreSentinel and VASPGuard form a complete AML intelligence stack — from the individual transaction to the institutional counterparty.

---

## Repository Structure

```
vaspguard/
│
├── README.md                          # This file
├── METHODOLOGY.md                     # BA-BO scoring framework documentation
├── CONTRIBUTING.md                    # Contribution guidelines
├── LICENSE                            # MIT License
│
├── enforcement-tracker/
│   ├── README.md                      # Tracker methodology
│   ├── global-enforcement-actions.csv # All major crypto AML penalties
│   └── india-fiu-ind-actions.csv      # India-specific enforcement
│
├── vasp-observatory/
│   ├── README.md                      # Observatory methodology
│   ├── scoring-methodology.md         # Full BA-BO scoring rubric
│   ├── vasp-scores.csv               # Master scores dataset
│   └── profiles/
│       ├── india/
│       │   ├── suncrypto.md
│       │   ├── coindcx.md
│       │   ├── wazirx.md
│       │   ├── zebpay.md
│       │   └── mudrex.md
│       └── global/
│           ├── binance.md
│           ├── okx.md
│           └── coinbase.md
│
├── red-flag-library/
│   ├── README.md
│   ├── by-typology/
│   │   ├── money-laundering.md
│   │   ├── sanctions-evasion.md
│   │   ├── terrorist-financing.md
│   │   ├── fraud.md
│   │   └── nested-exchanges.md
│   └── by-product/
│       ├── centralised-exchange.md
│       ├── defi-protocol.md
│       ├── otc-desk.md
│       ├── stablecoin-issuer.md
│       └── p2p-platform.md
│
└── regulatory-frameworks/
    ├── india-pmla-vasp-guidelines.md
    ├── fatf-recommendation-15.md
    ├── eu-mica-summary.md
    ├── us-genius-act-summary.md
    └── travel-rule-comparison.md
```

---

## The BA-BO Scoring Framework

VASPGuard scores each VASP across **eight compliance dimensions** — directly derived from the four mandatory BSA/AML programme elements and their practical application to VASPs.

Each dimension is scored **0–10** based entirely on publicly available information.

| # | Dimension | What We Assess | Max Score |
|---|---|---|---|
| 1 | **Regulatory Registration** | Active registration with primary jurisdiction regulator | 10 |
| 2 | **Policy Completeness** | Public AML/CFT/CPF policy covers FATF-required elements | 10 |
| 3 | **Travel Rule Maturity** | Travel Rule explicitly addressed in public policy | 10 |
| 4 | **Governance Structure** | Designated compliance officer roles publicly identified | 10 |
| 5 | **Product-Policy Alignment** | Policy scope covers all products offered | 10 |
| 6 | **Adverse Media** | Clean public record — no enforcement actions, fines, or regulatory warnings | 10 |
| 7 | **Policy Currency** | Policy updated within the last 12 months | 10 |
| 8 | **Transparency Indicators** | Registration number, officer contact, and audit commitment publicly disclosed | 10 |

**Total: 80 points → Normalised to 100**

### Score Interpretation

| Score | Rating | Interpretation |
|---|---|---|
| 80–100 | 🟢 **Strong** | Above-average public compliance posture |
| 60–79 | 🟡 **Adequate** | Meets baseline expectations with gaps |
| 40–59 | 🟠 **Developing** | Notable gaps in public compliance indicators |
| Below 40 | 🔴 **Concern** | Significant public compliance deficiencies |

> **Important:** VASPGuard scores reflect public information only. A low score does not imply actual non-compliance. A high score does not guarantee internal programme quality. Scores should be used as a starting point for due diligence — not a substitute for it.

---

## Enforcement Tracker

The enforcement tracker maintains a structured dataset of every major crypto AML, CFT, and sanctions enforcement action globally.

### Fields

| Field | Description |
|---|---|
| `firm_name` | Name of penalised entity |
| `jurisdiction` | Country of enforcement |
| `regulator` | Enforcing authority |
| `date` | Date of enforcement action |
| `penalty_usd` | Penalty in USD |
| `root_cause` | BA-BO dimension that failed |
| `primary_violation` | Legal provision violated |
| `ba_bo_category` | Which of the 8 BA-BO dimensions was the root cause |
| `settlement_terms` | Key conditions of settlement |
| `source_url` | Primary source |

### Sample Entries

| Firm | Jurisdiction | Regulator | Date | Penalty (USD) | BA-BO Root Cause |
|---|---|---|---|---|---|
| Binance | US | DOJ / FinCEN / OFAC | Nov 2023 | $4,300,000,000 | Governance — CCO Independence |
| OKX | US | DOJ | Feb 2025 | $504,000,000 | Written Programme — Growth Culture |
| KuCoin | US | DOJ | Jan 2025 | $297,000,000 | SAR Filing — No STR Process |
| Coinbase Europe | Ireland | Central Bank of Ireland | Nov 2025 | $23,300,000 | Independent Testing — Misconfiguration |
| BitMEX | US | FinCEN / CFTC | 2025 | $100,000,000 | Written Programme — Wilful Non-Compliance |
| Monzo | UK | FCA | Jul 2025 | $26,500,000 | Employee Training — No Ongoing Monitoring |
| Paxful | US | FinCEN | 2025 | $3,500,000 | SAR Filing — Wilful BSA Violations |

---

## Red Flag Library

The red flag library is a practitioner-facing reference of financial crime indicators specific to virtual asset environments — organised by typology and product type.

### Sample Entry Format

```markdown
## Red Flag: Dormant Account to High Volume — Nested Exchange Indicator

**Typology:** Money Laundering — Layering  
**Product:** Centralised Exchange  
**Severity:** High  
**FATF Reference:** FATF Guidance on Virtual Assets (2023), Para 4.2  

### Description
A corporate or individual account with minimal or zero historical activity 
suddenly processes volumes inconsistent with the stated business purpose.
Classic indicator of nested exchange infrastructure or account takeover 
for layering purposes.

### Real-World Case Reference
Zedcex and Zedxion (OFAC, January 2026) — UK-registered dormant companies 
processing $94 billion in transactions. Detected by TRM Labs / OCCRP.
[ChainSutra Analysis](https://chainsutra.in/binance-monitorship-paradox)

### Monitoring Rule Suggestion
Flag accounts where 30-day volume exceeds 50x the average of the prior 
6-month period. Escalate for EDD if corporate account with < 12 months 
trading history.

### Regulatory Guidance
- FATF R.15 Interpretive Note, Para 8(b)
- FinCEN FIN-2019-A003 (CVC Red Flags)
- FIU-IND AML/CFT Guidelines for VASPs, Section 4
```

---

## Regulatory Frameworks

VASPGuard maintains structured summaries of the key regulatory frameworks governing VASPs globally — written for practitioners, not lawyers.

### Covered Frameworks

| Framework | Jurisdiction | Status | Summary |
|---|---|---|---|
| PMLA + FIU-IND VASP Guidelines | India | In force | [View →](regulatory-frameworks/india-pmla-vasp-guidelines.md) |
| FATF Recommendation 15 | Global | Updated 2023 | [View →](regulatory-frameworks/fatf-recommendation-15.md) |
| EU MiCA | European Union | Full enforcement July 2026 | [View →](regulatory-frameworks/eu-mica-summary.md) |
| US GENIUS Act | United States | Signed July 2025 | [View →](regulatory-frameworks/us-genius-act-summary.md) |
| Travel Rule Comparison | Global | Multi-jurisdiction | [View →](regulatory-frameworks/travel-rule-comparison.md) |

---

## Methodology & Limitations

### What VASPGuard Is
- A structured framework for assessing VASP compliance posture from public information
- A practitioner reference for red flags, enforcement history, and regulatory frameworks
- A companion to transaction-level risk scoring (ScoreSentinel)
- A living document — updated as enforcement actions occur and regulations change

### What VASPGuard Is Not
- A legal opinion or regulatory determination
- A substitute for internal due diligence or examination
- An endorsement or condemnation of any specific firm
- A complete picture of any firm's internal compliance programme

### Data Sources
All VASP profiles and scores are derived exclusively from:
- Publicly available AML/KYC policies
- Regulatory registration databases (FIU-IND, FCA, FinCEN MSB Registrant Search)
- Official enforcement action press releases (DOJ, FinCEN, OFAC, FCA, ESMA)
- Published FATF mutual evaluation reports
- Adverse media from credible financial and regulatory news sources

---

## Contributing

VASPGuard is an open-source intelligence project. Contributions are welcome from compliance professionals, researchers, and practitioners.

### How to Contribute

**Add an enforcement action:**
Submit a PR adding a row to `enforcement-tracker/global-enforcement-actions.csv` with a source URL

**Add a VASP profile:**
Use the profile template in `vasp-observatory/profiles/` — public information only

**Add a red flag:**
Use the red flag template in `red-flag-library/` — include a regulatory reference and real-world case

**Correct an error:**
Open an issue with the correction and source

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting.

> All contributions must be based on verifiable public information. No speculation, no internal knowledge, no unverified claims.

---

## Intelligence Feed

VASPGuard data powers original analysis published on **[ChainSutra](https://chainsutra.in)** — a financial crime intelligence platform for compliance professionals.

### Related ChainSutra Articles
- [The BA-BO Problem: Why Crypto's Biggest Fines Were Always Avoidable](https://chainsutra.in/ba-bo-problem-crypto-aml-fines)
- [The Transparency Trap: Binance's $4.3B Compliance Overhaul and Nested Risk](https://chainsutra.in/binance-monitorship-paradox)
- [AML Has Eclipsed the SEC as Crypto's #1 Regulatory Risk](https://chainsutra.in/crypto-regulatory-war-aml-enforcement)
- [Stablecoins: From Concept to Compliance](https://chainsutra.in/stablecoins-concept-to-compliance-guide)

---

## Author

**Atul Krishnan, CAMS**  
AML/EDD Analyst · Founder, ChainSutra  
[chainsutra.in](https://chainsutra.in) · [GitHub](https://github.com/atulkrishnan18-wq)

> *Also see: [ScoreSentinel](https://github.com/atulkrishnan18-wq/transactionmonitoring) — Risk-based AML transaction risk scoring engine. SR 11-7 compliant. Covers structuring detection, geographic risk (OFAC/FATF/CPI), customer risk scoring, PEP & sanctions screening.*

---

## License

MIT License — free to use, adapt, and build upon with attribution.

---

*VASPGuard is maintained independently. It is not affiliated with any regulator, vendor, or financial institution. All assessments are based on public information and represent the analytical judgment of the author, not legal determinations.*

# PROFESSIONAL ENGINEERING QUALIFICATION MAP

Regulatory · Standards · Compliance · Competency · Certification · Professional Documentation

Type: Working research artifact — not legal advice, not a compliance certificate, not public documentation.
Input: `PORTFOLIO_MASTER_SNAPSHOT.md` (same directory).
Date: 2026-09-04.

## 0. Evidence Rule Applied

States used throughout, exactly as specified: VERIFIED, DOCUMENTED, PORTFOLIO-EVIDENCED, SELF-REPORTED, RECOMMENDED, TARGET, UNRESOLVED, NOT-APPLICABLE, SCOPE-DEPENDENT.

**VERIFIED** in this document means: an official source (EUR-Lex-linked EC page, ISO/ISA official page, ESMA official page) was fetched and read during this session, and its content is reflected accurately below. **DOCUMENTED** means the identifier is extremely well-established and stable but was not independently fetched this session — verify at EUR-Lex/official source before formal use. **UNRESOLVED** means genuine ambiguity or insufficient verification exists and must not be resolved by guessing.

---

## 1. Executive Professional Profile

Based only on `PORTFOLIO_MASTER_SNAPSHOT.md` evidence:

| Candidate Role | Evidence Supporting It | Evidence Strength |
|---|---|---|
| Senior Systems Architect | Repository-wide architecture (L0–L6 layer contracts, CPS control loop, AI authority contract) | PORTFOLIO-EVIDENCED (design-level) |
| Cyber-Physical Systems Engineer | Design docs + private FILE-VERIFIED embedded firmware and controller | PORTFOLIO-EVIDENCED (design public, implementation private) |
| Embedded Systems Engineer | FILE-VERIFIED `IntegratedController.ino` (ATmega4809, sensor/actuator I/O, calibration) | PORTFOLIO-EVIDENCED (private) |
| Edge Systems Engineer | FILE-VERIFIED systemd units, Raspberry Pi service supervision | PORTFOLIO-EVIDENCED (private) |
| AI Systems / AI Infrastructure Engineer | FILE-VERIFIED CoreAgent agent runtime, model router, TEST-VERIFIED test suite | PORTFOLIO-EVIDENCED (private) |
| Network / Security Engineer | Threat model + AI authority contract (design); mesh tooling installed only (self-reported) | PORTFOLIO-EVIDENCED (design) / SELF-REPORTED (tooling) |
| Agritech Systems Engineer | FILE-VERIFIED Golden Greens controller + firmware; biological claims unverified | PORTFOLIO-EVIDENCED (control layer only) |
| OT/ICS Cybersecurity Engineer | THREAT_MODEL.md design content; no OT deployment or audit evidence found | DOCUMENTED intent, no implementation evidence |
| Blockchain/Smart Contract Security Engineer | No implementation evidence found in the public repository or inspected private artifacts; Web3 tooling referenced only | UNRESOLVED — no supporting evidence located |
| Energy Systems Engineer | Data-center waste-heat integration mentioned as architecture text only | UNRESOLVED — no implementation evidence |

**Do not select a single "best" title** per the calling specification. The evidence supports "Senior Systems Architect" as the broadest justified positioning, with "Cyber-Physical Systems Engineer" and "AI Infrastructure Engineer" as the two most evidence-dense secondary positions.

---

## 2. Professional Competency Framework

| Competency | Portfolio Evidence | Evidence State | Technical Domain | Relevant Standards | Relevant Regulation | Credential (candidate, not recommended yet) |
|---|---|---|---|---|---|---|
| Systems Architecture | Layer contracts, CPS loop | PORTFOLIO-EVIDENCED | Cross-cutting | ISO/IEC 42010 (architecture description) — DOCUMENTED, not fetched | N/A | — |
| Embedded / Control | Firmware, FSM | PORTFOLIO-EVIDENCED (private) | Embedded | IEC 61508 (functional safety) — DOCUMENTED, not fetched | Machinery Regulation (EU) 2023/1230 (if a machine is placed on market) | Functional safety credential — TARGET |
| Industrial / OT | Threat model design | DOCUMENTED intent | OT | IEC 62443 series (VERIFIED, §5) | NIS2 (conditional — see §6) | ISA/IEC 62443 Cybersecurity Fundamentals — TARGET |
| Edge / Infrastructure | systemd, Raspberry Pi | PORTFOLIO-EVIDENCED (private) | Edge/Linux | N/A directly | N/A directly | — |
| Network / Security | Mesh tooling, threat model | SELF-REPORTED (tooling) / DESIGN | Cybersecurity | ISO/IEC 27001 (VERIFIED, §5) | NIS2 (conditional), Cyber Resilience Act (conditional — see §6) | ISO/IEC 27001 Foundation/Lead Implementer — TARGET |
| AI / Data | CoreAgent, model router | PORTFOLIO-EVIDENCED (private) | AI | N/A specific standard verified | EU AI Act (VERIFIED identifier, §6) | AI governance credential — TARGET, issuer TBD |
| Agritech / CPS | Greenhouse controller | PORTFOLIO-EVIDENCED (private, control layer) | AgTech | N/A | Fertilising Products Regulation (EU) 2019/1009 (DOCUMENTED — only if a product is placed on market) | N/A |
| Data Centre / Energy | Waste-heat integration text | UNRESOLVED (no implementation) | Energy | ISO 50001 (VERIFIED, §5) | N/A directly | — |

---

## 3. Legal Classification Reference

- REGULATION ≠ DIRECTIVE: a Regulation is directly applicable in all Member States without national transposition; a Directive requires national transposition (e.g., NIS2 required transposition by 17 October 2024 — VERIFIED, §6).
- CE MARKING ≠ CERTIFICATION: CE marking is a manufacturer's self-declaration (or, for higher-risk products, third-party conformity assessment) that a product meets applicable EU legislation — it is **not** a certification issued by a certification body. Confirmed by the European Commission machinery page (VERIFIED, §7): "It is not acceptable for certificates to bear a CE marking."
- CERTIFICATION ≠ LEGAL COMPLIANCE: an ISO/IEC 27001 certificate certifies an organization's management system meets the standard; it does not itself satisfy every applicable law (e.g., GDPR, NIS2 have their own independent legal requirements).
- PROFESSIONAL CREDENTIAL ≠ REGULATORY AUTHORISATION: holding CISSP/CISM/ISA-62443 credentials does not itself authorize regulated activity (e.g., does not create MiCA crypto-service authorization).

---

## 4. Regulatory Corpus (Cyber-Physical / OT / Product Security)

| Regulation/Directive | Identifier | Type | Status | Key Facts (this session) | Source |
|---|---|---|---|---|---|
| Cyber Resilience Act | Regulation (EU) 2024/2847 | EU REGULATION | VERIFIED | Entered into force 10 Dec 2024. Main obligations apply from **11 Dec 2027**. Reporting obligations (actively exploited vulnerabilities) apply from **11 Sep 2026**. Applies to "products with digital elements." CE marking indicates CRA compliance; some products require notified-body assessment. | digital-strategy.ec.europa.eu/en/policies/cyber-resilience-act (fetched this session) |
| NIS2 Directive | Directive (EU) 2022/2555 | EU DIRECTIVE | VERIFIED | Came into force Jan 2023. Member States had until **17 Oct 2024** to transpose. Repealed NIS1 (Directive 2016/1148) as of 18 Oct 2024. Applies to "essential/important entities" across 18 critical sectors. A **20 Jan 2026** proposal introduced targeted simplification amendments (not yet confirmed adopted). | digital-strategy.ec.europa.eu/en/policies/nis2-directive (fetched this session) |
| EU AI Act | Regulation (EU) 2024/1689 | EU REGULATION | VERIFIED | Risk-based: unacceptable (prohibitions 1–8 effective Feb 2025; prohibition 9 effective Dec 2026), high-risk (obligations from **2 Dec 2027**), transparency (from **Aug 2026**), GPAI rules (effective **Aug 2025**). | digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai (fetched this session) |
| GDPR | Regulation (EU) 2016/679 | EU REGULATION | VERIFIED | OJ L 119, 04.05.2016; applicable since **25 May 2018**. | gdpr-info.eu, cross-referencing EUR-Lex CELEX:32016R0679 (fetched this session) |
| Machinery Regulation | Regulation (EU) 2023/1230 | EU REGULATION | VERIFIED | Adopted 14 June 2023. Replaces Machinery Directive 2006/42/EC. **Mandatory application from 20 January 2027**; machinery placed on market before that date must comply with the current Directive 2006/42/EC. Integrates AI-powered safety functions and cyber-safety provisions. | single-market-economy.ec.europa.eu/sectors/mechanical-engineering/machinery_en (fetched this session) |
| Radio Equipment Directive | Directive 2014/53/EU | EU DIRECTIVE | DOCUMENTED — not fetched this session (attempted URL returned 404); identifier is extremely well-established but should be re-verified at EUR-Lex before formal use | — |
| Low Voltage Directive | Directive 2014/35/EU | EU DIRECTIVE | DOCUMENTED — not fetched this session | — |
| EMC Directive | Directive 2014/30/EU | EU DIRECTIVE | DOCUMENTED — not fetched this session | — |
| RoHS | Directive 2011/65/EU | EU DIRECTIVE | DOCUMENTED — not fetched this session | — |
| ETSI EN 303 645 | EN 303 645 | HARMONISED/TECHNICAL STANDARD | DOCUMENTED — not fetched this session (consumer IoT baseline security) | — |
| IEC 62443 series | IEC 62443-1-1, -2-1, -2-3, -2-4, -3-2, -3-3, -4-1, -4-2 | STANDARD (ISA/IEC dual-badged) | VERIFIED | Confirmed via official ISA page: ISA99/IEC TC65 WG10 co-develop; IEC recognized the series as a horizontal standard in 2021; endorsed by UN/UNECE/NATO. Exact part titles/years confirmed (e.g., ANSI/ISA-62443-3-3-2013, ANSI/ISA-62443-4-1-2018, ANSI/ISA-62443-2-1-2024). Roles defined: asset owner, product supplier, integrator, service provider. | isa.org/standards-and-publications/isa-standards/isa-iec-62443-series-of-standards (fetched this session) |

**Applicability note (mandatory, per calling spec)**: none of the above are asserted as directly applicable to the portfolio owner's current activity. Applicability depends on product classification, market placement, business activity, and role in the supply chain — none of which were established as evidence in `PORTFOLIO_MASTER_SNAPSHOT.md`. No product is currently placed on any market per that snapshot (Golden Greens Crop remains CONCEPT/HYPOTHESIS at the business/product level).

---

## 5. Standards Register (Professional/Management System)

| Standard | Exact Title | Issuer | Status | Portfolio Relevance | Source |
|---|---|---|---|---|---|
| ISO/IEC 27001:2022 | "Information security, cybersecurity and privacy protection — Information security management systems — Requirements" | ISO/IEC JTC 1/SC 27 | VERIFIED — Published, Edition 3 (2022-10), 1 amendment (2024) | POTENTIALLY RELEVANT — security architecture design work exists; no ISMS implementation evidence found | iso.org/standard/27001 (fetched this session) |
| ISO 50001:2018 | "Energy management systems — Requirements with guidance for use" | ISO/TC 301 | VERIFIED — Published, Edition 2 (2018-08), confirmed 2024, 1 amendment (2024) | POTENTIALLY RELEVANT — data-center waste-heat integration is architecture text only, no EnMS evidence found | iso.org/standard/69426.html (fetched this session) |
| ISA/IEC 62443 (series) | "Security for industrial automation and control systems" (multi-part) | ISA99 / IEC TC65 WG10 | VERIFIED | POTENTIALLY RELEVANT — OT/ICS threat-model design exists; no IACS deployment evidence found | isa.org (fetched this session) |
| ISO/IEC 30141 | IoT reference architecture | ISO/IEC JTC 1 | DOCUMENTED — not fetched this session | POTENTIALLY RELEVANT — digital twin/IoT architecture discussed conceptually | — |
| ISO 23247 (series) | Digital Twin Framework for Manufacturing | ISO/TC 184 | DOCUMENTED — not fetched this session | POTENTIALLY RELEVANT — digital twin mentioned in private canon documents only | — |
| ISO/IEC 30134-2 | Data centre PUE | ISO/IEC JTC 1/SC 39 | DOCUMENTED — not fetched this session | POTENTIALLY RELEVANT — waste-heat/PUE concept referenced, no measured PUE evidence | — |
| DIN EN 50600 (series) | Data centre facilities and infrastructures | DIN/CENELEC | DOCUMENTED — not fetched this session | POTENTIALLY RELEVANT (same basis as above) | — |
| IEEE P3217 | (exact title/status) | IEEE | UNRESOLVED — not independently verified this session; a private canon document lists it only as a roadmap item, not confirmed published/draft status | — |

---

## 6. CE Conformity Framework

CE marking is **not** a certification (VERIFIED, official EC source, §4 table). It is a manufacturer declaration/conformity-assessment outcome under one or more product regimes (LVD, EMC, RED, RoHS, Machinery, CRA once applicable). A technical file and EU Declaration of Conformity are standard required artifacts; harmonised standards may be used to demonstrate presumption of conformity. **No portfolio prototype is stated or implied to be CE compliant** — no product has been placed on the EU market per the evidence in the snapshot.

---

## 7. Agriculture / Fertilisers / Chemistry (identification only)

| Regulation | Identifier | Relevance Trigger | Status |
|---|---|---|---|
| Fertilising Products Regulation | Regulation (EU) 2019/1009 | Only if a fertilising product is placed on the EU market bearing CE marking | DOCUMENTED — not fetched this session; CONDITIONAL, no product exists per evidence |
| Biocidal Products Regulation | Regulation (EU) 528/2012 | Only if a biocidal product is placed on market | DOCUMENTED — NOT APPLICABLE per current evidence (no product) |
| Plant Protection Products | Regulation (EC) 1107/2009 | Only if a plant-protection product is placed on market | DOCUMENTED — NOT APPLICABLE per current evidence |
| REACH | Regulation (EC) 1907/2006 | Chemical substance registration | DOCUMENTED — NOT APPLICABLE per current evidence |
| CLP | Regulation (EC) 1272/2008 | Chemical classification/labelling | DOCUMENTED — NOT APPLICABLE per current evidence |
| Organic Production Regulation | Regulation (EU) 2018/848 | Only if organic certification is sought | DOCUMENTED — NOT APPLICABLE; explicitly distinct from private certification schemes (ECOCERT, FiBL are separate bodies, not the same as the EU Regulation) |
| Latvia / VAAD | National competent authority | Plant protection/fertiliser/agricultural input registration in Latvia | UNRESOLVED — official Latvian source not fetched this session |

**No product currently exists** per the portfolio snapshot (Golden Greens Crop remains a private CPS testbed with a real controller/firmware but no field product, no biological measurement, no market placement). All items in this section are therefore **NOT APPLICABLE at this time**, recorded for future-state awareness only.

---

## 8. AI / Data / Digital Resilience (identification only)

| Regulation | Identifier | Status |
|---|---|---|
| EU AI Act | Regulation (EU) 2024/1689 | VERIFIED (§4) |
| Data Act | Regulation (EU) 2023/2854 | DOCUMENTED — not fetched this session |
| Data Governance Act | Regulation (EU) 2022/868 | DOCUMENTED — not fetched this session |
| DORA | Regulation (EU) 2022/2554 | DOCUMENTED — not fetched this session; likely NOT APPLICABLE (financial-entity scope; no evidence of financial-sector activity in the portfolio) |
| eIDAS 2.0 | Regulation (EU) 2024/1183 | DOCUMENTED — not fetched this session |

---

## 9. Crypto / Digital Assets / Web3 (identification only)

| Item | Identifier | Status |
|---|---|---|
| MiCA | Regulation (EU) 2023/1114 | VERIFIED entry-into-force (June 2023) via ESMA official page; exact regulation number not re-confirmed verbatim in the fetched excerpt — treat identifier as DOCUMENTED pending direct EUR-Lex confirmation |
| Transfer of Funds Regulation | Regulation (EU) 2023/1113 | DOCUMENTED — not fetched this session |
| DLT Pilot Regime | Regulation (EU) 2022/858 | DOCUMENTED — not fetched this session |
| AMLD6 | Directive (EU) 2024/1640 | DOCUMENTED — not fetched this session |

**Portfolio relevance**: no blockchain/smart-contract implementation evidence was found anywhere in `PORTFOLIO_MASTER_SNAPSHOT.md` (§14). All items in this section are UNRESOLVED for portfolio applicability — there is currently no evidenced Web3 activity to map against these regulations.

**Blockchain security credentials (CBSP, Chainlink Developer, etc.)**: UNRESOLVED — ISSUER VERIFICATION REQUIRED. These names are used by multiple providers; no single-issuer confirmation was performed this session. Do not represent any of these as one universally recognized certification without first identifying and verifying a specific issuer.

---

## 10. Cybersecurity Certification Map

| Credential | Issuer | Domain | Status |
|---|---|---|---|
| ISA/IEC 62443 Cybersecurity Certificate Program | ISA | OT/ICS | VERIFIED to exist (ISA Cybersecurity Certificate Training Program referenced on the official ISA page fetched this session); exact exam/prerequisite details not independently fetched — DOCUMENTED pending direct program-page verification |
| GIAC GICSP | GIAC/SANS | OT/ICS | DOCUMENTED — not fetched this session |
| CISSP | ISC2 | Security architecture/governance | DOCUMENTED — not fetched this session |
| CISM | ISACA | Governance/risk | DOCUMENTED — not fetched this session |
| CRISC | ISACA | IT risk | DOCUMENTED — not fetched this session |
| ISO/IEC 27001 Lead Implementer/Auditor | Various accredited training providers (not ISO itself) | ISMS implementation/audit | DOCUMENTED — note: ISO does not itself issue personal certifications; these are third-party training-provider credentials aligned to the ISO/IEC 27001 standard (VERIFIED standard exists, §5) |
| ISO 50001 Lead Implementer/Auditor | Various accredited training providers | EnMS implementation/audit | DOCUMENTED, same note as above |
| ISACA AAIR / AAISM / CDPSE | ISACA | AI risk / AI security management / data privacy | UNRESOLVED — current status/requirements not fetched this session |

---

## 11. Professional Documentation Register (what exists vs. what's missing)

| # | Document | Exists? | Location |
|---|---|---|---|
| 01 | Professional Profile | Partial | `README.md` |
| 02 | Systems Architecture Competency Matrix | Yes | `COMPETENCY_EVIDENCE_MATRIX.md` |
| 03 | Cybersecurity Competency Matrix | Partial | `architecture/security/THREAT_MODEL.md` |
| 04 | OT/ICS Competency Matrix | No | — |
| 05 | Embedded & Control Engineering Matrix | Partial | `case-studies/CASE-003/README.md` |
| 06 | Edge/Infrastructure Matrix | Partial | `architecture/edge/README.md`, `projects/arm64-workstation/README.md` |
| 07 | AI/Data Governance Matrix | Partial | `architecture/security/AI_AUTHORITY_CONTRACT.md` |
| 08 | Blockchain/Web3 Security Matrix | No | — |
| 09 | Agritech/CEA Regulatory Matrix | No (this document, §7, is the first pass) | — |
| 10 | Data Centre/Energy Matrix | No | — |
| 11–24 | Regulatory Register, Standards Register, Certification Register, Roadmaps, Mappings, Gaps | Partial — this document | — |

---

## 12. Certification Register

| Credential | Issuer | Domain | Status | Priority |
|---|---|---|---|---|
| (none) | — | — | EXISTING: **none found** | — |
| ISA/IEC 62443 Fundamentals Specialist | ISA | OT/ICS cybersecurity | TARGET | TIER 1 |
| ISO/IEC 27001 Foundation | Accredited training provider | ISMS | TARGET | TIER 2 |
| CISSP or CISM | ISC2 / ISACA | Security governance | TARGET (choose one, not both initially) | TIER 2 |
| AI governance credential | Issuer TBD (ISACA AAIR/AAISM candidate, UNRESOLVED status) | AI governance | RECOMMENDED, not yet TARGET | TIER 3 |
| Blockchain/smart-contract security credential | Issuer UNRESOLVED | Web3 security | NOT RECOMMENDED at this time — no supporting portfolio evidence exists | TIER 4 |
| ISO 50001 Lead Implementer | Accredited training provider | Energy management | OPTIONAL — only if data-center/energy work becomes evidenced | TIER 4 |

---

## 13. Certification Priority and Recommended Stack

```
CORE SYSTEMS SECURITY (TIER 1)
├── ISA/IEC 62443 Fundamentals Specialist   [direct fit: embedded + OT design work already evidenced]
└── (GICSP deferred until OT deployment evidence exists)

CYBERSECURITY GOVERNANCE (TIER 2)
├── ISO/IEC 27001 Foundation
└── CISSP OR CISM — not both initially (redundant for current evidence level)

SPECIALIZATION (TIER 3 — evidence-dependent)
├── AI Governance credential — only once issuer/program is verified
└── (Digital Twin / Blockchain deferred — no supporting implementation evidence)

DOMAIN (TIER 4 — only if business activity evidence emerges)
├── Product Compliance / CE (only once a real product nears market placement)
└── ISO 50001 (only once energy-management work is actually implemented)
```

Rationale: the portfolio's strongest, most evidence-dense domain is embedded/OT-adjacent CPS architecture with a real (private) implementation trail. ISA/IEC 62443 has direct fit. Broad governance certifications (CISSP/CISM/CRISC) are useful but redundant if all three are pursued — recommend one, not three, until a specific professional context (e.g., a CISO-track role) justifies more.

---

## 14. Evidence → Standard → Regulation Chain (representative rows)

| Competency | Standard | Why Relevant | Evidence | Gap |
|---|---|---|---|---|
| OT/ICS security design | IEC 62443 series | Direct subject-matter match to `THREAT_MODEL.md` and embedded/edge architecture | DESIGN document exists | No IACS deployment, no clause-level conformity work — CLAUSE-LEVEL VERIFICATION REQUIRED |
| Information security architecture | ISO/IEC 27001 | Security-by-design principles already documented | DESIGN document exists | No ISMS scope, risk assessment, or Statement of Applicability exists |
| Energy/data-center integration | ISO 50001, ISO/IEC 30134-2 | Waste-heat reuse concept referenced | Architecture text only | No EnMS, no PUE measurement |

| Regulation | Technical Domain | Relevant Standards | Harmonised? | Notes |
|---|---|---|---|---|
| Cyber Resilience Act | Product cybersecurity | Harmonised standards under CRA are still being developed (per the CRA standardisation page referenced on the official EC site) | Partially, in progress | Standards can provide a technical means of conformity; a standard is never itself the law |
| Machinery Regulation | Product safety | Harmonised standards under the Machinery Directive/Regulation exist and are listed by the EC | Yes, for many machinery categories | Same principle: standard ≠ law |

---

## 15. Regulatory Scope Matrix

| Regulation | Portfolio Component | Potential Applicability | Trigger | Status |
|---|---|---|---|---|
| Cyber Resilience Act | Any future product with digital elements placed on EU market | CONDITIONAL | Actual product placement on market | UNRESOLVED — no product placed on market per evidence |
| NIS2 | Any future "essential/important entity" role | CONDITIONAL | Sector + size thresholds | UNRESOLVED — no entity/sector role established |
| Machinery Regulation | Golden Greens Crop physical equipment, if manufactured/placed on market | CONDITIONAL | Market placement after 20 Jan 2027 (or voluntary earlier compliance) | UNRESOLVED — currently a private testbed, not a placed product |
| EU AI Act | CoreAgent, if deployed as an AI system affecting others | CONDITIONAL | Deployment context, risk classification | UNRESOLVED — currently a private, non-deployed agent |
| GDPR | Any system processing personal data | PROFESSIONALLY RELEVANT | Processing of personal data | Not established as applicable — no personal-data processing system identified as deployed |
| MiCA / AMLD6 | None | NOT APPLICABLE | No crypto-asset service identified | — |
| Fertilising Products / Biocidal / PPP / REACH / CLP / Organic | Golden Greens Crop, if a product is ever placed on market | NOT APPLICABLE (currently) | Future market placement of a specific product type | — |

**Do not treat any row above as a current legal obligation.** Every row is CONDITIONAL/UNRESOLVED/NOT APPLICABLE pending real business/product/deployment decisions not yet evidenced.

---

## 16. Professional Evidence Gaps

| Gap | Impact | Evidence Needed | Priority |
|---|---|---|---|
| Architecture exists, implementation unverified publicly | Public portfolio understates real private engineering work | Sanitized, linked Evidence records per `schemas/evidence.schema.json` | High |
| Security design exists, no formal threat-model exercise performed | Cannot claim security maturity beyond DESIGN | A documented threat-modeling session (e.g., STRIDE walkthrough) with recorded output | Medium |
| Control architecture exists, no measured safety behavior | Cannot claim reliability maturity beyond DESIGN | Fault-injection test with recorded pass/fail and timing data | Medium |
| No populated `evidence/`, `measurements/`, `experiments/` records anywhere | Every claim in the public repo is capped at DESIGN/CONCEPT | At least one real, sanitized evidence record | High |
| No public/private CI or reproducibility for any private component | Cannot claim "publicly reproducible" for anything | A minimal, sanitized, publicly runnable subset (e.g., the FSM test suite) | Medium |

---

## 17. Professional Documentation Gaps

Recommended, not yet produced: Threat Model **execution record** (a document exists; a completed exercise output does not), Risk Register, FMEA/Hazard Analysis for the embedded control system, Interface Control Document for the 24-field telemetry protocol, Test Plan + Verification Matrix, SBOM for CoreAgent's Python dependencies, Vulnerability Management Process, Incident Response Plan. **Not recommended yet**: EU Declaration of Conformity template, AI System technical documentation under the AI Act, Smart Contract Security Report, Energy Management documentation — all premature given no product/deployment/Web3 evidence exists.

---

## 18. Professional Engineering Maturity (component-level)

| Component | Level |
|---|---|
| Public repository architecture (layer contracts, CPS loop, evidence model) | LEVEL 1 — ARCHITECTURE |
| CoreAgent agent runtime | LEVEL 2 — IMPLEMENTATION (private); tests give partial LEVEL 3 signal for the tested slice only |
| Golden Greens firmware + controller | LEVEL 2 — IMPLEMENTATION (private) |
| Industrial-runtime FSM | LEVEL 3 — VERIFIED IMPLEMENTATION (test-verified, narrow scope only) |
| Sovereign mesh | LEVEL 1 — ARCHITECTURE (tooling installed does not raise this) |
| Golden Greens Crop as a business/product | LEVEL 0 — CONCEPT |

No single maturity level applies to the whole portfolio.

---

## 19. Final Professional Positioning

**PRIMARY POSITIONING**: Senior Systems Architect — Cyber-Physical Systems.

**SECONDARY POSITIONING** (up to 5): Embedded/Control Systems Engineer; Edge Infrastructure Engineer; AI Infrastructure Engineer (local/agentic); Security-by-Design Architect (OT/ICS-adjacent); Agritech CPS Engineer.

**CORE DIFFERENTIATOR**: an explicit, documented separation between AI reasoning/recommendation and deterministic physical control authority, combined with real (privately verified) embedded firmware and agent-runtime implementation behind that architecture — not merely diagram-level claims.

**PROFESSIONAL DOMAIN STACK** (evidence-supported only):

```
Systems Architecture
        +
Cyber-Physical Systems (design + private embedded implementation)
        +
Embedded / Deterministic Control
        +
Edge Infrastructure
        +
Local AI (agent runtime, tested)
        +
Security-by-Design (design-level; OT/ICS-adjacent)
```

Blockchain Security, Energy/Data-Centre, and Agritech-as-a-regulated-product are explicitly **excluded** from this stack — no supporting implementation or deployment evidence exists for them yet (they remain roadmap items in a private canon document only).

---

## 20. Final Roadmap

1. **STAGE 1 — EVIDENCE**: Produce at least one real, sanitized Evidence record (per `schemas/evidence.schema.json`) from the already-tested FSM suite or CoreAgent bootstrap suite.
2. **STAGE 2 — DOCUMENTATION**: Threat-model execution record, FMEA for embedded control, Interface Control Document for the telemetry protocol.
3. **STAGE 3 — CORE CERTIFICATIONS**: ISA/IEC 62443 Fundamentals Specialist; ISO/IEC 27001 Foundation.
4. **STAGE 4 — SPECIALIZATION**: AI governance credential (once issuer verified) — defer blockchain/digital-twin until implementation evidence exists.
5. **STAGE 5 — REGULATORY EXPERTISE**: Track CRA (reporting from 11 Sep 2026, full obligations 11 Dec 2027), Machinery Regulation (mandatory 20 Jan 2027), and EU AI Act phased dates (§4) as they may become applicable if/when a real product or deployed AI system exists.
6. **STAGE 6 — PROFESSIONAL AUTHORITY**: Publish the already-strong architecture documents publicly (pending the PRE-PUSH AUDIT resolution), and consider a public, sanitized reference implementation of the FSM slice as a demonstrable system.

---

## 21. Official Source Registry

| Source | Document | URL | Access Date | Purpose |
|---|---|---|---|---|
| European Commission | Cyber Resilience Act | https://digital-strategy.ec.europa.eu/en/policies/cyber-resilience-act | 2026-09-04 | Verify CRA identifier and dates |
| European Commission | NIS2 Directive | https://digital-strategy.ec.europa.eu/en/policies/nis2-directive | 2026-09-04 | Verify NIS2 identifier and transposition date |
| European Commission | AI Act | https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai | 2026-09-04 | Verify AI Act identifier and phased dates |
| gdpr-info.eu (mirrors EUR-Lex CELEX:32016R0679) | GDPR | https://gdpr-info.eu/ | 2026-09-04 | Verify GDPR identifier and application date |
| European Commission | Machinery | https://single-market-economy.ec.europa.eu/sectors/mechanical-engineering/machinery_en | 2026-09-04 | Verify Machinery Regulation identifier and dates |
| ESMA | MiCA | https://www.esma.europa.eu/esmas-activities/digital-finance-and-innovation/markets-crypto-assets-regulation-mica | 2026-09-04 | Verify MiCA entry-into-force |
| ISO | ISO/IEC 27001:2022 | https://www.iso.org/standard/27001 | 2026-09-04 | Verify standard title/edition/status |
| ISO | ISO 50001:2018 | https://www.iso.org/standard/69426.html | 2026-09-04 | Verify standard title/edition/status |
| ISA | ISA/IEC 62443 series | https://www.isa.org/standards-and-publications/isa-standards/isa-iec-62443-series-of-standards | 2026-09-04 | Verify series parts/status/roles |

**Not fetched this session** (identifiers are DOCUMENTED from general knowledge, not independently verified — re-verify at EUR-Lex/official source before any formal use): RED 2014/53/EU, LVD 2014/35/EU, EMC 2014/30/EU, RoHS 2011/65/EU, ETSI EN 303 645, Fertilising Products Reg 2019/1009, Biocidal Reg 528/2012, PPP Reg 1107/2009, REACH 1907/2006, CLP 1272/2008, Organic Production Reg 2018/848, Data Act 2023/2854, Data Governance Act 2022/868, DORA 2022/2554, eIDAS2 2024/1183, Transfer of Funds Reg 2023/1113, DLT Pilot Regime 2022/858, AMLD6 2024/1640, ISO/IEC 30141, ISO 23247, ISO/IEC 30134-2, DIN EN 50600 series, IEEE P3217, GIAC GICSP, CISSP, CISM, CRISC, ISACA AAIR/AAISM/CDPSE, CBSP (any issuer), Chainlink Developer/Web3 credentials.

---

## 22. Legal Disclaimer

This document is an engineering/regulatory **research map**, not legal advice. Actual regulatory applicability depends on product classification, business activity, role in the supply chain, market, jurisdiction, customer, deployment, intended use, and technical characteristics — none of which have been established as fixed facts in the evidence reviewed. Consult qualified legal counsel and the relevant competent authority before making any compliance claim or business decision based on this document.

---

## 23. Final Master Summary

```yaml
professional_engineering_qualification_map:
  primary_professional_positioning: "Senior Systems Architect — Cyber-Physical Systems"
  secondary_positions:
    - Embedded/Control Systems Engineer
    - Edge Infrastructure Engineer
    - AI Infrastructure Engineer
    - Security-by-Design Architect (OT/ICS-adjacent)
    - Agritech CPS Engineer
  core_competencies: "see section 2"
  technical_domains: "systems architecture, embedded/OT, edge, AI infrastructure, security-by-design, agritech CPS"
  regulatory_domains: "see sections 4, 7, 8, 9, 15 — all CONDITIONAL/UNRESOLVED pending real product/deployment decisions"
  standards: "see section 5 — ISO/IEC 27001, ISO 50001, ISA/IEC 62443 VERIFIED to exist; others DOCUMENTED only"
  conformity_frameworks: "CE marking framework described in section 6; not claimed applicable to any current prototype"
  existing_credentials: []
  target_credentials:
    - ISA/IEC 62443 Fundamentals Specialist
    - ISO/IEC 27001 Foundation
    - CISSP or CISM (one, not both)
  tier_1_credentials: ["ISA/IEC 62443 Fundamentals Specialist"]
  tier_2_credentials: ["ISO/IEC 27001 Foundation", "CISSP or CISM"]
  tier_3_credentials: ["AI governance credential (issuer TBD)"]
  tier_4_credentials: ["Product Compliance/CE", "ISO 50001 Lead Implementer"]
  professional_documents: "see section 17 gaps"
  evidence_gaps: "see section 16"
  regulatory_gaps: "see section 15"
  certification_gaps: "see section 12"
  unresolved_items: "see section 21 'Not fetched this session' list"
  priority_next_steps:
    - "Produce one real sanitized Evidence record from an already-tested component"
    - "Pursue ISA/IEC 62443 Fundamentals Specialist as the highest-fit Tier 1 credential"
    - "Resolve the public-repository push gap before making any public professional claims based on unpublished work"
```

---

## 24. Final Quality Gate (self-check)

Regulation/directive/standard identifiers fetched this session were reproduced as found (CRA, NIS2, AI Act, GDPR, Machinery Regulation, ISO/IEC 27001, ISO 50001, ISA/IEC 62443). Items not fetched this session are explicitly marked DOCUMENTED and listed for re-verification (§21), not presented as VERIFIED. No certification is claimed as EXISTING. No compliance claim is made. No measurement is fabricated. No architecture was rewritten to produce this document. CE terminology, EU-vs-national distinctions, and standard-vs-law distinctions are preserved (§3). Unresolved items are preserved as UNRESOLVED throughout, not silently resolved.

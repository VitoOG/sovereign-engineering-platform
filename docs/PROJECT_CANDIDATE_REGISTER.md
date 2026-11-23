# Imported Project Candidate Register

Artifact Type: SOURCE INVENTORY / RECONCILIATION REGISTER

Maturity Status: DESIGN (registry); source states below are historical classifications, not current runtime claims.

Source of record: `ERICAOS-FUNCTIONAL-STATE-20261113T015820Z.txt`, especially the source inventory summary, Static Code Map, Project Audit Index, and Implementation Disposition Matrix. Snapshot date: 2026-11-13.

## Purpose and interpretation

This register preserves the imported project and component inventory while distinguishing:

- **Project** — independently scoped engineering application or applied R&D domain.
- **Subsystem** — bounded component owned by a parent platform.
- **Shared capability** — reusable engineering function used by multiple projects.
- **Infrastructure candidate** — cross-project platform or data-plane capability.
- **Reference concept** — research/design material without evidence for a distinct implemented product.
- **Isolated candidate** — preserve separately pending security, domain, state-ownership, or safety review.

Historical file counts are scan results, not source LOC, completeness, build success, test success, runtime state, or product maturity. Historical disposition labels are provisional; they do not automatically describe current status.

## A. Inventory roots and file counts

| Historical source group | Files | Test-related | Build/manifests | Interpretation |
|---|---:|---:|---:|---|
| Golden Greens products | 70 | 5 | 8 | Applied CEA product source |
| Smart Greenhouse products | 98 | 2 | 13 | Greenhouse controller source |
| Applications | 190 | 37 | 17 | Mixed engineering applications |
| Infrastructure | 9 | 0 | 3 | Infrastructure source |
| Engineering Knowledge | 121 | 31 | 8 | Knowledge and tooling material |
| Public Portfolio | 4 | 0 | 0 | Public portfolio artifacts |
| ERICAOS Reconstruction Domains | 0 | 0 | 0 | Empty at scan time |
| ERICAOS 40-Implementation | 113 | 24 | — | Historical Python implementation |
| ERICAOS AI Router | 1 | — | — | Candidate router source |
| ERICAOS Control Center | 2 | — | — | Control Center artifacts |
| ERICAOS LLM Router | 7 | — | — | Router implementation candidate |
| ERICAOS Unified | 66 | 24 | — | Historical Unified implementation |
| Sovereign Platform | 24 | 6 | 3 | Platform source |
| Knowledge Graph Navigator | 10 | 1 | 1 | Knowledge-navigation candidate |

A dash means the historical summary did not provide that sub-count. Do not infer zero.

## B. Project and subsystem catalogue

| Candidate | Class | Parent / relationship | Historical disposition | SEP record |
|---|---|---|---|---|
| Golden Greens Crop / CEA-CPS | Applied R&D domain | Applied business and CEA domain | REBUILD | [Golden Greens](../projects/golden-greens/README.md) |
| Smart Greenhouse Controller | Child application | Golden Greens | REBUILD | [Smart Greenhouse](../projects/smart-greenhouse/README.md); existing [CASE-005](../case-studies/CASE-005/README.md) |
| CAR-TWIN / Car Twin Capture | Engineering application | Standalone capture/reconstruction system | INVENTORIED; detailed source map | [CAR-TWIN](../projects/car-twin/README.md); [CASE-009](../case-studies/CASE-009/README.md) |
| Industrial Runtime | Experimental runtime | Separate from ERICA OS workflow authority | ISOLATE | [Industrial Runtime](../projects/industrial-runtime/README.md); [CASE-010](../case-studies/CASE-010/README.md) |
| ERICA OS 40-Implementation | Historical platform generation | ERICA OS lineage | REFERENCE | [ERICA OS](../projects/ericaos/README.md) |
| ERICAOS Unified | Historical platform generation / reconstruction lineage | ERICA OS lineage | HISTORICAL / REFERENCE | [ERICA OS](../projects/ericaos/README.md) |
| Current Go target | Current ERICA OS implementation line in the historical report | ERICA OS | RETAIN; locally tested slice | [ERICA OS](../projects/ericaos/README.md) |
| ERICA AI Router / LLM Router | Platform subsystem candidates | ERICA model routing | ISOLATE / REFERENCE pending endpoint, auth, egress, and state-owner review | ERICA OS profile; no duplicate project page |
| ERICA Control Center | Platform subsystem | ERICA OS operations/control surface | INVENTORIED | ERICA OS profile; no duplicate platform |
| ERICA Swarm | Agent orchestration candidate | ERICA OS-adjacent; separate mission/task state | REFERENCE | [ERICA Swarm](../projects/erica-swarm/README.md) |
| Smart Library | Knowledge/library application candidate | ERICA knowledge subsystem | ADAPT | [ERICA Library](../projects/erica-library/README.md) |
| Shredder / Content Extraction | Extraction capability | ERICA Library ingestion pipeline | REFERENCE | [ERICA Library](../projects/erica-library/README.md) |
| Knowledge Forge | Downstream consolidation candidate | ERICA knowledge pipeline | INVENTORIED / source relationship requires validation | [ERICA Library](../projects/erica-library/README.md) |
| Knowledge Graph Navigator | Knowledge navigation application candidate | Potential ERICA Library graph UI/model | INVENTORIED | [Knowledge Graph Navigator](../projects/knowledge-graph-navigator/README.md) |
| SEP Edge Data Fabric | Shared infrastructure candidate | SEP / edge data contracts | REFERENCE | [Edge Data Fabric](../projects/edge-data-fabric/README.md) |
| Legacy Arduino Server | Historical hardware bridge | CEA / ERICA edge integration | REFERENCE | Shared implementation lineage; no duplicate product page |
| Workspace Starter | Design material | Engineering workspace conventions | REFERENCE | Retain in candidate register only |
| INFOFORGE | Knowledge concept | Knowledge engineering | REFERENCE | Retain in candidate register only |
| Information Gravity | Separate research/domain concept | Independent from ERICA runtime | ISOLATE | Retain in candidate register only |
| Funding Map | Research/business planning artifact | Funding intelligence | REFERENCE | Retain in candidate register only |
| SERVER-0001 archive | Historical archive | Provenance unresolved | REFERENCE | Retain in candidate register only |
| SERVER-PROJECT candidates | Infrastructure archaeology | Candidate source collection | REFERENCE | Retain in candidate register only |
| Omarchy remediation | Host-specific remediation | Outside SEP product scope | REJECT as SEP project | Do not create project page |
| Core-to-Swarm advisory adapter | Experimental integration adapter | ERICA ↔ Swarm advisory boundary | REFERENCE | Document under ERICA Swarm; no standalone project |

## C. Detailed application evidence captured in the historical static map

### CAR-TWIN

- 32 Python modules; 24 classes; 37 functions; 4 test modules; 1,311 lines.
- Capture orchestration, serial turntable, camera abstraction, calibration, motion planning, state machine, digital twin, dataset manifests, reconstruction interfaces.
- Test modules were inventoried; pass/fail status is not inferred from their presence.

### Industrial Runtime

- 31 Python modules; 44 classes; 83 functions; 11 test modules; 4,347 lines.
- ACL, contracts, FSM, event store/event sourcing, simulator/device/MQTT, migrations, health, metrics, logging, tracing.
- Earlier persisted `8 passed` result applies only to the FSM test slice; the wider project was described as an initial scaffold.

### Smart Greenhouse Controller

- Python API and application entry points, configuration, cycle/mode engines, crop-steering modules, automation logic, digital-twin and event modules, plus Arduino firmware.
- Existing CASE-005 remains the canonical case study. Do not create a second greenhouse case study.

## D. Historical 23-candidate implementation disposition

| ID | Candidate | 2026-11-13 disposition | Required interpretation |
|---|---|---|---|
| C-001 | Root Python Core / 40-Implementation | INVENTORIED / REFERENCE | Lineage and workspace mismatch unresolved |
| C-002 | Historical nested Python Unified | HISTORICAL / REFERENCE | Separate state layout and admission provenance unresolved |
| C-003 | Reconstruction scaffold | INVENTORIED / REFERENCE | Evidence/governance input, not target runtime |
| C-004 | Industrial Runtime | UNVERIFIED / ISOLATE | Domain and safety contracts unassessed |
| C-005 | Smart Library | UNVERIFIED / ADAPT | Schema/security/test comparison required |
| C-006 | Content Extraction tooling | UNVERIFIED / REFERENCE | Multiple historical versions; license/parser/sandbox review |
| C-007 | ERICA Swarm | UNVERIFIED / REFERENCE | Separate JSON task/mission state and operations unverified |
| C-008 | SERVER-0001 archive | HISTORICAL / REFERENCE | Provenance/license/behaviour unresolved |
| C-009 | SERVER-PROJECT candidates | INVENTORIED / REFERENCE | Archaeology is not operational proof |
| C-010 | Golden Greens CEA-CPS | INVENTORIED / REBUILD | Physical contracts/equipment/safety unresolved; HIL gate |
| C-011 | Smart Greenhouse Controller | INVENTORIED / REBUILD | Physical contracts/equipment/safety unresolved; HIL gate |
| C-012 | Legacy Arduino Server | HISTORICAL / REFERENCE | Legacy hardware/protocol role unknown |
| C-013 | Workspace Starter | INVENTORIED / REFERENCE | Design material only |
| C-014 | SEP Edge Data Fabric | INVENTORIED / REFERENCE | Data-fabric design not validated |
| C-015 | INFOFORGE | INVENTORIED / REFERENCE | Knowledge concept ownership reconciliation |
| C-016 | Information Gravity | INVENTORIED / ISOLATE | Separate domain/data governance |
| C-017 | Funding Map | INVENTORIED / REFERENCE | Research input, not platform runtime |
| C-018 | Omarchy remediation | HISTORICAL / REJECT | Host remediation outside target SEP product scope |
| C-019 | Current Go target | LOCALLY_TESTED / RETAIN | Verified local source/evidence/workflow/operations slice in historical report |
| C-020 | Standalone AI Router | UNVERIFIED / ISOLATE | Potential egress, no observed caller, port/auth/limit conflict |
| C-021 | Control/prompt policy docs | DESIGNED / REFERENCE | Declarations do not prove runtime enforcement |
| C-022 | Knowledge-System / Hermes | UNVERIFIED / REFERENCE | Dependency/path/schema unresolved |
| C-023 | Core-to-Swarm advisory adapter | EXPERIMENTAL / REFERENCE | Inference bridge does not share task authority |

## E. Admission rules for future project profiles

A candidate receives a dedicated `projects/*` page only when its ownership, purpose, boundaries, and evidence basis can be stated without duplicating a parent platform or shared capability.

- A child application remains linked to its parent applied domain.
- A subsystem remains a subsystem, even if its source repository is separate.
- Historical generations remain in lineage notes; they do not become parallel active platforms.
- REFERENCE and ISOLATE candidates remain visible in this register even when no detailed profile is justified.
- A file count, static symbol count, README assertion, or historical disposition never qualifies a runtime as VERIFIED.
- Public implementation claims require sanitized artifacts and reproducible instructions in this repository.

## F. Additional manifesto-domain profiles

The November 2026 manifesto describes nine connected domains. The following profiles preserve work that is not represented by the original imported 23-candidate source list. They are added as bounded profiles, not promoted to verified products.

| Profile | Classification | Evidence boundary | SEP record |
|---|---|---|---|
| ERICA Model Routing / Specialist Runtime | ERICA OS subsystem | Historical task-to-model routing and runtime observations; canonical current routing remains unresolved | [AI Model Routing](../projects/ai-model-routing/README.md) |
| Offline Knowledge Archive | Digital preservation project | Candidate collections and acquisition plan; complete acquisition and disconnected access not verified | [Offline Knowledge Archive](../projects/offline-knowledge-archive/README.md) |
| Security Engineering / DevSecOps / IT-OT | Cross-cutting engineering capability | Separate hardening, architecture, and authorized research workstreams; no unified security product | [Security Engineering](../projects/security-engineering/README.md) |
| Experimental Game and Agent Engineering | Research direction | Manifesto-level research scope; executable environment and benchmark not verified | [Experimental Agent Lab](../projects/experimental-agent-lab/README.md) |
| Alpine Edge Node | Private infrastructure asset | Historical Raspberry Pi / Alpine host and selected services; current runtime and public reproducibility not asserted | [Alpine Edge Node](../projects/alpine-edge-node/README.md) |

### Additional named components retained under parent ownership

- **CoreAgent / Jarvis / Hermes / supervisor concepts:** AI runtime, coding-agent, and orchestration lineage. These names are not automatically separate products; reconcile repository identity, implementation generation, and task authority before creating standalone profiles.
- **CANON task routing:** intended task-to-model selection contract. Configuration and historical aliases do not prove current route execution.
- **Knowledge Forge:** downstream consolidation capability within the ERICA knowledge pipeline; separate implementation and ownership remain unresolved.
- **Shredder:** extraction subsystem within ERICA Library; its specifications and bounded implementation slices must not be counted as independent platforms.
- **Ultima / Elite / assembly-language research:** source/game research context for the experimental agent domain. Do not claim a completed emulator, game, agent arena, or benchmark without source and run evidence.
- **Funding Map / INFOFORGE / Information Gravity:** retain as historical research/design candidates with their dispositions above; do not silently promote them to active products.
- **Independent R&D / engineering business:** organisational and commercialisation domain represented by Golden Greens Crop and the engineering-services positioning, not a separate software product.

## G. Provenance

This register is a reconciliation of the 2026-11-13 historical inventory, not a fresh scan of every private source tree. All source roots, commits, licenses, duplicate copies, and runtime states must be re-inspected before implementation, migration, publication of source, or status upgrade.

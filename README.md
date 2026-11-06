# Open-Source EMS Pilot Programme Kenya(OpenEMS Kenya)

## Introduction

Research programme on deploying an open-source energy management system, in Kenya's high-renewable grid.

Kenya generates over 80% of its electricity from renewables, but faces 23.4% system losses, rising peak demand (2,316 MW in Feb 2025), fast-growing EV charging and a 50% net-metering export credit. This project asks whether an open-source EMS can help stabilise the grid, reduce losses, lower energy costs and safely integrate EV charging, and whether doing so is technically, economically and institutionally viable.

## Documents

### A. Foundation and governance

|ID | Document | Purpose | Phase | Proposed owner | Audience | Status |
|:-:|:--------:|:-------:|:------:|:-------------:|:--------:|:------:|
|A1	| [Problem Statement](docs/Problem_Statement.md) | Background, research gap, central question, objectives, scope | Foundation | **Research lead** | Funders, partners | [x] |
|A2 | [Executive Summary](docs/Executive_Summary.md) | Context, OpenEMS capabilities, evidence, techno-economic framework, risks, pilot design | Foundation | **Research lead** | Funders, regulators | [x] |
|A3 | [Programme charter and governance plan](docs/Programme_Charter.md) | Roles, decision rights, steering committee, escalation | Planning | **Programme manager** | Steering group | [x] |
|A4 | [Stakeholder engagement plan](docs/Stakeholder_Engagement_Plan.md) | Engagement of Ministry of Energy, EPRA, Kenya Power, universities, communities | Planning | **Programme manager** | Stakeholders | [x] |
|A5 | [MoUs and site agreements](docs/MoU_and_Site_Agreement_Templates.md) | Data sharing, site access, asset ownership, liability | Planning | **Legal/regulatory lead** | Site hosts, partners | [x] |
|A6 | [Risk register](docs/Risk_Register.xlsx) | Regulatory, cybersecurity, maintenance, interoperability, economic risks with owners and mitigations | Planning, then ongoing | **Programme manager** | Steering group | [x] |

### B. Feasibility and design

|ID | Document | Purpose | Phase | Proposed owner | Audience | Status |
|:-:|:--------:|:-------:|:------:|:-------------:|:--------:|:------:|
|B1 | [Feasibility study](docs/Feasibility_Study.md) | Validates the techno-economic framework and the 15–30% savings claim locally | Planning | **Techno-economic analyst** | Funders, steering group | [x] |
|B2 | [Techno-economic model and assumptions book](docs/Techno-Economic_Model_and_Assumptions_Book.xlsx) | NPV, payback, LCOE, sensitivities (battery ±20%, discount rate 5–12%, net-metering credit) | Planning | **Techno-economic analyst** | Internal, reviewers | [x] |
|B3 | [Site survey reports (A, B, C)](docs/Site_Survey_Reports.md) | Load profiles, existing assets, grid connection, connectivity | Planning | **Technical lead** | Design team | [x] |
|B4 | [Technical specification per site](docs/Technical_Specification_per_Site.md) | System sizing, OpenEMS controller selection, device compatibility | Planning | **Technical lead** | Procurement, installers | [x] |
|B5 | [Regulatory compliance assessment](docs/Regulatory_Compliance_Assessment.md) | Net-metering rules, BESS and EV charger licensing, EPRA and Kenya Power interconnection | Planning | **Legal/regulatory lead** | EPRA, Kenya Power | [x] |
|B6 | [Interoperability and device compatibility register](docs/Interoperability_and_Device_Compatibility_Register.md) | Tested inverters, meters, chargers against OpenEMS drivers | Planning, then Installation | **Technical lead** | Technical team | [x] |
|B7 | [Cybersecurity plan](docs/Cybersecurity_Plan.md) | Authentication, encryption, remote access, audit scope | Planning | **Cybersecurity lead** | Technical team, Kenya Power ICT | [x] |

### C. Procurement and installation

|ID | Document | Purpose | Phase | Proposed owner | Audience | Status |
|:-:|:--------:|:-------:|:------:|:-------------:|:--------:|:------:|
|C1 | [Procurement plan and tender documents](docs/#) | Hardware sourcing, vendor criteria, local service availability | Procurement | **Procurement lead** | Vendors | [ ] |
|C2 | [Budget and cost tracker](docs/#) | Tracks against KSh 50–100m, with contingency use | All | **Finance lead** | Funders | [ ] |
|C3 | [Installation and commissioning plan](docs/#) | Sequence, safety, acceptance criteria | Installation | **Technical lead** | Installers, site hosts | [ ] |
|C4 | [OpenEMS configuration baseline](docs/#) | Version-controlled Edge configs per site | Installation | **Software engineer** | Technical team | [ ] |
|C5 | [Site acceptance test reports](docs/#) | Evidence that each site meets spec before operation | Installation | **Technical lead** | Steering group | [ ] |
|C6 | [Health, safety and environmental plan](docs/#) | Battery handling, electrical safety, end-of-life | Installation | **Site engineer** | Installers, hosts | [ ]|

### D. Operation and monitoring

|ID | Document | Purpose | Phase | Proposed owner | Audience | Status |
|:-:|:--------:|:-------:|:------:|:-------------:|:--------:|:------:|
|D1 | [Monitoring and evaluation plan](docs/#) | KPI definitions, baselines, measurement points, data frequency | Planning, then Operation | **M&E / data analyst** | Evaluators | [ ] |
|D2 | [Data management and privacy plan](docs/#) | Logging, storage, access, retention, consent | Planning | **Data analyst** | Partners, regulators | [ ] |
|D3 | [Operations and maintenance manual](docs/#) | Routine checks, battery plan, fault handling, escalation | Operation | **Technical lead** | Local operators | [ ] |
|D4 | [Training materials and attendance records](docs/#) | Operator and utility staff capacity building | Installation, Operation | **Capacity-building lead** | Operators, KPLC staff | [ ] |
|D5 | [Incident and change log](docs/#) | Outages, security events, config changes | Operation | **Technical lead** | Internal | [ ] |
|D6 | [Monthly performance reports](docs/#) | KPI trends: peak import reduction, self-consumption ratio, bill savings, uptime, transformer loading | Operation | **Data analyst** | Steering group | [ ] |

### E. Evaluation and dissemination

|ID | Document | Purpose | Phase | Proposed owner | Audience | Status |
|:-:|:--------:|:-------:|:------:|:-------------:|:--------:|:------:|
|E1 | [Interim evaluation report](docs/#) | Mid-pilot findings and course corrections | Operation | **M&E lead** | Steering group | [ ] |
|E2 | [Final evaluation report](docs/#) | Answers the central and supporting research questions | Evaluation | **Research lead** | Funders, regulators | [ ] |
|E3 | [Lessons learned and replication guide](docs/#) | Reusable deployment playbook for Kenya | Evaluation	| **Technical lead** | Developers, utilities | [ ] |
|E4 | [Policy brief](docs/#) | Recommendations on net-metering, BESS and EV rules | Evaluation | **Legal/regulatory lead** | Ministry, EPRA | [ ] |
|E5 | [Open-source release package](docs/#) | Configs, scripts and anonymised data under Apache 2.0 | Evaluation | **Software engineer** | Community | [ ] |
|E6 | [Academic paper or conference submission](docs/#) | Peer-reviewed evidence | Evaluation | **Research lead** | Academic community | [ ] |

## Research at a glance

- **Central question:** Can OpenEMS be deployed in Kenya to stabilise a high-renewable grid, reduce losses, lower energy costs and safely integrate EV charging?
- **Scenarios compared:** rural microgrid, commercial and industrial facility, EV charging depot.
- **Proposed pilot:** 24 months, multi-site, indicative budget of KSh 50–100 million.
- **Pilot KPIs:** `peak import reduction`, `self-consumption ratio`, `bill savings`, `system uptime`, `transformer loading`.

## Status

Early stage. Cost figures in the documents are indicative (2026 prices) and international savings figures (15–30%) have not yet been validated locally.

## License

Released under the [Apache License 2.0](LICENSE).

## References

- [OpenEMS](https://openems.io)

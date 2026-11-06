# Charter and Governance Plan

## 1. Document Purpose

This document does two things. Part A (the Charter) formally defines what the programme is, why it exists, what it will deliver and who is accountable. Part B (the Governance Plan) sets out how the programme will be directed, controlled, funded, reported and closed. Together they give the Ministry of Energy, EPRA, Kenya Power, funders and delivery partners a single reference for decision-making.

# Part A: Programme Charter

## 2. Background and Justification

Kenya generated over 80% of its electricity from renewables in FY2024/25, led by geothermal (39.5%) and hydro (24.2%), with wind (13.2%) and utility solar (3.3%). Demand is growing quickly: peak load reached 2,316 MW in February 2025 (up 6.4% year on year) and EV tariff consumption grew 300% to 5.04 GWh. Variable renewables can reach about 34% of the instantaneous mix, system losses averaged 23.4% against a 17.5% regulatory benchmark, and the 2024 Net-Metering Regulations credit exports at only 50% of each kWh.

Most customers and distribution assets have no automated way to coordinate batteries, solar PV, loads and EV chargers. Proprietary energy management systems carry licence fees and vendor lock-in. OpenEMS is an open-source, device-agnostic alternative, but there is no documented evidence of how well, and at what cost, it performs under Kenyan grid, regulatory, climatic and skills conditions. International savings of roughly 15–30% have not been validated locally. This programme exists to close that evidence gap.

## 3. Vision, Mission and Central Question

**Vision.** A validated, low-cost, open-source EMS that helps protect the reliability of Kenya's renewable-dominated grid, cut avoidable losses, improve the economics of solar and storage, and prepare distribution networks for rapid EV uptake.

**Mission.** Design, deliver and openly publish a 24-month, multi-site pilot that produces the first locally validated evidence of OpenEMS performance in Kenya.

**Central research question.** Can OpenEMS be deployed in Kenya to stabilise a high-renewable grid, reduce losses, lower energy costs and safely integrate EV charging, and is it technically, economically and institutionally viable to do so?

## 4. Objectives

| # | Objective | Linked supporting question |
| --- | --- | --- |
| O1 | Assess the suitability of OpenEMS against Kenya's grid, tariff and regulatory context | Regulatory, cybersecurity, maintenance and capacity risks |
| O2 | Build a techno-economic framework comparing a rural microgrid, a C&I facility and an EV charging depot | Bill savings and payback under ToU tariffs and the 50% net-metering credit |
| O3 | Identify key risks and mitigation measures and maintain a live risk register | Regulatory, cybersecurity, maintenance and capacity risks |
| O4 | Design and deliver a 24-month, multi-site pilot with defined KPIs | Peak smoothing, loss reduction and EV transformer protection |

## 5. Scope

**In scope**

- Grid-connected and mini-grid applications at the distribution and customer level in Kenya, using OpenEMS Edge as the control platform
- Three pilot sites: Pilot A (industrial park or energy hub, existing or new PV with about 250 kWh battery), Pilot B (rural microgrid, 50–100 kW PV with about 200 kWh battery) and Pilot C (EV charging site, about 10–20 fast chargers with an optional small battery)
- Smart metering at each grid connection and added voltage and transformer-loading measurement where needed
- Techno-economic modelling, sensitivity analysis, risk register, operator training and open publication of findings
- An optional OpenEMS Backend for multi-site monitoring, potentially hosted by the Ministry of Energy

**Out of scope**

- Transmission-level planning and utility-scale generation
- Commercial roll-out beyond the three pilot sites
- Changes to tariffs or regulations (the programme informs these but does not decide them)
- Core development of OpenEMS beyond custom drivers or configuration needed for local hardware

## 6. Deliverables

| ID | Deliverable | Indicative timing |
| --- | --- | --- |
| D1 | Detailed feasibility study and stakeholder consultation report | Months 1–4 |
| D2 | Techno-economic model (three scenarios, with and without OpenEMS control) | Months 2–6 |
| D3 | Risk register and mitigation plan, including cybersecurity audit plan | Month 3, then continuous |
| D4 | Site specifications and compatibility test report for local hardware | Months 4–8 |
| D5 | Commissioned pilot installations at Sites A, B and C | Months 7–12 |
| D6 | Trained local OpenEMS implementation team and operator training materials | Months 6–14 |
| D7 | Monthly performance data sets and analysis reports | Months 13–24 |
| D8 | Final evaluation report, validated cost-savings findings and open publication | Months 22–24 |

Timings are relative to programme start. The research report's planning timeline places launch in 2027, with Year 1 for design, procurement, installation and commissioning, and Year 2 for operation, monitoring and analysis.

## 7. Success Criteria and KPIs

The programme measures each site against a pre-agreed baseline (storage idle or unmanaged). Numeric targets are to be set during feasibility (Next Step 4) and approved at Gate 1.

| KPI | Applies to | Target |
| --- | --- | --- |
| Peak grid import reduction (kW and %) | A, B, C | \[To be set at Gate 1\] |
| Renewable self-consumption ratio | A, B | \[To be set at Gate 1\] |
| Bill savings (KSh), compared with the 15–30% international range | A, B | \[To be set at Gate 1\] |
| System uptime and availability | A, B, C | \[To be set at Gate 1\] |
| Transformer loading (kW) and share of time chargers operate at full capacity | C | \[To be set at Gate 1\] |
| Technical and commercial loss reduction on served customers | B | \[To be set at Gate 1\] |

**Programme-level success** means: all three sites commissioned and operating; at least 12 months of continuous validated data; KPI results published openly; a techno-economic model and risk register adopted by at least one regulator or utility partner; and a trained local team able to operate and support OpenEMS without continuous foreign support.

## 8. Indicative Budget and Funding

The indicative budget for the full pilot is **KSh 50–100 million (about USD 400–800k)**, covering hardware, integration, installation, training and evaluation. Individual sites are estimated at USD 50k–150k depending on scale. OpenEMS carries no licence cost. All figures are indicative, in 2026 prices with inflation assumed at about 5% per year, and must be validated by the feasibility study before Gate 1.

The research report's reference cost structure for a 100 kW PV plus 300 kWh BESS site is a guide for budget allocation:

| Cost category | Share |
| --- | --- |
| Hardware (PV, BESS, inverters, meters) | 40% |
| Software and integration | 20% |
| First-year O&M | 15% |
| Installation and civil works | 10% |
| Contingency | 10% |
| Training and capacity building | 5% |

Contingency of 10–20% is held centrally by the Steering Committee, not by site teams. Funding sources and commitments: \[to be confirmed\].

## 9. Stakeholders and Roles

| Stakeholder | Interest and role in the programme |
| --- | --- |
| Ministry of Energy | Policy support; possible Backend host; evidence for national policy |
| EPRA | Tariff, standards and licensing liaison; regulatory guidance for BESS and EV charging |
| Kenya Power | Grid interface, data access and interconnection approvals |
| Local utilities and cooperatives | Operations and local service at pilot sites |
| University partners (e.g. Kenyatta University's Energy Institute) | Independent evaluation, research partnership, training |
| Technology partners (batteries, solar, telecoms, charger vendors) | Equipment supply, installation and service |
| Host site owners and communities | Site access, operation and social acceptance |
| Funders | Financing and accountability for results |

## 10. Assumptions, Constraints and Dependencies

**Assumptions**

- Suitable host sites can be secured for A, B and C within the first four months.
- Selected hardware can be integrated with OpenEMS drivers, or custom drivers can be built within budget.
- Kenya Power and EPRA will permit pilot connections and data access.

**Constraints**

- Fixed 24-month duration and the indicative KSh 50–100 million envelope
- Limited local OpenEMS expertise and a small, mostly European core developer community
- Intermittent connectivity at rural sites

**Dependencies**

- Regulatory clarity, including confirmation of net-metering terms
- Completion of the detailed feasibility study before procurement
- Independent cybersecurity audit before remote connection of any site

## 11. Authority and Approval

The Steering Committee (Section 13) holds delegated authority to approve scope, budget and stage gates within the envelope in this charter. Any change that exceeds the tolerances in Section 20 returns to the Programme Sponsor.

| Role | Name | Signature | Date |
| --- | --- | --- | --- |
| Programme Sponsor | \[Name, Organisation\] |  |  |
| Steering Committee Chair | \[Name, Organisation\] |  |  |
| Programme Director | \[Name, Organisation\] |  |  |
| Principal Funder representative | \[Name, Organisation\] |  |  |

# Part B: Governance Plan

## 12. Governance Principles

- **Evidence first.** Decisions rest on measured data; international figures are treated as hypotheses until validated locally.
- **Open by default.** Methods, code changes, data and findings are published, subject to security and privacy safeguards.
- **Regulator involvement from the start.** The Ministry of Energy and EPRA are engaged before design decisions, not after.
- **Safety and security before speed.** No site connects remotely until its security review is passed.
- **Local capacity as a deliverable.** Skills transfer is governed and measured like any technical output.
- **Proportionate control.** Governance effort scales to risk and spend.

## 13. Governance Structure

| Body | Composition | Core responsibility |
| --- | --- | --- |
| Programme Steering Committee (SteerCo) | Chair from Ministry of Energy or lead funder; representatives of EPRA, Kenya Power, principal funder, university partner and Programme Director (non-voting) | Strategic direction, stage-gate approvals, budget and contingency, escalated risks and changes |
| Programme Management Office (PMO) | Programme Director, Programme Manager, finance and procurement lead, risk and quality officer | Day-to-day delivery, planning, reporting, financial control, risk register and change log |
| Technical Working Group (TWG) | Lead OpenEMS engineer, site engineers, hardware and cybersecurity specialists, Kenya Power grid engineer | Architecture, drivers, interoperability testing, commissioning standards, data quality |
| Research and Evaluation Panel | University partner lead, independent economist or data analyst, EPRA observer | Measurement and verification protocol, baseline integrity, validation of savings claims |
| Regulatory and Stakeholder Forum | Ministry of Energy, EPRA, Kenya Power, utilities, community representatives, technology partners | Regulatory alignment, community and stakeholder input; advisory, not decision-making |
| Site Teams (A, B, C) | Site lead, host representative, installer, operator trainees | Local delivery, operation, safety and data collection |

### Key roles

- **Programme Sponsor** owns the business case and appoints the SteerCo Chair.
- **Programme Director** is accountable to the SteerCo for delivery within scope, time and budget.
- **Programme Manager** runs the PMO, plans, reporting and change control.
- **Technical Lead** owns architecture and OpenEMS configuration and chairs the TWG.
- **Research Lead** owns the evaluation method and the integrity of reported results, and reports independently to the Research and Evaluation Panel.
- **Cybersecurity and Data Protection Officer** owns security controls, audits and data-handling compliance.
- **Site Leads** are accountable for site safety, schedule and data capture.

## 14. Decision Rights (RACI)

R = Responsible, A = Accountable, C = Consulted, I = Informed.

| Decision or activity | SteerCo | Programme Director | PMO | TWG | Research Panel | Regulators and Kenya Power |
| --- | --- | --- | --- | --- | --- | --- |
| Approve charter and stage gates | A | R | C | C | C | C |
| Select pilot sites | A | R | C | C | C | C |
| Approve KPI targets and baselines | A | R | C | C | R | C |
| Approve procurement above threshold | A | R | R | C | I | I |
| Technical architecture and driver choices | I | A | C | R | I | C |
| Cybersecurity audit sign-off | I | A | C | R | I | C |
| Grid interconnection and compliance | I | A | C | R | I | R |
| Change requests beyond tolerance | A | R | R | C | C | I |
| Publication of results | A | R | C | C | R | C |
| Programme closure | A | R | R | C | C | I |

## 15. Meetings and Reporting Cadence

| Forum | Frequency | Inputs | Outputs |
| --- | --- | --- | --- |
| SteerCo | Quarterly, plus gate reviews | Programme dashboard, risk and change reports, financial statement | Decisions, minutes, gate approvals |
| PMO review | Fortnightly | Workstream updates, risk and issue logs | Action log, escalation list |
| TWG | Fortnightly during build, monthly in operation | Test results, defect log, security findings | Technical decisions, configuration baselines |
| Research and Evaluation Panel | Monthly in operation | Monthly KPI data and analysis | Validated KPI report, data quality notes |
| Regulatory and Stakeholder Forum | Twice a year | Progress summary, emerging findings | Regulatory feedback, stakeholder concerns |
| Site operations check-in | Weekly | Uptime, alarms, safety incidents | Site actions |

The monthly programme dashboard reports progress against milestones, KPI trends, spend against budget, top risks, open issues, change requests, security incidents and training progress.

## 16. Stage Gates

Each gate is a SteerCo decision to proceed, proceed with conditions, or stop. Month references are relative to programme start.

| Gate | Timing | Decision | Key evidence required |
| --- | --- | --- | --- |
| Gate 0: Mobilise | Month 0 | Approve charter, governance and feasibility funding | Signed charter, sponsor and funder commitment |
| Gate 1: Design approval | Month 4–6 | Approve sites, KPI targets, validated budget and procurement plan | Feasibility study, techno-economic model, host agreements, regulatory clarity on net-metering, risk register |
| Gate 2: Build readiness | Month 8 | Release installation funds | Compatibility test report, security design review, safety plans, trained installers |
| Gate 3: Go-live | Month 12 | Authorise operation and remote connection | Commissioning certificates, passed cybersecurity audit, baselines recorded, operators trained |
| Gate 4: Mid-operation review | Month 18 | Confirm continued operation or corrective action | Six months of validated data, uptime results, early KPI trends |
| Gate 5: Closure | Month 24 | Accept results, approve publication and handover | Final evaluation report, asset handover, lessons learned |

A stop decision at Gate 1 is a legitimate outcome: a well-evidenced finding that OpenEMS is not viable under Kenyan conditions is still a successful research result.

## 17. Financial Governance

- **Budget control.** The PMO maintains a single programme budget with site sub-budgets; the finance lead reports monthly.
- **Contingency.** Held centrally; release requires Programme Director recommendation and SteerCo approval.
- **Procurement.** Competitive procurement for hardware and services, with compatibility testing before award. Proposed thresholds, to be confirmed with funders: below KSh \[X\] approved by the Programme Director; KSh \[X\] to \[Y\] approved by two PMO signatories; above KSh \[Y\] approved by the SteerCo.
- **Audit.** Annual independent financial audit and funder audit rights as agreed in funding agreements.
- **Cost sensitivity.** The PMO reviews exposure to battery cost, tariff spreads and exchange rates each quarter, using the sensitivity ranges in the techno-economic framework (battery cost ±20%, discount rate 5–12%).
- **Assets.** Ownership of installed equipment, and arrangements at closure, are defined in host agreements before procurement.

## 18. Risk Management

The PMO owns the risk register, reviewed fortnightly and reported to the SteerCo quarterly. Each risk has an owner, rating, mitigation and trigger. Initial risks carried from the executive summary:

| Risk | Owner | Mitigation | Escalation trigger |
| --- | --- | --- | --- |
| Regulatory change (net-metering credit, BESS and charger licensing) | Programme Director | Engage Ministry of Energy and EPRA from the start; test sensitivity to lower export credits | Any formal proposal to change net-metering or licensing rules |
| Cybersecurity of remotely connected assets | Cybersecurity Officer | Independent audit, authentication and encryption, data-handling protocols | Any critical finding or confirmed incident |
| Limited local OpenEMS expertise | Technical Lead | Build a local team, train operators, partner with universities | Fewer than planned trainees certified at Gate 3 |
| Interoperability with local hardware | Technical Lead | Compatibility testing before procurement; budget for custom drivers | Failed compatibility test on a selected device |
| Poor rural connectivity | Site Lead (Pilot B) | Rely on Edge local control; cache data and sync when connected | Data gaps above agreed threshold |
| Cost overruns or tariff changes | Programme Manager | 10–20% contingency; quarterly sensitivity review | Forecast overrun above tolerance |
| Delay in host site or interconnection approval | Programme Director | Early engagement with Kenya Power; shortlist of backup sites | Approval not secured by Gate 1 |
| Savings fall short of the 15–30% international range | Research Lead | Report results honestly with context; no re-baselining without Panel approval | Interim results trend below range at Gate 4 |

## 19. Cybersecurity, Data and Safety Governance

- **Security.** Remote connection of a site requires a passed independent security audit (Gate 3), authentication and encryption, role-based access and a logged change process for Edge configuration. Open-source code is public, so security depends on configuration, patching and access control. An incident response plan names an owner and notification routes to Kenya Power and, where required, EPRA.
- **Data.** The PMO defines what is collected, who may access it and how long it is retained, in line with Kenyan data protection law and host agreements. Customer-level data is anonymised or aggregated before publication.
- **Data quality.** The Research Panel approves the measurement and verification protocol, meter accuracy checks and baseline method before data collection starts.
- **Safety.** Electrical work follows applicable Kenyan standards and utility requirements, with site safety plans approved before installation and incidents reported to the SteerCo.
- **Resilience.** Edge devices must continue local control during internet outages; this is tested at commissioning.

## 20. Change Control and Tolerances

All changes to scope, schedule, budget, KPIs or architecture are raised as a change request, assessed by the PMO and TWG, and logged. Proposed tolerances:

| Dimension | Programme Director may approve | SteerCo approval required |
| --- | --- | --- |
| Schedule | Slippage up to 4 weeks on non-gate milestones | Any gate date movement or slippage beyond 4 weeks |
| Budget | Reallocation within a site up to 5% | Any reallocation between sites, any contingency use, any increase to the total |
| Scope | Minor technical substitutions of equivalent function | Change of site, KPI or objective |
| KPIs and baselines | None after Gate 1 | Any change, with Research Panel advice |

## 21. Open-Source, Intellectual Property and Publication Governance

- **Licensing.** The programme repository is released under Apache 2.0. OpenEMS Edge and Backend are released under the Eclipse Public License 2.0 and its user interface under AGPL 3.0; the Technical Lead maintains a licence compliance register so that any modified or redistributed OpenEMS component meets its licence terms, including the network-use provisions of AGPL 3.0 for the UI.
- **Contribution.** Custom drivers and fixes are developed in the open and, where appropriate, offered upstream to the OpenEMS community, subject to TWG review.
- **Publication.** Results are published openly after a Research Panel check for accuracy and a security and privacy review. Negative or inconclusive findings are published with equal prominence.
- **Independence.** The Research Lead reports evaluation results without editorial control by equipment suppliers or funders.

## 22. Stakeholder and Community Engagement

- A stakeholder register, maintained by the PMO, records interests, influence and engagement plan for each group in Section 9.
- Host communities and site owners are consulted before site selection and receive plain-language updates at least quarterly, in English and Kiswahili where relevant.
- A complaints and feedback channel is established at each site and reviewed monthly by the PMO.
- Operator and community training is tracked as a KPI: number trained, assessed competence and retention.

## 23. Quality Assurance and Evaluation

- Each deliverable has acceptance criteria agreed at Gate 1 and is reviewed by a person independent of its author.
- Commissioning follows a standard checklist covering electrical safety, control behaviour, offline operation, data logging and security.
- The evaluation compares each site against its baseline with and without OpenEMS control, reporting peak import, energy cost, self-consumption, uptime and transformer loading, and states uncertainty and limitations.
- A lessons-learned review is held at Gates 3 and 5 and shared with partners.

## 24. Programme Closure and Sustainability

At Gate 5 the programme will confirm that all deliverables are accepted; hand over or decommission equipment as set out in host agreements; archive code, data and documents in a public repository; transfer the risk register, techno-economic model and training materials to named custodians (for example the Ministry of Energy, EPRA, Kenya Power or the university partner); and agree a post-pilot plan covering ongoing support, scale-up options and any funding needed to continue operation.

## 25. Immediate Next Steps

1. Confirm Programme Sponsor, SteerCo Chair and members, and obtain signatures on the charter (Gate 0).
2. Secure regulatory clarity, including confirmation of net-metering terms, through the Ministry of Energy and EPRA.
3. Appoint the Programme Director, Technical Lead, Research Lead and Cybersecurity Officer.
4. Commission the detailed feasibility study and set KPI targets for each site.
5. Begin host site shortlisting and early engagement with Kenya Power on interconnection.
6. Establish the local OpenEMS implementation team and training plan.
7. Set up the risk register, change log, stakeholder register and monthly dashboard template.

## Appendix: Glossary

- **BESS:** Battery energy storage system
- **C&I:** Commercial and industrial
- **EPRA:** Energy and Petroleum Regulatory Authority
- **EMS:** Energy management system
- **KPI:** Key performance indicator
- **PMO:** Programme Management Office
- **ToU:** Time-of-Use (tariff)
- **VRE:** Variable renewable energy

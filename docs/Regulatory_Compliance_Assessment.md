# Regulatory Compliance Assessment


## 1. Purpose and bottom line

This assessment identifies which Kenyan laws, licences, permits and approvals are likely to apply to Pilots A, B and C, what is known and unknown today, and what must be secured before each stage gate. It supports Gate 1 condition 1 (written EPRA position) and condition 2 (Kenya Power agreement in principle) in the Feasibility Study, and feeds site conditions precedent in the draft Host Site Agreements.

**Bottom line.** The pilot is not blocked by any known legal barrier, but it cannot be cleared from desk research. Five points are on the critical path:

1. **Net-metering terms for Pilot A** (Energy (Net-Metering) Regulations 2024, 50% export credit) are unconfirmed for the candidate site category.
2. **Licensing or permit treatment of battery storage (BESS)** at all three sites is unconfirmed.
3. **Mini-grid operation and tariffs at Pilot B** depend on who the operator is and whether EPRA treats the site as a licensable activity.
4. **EV charging station licensing** at Pilot C is unconfirmed.
5. **Kenya Power interconnection approval** has not been applied for for any site.

The data protection regime (Data Protection Act, 2019) is certain to apply to Pilots B and C and to utility data sharing, and is within the programme's own control.

**Recommendation.** Send a single, structured written request to EPRA and Kenya Power in Month 1 (not Month 3), using the questions in Appendix A. Treat a documented "no licence required" or "exemption with conditions" answer as a Gate 1 deliverable.

## 2. Scope, method and limits

**In scope.** Regulatory and compliance requirements for design, installation, operation, data collection and closure of the three pilots, as described in the Charter, Technical Specification (B4) and Site Survey Reports (B3).

**Out of scope.** Changing tariffs or regulations (the programme informs but does not decide them), and transmission or utility-scale matters.

**Method.** The assessment (1) lists candidate legal instruments and regulators, (2) maps them to each pilot, (3) rates each item for applicability and certainty, and (4) assigns an owner, evidence and a needed-by date tied to the gates.

**Limits.**

- No site is selected, so site-specific permits (county, building, environmental) are described generically.
- The underlying research report and the Risk Register workbook were not available in readable form. Regulatory risks below should be merged into the live register.
- Regulatory texts were not reviewed line by line. Where a rule is described, it is described as the programme documents state it.

**Rating key.** *Certainty*: High (the law clearly applies), Medium (likely applies, scope to confirm), Low (may apply, position unknown). *Status*: Not started, In progress, Confirmed.

## 3. Regulators and authorities

| Authority | Role for the programme | Engagement route |
| --- | --- | --- |
| Ministry of Energy and Petroleum | Policy support, SteerCo chair or member, possible OpenEMS Backend host | Policy and regulatory MoU (Schedule 1A) |
| Energy and Petroleum Regulatory Authority (EPRA) | Licensing and permits, net-metering terms, tariffs, standards, mini-grid and charging guidance, observer on the Research and Evaluation Panel | Policy and regulatory MoU; written position request |
| Kenya Power and Lighting Company PLC | Interconnection, metering, protection, power quality, feeder and transformer data, safety review of commissioning | Kenya Power MoU (Schedule 1B); technical working group |
| Office of the Data Protection Commissioner (ODPC) | Registration of data controllers and processors, breach notification | Data protection plan (D2) |
| National Commission for Science, Technology and Innovation (NACOSTI) and university ethics committee | Research licence and ethics clearance | University MoU (Schedule 1C) |
| County governments | Building, land use, signage and local permits | Site Leads at site selection |
| National Environment Management Authority (NEMA) | Environmental screening for battery and PV installations \[confirm thresholds\] | Site Leads, HSE plan (C6) |
| Directorate of Occupational Safety and Health Services (DOSHS) and fire authorities | Workplace safety, fire safety for battery rooms | Site safety plans |
| Kenya Revenue Authority and related import bodies | Duties and taxes on imported equipment | Procurement lead |

## 4. Legal instruments register

| # | Instrument | Relevance | Certainty | Notes |
| --- | --- | --- | --- | --- |
| 1 | Energy Act, 2019 | Framework for licensing of generation, distribution and related activities; EPRA powers; referred to in Host Site Agreement Section 17 | High | Scope for small-scale, behind-the-meter and storage activities to be confirmed |
| 2 | Energy (Net-Metering) Regulations 2024 | Export crediting at 50% per kWh; eligibility and capacity limits for Pilot A | High (Pilot A) | Eligibility, capacity cap and application process to be confirmed in writing |
| 3 | Regulations on solar photovoltaic systems and licensing of solar contractors \[confirm current instrument and any updates\] | Installers of PV may need EPRA-recognised licences | Medium | Check licences held by candidate installers |
| 4 | Electric power licensing and mini-grid regulations or draft regulations \[confirm current status\] | Pilot B operator and tariff arrangements | Medium | Draft or recent rules may change the position; verify |
| 5 | EPRA guidance or rules on EV charging stations and storage \[confirm if any exist\] | Pilot C and BESS at all sites | Low | Source documents say licensing is unconfirmed |
| 6 | Kenya Power grid code, interconnection and metering standards \[confirm current versions\] | Protection, anti-islanding, metering class, power quality | High (A, C; B if grid-connected) | Obtain from Kenya Power |
| 7 | Data Protection Act, 2019 and regulations | Household data (B), charger session data (C), customer data (A), utility data sharing | High | Registration, roles, breach notification |
| 8 | Occupational Safety and Health Act, 2007 and related rules | Installation, operation and maintenance safety; fire safety | High | Site safety plans |
| 9 | Environmental Management and Coordination Act, 1999 and EIA regulations | Environmental screening; battery waste and end-of-life | Medium | Screening threshold depends on size and location |
| 10 | Science, Technology and Innovation Act and NACOSTI requirements | Research licence for data collection involving people | Medium | Applies where data about participants is collected |
| 11 | Bribery Act, 2016 | Procurement and counterparties | High | Referred to in MoU Section 13 |
| 12 | Arbitration Act, 1995 | Dispute resolution in MoUs and agreements | High | Public-body limits to be confirmed by counsel |
| 13 | Public procurement rules \[apply only if public funds or public bodies procure\] | Depends on funding structure and contracting entity | Low | Confirm once the Programme Lead entity and funders are known |
| 14 | Standards (electrical installation, battery, EV charger) \[IEC or equivalent to be named\] | Equipment certification and insurer acceptance | Medium | Technical Specification names standards as an open item |

## 5. Compliance by topic

### 5.1 Net-metering and export (Pilots A and, if applicable, B)

**What is known.** The 2024 Regulations credit exports at 50% of each kWh. This favours self-consumption and storage, which is what OpenEMS is designed to optimise.

**Unknowns.** Whether the candidate Pilot A host category is eligible, any capacity or system-size cap, whether adding a battery to an existing net-metered PV system needs a new or amended application, the treatment of stored-then-exported energy, and the application lead time.

**Implications.**

- A written EPRA and Kenya Power position is a Gate 1 condition and appears in Host Site Agreement Pilot A special conditions.
- The economic model must test export credits below 50% throughout. Any formal proposal to change net-metering is an escalation trigger.
- The export limit set in OpenEMS (Technical Specification 5.2) must follow the approved limit, and acceptance test A5 verifies it.
- Net-metering applications, credits and bills remain between the host and the utility, not the programme (Host Agreement 8.2).

### 5.2 Battery storage licensing and permits (all pilots)

**Position.** Unconfirmed. It is not known whether behind-the-meter BESS at these sizes (about 200–250 kWh) needs a licence, permit or notification, or is exempt below a threshold.

**Actions.**

- Ask EPRA the specific questions in Appendix A, including thresholds, who must hold any permit (host, programme entity or installer), and whether a research pilot can use an exemption or sandbox.
- If an exemption or sandbox is granted, annex its conditions to the policy and regulatory MoU, where they bind the programme (Schedule 1A special clause).
- Make any required permit a condition precedent in each Host Site Agreement (Section 3).

### 5.3 Mini-grid and rural supply (Pilot B)

**Why it is the most sensitive item.** Pilot B involves supply to households and businesses, an operator, tariffs and possibly diesel generation. Regulatory treatment depends on topology (Technical Specification 6.1): grid-connected on a long feeder, mini-grid with grid, or isolated.

**Questions to settle.**

- Does the activity at Pilot B need a licence, permit or registration, and for whom (cooperative, estate, utility)?
- Which tariff rules apply to customers served, and who approves them?
- If the site is utility-served, does Kenya Power or the operator hold the supply relationship, and how does a PV and battery system on a feeder fit the licensing framework?
- What are the consumer protection and quality of supply obligations?

**Programme commitments already drafted.** No disconnection or price increase to customers because of the pilot; defined operator; fallback to local control. These must be consistent with whatever EPRA confirms.

**Decision point.** If licensing cannot be resolved by Gate 1, shortlist an alternative Pilot B site with a clearer regulatory path (Feasibility Study Section 10).

### 5.4 EV charging (Pilot C)

**Position.** EPRA guidance on charging station licensing is unconfirmed. Charging revenue stays with the site operator, so the operator is likely to be the party with any licensing or registration duty.

**Other points.**

- Managed charging (throttling) may affect customers' expectations and consumer rights. The charging policy and maximum wait time must be disclosed to drivers (Technical Specification 7.2).
- Any tariff or pricing display requirements for charging should be confirmed \[confirm with EPRA\].
- Kenya Power transformer data access and the site limit must be agreed with Kenya Power. OpenEMS protects the transformer by limiting site load, not by controlling utility assets.
- Charger equipment must meet applicable standards and communicate by OCPP, with vendor cooperation recorded in the site agreement.

### 5.5 Grid interconnection and utility requirements (A, C, and B if grid-connected)

| Requirement | Action | Evidence |
| --- | --- | --- |
| Interconnection application and fees | Submit early for A and C; for B once topology is known | Kenya Power agreement in principle by Gate 1 |
| Protection, anti-islanding and power quality | Confirm settings and approved inverter list | Kenya Power acceptance of design (Gate 2) |
| Metering | Confirm required meter class, who owns the meter, and whether the research meter can share the connection | Metering plan in B4 and B6 |
| Transformer and feeder data | Data sharing agreement and read access | Signed agreement before Gate 3 baselines |
| Control authority | Confirm in writing that OpenEMS controls only assets behind the connection point | MoU Schedule 1B |
| Commissioning witness | Invite Kenya Power to witness commissioning | Commissioning certificate (Gate 3) |

### 5.6 Data protection and privacy

| Pilot | Data | Personal data? | Controls |
| --- | --- | --- | --- |
| A | Interval load, bills, tariff terms | Mostly commercial; may identify the host | Confidentiality in site agreement; aggregate before publication |
| B | Household consumption | Yes | Consent and notice at community meetings; aggregate before sharing |
| C | Charger session logs | Yes, if drivers or vehicles can be identified | Pseudonymise; no payment data; privacy notice displayed at site |
| All | Utility feeder and transformer data | Possibly, at customer level | Data sharing agreement; anonymise before publication |

**Actions.**

- Determine, before any sharing, whether each party is controller, joint controller or processor (MoU Section 7.2), and record it in Schedule 6 of each site agreement.
- Check whether the Programme Lead entity and the Backend host must register with the ODPC and what impact assessment is required \[confirm with counsel\].
- Adopt the 48-hour internal breach notification to the PMO already drafted in the MoU, and map it to the statutory notification duties to the ODPC.
- Approve a retention and access plan in the data management plan (D2) before data collection starts.
- If data is hosted or processed outside Kenya (for example a Backend or cloud service), confirm the rules on cross-border transfer \[confirm with counsel\].

### 5.7 Cybersecurity

No Kenyan statute is assumed here to impose specific obligations on these installations, but critical-infrastructure and computer misuse rules may be relevant \[confirm with counsel, and with Kenya Power ICT\]. The programme's own controls are the main compliance lever: independent audit before remote connection (Gate 3), segmentation, authentication and encryption, logged change control, and an incident plan with notification routes to Kenya Power, EPRA where required, and the ODPC for personal data breaches.

### 5.8 Health, safety, fire and environment

- Electrical work only by licensed contractors, to applicable Kenyan standards and Kenya Power requirements.
- Site safety plan, battery fire risk assessment and emergency response plan agreed with local responders before installation (Gate 2). Insurer acceptance recorded.
- Environmental screening for each site, including battery location, drainage, waste and decommissioning. Confirm with NEMA whether an assessment or notification is required \[confirm thresholds\].
- Battery transport, storage and end-of-life must follow applicable waste and hazardous-material rules \[confirm\]. The decommissioning route and cost are to be fixed in Schedule 4 before procurement.
- County building and fire permits to be identified at site selection.

### 5.9 Research approvals

The university partner should confirm whether a NACOSTI research licence and institutional ethics clearance are needed, particularly for household data at Pilot B and driver data at Pilot C. These are required before data collection starts and are listed in the University MoU (Schedule 1C).

### 5.10 Contracting entity, procurement, tax and equipment title

- **Legal entity.** The Charter names no contracting entity. A legal person must be named at Gate 0 to sign MoUs and site agreements, hold insurance and, if applicable, hold equipment title. Registration status, tax status and any public-body constraints depend on this choice.
- **Procurement rules.** If public funds or a public entity procure, public procurement law may apply. Confirm once the entity and funders are known. Thresholds in Charter Section 17 remain placeholders.
- **Import duties and taxes.** Duty and VAT treatment of imported batteries, inverters and chargers, and any available relief for research or renewable equipment, to be confirmed with advisers \[confirm\].
- **Equipment title.** The choice between Programme Lead, funder or host ownership affects tax, insurance, warranty and licensing duties.

### 5.11 Open-source licences and intellectual property

OpenEMS Edge and Backend are under the Eclipse Public License 2.0 and the UI under AGPL 3.0. Programme software and configuration use Apache 2.0. The Technical Lead's licence compliance register must track modified or redistributed components, including AGPL network-use duties for any modified UI served over a network. These are licence obligations rather than regulatory ones, but a breach would undermine the open-publication commitment. Counsel should confirm compatibility of the licence mix.

## 6. Compliance matrix by pilot

Legend: **R** = required or likely required, **C** = to be confirmed, **N/A** = not applicable.

| Requirement | Pilot A | Pilot B | Pilot C | Needed by | Owner |
| --- | --- | --- | --- | --- | --- |
| Net-metering eligibility and terms in writing | R | C (if PV exports) | N/A | Before Gate 1 | Programme Director |
| Battery storage licence, permit or exemption | C | C | C | Gate 1 | Programme Director |
| Mini-grid or supply licence, operator and tariff position | N/A | C | N/A | Gate 1 | Programme Director |
| EV charging station licence or registration | N/A | N/A | C | Gate 1 | Programme Director |
| Kenya Power interconnection agreement in principle | R | C | R | Gate 1 | Technical Lead |
| Kenya Power design acceptance (protection, metering) | R | C | R | Gate 2 | Technical Lead |
| Kenya Power data sharing agreement | R | C | R | Before Gate 3 baselines | Technical Lead |
| Licensed contractors for PV and electrical work | R | R | R | Gate 2 | Site Leads |
| County, building and fire permits | C | C | C | Gate 2 | Site Leads |
| NEMA screening | C | C | C | Gate 2 | Site Leads |
| Insurer acceptance of battery installation | R | R | R | Gate 2 | Site Leads |
| Data protection roles, notices, ODPC registration | R | R | R | Before any data transfer | Cybersecurity and Data Protection Officer |
| NACOSTI licence and ethics clearance | C | R | R | Before data collection | University partner |
| Community informed agreement | N/A | R | N/A | Before procurement | Site Lead (B) |
| Landowner or owner consent | C | R | C | Gate 1 | Site Leads |
| Independent security audit | R | R | R | Gate 3 | Cybersecurity Officer |
| Contracting entity and equipment title decided | R | R | R | Gate 0 | Programme Sponsor |

## 7. Regulatory risks

| # | Risk | L | I | Mitigation | Trigger | Owner |
| --- | --- | --- | --- | --- | --- | --- |
| R1 | Net-metering credit or eligibility changes, or Pilot A host found ineligible | M | H | Early EPRA written position; model export credit below 50%; backup host | Any formal proposal or adverse EPRA reply | Programme Director |
| R2 | EPRA requires a BESS, mini-grid or charging licence that cannot be obtained in time | M | H | Ask in Month 1; seek exemption or sandbox; choose sites with clearer paths | No written position by Month 3 | Programme Director |
| R3 | Kenya Power interconnection delays or conditions | M | H | Early application; named grid engineer; backup sites | Approval not secured by Gate 1 | Technical Lead |
| R4 | Pilot B operator or tariff arrangement judged non-compliant | M | M | Define operator before consent; confirm with EPRA; no price rise clause | EPRA objection or customer complaint | Programme Director |
| R5 | Data protection breach or non-compliant data sharing | L | H | Roles agreed before sharing; ODPC registration; pseudonymisation; incident plan | Any personal data incident | Cybersecurity Officer |
| R6 | Research approval delays data collection | M | M | Apply in Months 1–3 | No approval by start of baseline | Research Lead |
| R7 | Unclear contracting entity blocks agreements and procurement | M | H | Decide at Gate 0 | Entity not named | Programme Sponsor |
| R8 | Environmental or county permits delay installation | M | M | Screen at site selection | Permit not secured by Gate 2 | Site Leads |
| R9 | Duties or taxes raise equipment cost beyond budget | M | M | Advice on relief; contingency | Budget variance above tolerance | Programme Manager |

## 8. Regulator engagement plan

| Timing | Action | Output |
| --- | --- | --- |
| Month 0 | Brief Ministry of Energy, EPRA and Kenya Power on this assessment and agree named counterparts | Counterparts list |
| Month 1 | Send the written request in Appendix A to EPRA and Kenya Power | Request log |
| Months 1–3 | Follow-up meetings; track responses in the regulatory issues log; agree whether a sandbox or exemption is possible | Written positions |
| Month 3 | Review responses; update compliance matrix; flag any site at risk | Updated B5 (v0.2) |
| Months 4–6 | Embed positions into host agreements, site specifications and the techno-economic model; confirm Gate 1 evidence | Gate 1 regulatory evidence |
| Months 6–8 | Submit design for Kenya Power acceptance; secure county, NEMA and insurer positions | Gate 2 evidence |
| Months 8–12 | Regulators and Kenya Power witness commissioning | Gate 3 evidence |
| Months 13–24 | Notify regulators of any formal proposals affecting the pilot; share interim findings | Regulatory feedback |
| Month 24 | Policy brief on net-metering, BESS and EV rules | Policy brief (E4) |

All contact is framed as seeking guidance. The programme does not treat engagement as pre-approval of any licence, tariff or interconnection (MoU Section 5.2).

## 9. Gate readiness

| Gate | Regulatory evidence required |
| --- | --- |
| Gate 0 | Contracting entity named; this assessment accepted as baseline; regulator briefings scheduled |
| Gate 1 | Written EPRA position on licensing and net-metering; Kenya Power agreement in principle; signed MoUs; host agreements with conditions precedent; research approvals applied for |
| Gate 2 | Kenya Power design acceptance; county, NEMA and insurer positions; licensed installers; data sharing and processing agreements signed; compatibility test report |
| Gate 3 | Commissioning certificates; passed security audit; ODPC and breach processes in place; baselines recorded; any licence or permit conditions met |
| Gate 4 | No unresolved regulatory non-compliance; regulatory change log reviewed |
| Gate 5 | Closure consistent with permits, decommissioning and data retention rules; policy brief delivered |

## 10. Open questions and decisions

1. Does EPRA treat behind-the-meter BESS of this size as licensable, and does a research pilot qualify for exemption or sandbox status?
2. Is the candidate Pilot A host eligible under the net-metering rules, and what are the capacity cap and application timeline?
3. What is the regulatory status of Pilot B (operator, tariff, supply licence), and does it depend on topology?
4. Does EV charging require a licence or registration, and who must hold it?
5. What are Kenya Power's requirements on protection, metering class, approved inverters and data sharing?
6. Which party must register with the ODPC, and does the Backend or any cloud hosting raise cross-border transfer questions?
7. Is NEMA screening or a full assessment needed for each site?
8. What is the contracting entity, and does it trigger public procurement or tax rules?
9. What import duty and VAT treatment applies to equipment?
10. Are the AGPL, EPL and Apache licence combinations acceptable to counsel for the planned release?

## Appendix A: Written request to EPRA and Kenya Power (question set)

**To EPRA.**

1. For a behind-the-meter battery of about 250 kWh with PV at a commercial or industrial customer, is a licence, permit or notification required? If so, by whom and with what lead time?
2. For the same customer, please confirm eligibility under the Energy (Net-Metering) Regulations 2024, applicable size limits, the export credit rate, and whether adding storage requires a new or amended application.
3. For a 50–100 kW PV and about 200 kWh battery system serving a village or estate, is a mini-grid or generation licence, permit or registration required, and what tariff and consumer-protection rules apply to customers served?
4. For a public or fleet charging site with about 10–20 fast chargers, is a licence or registration required, and are there pricing, display or safety rules?
5. Can a time-limited research pilot operate under an exemption or regulatory sandbox, and on what conditions?
6. What standards for batteries, inverters and chargers does EPRA expect?
7. Will EPRA nominate an observer to the Research and Evaluation Panel, and who is the named counterpart?

**To Kenya Power.**

1. What are the interconnection requirements, fees and lead times for Pilots A and C (and B if grid-connected)?
2. What protection, anti-islanding, metering and power quality requirements apply, and is there an approved equipment list?
3. Will Kenya Power share feeder and transformer loading and outage data for pilot feeders, in what format and at what update rate, and under what data sharing agreement?
4. Confirm that OpenEMS control will be limited to assets behind the customer connection and that no utility protection settings will be changed.
5. Who is the named grid engineer for the Technical Working Group?

## Appendix B: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter | Gates, dependencies, regulator roles, risk triggers |
| Feasibility Study (D1) | Regulatory table (Section 6), Gate 1 conditions, open questions |
| Technical Specification (B4) | Control authority, export limits, topology, open items |
| Site Survey Reports (B3) | Site-level permit and consent checks |
| MoU and Site Agreement templates | Conditions precedent, data roles, regulator clauses |
| Stakeholder Engagement Plan | Regulator and community engagement, grievance routes |

On receipt of the EPRA and Kenya Power replies, this document is updated to version 0.2, each "confirm" item is closed or reclassified, and counsel's review is recorded.

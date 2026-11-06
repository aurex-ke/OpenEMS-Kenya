# Feasibility Study

## 1. Executive Summary

**Question.** Can OpenEMS be deployed in Kenya to stabilise a high-renewable grid, reduce losses, lower energy costs and safely integrate EV charging, and is that technically, economically and institutionally viable?

**Preliminary verdict: conditional go.** On the evidence in the programme documents, a three-site, 24-month pilot is feasible and worth running. The case is strongest for technical and institutional feasibility. It is weakest, and least evidenced, for economics, because the 15–30% international savings range has never been validated in Kenya.

| Dimension | Preliminary rating | Main reason | What would change it |
| --- | --- | --- | --- |
| Technical | Moderate to high | OpenEMS supports the needed protocols (Modbus, MQTT, HTTP, OCPP) and controllers; Edge keeps local control offline | Failed compatibility tests on locally available inverters, batteries or chargers |
| Economic | Uncertain | No local savings data; 50% net-metering export credit; battery cost exposure | Baseline load and bill data showing weak tariff spreads or peak charges |
| Regulatory and institutional | Moderate, gated | Licensing for BESS, mini-grids and EV charging, and net-metering terms, are unconfirmed | Written EPRA and Kenya Power positions by Month 3 |
| Social and safety | Moderate to high | Pilot B has the most exposure; battery fire safety needs planning | Community consent at Pilot B; insurer acceptance |
| Delivery | Moderate | Limited local OpenEMS expertise; fixed 24-month window | Local team in place by Month 6 |

**Five conditions to proceed to Gate 1** (detailed in Section 12):

1. Written EPRA position on licensing and net-metering terms.
2. Kenya Power agreement in principle on interconnection and data access.
3. Signed host agreements and Pilot B community consent.
4. Passed compatibility testing for a shortlisted hardware set.
5. A reconciled, validated budget with KPI targets and baselines.

A "stop" at Gate 1 is a legitimate outcome. A well-evidenced finding that OpenEMS is not viable under Kenyan conditions would still be a successful research result.

## 2. Purpose, Scope and Method

### 2.1 Purpose

This study tests whether the programme should proceed to design and procurement. It feeds Gate 1 (Month 4–6) and underpins the techno-economic model (D2), risk register (D3) and site specifications (D4).

### 2.2 Scope

In scope: grid-connected and mini-grid applications at distribution and customer level, using OpenEMS Edge, at Pilots A (industrial park, hub or campus), B (rural microgrid) and C (EV charging site). Out of scope: transmission planning, utility-scale generation, tariff or regulatory change, commercial roll-out, and core OpenEMS development beyond drivers and configuration.

### 2.3 Evidence base and limitations

This version is a **desk-based baseline** drawn from the Executive Summary, Problem Statement, Programme Charter, Stakeholder Engagement Plan and the MoU and Site Agreement templates. Please note:

- The underlying Research Report (referenced in the README) was not available to this study, so its detailed evidence tables are not reproduced.
- No site-level load, tariff, meter or transformer data has been collected yet. Where this study quantifies anything beyond the source documents, it is arithmetic on stated figures or an explicit placeholder.
- The Risk Register workbook was not readable in the material provided. Risks in Section 9 are drawn from the Charter and Executive Summary and should be merged with it.
- Savings of 15–30% are treated as a hypothesis, not a forecast.

### 2.4 Method

Five lenses are applied: technical, economic, regulatory and institutional, social and environmental and safety, and delivery. Each is rated (high, moderate, low confidence of feasibility) with the evidence, gaps and a validation action. Section 13 sets out the fieldwork needed to turn this baseline into the final D1.

## 3. Context and Need

| Indicator | Value (FY2024/25 unless stated) |
| --- | --- |
| Renewable share of generation | Over 80% (geothermal 39.5%, hydro 24.2%, wind 13.2%, utility solar 3.3%) |
| Peak load | 2,316 MW (Feb 2025), up 6.4% year on year |
| Variable renewables, instantaneous peak share | About 34% |
| System losses | 23.4% against a 17.5% regulatory benchmark |
| EV tariff consumption | 5.04 GWh, up 300% |
| Time-of-Use consumption | 180.3 GWh, saving about KSh 1.44 bn |
| Net-metering export credit (2024 Regulations) | 50% of each kWh |

The need follows from these figures. Variability and clustered EV charging stress local networks, losses mean roughly a quarter of generation earns no revenue, and customers lack tools to act on ToU price signals or optimise self-consumption under a 50% export credit. Proprietary EMS products carry licence fees, lock-in and limited local support. OpenEMS removes licence cost but has no documented performance record in Africa.

## 4. Technical Feasibility

### 4.1 Platform fit

OpenEMS has an on-site Edge controller, a web UI and an optional cloud Backend. It integrates inverters, meters, batteries and EV chargers over Modbus, MQTT, HTTP and OCPP, and includes controllers for peak shaving, state-of-charge management, ToU optimisation, self-consumption and surplus feed-in, and EV cluster load balancing. These map directly onto the five problems in the Problem Statement. The Edge continues local control during internet outages, which is essential for rural sites.

**Assessment: high fit on capability; moderate confidence on integration**, because fit with the specific hardware sold in Kenya is untested.

### 4.2 Fit by pilot

|  | Pilot A: C&I / campus | Pilot B: rural microgrid | Pilot C: EV depot |
| --- | --- | --- | --- |
| Configuration | PV plus about 250 kWh battery | 50–100 kW PV, about 200 kWh battery, possible diesel | 10–20 fast chargers, optional small battery |
| Controllers used | Peak shaving, ToU shifting, net-metering optimisation | Self-consumption, SoC management, diesel offset, local control | EV cluster load balancing, transformer protection |
| Main technical risk | Existing inverter integration and warranties | Connectivity, theft, harsh environment, loss measurement | OCPP compatibility with local chargers, transformer data access |
| Key measurement need | Interval load and bill data (12 months or more) | Feeder and customer-level energy balance | Transformer loading, charger session data |
| Technical feasibility | Moderate to high | Moderate | Moderate |

Pilot B is the hardest to evaluate. Measuring technical and commercial loss reduction needs a defensible before-and-after energy balance on served customers, which depends on metering coverage that may not exist today.

### 4.3 Interoperability

The Charter lists interoperability with local hardware as a top risk. Recommended approach:

- Build a shortlist of locally available inverters, batteries, meters and chargers from vendors with local service.
- Test each against OpenEMS drivers in a laboratory or sandbox **before** procurement award (Gate 2 evidence).
- Record which devices have existing OpenEMS drivers, which need custom drivers, and the effort for each. The budget line for custom drivers sits inside the 20% software and integration share.
- Treat any failed test as an escalation trigger under the Charter.

### 4.4 Connectivity and resilience

Edge devices must keep local control offline, and this is tested at commissioning. For rural sites, cache data locally and sync when connected, and agree a data-gap threshold. Remote connection is not permitted until the independent security audit is passed (Gate 3).

### 4.5 Cybersecurity

Open-source code is public, so security rests on configuration, patching and access control. Requirements: independent audit before any remote connection, authentication and encryption, role-based access, a logged change process for Edge configuration, and an incident response plan with notification routes to Kenya Power and, where required, EPRA. Note that AGPL 3.0 applies to the UI, so any modification offered over a network triggers source-sharing duties tracked in the licence compliance register.

### 4.6 Grid interface

Kenya Power retains operational control of its network. OpenEMS control stays behind the customer connection point and the programme does not alter protection settings on utility assets (per the draft MoU Schedule 1B). Interconnection applications, protection, metering and power quality requirements must be confirmed early. This also defines what Pilot C can claim: it can protect the transformer by managing site load, not by controlling the utility asset.

### 4.7 Technical conclusion

Technically feasible, subject to compatibility testing, a security audit and confirmed interconnection requirements. Open technical questions are listed in Appendix B.

## 5. Economic Feasibility

### 5.1 Programme budget

Indicative total: **KSh 50–100 million (about USD 400–800k)**, implying about KSh 125 per USD. Site estimates are USD 50–150k each. OpenEMS has no licence cost.

**Reconciliation issue.** Three sites at USD 50–150k total USD 150–450k, which is below the USD 400–800k programme envelope. The gap would have to cover programme-level items: PMO, independent security audit, evaluation and university research costs, training, optional Backend, community liaison and central contingency. This should be itemised before Gate 1. If the gap is mostly programme-level cost, say so explicitly, because it tells funders what a replication would cost.

### 5.2 Reference cost structure applied to the envelope

The Charter's reference split (for a 100 kW PV plus 300 kWh site) is a guide only. Applied to the programme envelope as an illustration:

| Category | Share | USD 400k | USD 800k |
| --- | --- | --- | --- |
| Hardware (PV, BESS, inverters, meters) | 40% | 160k | 320k |
| Software and integration | 20% | 80k | 160k |
| First-year O&M | 15% | 60k | 120k |
| Installation and civil works | 10% | 40k | 80k |
| Contingency (held centrally) | 10% | 40k | 80k |
| Training and capacity building | 5% | 20k | 40k |

Two observations. First, "free" software still carries a 20% integration share, so the real cost of open-source is integration and skills, not licences. Second, the Executive Summary quotes a 10–20% contingency while the reference split carries 10%, so the plan should state which applies.

### 5.3 Benefit mechanisms to be measured

| Mechanism | Pilot | How OpenEMS acts | Value driver | Status |
| --- | --- | --- | --- | --- |
| Peak shaving | A, C | Discharge battery or throttle load at peak | Demand charges, if the tariff has them \[confirm\] | Unvalidated |
| ToU shifting | A | Charge off-peak, discharge on-peak | ToU spread | Unvalidated |
| Self-consumption under 50% export credit | A, B | Store surplus rather than export at half value | Difference between avoided retail kWh and 50% credit | Unvalidated |
| Diesel displacement | B | Prioritise PV and battery over generator | Fuel and O&M avoided | Unvalidated |
| Loss reduction | B | Generate and consume locally | Energy no longer lost on long lines | Unvalidated |
| Transformer protection | C | Cluster load balancing | Avoided outage and upgrade cost | Unvalidated |

### 5.4 Evaluation framework

Each site is compared against a pre-agreed baseline (storage idle or unmanaged), with and without control, over at least 12 months of validated data.

- **Metrics:** annual net benefit (KSh), simple payback, net present value, levelised cost of stored energy, and cost per kW of peak reduced.
- **Sensitivities (from the Charter):** battery cost ±20%, discount rate 5–12%, plus export credit below 50%, tariff spread, and inflation at about 5% a year.
- **Two views of cost:** the pilot cost, which includes research overhead, and a **replication cost**, which excludes it. Commercial viability should be judged on the replication cost.

### 5.5 Illustrative break-even arithmetic

This is not a forecast. It shows what a site must achieve. For a site with USD 100k net capex and a target simple payback of 8 years, the annual net benefit must be about USD 12.5k. If savings equal 15% of the energy bill, the bill base must be about USD 83k a year. At 30% savings it must be about USD 42k. Sites with smaller bills will not pay back from bill savings alone, so Pilot A should favour a host with a large, peak-heavy load, and Pilot B and C benefits may rest on diesel, reliability and asset protection rather than bills.

### 5.6 Economic conclusion

Economic feasibility cannot be confirmed from existing documents. It depends on tariff structure, load shape, battery cost and the export credit. The pilot is the means of testing it. Gate 1 should require the techno-economic model to show, by site, the **break-even conditions** under which OpenEMS is viable, not only a single point estimate.

## 6. Regulatory and Institutional Feasibility

| Issue | Position today | Needed by | Owner |
| --- | --- | --- | --- |
| Net-metering terms for Pilot A | Unconfirmed; 2024 Regulations credit exports at 50% | Before Gate 1 | EPRA, Programme Director |
| Licensing or permits for BESS, EV charging and mini-grid operation | Unconfirmed | Month 3 (requested) | EPRA |
| Interconnection approval (A, C, and B if relevant) | Not applied for | Gate 1 in principle | Kenya Power, Technical Lead |
| Data access to feeder and transformer data | Not agreed | Before Gate 3 baselines | Kenya Power |
| Data protection compliance (Data Protection Act, 2019) | To design | Before any data transfer | Cybersecurity and Data Protection Officer |
| Research approvals (NACOSTI, ethics) | To confirm | Before data collection | University partner |
| County permits | Not assessed | Gate 2 | Site Leads |

**Institutional structure.** The proposed governance (Steering Committee, PMO, Technical Working Group, Research and Evaluation Panel, Regulatory and Stakeholder Forum) is proportionate and keeps regulators involved from the start. The main institutional gap is that **no legal entity is named** to sign contracts, hold insurance and hold equipment title. This must be solved at Gate 0.

**Regulatory change risk.** A formal proposal to change net-metering or licensing rules is an escalation trigger. The economic model should test lower export credits throughout.

**Independence.** The programme informs but does not decide tariffs or regulation. Any EPRA exemption or sandbox conditions should be annexed to the MoU and bind the programme.

## 7. Social, Environmental and Safety Feasibility

### 7.1 Community and host acceptance

Pilot B carries the most direct exposure. Requirements from the Stakeholder Engagement Plan: consultation before site selection, separate sessions for women, youth and small businesses, documented informed agreement before procurement, honest research-pilot messaging, no promises of jobs, free power or permanent assets, and a grievance channel with acknowledgement in \[3\] working days. Host agreements should state that the pilot causes no disconnection or price rise for customers served.

Pilot C raises a different issue: drivers may be throttled. A fair-sharing or priority policy and a maximum acceptable wait time should be agreed, displayed and measured.

### 7.2 Safety

Battery fire and thermal safety, electrical work by licensed contractors, emergency response plans agreed with local responders, and insurer notification are conditions of Gate 2. Pilot B also needs theft, lightning, flood and wildlife protection.

### 7.3 Environmental

Battery handling, end-of-life and waste follow the safeguards in the host agreement schedule. Decommissioning responsibilities and costs must be fixed before procurement. Diesel offset at Pilot B needs an agreed measurement method.

### 7.4 Data and privacy

Household consumption at Pilot B and session data at Pilot C are personal data. Aggregate or pseudonymise, avoid payment data, and display notices to charger users.

## 8. Delivery and Organisational Feasibility

### 8.1 Timeline

| Phase | Months | Key outputs | Gate |
| --- | --- | --- | --- |
| Mobilise | 0 | Signed charter, funding commitment | Gate 0 |
| Feasibility and consultation | 1–4 | D1, D2 (months 2–6), D3 | Gate 1 at Month 4–6 |
| Design and procurement | 4–8 | D4 compatibility report, security design review | Gate 2 at Month 8 |
| Build and commissioning | 7–12 | D5 commissioned sites | Gate 3 at Month 12 |
| Operation and monitoring | 13–24 | D7 monthly data, mid-review at Month 18 | Gate 4, Gate 5 |

**Schedule pressure.** Gate 1 requires host agreements, regulatory clarity on net-metering and interconnection in principle. If EPRA or Kenya Power responses are late, installation in Months 7–12 compresses. Because the study needs 12 months of validated operating data, **late commissioning directly reduces evidence**. A stop-or-extend rule should be agreed in advance, and backup sites shortlisted.

### 8.2 Capacity

The OpenEMS core developer community is small and mostly European. A local implementation team, university partnership and operator training are therefore delivery deliverables, not extras. Programme success requires a local team able to operate OpenEMS without continuous foreign support. Training is budgeted at about 5% in the reference split. This may be thin given the importance of local capacity, and should be tested in the budget reconciliation.

### 8.3 Dependencies on third parties

Regulators, Kenya Power, hosts, vendors and the university partner each hold a critical-path dependency. The MoU and site agreement templates already assign these, but all are drafts. Signature of the three MoUs and three host agreements is a Gate 1 and Gate 2 prerequisite.

## 9. Risk Assessment

Ratings below are initial judgements (likelihood and impact: H, M, L) for validation in the live risk register.

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| 1 | Savings fall short of the 15–30% international range | M | H | Report honestly; no re-baselining without Panel approval; pre-define break-even | Research Lead |
| 2 | Regulatory change (net-metering credit, licensing) | M | H | Early EPRA engagement; sensitivity on export credit | Programme Director |
| 3 | Delay in host site or interconnection approval | M | H | Early Kenya Power engagement; backup sites | Programme Director |
| 4 | Hardware incompatible with OpenEMS | M | M | Pre-award compatibility tests; custom driver budget | Technical Lead |
| 5 | Cybersecurity incident | L | H | Independent audit; authentication; incident plan | Cybersecurity Officer |
| 6 | Limited local expertise | M | M | Local team, training, university partnership | Technical Lead |
| 7 | Cost overruns, tariff or battery price change | M | M | Central contingency; quarterly sensitivity review | Programme Manager |
| 8 | Poor rural connectivity | H | L | Edge local control; cache and sync | Site Lead (Pilot B) |
| 9 | Battery fire or safety incident | L | H | Safety plans, insurer engagement, emergency plans | Site Leads |
| 10 | Community opposition or unmet expectations | M | M | Broad consultation; honest messaging; grievance channel | Site Leads |
| 11 | No legal entity or equipment title agreed | M | H | Resolve at Gate 0; agree title in host agreements | Programme Sponsor |
| 12 | Budget envelope does not reconcile with site costs | M | M | Itemise programme-level costs before Gate 1 | Programme Manager |

The highest-leverage risks (1, 2, 3 and 11) are all addressed by actions before Gate 1.

## 10. Site Selection Criteria

Sites are selected by the Steering Committee at Gate 1. The following weighted criteria are proposed, with weights \[to be agreed\]. Each candidate is scored 1–5.

| Criterion | Pilot A | Pilot B | Pilot C | Proposed weight |
| --- | --- | --- | --- | --- |
| Availability of 12 or more months of load, bill or meter data | Essential | Desirable | Essential (transformer data) | \[15%\] |
| Representativeness of the scenario | Peak-heavy load, ToU or net-metering eligible | Long lines, diesel, measurable loss | 10–20 chargers on a shared transformer | \[15%\] |
| Host willingness and agreement readiness | Yes | Yes, plus community consent | Yes, plus vendor cooperation | \[15%\] |
| Interconnection and licensing path clarity | Yes | Yes | Yes | \[15%\] |
| Hardware compatibility and local service | Yes | Yes | OCPP compatibility | \[10%\] |
| Safety and security (space, fire, theft) | Yes | Yes | Yes | \[10%\] |
| Community acceptance and inclusion | Staff and neighbours | Broad consultation | Drivers and fleets | \[10%\] |
| Replication potential | Yes | Yes | Yes | \[10%\] |

A shortlist of at least two candidates per pilot is advised to protect the schedule.

## 11. Feasibility Scorecard

| Lens | Rating | Confidence | Key evidence gap |
| --- | --- | --- | --- |
| Technical | Moderate to high | Medium | Local hardware compatibility results |
| Economic | Uncertain | Low | Site load, tariff and cost data |
| Regulatory and institutional | Moderate, gated | Medium | Written EPRA and Kenya Power positions |
| Social, environmental, safety | Moderate to high | Medium | Community consultation and safety plans |
| Delivery | Moderate | Medium | Local team in place; reconciled budget |
| **Overall** | **Conditional go** | **Medium to low** | **Economics and regulatory clarity** |

## 12. Conclusions, Gate 1 Conditions and Recommendations

### 12.1 Conclusions

The pilot is justified. The risks are manageable, the evidence gap is real, and the governance design is proportionate. The programme's value lies as much in answering the economic and institutional questions as in proving the technology.

### 12.2 Gate 1 conditions

| # | Condition | Evidence | Owner |
| --- | --- | --- | --- |
| 1 | Regulatory position confirmed | Written EPRA letter on licensing and net-metering terms for Pilot A | Programme Director |
| 2 | Interconnection path agreed | Kenya Power agreement in principle and data-sharing protocol | Technical Lead |
| 3 | Sites and consent secured | Signed host agreements; Pilot B community consent record | Site Leads |
| 4 | Hardware shortlist tested | Compatibility report with driver effort estimated | Technical Lead |
| 5 | Budget validated | Reconciled budget, contingency stated, replication cost estimated | Programme Manager |
| 6 | KPI targets and baselines set | Research Panel approved M&V protocol | Research Lead |
| 7 | Contracting entity named | Legal entity and equipment title decision | Programme Sponsor |

### 12.3 Recommendations

1. Treat regulatory clarity as the critical path and request EPRA and Kenya Power positions in Month 1, not Month 3.
2. Name the legal entity and decide equipment title at Gate 0.
3. Reconcile the budget and set a single contingency policy.
4. Define break-even conditions, not only point savings estimates, in the techno-economic model.
5. Start compatibility testing as soon as the hardware shortlist exists.
6. Shortlist backup sites and pre-agree a rule for late commissioning.
7. Set KPI numeric targets only after baseline data is in, and freeze them at Gate 1.

## 13. Fieldwork Plan to Complete the Final Study

| Activity | Months | Output |
| --- | --- | --- |
| Stakeholder interviews and workshops (regulators, Kenya Power, vendors, universities) | 1–3 | Consultation report |
| Site visits and candidate community consultations | 1–4 | Site shortlist and evidence |
| Collection of load, tariff and bill data from candidate hosts | 1–3 | Baseline dataset |
| Kenya Power feeder and transformer data request | 1–3 | Loading and loss baselines |
| Hardware market scan and compatibility testing | 2–5 | Compatibility report |
| Techno-economic modelling and sensitivities | 2–6 | D2 model |
| Budget reconciliation and funding confirmation | 2–4 | Validated budget |
| Final feasibility report | 4 | D1 for Gate 1 |

## Appendix A: Data Request List

- **Hosts (A):** 12 or more months of interval load, electricity bills, tariff category, existing PV and inverter details, site electrical single-line diagram.
- **Pilot B:** customer count and consumption, feeder length and metering coverage, diesel use and cost, outage history, land and consent status.
- **Pilot C:** charger make, model and OCPP version, session logs, transformer rating and loading, fleet schedules.
- **Kenya Power:** interconnection requirements and timelines, feeder and transformer data, protection and metering standards.
- **EPRA:** current net-metering terms for the site category, BESS, EV charging and mini-grid licensing requirements.
- **Vendors:** driver availability, warranties, local service, pricing.

## Appendix B: Open Questions

1. What are the real ToU spreads and demand charges for the candidate Pilot A host categories?
2. Which local inverters, batteries and chargers already have OpenEMS drivers?
3. How will technical and commercial losses be separated at Pilot B?
4. Does EPRA treat each pilot site as needing a licence or exemption?
5. Who holds equipment title, and who pays decommissioning?
6. Does the Pilot A 250 kWh battery size match the Charter's 300 kWh reference site, and is that size right for the host's load?
7. How will host benefit-sharing be handled to avoid distorting the baseline?
8. What is the funded split between pilot sites and programme-level costs?

# Final Evaluation Report

## 1. Purpose and bottom line

The Charter makes Gate 5 the point where the Steering Committee accepts results, approves publication and agrees handover (Charter Section 16). The Problem Statement sets one central question and five supporting questions. The Monitoring and Evaluation Plan (D1) assigns the answers to this report (Section 13). E2 is the **final evaluation**: what twelve months of validated controlled operation at three pilot sites showed, how reliable that evidence is, how it compares with the 15 to 30% international range, whether OpenEMS is technically, economically and institutionally viable in Kenya, and what should happen next.

**Status note.** No site is selected, built or measured, and no data exists. This version is therefore a **pre-populated report template**: the structure, evidence rules, verdict rules, decision rules and tables are fixed now, and every result field is completed in Months 22 to 24 from validated monthly reports (D6) and the interim evaluation (E1). It must not be used to state or imply any result.

**Bottom line.** E2 is the programme's answer, so it is held to the strictest rules in the document set. Ten rules govern it:

1. **Validated data only.** E2 uses only months validated by the Research and Evaluation Panel. Provisional figures never enter it (D6 Section 1).
2. **Twelve months or say so.** The target is at least 12 months of validated controlled data per site (Charter Section 7). A site with less is reported with the shortfall stated and its results labelled partial.
3. **Same definitions as D1 and E1.** KPIs K1 to K6 use the frozen KPI dictionary and the pre-registered analysis plan. E2 introduces no new KPI, definition or method. Added analyses are labelled exploratory (D1 Section 12.1).
4. **Verdict rules before data.** The way results turn into an answer to the central question is fixed at Gate 2 (Section 9) and not altered after data is seen.
5. **Uncertainty with every number.** Each KPI carries its interval, completeness and mode record. Where uncertainty exceeds the effect, E2 says the effect is not distinguishable from zero.
6. **Mechanism before magnitude.** A saving is credited to OpenEMS only where the mechanism is visible in the data.
7. **Sites are reported separately.** Three heterogeneous sites are not averaged into a national estimate. Wider replication claims are hypotheses supported by break-even conditions, not extrapolated results (D1 Section 3.2).
8. **Negative and null results have equal prominence.** A result below the 15 to 30% range, a failed compatibility test or a "not viable" finding is a research result, not a programme failure (Charter Section 16).
9. **Independence.** The Research Lead writes the findings. Hosts, vendors, funders and regulators may comment on drafts but cannot require changes (MoU Section 10.2).
10. **Honest limits.** Pilot B loss separation, Pilot C delay effects and the external validity of three sites are limited. E2 states what the evidence cannot show.

**What cannot be settled from desk research.** Targets, thresholds, baseline length, tariff structures, the seasonal method and the verdict thresholds are not yet fixed. This document fixes the structure and rules and leaves values as placeholders for Gates 1 and 2.

## 2. Document control and relationships

**Owner:** Research Lead (README E2). **Authors:** data analyst, university partner, techno-economic analyst. **Contributors:** Technical Lead, software engineer, Cybersecurity and Data Protection Officer, Capacity-building lead, Legal and regulatory lead, Site Leads, Programme Manager and PMO, finance lead, Kenya Power grid engineer (TWG). **Review:** independent reviewer (Charter Section 23), Panel validation, security and privacy review. **Approval:** Programme Director presents to the SteerCo at Gate 5. **Method frozen:** Gate 2, with the M&V protocol. Changes follow Charter Section 20.

| Document | Relationship |
| --- | --- |
| Problem Statement | Central question and supporting questions Q1 to Q5 |
| Programme Charter (Sections 3, 7, 16, 18, 20, 21, 23, 24) | Mission, KPIs, Gate 5 evidence and decision, escalation triggers, change control, independence, closure |
| Feasibility Study (D1 baseline) | Conditional-go verdict, scorecard lenses, Gate 1 conditions, break-even logic, open questions |
| Monitoring and Evaluation Plan (D1) | KPI dictionary, modes, baseline method, quality checks, decision rules, scorecard |
| Monthly Performance Reports (D6) | Source series, Months 13 to 24 |
| Interim Evaluation Report (E1) | Month 18 findings, course-correction log, trigger test |
| Incident and Change Log (D5) | Incidents, changes, confounders, drift, failed changes |
| Operations and Maintenance Manual (D3), Training Records (D4) | Uptime, repair times, operator competence and retention |
| OpenEMS Configuration Baseline (C4), Interoperability Register (B6) | Mode records, hashes, tested device set, driver effort |
| Regulatory Compliance Assessment (B5), Cybersecurity Plan (B7) | Regulatory outcomes, audit and security record |
| Techno-economic model (B2), Budget tracker (C2) | Measured inputs, pilot cost and replication cost |
| Risk Register (A6) | Final risk status |
| Data Management and Privacy Plan (D2) | Disclosure rules, minimum group size, release process |
| Replication guide (E3), Policy brief (E4), Release package (E5), Paper (E6) | Built from E2 findings |

## 3. Questions E2 answers and the evidence behind each

| # | Question (Problem Statement) | Pilots | Primary evidence | Answer format |
| --- | --- | --- | --- | --- |
| Q1 | How effectively can OpenEMS battery dispatch smooth VRE variability and reduce peak demand? | A, B, C | K1, ramp rate of net import, mechanism evidence | Effect size with interval per site |
| Q2 | How much can local solar-plus-storage microgrids reduce technical and commercial losses? | B | K6, energy balance, check meters, voltage logs | Total loss change, split only if defensible |
| Q3 | What bill savings and payback are achievable under ToU tariffs and the 50% net-metering credit? | A (B, C where tariffs apply) | K3, tariff documents, break-even position | Savings against the 15 to 30% range, payback on replication cost |
| Q4 | Can EV cluster control prevent transformer overload without unacceptable charging delay? | C | K5a, K5b, wait-time distribution | Loading and delay against agreed limits |
| Q5 | What regulatory, cybersecurity, maintenance and capacity risks must be managed? | All | D5, B5, B7, D3, D4, regulator correspondence | Risk findings with mitigations that worked |

The **central question** is answered in Section 9 by combining Q1 to Q5 with the verdict rules.

## 4. Evidence base and rules of use

### 4.1 Data window

| Item | Rule |
| --- | --- |
| Window | Months 13 to 24 per site, from the start of validated controlled data (M2). Months 13 to 18 are the E1 window and are not re-analysed with a different method |
| Baseline | M1 data and the Panel-approved counterfactual model. Baseline length and test pattern as fixed at Gate 2 |
| Included | Validated monthly datasets (MR-1) with a valid mode flag and configuration hash |
| Excluded | M0, M3 and M4 periods from savings, with their effect on uptime reported separately. Confounder periods excluded or modelled as recorded |
| Cut-off | Month 24 minus the time needed for validation. Late data is reported with a restatement note. An earlier cut-off is stated, and the unvalidated tail is labelled as such |
| Minimum for a result | A KPI is a result only if completeness and reconciliation meet the Panel threshold [x]%. Otherwise "not reportable" with the reason |
| Restatements | Changes since E1 are listed with reasons (D6 Appendix F) |

### 4.2 Evidence hierarchy

1. Independent research meters and logger, reconciled with Edge data. The research meter prevails unless faulty.
2. Billing and tariff documents from hosts, checked against meter data.
3. Edge control data, used for mechanism and uptime.
4. Site logs, D5, D3 and D4 records, used for context and institutional findings.
5. Stakeholder, driver and community feedback, reported as qualitative evidence, not as a measure of effect.

### 4.3 Data quality summary (complete from D6)

| Site | Months validated | Completeness (%) | Longest gap (h) | Edge vs research meter difference (%) | Restatements since E1 | Seals and accuracy checks | Reportable KPIs |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| B | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| C | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

### 4.4 Deviations from the pre-registered plan

Any deviation from the M&V protocol or analysis plan is listed with its reason, the approving body and its effect on results. If there are none, the report says so.

| ID | Deviation | Reason | Approved by (SteerCo on Panel advice) | Effect on results |
| --- | --- | --- | --- | --- |
| DV-01 | [ ] | [ ] | [ ] | [ ] |

## 5. Programme delivery record

### 5.1 Delivery against the Charter

*Numbering note: Charter deliverables D1 to D8 differ from the README document IDs D1 to D6 (operation documents). Always write the scheme.*

| Charter deliverable | Planned | Actual | Variance and cause |
| --- | --- | --- | --- |
| D1 Feasibility study and consultation | Months 1 to 4 | [ ] | [ ] |
| D2 Techno-economic model | Months 2 to 6 | [ ] | [ ] |
| D3 Risk register and mitigation plan | Month 3, continuous | [ ] | [ ] |
| D4 Site specifications and compatibility report | Months 4 to 8 | [ ] | [ ] |
| D5 Commissioned installations | Months 7 to 12 | [ ] | [ ] |
| D6 Trained local team and materials | Months 6 to 14 | [ ] | [ ] |
| D7 Monthly data sets and reports | Months 13 to 24 | [ ] | [ ] |
| D8 Final evaluation and publication | Months 22 to 24 | [ ] | [ ] |

### 5.2 Gates

| Gate | Planned month | Actual | Decision and conditions | Lessons recorded |
| --- | --- | --- | --- | --- |
| Gate 0 to Gate 4 | [ ] | [ ] | [ ] | [ ] |
| Gate 5 | 24 | [ ] | This report | [ ] |

### 5.3 Sites actually evaluated

| Pilot | Planned | Actual (candidate, any substitution) | Months of validated controlled data | Departures from plan |
| --- | --- | --- | --- | --- |
| A | Industrial park, hub or campus, about 250 kWh battery | [ ] | [ ] | [ ] |
| B | Rural microgrid, 50 to 100 kW PV, about 200 kWh battery | [ ] | [ ] | [ ] |
| C | EV site, about 10 to 20 fast chargers | [ ] | [ ] | [ ] |

### 5.4 Operating record, Months 13 to 24

| Item | Source | A | B | C |
| --- | --- | --- | --- | --- |
| Days in M1, M2, M3, M4 | C4, D6 | [ ] | [ ] | [ ] |
| Control-off weeks (if used) | M&V protocol | [ ] | [ ] | [ ] |
| Uptime and availability (K4), cause breakdown | D6, D3 | [ ] | [ ] | [ ] |
| Mean time to acknowledge and to repair | D3 | [ ] | [ ] | [ ] |
| P1 to P4 incidents | D5 | [ ] | [ ] | [ ] |
| Safe-state events and setpoint clamps | Edge, D5 | [ ] | [ ] | [ ] |
| Changes by class C0 to C4, failed or rolled back | D5 | [ ] | [ ] | [ ] |
| Unexplained drift events | C4, D5 | [ ] | [ ] | [ ] |
| Supply continuity: no disconnection or price rise from the pilot | Operator, Kenya Power | n/a | [ ] | n/a |

Failures, rollbacks and workarounds appear with equal prominence to successes.

## 6. KPI results

Results use the standard KPI block (D6 Section 8.1). Targets are those frozen at Gate 1. Where none was set, status is NO TARGET and is not coloured.

### 6.1 Summary table (complete at Month 24)

| KPI | Pilot | Final result | Counterfactual or baseline | Difference with interval | Change since E1 | Result category (D1 12.1) | Target | Completeness | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| K1 Peak grid import reduction (kW, %) | A | [ ] | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| | B | [ ] | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| | C | [ ] | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| K2 Self-consumption ratio | A | [ ] | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| | B | [ ] | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| K3 Bill savings (KSh, %) | A | [ ] | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| | B | [ ] | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| K4 Uptime and availability | A, B, C | [ ] | n/a | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| K5 Transformer loading, full-capacity share | C | [ ] | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| K6 Loss fraction and reduction | B | [ ] | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |

Status words: ON TRACK, WATCH, OFF TRACK, ESCALATED, NO TARGET (D6 Section 10).

### 6.2 Pilot A: industrial park, hub or campus

| Item | Content to report |
| --- | --- |
| K1 | Adjusted baseline peak minus controlled peak over tariff-relevant windows and the monthly maximum interval |
| K2 | (PV generation minus export) divided by PV generation, battery losses separate |
| K3 | Counterfactual bill minus actual bill under the actual tariff and net-metering rules as confirmed by EPRA, in KSh and as % of the counterfactual bill, against the 15 to 30% range |
| Mechanism split | Peak or demand charge, ToU shifting and export credit shown separately, showing which mechanism pays |
| Tariff reality | Actual ToU spread and demand charges. If neither is meaningful the site is reported as a weak economic test (B4 Section 5.2) |
| Seasonality | Twelve-month result by season, with the approved adjustment |
| Critical loads and host effects | Overrides, excluded periods, host behaviour or tariff changes, benefit-sharing effects |

### 6.3 Pilot B: rural microgrid

| Item | Content to report |
| --- | --- |
| K6 | Loss fraction before and after control, normalised for load, season and customer numbers |
| Separation | Whether technical and commercial losses were separated defensibly. If not, total loss change only, stated plainly |
| Metering coverage | Share metered, check meter coverage, energy balance closure |
| K2 and diesel | Self-consumption, diesel energy and fuel displaced from generator kWh, run hours and fuel volume |
| Reliability | Outage frequency and duration against baseline, low-voltage events |
| Data gaps | Gap hours against the agreed threshold, and whether the escalation trigger fired |
| Community | Supply continuity, complaints, acceptance |
| Caveat | One feeder with a small customer count gives noisy estimates. Results are site evidence, not a general loss figure |

### 6.4 Pilot C: EV charging site

| Item | Content to report |
| --- | --- |
| K5a | Peak kW, load-duration curve, time above the agreed threshold, managed versus reconstructed unconstrained demand |
| K5b | Share of charging time at requested power |
| Delay | Wait per session: median, 90th percentile and maximum against the agreed maximum |
| Fairness | Energy share by customer class under the agreed policy |
| Acceptance | Complaints per 100 sessions, fleet and driver feedback, vehicles that reject limiting |
| Limits of claim | OpenEMS protects the transformer by managing site load behind the connection point, not by controlling utility assets (B4 Section 4.6). Avoided outage or upgrade cost is reported only if data supports it |

## 7. Comparison with the 15 to 30% range

The range is a hypothesis from international studies and is a reference, not a target (Problem Statement Section 3). Rules are pre-registered at Gate 2 and follow E1 Section 7.1.

| Step | Rule |
| --- | --- |
| 1 | Express K3 per site as % of the counterfactual bill with its interval, on twelve validated months where available |
| 2 | Compare the point estimate and interval with 15 to 30% |
| 3 | Classify: **within or above range**; **below range but distinguishable from zero**; **not distinguishable from zero**; **negative** |
| 4 | State the mechanism visible in the data and the share of savings from each mechanism |
| 5 | Apply the seasonal check. A full year removes most but not all seasonal risk. State the residual risk |

| Site | K3 (% of counterfactual bill) | Interval | Category | Position vs E1 | Main mechanism | Confidence |
| --- | --- | --- | --- | --- | --- | --- |
| A | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| B | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

A result below the range is reported as a local finding and diagnosed (Section 8). It does not lead to a change in baseline, range or method.

## 8. Diagnosis, mechanism and confounders

Where a KPI is below target or below the range, E2 uses the fixed diagnosis order from E1 Section 9 and records the answer.

| Order | Question | Possible finding |
| --- | --- | --- |
| 1 | Is the data sound? | Data problem, not a performance result |
| 2 | Was the system actually in control? | Availability or operating problem |
| 3 | Was the configuration as designed? | Configuration problem |
| 4 | Did the economic conditions exist (tariff spread, demand charges, load shape, export credit)? | Weak economic test, not a control failure |
| 5 | Did confounders distort the comparison? | Result contested or partly modelled |
| 6 | Is the mechanism visible in the data? | Mechanism present or absent |
| 7 | Is the effect real but smaller than the range? | Genuine local finding |

Diagnosis results per site and KPI: [ ].

## 9. The central question: verdict

### 9.1 Techno-economic validation

Measured results replace assumptions in the techno-economic model (B2), following D1 Section 11.

| Output per site | Value | Notes |
| --- | --- | --- |
| Annual net benefit (measured, twelve months) | [ ] | Interval and assumptions |
| Simple payback and NPV on **replication cost** | [ ] | Sensitivities: battery cost ±20%, discount rate 5 to 12%, export credit below 50%, tariff spread, inflation about 5% |
| Pilot cost versus replication cost | [ ] | Research overhead separated (Feasibility Study 5.4) |
| Cost per kW of peak reduced; levelised cost of stored energy | [ ] | |
| Break-even conditions | [ ] | Tariff spread, load size and battery cost under which OpenEMS is viable, not only a point estimate |
| Position against site break-even | [ ] | Illustration from the Feasibility Study: USD 100k net capex and an eight-year payback needs about USD 12.5k net benefit a year |

The report states which economics rest on bills and which rest on diesel, reliability or asset protection. The cost of "free" software is shown honestly: integration, skills and service rather than licences (Feasibility Study 5.2). Actual driver effort, custom drivers and training spend are reported against the budget reconciliation.

### 9.2 Rating scale (pre-registered at Gate 2)

Each lens is rated on evidence, with a confidence label.

| Rating | Meaning |
| --- | --- |
| Supported | The evidence meets the pre-registered threshold for the lens, with acceptable uncertainty |
| Supported with conditions | Met at one or more sites, or only under stated conditions (for example tariff structure or hardware class) |
| Not supported | Evidence at or below the threshold, with the diagnosis showing the cause is not data or operating failure |
| Inconclusive | Data, duration or confounders prevent a defensible rating |

### 9.3 Final scorecard (complete at Month 24)

| Lens | Evidence | Pre-registered threshold | E1 rating | Final rating | Confidence | Residual uncertainty |
| --- | --- | --- | --- | --- | --- | --- |
| Technical | K1, K2, K4, K5, K6, compatibility record, safe-state events, driver effort | [Gate 2] | [ ] | [ ] | [ ] | [ ] |
| Economic | K3, net benefit, payback and break-even on replication cost | [Gate 2] | [ ] | [ ] | [ ] | [ ] |
| Regulatory and institutional | EPRA and Kenya Power positions, net-metering, licensing, interconnection, adoption of model or register | [Gate 2] | [ ] | [ ] | [ ] | [ ] |
| Social, environmental, safety | Incident record, complaints, acceptance, supply continuity, waste and end of life | [Gate 2] | [ ] | [ ] | [ ] | [ ] |
| Delivery and capacity | Schedule, operators competent and retained, support without foreign input, spend | [Gate 2] | [ ] | [ ] | [ ] | [ ] |

### 9.4 Answer to the central question

> *Can an open-source energy management system such as OpenEMS be deployed in Kenya to stabilise a high-renewable grid, reduce losses, lower energy costs and safely integrate EV charging, and is it technically, economically and institutionally viable to do so?*

| Outcome | Condition (pre-registered) |
| --- | --- |
| Viable, go to scale | All lenses Supported or Supported with conditions, and break-even conditions are reachable on replication cost for at least [one] site type |
| Viable under conditions | Technical and safety lenses Supported, economic or institutional lenses Supported with conditions. The conditions are listed as the replication pre-requisites |
| Not yet viable | One or more lenses Not supported, with a diagnosed and addressable cause. State what would change the answer |
| Not viable in Kenyan conditions | Technical, economic or institutional evidence at or below threshold with no addressable cause. Reported as a successful research result |
| Inconclusive | Evidence insufficient to rate. State what evidence is missing and what it would cost to obtain |

Answer for this pilot: [ ]. Per scenario: C&I (A) [ ]; rural microgrid (B) [ ]; EV depot (C) [ ]. The answer is given per scenario because the sites differ, and no national claim is made from three sites.

### 9.5 Answers to supporting questions

| # | Answer (two to four sentences, with intervals) | Strength of evidence |
| --- | --- | --- |
| Q1 | [ ] | [ ] |
| Q2 | [ ] | [ ] |
| Q3 | [ ] | [ ] |
| Q4 | [ ] | [ ] |
| Q5 | [ ] | [ ] |

## 10. Regulatory, institutional and capacity findings

| Topic | What to report |
| --- | --- |
| Net-metering | Terms confirmed, any proposal to change them during the pilot, results at export credits at and below 50% |
| BESS, mini-grid and EV charging licensing | Positions obtained, exemptions or sandbox conditions, time taken, what a replicator should expect |
| Kenya Power | Interconnection time and conditions, data access, witness record, control-boundary compliance |
| Data protection | Registration, DPIA outcome, consent and notice experience, incidents, publication restrictions |
| Cybersecurity | Audit result at Gate 3, findings by severity, incidents, drift, patch record, what the audit missed |
| Contracting, equipment title, end of life | Decisions taken, problems, actual take-back and decommissioning route |
| Local capacity | Operators trained, assessed competent, retained after [12] months, local trainers at C4, support still needed from outside |
| Adoption | Regulators, utilities or developers that adopted the model or risk register |

Programme-level success criteria (Charter Section 7) are tested directly:

| Criterion | Met? | Evidence |
| --- | --- | --- |
| All three sites commissioned and operating | [ ] | [ ] |
| At least 12 months of continuous validated data | [ ] | [ ] |
| KPI results published openly | [ ] | [ ] |
| Techno-economic model and risk register adopted by at least one regulator or utility | [ ] | [ ] |
| Trained local team able to operate and support OpenEMS without continuous foreign support | [ ] | [ ] |

## 11. Risk register outcome

| Initial risk (Charter Section 18) | Occurred? | Effect | Mitigation that worked or failed | Residual |
| --- | --- | --- | --- | --- |
| Regulatory change | [ ] | [ ] | [ ] | [ ] |
| Cybersecurity of remote assets | [ ] | [ ] | [ ] | [ ] |
| Limited local OpenEMS expertise | [ ] | [ ] | [ ] | [ ] |
| Interoperability with local hardware | [ ] | [ ] | [ ] | [ ] |
| Poor rural connectivity | [ ] | [ ] | [ ] | [ ] |
| Cost overruns or tariff changes | [ ] | [ ] | [ ] | [ ] |
| Delay in host site or interconnection approval | [ ] | [ ] | [ ] | [ ] |
| Savings below the 15 to 30% range | [ ] | [ ] | [ ] | [ ] |

Risks added during the pilot, and risks still open at closure with named custodians: [ ].

## 12. Lessons learned

| Theme | Questions |
| --- | --- |
| Compatibility and integration | Which devices behaved as tested, which did not, and what did drivers actually cost? |
| Commissioning | What slipped, why, and what compressed the evidence window? |
| Operations | Repeated faults, repair times, spares, what operators found hard |
| Security | Findings, incidents, hardening gaps |
| Community and users | Complaints, acceptance, throttling reactions, supply continuity |
| Economics | Where bills, diesel, reliability and asset protection actually paid |
| Regulation | Where licensing, net-metering or interconnection created delay or doubt |
| Method | What the baseline and counterfactual approach could and could not support |

Negative lessons carry equal prominence and feed the replication guide (E3).

## 13. Recommendations

Recommendations are separate from findings, each traced to a finding and labelled by who must act.

| # | Recommendation | Finding it rests on | Audience | Timing | Evidence strength |
| --- | --- | --- | --- | --- | --- |
| R1 | [ ] | [ ] | Ministry of Energy, EPRA (policy and regulatory) | [ ] | [ ] |
| R2 | [ ] | [ ] | Kenya Power (interconnection, data, grid) | [ ] | [ ] |
| R3 | [ ] | [ ] | Developers and C&I hosts (economics, siting) | [ ] | [ ] |
| R4 | [ ] | [ ] | Mini-grid operators and communities | [ ] | [ ] |
| R5 | [ ] | [ ] | EV charging operators and fleets | [ ] | [ ] |
| R6 | [ ] | [ ] | Funders (scale-up, replication cost) | [ ] | [ ] |
| R7 | [ ] | [ ] | OpenEMS community and vendors (drivers, documentation) | [ ] | [ ] |
| R8 | [ ] | [ ] | Universities and training bodies | [ ] | [ ] |

Policy recommendations on net-metering, BESS and EV rules are developed in the policy brief (E4). The programme informs regulation but does not decide it (Charter Section 5).

## 14. Replication and scale-up

| Item | Content |
| --- | --- |
| Replication cost | Cost per site type with research overhead excluded, with ranges |
| Pre-requisites | Tariff structure, load size, connectivity, licensing, hardware class and local service needed for viability, taken from break-even conditions |
| Conditions where it does not pay | Stated as clearly as where it does |
| Skills and service model | Operator, backup, trainer and service arrangements that worked |
| Scale-up options | Options and funding needed, stated as options and not as promises |
| Post-pilot operation | Who operates, services and pays for each site after Gate 5 (D3 Section 18) |

## 15. Limitations

| Limitation | Effect on interpretation |
| --- | --- |
| Three sites, one per scenario | No statistical generalisation. Findings are site evidence |
| Twelve-month window | One cycle of seasons and tariffs. Multi-year degradation not observed |
| Counterfactual model | Model error carried into intervals |
| Host behaviour and benefit sharing | Possible confounding, recorded in D5 |
| Pilot B loss separation | Defensible only if the Panel judged so |
| Pilot C demand reconstruction | Depends on session data quality |
| Equipment and firmware specific | Results apply to the tested device and firmware set (B6) |
| Regulatory snapshot | Rules as at the pilot period. Later changes may alter the economics |

## 16. Publication and disclosure

| Item | Rule |
| --- | --- |
| Review chain | Independent reviewer, Panel accuracy check, security and privacy review, then Programme Director approval (Charter Section 21, D2 Section 10) |
| Directly involved parties | Hosts, Kenya Power, EPRA and communities see findings before release. Comment period [14] days. They cannot require changes. Delay up to [60] days only for personal data, security or a legitimate legal interest (MoU Section 10) |
| Outputs | This report, anonymised datasets and code (E5), policy brief (E4), replication guide (E3), paper (E6), plain-language English and Kiswahili summaries |
| Disclosure thresholds | No figure based on fewer than [k] customers, sessions or vehicles. Household data only at feeder or transformer-group level. Charger data only at hourly or session-distribution level. Host commercial data only with consent, but aggregated results cannot be blocked |
| Withheld | Credentials, live network details, unpatched vulnerabilities, personal data |
| Language | States this was a research pilot and results are measured, not guaranteed. No promises on tariffs, jobs or supply. Vendors make no performance claims from E2 without Research Lead approval |

## 17. Closure and handover

| Item | Requirement |
| --- | --- |
| Acceptance | SteerCo accepts results, approves publication and handover at Gate 5 |
| Custodians | Risk register, techno-economic model, training materials, datasets, code and series archive transferred to named custodians (Charter Section 24) |
| Equipment | Transferred, removed or decommissioned per Schedule 4, with safety and end-of-life briefing (D3 Section 18) |
| Data | Retained, anonymised or deleted per D2 Section 9. Confirmation to hosts, Kenya Power and the university |
| Credentials | Revoked or handed over |
| Post-pilot plan | Support, scale-up options and funding agreed |

## 18. Structure of the Month 24 report

| Section | Content |
| --- | --- |
| Cover | Report ID `E2-[YYYY-MM]`, status, authors, reviewer, Panel validation reference |
| Summary | Two pages: the answer to the central question, five findings, five recommendations, main limits |
| 1. Evidence base | Sections 4 and 5 |
| 2. Results | Section 6 |
| 3. Range comparison and diagnosis | Sections 7 and 8 |
| 4. Verdict | Section 9 |
| 5. Regulatory, institutional, capacity | Section 10 |
| 6. Risks and lessons | Sections 11 and 12 |
| 7. Recommendations and replication | Sections 13 and 14 |
| 8. Limitations | Section 15 |
| Annexes | Monthly series, data dictionary link, mode records, change and incident extract, restatement log, deviations, sign-off |

## 19. Schedule and gate evidence

| Activity | Months | Output | Gate |
| --- | --- | --- | --- |
| Pre-register structure, verdict rules and thresholds with the Panel | 6 to 8 | Pre-registered rules | Gate 2 |
| Dry-run E2 template on E1 data | 18 to 20 | Tested template | |
| Data cut-off, final analysis, diagnosis, model validation | 21 to 22 | Draft E2 | |
| Independent review, Panel validation, security and privacy review | 22 to 23 | Validated E2 | |
| Review by directly involved parties | 23 | Comments log | |
| Gate 5 SteerCo review | 24 | Acceptance and publication decision | **Gate 5** |
| Publication (E3, E4, E5, E6) | 24 and after | Published package | |

| Gate | Evidence from E2 |
| --- | --- |
| Gate 2 | Pre-registered structure, verdict rules and thresholds approved |
| Gate 5 | Validated E2, final scorecard, answer to the central question, recommendations, handover record, lessons learned |

**Critical path.** E2 depends on 12 months of validated controlled data. Late commissioning shortens the window. If a site has fewer than 12 months at cut-off, E2 reports that site as partial and says what the missing months would have added. A short extension needs SteerCo approval under the stop-or-extend rule (C3 Section 14).

## 20. Risks to add to the live Risk Register

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| FE1 | A site holds under 12 months of validated controlled data at cut-off | M | H | Early baseline start, stop-or-extend rule, backup sites, partial-site labelling | Programme Director |
| FE2 | Pressure to soften, delay or reframe results | M | H | Pre-registration, equal prominence, independence clauses, independent reviewer | Programme Director |
| FE3 | Verdict thresholds altered after data is seen | L | H | Gate 2 freeze, SteerCo approval on Panel advice | Research Lead |
| FE4 | Three-site results over-generalised by readers or funders | M | M | Per-scenario answers, limitations section, break-even conditions | Research Lead |
| FE5 | Results read as promises by hosts, communities or vendors | M | M | Research-pilot wording, plain-language summaries | Programme Manager |
| FE6 | Disclosure of personal or commercial data | L | H | k threshold, release clearance, host review | Cybersecurity Officer |
| FE7 | Analyst or university capacity gap at cut-off | M | M | Named backup analyst, documented code | Research Lead |
| FE8 | No funded custodian or post-pilot plan at Gate 5 | M | H | Name custodians early, post-pilot budget line | Programme Sponsor |
| FE9 | Regulatory change near closure alters the economic conclusion | M | M | Sensitivity runs, regulatory snapshot date stated | Legal and regulatory lead |

These risks are to be merged into the live Risk Register (README A6).

## 21. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Define lens thresholds and the verdict table numerically (Section 9) | Gate 2 | Panel |
| 2 | Fix the minimum validated months for a "final" versus "partial" result | Gate 2 | Panel |
| 3 | Agree the seasonal and annualisation method | Gate 2 | Research Lead, university partner |
| 4 | Decide the independent reviewer for E2 | Gate 3 | Programme Director |
| 5 | Agree how deviations and restatements are shown publicly | Gate 3 | Research Lead |
| 6 | Decide the publication route for E6 and authorship | Gate 4 | Research Lead, university partner |
| 7 | Agree the treatment of E1 course corrections in the final analysis | Gate 4 | Research Lead, Panel |
| 8 | Itemise E2 costs: analyst time, university budget, translation, publication | Gate 1 | Programme Manager |
| 9 | Name custodians of the report, datasets and series archive | Gate 5 | Programme Sponsor |

## 22. Immediate next steps

1. Panel and TWG to review this structure, including the Kenya Power grid engineer on feeder and transformer interpretation.
2. Research Lead to add the verdict rules and thresholds to the pre-registered analysis plan before any controlled data exists.
3. Data analyst to build the E2 pipeline and template and test it with E1 data.
4. Agree who presents E2 and who is the independent reviewer.
5. Draft the plain-language English and Kiswahili summary template.
6. Itemise E2 and publication costs in the budget reconciliation.
7. Add risks FE1 to FE9 and the open items to the PMO log and Risk Register.

---

# Appendix A: Gate 5 evidence checklist

| # | Requirement (Charter Section 16 and gate tables) | Evidence | Owner | Done |
| --- | --- | --- | --- | --- |
| 1 | Twelve months of validated data per site, or shortfall stated | MR-1 Months 13 to 24, Panel notes | Research Lead | [ ] |
| 2 | Final KPI results with uncertainty | Section 6 | Research Lead | [ ] |
| 3 | Range comparison and diagnosis | Sections 7 and 8 | Research Lead | [ ] |
| 4 | Techno-economic validation on replication cost | Section 9.1 | Techno-economic analyst | [ ] |
| 5 | Final scorecard and answer to the central question | Section 9 | Research Lead | [ ] |
| 6 | Regulatory, security and capacity findings | Section 10 | Programme Director | [ ] |
| 7 | Final risk register status | Section 11 | Programme Manager | [ ] |
| 8 | Lessons learned and recommendations | Sections 12 and 13 | Programme Manager | [ ] |
| 9 | Asset handover and decommissioning records | Section 17 | Site Leads | [ ] |
| 10 | Data archive, deletion and custodian briefings | D2 Section 9 | Cybersecurity Officer | [ ] |
| 11 | Independent review and Panel validation recorded | Sign-off | Research Lead | [ ] |
| 12 | Publication clearance (security and privacy) | Release record | Cybersecurity Officer | [ ] |

# Appendix B: Final result block (template, one per KPI per site)

| Field | Entry |
| --- | --- |
| KPI, site, window | [ ] |
| Result, unit | [ ] |
| Counterfactual or baseline, model version | [ ] |
| Difference and interval, method | [ ] |
| Result category | [ ] |
| Target and status | [ ] |
| Position against 15 to 30% range (K3) | [ ] |
| Change since E1 and reason | [ ] |
| Completeness, exclusions applied | [ ] |
| Mode record and configuration hash | [ ] |
| Mechanism evidence | [ ] |
| Confounders and overrides in the window | [ ] |
| Caveats (season, model fit, hardware set) | [ ] |

# Appendix C: Gate 5 recommendation sheet

| Field | Entry |
| --- | --- |
| Answer to the central question (viable at scale, viable under conditions, not yet viable, not viable, inconclusive) | [ ] |
| Per-scenario position | A [ ]; B [ ]; C [ ] |
| Decision requested (accept results, approve publication, approve handover) | [ ] |
| Conditions attached | [ ] |
| Dissenting views from the Panel, partners or hosts | [ ] |
| Presented by and decided by (names, date) | [ ] |

# Appendix D: Sign-off

| Role | Name | Signature | Date |
| --- | --- | --- | --- |
| Data analyst (author) | [ ] | | |
| Techno-economic analyst | [ ] | | |
| Research Lead | [ ] | | |
| Independent reviewer | [ ] | | |
| Panel chair (validation) | [ ] | | |
| Cybersecurity and Data Protection Officer (release clearance) | [ ] | | |
| Programme Director | [ ] | | |

# Appendix E: Traceability

| Source | Used for |
| --- | --- |
| Problem Statement | Central question, Q1 to Q5, research gap |
| Programme Charter (Sections 3, 5, 7, 16, 18, 20, 21, 23, 24) | Mission, scope limits, KPIs, success criteria, Gate 5, risks, change control, independence, closure |
| Feasibility Study (Sections 5.2, 5.4 to 5.6, 11, 12) | Scorecard lenses, break-even logic, replication cost, conditional go |
| Monitoring and Evaluation Plan (D1) | KPI dictionary, modes, baseline, decision rules, techno-economic validation |
| Monthly Performance Reports (D6) | Source series, status scheme, restatements |
| Interim Evaluation Report (E1) | Trigger test, diagnosis order, course corrections, interim scorecard |
| Incident and Change Log (D5) | Incidents, changes, confounders, drift |
| Operations and Maintenance Manual (D3), Training Records (D4) | Uptime, repair, competence, retention, post-pilot plan |
| OpenEMS Configuration Baseline (C4), Interoperability Register (B6) | Modes, hashes, tested device set, driver effort |
| Regulatory Compliance Assessment (B5), Cybersecurity Plan (B7) | Regulatory outcomes, audit and incident record |
| Data Management and Privacy Plan (D2) | Disclosure, retention, release process |
| Stakeholder Engagement Plan | Acceptance, complaints, disclosure before publication |
| MoU and Site Agreement templates (MoU Section 10; Site Agreement 9.3, Schedule 4) | Publication rights, host comment limits, equipment closure |

On completion of the Gate 1 and Gate 2 decisions (targets, thresholds, verdict rules, seasonal method), each bracketed value is updated and this document is re-issued as version 1.0 for Gate 2. The completed report is issued at Month 24 for Gate 5.

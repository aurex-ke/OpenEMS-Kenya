# Interim Evaluation Report

## 1. Purpose and bottom line

The Charter makes Gate 4 the point where the Steering Committee confirms continued operation or orders corrective action, on the evidence of six months of validated data, uptime results and early KPI trends (Charter Section 16). The Monitoring and Evaluation Plan (D1) assigns that evidence to this report (Section 13). E1 is the **mid-pilot findings report**: what the three pilots have shown so far, how reliable that evidence is, how it compares with the 15 to 30% international range, and what should change in the second half of the pilot.

**Status note.** No site is selected, built or measured, and no data exists. This version is therefore a **pre-populated report template**: the structure, evidence rules, interpretation rules, decision rules and tables are fixed now, and every result field is completed in Month 18 from validated monthly reports (D6). It must not be used to state or imply any result.

**Bottom line.** E1 is an interim, partial-year, partly seasonal reading. Nine rules govern it:

1. **Validated data only.** E1 uses only months validated by the Research and Evaluation Panel (Months 13 to 18). Provisional figures never enter it (D6 Section 1).
2. **Six months is not a year.** Results are labelled interim. Annualised figures are estimates with the approved seasonal adjustment and a stated uncertainty (D1 Section 12.1).
3. **Same definitions as D1.** KPIs K1 to K6 use the frozen KPI dictionary and the pre-registered analysis plan. E1 introduces no new KPI, definition or method. Any added analysis is labelled exploratory.
4. **Uncertainty with every number.** Each KPI carries its interval, data completeness and mode record. Where uncertainty exceeds the effect, E1 says the effect is not distinguishable from zero (D1 Section 8.3).
5. **Mechanism before magnitude.** A saving is credited to OpenEMS only where the mechanism is visible in the data.
6. **Negative and null results have equal prominence.** A result below the 15 to 30% range is a finding, not a failure of the programme. It is also a Charter escalation trigger at Gate 4 (Charter Section 18).
7. **Course corrections protect the experiment.** Corrections may fix operations, safety, capacity and data quality. They may not re-baseline, redefine a KPI or move a target without SteerCo approval on Panel advice (Charter Section 20).
8. **Independence.** The Research Lead writes the findings. Hosts, vendors and funders may comment on drafts but cannot require changes (MoU Section 10.2).
9. **Honest limits.** Pilot B loss separation and Pilot C delay effects are hard to measure. E1 states what cannot be shown.

## 2. Document control and relationships

**Owner:** Research Lead (README E1, "M&E lead"). **Authors:** data analyst, university partner. **Contributors:** Technical Lead, software engineer, Cybersecurity and Data Protection Officer, Capacity-building lead, Site Leads, Programme Manager and PMO, finance lead, Kenya Power grid engineer (TWG). **Review:** independent reviewer (Charter Section 23), then Panel validation. **Approval:** Programme Director presents to the SteerCo at Gate 4. **Method frozen:** at Gate 2 with the M&V protocol. Changes follow Charter Section 20.

| Document | Relationship |
| --- | --- |
| Problem Statement | Central question and supporting questions Q1 to Q5 |
| Programme Charter (Sections 7, 15, 16, 18, 20, 21, 23) | KPIs, Gate 4 evidence and decision, escalation trigger, change control, independence, evaluation rules |
| Monitoring and Evaluation Plan (D1) | KPI dictionary, modes, baseline method, quality checks, decision rules, scorecard |
| Monthly Performance Reports (D6) | Source series. E1 consolidates MR-1 to MR-3 for Months 13 to 18 |
| Incident and Change Log (D5) | Incidents, changes, confounders, drift, failed changes |
| Operations and Maintenance Manual (D3) | Uptime, faults, repair times, maintenance, spares |
| Training Materials and Attendance Records (D4) | Attended, competent and retained figures |
| OpenEMS Configuration Baseline (C4) | Mode records, hashes, drift, change classes |
| Techno-economic model (B2) and Budget tracker (C2) | Measured inputs replace assumptions. Spend and replication cost |
| Risk Register (A6) | Top risks, trigger status, risks added from findings |
| Data Management and Privacy Plan (D2) | Disclosure rules, minimum group size, release process |
| Stakeholder Engagement Plan | Complaints, participation, disclosure before publication |
| Final evaluation (E2), Replication guide (E3), Policy brief (E4) | Receive E1 findings and its course-correction record |

## 3. Evaluation questions and what E1 can and cannot answer

| # | Question (Problem Statement) | Pilots | What E1 can say at Month 18 | What it cannot say |
| --- | --- | --- | --- | --- |
| Q1 | Can battery dispatch smooth VRE variability and reduce peak demand? | A, B, C | Early K1 and ramp-rate results with uncertainty, and whether the dispatch mechanism is visible | Full-year peak behaviour across seasons |
| Q2 | How much can local solar-plus-storage reduce technical and commercial losses? | B | Early K6 on total loss, and technical versus commercial split only if the Panel judged it defensible | A general loss reduction figure from one feeder |
| Q3 | What bill savings and payback are achievable under ToU and the 50% net-metering credit? | A (B, C where tariffs apply) | Early K3 against the 15 to 30% range, split by mechanism, with a provisional break-even position | Annual savings or a final payback |
| Q4 | Can EV cluster control prevent transformer overload without unacceptable delay? | C | K5 transformer loading, full-capacity share and wait-time distribution against the agreed limit | Long-run behaviour as the charger fleet grows |
| Q5 | What regulatory, cybersecurity, maintenance and capacity risks must be managed? | All | Incident, change, uptime, training and regulatory record over six months | Whether capacity persists after the pilot |

The **central question** is not answered at Gate 4. E1 reports an interim scorecard (Section 10) and says what evidence is still needed.

## 4. Evidence base and rules of use

### 4.1 Data window

| Item | Rule |
| --- | --- |
| Window | Months 13 to 18 of the programme, per site, from the start of validated controlled data (M2) |
| Baseline | Baseline data from M1 and the counterfactual model approved by the Panel (D1 Section 7). Baseline length and test pattern as fixed at Gate 2 |
| Included | Validated monthly datasets (MR-1) with a valid mode flag and configuration hash |
| Excluded | M0 commissioning, M3 fault and M4 maintenance periods from savings, with their effect on uptime reported separately. Confounder periods excluded or modelled as recorded |
| Cut-off | Data cut-off at Month 18 month end plus the D6 production calendar. Late data goes into E2 with a restatement note |
| Early-month label | The first [3] months of controlled operation are labelled "early" (D6 Section 8.2) |
| Minimum for a result | A KPI is reported as a result only if completeness and reconciliation meet the Panel threshold [x]%. Otherwise it is "not reportable" with the reason |

### 4.2 Evidence hierarchy

1. Independent research meters and logger, reconciled with Edge data. The research meter prevails unless faulty.
2. Billing and tariff documents from hosts, checked against meter data.
3. Edge control data, used for mechanism and uptime.
4. Site logs, D5 entries, D3 reports and D4 records, used for context and institutional findings.
5. Stakeholder and driver feedback, reported as qualitative evidence and not as a measure of effect.

### 4.3 Data quality summary (complete from D6)

| Site | Months covered | Completeness (%) | Longest gap (h) | Edge vs research meter difference (%) | Restatements | Seals and accuracy checks | Reportable KPIs |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| B | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| C | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

## 5. Operating record to Month 18

### 5.1 Modes and configuration

| Site | Days in M1 | Days in M2 | Days in M3 | Days in M4 | Control-off weeks (if used) | Configuration tag and hash at cut-off | KPI-relevant changes (D5 IDs) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| B | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| C | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

### 5.2 Availability, incidents and changes

| Item | Source | A | B | C |
| --- | --- | --- | --- | --- |
| Uptime and availability (K4), with cause breakdown | D6, D3 | [ ] | [ ] | [ ] |
| Mean time to acknowledge and to repair | D3 | [ ] | [ ] | [ ] |
| P1, P2, P3, P4 incidents (D5) | D5 | [ ] | [ ] | [ ] |
| Safe-state events and setpoint clamps | Edge, D5 | [ ] | [ ] | [ ] |
| Changes by class C0 to C4, failed or rolled-back changes | D5 | [ ] | [ ] | [ ] |
| Unexplained drift events | C4, D5 | [ ] | [ ] | [ ] |
| Compatibility or firmware problems found in operation (B6 Gate 4 evidence) | D5, B6 | [ ] | [ ] | [ ] |
| Supply continuity confirmation: no disconnection or price rise from the pilot | Operator, Kenya Power | n/a | [ ] | n/a |

Failures, rollbacks and workarounds are listed with equal prominence to successes.

## 6. KPI results

Results use the standard KPI block (D6 Section 8.1). Targets are those frozen at Gate 1. Where a target is not set, the status is "NO TARGET" and is not coloured.

### 6.1 Summary table (complete at Month 18)

| KPI | Pilot | Interim result | Counterfactual or baseline | Difference with interval | Result category (D1 12.1) | Target | Completeness | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| K1 Peak grid import reduction (kW, %) | A | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| | B | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| | C | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| K2 Self-consumption ratio | A | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| | B | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| K3 Bill savings (KSh, %) | A | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| | B | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| K4 Uptime and availability | A | [ ] | n/a | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| | B | [ ] | n/a | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| | C | [ ] | n/a | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| K5 Transformer loading, full-capacity share | C | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |
| K6 Loss fraction and reduction | B | [ ] | [ ] | [ ] | [ ] | [Gate 1] | [ ] | [ ] |

Status words follow D6 Section 10: ON TRACK, WATCH, OFF TRACK, ESCALATED, NO TARGET.

### 6.2 Pilot A: industrial park, hub or campus

| Item | Content to report |
| --- | --- |
| K1 | Adjusted baseline peak minus controlled peak over tariff-relevant windows and the monthly maximum interval |
| K2 | (PV generation minus export) divided by PV generation, battery losses separate |
| K3 | Counterfactual bill minus actual bill under the actual tariff and the net-metering rules as confirmed by EPRA, in KSh and as % of the counterfactual bill, against the 15 to 30% range |
| Mechanism split | Savings from peak or demand charge, ToU shifting and export credit shown separately, so the report shows which mechanism pays |
| Tariff reality | Actual ToU spread and demand charges at the host. If neither is meaningful, E1 says the site is a weak economic test (B4 Section 5.2) |
| Critical loads | Protected-load overrides, periods excluded, any savings not counted because overrides distorted dispatch |
| Host effects | Host behaviour changes, tariff changes and benefit-sharing effects recorded as confounders |

### 6.3 Pilot B: rural microgrid

| Item | Content to report |
| --- | --- |
| K6 | Loss fraction (input minus billed over input) before and after control, normalised for load, season and customer numbers |
| Separation | State plainly whether technical and commercial losses could be separated defensibly. If not, report total loss change only |
| Metering coverage | Share of customers metered, check meter coverage, energy balance closure |
| K2 and diesel | Self-consumption, diesel energy and fuel displaced from generator kWh, run hours and fuel volume |
| Reliability | Outage frequency and duration against the baseline, with causes, and low-voltage events from voltage logs |
| Data gaps | Gap hours against the agreed threshold. An exceeded threshold is a Charter escalation trigger |
| Caveat | One feeder with a small customer count gives noisy estimates. Results are site evidence, not a general loss figure |

### 6.4 Pilot C: EV charging site

| Item | Content to report |
| --- | --- |
| K5a | Peak kW, load-duration curve and time above the agreed threshold, managed versus reconstructed unconstrained demand |
| K5b | Share of charging time at requested power, per session and in aggregate |
| Delay | Waiting time per session: median, 90th percentile and maximum, against the agreed maximum wait |
| Fairness | Share of energy by customer class under the agreed policy |
| Acceptance | Complaints per 100 sessions, fleet operator and driver feedback, vehicles that reject limiting |
| Limits of claim | OpenEMS protects the transformer by managing site load behind the connection point, not by controlling utility assets. Avoided outage or upgrade cost is reported only if data supports it |

## 7. Comparison with the 15 to 30% range and the Gate 4 trigger

The Charter makes interim results trending below the 15 to 30% range at Gate 4 an escalation trigger (Charter Section 18). Because the range is a hypothesis from international studies, E1 treats it as a reference, not a target.

### 7.1 Test applied (pre-registered, to be fixed at Gate 2)

| Step | Rule |
| --- | --- |
| 1 | Express K3 per site as % of the counterfactual bill, with its interval, using validated months only |
| 2 | Compare the point estimate and the interval with the 15 to 30% range |
| 3 | Classify: **within or above range**; **below range but distinguishable from zero**; **not distinguishable from zero**; **negative** |
| 4 | Define "trending below" before data is seen: [for example, the upper bound of the interval is below 15%, or the point estimate is below 15% for [3] consecutive validated months]. Fixed by the Panel at Gate 2 |
| 5 | Apply the seasonal adjustment note. A six-month window may over- or under-state the annual position |
| 6 | If the trigger fires, status is ESCALATED and Section 11 applies |

### 7.2 Result table (complete at Month 18)

| Site | K3 (% of counterfactual bill) | Interval | Category | Trigger fired (Y/N) | Main mechanism visible | Confidence in the estimate |
| --- | --- | --- | --- | --- | --- | --- |
| A | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| B | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

Sites are reported separately and are not averaged. A result below the range triggers a diagnosis (Section 9), not a change to the baseline or the range.

## 8. Techno-economic update

Measured results replace assumptions in the techno-economic model (B2), following D1 Section 11.

| Model input | Measured replacement at Month 18 | Status |
| --- | --- | --- |
| Annual energy bill and tariff spread | Host bills and tariff documents | [ ] |
| Peak reduction and shifted energy | K1 and mechanism split, annualised with stated adjustment | [ ] |
| Battery efficiency and degradation | Round-trip efficiency, cycles, state of health | [ ] |
| Diesel offset | Fuel and run-hour data (B) | [ ] |
| Equipment, integration and O&M cost | Cost tracker (C2) actuals, pilot cost and replication cost separate | [ ] |
| Export credit | Sensitivity runs at and below 50% | [ ] |

| Output per site | Value | Notes |
| --- | --- | --- |
| Running annual net benefit (estimate) | [ ] | Interval and assumptions |
| Simple payback and NPV on replication cost | [ ] | Charter sensitivities: battery cost ±20%, discount rate 5 to 12%, export credit below 50%, tariff spread |
| Cost per kW of peak reduced | [ ] | |
| Position against site break-even conditions | [ ] | Feasibility Study 5.5 logic: for example, USD 100k net capex and an eight-year payback needs about USD 12.5k net benefit a year. State where each site stands |

The report states which economics rest on bills and which rest on diesel, reliability or asset protection (Feasibility Study 5.5). Commercial viability is judged on replication cost, not pilot cost.

## 9. Diagnosis, mechanism and confounders

Where a KPI is below target or below the range, E1 does not assume OpenEMS failed. It works through a fixed diagnosis order and records the answer.

| Order | Question | Evidence | Possible finding |
| --- | --- | --- | --- |
| 1 | Is the data sound? | Completeness, reconciliation, meter checks, restatements | Data problem, not a performance result |
| 2 | Was the system actually in control? | Uptime, M3 and M4 days, overrides, safe-state events | Availability or operating problem |
| 3 | Was the configuration as designed? | Hash, drift reports, failed changes | Configuration problem |
| 4 | Did the economic conditions exist? | Tariff spread, demand charges, load shape, export credit | Weak economic test, not a control failure |
| 5 | Did confounders distort the comparison? | Confounder log, host behaviour, new loads, tariff changes | Result contested or partly modelled |
| 6 | Is the mechanism visible? | Battery discharge in peak window, generator avoided, charger limit binding | Mechanism present or absent |
| 7 | Is the effect real but smaller than the range? | Intervals against range | Genuine local finding |

Findings from this order feed Section 11 and are written into the replication guide (E3).

## 10. Interim scorecard

Rated on the same lenses as the Feasibility Study and D1 Section 12.2. Ratings are interim and carry a confidence label.

| Lens | Interim evidence | Interim rating | Confidence | Evidence still needed for E2 |
| --- | --- | --- | --- | --- |
| Technical | K1, K2, K4, K5, K6, compatibility results, safe-state events | [ ] | [ ] | [ ] |
| Economic | K3, net benefit, break-even position on replication cost | [ ] | [ ] | [ ] |
| Regulatory and institutional | EPRA and Kenya Power positions obtained and held, any formal proposals affecting the pilot, adoption of model or register | [ ] | [ ] | [ ] |
| Social, environmental, safety | Incident record, complaints, acceptance, participation, supply continuity | [ ] | [ ] | [ ] |
| Delivery and capacity | Schedule, operators competent and retained, support without foreign input, spend | [ ] | [ ] | [ ] |

## 11. Course corrections

### 11.1 What may and may not be corrected

| Category | Examples | Route |
| --- | --- | --- |
| Operations | Spares, service response, inspection routine, operator rota | PMO and Site Lead, logged in D5 |
| Safety and security | Control strengthening after an incident, hardening, drills | C6 and B7 routes, change class C1 or C3 |
| Capacity | Extra training, backup operators, trainer bench, allowances | D4 plan, SteerCo if budget changes |
| Data quality | Meter fixes, buffering, check meters, gap handling | Research Lead and Panel, change class as relevant |
| Control tuning that affects a KPI-relevant parameter | Peak setpoint, tariff window, charging policy | Class C2. Panel approval. Treated as a change to the experiment and recorded as such (C4 Section 6.6) |
| Sites | Dropping a site to a reserve, extending Gate dates, reducing scope | SteerCo only (Charter Section 20, C3 Section 14) |
| **Not allowed without SteerCo approval on Panel advice** | Re-baselining, changing a KPI definition, baseline, target or analysis method | Charter Section 20, risk 8 |

### 11.2 Course-correction log (complete at Month 18)

| ID | Finding behind it | Proposed correction | Class | Effect on evidence or baseline | Owner | Decision body | Due | Verification |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| CC-01 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| CC-02 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

### 11.3 Evidence still at risk

| Item | Question | Response |
| --- | --- | --- |
| Validated controlled data | Will each site reach at least 12 months of validated controlled data by Month 24? | [Yes / No, forecast]. If not, the stop-or-extend rule applies with Panel advice (C3 Section 14) |
| Seasonal coverage | Does the series cover the seasons that drive tariffs, load and diesel use? | [ ] |
| Pilot B loss separation | Is it defensible? | [ ] |
| Pilot C unconstrained demand | Is the reconstruction defensible? | [ ] |

## 12. Gate 4 decision framework

The SteerCo decides to **confirm continued operation**, **continue with corrective action**, or, in extremis, **reduce or stop a site**. A stop at Gate 1 was a legitimate outcome and a well-evidenced negative finding remains a legitimate research result (Charter Section 16).

| Decision input | Question | Evidence in E1 |
| --- | --- | --- |
| Safety | Any open safety-critical item or unresolved P1 or P2? | Section 5.2, D5 |
| Evidence | Is validated data on course for 12 months per site? | Section 11.3 |
| Performance | Where do KPIs stand against targets and the range, with uncertainty? | Sections 6 and 7 |
| Economics | Do break-even conditions look reachable on replication cost? | Section 8 |
| Security | Open critical or high findings, accepted risks? | B7 indicators, D5 |
| Capacity | Two competent operators per site, retention to date? | D4 |
| Regulatory | Any formal proposal or approval change affecting the pilot? | Regulatory log |
| Spend | Forecast against tolerance, contingency use? | C2 |

| Recommendation | When used |
| --- | --- |
| Continue as planned | No open safety-critical items, evidence on course, no unresolved trigger |
| Continue with corrective action | One or more triggers fired or a lens rated weak, with a correction that protects the experiment |
| Re-plan a site | A site cannot reach 12 months of validated data, or a safety, regulatory or community condition cannot be met. SteerCo decision on reserve site, extension or reduced scope |
| Stop a site or the programme | A critical, unresolvable safety or integrity problem. Recorded as a research finding |

A recommendation is drafted by the Programme Director on Panel advice and decided by the SteerCo.

## 13. Lessons learned

| Theme | Questions |
| --- | --- |
| Compatibility and integration | Which devices behaved as tested, which did not, and what did custom drivers cost? |
| Commissioning | What slipped, why, and what would be done differently? |
| Operations | Which faults repeated, repair times, spares, what operators found hard |
| Security | Findings, incidents, hardening gaps, what the audit missed |
| Community and users | Complaints, acceptance, throttling reactions, supply continuity |
| Economics | Where bills, diesel, reliability and asset protection actually paid |
| Regulation | Where licensing, net-metering or interconnection created delay or doubt |

Lessons feed the replication guide (E3) and the Gate 3 and Gate 5 lessons-learned reviews (Charter Section 23). Negative lessons carry equal prominence.

## 14. Publication and disclosure

| Item | Rule |
| --- | --- |
| Review chain | Independent reviewer, Panel accuracy check, Cybersecurity Officer security and privacy review, then Programme Director approval (Charter Section 21, D2 Section 10) |
| Directly involved parties | Hosts, Kenya Power, EPRA and communities see findings before public release. Hosts and partners may comment for [14] days but cannot require changes to findings. Publication may be delayed by up to [60] days only for personal data, security or a legitimate legal interest (MoU Section 10) |
| Public version | An aggregated data summary is published after Gate 4 (D1 Section 13), with plain-language English and Kiswahili summaries |
| Disclosure thresholds | No figure based on fewer than [k] customers, sessions or vehicles. Household data only at feeder or transformer-group level. Charger data only at hourly or session-distribution level. Host commercial data only with consent, but aggregated results cannot be blocked |
| Withheld | Credentials, live network details, unpatched vulnerabilities, personal data |
| Language | States that this is a research pilot and results are measured, not guaranteed. No promises on tariffs, jobs or supply. Vendors make no performance claims from E1 without Research Lead approval |

## 15. Structure of the Month 18 report

| Section | Content |
| --- | --- |
| Cover | Report ID `E1-[YYYY-MM]`, status, authors, reviewer, Panel validation reference |
| 1. Summary | One page: what the data shows, what it does not show, the Gate 4 recommendation |
| 2. Evidence base | Data window, quality, mode and configuration (Sections 4 and 5) |
| 3. KPI results | Per site, with uncertainty (Section 6) |
| 4. Range comparison | Trigger test and result (Section 7) |
| 5. Economics | Updated model outputs (Section 8) |
| 6. Diagnosis | Mechanism and confounders (Section 9) |
| 7. Interim scorecard | Five lenses (Section 10) |
| 8. Course corrections | Log and evidence at risk (Section 11) |
| 9. Gate 4 recommendation | Decision framework outcome (Section 12) |
| 10. Lessons | Section 13 |
| 11. Limits | What Month 18 cannot tell us |
| Annexes | Monthly series, data dictionary link, mode records, change and incident extract, restatement log, sign-off |

## 16. Schedule

| Activity | Months | Output | Gate |
| --- | --- | --- | --- |
| Agree E1 structure, trigger test and "trending below" rule with the Panel | 6 to 8 | Pre-registered rules | Gate 2 |
| Dry-run E1 template on lab or baseline data | 10 to 12 | Tested template | Gate 3 |
| Monthly validated reports feed the E1 series | 13 to 18 | MR-1 to MR-3 | |
| Quarterly SteerCo report with early trend view | 15 | Extended MR-2 | |
| Data cut-off, analysis, diagnosis | 17 to 18 | Draft E1 | |
| Independent review, Panel validation, security and privacy review | 18 | Validated E1 | |
| Gate 4 SteerCo review | 18 | Decision, correction log | **Gate 4** |
| Public aggregated summary | After Gate 4 | Published summary | |

| Gate | Evidence from E1 |
| --- | --- |
| Gate 2 | Pre-registered structure, trigger rule and decision framework approved with the M&V protocol |
| Gate 3 | E1 template tested on dry-run data |
| Gate 4 | Validated E1 with six months of data, uptime, KPI trends against targets and the 15 to 30% range, correction log, recommendation |
| Gate 5 | E1 findings and corrections carried into E2, E3 and E4 |

**Critical path.** E1 depends on commissioning by Month 12 and validated data from Month 13. Late commissioning shortens the interim window. If a site has fewer than [x] validated months at cut-off, E1 reports that site as "insufficient data" and does not interpolate.

## 17. Risks to add to the live Risk Register

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| IE1 | Interim window too short or unrepresentative, so results are over- or under-read | M | H | Interim label, seasonal adjustment, uncertainty, no extrapolation without stated method | Research Lead |
| IE2 | Pressure to soften, delay or reframe poor interim results | M | H | Pre-registration, equal prominence, MoU Section 10 limits, independent reviewer | Programme Director |
| IE3 | Corrections made that quietly alter the baseline or targets | L | H | Section 11.1 rules, SteerCo approval, change log visible to the Panel | Research Lead |
| IE4 | Early results read as promises by hosts, funders or communities | M | M | Research-pilot wording, plain-language summary, briefings | Programme Manager |
| IE5 | A site holds too little validated data at Month 18 | M | H | Early baseline start, stop-or-extend rule, backup sites | Programme Director |
| IE6 | Interim trigger fires and prompts premature stop decisions | L | H | Diagnosis order, Panel advice, evidence on data and economic conditions before conclusions | Steering Committee |
| IE7 | Disclosure of personal or commercial data in interim publication | L | H | k threshold, release clearance, host review | Cybersecurity Officer |
| IE8 | Analyst or university capacity gap at cut-off | M | M | Named backup analyst, documented code, student support | Research Lead |

These risks are to be merged into the live Risk Register (README A6).

## 18. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Define "trending below the range" numerically (Section 7.1, step 4) | Gate 2 | Panel |
| 2 | Fix minimum validated months and completeness threshold for a reportable interim KPI | Gate 2 | Panel |
| 3 | Agree seasonal adjustment method for interim and annualised estimates | Gate 2 | Research Lead, university partner |
| 4 | Set status thresholds (Watch, Off track) for interim reading | Gate 1 | Panel, Programme Director |
| 5 | Decide how control-off weeks, if used, appear in interim results | Gate 2 | Research Lead |
| 6 | Agree how failed changes and incidents are summarised publicly | Gate 3 | Research Lead, Cybersecurity Officer |
| 7 | Decide the independent reviewer for E1 | Gate 3 | Programme Director |
| 8 | Itemise E1 costs: analyst time, university budget, translation, publication | Gate 1 | Programme Manager |
| 9 | Name the custodian of the interim series and archive | Gate 5 | Programme Sponsor |

## 19. Immediate next steps

1. Panel and TWG to review this structure, including the Kenya Power grid engineer on feeder and transformer interpretation.
2. Research Lead to include the trigger test and decision framework in the pre-registered analysis plan (D1) before any controlled data exists.
3. Data analyst to build the E1 pipeline and template on lab data and test it in the D6 dry runs.
4. Agree with the Programme Director who presents E1 and the independent reviewer.
5. Draft the plain-language and Kiswahili interim summary template with the engagement lead.
6. Itemise E1 costs in the budget reconciliation.
7. Add risks IE1 to IE8 and the open items to the PMO log and Risk Register.

---

# Appendix A: Gate 4 evidence checklist

| # | Requirement (Charter Section 16 and gate tables) | Evidence | Owner | Done |
| --- | --- | --- | --- | --- |
| 1 | Six months of validated data per site | MR-1 Months 13 to 18, Panel validation notes | Research Lead | [ ] |
| 2 | Uptime results | K4 with cause breakdown | Data analyst | [ ] |
| 3 | Early KPI trends with uncertainty | Section 6 | Research Lead | [ ] |
| 4 | Trend against the 15 to 30% range, trigger test applied | Section 7 | Research Lead | [ ] |
| 5 | Incident and change summary, drift and failed-change review | D5 monthly summaries | Technical Lead | [ ] |
| 6 | Patch and firmware change review, compatibility problems in operation | D5, B6 | Technical Lead | [ ] |
| 7 | Security log and incident summary, access review, restore test repeated | B7 indicators | Cybersecurity Officer | [ ] |
| 8 | Meter accuracy rechecked | D1 Section 8.2 | Research Lead | [ ] |
| 9 | Safety summary, inspections, drill repeat, residual risks | C6, D3 | Site Leads | [ ] |
| 10 | Training: attended, competent, retained, two-per-site rule | D4 | Capacity-building lead | [ ] |
| 11 | Spend, forecast, contingency use | C2 | Finance lead | [ ] |
| 12 | Techno-economic update | Section 8 | Techno-economic analyst | [ ] |
| 13 | Regulatory log reviewed, no unresolved non-compliance | B5 | Programme Director | [ ] |
| 14 | Course-correction log and decision recommendation | Sections 11 and 12 | Programme Director | [ ] |
| 15 | Independent review and Panel validation recorded | Sign-off | Research Lead | [ ] |

# Appendix B: Interim result block (template, one per KPI per site)

| Field | Entry |
| --- | --- |
| KPI, site, window | [ ] |
| Result, unit | [ ] |
| Counterfactual or baseline, model version | [ ] |
| Difference and interval, method | [ ] |
| Result category | [ ] |
| Target and status | [ ] |
| Position against 15 to 30% range (K3) | [ ] |
| Completeness, exclusions applied | [ ] |
| Mode record and configuration hash | [ ] |
| Mechanism evidence | [ ] |
| Confounders and overrides in the window | [ ] |
| Caveats (season, early months, model fit) | [ ] |

# Appendix C: Gate 4 recommendation sheet

| Field | Entry |
| --- | --- |
| Recommendation (continue, continue with corrective action, re-plan a site, stop) | [ ] |
| Per-site position | A [ ]; B [ ]; C [ ] |
| Triggers fired | [ ] |
| Conditions attached | [ ] |
| Corrections requiring SteerCo approval | [ ] |
| Dissenting views from the Panel or partners | [ ] |
| Presented by and decided by (names, date) | [ ] |

# Appendix D: Sign-off

| Role | Name | Signature | Date |
| --- | --- | --- | --- |
| Data analyst (author) | [ ] | | |
| Research Lead | [ ] | | |
| Independent reviewer | [ ] | | |
| Panel chair (validation) | [ ] | | |
| Cybersecurity and Data Protection Officer (release clearance) | [ ] | | |
| Programme Director | [ ] | | |

# Appendix E: Traceability

| Source | Used for |
| --- | --- |
| Problem Statement | Questions Q1 to Q5 and the central question |
| Programme Charter (Sections 7, 15, 16, 18, 20, 21, 23) | KPIs, Gate 4 evidence and decision, escalation trigger, change control, independence, evaluation rules |
| Feasibility Study (Sections 5.4 to 5.6, 12) | Metrics, break-even logic, replication cost, scorecard lenses |
| Monitoring and Evaluation Plan (Sections 3, 6 to 9, 11 to 14, Appendices A, B) | KPI dictionary, modes, baseline, quality checks, decision rules, reporting |
| Monthly Performance Reports (Sections 5, 8 to 12, 14) | Source series, status scheme, data quality block, disclosure |
| Incident and Change Log (Sections 6, 12, Appendix C) | Incident and change summary, confounders, drift |
| Operations and Maintenance Manual (Sections 15, Appendix E) | Uptime, repair times, site reports |
| Training Materials and Attendance Records (Sections 14.3, 15) | Attended, competent, retained |
| OpenEMS Configuration Baseline (Sections 6.6, 9, 10) | Mode records, hashes, change classes |
| Data Management and Privacy Plan (Sections 8 to 10, 12) | Access, disclosure thresholds, release process |
| Stakeholder Engagement Plan (Sections 11, 13, 15) | Complaints, indicators, disclosure before publication |
| MoU and Site Agreement templates (MoU Section 10; Site Agreement 9.3) | Publication rights, host comment limits |

On completion of the Gate 1 and Gate 2 decisions (targets, thresholds, trigger rule, seasonal method) and the first dry runs, each bracketed value is updated and this document is re-issued as version 1.0 for Gate 2. The completed report is issued at Month 18 for Gate 4.

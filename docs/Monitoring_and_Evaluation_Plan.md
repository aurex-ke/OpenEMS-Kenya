# Monitoring and Evaluation Plan

## 1. Purpose and bottom line

The programme exists to produce the first locally validated evidence of OpenEMS performance in Kenya (Charter Section 3). The international savings range of 15 to 30% is a hypothesis, not a promise. This plan defines how that hypothesis is tested: what is measured, where, how often, against which baseline, with what uncertainty, and how results become the answers to the central research question and the five supporting questions.

**Bottom line.** The evaluation is only as credible as its baseline and its measurement chain. Eight rules follow:

1. **Baseline first, control second.** Each site runs in monitoring-only mode (M1, storage idle or unmanaged) before controllers are enabled (M2). Control modes switch only on the signed schedule in Section 7 (B4 design rule 7, C4 Section 6.6).
2. **Two views that agree.** Control-system data from the Edge and independent research-grade meters on a separate logger must reconcile. A KPI is reported from the independent view and checked against the Edge view (B4 Section 3.4).
3. **Counterfactual, not before-and-after.** Savings are measured against a weather-, load- and tariff-adjusted counterfactual, not a raw comparison of two periods.
4. **Uncertainty is part of every result.** Every KPI is reported with its uncertainty and its limitations (Charter Section 23).
5. **No re-baselining without Panel approval.** Any change to a baseline, KPI definition or analysis method after Gate 1 needs SteerCo approval on Panel advice (Charter Section 20, risk 8).
6. **Independence.** The Research Lead reports without editorial control by suppliers, hosts or funders. Vendors never analyse their own device's performance (Charter Section 21).
7. **Negative results count.** Shortfalls against the 15 to 30% range, failed tests and inconclusive results are published with equal prominence. A stop or no-go finding is a legitimate outcome (Charter Section 16).
8. **Honest limits.** Pilot B loss separation and Pilot C delay effects are hard to measure. Where a claim is not defensible, the report says so (Section 10).

**What cannot be settled from desk research.** No site is selected, surveyed or instrumented, and no baseline data exists. Tariff structure, load shape and metering coverage will change the detail. Numeric KPI targets are therefore **not set here**. They are set after baseline data is in and frozen at Gate 1 (Charter Section 7, Feasibility Study recommendation 7).

## 2. Document control and relationships

**Owner:** Research Lead (README D1, "M&E / data analyst"). **Contributors:** university partner, data analyst, Technical Lead, software engineer, Cybersecurity and Data Protection Officer, Kenya Power grid engineer (TWG), Site Leads, PMO. **Approval:** the Research and Evaluation Panel approves the method before data collection starts (Charter Section 19). The Programme Director presents it at Gate 1. The M&V protocol in Section 7 is frozen at Gate 2. Changes follow Charter Section 20.

| Document | Relationship |
| --- | --- |
| Problem Statement | Source of the central question and five supporting questions this plan answers |
| Programme Charter (Sections 7, 15, 16, 20, 21, 23) | KPI list, baseline rule, dashboard, gates, tolerances, independence, evaluation requirements |
| Feasibility Study (Sections 5.3 to 5.6, 12, Appendix B) | Benefit mechanisms, evaluation metrics, break-even logic, open questions |
| Technical Specification (B4, Sections 3.4, 5 to 7) | Measurement points, resolutions, loss-measurement design, acceptance tests A9, A10, B7, B10, C5 |
| Interoperability Register (B6) | Meter accuracy tests T-MTR, charger log quality test T-EVC-08, round-trip efficiency test T-BAT-07 |
| OpenEMS Configuration Baseline (C4, Sections 6.6, 9) | Operating modes M0 to M4, signed mode records, drift detection, change log to the Panel |
| Site Acceptance Tests (C5, Sections 10, 11) | Baseline readiness checks BR-1 to BR-7 |
| Cybersecurity Plan (B7, Sections 6.6, 6.10) | Log integrity, pseudonymisation, retention, evidence trail |
| Regulatory Compliance Assessment (B5, Sections 5.6, 5.9) | Data protection, NACOSTI and ethics approvals |
| MoU and Site Agreement templates (MoU Schedule 1C, Site Agreement 6.2, 9, Pilots A to C) | Baseline and test periods, benefit sharing, data roles, publication rights |
| Data management and privacy plan (D2) | Retention, access and anonymisation rules this plan relies on |
| Monthly performance reports (D6), Interim and final evaluation reports (E1, E2), Policy brief (E4), Replication guide (E3) | Outputs this plan produces |
| Techno-economic model (B2) | Receives measured inputs and is validated against measured results |

## 3. Evaluation questions and design

### 3.1 Questions and evidence

| # | Supporting question (Problem Statement) | Pilots | Primary evidence | Main KPI |
| --- | --- | --- | --- | --- |
| Q1 | How effectively can battery dispatch under OpenEMS smooth VRE variability and reduce peak demand? | A, B, C | Interval import at the grid connection, battery power, PV output | Peak grid import reduction; ramp-rate of net import |
| Q2 | How much can locally controlled solar-plus-storage microgrids reduce technical and commercial losses? | B | Feeder energy balance, check meters, voltage logs | Loss reduction on served customers |
| Q3 | What bill savings and payback are achievable under ToU tariffs and the 50% net-metering credit? | A (B, C where tariffs apply) | Bills, tariff schedule, meter data, cost data | Bill savings (KSh); payback and NPV under measured savings |
| Q4 | Can OpenEMS EV cluster controllers prevent transformer overload without unacceptable charging delays? | C | Transformer loading, charger session logs | Transformer loading; share of time at full capacity; wait time |
| Q5 | What regulatory, cybersecurity, maintenance and capacity risks must be managed? | All | Risk register, incident and change log, training records, regulator correspondence | Uptime; incidents; operators trained and retained |

The **central question** (technical, economic and institutional viability) is answered by combining Q1 to Q5 in the final report with the scorecard in Section 12.

### 3.2 Design

The design is a **within-site, baseline-versus-controlled comparison** with a counterfactual model, supplemented where the Panel judges it feasible by **short alternating periods** of control on and off (Section 7.3). There is no separate control site. With three heterogeneous sites, results are reported per site and are not averaged into a single national estimate. Claims about wider replication are stated as hypotheses supported by the break-even conditions in the techno-economic model (Feasibility Study Section 5.6).

### 3.3 Reference framework

The Panel may use the structure of recognised measurement and verification guidance (for example IPMVP options for whole-facility metering with a regression baseline) as a checklist, not as a certification goal. The auditor or Panel confirms the reference set in the M&V protocol \[confirm\].

## 4. Principles

| Principle | What it means in practice |
| --- | --- |
| Evidence first | Decisions rest on measured data. International figures remain hypotheses until validated locally (Charter Section 12) |
| Measure once, define once | Every KPI has one definition, one formula and one data source in the KPI dictionary (Appendix A). Definitions freeze at Gate 1 |
| Independence of measurement | Research meters and logger are separate from the control system, with their own time source and access roles |
| Pre-registration | The analysis plan, KPI definitions and decision rules are written and approved **before** controlled-mode data is seen |
| Transparent uncertainty | Meter error, model error and period effects are carried through to the reported result |
| Proportionate | Measurement effort scales with what each site must answer. Pilot B loss work is heavier than Pilot A bill work |
| Privacy by design | Household and driver data are pseudonymised at source and aggregated before publication (B7 Section 6.10) |
| Open by default | Method, code, anonymised data and findings are published after the Panel accuracy check and the security and privacy review |
| Honest reporting | Failed tests, gaps, rollbacks and null results appear with equal prominence |

## 5. Roles and responsibilities

| Role | Responsibility in M&E |
| --- | --- |
| Steering Committee | Approves KPI targets and baselines at Gate 1, any later change, and publication (Charter RACI) |
| Programme Director | Accountable for KPI approval route and publication. Presents Panel advice to the SteerCo |
| Research and Evaluation Panel | Approves the M&V protocol, meter locations, baseline method and start, analysis plan and validated KPI reports. Meets monthly in operation |
| Research Lead | Owns this plan and the integrity of reported results. Reports independently to the Panel |
| Data analyst (M&E) | Runs the data pipeline, quality checks, baseline models and monthly KPI reports |
| University partner | Designs the M&V protocol, validates monthly data, runs the independent savings analysis, co-authors the final report (MoU Schedule 1C) |
| Technical Lead and software engineer | Provide Edge data, mode records, configuration hashes and change logs. Do not alter research data |
| Cybersecurity and Data Protection Officer | Log integrity, pseudonymisation, access roles, retention, publication review |
| Site Leads and operators | Keep site logs: outages, maintenance, load changes, overrides. Protect meters and seals |
| Kenya Power grid engineer | Supplies feeder and transformer data and advises on meter and loading interpretation |
| EPRA observer | Observer on the Panel. May review draft findings |
| PMO | Reports KPIs on the monthly dashboard and tracks M&E risks and actions |
| Host representatives | Provide bills, tariff documents and notice of operational changes. Cannot alter research meters |

## 6. KPI framework

The Charter lists six KPIs. Numeric targets are placeholders until Gate 1. The table gives the definition and the pilots it applies to. Full formulas, units, sources and exclusion rules are in the KPI dictionary (Appendix A).

| ID | KPI (Charter Section 7) | Applies to | Short definition | Target |
| --- | --- | --- | --- | --- |
| K1 | Peak grid import reduction (kW and %) | A, B, C | Reduction in adjusted peak import from baseline to controlled mode, over defined peak windows | \[Gate 1\] |
| K2 | Renewable self-consumption ratio | A, B | Share of PV energy used on site, directly or through the battery | \[Gate 1\] |
| K3 | Bill savings (KSh), compared with the 15 to 30% international range | A, B | Counterfactual bill minus actual bill, same tariff, same period | \[Gate 1\] |
| K4 | System uptime and availability | A, B, C | Share of time the Edge and the controlled assets are available and under control | \[Gate 1\] |
| K5 | Transformer loading (kW) and share of time chargers operate at full capacity | C | Peak and distribution of transformer loading, and share of charging time at requested power | \[Gate 1\] |
| K6 | Technical and commercial loss reduction on served customers | B | Change in the feeder loss fraction after normalisation | \[Gate 1\] |

### 6.1 Supporting indicators

These do not replace KPIs. They explain them and feed the techno-economic model.

| Group | Indicator | Use |
| --- | --- | --- |
| Technical | Battery round-trip efficiency, depth of discharge, cycles, state of health where reported | Model input, degradation, T-BAT-07 |
| Technical | Export limit compliance, number of setpoint clamps and rejects, safe-state events | Safety and control quality |
| Technical | Diesel energy and fuel displaced (Pilot B), generator run hours | Diesel offset benefit |
| Technical | Voltage at feeder end and transformer secondary, outage count and duration (Pilot B) | Reliability and loss interpretation |
| Economic | Annual net benefit, simple payback, NPV, cost per kW of peak reduced, levelised cost of stored energy | Feasibility Study Section 5.4 |
| Economic | Pilot cost and replication cost (excluding research overhead) | Commercial viability on replication cost |
| EV | Waiting time per session, number of throttled sessions, complaints, energy delivered | Delay without unacceptable effect (Q4) |
| Institutional | Operators trained, assessed competent and retained; regulator or utility adoption of the model or register | Charter programme-level success |
| Engagement | Participation and acceptance indicators (Stakeholder Engagement Plan Section 13) | Social viability |
| Data | Completeness, gap hours, meter accuracy checks passed, drift alarms | Quality of evidence |

## 7. Baseline and M&V protocol

### 7.1 Baseline principle

The Charter defines the baseline as **storage idle or unmanaged**. The baseline is a measured period in mode M1, extended by a statistical model that predicts what import, cost or loss would have been under controlled-mode conditions had control not been applied.

### 7.2 Operating modes and the mode schedule

Modes are defined in C4 Section 6.6 and are recorded in signed mode records.

| Mode | Name | Use in evaluation |
| --- | --- | --- |
| M0 | Commissioning | Excluded from baseline and operating datasets |
| M1 | Monitoring only | **Baseline data.** Battery idle or unmanaged, all controllers off |
| M2 | Controlled | **Controlled data.** Controllers enabled in the agreed sequence |
| M3 | Fallback or fault | Flagged. Excluded from savings, analysed separately for uptime and safety |
| M4 | Maintenance | Flagged. Excluded from savings and uptime denominators as the protocol states |

**Schedule rule.** Entry to M1 and M2 is approved by the Panel. Each switch is a scheduled event with date, time, configuration tag and hash.

### 7.3 Baseline length and test pattern (open decision)

The baseline must fit before Gate 3 and still leave at least 12 months of validated operating data in Months 13 to 24 (Charter Section 7, C3 Section 14, C5 BR-7). The Panel must fix this before Gate 2. The options below are for decision, not a recommendation.

| Option | Description | Strength | Weakness |
| --- | --- | --- | --- |
| 1 | Short pre-control baseline (weeks), then continuous control, with a counterfactual model fitted on pre-period plus historical host data | Preserves 12 months of controlled data | Seasonal coverage depends on historical data. Model risk |
| 2 | Short baseline, then continuous control, plus **scheduled control-off weeks** (for example \[x\] weeks per quarter) | Gives ongoing within-season comparison and checks model drift | Lost benefit to host in off weeks. Compensation under Site Agreement Schedule 5 |
| 3 | Longer baseline covering a season | Better baseline | Compresses operating period. Conflicts with the 12-month data rule |

Pilot A should use at least \[12\] months of historical interval load and bills where available to fit the model (Feasibility Study Section 10). Pilot B and C rely more on direct comparison and physical balances.

### 7.4 Normalisation and counterfactual models

| Site | Drivers to normalise | Model approach (to be approved by the Panel) |
| --- | --- | --- |
| A | Weather, working days, production schedule, occupancy, PV output, tariff changes | Regression of baseline interval or daily load on drivers. Predict counterfactual import in controlled mode. Re-price with the actual tariff |
| B | Load growth, season and rainfall, customer numbers, diesel availability, outages | Energy-balance comparison with matched periods. Load model for evening peak. Technical loss from feeder model |
| C | Charger demand pattern, day of week, fleet schedules, number of active chargers | Replay of recorded session demand to estimate unconstrained transformer loading, compared with managed loading |

**Model checks.** Out-of-sample prediction error is reported. Models are refitted only on a schedule approved by the Panel. A model that fails the agreed fit criterion \[x\] is not used for savings claims.

### 7.5 Confounders and change log

Sites keep a log of events that could distort results: new loads, equipment changes, tariff changes, outages, maintenance, holidays and shutdowns, host operational changes, theft or damage. The log links to the C4 change log and the D5 incident log. Where a confounder is large, the affected period is excluded or modelled, and the decision is recorded.

### 7.6 Benefit sharing and behaviour effects

Where the host keeps bill savings (Site Agreement 8.2), the host may change behaviour once savings are visible. Where a benefit-sharing choice is made, its effect on the baseline is noted (C5 BR-6). Host-initiated load changes are recorded and treated as confounders.

## 8. Measurement plan

### 8.1 Measurement points and resolution

Points and resolutions follow B4 Section 3.4. Research meters and the independent logger are approved by the Panel before data collection.

| Point | Quantity | Resolution | Source of record | Used for |
| --- | --- | --- | --- | --- |
| Grid connection (import, export) | kW, kWh | 1 min logged, 15 or 30 min for billing comparison \[confirm tariff interval\] | Research meter | K1, K3, K2 |
| PV generation | kW, kWh | 1 min | Edge, cross-checked with research meter where fitted | K2 |
| Battery AC terminals | kW, kWh, SoC | 1 min | Edge, cross-checked | Efficiency, K1, K3 |
| Key controllable loads (A) | kW | 1 to 5 min | Edge | Load shifting, critical-load protection |
| Generator output and fuel (B) | run hours, kWh, litres | Per run and daily | Edge and site log | Diesel offset |
| Feeder input and check meters (B) | kWh, kW | 15 min or finer | Research meters | K6 |
| Voltage at feeder end and transformer secondary | V | 1 min at least during peak | Research logger | K6, reliability |
| Transformer secondary (C, A and B where possible) | kW, kVA, V | 1 min | Research meter, Kenya Power read access | K5 |
| Charger sessions (C) | start, stop, energy, power, wait | Per session, pseudonymised | Edge | K5, wait time |
| Outages and events | start, end, cause | Event-based | Site log, Edge, Kenya Power | K4, reliability |

### 8.2 Rules for measurement

- Time is synchronised on all loggers to one source, with a drift alarm (B4 Section 3.4, CT-2 in C5).
- Local buffering is at least \[30\] days.
- Meter accuracy checks are done against a reference at \[3\] load points at commissioning and repeated at Gate 4 and before closure (C5 A9, CT-1).
- Meter seals, calibration certificates and serial numbers are recorded. A broken seal flags the affected data.
- Customer-level and driver-level data are aggregated or pseudonymised before leaving the site (B7 Section 6.10).
- The Panel approves meter locations and the accuracy limit before data collection starts (Charter Section 19).

### 8.3 Instrument and data uncertainty

Each KPI carries a combined uncertainty from meter class, sampling, model error and missing data. The method is written in the analysis plan and applied at every monthly report. Where combined uncertainty is larger than the measured effect, the report says the effect is not distinguishable from zero at that site.

## 9. Data management and quality

### 9.1 Data flow

1. **Capture.** Research meters and logger record independently. The Edge records control data.
2. **Buffer and transfer.** Local buffer first. Before Gate 3, data moves by manual or local transfer only. After Gate 3, transfer uses the approved outbound-only encrypted path (B7 Section 6.2). Remote access never alters the baseline or the mode schedule.
3. **Pseudonymise and aggregate** at source where personal data is involved.
4. **Validate.** Automated checks (Section 9.2), then analyst review.
5. **Store.** Raw data is immutable. Cleaned data is derived and versioned. A data dictionary and version-controlled configuration accompany every dataset.
6. **Analyse and report.** Monthly KPI report to the Panel, then the dashboard.
7. **Publish.** Anonymised datasets and code after the Panel accuracy check and the security and privacy review.

### 9.2 Data quality checks

| Check | Rule | Action on failure |
| --- | --- | --- |
| Completeness | Share of expected intervals present per channel and month. Target \[x\]% | Flag. Gap above the agreed threshold is a Charter escalation trigger for Pilot B |
| Range and plausibility | Values within physical limits and device ratings | Flag and investigate |
| Reconciliation | Edge and research meter energy agree within \[x\]%. Energy balance closes at the site | Investigate. Research meter prevails unless faulty |
| Sign and unit | Import and export signs consistent (T-MTR-03) | Correct at source or exclude |
| Time | Drift within \[x\] s | Correct if documented, else flag |
| Mode flag | Each record carries M0 to M4 and configuration hash | Records with missing flag are excluded |
| Seal and calibration | Seals intact, certificates valid | Flag affected period |
| Duplicates and backfill | Late data is merged with a record of what changed | Log the change |

### 9.3 Roles for data access

Access follows Schedule 6 of each site agreement and the data sharing agreements. The Research Lead and analyst hold analysis access. Hosts see their own site data through the OpenEMS UI. Vendors have no access to research data. Kenya Power has read access to pilot feeder data. Utility, university and regulator access is defined in writing before any transfer (MoU Section 7.2).

### 9.4 Ethics, privacy and approvals

Household consumption at Pilot B and session data at Pilot C are personal data under the Data Protection Act, 2019. The university partner confirms NACOSTI and ethics clearance before data collection starts (B5 Section 5.9). Pilot B uses consent and notice at community meetings. Pilot C displays a privacy notice and keeps payment data out of the dataset. Small-group re-identification risk is checked before release, for example few customers on one transformer.

## 10. Pilot-specific evaluation methods

### 10.1 Pilot A: industrial park, hub or campus

| Item | Method |
| --- | --- |
| K1 peak reduction | Adjusted baseline peak minus controlled peak, over tariff-relevant peak windows and over the monthly maximum demand interval. Reported in kW and % |
| K2 self-consumption | (PV generation minus export) divided by PV generation, with battery losses reported separately |
| K3 bill savings | Counterfactual bill (baseline model, actual tariff and the 50% net-metering credit rules as confirmed by EPRA) minus actual bill. Reported in KSh and as % of counterfactual bill, against the 15 to 30% range |
| Mechanism split | Savings split into peak or demand charge, ToU shifting and export-credit effects, so the report shows which mechanism pays |
| Critical loads | Any override of protected loads is logged and reported. Savings are not counted for periods when overrides distorted dispatch |
| Pre-condition | If the host has no meaningful ToU spread or demand charge, the site is a weak economic test. This is reported, not hidden (B4 Section 5.2) |

### 10.2 Pilot B: rural microgrid

| Item | Method |
| --- | --- |
| K6 loss reduction | Energy balance: (energy into the feeder minus energy billed or metered at customers) divided by energy into the feeder, before and after control, normalised for load, season and customer numbers (B4 Section 6.4) |
| Technical versus commercial | Technical loss estimated from feeder data (length, conductor, loading) and measured voltage drop with stated uncertainty. Commercial loss is the remainder. **If separation is not defensible, report total loss change only and say so.** The Panel fixes the method before data collection |
| Metering coverage | Share of customers metered is recorded. Check meters on selected transformers or groups fill gaps |
| K2 and diesel | Self-consumption ratio, diesel energy and fuel displaced using generator kWh, run hours and fuel volume with an agreed manual or automatic method |
| Reliability | Outage frequency and duration before and after, with causes. Supply continuity is checked: no disconnection or price rise from the pilot |
| Caveat | A single feeder with a small customer count gives noisy loss estimates. Results are reported as site evidence, not as a general loss reduction figure |

### 10.3 Pilot C: EV charging site

| Item | Method |
| --- | --- |
| K5 transformer loading | Peak and load-duration curve at the transformer secondary in managed mode, compared with unconstrained demand reconstructed from charger session demand. Time above the agreed threshold is reported |
| Full-capacity share | Share of charging time in which each charger delivers its requested power, per session and in aggregate |
| Delay | Waiting time and extra charging time per session against an unthrottled estimate, with distribution (median, 90th percentile, maximum), against the agreed maximum wait |
| Fairness | Share of energy by customer class under the agreed policy (fair-sharing or priority) |
| Complaints and acceptance | Complaints per 100 sessions, drivers' feedback, fleet operator views |
| Limits of claim | OpenEMS protects the transformer by managing site load behind the connection point, not by controlling utility assets (B4 Section 4.6). Avoided outage or upgrade cost is reported only if the data supports it |

## 11. Techno-economic validation

Measured results are fed back into the techno-economic model (B2) to replace assumptions with evidence.

| Model input | Measured replacement | Timing |
| --- | --- | --- |
| Annual energy bill and tariff spread | Host bills and tariff documents | Baseline |
| Peak reduction and shifted energy | K1, mechanism split | Monthly, then annual |
| Battery efficiency and degradation | Round-trip efficiency, cycles, health | Quarterly |
| Diesel offset | Fuel and run-hour data | Monthly |
| Equipment, integration and O&M cost | Cost tracker (C2) actuals, with pilot cost and replication cost separated | Gate 4 and Gate 5 |
| Export credit | Sensitivity runs at and below 50% | Gate 4 and final |

**Outputs.** Annual net benefit, simple payback, NPV and cost per kW of peak reduced per site. The Charter sensitivities are re-run on measured inputs: battery cost ±20%, discount rate 5 to 12%, export credit below 50% and tariff spread (Charter Section 17). Break-even conditions, not only a point estimate, are reported (Feasibility Study Section 5.6). Using the Feasibility Study logic, a site with USD 100k net capex and an eight-year payback target needs about USD 12.5k net benefit a year. The report states where each site stands relative to its own break-even.

## 12. Decision rules and the scorecard

### 12.1 Interpretation rules (set before data is seen)

| Rule | Detail |
| --- | --- |
| Result categories per KPI | Meets or exceeds target; below target but statistically distinguishable from zero; not distinguishable from zero; negative effect |
| Comparison with the 15 to 30% range | Reported per site with uncertainty. A result below the range is a finding, not a failure of the programme (Charter risk: savings fall short) |
| No selective reporting | All pre-registered KPIs are reported. Added analyses are labelled exploratory |
| Mechanism before magnitude | A saving is credited to OpenEMS only if the mechanism is visible in the data (for example battery discharge in the peak window) |
| Extrapolation | Annual figures from partial years use stated seasonal adjustment and are labelled estimates |

### 12.2 Scorecard for the central question

The final evaluation (E2) rates each lens with evidence, as in the Feasibility Study scorecard.

| Lens | Evidence from this plan | Rating |
| --- | --- | --- |
| Technical | K1, K2, K4, K5, K6, compatibility results, safe-state events | \[to be rated\] |
| Economic | K3, net benefit, payback, break-even conditions on replication cost | \[to be rated\] |
| Regulatory and institutional | Regulator positions obtained, net-metering and licensing outcomes, adoption of model or register | \[to be rated\] |
| Social, environmental, safety | Incident record, complaints, acceptance, participation | \[to be rated\] |
| Delivery and capacity | Schedule, trained operators retained, support without foreign input | \[to be rated\] |

## 13. Reporting and use of results

| Output | Frequency | Audience | Content |
| --- | --- | --- | --- |
| Monthly performance report (D6) | Monthly in operation | Panel, SteerCo, PMO | KPI trends, data quality, mode records, confounders, uncertainty |
| Programme dashboard | Monthly | SteerCo, funders | KPI trends, uptime, incidents, training, spend (Charter Section 15) |
| Panel validation | Monthly in operation | Research Panel | Validated KPI report and data quality notes |
| Interim evaluation (E1) | Gate 4, Month 18 | SteerCo | Six months of validated data, early KPI trends, course corrections |
| Mid-operation public data summary | After Gate 4 | Public, partners | Aggregated results with privacy safeguards |
| Final evaluation (E2) | Months 22 to 24 | Funders, regulators | Answers to central and supporting questions, scorecard, limitations |
| Policy brief (E4) | Month 24 | Ministry, EPRA | Findings on net-metering, BESS and EV rules |
| Replication guide (E3), paper (E6), release package (E5) | Months 22 to 24 | Developers, utilities, academics | Method, results, anonymised data, code |

Host sites, Kenya Power, EPRA and communities receive findings before public release (Stakeholder Engagement Plan Section 15). Hosts may comment on drafts for \[14\] days but cannot require changes to findings. Publication may be delayed by up to \[60\] days only for personal data, security or a legitimate legal interest (MoU Section 10).

## 14. Schedule and gate evidence

| Activity | Months | Output | Gate |
| --- | --- | --- | --- |
| Draft M&V protocol, KPI dictionary, analysis plan | 2 to 4 | Method v0.2 | Gate 1 input |
| Ethics and NACOSTI applications | 1 to 3 | Approvals applied for | Gate 1 |
| Baseline data requests to hosts and Kenya Power | 1 to 3 | Historical data | Gate 1 |
| KPI targets set from baseline data, frozen | 4 to 6 | Approved targets and baselines | **Gate 1** |
| Panel approves meter locations, accuracy limits, baseline length and test pattern | 6 to 8 | Signed M&V protocol | **Gate 2** |
| Measurement chain verified, baseline readiness checks | 10 to 12 | BR-1 to BR-7 complete | Gate 3 |
| Baseline period and start of controlled data | 11 to 13 | Mode records M1, M2 | Gate 3 |
| Monthly validated KPI reports | 13 to 24 | D6 | Gate 4 |
| Interim evaluation | 18 | E1 | **Gate 4** |
| Final evaluation and publication | 22 to 24 | E2, E3, E4, E5, E6 | **Gate 5** |

| Gate | Evidence from this plan |
| --- | --- |
| Gate 1 | Approved method and KPI dictionary. Numeric KPI targets and baselines proposed from data. Ethics and NACOSTI status. Data sharing positions |
| Gate 2 | Signed M&V protocol with baseline length and test pattern. Meter plan and accuracy limits. Analysis plan pre-registered |
| Gate 3 | Baseline readiness complete. Meter accuracy verified. Mode records signed. Data pipeline tested |
| Gate 4 | Six months of validated data. Interim trends against the 15 to 30% range with uncertainty. Meter accuracy rechecked |
| Gate 5 | Final evaluation accepted. Data and code archived. Custodians named |

**Critical path.** Late commissioning shortens the controlled period. If any site is forecast to fall below 12 months of validated controlled data, the stop-or-extend rule in C3 Section 14 applies and the Panel advises on the effect on evidence.

## 15. Risks to add to the live Risk Register

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| ME1 | Baseline too short or unrepresentative, making savings contestable | M | H | Historical data, counterfactual model, off-weeks option, Panel approval | Research Lead |
| ME2 | Baseline integrity disputed because mode switches or changes are undocumented | M | H | Signed mode records, change log to Panel, hash checks | Research Lead |
| ME3 | Meter error or tampering distorts results | L | H | Class limits, seals, repeat accuracy checks, reconciliation with Edge | Research Lead |
| ME4 | Host behaviour change or benefit sharing confounds the comparison | M | M | Confounder log, benefit-sharing note, modelling or exclusion | Research Lead |
| ME5 | Pilot B loss separation not defensible | H | M | Check meters, honest reporting of total loss change | Research Lead |
| ME6 | Data gaps from poor connectivity, power loss or theft | H | M | Local buffering, gap threshold, spares, local operator | Site Lead B |
| ME7 | Savings fall below the 15 to 30% range and results are pressured | M | H | Pre-registration, independence clauses, equal prominence rule | Programme Director |
| ME8 | Privacy breach or re-identification from published data | L | H | Pseudonymisation, aggregation checks, publication review | Cybersecurity Officer |
| ME9 | Ethics or NACOSTI approval delays data collection | M | M | Apply in Months 1 to 3 | Research Lead |
| ME10 | Too little time for 12 months of controlled data | M | H | Stop-or-extend rule, early baseline start, backup sites | Programme Director |
| ME11 | Analyst capacity or university partner availability | M | M | Named backup analyst, student support, documented code | Research Lead |
| ME12 | M&E under-budgeted (meters, check meters, analyst time, audit of method) | M | M | Itemise in the budget reconciliation before Gate 1 | Programme Manager |

These risks are merged into the live Risk Register (README A6). Interim results trending below the 15 to 30% range at Gate 4 are a Charter escalation trigger.

## 16. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Fix baseline length and the control on and off test pattern (Section 7.3) | Gate 2 | Research Lead, Panel |
| 2 | Agree meter class and accuracy limits with Kenya Power | Meter shortlist | Research Lead, Technical Lead |
| 3 | Confirm tariff interval and structure (ToU, demand charges) at Pilot A candidates | Counterfactual pricing | Data analyst |
| 4 | Choose the Pilot B loss-separation method and check meter plan | Before data collection | Research Lead |
| 5 | Set numeric tolerances and fit criteria for models, reconciliation and drift | Gate 2 | Panel |
| 6 | Decide Pilot C unconstrained-demand reconstruction method and maximum wait | Gate 2 | Research Lead, Technical Lead |
| 7 | Confirm NACOSTI licence and ethics route, and data controller roles | Before data collection | University partner |
| 8 | Agree compensation for control-off weeks (if used) | Gate 2 | Site Leads, Programme Manager |
| 9 | Decide how data and code are published and what is withheld | Gate 3 | Research Lead, Cybersecurity Officer |
| 10 | Itemise M&E costs: meters, check meters, analyst, university research budget | Gate 1 | Programme Manager |
| 11 | Name the custodian of the datasets and analysis code after closure | Gate 5 | Programme Sponsor |

## 17. Immediate next steps

1. Panel and TWG to review this method, including the Kenya Power grid engineer on feeder and transformer data.
2. Research Lead to draft the KPI dictionary (Appendix A) and analysis plan, and file them before any controlled-mode data exists.
3. University partner to apply for NACOSTI and ethics clearance in Months 1 to 3.
4. Send baseline data requests to candidate hosts and Kenya Power (Feasibility Study Appendix A).
5. Decide the baseline length options and test pattern for Panel review.
6. Specify research meters, check meters and logger with the Technical Lead for the B6 and procurement packages (P2).
7. Build and test the data pipeline, quality checks and monthly report template on lab data.
8. Add risks ME1 to ME12 and the open items to the PMO log and Risk Register.

## Appendix A: KPI dictionary (template)

| ID | Name | Formula | Unit | Source | Interval | Exclusions | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- |
| K1 | Peak grid import reduction | (Peak\_cf − Peak\_ctrl) ÷ Peak\_cf, where Peak\_cf is the counterfactual peak under baseline behaviour and Peak\_ctrl the measured peak, over \[defined peak windows and monthly maximum\] | kW and % | Research meter at grid connection | 1 min, windowed | M0, M3, M4 periods | Data analyst |
| K2 | Renewable self-consumption ratio | (E\_PV − E\_export) ÷ E\_PV | % | PV and grid meters | 1 min, daily to monthly | M0, M4 | Data analyst |
| K3 | Bill savings | Bill\_cf − Bill\_actual, same tariff, same period | KSh and % | Bills, tariff schedule, meter data | Monthly | Periods with tariff change unless re-priced | Data analyst |
| K4 | System uptime and availability | Hours with Edge running and assets under control ÷ hours in period (excluding M4) | % | Edge status, research logger | Hourly | M4 | Data analyst |
| K5a | Transformer loading | Peak kW and load-duration curve at the transformer secondary, time above threshold | kW, h | Transformer meter | 1 min | M0, M4 | Data analyst |
| K5b | Full-capacity share | Charging time at requested power ÷ total charging time | % | Charger session logs | Per session | Sessions with vehicle-side limits | Data analyst |
| K6 | Loss fraction and reduction | (E\_in − E\_billed) ÷ E\_in, compared baseline versus controlled after normalisation | % | Feeder and check meters, billing | 15 min to monthly | Periods with metering failure | Research Lead |

Each row also holds the data dictionary link, the approved uncertainty method and the Panel approval date.

## Appendix B: Monthly KPI report outline

1. Period covered, mode records and configuration hashes.
2. Data quality summary: completeness, reconciliation, flags, drift alarms.
3. KPI results per site with uncertainty and comparison with target and the 15 to 30% range.
4. Mechanism analysis: what drove the result.
5. Confounders, outages, maintenance and overrides in the period.
6. Supporting indicators and cost updates.
7. Issues, risks and recommended actions.
8. Panel validation note and sign-off.

## Appendix C: Traceability

| Source | Used for |
| --- | --- |
| Problem Statement | Central question and supporting questions Q1 to Q5 |
| Programme Charter (Sections 7, 12, 15, 16, 17, 19, 20, 21, 23) | KPIs, baseline definition, dashboard, gates, sensitivities, tolerances, independence, evaluation requirements |
| Feasibility Study (Sections 5.3 to 5.6, 10, 12, Appendix A and B) | Benefit mechanisms, metrics, break-even logic, data requests, open questions |
| Technical Specification per Site (Sections 3.4, 4.6, 5 to 7) | Measurement points, resolution, loss design, acceptance tests |
| Interoperability Register (Sections 6.2, 11) | Meter, battery efficiency and charger log tests, escalation |
| OpenEMS Configuration Baseline (Sections 6.6, 9, 10) | Operating modes, mode records, drift detection, change classes |
| Site Acceptance Tests (Sections 6.3, 10, 11) | Measurement chain checks, baseline readiness |
| Cybersecurity Plan (Sections 6.6, 6.10) | Log integrity, pseudonymisation, retention |
| Regulatory Compliance Assessment (Sections 5.1, 5.6, 5.9) | Net-metering rules for pricing, data protection, research approvals |
| MoU and Site Agreement templates (MoU 7, 10, Schedule 1C; Site Agreement 6.2, 8.2, 9) | Baseline periods, benefit sharing, data roles, publication rights |
| Stakeholder Engagement Plan (Sections 13, 15) | Engagement indicators, disclosure before publication |

On completion of the site surveys, baseline data collection and the Panel's decisions on baseline length and test pattern, each bracketed value is updated and this document is re-issued as version 1.0 for Gate 2.

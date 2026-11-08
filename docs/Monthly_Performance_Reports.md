# Monthly Performance Reports

## 1. Purpose and bottom line

The Charter requires a monthly dashboard and monthly validated KPI reporting (Charter Sections 15 and 23). The Monitoring and Evaluation Plan (D1) defines what is measured and how. This document (D6) defines the **monthly report set that carries those results to the Panel, the Steering Committee, funders and partners**: what each report contains, who produces and checks it, when it is issued, how uncertainty and data quality are shown, and how it becomes the evidence for Gate 4, Gate 5 and the final evaluation.

**Bottom line.** A monthly report is the unit of evidence. If it is late, unchecked or selectively framed, the final result is contestable. Eight rules follow:

1. **Validated before shared.** No KPI leaves the analyst's desk until the Research and Evaluation Panel has validated it (D1 Section 13). The dashboard shows "provisional" until then.
2. **Independent view first.** KPIs are reported from research-grade meters and the independent logger, and reconciled against Edge data. Where the two disagree, the research meter prevails unless faulty (D1 Section 9.2).
3. **Every number has an uncertainty and a mode.** Each KPI shows its uncertainty, the operating mode record behind it (M0 to M4), the configuration hash and the share of data that is complete.
4. **Same definitions every month.** KPIs follow the frozen KPI dictionary (D1 Appendix A). A change to a definition, baseline or method after Gate 1 needs SteerCo approval on Panel advice (Charter Section 20).
5. **Pre-registered, no selective reporting.** All pre-registered KPIs are reported every month, including when they are poor. Added analyses are labelled exploratory (D1 Section 12.1).
6. **Mechanism before magnitude.** A saving is credited to OpenEMS only where the mechanism is visible in the data (D1 Section 12.1).
7. **Negative and null results have equal prominence.** A shortfall against the 15 to 30% range is a finding. Interim results trending below the range at Gate 4 are a Charter escalation trigger.
8. **Reports do not make promises.** Language states that this is a research pilot, results are measured not guaranteed, and monthly figures are partial-year and seasonal. Vendors, hosts and funders cannot edit findings.

**What cannot be settled from desk research.** Numeric KPI targets, the baseline length, tariff structures, meter classes, the log tool and the dashboard tool are not yet fixed. This document therefore fixes the report set, the production calendar, the review chain, the colour-independent status scheme and the templates, and leaves thresholds as placeholders for Gate 1 and Gate 2.

## 2. Document control and relationships

**Owner:** Data analyst (README D6), under the Research Lead. **Contributors:** Research Lead, university partner, Technical Lead, software engineer, Cybersecurity and Data Protection Officer, Site Leads, Capacity-building lead, Programme Manager and PMO, finance lead, Kenya Power grid engineer (TWG). **Approval:** report structure approved by the Panel and Programme Director at Gate 1, templates and calendar frozen at Gate 2, first report issued for Month 13. Reviewed at the first three reports and then at each gate. Changes follow Charter Section 20.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 7, 15, 16, 20, 21, 23) | KPI list, dashboard content, gate evidence, change control, publication governance, evaluation requirements |
| Monitoring and Evaluation Plan (D1, Sections 6 to 9, 12, 13, Appendices A and B) | KPI dictionary, modes, data quality checks, decision rules, monthly report outline that this document expands |
| Data Management and Privacy Plan (D2, Sections 8 to 10) | Access matrix, disclosure rules, minimum group size, release process |
| Operations and Maintenance Manual (D3, Sections 15, Appendix E) | Monthly site report from the site team, which is an input here |
| Training Materials and Attendance Records (D4, Sections 14.3, 15) | Attended, competent and retained figures, shown separately |
| Incident and Change Log (D5, Section 12, Appendix C) | Monthly summary of incidents, changes, confounders and drift |
| OpenEMS Configuration Baseline (C4, Sections 6.6, 9) | Mode records, hashes, drift reports |
| Site Acceptance Test Reports (C5, Section 10) | Baseline readiness and start of monthly reporting |
| Health, Safety and Environmental Plan (C6, Section 18) | Safety indicators |
| Cybersecurity Plan (B7, Section 12.3) | Security indicators |
| Budget and cost tracker (C2) | Spend against budget, contingency use |
| Risk Register (A6) | Top risks and trigger status |
| Stakeholder Engagement Plan (Sections 11, 13) | Complaints, participation and acceptance indicators |
| Techno-economic model (B2) | Receives measured inputs. Provides break-even position |
| Interim evaluation (E1), Final evaluation (E2), Policy brief (E4), Replication guide (E3) | Built from the monthly series |

## 3. Principles

| Principle | What it means in practice |
| --- | --- |
| Evidence first | Reports state what was measured. International figures remain hypotheses until validated locally (Charter Section 12) |
| One definition | KPIs, formulas, exclusions and units come only from the KPI dictionary |
| Traceable | Each figure links to a dataset version, a mode record, a configuration hash and a data-quality note |
| Proportionate | Detail scales with audience. The SteerCo sees a short dashboard, the Panel sees the full technical report |
| Plain language | Summaries are readable by non-specialists, with Kiswahili summaries for community-facing versions |
| Honest limits | Partial-year effects, noisy Pilot B loss estimates and model error are stated in the report, not in a footnote nobody reads |
| Open by default | Aggregated results, method and code are published after review. Personal and security-sensitive data are not |
| Colour is never the only signal | Status uses words and symbols as well as colour |
| Timely | A late complete report is worse than an on-time provisional one, so both stages exist (Section 6) |

## 4. Scope

**In scope.** The monthly report set from Month 13 (first month of controlled and validated operation) to Month 24, plus a pre-start dry run on lab or baseline data in Months 11 and 12. Content covers KPIs K1 to K6, supporting indicators, data quality, mode records, confounders, operations, safety, security, training, engagement, spend, risks and gate readiness.

**Out of scope.** The interim and final evaluation reports (E1, E2), which draw on this series but have their own structure. Site-level logbooks and service reports (D3), which feed this series. Budget and contract management documents (C2). Public communication beyond the aggregated releases in Section 12.

## 5. Report set

Four products come out of each monthly cycle. They share one data source and one set of numbers.

| ID | Product | Audience | Length (proposal) | Content |
| --- | --- | --- | --- | --- |
| MR-1 | **Site KPI report** (one per pilot) | Research and Evaluation Panel, Technical Lead, Site Lead | [6 to 10] pages | Full KPI results with uncertainty, mechanism analysis, data quality, mode and confounder detail, supporting indicators |
| MR-2 | **Programme performance report** | Programme Director, PMO, TWG | [4 to 6] pages | Cross-site summary, delivery against milestones, operations, safety, security, training, engagement, spend, risks and change |
| MR-3 | **Programme dashboard** | SteerCo, funders | [1 to 2] pages | Charter dashboard items with trend and status |
| MR-4 | **Plain-language summary** | Hosts, communities, drivers, partners, public (after review) | [1] page, English and Kiswahili | What the pilot did this month, in aggregate, with honest caveats |

Quarterly, MR-2 is extended into the **SteerCo quarterly report** (Charter Section 15). At Gate 4 the twelve-month series is consolidated into the interim evaluation (E1).

## 6. Production cycle and calendar

Working days (WD) are counted from the first working day after month end. All dates are proposals for Gate 2.

| Step | Owner | Due | Output |
| --- | --- | --- | --- |
| 1. Data cut-off and lock of raw monthly dataset with checksum | Data analyst | WD 2 | Immutable raw set |
| 2. Automated quality checks and reconciliation (D1 Section 9.2) | Data analyst | WD 3 | Quality log, flags |
| 3. Operations, incident, change, training and engagement inputs received | Site Leads, Technical Lead, Capacity-building lead, PMO | WD 4 | D3 monthly site reports, D5 summary, D4 figures |
| 4. KPI computation and uncertainty (provisional) | Data analyst | WD 6 | Draft MR-1 |
| 5. Analyst and Research Lead review. Independent check of a sample of calculations | Research Lead, second analyst | WD 8 | Reviewed MR-1 |
| 6. **Provisional dashboard** to PMO, marked "provisional" | PMO | WD 8 | Provisional MR-3 |
| 7. Panel validation meeting (monthly, Charter Section 15) | Panel | WD [10] | Validation note, data quality notes |
| 8. Security and privacy check of anything to be shared beyond the Panel | Cybersecurity Officer | WD [11] | Release clearance |
| 9. Final MR-1, MR-2, MR-3 issued | Research Lead, Programme Manager | WD [12] | Validated set |
| 10. Plain-language summary issued after Programme Director approval | Programme Manager | WD [15] | MR-4 |

**Late-data rule.** Data arriving after the cut-off goes into the next month with a restatement note for the affected month. A restated figure is shown with the original and the reason. Restatements are counted as a quality indicator.

**Missed-deadline rule.** If validation slips, the provisional dashboard is still issued on time and the delay is stated. Provisional figures are never used for a gate decision.

## 7. Roles and responsibilities

| Role | Responsibility in monthly reporting |
| --- | --- |
| Steering Committee | Receives the dashboard monthly and the quarterly report. Decides on escalations and any KPI or baseline change |
| Programme Director | Accountable for reporting integrity. Approves release of MR-4. Presents Panel advice to the SteerCo |
| Research and Evaluation Panel | Validates MR-1 each month. Records data quality notes. Approves any method or baseline change advice. EPRA observer may review drafts |
| Research Lead | Owns MR-1 content and the integrity of reported results. Reports independently to the Panel |
| Data analyst (D6 owner) | Runs the pipeline, computes KPIs, produces all four products, keeps the restatement log |
| Second analyst or university partner | Independent check of calculations and model fits (MoU Schedule 1C) |
| Technical Lead and software engineer | Supply Edge data, mode records, hashes and change summaries. Do not alter research data |
| Cybersecurity and Data Protection Officer | Release clearance, disclosure-risk check, security indicators |
| Site Leads and operators | Supply the D3 monthly site report, confounder and override logs on time |
| Capacity-building lead | Supplies training and retention figures (D4) |
| Programme Manager and PMO | Assemble MR-2 and MR-3, track actions, schedule and spend, risk and change summaries |
| Finance lead | Spend, forecast and contingency figures (C2) |
| Kenya Power grid engineer | Supplies feeder and transformer data and advises on interpretation |
| Hosts and vendors | Provide bills and tariff documents (hosts). Have no role in analysis or editing of findings (vendors) |

## 8. KPI content of MR-1

The six Charter KPIs are reported every month for the pilots they apply to. Definitions, formulas and exclusions are in D1 Appendix A. This section sets how they are **presented**.

| ID | KPI | Pilots | Monthly presentation |
| --- | --- | --- | --- |
| K1 | Peak grid import reduction (kW and %) | A, B, C | Counterfactual peak, measured peak, reduction, over defined peak windows and the monthly maximum interval. Uncertainty band |
| K2 | Renewable self-consumption ratio | A, B | Ratio, with battery losses shown separately. Month and cumulative |
| K3 | Bill savings (KSh and %) vs the 15 to 30% range | A, B | Counterfactual bill, actual bill, saving in KSh and as % of counterfactual, split by mechanism (peak or demand charge, ToU shifting, export credit). Position against the range with uncertainty |
| K4 | System uptime and availability | A, B, C | Hours under control divided by hours in period excluding M4. Breakdown by cause (device, link, power, maintenance, safe state) |
| K5 | Transformer loading and full-capacity share | C | Peak kW, load-duration curve, time above threshold, share of charging time at requested power. Wait-time median, 90th percentile and maximum against the agreed limit |
| K6 | Loss fraction and reduction | B | Loss fraction (input minus billed over input), change against baseline after normalisation, with technical and commercial split only if defensible. Otherwise total loss only, and the report says so |

### 8.1 Standard KPI block (one per KPI per site)

Every KPI appears in the same block so that months can be compared.

| Field | Content |
| --- | --- |
| Result this month | Value, unit |
| Counterfactual or baseline value | Value, model version |
| Difference and uncertainty | Value with interval, method reference |
| Result category | Meets or exceeds target; below target but distinguishable from zero; not distinguishable from zero; negative effect (D1 Section 12.1) |
| Target | [From Gate 1], or "not yet set" |
| Cumulative and rolling 3-month | Value |
| Data completeness for this KPI | % of expected intervals, gap hours |
| Mode record and hash | M1 or M2, configuration tag |
| Exclusions applied | M0, M3, M4 periods, confounders excluded or modelled |
| Mechanism evidence | What in the data shows OpenEMS caused the result |
| Status | See Section 10 |

### 8.2 Season, partial-year and early-month cautions

- Single months are not annual results. Annual figures from partial years use the approved seasonal adjustment and are labelled estimates.
- Months in which a site spent time in M1 (baseline), control-off weeks or M3 and M4 are reported with the split shown.
- Results from the first [3] months of controlled operation are labelled "early" because model fit and operator practice are still settling.

## 9. Supporting indicators and other content

### 9.1 Supporting indicators (MR-1 and MR-2)

| Group | Indicators (from D1 Section 6.1) |
| --- | --- |
| Technical | Battery round-trip efficiency, depth of discharge, cycles, state of health where reported, export limit compliance, setpoint clamps and rejects, safe-state events, diesel energy and fuel displaced (B), voltage at feeder end and transformer secondary, outages |
| Economic | Running annual net benefit, simple payback, NPV and cost per kW of peak reduced using measured values, with pilot cost and replication cost shown separately. Position against the break-even conditions (D1 Section 11) |
| EV | Wait time per session, throttled sessions, complaints per 100 sessions, energy delivered, vehicles that reject limiting |
| Institutional | Operators trained and retained, adoption of model or register by regulators or utilities |
| Engagement | Participation and acceptance indicators, complaints acknowledged and resolved on time |
| Data | Completeness, gap hours, meter accuracy checks passed, drift alarms, restatements |

### 9.2 Programme content (MR-2 and MR-3)

These are the Charter dashboard items (Charter Section 15).

| Item | Source | Content |
| --- | --- | --- |
| Progress against milestones | PMO | Deliverable and gate status, slippage against the stop-or-extend rule (C3 Section 14) |
| KPI trends | MR-1 | Headline KPIs per site, trend and status |
| Spend against budget | Finance lead, C2 | Spend, forecast, variance, contingency use and any request, exchange-rate exposure |
| Top risks | PMO, A6 | Top [5] risks with trigger status, including the Gate 4 trigger on savings below the range |
| Open issues | PMO | Issues log with age and owner |
| Change requests | PMO, D5 | PMO and technical change requests, outcomes, failed or rolled-back changes |
| Security incidents | Officer, D5 | Counts by severity, open critical or high findings, drift events, time to contain and notify |
| Training progress | D4 | Planned, enrolled, attended, assessed competent, retained, two-per-site rule. Shown separately |
| Safety and environment | C6, D5 | Class 1 to 4 incidents, near misses, open safety-critical items, inspections, drills, waste records |
| Operations | D3 | Uptime, mean time to acknowledge and repair, maintenance completion, spares availability |
| Engagement | PMO | Complaints and feedback, participation, upcoming community updates |

## 10. Status scheme and thresholds

Status is shown as a word and a symbol, with colour as a third cue. Thresholds are proposals for Gate 1 and apply per indicator.

| Status | Word | Symbol | Meaning |
| --- | --- | --- | --- |
| On track | ON TRACK | ● | Meets target or plan, no action needed |
| Watch | WATCH | ▲ | Within [x]% of the limit or one month below plan. Owner named, action noted |
| Off track | OFF TRACK | ■ | Below target or plan for [2] consecutive months, or a limit breached. Action plan and date required |
| Escalated | ESCALATED | ◆ | A Charter escalation trigger has fired. Goes to the Programme Director and SteerCo |
| Not yet set | NO TARGET | ○ | No target or insufficient data. Shown honestly and not coloured |

**Charter escalation triggers monitored every month** (Charter Section 18): any critical security finding or confirmed incident; fewer than planned trainees certified (at Gate 3); a failed compatibility test on a selected device; data gaps above the agreed threshold (Pilot B); forecast overrun above tolerance; approval not secured by Gate 1; any formal proposal to change net-metering or licensing rules; interim results trending below the 15 to 30% range (at Gate 4).

**Rule.** Status cannot be improved by changing a target, a baseline or a definition. Any such change follows Section 11.

## 11. Data quality, uncertainty and control of changes

### 11.1 Data quality block (top of every MR-1)

| Check | Reported |
| --- | --- |
| Completeness | % of expected intervals per channel, gap hours, longest gap |
| Reconciliation | Edge vs research meter energy difference, energy balance closure |
| Plausibility and sign | Flags raised and resolved |
| Time | Maximum drift, source status |
| Mode flags | Share of records with a valid mode flag and hash. Records without are excluded |
| Seals and calibration | Seals intact, certificate dates, accuracy checks done this month |
| Restatements | Prior-month figures changed, with reason |

A KPI is shown "not reportable" for the month where completeness or reconciliation falls below the Panel's threshold [x]%, with the reason. A blank is never used.

### 11.2 Uncertainty

Each KPI carries combined uncertainty from meter class, sampling, model error and missing data (D1 Section 8.3). Where uncertainty exceeds the measured effect, the report states that the effect is not distinguishable from zero at that site.

### 11.3 Models and changes

- Counterfactual models are refitted only on the schedule the Panel approved. Out-of-sample error is shown each month. A model that fails the fit criterion [x] is not used for savings claims (D1 Section 7.4).
- A change to a KPI definition, baseline, method or target after Gate 1 needs SteerCo approval on Panel advice (Charter Section 20). The report shows the change, the reason and the effect on past figures.
- Any configuration change that affects a KPI-relevant parameter during M1 or M2 is listed with the change ID and Panel decision (D5).

## 12. Distribution, access and publication

| Product | Recipients | Condition |
| --- | --- | --- |
| MR-1 | Panel, Research Lead, Technical Lead, relevant Site Lead, university partner, Programme Director | Panel validated. Host sees own site section only (Site Agreement 9.4) |
| MR-2 | PMO, TWG, Programme Director, SteerCo | Programme-level, no personal data |
| MR-3 | SteerCo, funders, Panel | Provisional label until validation |
| MR-4 | Hosts, Kenya Power, EPRA, communities, public | Findings seen by directly involved parties before public release (Stakeholder Plan Section 15). Hosts may comment on drafts for [14] days but cannot require changes. Publication may be delayed by up to [60] days only to protect personal data, security or a legitimate legal interest (MoU Section 10.3) |

**Disclosure rules** (D2 Section 10). No figure is based on fewer than [k] customers, sessions or vehicles. Household data is published only at feeder or transformer-group level. Charger data is published only at hourly or session-distribution level. Host commercial data is published in identifiable form only with host consent, but aggregated results cannot be blocked (Site Agreement 9.3). Incident detail is summarised. Credentials, network details and unpatched vulnerabilities never appear.

**Public series.** After Gate 4 an aggregated data summary is published (D1 Section 13). Monthly aggregated datasets and code are released with the anonymised release package (E5) after the Panel accuracy check and the security and privacy review.

## 13. Pilot-specific reporting notes

| Pilot | Additional content |
| --- | --- |
| A: Industrial park, hub or campus | Mechanism split of savings; tariff or demand-charge changes and their treatment; protected-load overrides and periods excluded; net-metering status and export limit compliance; host behaviour changes; benefit-sharing note |
| B: Rural microgrid | Loss separation status (defensible or total only); metering coverage; check meter and feeder input reconciliation; diesel and fuel displaced; outages and low-voltage events; supply continuity confirmation (no disconnection or price rise from the pilot); data-gap hours against the agreed threshold; theft, vandalism and community feedback. Results are described as site evidence, not a general loss figure |
| C: EV charging site | Transformer loading against threshold and unconstrained reconstruction; full-capacity share; wait-time distribution against the agreed maximum; fairness by customer class; throttling complaints; site limit in force and any change agreed with Kenya Power; vehicle compatibility notes |

## 14. Reporting through the gates

| Gate | Timing | Use of the monthly series |
| --- | --- | --- |
| Gate 2 | Month 8 | Templates, calendar, thresholds and dashboard tool frozen. Dry run on lab data |
| Gate 3 | Month 12 | Dry run on baseline data complete. First provisional report issued. Baseline readiness (C5 BR-1 to BR-7) evidenced |
| Gate 4 | Month 18 | Six months of validated data (Months 13 to 18) consolidated into E1 with trend, uncertainty and position against the 15 to 30% range. Trigger test applied |
| Gate 5 | Month 24 | Twelve validated months consolidated into E2. Series archived and handed to the custodian |

If any site is forecast to hold fewer than 12 months of validated controlled data, the monthly report states this and the stop-or-extend rule in C3 Section 14 applies, with Panel advice on the effect on evidence (D1 Section 14).

## 15. Schedule

| Activity | Months | Output | Gate |
| --- | --- | --- | --- |
| Draft report set, templates and status scheme | 4 to 6 | This document v0.1 reviewed by Panel and TWG | Gate 1 input |
| Set thresholds, KPI targets and review chain | 4 to 6 | Approved structure | **Gate 1** |
| Choose and configure dashboard and report tooling. Build pipeline and templates | 6 to 8 | Tested on lab data | **Gate 2** |
| Dry run: two full cycles on lab or commissioning data | 10 to 12 | Dry-run reports and lessons | Gate 3 input |
| First provisional report on baseline data | 12 | MR-1 to MR-3 | **Gate 3** |
| Monthly validated reports | 13 to 24 | MR-1 to MR-4 each month | |
| Quarterly SteerCo reports | 15, 18, 21, 24 | Extended MR-2 | |
| Interim evaluation | 18 | E1 | **Gate 4** |
| Final series archive and handover | 22 to 24 | Archive, custodian briefing | **Gate 5** |

## 16. Risks to add to the live Risk Register

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| MP1 | Reports late or unvalidated, so gate decisions rest on provisional data | M | H | Fixed calendar, provisional label, no gate use of provisional figures, backup analyst | Research Lead |
| MP2 | Selective emphasis or softening of poor results under pressure | M | H | Pre-registered KPI set, equal prominence rule, Panel validation, MoU Section 10 limits | Programme Director |
| MP3 | Definitions, targets or baselines altered to improve status | L | H | Change control, restatement log, SteerCo approval on Panel advice | Research Lead |
| MP4 | Misreading of partial-year or seasonal results as annual performance | M | M | Labels, rolling and cumulative views, seasonal adjustment note | Data analyst |
| MP5 | Analyst or university capacity gap in a month | M | M | Named backup analyst, documented code, student support | Research Lead |
| MP6 | Data gaps make KPIs "not reportable", especially at Pilot B | H | M | Local buffering, spares, gap threshold, honest not-reportable status | Site Lead B |
| MP7 | Disclosure of personal or commercial data through reports | L | H | k threshold, release clearance, host review, restricted fields | Officer |
| MP8 | Report burden on small site teams causes late or poor inputs | M | M | Reuse D3 monthly report, single input template, PMO reminders | Programme Manager |
| MP9 | Dashboard tool unavailable or unsuitable at low connectivity | M | L | Offline-capable export, PDF fallback, tested at Gate 2 | Data analyst |
| MP10 | Reporting under-budgeted (analyst time, tooling, university cost) | M | M | Itemise in budget reconciliation before Gate 1 | Programme Manager |

These risks are to be merged into the live Risk Register (README A6).

## 17. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Set numeric KPI targets and status thresholds (Watch, Off track) | Gate 1 | Panel, Programme Director |
| 2 | Fix the validation threshold for completeness and reconciliation below which a KPI is "not reportable" | Gate 2 | Panel |
| 3 | Confirm the production calendar and Panel meeting date against site and university availability | Gate 2 | Research Lead |
| 4 | Choose the dashboard and report tool, with offline export and access roles | Gate 2 | Data analyst, Technical Lead |
| 5 | Agree minimum group size k and disclosure rules for MR-4 and public series | Gate 1 | Officer, Research Lead |
| 6 | Decide Kiswahili and local-language MR-4 production and who translates | Gate 2 | Programme Manager |
| 7 | Decide how restatements and the restatement log are shown publicly | Gate 3 | Research Lead |
| 8 | Agree what spend and contingency detail funders receive in MR-3 | Gate 1 | Programme Manager, finance lead |
| 9 | Fix baseline length and test pattern, which determine early-month reporting (D1 Section 7.3) | Gate 2 | Research Lead, Panel |
| 10 | Name the custodian of the report series and archive | Gate 5 | Programme Sponsor |

## 18. Immediate next steps

1. Panel and TWG to review this structure, including the Kenya Power grid engineer on feeder and transformer data in MR-1.
2. Research Lead to align the KPI dictionary (D1 Appendix A) and the standard KPI block in Section 8.1.
3. Data analyst to build the pipeline, report templates and status scheme and test them on lab data.
4. Agree the input templates from Site Leads, D4 and D5 so that monthly inputs arrive in one format.
5. Propose targets and status thresholds for Gate 1 once baseline data is in.
6. Draft the plain-language MR-4 template in English and Kiswahili and review it with the Stakeholder Engagement lead.
7. Itemise reporting costs in the budget reconciliation.
8. Add risks MP1 to MP10 and the open items to the PMO log and Risk Register.

---

# Appendix A: MR-1 Site KPI report (template)

| Section | Content |
| --- | --- |
| 1. Cover | Report ID `MR1-[site]-[YYYY-MM]`, site, period, status (provisional or validated), author, reviewer, Panel validation reference |
| 2. Headlines | Three to five plain sentences: what the data shows, what it does not show, what changed |
| 3. Mode and configuration | Mode records in force, days in each mode, configuration tag and hash, changes affecting KPIs |
| 4. Data quality block | As Section 11.1 |
| 5. KPI blocks | One block per applicable KPI, as Section 8.1 |
| 6. Mechanism analysis | What drove the result, with the supporting data |
| 7. Supporting indicators | As Section 9.1 |
| 8. Confounders and exclusions | Events from the confounder log, periods excluded or modelled, overrides |
| 9. Uncertainty and limits | What this month's data cannot tell us |
| 10. Actions | Issues, owners, dates, recommendations |
| 11. Validation note | Panel decisions, data quality notes, sign-off |

# Appendix B: MR-2 Programme performance report (template)

| Section | Content |
| --- | --- |
| 1. Executive summary | Overall status, key messages, decisions or support needed |
| 2. Delivery | Milestones, deliverables, gate readiness, schedule risks, stop-or-extend position |
| 3. KPI summary | Headline KPI per site with status symbol, linked to MR-1 |
| 4. Operations | Uptime, faults, response and repair times, maintenance, spares |
| 5. Safety and environment | Incidents by class, near misses, inspections, drills, waste, open safety-critical items |
| 6. Security and data | Incidents by severity, drift events, patches, access review, privacy matters |
| 7. Change | PMO and technical change requests, failed or rolled-back changes |
| 8. Training and capacity | Planned, enrolled, attended, assessed competent, retained, two-per-site rule |
| 9. Engagement | Complaints and responses, participation, planned engagement |
| 10. Finance | Spend, forecast, variance, contingency, exchange-rate exposure |
| 11. Risks and issues | Top risks, trigger status, new risks, open issues |
| 12. Next month | Planned events, outages, tests, reviews |

# Appendix C: MR-3 Programme dashboard (template)

| Item | Display | Status |
| --- | --- | --- |
| Milestones | Gate and deliverable timeline, % complete | ● ▲ ■ ◆ ○ |
| K1 Peak import reduction | A, B, C: value, trend, uncertainty | [ ] |
| K2 Self-consumption | A, B: value, trend | [ ] |
| K3 Bill savings vs 15 to 30% range | A, B: value, interval, position vs range | [ ] |
| K4 Uptime | A, B, C: value, trend | [ ] |
| K5 Transformer loading and full-capacity share | C: value, trend | [ ] |
| K6 Loss reduction | B: value or "total only", trend | [ ] |
| Data quality | Completeness, gap hours | [ ] |
| Spend | Spend vs budget, forecast, contingency | [ ] |
| Top risks | Top [5] with trigger status | [ ] |
| Open issues and change requests | Counts, ageing | [ ] |
| Security incidents | Counts by severity | [ ] |
| Safety incidents | Counts by class | [ ] |
| Training | Attended, competent, retained | [ ] |

Each tile carries the label "provisional" or "validated" and the period covered.

# Appendix D: MR-4 Plain-language summary (template)

Short, in English and Kiswahili, readable aloud, with pictures where helpful.

1. What this pilot is, in one sentence, and that it is a research pilot.
2. What the equipment did this month, in simple terms and aggregated.
3. What went well, what did not, and what we are doing about it.
4. Any interruptions, tests or works planned next month, and when.
5. What the results mean so far and what they do not. No promises of savings, jobs or lower tariffs.
6. How to ask a question, complain or give feedback, and how data is protected.

# Appendix E: Report sign-off (template)

| Role | Name | Signature | Date |
| --- | --- | --- | --- |
| Data analyst (author) | [ ] | | |
| Research Lead | [ ] | | |
| Second analyst (calculation check) | [ ] | | |
| Panel chair (validation) | [ ] | | |
| Cybersecurity and Data Protection Officer (release clearance) | [ ] | | |
| Programme Manager (MR-2, MR-3) | [ ] | | |
| Programme Director (MR-4 release) | [ ] | | |

# Appendix F: Restatement log (template)

| Date | Month restated | Report ID | KPI or item | Original value | Revised value | Reason | Approved by | Effect on conclusions |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

# Appendix G: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 7, 12, 15, 16, 18, 20, 21, 23) | KPIs, dashboard items, gates, escalation triggers, change control, independence, publication, evaluation requirements |
| Problem Statement | Central and supporting questions the series ultimately answers |
| Feasibility Study (Sections 5.4 to 5.6, 12) | Metrics, break-even logic, replication cost |
| Monitoring and Evaluation Plan (Sections 6 to 9, 11 to 14, Appendices A, B) | KPI dictionary, modes, quality checks, decision rules, monthly report outline, schedule |
| Data Management and Privacy Plan (Sections 8 to 10, 12) | Access, disclosure thresholds, release process |
| Operations and Maintenance Manual (Sections 15, Appendix E) | Monthly site report input |
| Training Materials and Attendance Records (Sections 14.3, 15) | Attended, competent, retained reporting |
| Incident and Change Log (Sections 12, Appendix C) | Incident, change and confounder summary |
| OpenEMS Configuration Baseline (Sections 6.6, 9) | Mode records, hashes, drift |
| Site Acceptance Test Reports (Section 10) | Baseline readiness before reporting starts |
| Health, Safety and Environmental Plan (Section 18) | Safety indicators |
| Cybersecurity Plan (Section 12.3) | Security indicators |
| Stakeholder Engagement Plan (Sections 11, 13, 15) | Complaints, engagement indicators, disclosure before publication |
| MoU and Site Agreement templates (MoU Section 10; Site Agreement 9.3, 9.4) | Publication rights, host access and comment limits |

On completion of the Gate 1 decisions (targets, thresholds, disclosure rules) and the Gate 2 tool choice and dry-run lessons, each bracketed value is updated and this document is re-issued as version 1.0 for Gate 2.

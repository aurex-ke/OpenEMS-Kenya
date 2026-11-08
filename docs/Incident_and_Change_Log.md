# Incident and Change Log

## 1. Purpose and bottom line

This document (D5) defines the single controlled record of **what went wrong and what was changed** at the three pilot sites and in the programme systems. It gives the Technical Working Group, the PMO, the Research and Evaluation Panel, Kenya Power, the insurer and auditors one place to see outages, safety events, security events, configuration changes, firmware changes and the decisions taken. Other documents already refer to it: C4 logs every change in D5, C6 links incident reports to it, B7 sends incident records to it, and the O&M Manual files service reports against it.

**Bottom line.** The log is part of the evidence, not just admin. The evaluation compares each site with its baseline, so an unlogged change or an unlogged outage can make a result impossible to defend. Eight rules follow:

1. **One log, two registers.** An incident register and a change register, cross-referenced, with one ID scheme and one severity map.
2. **Append-only.** An entry is never overwritten or deleted. A correction is a new entry that points to the old one.
3. **Log first, fix fast.** In an emergency, make safe first (C6 Section 14.2), then log within the time limits in Section 7. Late entries are marked late, not refused.
4. **Every change has a request, a commit, a test record, an approver and a log line.** This is the evidence trail required by C4 Section 9.
5. **Every entry carries a data flag.** The operating mode (M0 to M4) and any effect on the baseline or a KPI are recorded, so the Panel can exclude or model the affected period (D1 Section 7.5).
6. **Blameless, but not anonymous to the process.** Reports are never penalised. The record still names roles and approvers, because accountability is a Charter principle.
7. **Failures are published with equal prominence.** Rollbacks, failed changes and incidents appear in sanitised form in the Gate reports and the replication guide (Charter Section 21).
8. **Personal and security-sensitive detail is restricted.** Incident records can hold personal data, health details and unpatched vulnerability information. Access and publication follow D2 and B7.

**What cannot be settled from desk research.** The tool, the alarm codes, the device list and the real incident volumes are unknown. This document fixes the structure, rules and templates, and leaves tool and threshold choices to Gate 2.

## 2. Document control and relationships

**Owner:** Technical Lead (README D5). **Contributors:** software engineer, Site Leads, site engineer (C6 owner), Cybersecurity and Data Protection Officer, Research Lead and data analyst, PMO, Kenya Power grid engineer (TWG). **Approval:** Programme Director at Gate 1 (method); tool and templates frozen at Gate 2; live from first energisation. Reviewed fortnightly in the TWG during build and monthly in operation. Changes to this method follow Charter Section 20.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 15, 16, 18, 19, 20, 23) | Dashboard, gates, escalation triggers, safety governance, change control tolerances, independent review |
| Health, Safety and Environmental Plan (C6, Section 14, Appendix C) | Incident classes 1 to 4, response, investigation, report template. This log holds the register of those reports |
| Cybersecurity Plan (B7, Sections 6.3, 6.6, 10) | Security severity S1 to S4, notification routes, playbooks, log integrity |
| OpenEMS Configuration Baseline (C4, Sections 6.6, 9, 10, Appendix B) | Change classes C0 to C4, change request template, modes, drift alarm, rollback |
| Interoperability Register (B6, Sections 10.3, 11) | Delta testing after any change, failed-test escalation |
| Operations and Maintenance Manual (D3, Sections 7, 10, 15) | Override log, maintenance records, return to service, escalation ladder |
| Site Acceptance Test Reports (C5, Section 14) | Non-conformance log during commissioning, which carries into D5 at Gate 3 |
| Installation and Commissioning Plan (C3, Sections 8, 16, Appendix C) | Punch list, hold points, change control during build |
| Monitoring and Evaluation Plan (D1, Sections 7.5, 9.2) | Confounder log, mode flags, data exclusions |
| Data Management and Privacy Plan (D2, Sections 8, 9, 12) | Access, retention, breach steps |
| Risk Register (A6) | Receives risks raised from incidents and changes |
| MoU and Site Agreement templates (MoU Sections 7.4, 8; Site Agreement Sections 5.3, 10) | Contractual notification duties |

## 3. Scope

**In scope.** From first energisation of any site (and from lab testing for changes to the test configuration) to Gate 5: safety, security, data, equipment, supply, environmental and community incidents and near misses; changes to configuration, firmware, drivers, safe states, limits, mode, network, access rights, procedures and schedules; planned maintenance windows that change system state; overrides that exceed review limits.

**Out of scope.** Routine checks with no exception (D3 logbook), cost and budget changes (Charter Section 20 change log held by the PMO), and Kenya Power's internal records. Programme budget, scope and schedule change requests keep their own PMO log, and the entries here link to them where a technical change triggers one.

## 4. What is logged, and where it lives

| Record | Purpose | Lives in | Link to D5 |
| --- | --- | --- | --- |
| Incident register | Every Class 1 to 3 incident and near miss, and S1 to S4 security events | D5 Appendix A | Master |
| Change register | Every change to layers L1 to L7 (C4) and to procedures that affect safety, data or the baseline | D5 Appendix B | Master |
| Site logbook | Daily and weekly checks, visitors, events | Site (D3 Appendix B) | Events that meet Section 5 criteria are copied into D5 |
| Override log | Time, person, reason, duration | Edge and operator (D3 Section 7) | Overrides above review limits get a D5 entry |
| Maintenance and service log | Work, permit, parts, serials | Site engineer (D3 Appendix D) | Corrective maintenance that touches a protection, limit or firmware is also a change |
| Confounder log | Events that could distort results | Operator and Site Lead (D1 7.5) | Each D5 entry marks whether it is a confounder |
| Non-conformance log | Test and inspection failures | C5 Section 14, C3 Appendix C | Failures on a selected device carry into D5 |
| Mode records | Signed M1 and M2 entries | C4 Section 6.6 | Linked, never duplicated |
| Complaints log | Community and driver concerns | PMO | Safety or data-related complaints are cross-referenced |

**Rule.** One event, one primary entry. Other logs hold a reference ID, not a second copy of the facts.

## 5. What triggers an entry

| Trigger | Register | Examples |
| --- | --- | --- |
| Harm or potential harm to people, equipment or environment | Incident | Injury, fire or thermal alarm, spill, electric shock, near miss, unsafe act |
| Unsafe or unplanned equipment state | Incident | Safe state entered, protection trip, setpoint clamp pattern, charger fallback |
| Security or privacy event | Incident | Drift alarm, unknown device, vendor access found, lost device, personal data exposure |
| Loss of supply, availability or data | Incident | Edge failure, outage to customers (B), data gap above threshold, meter fault |
| Breach of a rule | Incident | Reset without cause, broken seal, unrecorded override, permit breach |
| Any change to a configuration layer, firmware, driver, image, network or account roles | Change | Tariff schedule update, firmware patch, new account, firewall rule |
| Any change to safe states, limits or override rules | Change (class C1) | Export limit, site limit, SoC window, charger fallback |
| Change to operating mode or test pattern | Change | Entry to M1 or M2, control-off week |
| Planned work that alters system state | Change (class C4 if non-behavioural) | Maintenance window, host shutdown, generator service |
| Complaint with a safety, supply or data element | Incident (linked) | Throttling dispute that alleges damage, supply interruption |

When unsure, log it. A rejected entry costs a minute, a missing entry can cost a result.

## 6. Classification and the severity map

The programme has three existing scales that overlap. They are not replaced. D5 maps them so one event gets one consistent rating.

*Numbering note. Alarm classes A1 to A4 (D3) and acceptance tests A1 to A10 (B4) share letters. Change classes C0 to C4 (C4) are unrelated to document IDs C1 to C6. In D5 entries, always write the scheme: "Class 2", "S2", "Alarm A2", "Change C1".*

| D5 priority | C6 incident class | B7 security severity | D3 alarm class | Typical response |
| --- | --- | --- | --- | --- |
| P1 Critical | Class 1: fatality, life-changing injury, fire, thermal event, major release, serious public harm | S1: unsafe state, confirmed unauthorised control, serious personal data breach | A1 Emergency | Emergency response, site stopped, immediate escalation |
| P2 High | Class 2: lost-time injury, medical treatment, significant spill, equipment or property damage, unsafe state from control failure | S2: confirmed compromise without safety impact, vendor remote path found, critical drift | A2 Safety-relevant | Make safe, report within hours, investigation required |
| P3 Medium | Class 3: near miss, first aid, minor spill, unsafe act | S3: suspicious activity, failed intrusion, firmware tamper alarm | A3 Operational | Same-day report, local fix and learning |
| P4 Low | Class 4: observation | S4: policy breach, lost non-sensitive device, minor misconfiguration | A4 Advisory | Log and review monthly |

**Rules.** The highest of the applicable scales sets the D5 priority. A failed hold point test, a failed hardware protection test or any unexplained change to the safety set is at least P2 (C6 Section 14.2, C4 Section 17). Priority can be raised on review, never lowered without a recorded reason.

### 6.1 Change classes (from C4)

| Class | Meaning | Examples | Approval (summary) |
| --- | --- | --- | --- |
| C0 Emergency safety | Immediate isolation or lowering of a limit | Isolating a device after an alarm | Site Lead on site, Technical Lead informed same day, review within \[2\] working days |
| C1 Safety layer (L5) | Safe state, plausibility or grid limit | Export limit, site limit, fallback limit | Technical Lead and Cybersecurity Officer; Kenya Power for grid limits; two-person on-site rule \[pending\] |
| C2 Behaviour (L4) | Setpoints, tariff schedule, policy | Peak setpoint, ToU windows | Technical Lead; Panel approval if KPI-relevant during M1 or M2 |
| C3 Platform | OpenEMS release, image, driver, firmware | Firmware patch, driver update | TWG with Cybersecurity Officer; B6 delta tests |
| C4 Non-behavioural | Documentation, labels | Manual correction | Maintainer with independent reviewer |

## 7. Roles and time limits

| Role | Responsibility |
| --- | --- |
| Reporter (anyone) | Reports an event to the operator or Site Lead without delay |
| Operator and backup | Opens the entry for events they see, with time, what, who was told. First response per D3 |
| Site Lead | Owns incident entries for the site, assigns priority, authorises return to service, holds stop authority |
| Technical Lead | Owns the change register, approves C1 to C3 changes, chairs TWG review of repeats |
| Software engineer | Raises and executes change requests, records hashes and test references |
| Cybersecurity and Data Protection Officer | Owns security and privacy incidents, approves access to restricted entries, leads breach steps |
| Research Lead and data analyst | Marks data effects, confounders and baseline impact. Receives the monthly extract |
| PMO | Keeps the master index, tracks actions and ageing, reports on the dashboard |
| Programme Director | Receives P1 and P2, notifies regulators and funders, releases P1 return to service |
| Independent reviewer | Reviews investigations for P1 and P2 and merges that change class C1 or C3 |
| Kenya Power, EPRA, insurer | Notified per Section 10. Do not edit the log |

**Proposed time limits** (to be harmonised across C6, B7 and D3 at Gate 2, see open item 2):

| Step | P1 | P2 | P3 | P4 |
| --- | --- | --- | --- | --- |
| Make safe | Immediately | Immediately | As needed | n/a |
| Entry opened in D5 | Within \[1\] hour of safe state | Within \[24\] hours | Same day | Within \[3\] working days |
| Notify PMO and Programme Director | Within \[1\] hour | Within \[24\] hours | Next review | Monthly |
| Initial assessment complete | \[4\] hours | \[2\] working days | \[5\] working days | Monthly review |
| Investigation report | Independent lead, within \[10\] working days | \[10\] working days | If repeated | n/a |
| Corrective actions assigned | With the report | With the report | With the entry | At review |

## 8. Incident workflow

1. **Make safe.** Protect life first. Isolate equipment, call responders, evacuate as the plan says. Nobody re-enters a battery or fire area except trained responders (C6 Section 14.2, D3 Section 11).
2. **Report and open the entry.** Anyone reports. The Site Lead or operator opens the entry with the fields in Appendix A, even if incomplete. Mark unknowns as "unknown", not blank.
3. **Triage.** Site Lead assigns priority from the severity map. The Officer confirms any security or privacy element. Mark restricted if it contains personal data, health detail or live vulnerability detail.
4. **Preserve evidence.** Keep logs, images, configuration hash, firmware list and equipment as they are, unless that creates danger. Record the hash and mode flag at the time of the event.
5. **Notify.** Follow Section 10. Record who, when and by what route.
6. **Contain and recover.** Follow the playbooks (B7 Section 10.5, D3 Section 10). Any restoration is a change entry if it alters configuration.
7. **Investigate.** Blameless root-cause review, with an independent lead for P1. State direct cause, contributing factors and what was not known.
8. **Act.** Corrective and preventive actions with owner, due date and verification. The PMO tracks them to closure.
9. **Return to service.** Site Lead signs the D3 return-to-service checklist. P1 needs the Programme Director's approval (C6 Section 14.2).
10. **Close and learn.** Close only when actions are verified. Add risks to the Risk Register where the cause could recur. Share lessons at Gates 3 and 5.

**Repeat rule.** Three entries with the same cause at one site in \[90\] days, or the same cause at two sites, trigger a TWG root-cause review and a risk entry.

## 9. Change workflow

The procedure is defined in C4 Section 10.2. D5 holds its register and adds the following.

| Step | D5 requirement |
| --- | --- |
| Raise | Change ID `CR-[site]-[number]` created before work starts. Reason, layers affected (L1 to L7), class (C0 to C4), expected effect on KPIs and baseline, rollback plan |
| Assess | Technical Lead, and where relevant Cybersecurity Officer, Research Lead and Kenya Power. Record who was consulted |
| Approve | Approvers per class. Panel notified or approval recorded for any KPI-relevant change during M1 or M2 |
| Test | Lab or spare Edge first. Record B6 test IDs and the C5 subset. Delta rules from B6 Section 10.3 apply |
| Schedule | Time chosen to protect data and operations. Data flagged M4 where behaviour changes. Host, community or operator told |
| Deploy | Hash before and after, method (on site or remote after Gate 3), deployer, witness |
| Verify | Safe states still work, drift check clean, backup taken |
| Close | Outcome: success or rolled back. Link to commit, tag and manifest version. Failed changes stay in the register |

**Rules.**

- No change is deployed without an open `CR` entry, except class C0, where the entry is raised within the C0 review window.
- Remote deployment after Gate 3 is allowed only for classes C2 to C4. Safety-layer changes follow the on-site route (C4 Section 10.3).
- Any change during a baseline period (M1) is flagged to the Panel. A change that alters a KPI-relevant parameter is a change to the experiment, not a routine edit (C4 Section 6.6).
- A change that needs a budget, schedule or scope decision beyond Programme Director tolerance also raises a request in the PMO change log (Charter Section 20), and the two IDs are cross-referenced.
- Mode switches (M1, M2, control-off weeks) are logged here as changes and linked to the signed mode record, which remains the authority.

## 10. Notification routes

| Recipient | When | Who notifies | Source |
| --- | --- | --- | --- |
| PMO | All P1 to P3 incidents without delay. Any personal data breach within \[48\] hours | Site Lead, Officer | MoU 7.4, B7 10.3 |
| Programme Director | P1 and P2 | PMO, Site Lead | C6 14.1 |
| Steering Committee Chair | P1 immediately. P2 within \[2\] working days. All in the quarterly report | Programme Director | Charter 15, B7 10.3 |
| Kenya Power | Cyber incidents, grid-affecting events, transformer threshold events, any P1 or P2 at the connection point, and any change to a grid-related limit | Programme Director, Technical Lead | Charter 19, MoU Schedule 1B |
| EPRA | Where licence, exemption or sandbox conditions or regulation require | Programme Director | MoU Schedule 1A |
| Insurer | Fire or thermal events always, other events as the policy requires | Programme Director, Site Lead | Site Agreement 13 |
| Office of the Data Protection Commissioner and affected people | Personal data breaches meeting the statutory threshold, within the statutory time \[confirm with counsel\] | Officer | D2 Section 12 |
| Statutory safety, fire, environment bodies and police | As the law requires \[confirm\] | Programme Director with counsel | C6 14.1 |
| Research and Evaluation Panel | Every entry marked as a confounder or baseline effect, monthly extract, immediate notice for KPI-relevant changes | Research Lead | D1 7.5, C4 6.6 |
| Host representative, operator, community or users | Outages, tests, safety events and anything that affects them | Site Lead, liaison | Stakeholder Plan 7.3 |
| Vendor or upstream community | Product defects and vulnerabilities, by responsible disclosure after mitigation | Technical Lead, Officer | B7 6.9 |

## 11. Data integrity, privacy and access

| Topic | Rule |
| --- | --- |
| Append-only | Entries are never edited after submission. Corrections are new entries referencing the original ID. The tool must keep a time-stamped history |
| Time | All times from the synchronised source, in East Africa Time, with the source recorded. Manual times are marked as such |
| Identity | Entries are made under named accounts. No shared logins (B7 6.1) |
| Tamper resistance | Daily export with checksum to a second location. Monthly integrity check by the Officer |
| Personal data | Incident and complaint entries record roles rather than names where possible. Health details, children's information and personal identifiers go only in the restricted field with limited access |
| Security-sensitive detail | Credentials, network maps and unpatched vulnerability details are never in the open fields. They are referenced to the private repository (C4 Section 5.1) |
| Access | Open fields: PMO, Site Leads, TWG, Panel. Restricted fields: Officer, Programme Director, named investigators. Hosts see their own site's summary. Vendors see only entries about their own device, after review |
| Retention | Incident and breach records for \[3\] years or as the law requires (B7 6.6, D2 Section 9). Change records for the pilot period plus \[x\] years. Then anonymise or delete |
| Publication | Sanitised summaries only, after the security and privacy review. Equal prominence for failures (Charter Section 21) |

## 12. Review, reporting and measures

| Forum | Frequency | Input from D5 |
| --- | --- | --- |
| Site operations check-in | Weekly | Open P1 to P3, overrides above limits, changes planned |
| TWG | Fortnightly in build, monthly in operation | Changes awaiting decision, repeat causes, failed changes, drift events |
| Research and Evaluation Panel | Monthly in operation | Extract of confounders, mode and KPI-relevant changes, data gaps |
| PMO review and monthly dashboard | Fortnightly and monthly | Counts by priority, ageing, actions overdue, security incidents (already a Charter dashboard item) |
| Steering Committee | Quarterly and at gates | Summary, P1 and P2 detail, accepted risks, lessons learned |
| Gate reviews | Gates 3, 4, 5 | Evidence in Section 15 |

| Indicator | Measure | Target |
| --- | --- | --- |
| Reporting culture | Near misses and P3 and P4 reports per month, and share closed on time | Rising reporting, \[x\]% on time |
| Timeliness | Share of entries opened within the Section 7 limits | \[95\]% |
| Serious incidents | P1 and P2 per site | Zero P1. P2 trend reviewed monthly \[targets at Gate 1\] |
| Action closure | Corrective actions closed by due date, and overdue actions | \[90\]% on time, zero overdue P1 or P2 actions |
| Change discipline | Changes with a complete evidence trail (request, test, approval, hash, D5 line) | 100% |
| Unplanned change | Drift alarms and unapproved changes found | Zero unexplained; each treated as P2 if L5 changed |
| Failed or rolled back changes | Count and share | Reported, no target that rewards hiding |
| Repeat causes | Entries meeting the repeat rule | Trend down |
| Data effect | Entries flagged as confounders and data-days lost per site | Reported to Panel |
| Time to return to service | Mean, by device class and priority | \[x\] hours |

## 13. Pilot-specific notes

| Pilot | Extra logging needs |
| --- | --- |
| A: Industrial park, hub or campus | Host-initiated load or tariff changes, shutdowns, protected-load overrides, existing PV inverter alarms, host IT changes. Host confidential detail goes in the restricted field |
| B: Rural microgrid | Customer supply interruptions and low-voltage reports, generator events and fuel readings, theft and vandalism, community complaints, connectivity loss and data-gap hours, planned transfer tests. Entries are plain-language and, where shared with the community, in English and Kiswahili |
| C: EV charging site | Charger faults and fallback events, site-limit changes and the Kenya Power agreement for each, transformer-feed loss, throttling complaints, vehicles that reject limiting, public safety events. Driver identifiers stay pseudonymised |

## 14. Risks to add to the live Risk Register

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| IL1 | Under-reporting of near misses and incidents at remote or small sites | M | H | Non-retaliation, easy reporting, operator training, audits | Site Leads |
| IL2 | Changes made without a request, distorting the baseline or breaking safety limits | L | H | Drift alarms, named accounts, hash checks, no manual edits | Software engineer |
| IL3 | Three severity scales produce inconsistent ratings and response times | M | M | Severity map, harmonise at Gate 2 | Technical Lead |
| IL4 | Log tool unavailable or lost at sites with poor connectivity | H | M | Offline entry, daily export, paper fallback, Pilot B sync routine | Site Lead B |
| IL5 | Personal or security-sensitive detail exposed through the log or its summaries | L | H | Restricted fields, access roles, pre-release scan | Officer |
| IL6 | Confounders not flagged, so savings are contested | M | H | Mandatory data-effect field, monthly Panel extract | Research Lead |
| IL7 | Corrective actions not closed, repeat incidents | M | M | PMO tracking, overdue escalation, repeat rule | Programme Manager |
| IL8 | Pressure to soften or delay publication of incidents | M | H | Equal prominence rule, MoU Section 10 limits | Programme Director |

## 15. Schedule and gate evidence

| Activity | Months | Output | Gate |
| --- | --- | --- | --- |
| Draft method and templates, agree severity map with TWG | 4 to 8 | This document v0.1 | Gate 1 input |
| Choose tool, offline method and storage, set up access roles | 6 to 8 | Tool configured, test entries | Gate 2 |
| Harmonise time limits across C6, B7 and D3 | 6 to 8 | Single table | Gate 2 |
| Use the register during lab testing and build (changes and non-conformances) | 4 to 12 | Entries from lab and C5 | Gate 3 |
| Live operation, monthly extracts to Panel and dashboard | 13 to 24 | Monthly summaries | Gate 4 |
| Final register, sanitised summary, handover to custodian | 22 to 24 | Archive, lessons | Gate 5 |

| Gate | Evidence from D5 |
| --- | --- |
| Gate 1 | Approved method and templates. Severity map agreed |
| Gate 2 | Tool live and tested. Time limits harmonised. Roles and access set. Test entries and an exercise logged |
| Gate 3 | Complete change trail for the frozen baseline, non-conformances from C5 carried in, no open P1 or P2, incident exercise logged (B7 10.6) |
| Gate 4 | Incident and change summary, drift and failed-change review, action closure, repeat causes, effect on data |
| Gate 5 | Final register with lessons learned, sanitised publication, custodian named |

## 16. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Choose the log tool (shared database, issue tracker or spreadsheet) with offline entry and append-only history | Gate 2 | Technical Lead, Cybersecurity Officer |
| 2 | Harmonise response and notification times across C6 Class 1 to 4, B7 S1 to S4 and D3 alarm classes | Gate 2 | TWG |
| 3 | Decide whether D5 is one tool or two linked tools (incident and change) | Gate 1 | Technical Lead |
| 4 | Fix thresholds for override review, repeat rule and data-gap entries | Gate 2 | Technical Lead, Research Lead |
| 5 | Decide the two-person on-site approval rule for class C1 changes (B7 open item 5) | Gate 2 | TWG |
| 6 | Confirm statutory notification routes and times with counsel | Gate 1 | Officer, counsel |
| 7 | Decide what is published, when, and in what sanitised form | Gate 3 | Officer, Research Lead |
| 8 | Agree access for hosts, vendors and Kenya Power | Gate 2 | Programme Director, Officer |
| 9 | Set retention periods | Gate 1 | Officer, counsel |
| 10 | Name the custodian of the final register | Gate 5 | Programme Sponsor |

## 17. Immediate next steps

1. TWG to review this method, including the Kenya Power grid engineer on notification of grid-related events and limits.
2. Agree the severity map and one set of time limits with the C6, B7 and D3 owners.
3. Select and configure the tool, with offline entry for Pilot B and a daily checksum export.
4. Pre-load templates, ID schemes and role access, and run a test exercise with dummy entries.
5. Brief operators and Site Leads on what to log, in English and Kiswahili, as part of D4 training.
6. Start using the change register for the lab Edge and the first lab configuration tags.
7. Add risks IL1 to IL8 and the open items to the PMO log and Risk Register.

---

# Appendix A: Incident register (template)

| Field | Entry |
| --- | --- |
| Incident ID | `INC-[site]-[number]` (C6 Appendix C) |
| Date, time, time source | \[ \] |
| Site, pilot, location | \[ \] |
| Reported by (role), received by | \[ \] |
| Priority (P1 to P4) and the scale ratings behind it (Class, S, Alarm) | \[ \] |
| Category (safety, security, privacy, equipment, supply, data, environment, community, rule breach) | \[ \] |
| Description of what happened | \[ \] |
| Immediate actions, injuries or damage | \[ \] |
| Operating mode at the time (M0 to M4), configuration tag and hash | \[ \] |
| Devices, firmware and registers involved (B6 IDs) | \[ \] |
| Effect on data, baseline or KPIs. Confounder flag (Y/N), periods to exclude | \[ \] |
| Effect on customers, host, drivers or community | \[ \] |
| Environmental effect | \[ \] |
| Evidence held (logs, photos, images, checksums) | \[ \] |
| Notifications made (who, when, route) | \[ \] |
| Restricted content present (Y/N) | \[ \] |
| Root cause and contributing factors | \[ \] |
| Corrective and preventive actions (owner, due date, verification) | \[ \] |
| Related change IDs, maintenance IDs, complaint IDs, risk IDs | \[ \] |
| Return to service (checklist reference, authoriser, date) | \[ \] |
| Status (open, investigating, actions open, closed) and closed by | \[ \] |

**Index view (open fields only).**

| ID | Date | Site | Priority | Category | Short title | Status | Owner | Next action and due | Confounder |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `INC-[ ]` | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[Y/N\] |

# Appendix B: Change register (template)

| Field | Entry |
| --- | --- |
| Change ID | `CR-[site]-[number]` (C4 Appendix B) |
| Date raised, requester (role) | \[ \] |
| Site and baseline version affected | \[ \] |
| Class (C0 to C4) and layers affected (L1 to L7) | \[ \] |
| Reason and linked incident or request | \[ \] |
| Expected effect on KPIs or baseline (Y/N, explain). Panel notified or approval reference | \[ \] |
| Risk assessment and rollback plan | \[ \] |
| Test plan and results (B6 test IDs, C5 subset, lab or spare Edge) | \[ \] |
| Approvers (names, roles, dates). Kenya Power agreement where grid-related | \[ \] |
| Commit, branch and tag, manifest version | \[ \] |
| Scheduled date and method (on site or remote). Mode flag set (M4) | \[ \] |
| Hash before and after (separate hash for L5) | \[ \] |
| Deployer and witness | \[ \] |
| Post-change verification (safe state, drift check, backup, data flowing) | \[ \] |
| Outcome (success, rolled back, partly applied) and notes | \[ \] |
| Linked PMO change request (budget, schedule or scope), if any | \[ \] |
| Status and closed by | \[ \] |

**Index view.**

| ID | Date | Site | Class | Layers | Short title | Approver | Effect on KPI or baseline | Outcome | Hash after | D5 incident link |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `CR-[ ]` | \[ \] | \[ \] | C\[ \] | L\[ \] | \[ \] | \[ \] | \[Y/N\] | \[ \] | \[ \] | \[ \] |

# Appendix C: Monthly summary outline (for the Panel and the dashboard)

1. Period, site, modes in force and configuration hashes.
2. Incidents by priority and category, open and closed, ageing.
3. Changes by class, outcomes, failed or rolled-back changes, unexplained drift.
4. Confounders and baseline effects, data-days excluded, KPI-relevant changes.
5. Overrides above review limits.
6. Corrective actions due, closed, overdue.
7. Repeat causes and risks added.
8. Lessons and proposals for the TWG.

# Appendix D: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 15, 16, 18, 19, 20, 21, 23) | Dashboard, gates, escalation triggers, safety governance, change control, publication, independent review |
| Health, Safety and Environmental Plan (Sections 6, 14, 15, Appendix C) | Incident classes, response and investigation, report template, return to service |
| Cybersecurity Plan (Sections 6.1, 6.3, 6.6, 10, 11) | Severity, notification, playbooks, log integrity, named accounts |
| OpenEMS Configuration Baseline (Sections 6.6, 9, 10, 17, Appendix B) | Change classes, procedure, modes, drift, failed-change prominence |
| Interoperability Register (Sections 10.3, 11) | Delta testing, escalation on failed compatibility test |
| Operations and Maintenance Manual (Sections 7, 10, 12, 15) | Overrides, return to service, escalation, logs |
| Site Acceptance Test Reports (Section 14) | Non-conformance carry-over |
| Installation and Commissioning Plan (Sections 8, 16, Appendix C) | Punch list, hold points, build change control |
| Monitoring and Evaluation Plan (Sections 7.5, 9.2) | Confounder log, mode flags, data exclusions |
| Data Management and Privacy Plan (Sections 8, 9, 12) | Access, retention, breach handling |
| Stakeholder Engagement Plan (Sections 7.3, 11) | Notice to hosts and community, complaints link |
| MoU and Site Agreement templates (MoU 7.4, 8, Schedule 1B; Site Agreement 5.3, 10, 13) | Notification duties, insurer and utility routes |

On completion of the Gate 1 decisions, the tool choice and the harmonised time limits, each bracketed value is updated and this document is re-issued as version 1.0 for Gate 2.

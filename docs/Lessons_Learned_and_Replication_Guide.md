# Lessons Learned and Replication Guide

## 1. Purpose and bottom line

The Charter requires lessons-learned reviews at Gates 3 and 5 and shared with partners (Charter Section 23), and the README assigns a reusable deployment playbook for Kenya to E3. The Final Evaluation Report (E2) answers whether OpenEMS is viable. This document (E3) answers the next question: **if it is viable, how does someone else do it, at what cost, in which conditions, and what should they avoid?** It has two halves. Part A is the lessons system: how lessons are captured during the pilot, rated, checked against evidence and turned into guidance. Part B is the replication guide: the sequence, decision rules, requirements and templates a utility, developer, C&I host, mini-grid operator or charging operator would follow.

**Status note.** No site is selected, built or measured, and no lesson exists yet. This version is therefore a **pre-populated guide template**. The capture method, lesson record, evidence rules, guide structure, go/no-go logic and templates are fixed now. Every finding, number and "what worked" field is completed from the pilot record in Months 12 to 24. Statements in Part B that read as guidance are **hypotheses carried from the programme documents, marked [H]**, until the pilot confirms, changes or removes them. Nothing here may be used to state or imply a result.

**Bottom line.** A replication guide is only as honest as its evidence. Ten rules govern it:

1. **Every lesson cites evidence.** A lesson links to a D5 entry, a test record, a monthly report, a survey or a log. A remembered opinion is recorded as a "view", not a lesson.
2. **Guidance cites the finding it rests on.** Each instruction in Part B carries an evidence tag: **[H]** hypothesis, **[P]** pilot-supported, **[C]** pilot-contradicted and changed, **[N]** not tested.
3. **Replication cost excludes research overhead.** Costs are given as pilot cost and replication cost, and a replicator is told which applies (Feasibility Study 5.4).
4. **Say where it does not pay.** The guide states the conditions under which replication is not advisable, as prominently as where it is (E2 Section 14).
5. **Per scenario, not national.** Three sites support three scenario playbooks (C&I, rural microgrid, EV depot). No national roll-out claim is made.
6. **Results apply to the tested set.** Hardware, firmware, OpenEMS release and driver findings are version-pinned (B6). The guide says so, and tells replicators to retest.
7. **Negative lessons have equal prominence.** Failed tests, rollbacks, delays, incidents, null results and abandoned approaches are recorded with the same weight as successes (Charter Section 21).
8. **Blameless capture, accountable follow-through.** People are never penalised for a lesson. Every lesson that needs action has an owner and a date.
9. **Open by default, safe by review.** The guide, templates and sanitised lessons are published after the Panel accuracy check and the security and privacy review. Credentials, live network details, unpatched vulnerabilities, personal data and host-confidential data are withheld.
10. **Built to be reused locally.** Written for Kenyan conditions, in plain English with Kiswahili summaries, so a local team can use it without the programme.

**What cannot be settled from desk research.** Real durations, real driver effort, real replication costs, real regulatory lead times and real failure modes. The guide fixes the structure and leaves those as placeholders.

## 2. Document control and relationships

**Owner:** Technical Lead (README E3). **Contributors:** Programme Manager and PMO, Research Lead and data analyst, software engineer, site engineer, Site Leads, Cybersecurity and Data Protection Officer, Capacity-building lead, Legal and regulatory lead, procurement lead, finance lead, university partner, Kenya Power grid engineer (TWG). **Review:** independent reviewer (Charter Section 23), Research and Evaluation Panel for any claim drawn from results, security and privacy review before release. **Approval:** Programme Director. Structure approved at Gate 1, lessons captured continuously from Gate 2, first consolidated lessons review at Gate 3, version 1.0 of the guide issued at Gate 5. Changes follow Charter Section 20.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 5, 7, 16, 21, 23, 24) | Scope limits, success criteria, lessons-learned reviews, open publication, closure and custodians |
| Final Evaluation Report (E2, Sections 9, 12 to 14) | Verdict, lessons themes, recommendations, replication cost, conditions. E3 turns these into method |
| Interim Evaluation Report (E1, Sections 9, 11, 13) | Diagnosis order, course-correction log, interim lessons |
| Feasibility Study (Sections 5.4 to 5.6, 9, 12) | Replication cost, break-even logic, risks, Gate 1 conditions |
| Monitoring and Evaluation Plan (D1) | KPI definitions and baseline method a replicator needs to prove results |
| Monthly Performance Reports (D6) | Evidence source and report format reused by replicators |
| Incident and Change Log (D5) | Primary evidence for operational, safety and security lessons |
| Interoperability Register (B6), Configuration Baseline (C4) | Device, driver, release and configuration findings, version-pinned |
| Technical Specification (B4), Installation Plan (C3), Acceptance Tests (C5) | Design rules, build sequence and test sets the guide generalises |
| Regulatory Compliance Assessment (B5), Cybersecurity Plan (B7), Data Plan (D2) | Regulatory, security and privacy playbooks |
| Procurement Plan (C1), Budget tracker (C2), Techno-economic model (B2) | Procurement lessons, actual cost, replication cost model |
| HSE Plan (C6), O&M Manual (D3), Training Records (D4) | Safety, operating and capacity lessons |
| Stakeholder Engagement Plan | Community, host and regulator engagement lessons |
| Policy brief (E4), Release package (E5), Paper (E6) | Share findings and open artefacts with E3 |
| Risk Register (A6) | Final risk status and risks that became lessons |

## 3. Scope and audience

**In scope.** Capture, validation and publication of lessons from lab testing (Month 4) to closure (Month 24); a replication guide for three scenarios; replication cost model; go/no-go screening; step sequence with gates; playbooks for compatibility, regulation, security, measurement, community, training, operations and closure; checklists and templates.

**Out of scope.** Core OpenEMS development beyond drivers and configuration (Charter Section 5); changes to tariffs or regulation (E4 informs these); commercial roll-out beyond the three pilots; legal advice. Replicators must take their own advice from advocates, insurers and licensed engineers.

| ID | Audience | What they need from E3 |
| --- | --- | --- |
| R-A | C&I hosts and campus managers | Whether it pays for their load and tariff, what it costs, what changes at site |
| R-B | Mini-grid operators, cooperatives, estates, utilities | Whether it helps losses and reliability, community and licensing path, operator model |
| R-C | EV charging operators and fleets | Whether managed charging protects the transformer without unacceptable delay |
| R-D | Developers, EPCs and integrators | Compatibility method, driver effort, commissioning sequence, risks |
| R-E | Kenya Power and other utilities | Interconnection, data, control boundary, incident notification |
| R-F | EPRA and Ministry of Energy | Where rules created friction, what evidence supports changes |
| R-G | Funders | Replication cost, conditions, what to fund and not fund |
| R-H | Universities, training bodies, OpenEMS community | Curriculum, drivers, test method, upstream contributions |

## 4. Principles

| Principle | What it means in practice |
| --- | --- |
| Evidence tagged | Every instruction is [H], [P], [C] or [N] and shows the lesson ID behind it |
| Conditions before claims | Each recommendation states the condition under which it holds (tariff, size, hardware class, topology) |
| Honest about cost | Integration, skills and service cost are shown, not hidden behind "free software" |
| Specific and usable | Steps, owners, durations and tests, not slogans |
| Proportionate | The guide scales from a single-site C&I project to a village microgrid. It does not require pilot-level research governance from a commercial replicator |
| Separate what is essential from what was research | Replicators are told which pilot controls were for the evaluation (for example independent research meters, pre-registration) and which were for safety or security |
| Safety and security are not optional | Hold points, hardware protection, no remote path before audit and licensed contractors stay in every scenario |
| Local ownership | Local trainers, operators and service providers are named as part of the method |
| Living document | The guide is versioned, owned by a named custodian, and updated from replication experience |

## 5. Roles and responsibilities

| Role | Responsibility |
| --- | --- |
| Steering Committee | Receives the lessons summaries at Gates 3, 4 and 5. Approves publication and custodian |
| Programme Director | Accountable for the lessons process and for release of the guide |
| Technical Lead (E3 owner) | Owns method and the guide. Chairs the lessons reviews. Approves technical guidance |
| Programme Manager and PMO | Runs the lessons register, schedules reviews, tracks actions, links lessons to the risk register |
| Research Lead | Verifies that guidance drawn from results matches E2 and the Panel-validated data. Owns the limits statements |
| Software engineer | Integration, driver, configuration and test lessons. Maintains example configurations |
| Site engineer and Site Leads | Build, safety, operations and community lessons from their site. Capture at hold points |
| Cybersecurity and Data Protection Officer | Security and privacy lessons. Release review of every public output |
| Legal and regulatory lead | Regulatory, licensing, contracting and tax lessons |
| Procurement lead and finance lead | Procurement, price, lead time, duty and cost lessons. Replication cost model inputs |
| Capacity-building lead | Training and retention lessons, curriculum reuse |
| University partner | Independent facilitation of lessons workshops, synthesis support, co-authorship |
| Independent reviewer | Reviews each version for balance and evidence |
| Custodian (named at Gate 5) | Maintains the guide after the pilot |
| Hosts, operators, community members, drivers, vendors, Kenya Power, EPRA | Contribute views through structured sessions. Review before publication |

## 6. Part A: The lessons system

### 6.1 What counts as a lesson

A lesson is a **statement of what happened, why, and what to do differently or the same**, backed by evidence. Types:

| Type | Meaning | Example prompt (not a finding) |
| --- | --- | --- |
| L-W | Worked, repeat it | A step, tool or arrangement that saved time or prevented a problem |
| L-F | Failed or underperformed, avoid or change it | A device, method or assumption that did not hold |
| L-S | Surprise, not anticipated | An event or effect nobody planned for |
| L-G | Gap, missing knowledge or capability | Something the team had to improvise |
| L-C | Cost or time driver | Where cost or duration differed from plan, with numbers |
| L-V | View, opinion without evidence | Recorded, tested later, not published as a lesson |

### 6.2 Capture points

| When | Trigger | Method | Owner |
| --- | --- | --- | --- |
| Continuously | Any D5 entry of priority P1 to P3, any failed change, any failed test | "Lesson flag" field on the entry (Section 6.4) | Site Lead, Technical Lead |
| Each hold point H0 to H8 | Close of the hold point | 15-minute after-action review with the crew and host | Site Lead |
| Each stage gate | Gates 1, 2, 3, 4, 5 | Facilitated lessons review (Section 6.5) | Programme Manager |
| After compatibility campaign | End of lab campaign | Review of B6 results, driver effort and vendor behaviour | Software engineer |
| After tender award | Award at Gate 2 | Procurement review (price, lead time, bidders, local service) | Procurement lead |
| After the independent audit | Audit report received | Security review of findings and what the design missed | Cybersecurity Officer |
| After any Class 1 or 2 incident | Investigation closed | Blameless review output (C6 Section 14.2) | Programme Director |
| Quarterly | Every quarter in operation | Operator and host check-in focused on routines, spares and service | Site Lead |
| Community and driver feedback | Quarterly and at Gates 3, 5 | Structured sessions, separate for women, youth, small businesses | Community liaison, Site Leads |
| Closure | Months 22 to 24 | Synthesis workshop across sites, with regulators and utility | Technical Lead, university partner |

### 6.3 Rules for capture

1. **Capture within [5] working days** of the trigger, while detail is fresh. A late capture is marked late, not refused.
2. **Write in plain language** and in the language of the person speaking where possible, translated later.
3. **Separate fact from interpretation.** The record has distinct fields for what happened, evidence, cause and recommendation.
4. **Record the condition.** Tariff, size, topology, firmware, season, vendor, team experience.
5. **Record who was affected**, in roles, not names, where personal data could be exposed.
6. **No blame language.** The cause is stated as process, information, equipment or decision, not as a person.
7. **Restricted material goes in the restricted field** (credentials, network detail, host-confidential data, personal data, unpatched vulnerabilities), per D5 Section 11 and D2.

### 6.4 Lesson record

| Field | Entry |
| --- | --- |
| Lesson ID | `LL-[theme code]-[number]` (theme codes in Section 7) |
| Date, captured by (role), capture point | [ ] |
| Site, pilot, phase, hold point or gate | [ ] |
| Type (L-W, L-F, L-S, L-G, L-C, L-V) | [ ] |
| What happened (facts only) | [ ] |
| Conditions (tariff, size, topology, device and firmware, season, team) | [ ] |
| Evidence references (D5, B6, C5, D6, survey, photo, log, interview) | [ ] |
| Cause and contributing factors | [ ] |
| Effect on safety, evidence quality, cost, schedule, community | [ ] |
| Number attached (hours, days, KSh, %, count) with source, if any | [ ] |
| Recommendation to a future replicator | [ ] |
| Evidence tag for the recommendation ([H], [P], [C], [N]) | [ ] |
| Action for the programme (owner, due, verification), if any | [ ] |
| Generalisable beyond this site? (Y/N, why) | [ ] |
| Restricted content present (Y/N) | [ ] |
| Review status and reviewer (technical, research, security, independent) | [ ] |
| Published form (full, sanitised, summary, not published) and date | [ ] |
| Linked guide section | [ ] |

### 6.5 Lessons reviews

| Review | Timing | Participants | Output |
| --- | --- | --- | --- |
| Gate 3 review | Month 12 | Programme team, Site Leads, installers, host representatives, Kenya Power, operators, a Panel member | Build and commissioning lessons, first guide draft of Sections 11 to 16, action list (Charter Section 23) |
| Gate 4 review | Month 18 | Programme team, Panel, operators, hosts, community liaison | Operations, cost and early results lessons, guide revision, link to E1 corrections |
| Gate 5 review | Month 24 | All of the above, regulators, funders, university, vendors | Final lessons, guide v1.0, E4 and E2 cross-check |

**Format.** A neutral facilitator (university partner or independent) runs a structured session: what was planned, what happened, why, what to keep, what to change. Quieter voices are heard first, with separate sessions for women, youth and small businesses where relevant (Stakeholder Plan Section 3). Dissenting views are recorded. Results are circulated for comment within [10] working days.

### 6.6 Validation of a lesson before it enters the guide

| Test | Question | Fail action |
| --- | --- | --- |
| Evidence | Is there at least one cited record, and does it say what the lesson says? | Downgrade to L-V |
| Condition | Are the conditions stated and are they likely to recur for a replicator? | Narrow the claim |
| Independence | Was it seen at more than one site, or by more than one observer, or can it be explained by one site's peculiarity? | Label "single-site" |
| Consistency with E2 | Does it match validated results and the Panel's limits? | Research Lead resolves or removes |
| Security and privacy | Could publishing it expose a vulnerability, a person or a host? | Sanitise or withhold |
| Usefulness | Does it change what a replicator would do? | Merge or drop |
| Balance | Is the negative side of the story included? | Reviewer adds |

### 6.7 Evidence tags in the guide

| Tag | Meaning | How the guide treats it |
| --- | --- | --- |
| [H] | Hypothesis carried from the programme documents. Not yet tested | Presented as "plan", with a note to verify |
| [P] | Pilot-supported. Evidence cited, conditions stated | Presented as guidance, with lesson IDs |
| [C] | Pilot-contradicted. The original assumption was changed | Presented with the old assumption and the reason it changed, so replicators do not repeat it |
| [N] | Not tested in the pilot | Listed as an open question, with the suggested way to test it |

At v1.0 no [H] may remain in a safety-critical instruction. It is either confirmed, changed or moved to [N] with a warning.

### 6.8 Link to risks, action and course correction

A lesson with an action goes to the PMO action log. A lesson that shows a risk could recur adds it to the Risk Register (A6). Lessons that touch KPI definitions, baselines or methods are **not** used to alter the live experiment. They go to E2 and E3 and, if they require a change to the live plan, through SteerCo approval on Panel advice (Charter Section 20, E1 Section 11.1).

## 7. Lesson themes and what to capture

Each theme has a code, a lead and seeded questions. The questions are prompts. The answers are findings and must come from the record. Charter and document hypotheses to test are shown as [H] in the third column.

| Code | Theme | Lead | Seeded questions | Hypotheses to test [H] |
| --- | --- | --- | --- | --- |
| COM | Compatibility and integration | Software engineer | Which devices passed L3 and L4, which failed, and why? Actual driver effort by route R1 to R5 against the S/M/L/XL scale. What did vendors refuse or delay? Did existing Pilot A inverters open to control? Did chargers accept in-session limits? | The real cost of "free" software is integration and skills (Feasibility Study 5.2). Existing driver availability must be checked against the pinned release, not assumed. A failure found early costs less than a failure at site |
| PRO | Procurement and supply | Procurement lead | Number of qualified bidders, local service evidence, bid versus estimate, lead times, duty and VAT outcome, exchange-rate effect, early-order use, loan units | Thin competition for OpenEMS-compatible, serviceable devices (C1 risk PR1). Lead time is the main schedule risk |
| REG | Regulation and licensing | Legal and regulatory lead | Time and outcome of EPRA position on BESS, mini-grid, EV charging and net-metering. Exemption or sandbox used? Kenya Power interconnection lead time and conditions. Any proposal to change rules | Regulatory clarity is the critical path (Feasibility Study 12.3). Written positions requested in Month 1 save time |
| CON | Contracting, title, insurance | Programme Sponsor, counsel | Which entity contracted, equipment title choice and effect, insurer conditions on batteries, benefit-sharing choice, decommissioning terms | No named contracting entity blocks procurement (Feasibility Study risk 11). Benefit sharing affects the baseline |
| DES | Design and sizing | Technical Lead | Did measured load confirm the 250 kWh and 200 kWh sizes? What changed after survey data? Pilot B topology decision. Pilot C site limit versus nameplate | The sizing method gives different answers from the Charter reference sizes (B4 open item 1) |
| BLD | Build and commissioning | Site Leads | Hold point slips, delivery delays, punch-list themes, L3 versus L4 differences, supply interruptions, commissioning duration per site | Four months from award to go-live is compressed (C1, C3). Pilot B is most likely to slip |
| SAF | Safety, health and environment | Site engineer | Incidents and near misses, fire design lessons, responder familiarisation, insurer acceptance, waste and take-back, community safety | Battery fire is low likelihood and high impact. Remote response time is a Pilot B issue |
| SEC | Cybersecurity and data protection | Cybersecurity Officer | Audit findings by severity, what the design missed, vendor remote paths found, drift events, offline operation, pseudonymisation experience, consent experience | Late audit findings can delay Gate 3 (B7 risk C1). Vendors may leave remote paths (B7 T13) |
| OPS | Operations and maintenance | Technical Lead, Site Leads | Faults by class, repair time, spares used, alarm response quality, override use, operator workload, what the manual got wrong | Remote service is slow (O&M risk OM3). Alarm fatigue is a risk |
| MEA | Measurement and evaluation | Research Lead | Baseline length used, counterfactual fit, meter issues, data completeness, confounders found, what the pre-registration protected or prevented | Short baseline plus counterfactual preserves 12 months of controlled data (D1 7.3). Host behaviour confounds the comparison |
| ECO | Economics | Techno-economic analyst | Where bills, diesel, reliability and asset protection actually paid. Actual net benefit, payback, break-even. Cost of pilot versus replication. Sensitivity to export credit | Sites with small bills will not pay back from bill savings alone (Feasibility Study 5.5). Savings may fall below 15 to 30% |
| SOC | Community, host and users | Site Leads, liaison | Consent process, complaints, expectations, throttling reactions, supply continuity, local labour, inclusion results | Community expectations exceed what a pilot can deliver (Stakeholder Plan risk). Drivers may tamper if throttling is unexplained |
| CAP | Capacity and training | Capacity-building lead | Trainees nominated, assessed competent, retained, time to competence, trainer bench, what training was missing | Operators need supervised on-site practice. Retention is a risk |
| GOV | Governance and delivery | Programme Manager | Which decisions were slow, where the gates helped or hindered, stop-or-extend use, contingency use, reporting burden | Proportionate governance may be heavy for small teams (D6 risk MP8) |

Lessons from every theme must also state, where known, **what a replicator at commercial scale could drop** because it existed only for research.

## 8. Part B: Replication guide

### 8.1 How to use the guide

1. Read Section 9 (before you start) and complete the screening in Section 10.
2. Choose the scenario playbook in Sections 18 to 20.
3. Follow the step sequence in Section 11, applying the playbooks in Sections 12 to 17.
4. Use the cost model in Section 21 and the checklists in the appendices.
5. Tag your own findings against this guide and send them to the custodian.

### 9. Before you start: the honest summary

This section is completed at Gate 5 from E2 Section 9.4. The wording below is the structure. **Do not publish it with placeholders.**

| Question | Answer from the pilot | Evidence tag |
| --- | --- | --- |
| Did OpenEMS work technically in Kenya on the tested hardware? | [ ] | [ ] |
| Did it save money, and how does that compare with the 15 to 30% range? | [ ] | [ ] |
| Did it reduce losses or improve reliability at the microgrid? | [ ] | [ ] |
| Did managed charging protect the transformer without unacceptable delay? | [ ] | [ ] |
| What were the main surprises? | [ ] | [ ] |
| What would we do differently? | [ ] | [ ] |
| Who should not replicate, and when? | [ ] | [ ] |
| What does it cost to replicate, and what does it need? | [ ] | [ ] |

### 10. Go/no-go screening for a replicator

Screening is done before any spend. Each question is answered Yes, No or Unknown. An Unknown on a safety, regulatory or economic gate is treated as No until evidenced.

#### 10.1 Common gates

| # | Gate | Question | Evidence needed | Tag |
| --- | --- | --- | --- | --- |
| G1 | Legal entity | Is there a legal person that can sign, insure and hold equipment title? | Registration, authority to sign | [H] |
| G2 | Regulatory position | Do you have a written EPRA position on licensing of the battery, charging or mini-grid activity, and net-metering eligibility if exports are involved? | EPRA letter or documented exemption | [H] |
| G3 | Utility path | Has Kenya Power confirmed interconnection requirements and timelines in principle? | Letter or meeting record | [H] |
| G4 | Safety path | Can you meet battery fire, insurer, licensed-contractor and responder requirements for the site? | Fire assessment plan, insurer view | [H] |
| G5 | Security path | Can you keep programme devices separate from host IT and disable remote access until audited? | Network design | [H] |
| G6 | Skills and service | Is there a named operator, a backup and a local service route for each device? | Names, vendor letters | [H] |
| G7 | Data | Can you get at least 12 months of interval load and bill data (A, C) or a defensible estimate (B)? | Data received | [H] |
| G8 | Hardware | Is each device on the compatibility register at a pass level for your OpenEMS release, or can you afford to test it? | B6 record or test budget | [H] |
| G9 | Money | Does the net benefit reach break-even on replication cost under pessimistic sensitivities? | Model output | [H] |

#### 10.2 Scenario gates

| Scenario | Additional gate | Rule of thumb to confirm [H] |
| --- | --- | --- |
| C&I (A) | Tariff has a meaningful ToU spread or demand charge, or net-metering with a 50% export credit makes self-consumption valuable | If neither exists, peak shaving and ToU shifting earn little (B4 Section 5.2). Replicator should not proceed on bill savings alone |
| C&I (A) | Existing inverters open to control without voiding warranty | Written vendor permission or a funded remedy (B6, C1 package P8) |
| C&I (A) | Bill base large enough for the battery capex | Use the break-even arithmetic (Feasibility Study 5.5). A site with USD 100k net capex and an eight-year payback needs about USD 12.5k net benefit a year [H, illustration only] |
| Rural microgrid (B) | Defined operator and tariff arrangement consistent with EPRA mini-grid requirements | Resolve before community consent (B5 Section 5.3) |
| Rural microgrid (B) | Informed community agreement and a no-disconnection, no-price-rise commitment | No works without it (C3 Section 10) |
| Rural microgrid (B) | A method to measure losses, or acceptance that only reliability and diesel offset will be claimed | Technical versus commercial split may not be defensible (B4 Section 6.4) |
| Rural microgrid (B) | Service and spares reachable within an agreed time | Remote locations make this the main O&M risk |
| EV depot (C) | Chargers accept dynamic power limits in session and speak a supported OCPP version | A charger that cannot limit in session fails (B6 T-EVC-02) |
| EV depot (C) | Transformer loading data with a response time suited to control | Depends on Kenya Power data access (B4 open item 5) |
| EV depot (C) | Charging policy and maximum wait agreed with the operator and displayed | Needed before go-live (C3 Section 11) |

**Decision rule.** All common gates Yes, scenario gates Yes, and the break-even test passed under the pessimistic case: proceed to detailed design. Any No: fix the gap or do not proceed. State the outcome and the reason in writing.

### 11. Step sequence (all scenarios)

Durations are placeholders to be replaced from the pilot record. The sequence follows the Charter gates and is shown at the weight a commercial replicator needs. Steps marked **R** exist for research and may be dropped or lightened by a replicator that does not need independent evidence. Steps marked **S** are safety or security and are never dropped.

| Step | Name | Key outputs | Typical duration (pilot) | Typical duration (replicator) | Type | Playbook |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Screening and business case | Go/no-go (Section 10), break-even | [ ] | [ ] | | 10, 21 |
| 2 | Entity, title, insurance, contracts | Legal entity, host agreement, insurer view | [ ] | [ ] | | 12 |
| 3 | Written regulator and utility positions | EPRA letter, Kenya Power in-principle | [ ] | [ ] | | 12 |
| 4 | Site survey and data collection | Survey, load and tariff data, red items | [ ] | [ ] | | 13 |
| 5 | Sizing and design | Sizing note, single-line diagram, topology, safe states | [ ] | [ ] | S | 13 |
| 6 | Compatibility testing | Test record per device at L3 | [ ] | [ ] | S | 14 |
| 7 | Procurement | Contracts with warranty, service, security clauses | [ ] | [ ] | | 15 |
| 8 | Measurement plan and baseline design | Meter plan, baseline rule, KPI definitions | [ ] | [ ] | R (lightened) | 16 |
| 9 | Safety plans and permits | Fire assessment, method statements, permits, insurer acceptance | [ ] | [ ] | S | 17 |
| 10 | Installation | Installed, un-energised system, as-builts | [ ] | [ ] | S | 17 |
| 11 | Hardware proof and energisation | Protections proven with OpenEMS not in command | [ ] | [ ] | S | 17 |
| 12 | OpenEMS commissioning and acceptance | L4 tests, safe states, offline, restore | [ ] | [ ] | S | 17 |
| 13 | Security review and audit | Audit or independent review, no remote path before pass | [ ] | [ ] | S | 14 |
| 14 | Training and handover | Operators competent, backup, manual | [ ] | [ ] | S | 17 |
| 15 | Baseline, go-live and monitoring | Baseline recorded, controlled operation, monthly reports | [ ] | [ ] | R (lightened) | 16 |
| 16 | Review, optimise within rules, close or continue | Review, lessons, post-pilot plan | [ ] | [ ] | | 17, 22 |

**Sequence rules.** [H] Do not buy before compatibility is proven. [H] Do not energise before hardware protections are proven independent of OpenEMS. [H] Do not connect remotely before the security review is passed. [H] Do not switch control mode on an ad hoc basis if you intend to claim savings. These are confirmed, changed or removed at Gate 5.

### 12. Playbook: contracts, regulation and utility

| Topic | What to do | What the pilot showed | Tag |
| --- | --- | --- | --- |
| Entity and title | Name the contracting entity and decide equipment title and decommissioning cost before any tender | [ ] | [H] |
| Regulator request | Send one structured written request to EPRA and Kenya Power early, using the question set in B5 Appendix A | Time to answer: [ ] days. What was refused or unclear: [ ] | [H] |
| Exemption or sandbox | Ask whether a time-limited pilot or small installation qualifies. Annex any conditions to the agreements | [ ] | [H] |
| Net-metering | Confirm eligibility, size cap and whether adding storage needs a new application. Model export credit at and below 50% | [ ] | [H] |
| Interconnection | Apply early. Agree protection, metering and anti-islanding. Confirm control boundary: assets behind the connection only | Lead time: [ ] weeks. Conditions: [ ] | [H] |
| Data sharing | Agree feeder and transformer data, read-only, with roles and retention | [ ] | [H] |
| Insurance | Engage the insurer on the battery before design is fixed | Conditions imposed: [ ] | [H] |
| Contracts | Include warranty permission for third-party control, firmware hold, no undocumented remote access, local service, take-back, security clauses | Clauses vendors resisted: [ ] | [H] |
| Host agreement | Baseline and test period consent, benefit sharing, override right, no price rise at microgrid, data roles, safe states | [ ] | [H] |

### 13. Playbook: survey, data and design

| Topic | What to do | What the pilot showed | Tag |
| --- | --- | --- | --- |
| Data first | Obtain 12 months of interval load and bills before sizing. For microgrids, get the best estimate and plan check meters | Data actually obtainable: [ ] | [H] |
| Tariff check | Read the tariff for ToU spread and demand charges before designing for peak shaving or shifting | [ ] | [H] |
| Sizing method | Size from measured load using the B4 Section 4 method. Do not copy the Charter reference sizes | Size changes found: [ ] | [H] |
| Existing equipment | Record make, model, firmware and warranty of existing inverters at survey | Red items found: [ ] | [H] |
| Topology (B) | Decide grid-connected, mini-grid with grid or isolated before choosing the battery inverter | [ ] | [H] |
| Transformer limit (C) | Set the site limit below the safe transformer limit with Kenya Power approval. Lower first, raise only with agreement | [ ] | [H] |
| Safe states | Define safe state per device and per site before procurement | [ ] | [H] |
| Siting | Fire separation, ventilation, flood, lightning, theft and responder access | [ ] | [H] |
| Survey red items | Treat an unknown critical item as red until evidenced | Closure time: [ ] | [H] |

### 14. Playbook: compatibility, drivers and security

| Topic | What to do | What the pilot showed | Tag |
| --- | --- | --- | --- |
| Compatibility levels | Use L0 to L4. Require L3 in the lab before award and L4 at site | Pass and fail record: [ ] | [H] |
| Release pinning | Pin the OpenEMS release and test the combination. Retest on any firmware, driver or release change | Delta tests triggered: [ ] | [H] |
| Driver routes | Prefer R1 to R3. Treat R4 and R5 as cost and risk drivers | Effort by route: [ ] person-days. Upstreamed: [ ] | [H] |
| Vendor commitments | Collect protocol documents, warranty permission, firmware policy and service commitment in writing before award | Refusals: [ ] | [H] |
| Chargers | Prove in-session power limiting per model and OCPP version. Do not rely on simulators for award | [ ] | [H] |
| Generators and existing PV | Expect weak digital interfaces. Plan relay or gateway routes and warranty checks | [ ] | [H] |
| Local first | Keep protection and control on site. Prove offline operation for the required duration | Result: [ ] | [H] |
| Hardware protects | Prove BMS, inverter, breaker and fire protections with OpenEMS not in command | [ ] | [H] |
| Remote access | Disable until a security review is passed. Then outbound-only, encrypted, multi-factor, logged | Findings: [ ] | [H] |
| Network | Separate programme devices from host IT. No path from host IT. No open inbound ports | [ ] | [H] |
| Accounts and secrets | Named accounts only. No shared logins. Unique secrets per site. No secrets in repositories | [ ] | [H] |
| Configuration control | Keep configuration under version control with hashes, a manifest and a protected safety layer | Drift events: [ ] | [H] |
| Audit | Use an independent auditor with no vendor relationship. Treat critical findings as blocking | Findings by severity: [ ] | [H] |
| Lite option for small replicators | A small commercial replicator may use an independent security review instead of a full audit, with the same blocking rule for critical findings | Not tested | [N] |

### 15. Playbook: procurement and supply

| Topic | What to do | What the pilot showed | Tag |
| --- | --- | --- | --- |
| Two-stage approach | Pre-qualify on documents, service and commitments, then invite shortlisted bids with test units | Bidders per lot: [ ] | [H] |
| Compatibility as a gate | A device that fails the gate is not scored | [ ] | [H] |
| Local service | Treat local service route, response time and spares as pass or fail for devices you cannot replace yourself | [ ] | [H] |
| Total cost | Compare on total cost of ownership including integration, service and end of life | Price spread: [ ] | [H] |
| Lead times | Ask for lead times early. Consider a conditional early order for long-lead items | Lead times: batteries [ ] weeks, chargers [ ] weeks | [H] |
| Duties and exchange | Fix the price basis and adjustment rule. Seek advice on duty and VAT relief | Actual duty effect: [ ] | [H] |
| Loan units | Accept loan units for testing but declare them and never make them a condition of award | [ ] | [H] |
| Contract terms | Milestone payments, performance security, liquidated damages, firmware hold, take-back, no undocumented remote path | [ ] | [H] |

### 16. Playbook: measurement, baseline and proof of savings

This playbook has two levels so a replicator takes what it needs.

| Level | Purpose | Elements | Tag |
| --- | --- | --- | --- |
| Operational proof | A host or operator wants to know if it pays | Revenue-grade meter at the connection, tariff-aware bill comparison, a documented baseline period or counterfactual from historical data, a log of confounders, monthly review | [H] |
| Evidence-grade proof | A funder, regulator or developer needs a defensible claim | Independent research meters and logger, pre-registered analysis plan, counterfactual model with out-of-sample error, uncertainty with every KPI, signed mode records, independent review | [H] |

| Topic | What to do | What the pilot showed | Tag |
| --- | --- | --- | --- |
| Baseline | Run a baseline with storage idle or unmanaged, or build a counterfactual from at least 12 months of history | Baseline length used: [ ]. Adequacy: [ ] | [H] |
| Mode discipline | Switch control modes only on a written schedule. Log every switch | [ ] | [H] |
| Confounders | Log new loads, tariff changes, outages, maintenance and host behaviour changes | Confounders that mattered: [ ] | [H] |
| Mechanism | Credit savings only where the mechanism is visible in the data | [ ] | [H] |
| Uncertainty | Report intervals. State when the effect is not distinguishable from zero | [ ] | [H] |
| Microgrid losses | Plan check meters and an energy balance. Say plainly if technical and commercial losses cannot be separated | Separable: [ ] | [H] |
| EV delay | Reconstruct unconstrained demand from session data and report wait distribution | [ ] | [H] |
| KPI dictionary | Reuse the definitions in D1 Appendix A so results are comparable | [ ] | [H] |

### 17. Playbook: safety, build, training, operations and closure

| Topic | What to do | What the pilot showed | Tag |
| --- | --- | --- | --- |
| Fire and battery | Complete a site-specific fire risk assessment with specialist input before the battery is delivered. Engage responders and the insurer | [ ] | [H] |
| Licensed work | Use licensed contractors. Named supervisors. Permit to work | [ ] | [H] |
| Hold points | Treat hold points as stops. No energisation, OpenEMS enablement or go-live without a signed hold point | Hold points that caught problems: [ ] | [H] |
| Staged energisation | Hardware proof, then read-only communication, then writes, then controllers one at a time | [ ] | [H] |
| Supply continuity (B) | Agree outage windows and a rehearsed transfer plan | Interruptions: [ ] | [H] |
| Public interface (C) | Separate public from works. Explain throttling on signage. Display policy | Complaints: [ ] | [H] |
| Operators | Name a primary and a backup. Teach what operators must not do. Do not let operators tune | Time to competence: [ ] | [H] |
| Training | Competence is assessed and observed, not attended. Include supervised on-site practice | Pass and retake rates: [ ] | [H] |
| Operations | Daily and weekly routines, alarm card, no-reset rule, return-to-service checklist, escalation ladder | Faults and repair times: [ ] | [H] |
| Spares and service | Hold critical spares on or near site. Agree service response in contract | [ ] | [H] |
| Logs | Keep an incident and change log and use it for every configuration change | [ ] | [H] |
| Community | Informed agreement before works, honest research or commercial messaging, grievance channel, no promises beyond the agreement | [ ] | [H] |
| Closure | Decide ownership, decommissioning, data deletion and custodian before procurement. Brief the receiver in writing | [ ] | [H] |

## 18. Scenario playbook A: C&I facility, industrial park or campus

| Item | Content (completed from the pilot) |
| --- | --- |
| Who it suits | [ ] (for example, loads with high peak share and meaningful tariff structure) |
| Who it does not suit | [ ] |
| Configuration that was tested | About 250 kWh battery, existing or new PV, Edge, grid and research meters (sizes as finally confirmed: [ ]) |
| Value drivers that paid | Peak or demand charge [ ]; ToU shifting [ ]; export credit and self-consumption [ ] |
| Measured result vs 15 to 30% range | [ ] with interval and conditions |
| Replication cost and payback | [ ] and sensitivities. Break-even conditions: [ ] |
| Critical steps | Tariff check, net-metering confirmation, existing inverter warranty, battery room fire design, host IT separation, protected loads and override |
| Typical problems | [ ] (for example inverter interface, host shutdown coordination, confounding load changes) |
| What to drop or lighten for commercial replication | [ ] |
| What must never be dropped | Licensed work, fire design and insurer acceptance, hardware protection proof, no remote path before review, safe states, logged changes |

## 19. Scenario playbook B: Rural microgrid

| Item | Content (completed from the pilot) |
| --- | --- |
| Who it suits | [ ] (for example operators with defined governance, long feeders, measurable diesel use) |
| Who it does not suit | [ ] |
| Configuration that was tested | 50 to 100 kW PV, about 200 kWh battery, Edge, dual-link router, check meters, generator interface if present (final: [ ]) |
| Topology | [grid-connected, mini-grid, isolated] and why |
| Value drivers | Diesel offset [ ]; reliability [ ]; self-consumption [ ]; loss reduction [ ] or "not separable" |
| Measured result | [ ] with limits statement |
| Replication cost | [ ] with operator and service costs |
| Critical steps | Operator and tariff arrangement, informed community agreement, topology decision, check meters, connectivity fallback, theft protection, spares and service, no-disconnection commitment |
| Typical problems | [ ] (for example logistics, theft, connectivity, community expectations) |
| Operator model that worked | [host staff / cooperative / vendor / hired], with stipend and retention results [ ] |
| What to drop or lighten | [ ] |
| What must never be dropped | Community agreement, licensed work, fire and lightning protection, local control offline, safe states, emergency plan suited to long response times |

## 20. Scenario playbook C: EV charging depot

| Item | Content (completed from the pilot) |
| --- | --- |
| Who it suits | [ ] (for example sites where chargers could exceed transformer capacity) |
| Who it does not suit | [ ] |
| Configuration that was tested | 10 to 20 fast chargers, transformer and site meters, Edge, optional battery (final: [ ]) |
| Charger models and OCPP versions that passed | [ ] (pinned to firmware) |
| Policy and limit used | [fair-sharing or priority], maximum wait [ ], site limit [ ] |
| Measured result | Transformer loading [ ], full-capacity share [ ], wait distribution [ ] |
| Value | Avoided upgrade or outage cost only if supported by data: [ ] |
| Replication cost | [ ] |
| Critical steps | In-session power limit proof per charger model, transformer data path from Kenya Power, site limit agreement, driver signage, privacy notice, vendor cooperation |
| Typical problems | [ ] (for example vehicles that reject limiting, driver complaints, data response time) |
| What to drop or lighten | [ ] |
| What must never be dropped | Public separation during works, charger fallback limit, read-only utility data path, thermal safety, no payment data in analysis datasets |

## 21. Replication cost model

### 21.1 Principles

1. State **pilot cost** and **replication cost** separately. Replication cost excludes research overhead (independent meters beyond operational need, pre-registration, university research budget, public reporting).
2. Show the **integration and skills share**, not only equipment.
3. Show **ranges** and the sensitivities used (battery cost ±20%, discount rate 5 to 12%, export credit at and below 50%, tariff spread, inflation about 5%).
4. Show **what drives the range** (lead time, duty, driver effort, service distance, site works).

### 21.2 Cost structure template (per site type)

The Charter reference split is a guide only (Charter Section 8). Actual shares are completed from C2.

| Category | Reference share (Charter) | Pilot actual (A / B / C) | Replication estimate | Notes |
| --- | --- | --- | --- | --- |
| Hardware (PV, BESS, inverters, meters, chargers) | 40% | [ ] | [ ] | |
| Software and integration (including custom drivers, Edge, network) | 20% | [ ] | [ ] | Driver effort by size S, M, L, XL: [ ] |
| First-year O&M (service, spares, inspections) | 15% | [ ] | [ ] | |
| Installation and civil works | 10% | [ ] | [ ] | |
| Contingency | 10% | [ ] | [ ] | Actual use: [ ] |
| Training and capacity building | 5% | [ ] | [ ] | Tested for adequacy in the Feasibility Study (8.2) |
| Insurance, permits, legal and regulatory costs | not in reference | [ ] | [ ] | |
| Security review or audit | not in reference | [ ] | [ ] | |
| Safety and fire design, waste and take-back | not in reference | [ ] | [ ] | |
| Measurement and reporting (operational or evidence-grade) | not in reference | [ ] | [ ] | |
| Duties, taxes and exchange-rate effects | not in reference | [ ] | [ ] | |
| Decommissioning and end of life | not in reference | [ ] | [ ] | |

### 21.3 Viability test for a replicator

| Step | Calculation (illustration from the Feasibility Study, to be replaced with measured values) |
| --- | --- |
| 1 | Net capex after any grant: [ ] |
| 2 | Required annual net benefit for the target payback: capex divided by years. For example, USD 100k and eight years gives about USD 12.5k a year [H, illustration] |
| 3 | Required bill base at the measured saving: required benefit divided by saving rate |
| 4 | Test the pessimistic case: lower saving, lower export credit, higher battery cost, longer lead time |
| 5 | State which benefits are bills and which are diesel, reliability or asset protection |
| 6 | Decide: proceed, redesign, or do not proceed |

## 22. Common mistakes and early warnings

Completed at Gate 5 from L-F and L-S lessons. Each line is a real lesson with an ID or it is removed.

| # | Mistake or warning sign | Consequence seen | How to avoid | Lesson ID |
| --- | --- | --- | --- | --- |
| 1 | [ ] | [ ] | [ ] | `LL-[ ]` |
| 2 | [ ] | [ ] | [ ] | `LL-[ ]` |
| 3 | [ ] | [ ] | [ ] | `LL-[ ]` |

Early-warning indicators a replicator can watch (to be calibrated from the pilot): [for example a slipping hold point, a vendor delaying written warranty permission, a data gap above threshold, a drift alarm, a rising complaint rate].

## 23. Reusable artefacts

| Artefact | Source | Licence and route | Notes |
| --- | --- | --- | --- |
| Configuration templates and schema | C4 repository | Apache 2.0, sanitised | Version-pinned. Retest before use |
| Custom drivers and mappings | Drivers repository | Apache 2.0, upstream offered after TWG review | Component licences preserved (EPL 2.0, AGPL 3.0 for the UI) |
| Compatibility test sets and record templates | B6 | Open licence | Results apply only to tested versions |
| Site acceptance test scripts and checklists | C5 | Open licence | |
| Commissioning hold points and certificate | C3 | Open licence | |
| Safety plan, permit and emergency sheet templates | C6 | Open licence | Site-specific values must be added |
| Operator manual and alarm card templates | D3 | Open licence | Kiswahili versions |
| Training curriculum, assessments and certificate template | D4 | Open licence | Certificate is not a statutory licence |
| Incident and change register templates | D5 | Open licence | |
| KPI dictionary, report templates, analysis code | D1, D6, E5 | Open licence | Anonymised data only |
| Regulatory question set | B5 Appendix A | Open licence | Update with current rules |
| Tender templates and questionnaires | C1 | Open licence | Counsel review before use |
| Replication cost model | B2 and this document | Open licence | Inputs must be replaced with replicator data |

Withheld: credentials, live network details, host-confidential data, personal data, unpatched vulnerabilities (C4 Section 14, D2 Section 10).

## 24. Publication and disclosure

| Item | Rule |
| --- | --- |
| Review chain | Technical review, Research Lead check against E2, security and privacy review, independent reviewer, Programme Director approval (Charter Section 21) |
| Directly involved parties | Hosts, Kenya Power, EPRA, vendors named in lessons and communities see relevant lessons before release. Comment period [14] days. They may correct facts and request redaction of personal or confidential data. They cannot require removal of a negative lesson that is evidenced. Delay up to [60] days only for personal data, security or a legitimate legal interest (MoU Section 10) |
| Naming vendors | Lessons about a device or vendor are published with evidence and the tested version, and the vendor may add a response. Language is factual |
| Language | English with Kiswahili summaries. States this was a pilot and results are tested, not guaranteed. No promises on tariffs, jobs or supply |
| Format | Open repository, versioned, with a change log. Short summary for decision-makers, full guide for practitioners |
| Disclosure thresholds | No figure based on fewer than [k] customers, sessions or vehicles. Household data only at feeder or transformer-group level. Charger data only at hourly or session-distribution level (D2 Section 10) |

## 25. Custodianship and maintenance of the guide

| Item | Plan |
| --- | --- |
| Custodian | Named at Gate 5 (for example the university partner, Ministry of Energy or a utility). Decision [ ] |
| Maintenance | Yearly review, update after any major OpenEMS release, regulatory change or reported incident |
| Feedback route | Public issue tracker and a contact for replicators to submit lessons using the Section 6.4 record |
| Version control | Semantic versions. Each change lists the lesson IDs and evidence tags affected |
| Funding | Post-pilot plan includes a small maintenance budget [KSh [ ]] |
| Retirement | The guide states its review date and a notice that it should not be used after it, unless re-reviewed |

## 26. Schedule and gate evidence

| Activity | Months | Output | Gate |
| --- | --- | --- | --- |
| Approve method, lesson record, themes and guide structure | 4 to 6 | This document v0.1 | **Gate 1** |
| Set up lessons register and flag in D5. Train capture roles | 6 to 8 | Register live | Gate 2 |
| Capture from lab campaign, procurement and Gate 2 | 4 to 8 | First lessons | Gate 2 |
| Capture during build and commissioning, after hold points | 8 to 12 | Build lessons | |
| Gate 3 lessons review, draft Sections 11 to 17 | 12 | Lessons summary, guide draft v0.2 | **Gate 3** |
| Capture in operation, quarterly check-ins | 13 to 24 | Operations lessons | |
| Gate 4 lessons review, guide v0.3, link to E1 | 18 | Revised draft | **Gate 4** |
| Fill scenario playbooks and cost model from E2 and C2 | 21 to 22 | Draft v0.9 | |
| Review chain, comment period, translation | 22 to 23 | Reviewed guide | |
| Gate 5 lessons review, publication, custodian briefing | 24 | Guide v1.0 | **Gate 5** |

| Gate | Evidence from E3 |
| --- | --- |
| Gate 1 | Approved method and themes. Lesson record template. Budget for facilitation and translation |
| Gate 2 | Register live. First lessons from lab and procurement. Capture roles trained |
| Gate 3 | Lessons-learned review held and shared (Charter Section 23). Build lessons recorded. Guide draft of build and commissioning sections |
| Gate 4 | Operations and cost lessons. Link to E1 corrections. Guide revision |
| Gate 5 | Final lessons review. Guide v1.0 published. Evidence tags resolved. Custodian named and briefed |

**Critical path.** E3 depends on capture happening **during** the pilot. A lesson reconstructed from memory at Month 24 is weak evidence. If capture discipline slips at any site, the Programme Manager reports it on the dashboard and the stop-or-extend rule is not a reason to skip a review.

## 27. Budget and resources

Lessons and replication costs are drawn from the PMO, the university partner's budget line and the dissemination share of the programme budget. Items to itemise before Gate 1: facilitation of three lessons reviews, community and driver feedback sessions, travel to Pilot B, translation and printing of Kiswahili summaries, editor and layout, independent review, publication and hosting of the open repository, custodian handover, a small annual maintenance budget. Amount: KSh [to be confirmed at Gate 1]. Any use of contingency needs Steering Committee approval (Charter Section 20).

## 28. Risks to add to the live Risk Register

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| LL1 | Lessons not captured at the time, so evidence is weak or lost | M | H | Capture at hold points, lesson flag in D5, reviews at gates, named capture roles | Programme Manager |
| LL2 | Pressure to hide or soften negative lessons or vendor failures | M | H | Equal prominence rule, MoU Section 10, independent reviewer | Programme Director |
| LL3 | Guide read as a promise of savings or as a national roll-out plan | M | H | Evidence tags, conditions, per-scenario framing, limitations, no-promise wording | Research Lead |
| LL4 | Hardware, firmware or release changes make guidance obsolete quickly | H | M | Version-pinned findings, retest instruction, yearly review | Technical Lead |
| LL5 | Disclosure of personal, commercial or security-sensitive detail | L | H | Restricted field, sanitising, release review | Cybersecurity Officer |
| LL6 | Guide too heavy for small replicators, so it is ignored | M | M | Two-level measurement, "drop or lighten" lists, short summaries | Technical Lead |
| LL7 | Replicators skip safety or security steps they see as pilot overhead | L | H | S markers, "never drop" lists, hold points in the guide | Technical Lead |
| LL8 | No funded custodian after Gate 5 | M | H | Name custodian early, maintenance budget line | Programme Sponsor |
| LL9 | Single-site lessons presented as general | M | M | "Single-site" label, independence test | Research Lead |
| LL10 | Vendors dispute lessons about their products | M | M | Evidence and version stated, right of reply, factual language | Technical Lead |
| LL11 | Facilitation and translation under-budgeted | M | M | Itemise before Gate 1 | Programme Manager |

These risks are to be merged into the live Risk Register (README A6).

## 29. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Approve the lesson record, themes and evidence tag scheme | Gate 1 | Technical Lead, Programme Director |
| 2 | Add the lesson flag and lesson ID to the D5 tool | Gate 2 | Technical Lead |
| 3 | Decide the independent facilitator for the three reviews | Gate 2 | Programme Manager, university partner |
| 4 | Decide the typical-duration basis for the step table (median, range, worst case) | Gate 4 | Technical Lead |
| 5 | Decide the lighter evidence level for commercial replicators and who certifies it | Gate 4 | Research Lead |
| 6 | Decide whether a lighter security review may replace a full audit for small sites | Gate 4 | Cybersecurity Officer, TWG |
| 7 | Decide how vendors are named and how their response is published | Gate 3 | Programme Director, counsel |
| 8 | Decide the open licence for text and images | Gate 3 | Technical Lead, counsel |
| 9 | Decide the Kiswahili and local-language production route | Gate 4 | Capacity-building lead |
| 10 | Name the custodian, repository host and maintenance budget | Gate 5 | Programme Sponsor |
| 11 | Agree how a replicator submits feedback and who moderates it | Gate 5 | Custodian |
| 12 | Decide whether the guide is published as one document or as scenario-specific booklets | Gate 4 | Technical Lead |

## 30. Immediate next steps

1. TWG and Panel to review this structure, including the Kenya Power grid engineer on utility lessons and notification.
2. Add the lesson flag, lesson ID and theme code to the incident and change register design (D5).
3. Brief Site Leads, operators and installers on the capture points and the blameless rule, in English and Kiswahili, through D4 training.
4. Agree the facilitator and schedule for the Gate 3 lessons review with the university partner.
5. Agree the evidence tag rules and independent review with the Research Lead and independent reviewer.
6. Itemise facilitation, translation, publication and maintenance costs in the budget reconciliation.
7. Start the lessons register with lessons from lab planning and the first market briefing.
8. Add risks LL1 to LL11 and the open items to the PMO log and Risk Register.

---

# Appendix A: After-action review at a hold point (template)

| Question | Entry |
| --- | --- |
| Hold point, site, date, participants (roles) | [ ] |
| What did we plan to happen? | [ ] |
| What actually happened? | [ ] |
| Why was there a difference? | [ ] |
| What worked and should be repeated? | [ ] |
| What should change next time? | [ ] |
| Any near miss or safety concern? | [ ] |
| Any surprise about the host, community, vendor or equipment? | [ ] |
| Lessons raised (IDs) | `LL-[ ]` |
| Facilitator and sign-off | [ ] |

# Appendix B: Lessons review agenda (Gates 3, 4, 5)

1. Purpose and ground rules: blameless, evidence-based, all voices heard (10 min).
2. Timeline of the stage: what was planned and what happened (20 min).
3. Theme rounds in the order of Section 7, with lessons raised since the last review (90 min).
4. Separate short sessions for operators, community members, drivers or host staff (as relevant).
5. Dissenting views and issues not agreed (15 min).
6. Actions, owners and dates (15 min).
7. What a replicator must be told about this stage (15 min).
8. Close and circulation plan (5 min).

# Appendix C: Replication readiness checklist (for a replicator)

| # | Check | Evidence | Done |
| --- | --- | --- | --- |
| 1 | Screening gates G1 to G9 answered, with Unknown treated as No | Screening record | [ ] |
| 2 | Scenario gates answered | Screening record | [ ] |
| 3 | Break-even passed in the pessimistic case | Model output | [ ] |
| 4 | Written regulator and utility positions held | Letters | [ ] |
| 5 | Entity, title, insurance and host agreement in place | Signed documents | [ ] |
| 6 | Compatibility test record at L3 for every device and the OpenEMS release | Test records | [ ] |
| 7 | Vendor written commitments held (warranty permission, protocol, service, firmware hold) | Vendor letters | [ ] |
| 8 | Fire risk assessment, insurer acceptance, responders briefed | Documents | [ ] |
| 9 | Licensed contractors and permits confirmed | Licences | [ ] |
| 10 | Safe states, limits and override rules defined | Schedule | [ ] |
| 11 | Network separated from host IT. Remote access disabled until review | Design, scan | [ ] |
| 12 | Operators and backup trained and assessed | Records | [ ] |
| 13 | Operator manual, alarm card, emergency sheet issued | Documents | [ ] |
| 14 | Measurement plan and baseline rule agreed | Plan | [ ] |
| 15 | Incident and change register ready | Tool | [ ] |
| 16 | Closure, ownership and decommissioning agreed | Contract | [ ] |

# Appendix D: Guide section template (for each playbook line)

| Field | Entry |
| --- | --- |
| Instruction | [ ] |
| Condition under which it holds | [ ] |
| Evidence tag | [H] / [P] / [C] / [N] |
| Lesson IDs | `LL-[ ]` |
| What the pilot showed (numbers with source) | [ ] |
| What to drop or lighten for commercial replication | [ ] |
| What must never be dropped | [ ] |
| Last reviewed (date, reviewer) | [ ] |

# Appendix E: Sign-off

| Role | Name | Signature | Date |
| --- | --- | --- | --- |
| Technical Lead (author) | [ ] | | |
| Research Lead (check against E2) | [ ] | | |
| Cybersecurity and Data Protection Officer (release clearance) | [ ] | | |
| Independent reviewer | [ ] | | |
| Programme Director | [ ] | | |
| Custodian (acceptance at Gate 5) | [ ] | | |

# Appendix F: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 5, 7, 8, 16, 20, 21, 23, 24) | Scope limits, success criteria, reference cost structure, gates, change control, publication, lessons-learned reviews, closure |
| Problem Statement | Central question and supporting questions the guide helps others answer locally |
| Feasibility Study (Sections 5.2, 5.4 to 5.6, 8, 9, 12) | Replication cost, break-even logic, risks, conditions to proceed, recommendations |
| Final Evaluation Report (E2, Sections 9 to 15) | Verdict, lessons themes, recommendations, replication prerequisites, limitations |
| Interim Evaluation Report (E1, Sections 9, 11, 13) | Diagnosis order, corrections, interim lessons |
| Monitoring and Evaluation Plan (D1) | KPI dictionary, baseline, mode discipline, uncertainty rules |
| Monthly Performance Reports (D6) | Evidence source and report format |
| Incident and Change Log (D5) | Primary evidence and lesson flag |
| Interoperability Register (B6), Configuration Baseline (C4) | Compatibility levels, driver routes, version pinning, configuration control |
| Technical Specification (B4), Installation Plan (C3), Acceptance Tests (C5) | Design rules, sizing method, hold points, test sets |
| Regulatory Compliance Assessment (B5), Cybersecurity Plan (B7), Data Plan (D2) | Regulatory question set, security controls, audit, privacy rules |
| Procurement Plan (C1), Budget tracker (C2), Techno-economic model (B2) | Procurement method, cost categories, cost model |
| HSE Plan (C6), O&M Manual (D3), Training Records (D4) | Safety controls, operating routines, competence model |
| Stakeholder Engagement Plan | Community engagement, inclusion, grievance, disclosure before publication |
| MoU and Site Agreement templates (MoU Section 10; Site Agreement Sections 9.3, 16, Schedule 4) | Publication rights, host comment limits, closure |

On completion of the Gate 1 decisions (method, tags, facilitator), the Gate 3 and Gate 4 lessons reviews and the final results in E2, each bracketed value is updated, evidence tags are resolved, and this document is re-issued as version 1.0 at Gate 5.

# Training Materials and Attendance Records

## 1. Purpose and bottom line

The Charter makes "local capacity as a deliverable" a governance principle and sets as a programme-level success criterion a trained local team able to operate and support OpenEMS without continuous foreign support (Charter Sections 7 and 12). Deliverable D6 is that team and its training materials. Gate 3 requires operators trained, and a Charter risk trigger fires if fewer than the planned number of trainees are certified at Gate 3 (Charter Section 18). This document (D4) defines **who is trained, in what, how competence is judged, how attendance and results are recorded, and how the records are protected**. It also provides the material outlines and templates that trainers use.

**Bottom line.** Training here is a safety control, an evidence control and a sustainability control, not a classroom formality. Nine rules follow:

1. **Competence, not attendance.** Sitting in a session earns an attendance record. Only an assessed, observed demonstration earns a competence record. Gate 3 counts competence (C5 Section 12, TR-1 to TR-6).
2. **Train before exposure.** Nobody works on a site, operates a system or handles data until the matching induction or module is signed off. Site Leads before Gate 2, installers before H0, operators before Gate 3.
3. **Hands on, on the real system.** Trainees take part in at least one commissioning test and one drill on their own site (C3 8.9, C5 TR-2). Lab and simulator training prepares for this and does not replace it.
4. **Trainees never perform live work.** Electrical and battery tasks remain with licensed contractors and vendor-authorised technicians. Operators are trained to recognise, stop, isolate if safe, log and escalate (O&M Manual Section 5.3).
5. **Operators do not tune.** Training covers what operators may do, and equally what they must not: edit configuration, change mode, bypass protection, add remote access (O&M Manual Sections 5.2 and 5.3).
6. **Two people per role.** Every site has a named primary operator and a trained backup. Training plans and records are built around that pair, because retention of trained staff is a stated risk.
7. **Local language and local context.** Materials are in English and Kiswahili, with local-language support at Pilot B, and use pictures and practical demonstration for lower-literacy audiences. Assessment is practical wherever possible.
8. **Records are personal data.** Attendance, scores, photographs and certificates are handled under the Data Protection Act, 2019, with the minimum collected, defined access and a retention period (Section 14, D2 dataset DS07).
9. **Honest records.** Failed assessments, retakes and withdrawn trainees stay in the record. Reported numbers separate "attended", "assessed competent" and "retained after [12] months".

**What cannot be settled from desk research.** No site is selected, no equipment is bought, no vendor manuals exist and no trainees are nominated. Device names, alarm codes, battery chemistry, training venues, trainee education levels, language needs and the operator employment model will change the detail. This document fixes the structure, minimum curriculum, assessment rules and record formats, and leaves site and vendor specifics as placeholders to be completed at Gate 2 and Gate 3.

## 2. Document control and relationships

**Owner:** Capacity-building lead (README D4). **Contributors:** Technical Lead, software engineer, Site Leads, site engineer (C6 owner), Cybersecurity and Data Protection Officer, Research Lead and data analyst, university partner, vendors' local service agents, community liaison officers, Kenya Power grid engineer (TWG), local fire and emergency responders. **Approval:** Programme Director at Gate 1 (method), site training plans and trainee lists approved at Gate 2, completion verified at Gate 3. Reviewed monthly in the TWG during build and operation. Changes follow Charter Section 20 change control. Safety content follows the C6 change route and security content the B7 route.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 7, 8, 12, 15, 16, 18, 22, 23, 24) | Local capacity principle, success criteria, training budget share, Gate 3 evidence, risk trigger, training KPI, closure and custodians |
| Stakeholder Engagement Plan (Sections 6.4, 7.3, 7.4, 8, 12, 13) | University partnership, operator and community training, local labour, capacity and retention indicators |
| Operations and Maintenance Manual (D3, Sections 5, 8 to 13, 16) | The content operators are trained and assessed against; staffing rules; operator competence table |
| Health, Safety and Environmental Plan (C6, Sections 6, 9, 12, 14, 15) | Induction, contractor competence, emergency drills, trainee restrictions, responder familiarisation |
| Cybersecurity Plan (B7, Sections 6.1, 6.8, 10.6, 11, Appendix B) | Security training content, named accounts, tabletop and site drills |
| Data Management and Privacy Plan (D2, Sections 6, 8, 9, 11) | Data handling training, privacy of training records, dataset DS07 |
| Installation and Commissioning Plan (C3, Sections 8.9, 12, 13, 17) | Trainee participation in commissioning, handover pack, Gate 3 evidence |
| Site Acceptance Test Reports (C5, Section 12, tests B9 and equivalents) | Operator drills and handover verification that D4 records feed |
| OpenEMS Configuration Baseline (C4, Sections 6.6, 10, 11) | Modes, change classes, backup and restore taught at the level operators need |
| Monitoring and Evaluation Plan (D1, Sections 6.1, 7.5, 8) | Confounder log, meter and seal care, training indicators |
| Procurement Plan (C1, Sections 7, 9, 11) | Vendor training obligations, local technician requirements, service levels |
| MoU and Site Agreement templates (MoU Schedule 1C; Site Agreement Sections 4.1, 11, Schedule 7) | University role, student placements, host staff release, operator training duty |
| Interoperability Register (B6) | Device and firmware set that training material must match |
| Regulatory Compliance Assessment (B5, Sections 5.8, 5.9) | Licensed contractor requirements, research approvals for any trainee data |

## 3. Principles

| Principle | What it means in practice |
| --- | --- |
| Safety before schedule | A trainee who has not passed the safety module does not work on site, whatever the schedule says. Slippage goes to the stop-or-extend rule (C3 Section 14) |
| Competence is observed | Assessment is a demonstrated task against a checklist, signed by an assessor who is not the trainer where practicable |
| Match the real system | Material is built from the frozen configuration, the B6 firmware set and the vendor manuals for the equipment actually installed. Generic material is labelled as such |
| Learn in the order of exposure | Awareness first, then supervised practice, then assessed independent work |
| Inclusive access | Women, youth, people with disabilities and local residents are deliberately recruited, scheduled around and supported, not only existing technicians (Stakeholder Plan Section 3) |
| Proportionate | Depth scales with the role. A community liaison officer does not need inverter register maps, and an operator does not need grid-forming design |
| Local ownership | Local trainers are developed so that refresher and new-joiner training continue after the pilot without foreign support |
| Open by default | Curriculum, slide decks, checklists and videos are published under an open licence after review. Credentials, network details, host-confidential data and personal records are not (C4 Section 14) |
| No overpromising | Training does not promise jobs, certification beyond what the programme issues, or permanent assets (Stakeholder Plan 7.4) |
| Honest limits | The programme certificate is a programme record of demonstrated competence on this system. It is not a statutory electrical licence and does not replace one |

## 4. Scope

**In scope.** Training needs analysis; curriculum and materials; delivery at the lab, on site and online where connectivity allows; assessment and certification; attendance and competence records; trainer development; refresher and new-joiner training; training effectiveness measurement; handover of materials to custodians. Audiences are in Section 6.

**Out of scope.** Statutory licensing of electricians and solar contractors (EPRA and Kenyan law, B5); university degree curricula; vendor product training beyond what the contracts require; general public awareness (covered by the engagement plan); core OpenEMS software development training beyond custom drivers and configuration needed for local hardware (Charter Section 5).

## 5. Roles and responsibilities

| Role | Training responsibility |
| --- | --- |
| Steering Committee | Receives training KPIs quarterly. Decides on any trigger breach or Gate 3 shortfall |
| Programme Director | Accountable for training meeting the Gate 3 evidence rule. Signs approval of trainee lists with the host |
| Capacity-building lead (D4 owner) | Owns this document, curriculum, schedule, trainee register, assessments, certificates and reporting |
| Technical Lead | Approves technical content. Signs off competence for operators together with the site engineer |
| Software engineer | Builds the lab environment and exercises on the lab Edge. Maintains technical modules |
| Site engineer | Practical assessor for site tasks. Co-owns safety content with the C6 plan |
| Site Leads | Release trainees, host the on-site sessions, hold stop authority, sign site induction records |
| Cybersecurity and Data Protection Officer | Owns security and data modules, approves how records are stored, assesses security habits |
| Research Lead and data analyst | Own the data quality, confounder, meter and seal content |
| University partner | Co-delivers lab sessions, supports student placements and trainer development, hosts the lab where agreed (MoU Schedule 1C) |
| Vendors and local service agents | Deliver product-specific modules as a contract obligation and supply manuals, alarm lists and demonstration units |
| Licensed electrical contractor | Delivers isolation, lock-out and electrical awareness and signs the electrical competence of their own crews |
| Kenya Power grid engineer | Contributes utility-interface and isolation content and joins relevant sessions |
| Local fire and emergency responders | Take part in familiarisation visits and joint drills |
| Community liaison officers | Co-deliver community safety sessions and are trained in grievance handling |
| Host representatives | Nominate trainees, release staff, take part in awareness sessions and co-sign records |
| PMO | Tracks training progress, cost and risks on the dashboard |
| Assessors | Observe and sign competence checklists. Declare any conflict of interest with the trainee |

## 6. Audiences and training needs

### 6.1 Audience map

| ID | Group | Pilots | Needs in short | Required before |
| --- | --- | --- | --- | --- |
| G1 | Local operators (primary) and trained backups | A, B, C | Run and inspect the system, respond to alarms, log, escalate, protect data and meters | Gate 3 |
| G2 | Site Leads and safety officers | A, B, C | Permits to work, incident handling, escalation, return to service, first aid | Gate 2 |
| G3 | Site engineers and local technicians | A, B, C | Inspection, corrective maintenance support, L4 tests, configuration verification, restore | Gate 3 |
| G4 | Contractors, installers and vendor crews | A, B, C | Site rules, method statements, isolation, battery handling, code of conduct, no undocumented remote access | H0 |
| G5 | Host staff (Pilot A), site operator staff (Pilot C) | A, C | Awareness, what the system does, override right, who to call | Go-live |
| G6 | Community liaison officers | B, C if appointed | Safety messages, complaints handling, safeguarding, referral routes | H0 |
| G7 | Kenya Power staff (grid engineer and relevant field staff) | A, B, C | Awareness of the control boundary, data interface, incident notification, commissioning witness | Before H5 |
| G8 | Local responders | A, B, C | Site familiarisation: layout, isolation points, battery behaviour, what suppression does, no-entry rule | H5 |
| G9 | Students, university staff and interns | All | Induction, supervised measurement and configuration tasks, restricted tasks | Before first site visit |
| G10 | Local implementation team and trainers | Programme | Configuration management, drivers, testing, security, training delivery | Months 6 to 14 |
| G11 | Data analysts and Research team | Programme | KPI dictionary, quality checks, privacy and disclosure rules | Before data collection |
| G12 | EV drivers and fleet operators | C | How managed charging works, expected effects, how to give feedback | Before go-live |
| G13 | Community members, school and leaders | B | Safety near the site, what the pilot is and is not, how to complain | Before works |
| G14 | Custodians at closure | All | Safety, security, data and end-of-life duties after handover | Gate 5 |

### 6.2 Training needs analysis

A short analysis is run for each candidate site once trainees are nominated, and results are stored with the trainee record.

| Item | Method |
| --- | --- |
| Existing skills | Interview and practical check: electrical basics, computer use, record keeping, mobile and messaging tools, first aid |
| Literacy, numeracy and language | Respectful screening to choose delivery format. Never used to exclude people, only to choose support |
| Availability and release | Host or employer agreement on paid release time, travel, childcare or meals where needed |
| Access and inclusion | Venue accessibility, times that suit women and carers, transport safety, youth and disability needs |
| Gaps | Compare to the competence profile for the role (Section 9) |
| Output | Individual learning plan listing modules, format and support, signed by trainee and Capacity-building lead |

## 7. Curriculum

### 7.1 Module catalogue

Module IDs are used in all records. Hours and formats are proposals for Gate 1 approval. "P" means practical, "C" classroom, "D" demonstration, "S" supervised on-site, "E" e-learning or phone-based where connectivity allows.

| ID | Module | Main audience | Format | Hours | Content summary | Source documents |
| --- | --- | --- | --- | --- | --- | --- |
| TM-01 | Programme and research pilot basics | All | C | [1] | What OpenEMS is and is not, research pilot not guaranteed savings, behind-the-connection-point control, roles, how to answer visitors | Charter, Stakeholder Plan 7.2 |
| TM-02 | Site induction and safety essentials | All entering site | C, D | [2] | Hazards, assembly point, stop authority, PPE, permits, reporting, no tampering, no remote access | C6 Sections 9, 12 |
| TM-03 | Electrical awareness for non-electricians | G1, G5, G6, G9 | C, D | [3] | Shock and DC hazards, isolation and lock-out as a concept, why operators never work live, emergency isolation | C6 9.1, D3 5.3 |
| TM-04 | Battery and fire safety for operators | G1, G2, G3 | C, D | [3] | Warning signs, alarm classes, evacuation, no-entry rule, detection and suppression basics, post-incident rules | C6 9.2, D3 8.2, 11.1 |
| TM-05 | System overview and operating modes | G1, G3, G5 | C, D | [3] | Layers, devices, safe states, modes M0 to M4, why mode is a research decision, what the UI shows | B4 Section 3, C4 6.6, D3 6 |
| TM-06 | Daily, weekly and monthly routines | G1 | P, S | [4] | Walk-round, UI status, logbook, mode check, data completeness, battery checks, housekeeping | D3 Section 8 |
| TM-07 | Alarms, first response and resets | G1, G2, G3 | P, D | [3] | Alarm classes A1 to A4, alarm card, reset rules, fault table first checks, escalation ladder | D3 Sections 9, 10, 12 |
| TM-08 | Overrides and logging | G1, G5 | C, P | [1.5] | Emergency, host and operator override, logging rule, review limits | D3 Section 7 |
| TM-09 | Emergency procedures and drills | All site personnel | P | [3] | Fire, shock, spill, weather, security, communication loss, evacuation, first aid | D3 Section 11, C6 Section 15 |
| TM-10 | Security habits for operators | G1, G3, G5 | C, P | [2] | Named accounts, phishing, USB, social engineering, remote support rules, suspicious requests | B7 Section 11, D3 13 |
| TM-11 | Data, meters, seals and confounders | G1, G3, G11 | C, P | [2] | Why evidence matters, seal checks, clock alarms, confounder log, privacy rules, who to ask | D1 Sections 7.5, 8, D2, D3 13.3 |
| TM-12 | Return to service and maintenance coordination | G1, G2, G3 | C, P | [2] | M4 flag, permit to work, two-person rule, service reports, return-to-service checklist | D3 Section 10 |
| TM-13 | Pilot A module | G1, G5 | C, S | [2] | Host interface, protected loads, existing PV inverters, export limit, host IT boundary | D3 8.3, C3 Section 9 |
| TM-14 | Pilot B module | G1, G6 | C, S | [3] | Supply continuity, generator checks, PV array care, check meters, connectivity fallback, theft response, community interface | D3 8.4, C3 Section 10 |
| TM-15 | Pilot C module | G1, G5, G12 | C, S | [3] | Charger checks, policy and throttling explanation, transformer feed, driver communication, public safety | D3 8.5, C3 Section 11 |
| TM-16 | Configuration, verification and restore | G3, G10 | P | [8] | Manifest, hashes, verify tool, backup and restore, rebuild, change classes, never edit live | C4 Sections 6 to 11 |
| TM-17 | Compatibility testing and drivers | G10 | P | [12] | Levels L0 to L4, test sets, driver routes R1 to R5, test records, delta tests | B6 |
| TM-18 | Acceptance testing and commissioning support | G3, G10 | S | [6] | Reading and running site acceptance tests, witnessing, records | C5 |
| TM-19 | Measurement and KPI basics | G3, G11 | C, P | [4] | KPI dictionary, meter accuracy, data quality checks, mode flags | D1 |
| TM-20 | Grievance handling and safeguarding | G6, G2 | C, role-play | [3] | Receiving, recording, escalating complaints, confidentiality, non-retaliation, safeguarding and referral | Stakeholder Plan 11, C6 Section 10 |
| TM-21 | Community and driver briefings | G6, G12, G13 | C, D | [1 to 2] | Plain-language messages, what to expect, safety near site, how to complain | Stakeholder Plan 7 |
| TM-22 | Utility interface and notification | G7 | C, D | [2] | What OpenEMS controls and does not, read-only data, event notification, witnessing commissioning | MoU Schedule 1B, B4 3.2 |
| TM-23 | Responder familiarisation | G8 | S | [2] | Site walk, isolation points, battery behaviour, suppression limits, no-entry rule, contact routes | C6 Section 12, 15 |
| TM-24 | Contractor and installer briefing | G4 | C, D | [2] | Method statement, hold points, isolation, battery handling, code of conduct, credential handover, no undocumented remote paths | C3 Section 8, B7 App A |
| TM-25 | Trainer development | G10 | C, P | [16] | Adult learning, assessing competence, practical teaching, safe demonstration, inclusive delivery, record keeping | This document |
| TM-26 | Handover and custodian briefing | G14 | C, S | [3] | Safety, security, data, end-of-life, post-pilot duties | Charter Section 24, D3 Section 18 |
| TM-27 | Refresher and drill rotation | G1, G3 | P | [2 per quarter] | Rotating drill topics, lessons from incidents, changes since last training | D3 Section 8.1 |

### 7.2 Learning pathways

| Pathway | Modules in order | Total hours (proposal) | Assessment |
| --- | --- | --- | --- |
| Operator (G1) | TM-01, 02, 03, 04, 05, 06, 07, 08, 09, 10, 11, 12, then pilot module TM-13, 14 or 15 | [about 35] | Written or oral check plus practical competence checklist (Appendix C) and drill |
| Site Lead and safety officer (G2) | TM-01, 02, 04, 07, 09, 12, 20, plus first aid and permit to work from the C6 plan | [about 25] | Practical and scenario assessment |
| Site engineer and technician (G3) | TM-01 to 05, 07, 09, 10, 11, 12, 16, 18, 19 | [about 50] | Practical assessment on lab Edge and on site |
| Implementation team and trainers (G10) | TM-05, 10, 16, 17, 18, 19, 25 plus G3 pathway | [about 70] | Lab practical, written test, observed teaching session |
| Contractor and installer (G4) | TM-02, 24 plus the contractor's own licensed competence | [about 4] | Induction check and licence verification |
| Host and site operator staff (G5) | TM-01, 02, 03, 05, 08, 09, pilot module | [about 8] | Short check and drill participation |
| Community liaison officer (G6) | TM-01, 02, 20, 21, 14 or 15 | [about 12] | Role-play and scenario |
| Utility staff (G7) | TM-22 | [2] | Attendance and short check |
| Responders (G8) | TM-23 | [2] | Familiarisation visit record |
| Student (G9) | TM-01, 02, then supervised tasks | [about 6] | Induction check |
| Analyst (G11) | TM-01, 11, 19 | [about 8] | Practical on lab data |
| Driver or fleet (G12), community (G13) | TM-21 | [1 to 2] | Attendance and feedback only |

Hours are indicative and are fixed at Gate 1 after the needs analysis. Pathways are shortened only by prior-learning evidence signed by the assessor, never by waiving safety modules.

## 8. Delivery model

### 8.1 Formats and venues

| Format | Use | Notes |
| --- | --- | --- |
| Lab sessions | Technical modules on the lab Edge, device demonstrations, drivers and tests | Run at the university or technology partner lab where agreed (B6 Section 6.1) under the lab safety plan |
| On-site supervised practice | Routines, alarm drills, commissioning participation, return-to-service | The main route to operator competence. Always with a named supervisor |
| Classroom or community meeting | Awareness, safety, grievance, driver and community briefings | Held at accessible local venues, outside peak working or farming hours where possible |
| Demonstration units | Safe isolated units or simulators for alarm and fault practice | Simulators are labelled as such and are not used to claim competence on live equipment |
| Phone-based and offline materials | Refreshers, quick cards, short videos | Downloaded and played offline. Not dependent on connectivity at Pilot B |
| Drills | Fire, evacuation, battery alarm, spill, security, reset | Scheduled, witnessed, recorded (Section 12) |
| Tabletop exercise | Incident response with Kenya Power and a host | Before Gate 3 (B7 Section 10.6) |
| Peer coaching | Experienced operator supports a new joiner | New joiner still completes the full pathway |

### 8.2 Group size and ratios

| Activity | Proposal |
| --- | --- |
| Classroom | Up to [20] participants per trainer |
| Practical and drills | Up to [6] participants per assessor, [4] for any battery or electrical demonstration |
| On-site supervised practice | One supervisor per [2] trainees |
| Student visits | One supervisor per [5] students, no live work |

### 8.3 Language, accessibility and inclusion

- Written materials and the alarm card are in English and Kiswahili. Pilot B adds the local language for the community and operator summaries where needed (Stakeholder Plan Section 3).
- Materials use short sentences, pictures, colour-and-symbol coding that does not rely on colour alone, and practical demonstration rather than reading.
- Oral or practical assessment is offered to anyone who prefers it. Interpretation is arranged where needed.
- Venues are accessible. Times and locations are agreed with trainees, including women, carers and young people.
- A small allowance or paid release time for trainees is considered so that cost does not exclude people \[to be decided with the host and funders, open item 3\].
- Women and youth are deliberately recruited as operators and backups, with targets set at Gate 1.
- Any trainee can raise a concern about a trainer or session through the programme complaints channel. Safeguarding rules apply to all sessions (Section 13).

### 8.4 Material standards

| Standard | Requirement |
| --- | --- |
| Version control | Every material has an ID, version, date, owner and reviewer. Material versions are tied to the C4 baseline tag and B6 firmware list |
| Accuracy review | Reviewed for technical accuracy by the Technical Lead or delegate and for safety by the site engineer before release. Independent reviewer for safety content (Charter Section 23) |
| Security and privacy review | Reviewed by the Cybersecurity Officer before public release. No credentials, network diagrams of live sites or personal data |
| Source of truth | Vendor manuals and the O&M Manual prevail on equipment details. Where they differ, the material is corrected |
| Updating | Updated after every Class 1 or 2 incident, major change of equipment or configuration, and at least at Gate 4 |
| Licence | Programme-authored material under an open licence agreed with counsel \[Apache 2.0 for code and scripts, a Creative Commons licence for text and images, open item 6\]. Vendor material is used under the vendor's terms |
| Marking | Practical cards and decks are marked "training material, not the site manual" and point to D3 |

## 9. Competence framework and assessment

### 9.1 Competence levels

| Level | Name | Meaning |
| --- | --- | --- |
| C0 | Not trained | No training or assessment recorded |
| C1 | Aware | Attended and passed a basic check. May be on site under escort and supervision |
| C2 | Supervised | Completed the pathway modules and practical practice. May perform listed tasks only under direct supervision |
| C3 | Competent | Demonstrated every task on the role checklist independently, with an assessor's signature |
| C4 | Assessor or trainer | Competent and has completed TM-25. May assess and train others |

**Rules.** Operators need C3 before Gate 3 and before working unsupervised. Backups need C3. A person falls back one level if a required refresher is missed by more than [x] weeks or after a serious unsafe act pending review.

### 9.2 Assessment methods

| Method | Use | Notes |
| --- | --- | --- |
| Practical observation against a checklist | Primary method for operators, site engineers, technicians | Each task is marked "done unaided", "done with prompts" or "not done" |
| Scenario and drill | Alarms, fire, spill, security, loss of supply or communications | Scripted, timed where relevant, with debrief |
| Oral questions | Understanding of rules and reasons | Used instead of written tests for lower-literacy trainees |
| Short written or multiple-choice check | Safety essentials and rules | Pass mark [80]% for safety and security items, retake allowed after review |
| Work sample | Logbook entries, fault reports, confounder log entries | Reviewed for accuracy and completeness |
| Observed teaching session | Trainers (TM-25) | Marked against a teaching checklist |
| Peer and supervisor feedback | Supplement only | Not a substitute for observation |

### 9.3 Pass rules

1. **Safety-critical items are all-or-nothing.** Failing an item marked critical (for example approaching a battery in alarm, resetting a protection alarm without cause, ignoring lock-out, sharing a password) fails the whole assessment for that task. The trainee repeats the task after coaching.
2. **Retakes.** Up to [two] retakes per module without penalty. A third attempt needs a Site Lead and Capacity-building lead review and a changed learning plan.
3. **Independence.** The assessor is not the person who trained the candidate where practicable. At Gate 3 a sample of assessments is re-observed by the Technical Lead or an independent assessor.
4. **Fairness.** Assessors declare any relationship with the trainee. Assessment adjustments for disability or language are recorded, but the standard is unchanged.
5. **Evidence.** Each competence record cites the checklist, date, assessor, site and unit tested.

### 9.4 Operator competence profile (minimum for C3)

Derived from O&M Manual Sections 5 to 13 and C5 test B9. The detailed checklist is Appendix C.

| # | Competence | Critical? |
| --- | --- | --- |
| OC-01 | Explains what the operator may and may not do (D3 5.2 and 5.3) | Yes |
| OC-02 | Performs the daily walk-round and UI check and records it correctly | No |
| OC-03 | Recognises the operating mode and compares it with the signed record | Yes |
| OC-04 | Identifies alarm classes A1 to A4 and states the first response to each | Yes |
| OC-05 | Responds correctly to a simulated fire or battery alarm, including evacuation and calling | Yes |
| OC-06 | Uses emergency isolation correctly when safe, and explains when not to | Yes |
| OC-07 | Does not reset an alarm without cause. Follows the reset table | Yes |
| OC-08 | Completes a reset and fault procedure using the fault table within the target time (C5 B9) | No |
| OC-09 | Uses and logs an override correctly | Yes |
| OC-10 | Keeps the logbook, confounder log and visitor log accurately | No |
| OC-11 | Applies security habits: own account, no USB, no remote access, reports suspicious requests | Yes |
| OC-12 | Checks seals, spots data gaps and clock alarms, reports the same day | No |
| OC-13 | Follows the permit-to-work rule and escorts contractors | Yes |
| OC-14 | Completes the return-to-service checklist items an operator may do and escalates the rest | No |
| OC-15 | Explains the pilot honestly to a visitor and refers performance questions on | No |
| OC-16 | Pilot-specific tasks (A: protected loads; B: generator and supply continuity; C: charger and policy checks) | Yes for safety items |

## 10. Pilot-specific training requirements

### 10.1 Pilot A: Industrial park, hub or campus

| Item | Requirement |
| --- | --- |
| Operators | Host staff or named delegates, with a trained backup. Host rules and the programme rules both taught, the stricter rule applying |
| Host override right | Host representative and delegates are trained and tested on the override and its logging (test A8) |
| Production interface | Training on planned shutdown notice, protected-loads list and what not to interrupt |
| Existing equipment | Awareness of inverter warranty limits and the rule that operators do not touch inverter settings |
| Campus case | Separate awareness for students and public, supervision rules for teaching visits |
| Battery room | Fire officer or facilities lead joins the fire and ventilation module |

### 10.2 Pilot B: Rural microgrid

| Item | Requirement |
| --- | --- |
| Operators | Named local operator and trained backup, ideally from the community, selected through the community process. Not dependent on one person |
| Community | Safety sessions for households, schools and leaders on fencing, children and livestock, what to do if an alarm sounds, who to call. Pictorial, in local language |
| Remote conditions | Longer first-aid and emergency content because response times are long (C6 Section 15). Radio or satellite communication drill |
| Supply continuity | Transfer plan rehearsal with the operator, announced in advance (C3 Section 10) |
| Generator | Basic checks, fuel handling and spill response, and the rule that the generator keeps its own protection |
| Security | Theft and vandalism response, no confrontation, reporting. Community liaison trained in safeguarding and conduct |
| Spares and service | Operator knows the spares kit, how to log use and how to call the service agent |
| Local labour | Local installers and helpers inducted on the same terms as others and trained on site where qualified and cost-effective (Stakeholder Plan 7.4) |

### 10.3 Pilot C: EV charging site

| Item | Requirement |
| --- | --- |
| Operators | Site operator staff plus a trained backup. Staff trained to explain throttling and manage upset customers calmly |
| Public safety | Evacuation of the public and fleet drivers, extinguisher use for vehicle fires where assessed as appropriate, emergency stop locations |
| Charger and policy | Daily checks, throttling message and policy display, maximum-wait alarm, complaints routing |
| Fleet customers | Briefing for fleet managers and drivers on managed charging, expected effects on times and feedback route (C5 CX-4) |
| Privacy | Staff trained on the privacy notice, no payment or identity data in the programme dataset, and how to refer data questions |
| Transformer interface | Awareness of the site limit, that it is lowered first and raised only with Kenya Power agreement |

## 11. Trainer development and local sustainability

| Item | Plan |
| --- | --- |
| Initial trainers | University partner staff, programme engineers and vendor agents deliver the first cycle with local co-trainers |
| Train-the-trainer | Local technicians, university staff and experienced operators complete TM-25 and co-teach, then teach with observation, then teach independently (C4 level) |
| Local trainer bench | Aim for at least [2] local trainers per language and per technical area by Gate 4, so that training survives staff turnover |
| University role | Student projects and placements on measurement and OpenEMS configuration, joint workshops and an open training repository (Stakeholder Plan 6.4) |
| Vocational links | Early contact with technical and vocational institutions so the curriculum can be reused for later entrants (Stakeholder Plan Section 4) |
| Quality | Trainers are observed [once per cycle] and receive feedback. Participant feedback is reviewed after each session |
| After the pilot | Materials, trainer lists and records pass to the named custodian (Section 16) with a short plan for who delivers refreshers |

## 12. Drills and exercises

| Drill | Participants | Timing | Pass criterion | Record |
| --- | --- | --- | --- | --- |
| Fire and evacuation | All on site, host staff, responders where possible | Before energisation (H5), repeated at Gate 4 and each year | All reach assembly point within [x] minutes, count correct, correct call made, no re-entry | Drill sheet, Appendix D |
| Battery alarm tabletop | Operators, Site Lead, Technical Lead, host | Before Gate 3, Gate 4 | Correct alarm class, correct first response and escalation | Drill sheet |
| Spill response | Operators, site staff | Before Gate 3 | Spill contained with kit, reported, waste routed correctly | Drill sheet |
| Reset and fault procedure | Operator and backup | Before Gate 3 (C5 B9), quarterly rotation | Completed unaided within [x] minutes using D3 | Competence record |
| Security incident | Operators, Cybersecurity Officer | Before Gate 3, Gate 4 | Correct playbook step, no unsafe action, report within target | Drill sheet |
| Loss of supply or communications | Operators, Site Lead | Before Gate 3 (Pilot B rehearsal of transfer plan) | Safe state confirmed, log kept, communications fallback used | Drill sheet |
| Community alert (Pilot B), public evacuation (Pilot C) | Liaison, operator, community or station staff | Before go-live | Alert reaches nearby households or public within [x] minutes | Drill sheet |
| Tabletop with Kenya Power and a host | Programme and partners | Before Gate 3 | Roles and notification routes work | Exercise report (B7 10.6) |

Drills are announced to hosts, communities and users where they could cause concern. Any drill that finds a gap generates a non-conformance and a retest.

## 13. Safeguarding, conduct and welfare in training

- A code of conduct applies to trainers, trainees and visitors: respect, no harassment, no discrimination, no exploitation, no retaliation (C6 Section 10).
- Trainees under 18 are not accepted onto the operator pathway. Where school visits are held, they are awareness only, with a teacher present and no data about children collected.
- No lone training or assessment with one trainer and one trainee behind a closed door. Practical sessions have at least two people present.
- Trainers and assessors are briefed on safeguarding and the confidential complaints route. Concerns go to the Programme Manager and, for safeguarding, to the Programme Director.
- Welfare: water, shade, toilets and rest breaks at every session. Sessions avoid peak heat where possible.
- Nobody is penalised for stopping a session or a task for safety.

## 14. Attendance and training records

### 14.1 Record types

| Record | Purpose | Contents | Owner |
| --- | --- | --- | --- |
| Training register (master) | One line per person: role, pathway, status, competence level, certificate, retention | Appendix B | Capacity-building lead |
| Attendance register | Evidence a person attended a session | Appendix A | Trainer, filed by Capacity-building lead |
| Competence assessment record | Evidence a person demonstrated tasks | Appendix C | Assessor |
| Drill record | Evidence a drill happened and what it found | Appendix D | Site Lead |
| Induction record | Evidence of site induction before entry | Appendix E | Site Lead |
| Learning plan | Individual needs, modules, support | Section 6.2 | Capacity-building lead |
| Feedback form | Participant view of the session | Appendix F | Trainer |
| Certificate | Programme record of demonstrated competence | Appendix G | Programme Director |
| Trainer record | Trainer and assessor qualifications and observation results | Training register, trainer tab | Capacity-building lead |
| Responder visit record | Familiarisation visit by local responders | Appendix D variant | Site Lead |

### 14.2 Identifiers and format

| Item | Convention |
| --- | --- |
| Trainee ID | `TR-[site code][number]`, for example `TR-A001`. Names are held only on the master register |
| Session ID | `TS-[module ID]-[site or lab code]-[date]-[run]`, for example `TS-TM-07-B1-2027-03-14-01` |
| Attendance record | `ATT-[session ID]` |
| Competence record | `CMP-[trainee ID]-[module or role ID]-[number]` |
| Drill record | `DRL-[site]-[type]-[date]` |
| Certificate | `CERT-[trainee ID]-[role]-[number]` |

### 14.3 Rules for recording attendance

1. **Sign in and out.** Each participant signs at the start and at the end of the session. Absence for more than [x] minutes is recorded as partial attendance.
2. **Identity.** Trainers check identity against the nominated list. No proxy signing. Where signing is difficult, a trainer records an alternative acknowledgement (thumbprint or witnessed mark) and notes it.
3. **Minimum fields.** Date, time, venue, module, trainer, attendee name or ID, role, organisation, signature. Gender and age group are collected only on the optional monitoring section, as aggregated indicators for inclusion reporting (Stakeholder Plan 13), and are not shown on public outputs.
4. **Same-day filing.** Registers are photographed or entered the same day, checked by a second person and filed. Paper originals are stored securely.
5. **Corrections.** Errors are struck through and initialled. Records are never overwritten. A missing signature is not retrofitted.
6. **Attendance is not competence.** The master register shows both separately.
7. **Reporting.** Attendance, competence and retention are reported on the monthly dashboard and quarterly to the SteerCo, with "attended", "assessed competent" and "retained" shown separately.

### 14.4 Privacy and handling of training records

Training records are personal data. They are covered by the Data Management and Privacy Plan (D2 dataset DS07) and the Data Protection Act, 2019.

| Item | Rule |
| --- | --- |
| Lawful basis and notice | Trainees are told what is recorded, why, who sees it and how long it is kept, in plain language and Kiswahili where relevant, before the first session. Consent is recorded where it is the basis \[confirm with counsel, D2 Section 4\] |
| Minimisation | Collect name, contact, role, organisation, attendance, assessment results. No identity document numbers unless the licence check requires it. No health information. Photographs only with specific consent and never of children |
| Access | Capacity-building lead, Programme Manager, Site Lead (own site), Technical Lead and assessors for competence, Officer for audit. Hosts see only their own staff's results. Funders and the Panel see aggregated data |
| Sharing | Employers, universities and Kenya Power receive only the records of their own people, under written agreement. Certificates are given to the individual |
| Security | Stored in the controlled workspace, encrypted at rest, with paper originals locked. No records in chat tools or personal drives |
| Retention | Attendance and competence records for the pilot period plus [x] years, then anonymised or deleted. Certificates are held by the individual. Records kept longer only if the person agrees \[D2 Section 9\] |
| Rights | Trainees may see and correct their record, and may withdraw consent for photographs and optional data without penalty |
| Publication | Only aggregated, anonymised figures are published. Small groups are suppressed (D2 Section 10) |
| Breach | A loss of training records follows the D2 Section 12 steps |

### 14.5 Certification

| Item | Rule |
| --- | --- |
| Certificate | Issued by the programme on the Programme Director's authority, citing role, modules, level reached, assessor and date. It states that it records demonstrated competence on the OpenEMS Kenya pilot systems and is not a statutory electrical licence |
| Validity | [12] months, renewed by passing the annual refresher and drill. Lapses after a missed refresher beyond [x] weeks |
| Recognition | The programme seeks recognition of the curriculum by a university or vocational body so that holders can use it later \[open item 5\] |
| Revocation | Removed for serious unsafe conduct, security breach or misconduct after a fair review, with the reason recorded |
| Verification | An employer or host may verify a certificate with the Capacity-building lead by certificate ID |

## 15. Measures and reporting

| Indicator | Measure | Target |
| --- | --- | --- |
| Coverage | Planned trainees nominated, enrolled, attended, assessed competent, by group and site | Planned numbers set at Gate 1 \[Charter risk trigger applies at Gate 3\] |
| Two-per-site rule | Sites with a competent primary operator and a competent backup | 100% at Gate 3 |
| Competence | Operators at C3 before Gate 3, with all critical items passed | 100% of operators working unsupervised |
| Assessment quality | First-time pass rate, retake rate, share re-observed by an independent assessor | Reported, no target that rewards lowering standards |
| Drills | Drills completed on schedule and gaps closed | 100% before Gate 3 |
| Inclusion | Share of women, youth and local residents among trainees and operators, and share of trainees with a disability | Targets set at Gate 1, reported in aggregate |
| Retention | Competent operators still in post after [12] months | Per Charter risk trigger and Stakeholder Plan Section 13 |
| Application | Operator logbook quality, response to alarms, time to acknowledge, faults escalated correctly (from D3 15.3) | Reported monthly |
| Learning quality | Participant feedback scores and trainer observation results | Reviewed after each cycle |
| Local trainer capacity | Local trainers at C4 | At least [2] per area by Gate 4 |
| Utility and responder awareness | Kenya Power staff and responders briefed before H5 | 100% before H5 |
| Cost | Spend against the training and capacity line (about 5% of the reference cost structure) | Reported monthly |

Charter Section 22 treats operator and community training as a KPI (number trained, assessed competence and retention). This table is the measurement design for that KPI.

## 16. Schedule and gate evidence

Months are relative to programme start and follow the Charter gates. Charter deliverable D6 places the trained local team and materials in Months 6 to 14.

| Activity | Months | Output | Gate link |
| --- | --- | --- | --- |
| Appoint Capacity-building lead. Draft needs analysis method and curriculum outline | 0 to 3 | Method v0.1 | Gate 1 input |
| Local implementation team recruited, trainer bench identified | 3 to 6 | Team list | Gate 1 |
| Budget lines for training, allowances, venues and materials itemised | 2 to 4 | Costed plan | Gate 1 |
| Approve curriculum, assessment rules, record formats, targets | 4 to 6 | This document v0.2 | **Gate 1** |
| Site Leads, safety officers and site engineers trained. Trainees nominated per site | 6 to 8 | Records, trainee list | **Gate 2** |
| Contractor and installer briefings before mobilisation | 7 to 8 | Induction records | H0 |
| Vendor modules and manuals collected, site-specific materials prepared | 8 to 11 | Site material packs | Gate 2 and Gate 3 input |
| Classroom and lab training for operators, technicians, implementation team | 8 to 11 | Attendance records | |
| Supervised on-site practice and commissioning participation | 10 to 12 | Competence records (C5 TR-2) | H7 and H8 |
| Responder familiarisation, utility awareness, drivers and community briefings | 10 to 12 | Visit and briefing records | H5 and go-live |
| Drills and tabletop. Operator assessments and independent re-observation sample | 11 to 12 | Drill and competence records | **Gate 3** |
| Refresher cycle and new-joiner training | 13 to 24 | Quarterly records | Gate 4 |
| First review of material from operating experience | 15 to 16 | Version 0.3 | Gate 4 input |
| Retention check at [12] months after training | 22 to 24 | Retention report | Gate 5 |
| Handover of materials, records and trainer list to custodians | 22 to 24 | Handover record | **Gate 5** |

| Gate | Evidence from this document |
| --- | --- |
| Gate 0 | Capacity-building lead named. Training principle and budget line acknowledged |
| Gate 1 | Approved curriculum and assessment rules. Needs analysis method. Trainee targets, including inclusion targets. Costed budget. Local trainer plan |
| Gate 2 | Site Leads and safety officers trained. Trainee lists approved with hosts. Installers inducted. Vendor training obligations in contracts. Material packs drafted |
| Gate 3 | Operators and backups assessed competent with records. Drills completed. Utility and responder briefings done. Training numbers meet the Charter trigger. Registers complete (C5 Section 12) |
| Gate 4 | Refresher results, retention to date, drill repeat, material update, independent assessment sample |
| Gate 5 | Retention report. Materials, records and trainer list handed to custodians. Lessons in the replication guide (E3) |

**Compression warning.** Operator training depends on the equipment being on site, which depends on delivery at Months 8 to 11. Practical competence cannot be finished early. Lab and simulator training shortens site time, but it does not replace supervised on-site practice. If delivery slips, the stop-or-extend rule in C3 Section 14 applies and a Gate 3 shortfall in competent operators is reported as a trigger, not hidden.

## 17. Budget and resources

Training costs come from the training and capacity share (about 5% of the reference cost structure), the vendor contracts (which should include training), the PMO and the university partner's budget line (Charter Section 8, Stakeholder Plan Section 14). The Feasibility Study notes this share may be thin given the importance of local capacity (Feasibility Study Section 8.2), so the budget reconciliation tests it.

Cost items to itemise before Gate 1: trainer time and fees, assessor time, lab set-up and consumables, demonstration units and simulators, venues, travel and subsistence (Pilot B especially), trainee allowances or paid release, interpreters and translation, printing, offline devices and cards, first aid and PPE for training, certificates, record system, trainer development, responder and utility sessions, community sessions, refresher cycles, drills, and the retention follow-up. Amount: KSh \[to be confirmed at Gate 1\]. Any use of contingency for training needs Steering Committee approval (Charter Section 20). A safety module is never removed or shortened for cost without Programme Director approval and a documented risk assessment.

## 18. Risks to add to the live Risk Register

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| TR1 | Fewer trainees certified at Gate 3 than planned (Charter trigger) | M | H | Early nomination, two-per-site rule, supervised practice scheduled around delivery, stop-or-extend rule | Capacity-building lead |
| TR2 | Equipment arrives late, leaving too little time for on-site practice | M | H | Lab and simulator preparation, early manuals from vendors, flexible shifts, escalation | Technical Lead |
| TR3 | Trained operators leave or are unavailable | M | M | Trained backup, local trainer bench, refresher cycle, retention tracking, post-pilot plan | Site Leads |
| TR4 | Training is attended but competence is not demonstrated | M | H | Observed assessment, critical items, independent re-observation sample | Capacity-building lead |
| TR5 | Materials do not match installed equipment or firmware | M | M | Tie versions to C4 and B6, vendor manuals, update after changes | Technical Lead |
| TR6 | Trainees from marginal groups excluded by cost, time, language or venue | M | M | Needs analysis, allowances, accessible venues, targeted recruitment, local language | Capacity-building lead |
| TR7 | Vendor training late, thin or foreign-only | M | M | Training clauses in contracts, local technician requirement, acceptance condition | Procurement lead |
| TR8 | Unsafe practice during training, including trainees near live or battery equipment | L | H | No live work for trainees, ratios, demonstration safety plan, stop authority | Site engineer |
| TR9 | Training records lost, mishandled or used beyond purpose | L | H | D2 controls, access matrix, retention rules, breach process | Cybersecurity Officer |
| TR10 | Training under-budgeted | M | M | Itemise in budget reconciliation before Gate 1, protected line | Programme Manager |
| TR11 | Overreliance on a few foreign or university trainers | M | M | Train-the-trainer, local bench, custodian plan | Capacity-building lead |
| TR12 | Certificates mistaken for statutory licences, or used to claim competence beyond scope | L | M | Wording on certificate, briefing to hosts, verification route | Programme Director |
| TR13 | Community or host expectations of jobs or permanent assets raised by training | M | M | Honest messaging, host agreement wording, no promises (Stakeholder Plan 7.4) | Site Leads |

These risks are merged into the live Risk Register (README A6). Fewer than planned trainees certified at Gate 3 is a Charter escalation trigger.

## 19. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Set planned trainee numbers per group and site, including backups | Gate 1 | Capacity-building lead, Programme Director |
| 2 | Decide operator employment model (host staff, cooperative, vendor, programme-hired) and its effect on release and retention | Gate 1 | Programme Director |
| 3 | Decide allowances, paid release time and transport support for trainees | Gate 1 | Programme Manager, hosts, funders |
| 4 | Fix module hours, pass marks, retake rules and certificate validity | Gate 1 | Technical Lead, Capacity-building lead |
| 5 | Seek recognition of the curriculum by a university or vocational body | Gate 4 | University partner |
| 6 | Choose the open licence for materials, with counsel | Gate 3 | Capacity-building lead, counsel |
| 7 | Agree language mix per site and who produces Kiswahili and local-language versions | Gate 2 | Capacity-building lead |
| 8 | Obtain vendor manuals, alarm lists and training commitments for the selected devices | Gate 2 | Procurement lead, Technical Lead |
| 9 | Decide the lab venue, access and safety arrangements for technical modules | Month 4 | Technical Lead, university partner |
| 10 | Set inclusion targets for women, youth and people with disabilities | Gate 1 | Capacity-building lead, Programme Director |
| 11 | Decide how training records are stored at low-connectivity sites and who holds paper originals | Gate 2 | Cybersecurity Officer |
| 12 | Confirm lawful basis, consent wording and retention periods for training records | Gate 1 | Cybersecurity Officer, counsel |
| 13 | Agree the roles of Kenya Power and responders in training and drills, with lead times | Gate 2 | Technical Lead, Site Leads |
| 14 | Name the custodian of the curriculum, records and trainer list after closure | Gate 5 | Programme Sponsor |

## 20. Immediate next steps

1. Appoint the Capacity-building lead and approve this document in outline with the Charter at Gate 0.
2. Fix planned trainee numbers, the two-per-site rule and inclusion targets with the Programme Director and hosts.
3. Add training clauses, local technician requirements and delivery of manuals and alarm lists to the tender and vendor questionnaire (C1, B6 Appendix A).
4. Draft the needs analysis method, learning plan form and nomination process, and agree release terms with hosts.
5. Build the lab exercises on the lab Edge with the software engineer and the university partner.
6. Draft Kiswahili and local-language versions of the alarm card, safety essentials and community messages.
7. Set up the training register, attendance forms and secure storage under the D2 rules.
8. Plan the drill calendar and book Kenya Power and responder participation provisionally.
9. Itemise training costs for the budget reconciliation.
10. Add risks TR1 to TR13 and the open items to the PMO log and Risk Register.

---

# Appendix A: Attendance register (template)

| Field | Entry |
| --- | --- |
| Session ID and attendance record ID | `TS-[ ]` / `ATT-[ ]` |
| Module ID and title | [ ] |
| Date, start and end time, venue | [ ] |
| Format (classroom, practical, on-site, drill, online) | [ ] |
| Language of delivery and interpreter | [ ] |
| Trainer and co-trainer (names, level) | [ ] |
| Site or lab, pilot | [ ] |
| Materials version used | [ ] |
| Privacy notice read to participants (Y/N) | [ ] |

| # | Trainee ID | Name | Role and organisation | Signed in | Signed out | Partial attendance (minutes missed) | Identity checked by | Optional: gender, age group (aggregated use only) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| 2 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| 3 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

| Closing check | Entry |
| --- | --- |
| Number attended, number nominated, number absent | [ ] / [ ] / [ ] |
| Issues, safety incidents or near misses in the session | [ ] |
| Complaints or feedback raised | [ ] |
| Register checked by second person (name, date) | [ ] |
| Filed (location or system reference, date) | [ ] |
| Trainer signature | [ ] |

# Appendix B: Training register (master, template)

| Trainee ID | Name | Contact | Role and site | Employer or host | Pathway | Modules completed (IDs, dates) | Highest competence level | Competence records | Certificate ID and validity | Refresher due | Status (active, on leave, left) | Backup for (name) | Consent or notice recorded | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `TR-[ ]` | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | C[ ] | `CMP-[ ]` | `CERT-[ ]` | [ ] | [ ] | [ ] | [Y/N] | [ ] |

**Summary view for dashboard (no names).**

| Site | Planned | Enrolled | Attended core modules | C3 assessed competent | Backup competent (Y/N) | Retained at 12 months | Women (%) | Youth (%) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| B | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| C | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

# Appendix C: Competence assessment record (template)

| Field | Entry |
| --- | --- |
| Competence record ID | `CMP-[trainee ID]-[role or module]-[number]` |
| Trainee ID and name | [ ] |
| Role and pathway | [ ] |
| Site, unit and configuration tag assessed on | [ ] |
| Assessor (name, level) and any relationship with trainee | [ ] |
| Date, location, conditions | [ ] |
| Assessment type (practical, scenario, oral, written, work sample) | [ ] |

| Task or competence | Critical (Y/N) | Done unaided | Done with prompts | Not done | Evidence or comment |
| --- | --- | --- | --- | --- | --- |
| OC-01 Explains what operators may and may not do | Y | [ ] | [ ] | [ ] | [ ] |
| OC-02 Daily walk-round and UI check recorded | N | [ ] | [ ] | [ ] | [ ] |
| OC-03 Recognises mode and compares with signed record | Y | [ ] | [ ] | [ ] | [ ] |
| OC-04 Names alarm classes and first response | Y | [ ] | [ ] | [ ] | [ ] |
| OC-05 Responds to simulated fire or battery alarm | Y | [ ] | [ ] | [ ] | [ ] |
| OC-06 Uses emergency isolation correctly, explains when not to | Y | [ ] | [ ] | [ ] | [ ] |
| OC-07 Does not reset without cause, follows reset table | Y | [ ] | [ ] | [ ] | [ ] |
| OC-08 Reset and fault procedure within target time | N | [ ] | [ ] | [ ] | [ ] |
| OC-09 Uses and logs an override | Y | [ ] | [ ] | [ ] | [ ] |
| OC-10 Logbook, confounder and visitor logs accurate | N | [ ] | [ ] | [ ] | [ ] |
| OC-11 Security habits | Y | [ ] | [ ] | [ ] | [ ] |
| OC-12 Seals, data gaps and clock alarms | N | [ ] | [ ] | [ ] | [ ] |
| OC-13 Permit-to-work rule and escort | Y | [ ] | [ ] | [ ] | [ ] |
| OC-14 Return-to-service checklist items | N | [ ] | [ ] | [ ] | [ ] |
| OC-15 Honest explanation to a visitor | N | [ ] | [ ] | [ ] | [ ] |
| OC-16 Pilot-specific tasks | Y (safety items) | [ ] | [ ] | [ ] | [ ] |

| Result | Entry |
| --- | --- |
| Outcome (Competent C3 / Supervised C2 / Not yet) | [ ] |
| Critical items all passed (Y/N) | [ ] |
| Coaching actions, retake date | [ ] |
| Re-observed by independent assessor (Y/N, name) | [ ] |
| Signatures | Trainee [ ]; Assessor [ ]; Site Lead [ ]; Technical Lead (for operators) [ ] |

# Appendix D: Drill and familiarisation record (template)

| Field | Entry |
| --- | --- |
| Drill record ID | `DRL-[site]-[type]-[date]` |
| Type (fire and evacuation, battery alarm, spill, reset, security, loss of supply, community alert, responder visit) | [ ] |
| Site, date, start and end time | [ ] |
| Scenario and script version | [ ] |
| Participants (trainee IDs, roles, organisations) | [ ] |
| Responders, Kenya Power or host present | [ ] |
| Observers and timekeeper | [ ] |
| Key times (alarm raised, assembly complete, call made, safe state confirmed) | [ ] |
| Pass criterion and result | [ ] |
| Gaps found, owner, due date, retest date | [ ] |
| Notice given to host, community or users | [ ] |
| Signatures | Site Lead [ ]; Observer [ ]; Technical Lead [ ] |

# Appendix E: Site induction record (template)

| Field | Entry |
| --- | --- |
| Induction ID and date | [ ] |
| Name, organisation, role, licence number if relevant | [ ] |
| Hazards briefed (battery and fire, electrical, height, vehicles, weather, wildlife, public) | [ ] |
| Assembly point, emergency routes and contacts shown | [ ] |
| Stop authority and reporting explained | [ ] |
| PPE issued or checked | [ ] |
| Permit-to-work rule explained | [ ] |
| No tampering, no remote access, no photographs of credentials or network details | [ ] |
| Code of conduct and complaints route explained | [ ] |
| Check questions answered correctly | [ ] |
| Inducted by (name, signature) and person inducted (signature) | [ ] |
| Valid until, re-induction triggers | [ ] |

# Appendix F: Participant feedback form (template)

Short, anonymous, in English and Kiswahili, available orally for those who prefer it.

| # | Question | Response |
| --- | --- | --- |
| 1 | Was the content clear and useful for your job? | 1 to 5 |
| 2 | Was the language and pace right for you? | 1 to 5 |
| 3 | Did you have enough hands-on practice? | 1 to 5 |
| 4 | Did you feel safe and respected in the session? | Yes / No / Comment |
| 5 | What would you change? | Free text |
| 6 | Is there something you still do not feel confident to do? | Free text |
| 7 | Did anything prevent you attending fully (cost, time, venue, language)? | Free text |

Results are reviewed after each session, themes reported quarterly, and serious concerns routed to the Programme Manager.

# Appendix G: Programme competence certificate (template)

| Field | Entry |
| --- | --- |
| Certificate ID | `CERT-[trainee ID]-[role]-[number]` |
| Name | [ ] |
| Role and site | [ ] |
| Modules completed | [ ] |
| Competence level reached | C[ ] |
| Date of assessment, assessor name | [ ] |
| Valid until | [ ] |
| Statement | "This certificate records competence demonstrated on the OpenEMS Kenya pilot systems. It is not a statutory electrical or solar licence and does not replace one." |
| Issued by | Programme Director [name, signature, date] |

# Appendix H: Module outline sheets (template and two worked outlines)

**Template.**

| Field | Entry |
| --- | --- |
| Module ID, title, version, owner, reviewer | [ ] |
| Audience and prerequisites | [ ] |
| Learning outcomes (what the trainee can do) | [ ] |
| Format, duration, group size, venue | [ ] |
| Equipment and demonstration units | [ ] |
| Safety arrangements for the session | [ ] |
| Session plan with times | [ ] |
| Practical exercises and checklists | [ ] |
| Assessment method and critical items | [ ] |
| Handouts, cards, videos (IDs, languages) | [ ] |
| Source documents and vendor manual references | [ ] |
| Known updates needed | [ ] |

**Worked outline: TM-07 Alarms, first response and resets (3 hours).**

| Part | Time | Content | Method |
| --- | --- | --- | --- |
| 1 | 20 min | The four alarm classes and why hardware protects while OpenEMS supervises | Short talk, alarm card |
| 2 | 30 min | The alarm card step by step, with pictures. Why operators never reset an A1 and reset an A3 only once | Demonstration, discussion |
| 3 | 40 min | Fault table first checks on the lab Edge or demonstration unit: device offline, data gap, clock alarm, drift alarm | Hands-on in pairs |
| 4 | 30 min | Logging: what to write, how to word it, who to tell | Worked examples, logbook practice |
| 5 | 40 min | Escalation ladder and call practice, with times | Role-play with the contact list |
| 6 | 20 min | Check questions and the critical items (OC-04 and OC-07) | Oral, observed |

Learning outcomes: names the class of each alarm shown, performs the correct first response, refuses to reset an A1 or repeat-reset an A3, writes a correct log entry, calls the right person within the target time.

**Worked outline: TM-10 Security habits for operators (2 hours).**

| Part | Time | Content | Method |
| --- | --- | --- | --- |
| 1 | 15 min | What the system protects and why a small mistake matters | Talk with examples |
| 2 | 25 min | Named accounts, passwords, never sharing, never writing credentials where others see them | Demonstration, practice on the training account |
| 3 | 25 min | Spotting phishing, strange calls and visitors, USB and unknown devices | Examples, quick quiz |
| 4 | 25 min | Remote support rules: none before Gate 3, afterwards only the approved path, never hand control to a caller | Role-play of a phone request |
| 5 | 20 min | Seals, cabinets, escorts, visitor log | Walk-round demonstration |
| 6 | 10 min | Check and critical item OC-11 | Observed scenario |

Learning outcomes: uses only their own account, refuses a remote access request, reports an unknown device, keeps cabinets locked and visitors logged.

# Appendix I: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 5, 7, 8, 12, 15, 16, 18, 20, 22, 23, 24) | Local capacity principle, scope limit on core development, success criteria, training budget share, gates, risk trigger, change control, training KPI, independent review, closure |
| Feasibility Study (Sections 7.1, 8.2, 12) | Capacity risk, thin training budget, Gate 1 conditions |
| Stakeholder Engagement Plan (Sections 3, 4, 6.4, 7.3, 7.4, 8, 11, 12, 13, 14) | Inclusion, university partnership, community and driver sessions, local labour, retention risk, capacity indicators, budget |
| Technical Specification per Site (Sections 3, 5 to 7, 9) | System layers, safe states, acceptance tests, commissioning steps |
| Interoperability Register (Sections 3, 6, 9, 10) | Compatibility levels, test sets, vendor training commitments, version pinning |
| Cybersecurity Plan (Sections 6.1, 6.8, 10.6, 11, Appendix B) | Security training content, accounts, tabletop and drills |
| Health, Safety and Environmental Plan (Sections 6, 9, 10, 12, 13, 14, 15) | Induction, contractor competence, safeguarding, drills, responder familiarisation, incident classes |
| Installation and Commissioning Plan (Sections 8.9, 12, 13, 14, 17) | Trainee participation in commissioning, Gate 3 evidence, handover pack, schedule |
| OpenEMS Configuration Baseline (Sections 6.6, 10, 11) | Modes, change classes, backup and restore |
| Site Acceptance Test Reports (Sections 5, 12, tests A8, B9) | Operator drills, training verification TR-1 to TR-6 |
| Monitoring and Evaluation Plan (Sections 6.1, 7.5, 8) | Training indicators, confounder log, meter care |
| Data Management and Privacy Plan (Sections 4, 6, 8, 9, 10, 11, 12, Appendix A DS07) | Lawful basis, access, retention, publication, breach handling for training records |
| Operations and Maintenance Manual (Sections 5, 6, 7, 8, 9, 10, 11, 12, 13, 16) | Competence content, operator limits, routines, alarms, emergency procedures, staffing rules |
| Procurement Plan (Sections 7, 9, 11) | Vendor training and local service obligations |
| MoU and Site Agreement templates (MoU Schedule 1B, 1C; Site Agreement 4.1, 11, Schedules 5, 7) | University role, utility boundary, host release of trainees, compensation, training duty |
| Regulatory Compliance Assessment (Sections 5.8, 5.9, 6) | Licensed contractors, research approvals |

On completion of the Gate 1 decisions (trainee numbers, hours, pass marks, allowances, targets), the vendor manuals and the tender award, each bracketed value is updated, site-specific training packs are issued with the handover pack, and this document is re-issued as version 1.0 for Gate 2.

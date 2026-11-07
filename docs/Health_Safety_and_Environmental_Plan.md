# Health, Safety and Environmental Plan

## 1. Purpose and bottom line

The Charter requires safety plans to be approved before installation and incidents to be reported to the Steering Committee (Section 19). The Installation and Commissioning Plan (C3) makes the approved site safety plan, battery fire risk assessment and emergency response plan a Gate 2 condition. This document (C6) is the programme-level plan that those site documents must follow. It covers the hazards of building, commissioning, operating, maintaining and closing three pilot sites, the controls for each, who is responsible, how incidents are handled, and how environmental harm is prevented, including battery end of life.

**Bottom line.** The programme's hazards are concentrated in a few places: lithium battery systems, live electrical work, fast chargers on a public site, a remote rural build with community exposure, and the handling and disposal of batteries at the end of the pilot. Seven rules follow:

1. **Hardware protects, OpenEMS supervises.** Battery management systems, inverter protection, breakers and fire detection act independently of OpenEMS and the network. Commissioning proves them before OpenEMS is allowed to command anything (B4 design rule 4, C3 Phase 6).
2. **Competent people only.** Electrical work is done by licensed contractors, named supervisors are on site every working day, and nobody works on a system they have not been inducted on.
3. **Hold points are real.** No energisation, no OpenEMS enablement and no go-live without a signed hold point (C3 Section 7).
4. **Anyone may stop work.** A stop is never penalised. Work resumes only on the Site Lead's written release.
5. **Plan for the fire before the battery arrives.** Fire risk assessment, detection, suppression type, responder briefing and insurer acceptance are in place before batteries are placed on site.
6. **Environment is part of the build, not an afterthought.** Waste, spills, drainage, wildlife and battery take-back are fixed before procurement, not at closure.
7. **Communities and the public are protected as carefully as workers.** Children, livestock, drivers and neighbours are named in the controls, not assumed.

**What cannot be settled from desk research.** No site is selected or surveyed. Site layouts, topology at Pilot B, battery chemistry and container design, local fire and ambulance response times, and county permit rules will change the detail. This plan fixes the method, minimum controls and responsibilities, and leaves site-specific values as placeholders for each site safety plan.

## 2. Document control and relationships

**Owner:** Site engineer (README C6), under the Technical Lead. **Contributors:** Site Leads, licensed electrical contractor, Cybersecurity and Data Protection Officer, Kenya Power grid engineer (TWG), insurer or broker, local fire and emergency responders, community liaison officers, university partner (student safety). **Approval:** Programme Director at Gate 1 (method), site plans approved at Gate 2 and frozen as the build baseline. Reviewed fortnightly in the TWG during build, monthly in operation. Changes follow Charter Section 20 change control.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 12, 19, 20, 23) | Safety before speed, safety governance, change control, commissioning checklist |
| Feasibility Study (Sections 7.2, 7.3, 9) | Battery fire and thermal risk, environmental safeguards, risk 9 |
| Technical Specification per Site (B4, Sections 3.2, 3.6) | Design rules, safety baseline, battery location, isolation and signage |
| Interoperability Register (B6) | Battery and charger safety certification, BMS limits, tested protections |
| Cybersecurity Plan (B7) | Cyber events that could cause unsafe states, incident response, physical security |
| Regulatory Compliance Assessment (B5, Sections 5.8, 6) | OSH, fire, NEMA, county and waste rules to confirm |
| Installation and Commissioning Plan (C3, Sections 8 to 15) | Phases, hold points, permit to work, punch list, emergency drills |
| Site Acceptance Test Reports (C5) | Safety test evidence, witnesses and stop authority |
| Procurement Plan (C1) | Safety clauses, certification, insurance, end-of-life and take-back in contracts |
| MoU and Site Agreement templates (Site Agreement Sections 5, 13, 14, 17, Schedules 4, 7) | Site safety duties, insurance, liability, safeguards, decommissioning |
| Stakeholder Engagement Plan (Sections 7.3, 11) | Notice of works, community protection, grievance channel |
| Operations and maintenance manual (D3) | Receives the operating safety rules and emergency procedures |

## 3. Principles

| Principle | What it means in practice |
| --- | --- |
| Safety before schedule | Schedule pressure is never a reason to skip a check. Slippage goes to the stop-or-extend rule (C3 Section 14) |
| Eliminate, then control | Remove the hazard where possible (for example de-energise, isolate, relocate). Then engineer it out, then use procedures, then PPE |
| Proportionate | Controls scale with risk. A 250 kWh battery room and a school-adjacent village microgrid need the same logic but different physical measures |
| Assume the first response is local | Fire, medical and spill response must work with local resources and travel times, not assumed urban standards |
| Report and learn | Near misses are reported and not penalised. Lessons are shared at Gates 3 and 5 (Charter Section 23) |
| Honest records | Incidents, failed tests and workarounds are recorded with equal prominence to successes |
| Inclusive protection | Controls consider children, people with disabilities, women working on site, elderly residents and livestock owners |
| Environmental duty of care | The programme is responsible for equipment from delivery to compliant disposal, whoever holds title |
| Open by default | The plan and non-sensitive incident summaries are published after review. Personal and security-sensitive details are withheld |

## 4. Scope

**In scope.** All programme activity at Pilots A, B and C and at the test lab: transport and storage of equipment, site preparation and civil works, mechanical and electrical installation, commissioning and testing, operation and routine maintenance, training, community and public interfaces, closure, decommissioning and disposal. Persons covered: programme staff, contractors, vendors, hosts' staff, students and trainees, visitors, EV drivers, community members and responders.

**Out of scope.** Kenya Power's own assets and procedures (the programme follows its requirements but does not manage them), host operations unrelated to the pilot, and transmission-level work. Where host rules are stricter than this plan, the stricter rule applies.

## 5. Legal and standards basis

Regulatory texts were not reviewed line by line. The register below lists what is likely to apply and must be confirmed by counsel and the Regulatory Compliance Assessment (B5).

| Topic | Instrument or standard (to confirm) | Use in this plan |
| --- | --- | --- |
| Workplace safety | Occupational Safety and Health Act, 2007, and its rules, including fire safety rules \[confirm current instruments\] | Duty of care, risk assessment, registered workplace requirements, fire safety |
| Work injury | Work Injury Benefits Act, 2007 \[confirm\] | Insurance for workers, injury reporting |
| Electrical work | Energy Act, 2019 and EPRA licensing of electrical and solar contractors \[confirm\] | Licensed contractors only |
| Environment | Environmental Management and Coordination Act, 1999, EIA rules, waste management rules \[confirm thresholds\] | Screening, waste handling, battery waste |
| Public health | County public health and building rules \[confirm\] | Site hygiene, building and fire permits |
| Data and privacy | Data Protection Act, 2019 | Incident records containing personal data |
| Utility requirements | Kenya Power grid code, protection and metering standards \[confirm current versions\] | Isolation, protection, witness of energisation |
| Equipment standards | IEC or equivalent for batteries, inverters, chargers, electrical installation \[standards to be named with Kenya Power and the insurer\] | Certification, acceptance |
| Insurance | Policy conditions for battery installations | Insurer acceptance before installation |

**Rule.** Where a legal requirement is unclear, the programme asks the authority in writing and records the answer. A missing answer does not weaken a control.

## 6. Roles and responsibilities

| Role | Safety, health and environment responsibility |
| --- | --- |
| Steering Committee | Approves this plan at Gate 1 and site plans at Gate 2. Receives all serious incidents immediately and a quarterly summary. Decides on accepted high risks |
| Programme Director | Accountable for safety governance. Signs hold point H0 and H8. Handles regulator, insurer and law enforcement communication |
| Programme Manager and PMO | Tracks incidents, actions, risks and budget. Includes safety items on the monthly dashboard |
| Technical Lead | Approves method statements and design safety. Signs H1 to H3 and H6 and H7 |
| Site engineer (C6 owner) | Maintains this plan, hazard registers, audits and training records. Supports Site Leads |
| Site Lead (per pilot) | Accountable for site safety, permits to work, daily briefing, stop authority, first response and incident reporting |
| Licensed electrical contractor | Competent electrical work, isolation, testing, safety certificate, compliance with permit to work |
| Safety officer or competent person \[to be appointed per site or shared\] | Day-to-day site safety checks, inductions, toolbox briefings, near-miss log |
| Cybersecurity and Data Protection Officer | Cyber events with safety effect, physical security, incident coordination (B7 Section 10) |
| Host representative | Site rules, access, hazard disclosure, emergency contacts, co-signs the commissioning certificate |
| Community liaison officer | Notice of works, community briefings, complaints and concerns from residents |
| Contractors and vendors | Follow the site safety plan, supply method statements, certificates and trained staff, report incidents within \[24\] hours |
| Operators and trainees | Follow D3 procedures, stop and report unsafe conditions, never bypass protection |
| Kenya Power grid engineer | Advises on isolation, protection settings, energisation and utility interface safety |
| Insurer or broker | Reviews battery installations, sets conditions, reviews incidents |
| Local fire and emergency responders | Briefed on the site, consulted on response plan and access |

**Stop authority.** Every person on a programme site has the authority and the duty to stop work they believe is unsafe. The Site Lead decides when work resumes and records the decision.

## 7. Hazard and risk assessment method

### 7.1 Method

1. **Identify** hazards by activity, using the register in Section 8 and site survey data (B3 sections A8, B7).
2. **Assess** likelihood (L) and severity (S) before controls, each on a scale of 1 to 5, and compute a rating R = L x S.
3. **Control** using the hierarchy: eliminate, substitute, engineer, administer, protect with PPE.
4. **Re-assess** residual risk. Any residual rating above \[12\] needs Programme Director approval, and above \[16\] needs Steering Committee approval.
5. **Record** in the site hazard register (Appendix A), with owner, review date and verification.
6. **Review** at each hold point, after any incident, after any change of design, method or site condition, and at least \[quarterly\] in operation.

| Rating | Level | Action |
| --- | --- | --- |
| 1 to 4 | Low | Manage by routine controls |
| 5 to 9 | Medium | Specific controls and named owner |
| 10 to 15 | High | Controls verified before work. Programme Director informed |
| 16 to 25 | Very high | Work does not start. Redesign or reduce risk first |

### 7.2 Method statements and safety plans

Every site has, before H0: a site safety plan, a method statement per phase (C3 Phases 2 to 8), a battery fire risk assessment, an emergency response plan, an environmental management plan (Section 11) and an induction pack. These are approved by the Technical Lead and Site Lead, reviewed by the independent reviewer (Charter Section 23) and agreed with the host and local responders. Contractors submit their own method statements, which are reviewed against this plan.

## 8. Hazard register (programme level)

Initial ratings are judgements for validation at each site survey. L and S are 1 to 5. R is the rating before controls.

| # | Hazard | Phase | Pilots | L | S | R | Main controls (section) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| H1 | Electric shock or arc flash during installation, testing or maintenance | 3 to 8, operation | A, B, C | 3 | 5 | 15 | Licensed contractors, isolation and lock-out, permit to work, testing before touching, arc-rated PPE where required (9.1) |
| H2 | Battery fire, thermal runaway or toxic gas release | 1, 6 to 8, operation | A, B, C (optional) | 2 | 5 | 10 | Certified batteries, BMS, detection and suppression, separation, staged first cycles, responder plan (9.2) |
| H3 | Fast charger fault, overheating or electric shock to public | 7, operation | C | 2 | 4 | 8 | Certified chargers, protection, signage, inspection, separation from works (9.5) |
| H4 | Fall from height (roof PV, scaffolds, ladders) | 2, 3, maintenance | A, B | 3 | 5 | 15 | Fall protection, structural check, permit to work, no work in high wind or rain (9.3) |
| H5 | Manual handling and lifting of heavy equipment (batteries, inverters, modules) | 1 to 3 | All | 4 | 3 | 12 | Mechanical aids, lifting plans, trained crews, weight labelling (9.4) |
| H6 | Vehicle and traffic collisions on site and on delivery routes | 1 to 3 | All | 3 | 4 | 12 | Traffic plan, banksman, speed limits, public separation, remote-route journey plan (9.6) |
| H7 | Excavation collapse and striking buried services | 2 | A, B, C | 2 | 4 | 8 | Service search, shoring, permit, hand digging near services (9.4) |
| H8 | Heat stress, sun exposure, dehydration, insect and snake bites | 2 to 3, maintenance | B especially | 4 | 3 | 12 | Work scheduling, water and shade, first aid, local knowledge (9.7) |
| H9 | Lightning strike on PV arrays, cabinets or workers | All | B, A | 3 | 5 | 15 | Lightning protection and earthing, stop work in storms, weather monitoring (9.1) |
| H10 | Unauthorised access by children, livestock, public | 2 to operation | B, C, A | 3 | 4 | 12 | Fencing, signage, lockable enclosures, community briefings (10) |
| H11 | Chemical exposure and spills (electrolyte, coolant, fuel, hydraulic oil) | 1 to 3, maintenance, closure | All, B (diesel) | 2 | 3 | 6 | Spill kits, bunding, safety data sheets, trained handlers (11.3) |
| H12 | Unsafe state caused by a cyber event or setpoint error | Operation | All | 1 | 5 | 5 | Hardware limits, plausibility limits, safe states, no remote safety edits (B7 6.3) |
| H13 | Poor ergonomics, noise, dust and manual work fatigue | 2 to 3 | All | 3 | 2 | 6 | Rotation, breaks, hearing and dust protection |
| H14 | Violence, theft confrontation, harassment or gender-based risk to workers and community | All | B especially | 2 | 4 | 8 | Security plan, no lone working, code of conduct, grievance channel (10) |
| H15 | Fire from hot work, waste or vegetation near PV and batteries | 2 to 3, operation | B, A | 2 | 4 | 8 | Hot work permits, clearance zones, extinguishers (9.2) |
| H16 | Disease and public health risks (communicable disease, poor sanitation at remote work camp) | 2 to 3 | B | 2 | 3 | 6 | Welfare facilities, health briefings, referral route |
| H17 | Students or trainees injured during site learning | Training | All | 2 | 4 | 8 | Induction, supervision ratios, no live work by trainees (12) |
| H18 | Environmental release at end of life (battery waste, e-waste) | Closure | All | 3 | 3 | 9 | Take-back, licensed handlers, decommissioning plan (11.5) |

Ratings feed the live Risk Register (README A6) as programme risks, with the highest (H1, H4, H9 and H2) reviewed at every PMO review during build.

## 9. Core controls by hazard family

### 9.1 Electrical safety

| Control | Requirement |
| --- | --- |
| Competence | Work done only by contractors holding the licences required by EPRA and Kenyan law \[confirm lists\]. Named supervisors present every working day. Evidence of competence checked at induction |
| Isolation | Documented isolation points. Lock-out and tag-out with individual locks. Proving dead with a tested instrument before touching. Try-and-test and re-test after any break |
| Permit to work | Permit required for isolation, live testing, hot work, work at height and excavation. Issued and closed by the Site Lead or delegate daily (C3 Section 15) |
| Live work | Prohibited by default. Exceptions need a written justification, a second competent person and Technical Lead approval |
| Staged energisation | As C3 Phase 6. Kenya Power informed. A named person on site with authority to isolate. Hardware protection proven first |
| Testing | Insulation, continuity, polarity, earth loop impedance, protection settings, with recorded values and a signed safety certificate before energisation (tests A1, B1, C1) |
| Arc flash and DC hazards | Battery and PV DC circuits are always live when exposed to light or stored energy. Insulated tools, DC-rated isolators, arc-rated PPE where the hazard study requires |
| Lightning | Lightning protection and earthing designed to standard, tested and recorded. Work on roofs, arrays and open ground stops on the Site Lead's call when storms approach \[weather watch method to be set\] |
| Signage and labelling | Warning labels, circuit labels, emergency stop and isolation signage in English and Kiswahili where relevant |

### 9.2 Battery and fire safety

| Control | Requirement |
| --- | --- |
| Certification | Battery systems certified to the named standard \[IEC or UL standard, confirmed with Kenya Power and the insurer\]. Certificates on file before procurement award (B4 3.3, C1 Section 7) |
| Fire risk assessment | Site-specific, completed by a competent person with specialist input \[needed\] before the battery is delivered. Covers location, separation from occupied areas and fuel stores, ventilation, detection, suppression, thermal and gas hazards, access for responders |
| Detection | Smoke, heat and, where the assessment requires, gas detection, independent of OpenEMS. Alarms reach a named responder and the Site Lead by a path that works without internet |
| Suppression | Type and quantity set by the assessment \[specialist input needed\]. Not assumed to be water-only or gas-only. Responders briefed on what the system does and what it does not do |
| Separation | Battery room or container located away from occupied buildings, fuel stores, vehicle routes and combustible vegetation. Clearance distance \[x m\] set by the assessment |
| Thermal management | Ventilation or cooling suited to local ambient temperature, dust and humidity (B4 3.3). Temperature monitored and alarmed |
| Staged first cycles | Low-power cycles first, with observation of cell temperatures and voltages, thermal imaging where available (C3 8.7) |
| Storage before installation | Controlled access, ventilation, fire precautions, limits on state of charge and quantity as the vendor and insurer require (C3 8.2) |
| Hot work | Permit required. Fire watch for \[60\] minutes after work. No hot work within \[x m\] of batteries |
| Vegetation and housekeeping | Cleared zone around PV, batteries and cabinets. No combustible storage in battery rooms. Waste removed daily |
| Emergency response | Plan agreed with local fire and emergency responders, including access routes, isolation points, what to do on alarm and a no-entry rule for non-responders. Familiarisation visit before energisation |
| Insurance | Insurer notified and acceptance recorded before installation (Site Agreement 13) |
| Post-incident | Any thermal event or alarm: isolate, keep clear, call responders, preserve evidence, no re-energisation until root cause is known (B7 10.5 playbook) |

### 9.3 Work at height

A structural check of roofs and mounting precedes any work on them. Fall protection (guardrails, harnesses and anchor points, or fall arrest) is provided and inspected. Ladders and scaffolds are used only if inspected and tagged. No work on roofs in rain, high wind, storm approach or low light. No lone work at height. Rescue arrangements are part of the method statement.

### 9.4 Manual handling, lifting and excavation

Weights of batteries, inverters and modules are recorded in the method statement. Mechanical aids are used for loads above \[x kg\]. Lifts are planned, with competent operators and inspected equipment. Excavation needs a services search, shoring or battering as the ground requires, edge protection and a permit. Hand digging is used near known or suspected services.

### 9.5 EV chargers and the public interface (Pilot C)

Works are phased so that the public is separated from construction by barriers and signage (C3 Section 11). Chargers are installed with their own protection and a configured fallback limit before OpenEMS control is enabled. Customer-accessible ports and screens are separated from the control network. Cable management, trip hazards, lighting, emergency stop and clear instructions for drivers are provided. Public liability cover is confirmed before works. Throttling messages explain why charging is slower so that drivers do not tamper with equipment. Thermal safety inspection of chargers forms part of routine maintenance.

### 9.6 Transport, traffic and remote logistics

A traffic management plan covers delivery routes, site access, speed limits, banksmen and pedestrian separation. For Pilot B, a journey plan for each delivery covers road condition, season, daylight, fuel, communications, escort and recovery. Batteries are transported by competent carriers under the transport rules applicable to the cargo class \[confirm\]. Equipment is not left unattended before locked enclosures are fitted (C3 Section 10).

### 9.7 Health and welfare

Potable water, shade or shelter, toilet and handwashing facilities, first aid kits and trained first aiders are provided at every site. Work is scheduled to limit heat stress. Workers are briefed on local hazards including snakes, insects and wildlife. Referral routes to the nearest clinic and hospital, with travel times, are on the site emergency sheet. Workers' injuries are covered by the insurance required under the applicable work injury rules \[confirm\].

### 9.8 Personal protective equipment

PPE is the last line of defence. Minimum: safety footwear, hard hat where overhead or lifting risk exists, high-visibility clothing, gloves suited to the task, eye protection, hearing protection where noise exceeds \[x dB\], insulated tools and arc-rated PPE as assessed, and fall protection. PPE is supplied, fitted, inspected and replaced by the employer or contractor, and worn as the site safety plan requires. Visitors are inducted and wear PPE.

## 10. Community and public safety

The Stakeholder Engagement Plan requires notice of construction, expected disruption and safety precautions before works begin, with attention to children, livestock and traffic near the site (Section 7.3). This plan turns that into controls.

| Control | Requirement |
| --- | --- |
| Notice | Plain-language notice in English and Kiswahili before works start, before each outage and before test windows. Delivered by community meetings, notice boards and local channels |
| Perimeter | Fencing and signage around PV, battery and cabinets before equipment is placed. Gates locked outside working hours |
| Children and livestock | Briefings through schools and local leaders. Pictorial signs. Livestock routes kept clear of works. No unattended open trenches or lifting areas |
| Supply continuity | Planned interruptions agreed with the operator and announced. Transfer plan to existing supply or generator rehearsed (Pilot B) |
| Noise, dust and traffic | Working hours agreed with the host or community. Dust and noise controls. Speed limits on community roads |
| Security of workers and community | No lone working. Code of conduct for all workers covering respectful behaviour and prohibiting harassment and exploitation. Safe, confidential complaint route including for gender-based concerns. Local security arrangements agreed with the community, not imposed |
| Complaints | At least two ways to raise a concern at each site, acknowledgement in \[3\] working days, safety concerns escalated immediately (Stakeholder Plan Section 11) |
| Public information at Pilot C | Signage on throttling, fire and emergency instructions, privacy notice, how to report a fault or injury |
| Local labour | Local workers are inducted and protected on the same terms as others. No child labour. Minimum age rules applied \[confirm\] |

## 11. Environmental management

### 11.1 Principles and screening

Each site undergoes environmental screening at site selection and again at design, including battery location, drainage, flood risk, wildlife, vegetation, water sources and waste routes. NEMA screening requirements are confirmed per site \[thresholds to confirm, B5\]. County permits are identified at selection and tracked in the C3 readiness checklist.

### 11.2 Environmental management plan per site

Each site plan states: environmental risks and controls, waste streams and handlers, spill response, protection of water and vegetation, noise and dust controls, working-hour limits, monitoring and reporting, and responsible persons. It is approved before H0 and reviewed at each hold point.

### 11.3 Spill, chemical and fuel control

Safety data sheets are held on site for every hazardous product. Spill kits are sited near batteries, generators, fuel stores and chargers. Fuel and oil are stored in bunded, locked containers away from drains and water. Refuelling is controlled and supervised. Spill response is practised at induction. Contaminated material is collected and disposed of through licensed handlers \[confirm\]. Any significant release is reported as an incident (Section 14).

### 11.4 Waste management

| Waste stream | Control |
| --- | --- |
| Packaging (wood, cardboard, plastic) | Segregate, reuse where possible, remove through approved handlers. No burning of waste |
| Cable offcuts and metal | Segregate, secure to avoid theft, recycle through approved handlers |
| Damaged or end-of-life batteries | Treated as hazardous. Isolated, labelled and stored safely. Returned to the vendor or collected by licensed handlers under the take-back clause. Never landfilled or burned |
| Electronic waste (Edge computers, meters, chargers) | Data erased securely. Collected by licensed e-waste handlers |
| Excavated soil and civil waste | Reused on site where suitable. Surplus removed to approved locations |
| General and sanitary waste | Collected and disposed of through county arrangements, with welfare facilities maintained |

A waste log records quantity, handler, licence number and destination for hazardous waste.

### 11.5 Battery end of life and decommissioning

Battery end of life is fixed before procurement (Feasibility Study 7.3, C1 Section 7). Equipment title follows Schedule 4 of each site agreement, but the programme remains responsible for safe decommissioning until handover is accepted. Requirements: a take-back or compliant disposal route in every battery contract with data erase for devices; a decommissioning method statement approved before closure; discharge, isolation and packaging under vendor guidance; transport by competent carriers under the applicable rules \[confirm\]; records kept for \[x\] years; cost allocation stated in Schedule 4 and the budget. If equipment transfers to a host or custodian, the receiving party is briefed on its end-of-life duties in writing.

## 12. Induction, training and competence

| Group | Training | Assessment | Timing |
| --- | --- | --- | --- |
| All workers and visitors | Site induction: hazards, emergency routes, assembly point, stop authority, reporting, PPE, permit system, no remote access or tampering with equipment | Signed induction record | Before first entry |
| Contractors and installers | Method statement briefing, isolation and lock-out, battery handling, work at height, fire response, spill response, code of conduct | Competence check and licence verification | Before H0 and when crews change |
| Operators and trainees | Operating safety: safe states, override and logging rule, alarm response, emergency isolation, first-response fire and spill actions, incident reporting (links to D3 and D4, B7 Section 11) | Assessed competence and drill | Before Gate 3, refreshed \[annually\] |
| Site Leads and safety officers | Risk assessment, permit to work, incident investigation, first aid, emergency coordination | Certificate or competence record | Before Gate 2 |
| Students and university staff | Induction, supervision, restricted tasks | Induction record | Before any site visit |
| Community liaison officers | Safety messages, grievance handling, safeguarding, referral routes | Briefing record | Before H0 |
| Local responders | Site familiarisation: layout, isolation points, battery behaviour, what the suppression system does, no-entry rule | Visit record | Before energisation (H5) |

**Rules.** Trainees never perform live work. Trainees take part in at least one commissioning test under supervision (C3 8.9). Training records are kept in D4 and reported on the dashboard with the Charter training KPI.

## 13. Contractor and vendor safety management

| Step | Requirement |
| --- | --- |
| Pre-qualification | Safety record, HSE policy, licences, insurance, named supervisors, references (C1 Appendix B) |
| Tender | Safety and environmental clauses, certificates, take-back and end-of-life terms in every battery contract, price for safe working included |
| Contract | Compliance with this plan and site safety plan, reporting of incidents within \[24\] hours, right of the Site Lead to stop work, audit access, insurance certificates before delivery |
| Method statements | Submitted, reviewed and approved before the relevant phase |
| Monitoring | Daily site records, toolbox briefings, weekly safety walk by the Site Lead, monthly review by the site engineer |
| Sanctions | Repeated breach leads to removal of the crew or termination under C1 Section 11.2 |
| Subcontractors | Named and approved. Same standards apply. No unapproved subcontracting |

## 14. Incident reporting, investigation and response

### 14.1 Classification

| Class | Examples | Response |
| --- | --- | --- |
| 1 Fatality or life-changing injury, fire, thermal event, explosion, major release, serious public harm | Battery thermal event, electrocution, fire, vehicle fatality | Emergency response first. Site stopped. Notify Site Lead immediately, PMO and Programme Director within \[1\] hour, SteerCo Chair, Kenya Power, insurer and statutory bodies as the law requires \[confirm\] |
| 2 Lost-time injury, medical treatment, significant spill, damage to equipment or property, unsafe state caused by a control failure | Fall with injury, fuel spill reaching drains | Make safe. Report within \[24\] hours. Investigation required |
| 3 Near miss, first aid case, minor spill, unsafe act or condition | Dropped tool, missing guard | Report same day. Local fix and learning |
| 4 Observation | Good practice or improvement idea | Log and review monthly |

Cyber events with a safety effect follow the Cybersecurity Plan (B7 Section 10) and are also logged here. Personal data in incident records is handled under the Data Protection Act, 2019.

### 14.2 Response and investigation

1. **Make safe.** Protect life first. Isolate equipment, call responders, evacuate as the plan says. Nobody re-enters a battery or fire area except trained responders.
2. **Report.** The Site Lead notifies by the route in the site emergency sheet. Contact lists are on every cabinet and in D3.
3. **Preserve.** Keep the scene, logs, images and equipment as they are, unless that creates danger.
4. **Investigate.** A blameless review within \[10\] working days for Class 1 and 2. A root-cause method is used. For Class 1, an independent person leads. The insurer and, where required, the regulator take part.
5. **Act.** Corrective actions have owners and dates and are tracked by the PMO.
6. **Learn.** Findings go to the TWG, the risk register and the Gate 3 and Gate 5 lessons-learned reviews. A sanitised summary is published where useful.
7. **Resume.** Work restarts only on the Site Lead's written release, and for Class 1 on the Programme Director's approval.

A failed hold point test, a failed hardware protection test or any unexplained change to the safety set is treated as at least a Class 2 event (C4 Section 17).

## 15. Emergency preparedness

Each site has an emergency response plan covering: emergency contacts and responder numbers, assembly points, evacuation routes, who has authority to isolate, actions for fire, battery alarm, electric shock, serious injury, spill, lightning, severe weather, security threat and loss of communications. Plans are written in English and Kiswahili where relevant and displayed at site entrances and in the battery area.

| Element | Requirement |
| --- | --- |
| Response times | Travel times to the nearest fire station, clinic and hospital are recorded in the survey and used in the plan. Where times are long (Pilot B), the plan adds on-site capability and an evacuation route |
| Communications | A working communication method independent of the site network (mobile, radio or satellite as coverage requires) |
| First aid | Trained first aiders and kits on site at all working times. Defibrillator where the host has one nearby |
| Drills | A fire and evacuation drill before energisation. A battery alarm tabletop and a spill drill before Gate 3. Repeat at Gate 4 |
| Responder access | Gates, keys, lock boxes, signage and isolation point maps available to responders at any hour |
| Public alarm | At Pilot C, the plan covers evacuation of the public and fleet drivers |
| Community alert | At Pilot B, a simple alert route for nearby households if a battery event occurs |

## 16. Pilot-specific safety, health and environmental requirements

### 16.1 Pilot A: Industrial park, hub or campus

| Issue | Requirement |
| --- | --- |
| Host rules and permits | Follow the host's site permit system and induction, using the stricter rule where they differ. Agree one permit process with the host at H0 |
| Battery room | Fire detection, suppression, ventilation, access control and insurer acceptance verified (test AX-5). Separation from production, fuel and occupied areas |
| Production interface | Planned shutdowns agreed in writing. No production-critical load interrupted without host approval (C3 Section 9) |
| Existing inverters and switchboards | Condition and protection coordination reviewed by a licensed engineer. Warranty and safety implications of control checked before work |
| Staff and neighbours | Briefings on works, outages and emergency actions. Evacuation routes aligned with host plans |
| Campus case | Where the host is a campus, separate access for students and public, supervision rules for any teaching visits |
| Environment | Host waste systems used only if agreed. Battery and e-waste handled under Section 11 |

### 16.2 Pilot B: Rural microgrid

| Issue | Requirement |
| --- | --- |
| Remoteness | Emergency plan accounts for long response times. Spares, first aid, water and communications on site. Journey plans for deliveries and staff |
| Community | No works begin without documented informed community agreement. Fencing, signage and briefings protect children and livestock. Community alert route for emergencies |
| Security | Equipment and stores guarded or secured before enclosures are locked. Theft and vandalism risks reviewed with the community. No lone working |
| Lightning, flood, dust, heat, wildlife | Protections installed and verified at H5. Work stops in storms. Cabinets and batteries raised above flood level. Snake and insect precautions |
| Diesel generator | Fuel in bunded, locked storage. Spill kit. Exhaust and noise controlled. Generator keeps its own protection and fire precautions |
| Supply continuity | Planned interruptions agreed with the operator and announced. Transfer plan rehearsed. No disconnection or price rise to customers from the pilot |
| Welfare | Water, toilets, shade and a safe place to rest for workers. Local labour inducted and protected equally |
| Safeguarding | Code of conduct, confidential complaint route, community liaison in local languages |
| Environment | Care for vegetation and water sources. Wildlife-safe fencing and cable routing. Waste taken to approved locations. No burning |

### 16.3 Pilot C: EV charging site

| Issue | Requirement |
| --- | --- |
| Public interface | Barriers and signage separate the public from works. Phasing keeps part of the site safe for use. Public liability cover confirmed |
| Charger safety | Certified chargers with protection and fallback limits. Cable and connector inspection, emergency stop, thermal checks, lighting and clear instructions |
| Fire | Fire response plan covers vehicles on charge. Responders briefed on EV and battery hazards. Fire extinguishers and signage suited to electrical and vehicle fires \[type per assessment\] |
| Vehicle behaviour | Any vehicle that rejects power limiting is recorded and handled by the operator. Drivers are told how to stop a session safely |
| Transformer and utility interface | Isolation and switching follow Kenya Power rules. Site limit lowered first, raised only with Kenya Power agreement (C3 Section 11) |
| Customer behaviour | Throttling messages reduce tampering. Complaint route for drivers. Staff trained to manage upset customers |
| Environment | Spill kits for vehicles, drainage protection around chargers, waste from construction removed daily |
| Optional battery | Same fire and insurance controls as Section 9.2 |

### 16.4 Test lab

Battery and charger tests run under a written lab safety plan with a licensed electrician present for any mains work (B6 Section 6.1). Test batteries are stored and charged under fire precautions. Students are supervised. Unit return, purchase or disposal is agreed before testing (C1 Appendix C).

## 17. Operation, maintenance and closure

| Stage | Requirement |
| --- | --- |
| Routine checks | Operators follow D3 checks for batteries, cabinets, chargers, fire detection, signage, fencing, spill kits and drainage. Findings are logged |
| Planned maintenance | Permit to work, isolation, lock-out, two-person rule for electrical and battery work, notice to host or community |
| Alarms | Operators know the first response to each alarm class and who to call. Unresolved safety alarms are never reset without a recorded cause |
| Inspections | Monthly safety walk by the Site Lead. Quarterly inspection by the site engineer. Annual independent check where the insurer or law requires |
| Changes | Any change to layout, equipment, firmware or safe states follows change control, with a safety review for changes that affect protection (C4 Section 10) |
| Closure and decommissioning | Method statement approved before closure. De-energise, isolate, discharge and remove under vendor guidance and permit. Environmental handover and waste records. Equipment either removed or handed over with a written safety and end-of-life briefing (Schedule 4) |
| Post-pilot custody | Custodians are named for safety duties after the pilot (Charter Section 24), and receive this plan and the maintenance manual |

## 18. Monitoring, audit and performance measures

| Indicator | Measure | Target |
| --- | --- | --- |
| Serious incidents | Class 1 and 2 incidents per site and programme | Zero Class 1. Class 2 trend reviewed monthly \[targets set at Gate 1\] |
| Near-miss reporting | Reports per month and share closed on time | Rising reporting, \[x\]% closed on time |
| Hold point compliance | Hold points signed with all evidence before the next phase | 100% |
| Permit compliance | Permits issued and closed daily | 100% |
| Inspection findings | Open safety-critical items | Zero open at hold points |
| Training | Workers inducted, operators assessed competent | 100% inducted before entry. Competence target per Charter |
| Drills | Emergency drills completed on schedule | 100% before Gate 3 |
| Environmental | Spills, waste records complete, hazardous waste with licensed handler | Zero unreported spills. 100% waste records |
| Community | Safety-related complaints acknowledged and resolved on time | Per Stakeholder Plan Section 11 |
| Insurance and permits | Insurer acceptance, county, NEMA and fire permits in place | Before H0 for each site |

The monthly programme dashboard reports these items, with security incidents already a dashboard item under the Charter. Audits: a self-audit by the Site Lead monthly, an internal audit by the site engineer or an independent person each quarter during build and at Gate 4, and an independent safety review before Gate 3. Findings are tracked as non-conformances using the C3 severities.

## 19. Schedule and gate evidence

| Gate | Timing | Evidence from this plan |
| --- | --- | --- |
| Gate 0 | Month 0 | Plan accepted as baseline. Safety roles identified. Insurance approach agreed |
| Gate 1 | Months 4 to 6 | Method approved. Hazard register opened per candidate site. Fire and environmental screening started. Budget lines for safety, fire design, insurance and waste included in the validated budget |
| Gate 2 | Month 8 | Site safety plans, method statements, battery fire risk assessments, emergency response plans and environmental management plans approved. Insurer acceptance. Licences, county, NEMA and fire permits. Responder familiarisation planned. Installers inducted. Take-back and end-of-life terms in contracts |
| Gate 3 | Month 12 | Electrical safety certificates. Hardware protection proven. Emergency drills done. Operators trained. No open safety-critical non-conformance. Independent safety review. Lessons learned |
| Gate 4 | Month 18 | Incident and near-miss summary. Inspection and audit results. Drill repeat. Review of controls and any residual risks |
| Gate 5 | Month 24 | Decommissioning and handover safety. Waste and end-of-life records. Custodians briefed. Final safety and environmental report with lessons learned |

| Activity | Months | Output |
| --- | --- | --- |
| Approve method and templates with the TWG | 3 to 4 | This document v0.1 approved |
| Safety and environmental screening of candidate sites | 4 to 6 | Hazard registers, site screening notes |
| Fire risk assessments and responder engagement | 6 to 8 | Assessments and response plans |
| Insurer and permit confirmation | 6 to 8 | Letters and permits |
| Induction and training before mobilisation | 7 to 8 | Records |
| Build and commissioning controls | 8 to 12 | Daily records, permits, hold points |
| Drills and independent safety review | 11 to 12 | Gate 3 evidence |
| Operation, audits and drills | 13 to 24 | Monthly reports, Gate 4 review |
| Decommissioning and closure | 22 to 24 | Final report |

**Compression warning.** The window from award in Month 8 to Gate 3 in Month 12 puts pressure on safety checks. Any proposal to shorten a hold point, skip a witnessed test or reduce a safety control is refused and escalated, and the stop-or-extend rule in C3 Section 14 applies instead.

## 20. Budget and resources

Safety, health and environmental costs are drawn from the programme budget, mainly from installation and civil works, first-year O&M, training and the contingency, and from contractor prices. Cost items to be itemised in the budget reconciliation before Gate 1 (Feasibility Study 5.1) include: fire risk assessment and specialist input, detection and suppression, fencing and security, lightning protection, spill and waste handling, PPE and first aid, insurance premiums, responder familiarisation, independent safety review, drills, training, welfare facilities, battery take-back and decommissioning. Amount: KSh \[to be confirmed at Gate 1\]. Use of contingency for safety needs Steering Committee approval (Charter Section 20). A safety control is never removed for cost without Programme Director approval and a documented risk assessment.

## 21. Risks to add to the live Risk Register

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| HS1 | Battery fire or thermal event during commissioning or operation | L | H | Certified batteries, fire risk assessment, detection, staged cycles, responder plan | Site Leads |
| HS2 | Electrical injury due to unlicensed or rushed work | L | H | Licence checks, permit to work, hold points, supervision | Site Leads |
| HS3 | Schedule pressure leads to skipped or unwitnessed safety tests | M | H | Hold points, stop-or-extend rule, no certificate without signatures | Programme Director |
| HS4 | Long emergency response times at Pilot B | H | M | On-site capability, communications, community alert, journey plans | Site Lead B |
| HS5 | Insurer refuses or conditions battery cover | M | H | Early insurer engagement, standards agreed, design changes costed | Site Leads |
| HS6 | Safety and environment under-budgeted | M | M | Itemise in budget reconciliation, protected lines | Programme Manager |
| HS7 | Battery end of life unresolved at closure | M | M | Take-back clause in contracts, Schedule 4, decommissioning plan | Technical Lead |
| HS8 | Harm to children, livestock or public near works or chargers | M | H | Fencing, signage, briefings, phased works | Site Leads |
| HS9 | Worker welfare or safeguarding incident at remote site | L | H | Code of conduct, no lone working, confidential complaint route | Programme Manager |
| HS10 | Spill or waste mismanagement causes environmental harm | M | M | Spill kits, bunding, licensed handlers, waste log | Site Leads |
| HS11 | Weak safety culture or under-reporting among contractors | M | M | Non-retaliation, toolbox talks, audits, contract sanctions | Site engineer |
| HS12 | Cyber event causes an unsafe equipment state | L | H | Hardware limits, safe states, no remote safety edits (B7 6.3) | Cybersecurity Officer |

These risks are merged into the live Risk Register (README A6). A Class 1 incident is a Charter escalation event.

## 22. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Name the battery safety standard accepted by Kenya Power and the insurer | Procurement, H5 | Site Leads |
| 2 | Commission specialist input for battery fire design, detection and suppression | Gate 2 | Technical Lead |
| 3 | Confirm current OSH, fire, environment, waste and transport instruments with counsel | Gate 1 | Legal and regulatory lead |
| 4 | Confirm NEMA screening thresholds and county permits per site | Gate 2 | Site Leads |
| 5 | Confirm insurance structure, work injury cover and premium budget | Gate 1 | Programme Manager |
| 6 | Decide whether a dedicated safety officer is appointed per site or shared | Gate 1 | Programme Director |
| 7 | Agree response times and emergency capability at Pilot B | Gate 2 | Site Lead B |
| 8 | Set residual-risk approval thresholds and numeric targets for indicators | Gate 1 | Programme Director |
| 9 | Agree battery take-back terms and who pays decommissioning (Schedule 4) | Before procurement | Programme Sponsor |
| 10 | Decide arrangements with the host for permits to work at Pilot A | H0 | Site Lead A |
| 11 | Define weather-watch method for lightning and storm stop rules | Gate 2 | Technical Lead |
| 12 | Decide how incident summaries are published and what is withheld | Gate 3 | Programme Manager, Cybersecurity Officer |

## 23. Immediate next steps

1. TWG to review this plan, including the Kenya Power grid engineer on isolation and utility interface.
2. Appoint the site engineer as plan owner and decide on site safety officers.
3. Ask the insurer or broker for battery installation requirements and accepted standards.
4. Commission specialist input for battery fire risk assessments.
5. Open hazard registers for the candidate sites and attach them to the site survey reports.
6. Confirm legal instruments, permits and thresholds with counsel and the regulators.
7. Itemise safety, fire, insurance, waste and end-of-life costs in the budget reconciliation.
8. Draft induction packs, permit forms and emergency sheets in English and Kiswahili.
9. Agree take-back and decommissioning wording for the tender and Schedule 4.
10. Add risks HS1 to HS12 and the open items to the PMO log and Risk Register.

---

# Appendix A: Site hazard register (template)

| ID | Activity and phase | Hazard | Who is at risk | L before | S before | R before | Controls (hierarchy) | L after | S after | R after | Owner | Verified by, date | Review date |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] | \[ \] |

# Appendix B: Permit to work (template)

| Field | Entry |
| --- | --- |
| Permit number and type (isolation, hot work, height, excavation, confined or battery area) | \[ \] |
| Site, location and equipment | \[ \] |
| Work description and method statement reference | \[ \] |
| Hazards and controls | \[ \] |
| Isolation points, lock numbers, proved dead by (name, time) | \[ \] |
| PPE and equipment required | \[ \] |
| Workers and supervisor (names, licences) | \[ \] |
| Valid from and to | \[ \] |
| Issued by and accepted by (names, signatures) | \[ \] |
| Changes or suspension | \[ \] |
| Work complete, area made safe, locks removed (name, time) | \[ \] |
| Permit closed by | \[ \] |

# Appendix C: Incident and near-miss report (template)

| Field | Entry |
| --- | --- |
| Report ID | `INC-[site]-[number]` |
| Date, time, location | \[ \] |
| Class (1 to 4) | \[ \] |
| People involved (roles only where personal data should be limited) | \[ \] |
| Description of what happened | \[ \] |
| Immediate actions and injuries or damage | \[ \] |
| Environmental effect (spill quantity, waste, water or soil affected) | \[ \] |
| Equipment, configuration and firmware involved | \[ \] |
| Witnesses and evidence (photos, logs) | \[ \] |
| Notifications made (who, when) | \[ \] |
| Root cause and contributing factors | \[ \] |
| Corrective actions, owners, dates | \[ \] |
| Link to D5 log and risk register | \[ \] |
| Reviewed and closed by | \[ \] |

# Appendix D: Site emergency sheet (template)

| Item | Entry |
| --- | --- |
| Site address, GPS and access instructions for responders | \[ \] |
| Fire, ambulance, police, utility and insurer numbers | \[ \] |
| Nearest clinic and hospital, with travel time | \[ \] |
| Site Lead, deputy, host representative, Technical Lead, Cybersecurity Officer contacts | \[ \] |
| Kenya Power control or fault number | \[ \] |
| Assembly points and evacuation routes | \[ \] |
| Isolation points and location of emergency stops | \[ \] |
| Battery area warnings and no-entry rule | \[ \] |
| Spill kit and extinguisher locations | \[ \] |
| Communications method independent of the site network | \[ \] |
| Community alert route (Pilot B) and public evacuation (Pilot C) | \[ \] |

# Appendix E: Pre-energisation safety checklist (per site)

| # | Check | Evidence | Done |
| --- | --- | --- | --- |
| 1 | Fire risk assessment complete and its actions closed | Assessment, close-out | \[ \] |
| 2 | Detection and suppression installed, tested and linked to alarm path | Test record | \[ \] |
| 3 | Insurer acceptance and certificates exchanged | Insurer letter | \[ \] |
| 4 | Responders familiarised and emergency plan agreed | Visit record | \[ \] |
| 5 | Electrical safety certificate signed | Certificate | \[ \] |
| 6 | Earthing and lightning protection tested | Test values | \[ \] |
| 7 | Isolation, lock-out and emergency stop tested | Test record | \[ \] |
| 8 | Fencing, signage and access control in place | Photo log | \[ \] |
| 9 | Spill kits, extinguishers and first aid in place | Inspection | \[ \] |
| 10 | Operators and workers inducted. Drill completed | Records | \[ \] |
| 11 | Community, host or public notified | Notice record | \[ \] |
| 12 | Kenya Power approval received | Letter | \[ \] |
| 13 | Environmental management plan in place and waste handlers named | Plan, licences | \[ \] |
| 14 | Site Lead written authority to energise (H5) | H5 record | \[ \] |

# Appendix F: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 12, 16, 18, 19, 20, 21, 23, 24) | Safety principles, gates, risk triggers, safety governance, change control, independent review, closure |
| Feasibility Study (Sections 7.2, 7.3, 9) | Battery fire risk, environmental safeguards, risk register |
| Technical Specification per Site (Sections 3.2, 3.3, 3.6, 5 to 7, 9) | Design rules, equipment requirements, safety baseline, acceptance tests |
| Interoperability and Device Compatibility Register (Sections 4, 6.1, 9) | Safety certification, lab safety, vendor commitments |
| Cybersecurity Plan (Sections 6.3, 6.5, 10, 11) | Unsafe-state controls, physical security, incident response, training |
| Regulatory Compliance Assessment (Sections 5.8, 6, 9) | OSH, fire, environment, permits, gate readiness |
| Installation and Commissioning Plan (Sections 4, 8 to 11, 14, 15, Appendices A to D) | Hold points, permit to work, enablement order, emergency drills, stop-or-extend rule |
| Site Acceptance Test Reports (Sections 3, 4, 6 to 9, Appendix B) | Witnessed safety tests, stop authority, test-day checks |
| OpenEMS Configuration Baseline (Sections 6.4, 10) | Safety set, change classes, emergency changes |
| Procurement Plan (Sections 3, 7, 11, Appendix F) | Safety clauses, certification, take-back, insurance |
| MoU and Site Agreement templates (Site Agreement Sections 5, 13, 14, 17, Schedules 4, 5, 7) | Site safety duties, insurance, liability, safeguards, decommissioning |
| Site Survey Reports (A8, B7) | Fire, environment and site constraints to be surveyed |
| Stakeholder Engagement Plan (Sections 7.3, 7.4, 11) | Notice of works, community protection, grievance mechanism, local labour |

On completion of the site surveys, insurer and regulator responses and the Gate 2 design review, each bracketed value is updated and this document is re-issued as version 1.0 for Gate 2.

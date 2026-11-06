# Installation and Commissioning Plan

## 1. Purpose and bottom line

This plan sets out how the equipment bought through procurement (C1) becomes three working, safe, secure and measurable pilot installations. It turns the Technical Specification (B4), the Interoperability Register (B6), the Cybersecurity Plan (B7), the Regulatory Compliance Assessment (B5) and the Site Agreement templates into one sequence of work with hold points, acceptance criteria and handover evidence.

**Bottom line.** Installation and commissioning is the stage where the programme's schedule is most exposed and where its evidence is created. Five rules shape the plan:

1. **Nothing is energised or connected remotely on trust.** Every step has a hold point with a named approver. Remote access stays disabled until Gate 3.
2. **Lab proof comes first, site proof second.** Devices arrive having passed L3 in the lab (B6). Site work proves L4, meaning the same behaviour with real wiring, network and loads.
3. **Commissioning is also data collection.** Meters, loggers, time sync and the baseline are verified before any control mode is switched on, because the evaluation compares each site with its baseline (Charter Section 7).
4. **Hardware protects, OpenEMS supervises.** Commissioning proves that BMS, inverter, breaker and fire protections work on their own before OpenEMS is allowed to command anything (B4 design rule 4).
5. **Late commissioning costs evidence.** The evaluation needs at least 12 months of validated operating data. Slippage is managed through the stop-or-extend rule in Section 14, not absorbed silently.

**What cannot be settled from desk research.** No site is selected or surveyed. Site layouts, topology at Pilot B, lead times and the host's own rules will change the detail. This plan therefore fixes the method, sequence and gates, and leaves site-specific durations and values as placeholders for the site method statements.

## 2. Document control and relationships

**Owner:** Technical Lead (README C3). **Contributors:** site engineers, Site Leads, software engineer, Cybersecurity and Data Protection Officer, Research Lead, Kenya Power grid engineer (TWG), procurement lead, installers. **Approval:** Programme Director at Gate 2, then frozen as the build baseline. Reviewed fortnightly in the TWG during build. Changes follow Charter Section 20 change control.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 6, 16, 19, 20, 23) | Deliverable D5, gates, safety governance, change control, commissioning checklist requirement |
| Technical Specification per Site (B4, Sections 3 to 9) | Equipment requirements, safe states, acceptance tests A1 to A10, B1 to B10, C1 to C10, commissioning steps |
| Interoperability and Device Compatibility Register (B6) | Tested device and firmware set, L4 site re-verification, delta testing rules |
| Cybersecurity Plan (B7, Section 8, Appendix B) | Hardening, no-remote-access rule, commissioning security checklist, audit timing |
| Regulatory Compliance Assessment (B5) | Kenya Power acceptance, permits, licensed contractors, witness arrangements |
| Procurement Plan (C1) | Contracts, delivery dates, acceptance conditions, liquidated damages, warranty |
| Site Survey Reports (B3) | Site constraints, red items and existing equipment |
| MoU and Site Agreement templates (Site Agreement Sections 3 to 6, Schedules 2 to 4) | Conditions precedent, access, commissioning certificate, equipment list, safe states, closure |
| Stakeholder Engagement Plan (Sections 7.3, 8) | Community and staff notice before works, launch events |
| Health, safety and environmental plan (C6), Configuration baseline (C4), Acceptance test reports (C5) | Receive the safety rules, frozen versions and test evidence this plan produces |
| Operations and maintenance manual (D3), Training materials (D4) | Receive the handover pack and trained operators |

## 3. Scope

**In scope.** Receiving and inspecting equipment; site preparation and civil works; mechanical and electrical installation; Edge, network and measurement installation; pre-energisation checks; energisation; OpenEMS configuration; site acceptance testing; baseline recording; operator training; the independent audit window before Gate 3; commissioning certificates and handover to operations.

**Out of scope.** Procurement and lab compatibility testing (C1, B6); site selection and surveys (B3); operation, monitoring and maintenance after Gate 3 (D3); changes to utility assets. OpenEMS controls only assets behind the customer connection point, and the programme never changes Kenya Power protection settings (draft MoU Schedule 1B).

## 4. Principles

| Principle | What it means in practice |
| --- | --- |
| Safety before schedule | Any person may stop work. A stop is never penalised. Work resumes only on the Site Lead's written release |
| Hold points are real | A hold point is a stop. The next step starts only when the named approver signs |
| Prove the baseline | The measurement chain is verified before control is enabled. No control mode change outside the M&V schedule |
| Local first, offline first | Control and protection work on site. Offline operation is tested, not assumed |
| Least connectivity | Programme network separate from host IT. No remote access, tunnels or cloud sync before Gate 3 |
| Record everything | Serial numbers, firmware, settings, photos, test data and overrides are logged and stored with the configuration baseline |
| Honest reporting | Failed tests, workarounds and delays are recorded with equal prominence to passes (Charter Section 21) |
| Local capacity | Local technicians and operators take part in installation, not only in classroom training |

## 5. Roles and responsibilities

| Role | Responsibility in installation and commissioning |
| --- | --- |
| Steering Committee | Releases installation funds at Gate 2, authorises go-live at Gate 3, decides on any gate date movement or stop-or-extend trigger |
| Programme Director | Accountable for readiness gates, Kenya Power and regulator liaison, cybersecurity audit sign-off |
| Programme Manager and PMO | Schedule, budget, change log, risk register, dashboard, delivery tracking |
| Technical Lead | Owns this plan, method statements, configuration baseline, commissioning sign-off. Chairs readiness reviews |
| Software engineer | Edge image, OpenEMS configuration, drivers, version pinning, test scripts, backups |
| Site Lead (per pilot) | Accountable for site safety, schedule, access, permits, daily records and the commissioning certificate (with the host representative) |
| Licensed electrical contractor | Installation to approved design, electrical safety certificate, isolation and lock-out compliance |
| Site engineer | Inspection, test execution, as-built records, L4 verification |
| Cybersecurity and Data Protection Officer | Hardening, network design check, security commissioning checklist, audit liaison, data notices |
| Research Lead and Panel | Approve meter locations, accuracy checks and baseline start before data collection |
| Kenya Power grid engineer | Design acceptance, witness of energisation and commissioning, protection and metering checks |
| Host representative | Access, local rules, co-signs certificate, nominates operator trainees |
| Community liaison officer (B, C if needed) | Notice of works, community briefings, complaints during build |
| Installers and vendors | Supply, install, support tests, follow safety plan, hand over all credentials and configuration |

## 6. Entry conditions and readiness gates

Installation does not start on a site until the Gate 2 evidence below is complete. Gate 2 is held at Month 8 (Charter Section 16).

### 6.1 Pre-mobilisation readiness checklist (per site)

| # | Condition | Evidence | Owner | Status |
| --- | --- | --- | --- | --- |
| 1 | Gate 2 approved and installation funds released | SteerCo minute | Programme Director | [ ] |
| 2 | Host Site Agreement signed with conditions precedent met (owner consent, interconnection approval, licences and permits, approved safety plan) | Signed agreement, letters | Site Lead | [ ] |
| 3 | Kenya Power design acceptance (protection, metering, anti-islanding) | Acceptance letter | Technical Lead | [ ] |
| 4 | EPRA position on BESS, mini-grid or charging licensing, and net-metering terms for Pilot A | Written position | Programme Director | [ ] |
| 5 | County, building, fire and NEMA positions | Permits or exemptions | Site Lead | [ ] |
| 6 | Insurer acceptance of battery installation and insurance certificates exchanged | Insurer letter | Site Lead | [ ] |
| 7 | All devices at `PASS` or `COND` with L3 in the lab, conditions closed or costed | B6 register extract | Technical Lead | [ ] |
| 8 | Written vendor permission for third-party control under warranty | B6 Section 9 | Procurement lead | [ ] |
| 9 | Production OpenEMS release, Edge image, firmware set and SBOM frozen | C4 baseline | Software engineer | [ ] |
| 10 | Site method statement, safety plan, battery fire risk assessment and emergency response plan approved and agreed with local responders | Signed plans | Site Lead, Technical Lead | [ ] |
| 11 | Installers and contractors licensed, inducted and named | Licence copies, induction record | Site Lead | [ ] |
| 12 | Equipment delivered, inspected and stored securely, or delivery date confirmed | Delivery record | Procurement lead | [ ] |
| 13 | Meter locations and accuracy check method approved | Panel minute | Research Lead | [ ] |
| 14 | Safe states, plausibility limits and override rules set per site (Site Agreement Schedule 3) | Schedule 3 | Technical Lead | [ ] |
| 15 | Notice given to staff, neighbours or community (Pilot A, B, C as relevant) | Notice record | Site Lead, liaison | [ ] |
| 16 | Operator trainees nominated and release agreed | Host letter | Site Lead | [ ] |
| 17 | Data protection roles agreed, privacy notice ready (Pilot C), community notice and consent approach (Pilot B) | D2 plan, notices | Cybersecurity Officer | [ ] |
| 18 | Contracting entity named and equipment title decided | Gate 0 record | Programme Sponsor | [ ] |

**Rule.** Any red item blocks mobilisation of that site. The Programme Director may release a site with a documented, time-limited exception only for items that do not affect safety, security or the baseline.

### 6.2 Go-live gate (Gate 3) evidence in this plan

Gate 3 requires commissioning certificates, a passed independent cybersecurity audit, baselines recorded and operators trained (Charter Section 16). Section 12 maps each to the work in this plan.

## 7. Phased approach

| Phase | Name | Output | Hold point at end |
| --- | --- | --- | --- |
| 0 | Mobilisation and site readiness | Readiness checklist closed | **H0** Site release |
| 1 | Receipt, inspection and factory or lab acceptance | Inspected, serialised, configured equipment | **H1** Equipment release |
| 2 | Site preparation and civil works | Prepared site, cable routes, foundations, enclosures | **H2** Ready to install |
| 3 | Mechanical and electrical installation | Installed, labelled, un-energised system | **H3** Ready for pre-energisation checks |
| 4 | Edge, network and measurement installation | Local data collection chain verified, remote access disabled | **H4** Measurement chain verified |
| 5 | Pre-energisation inspection and testing | Electrical safety certificate, protection checks | **H5** Permission to energise |
| 6 | Energisation and hardware proof | Hardware protections proven with OpenEMS not in command | **H6** Permission to enable OpenEMS |
| 7 | OpenEMS commissioning and site acceptance tests | L4 results, safe states, offline and fault tests | **H7** Acceptance |
| 8 | Baseline recording, training and audit window | Baseline data, trained operators, audit report | **H8** Commissioning certificate |
| 9 | Gate 3 and handover | Go-live authorisation, handover pack | Gate 3 |

Phases may overlap across sites but never skip a hold point on the same site.

## 8. Common method (all sites)

### 8.1 Phase 0: Mobilisation

1. Confirm the readiness checklist (Section 6.1) and hold a pre-start meeting with the host, contractor, Kenya Power and, at Pilot B, the community liaison officer.
2. Walk the site with the contractor to confirm routes, laydown area, isolation points, hazards and emergency access.
3. Agree working hours, noise and dust limits, traffic control, and the notice to staff, neighbours or community. Pay attention to children, livestock and traffic near the site (Stakeholder Engagement Plan 7.3).
4. Open the site log, the daily safety briefing record, the complaints channel and the change log for the site.
5. Record an initial photo log, including nameplates of existing equipment.

### 8.2 Phase 1: Receipt, inspection and acceptance

| Step | Action | Record |
| --- | --- | --- |
| 1 | Check delivery against the purchase order and the Site Agreement Schedule 2 equipment list | Delivery note, packing list |
| 2 | Inspect for transit damage. Batteries are inspected for swelling, leaks, damaged terminals and state of charge on arrival | Inspection sheet, photos |
| 3 | Record make, model, serial and firmware for every device and compare with the B6 tested combination. A mismatch triggers a delta test (B6 10.3) before installation | C4 register update |
| 4 | Secure storage with controlled access, ventilation and fire precautions for batteries. Storage limits follow the safety plan | Store log |
| 5 | Factory or lab acceptance of the Edge computer: image installed from the signed build, hash verified, burn-in complete | Acceptance record |
| 6 | Pre-load device configurations in the lab where possible to reduce site time | Config files in C4 |
| 7 | Confirm meter calibration certificates and seals | Certificates |

**H1 criteria.** Equipment matches the tested set, is undamaged, is serialised and recorded, and is secured.

### 8.3 Phase 2: Site preparation and civil works

- Foundations, plinths, battery room or container base, cable trenches and ducts, roof or ground mounting works, as designed. Floor loading, drainage, flood risk and ventilation are checked against the survey.
- Fire detection and suppression, signage, fencing and access control for the battery area are installed or confirmed before batteries are placed.
- Earthing and lightning protection are installed to the approved design and tested (resistance values recorded).
- Enclosures for Edge, network and meters are fitted, lockable and ingress-rated.
- Environmental controls: waste segregation, spill and dust controls, protection of existing vegetation and water. Waste is removed by approved handlers.

**H2 criteria.** Civil works inspected by the Technical Lead or delegate, drainage and loading verified, earthing tested, fire and security provisions in place.

### 8.4 Phase 3: Mechanical and electrical installation

1. Install equipment to the approved design, manufacturer instructions and Kenyan electrical standards, by licensed contractors only.
2. Install cabling with segregation of power and data, correct cable sizing and protection, labelled both ends, and strain relief.
3. Fit isolation points, lock-out and tag-out points, emergency stops and signage as designed.
4. Keep the system **un-energised and isolated** from the grid and loads until H5.
5. Maintain as-built drawings, marked up daily, and a punch list (Appendix C).

**H3 criteria.** Installation complete to design, labelled, as-built drawings up to date, punch list holds no safety-critical items.

### 8.5 Phase 4: Edge, network and measurement installation

| Step | Action | Source |
| --- | --- | --- |
| 1 | Mount the Edge in a locked enclosure with surge protection and backup power (UPS or supercapacitor) | B4 3.3 |
| 2 | Install the programme network on a dedicated network or VLAN behind a firewall. No route from host IT into the control network | B4 3.5, B7 6.2 |
| 3 | Connect field devices over their tested protocols only. Disable unused ports and services | B7 6.4 |
| 4 | Remove or neutralise default credentials. Create named accounts. Hand over credentials in the sealed handover record | B7 6.1 |
| 5 | Install research-grade meters and the independent logger at the points approved by the Research Panel (B4 3.4) | B4 3.4 |
| 6 | Synchronise time on all loggers to the agreed source and alarm on drift | B4 3.4 |
| 7 | Confirm **no remote access, tunnels, cloud sync or vendor remote tools are active**. Evidence: firewall and Edge settings, port scan | B7 App. B item 5 |
| 8 | Start local data collection and confirm the local buffer of at least [30] days | B4 3.4 |

**H4 criteria.** Measurement chain verified against reference readings, time sync confirmed, network scan clean, remote access confirmed disabled, security checklist items 1 to 6 and 10 to 12 passed (B7 Appendix B).

### 8.6 Phase 5: Pre-energisation inspection and testing

| # | Check | Pass criterion |
| --- | --- | --- |
| 1 | Visual inspection against design and as-builts | No deviations, or approved deviations logged |
| 2 | Insulation resistance, continuity, polarity, earth loop impedance | Within standard limits, values recorded |
| 3 | Protection settings and breaker ratings vs design and Kenya Power requirements | Match approved settings |
| 4 | Battery pre-checks: terminal torque, ventilation, BMS communication, no active alarms | Vendor checklist signed |
| 5 | Fire detection and alarm test | Detectors and alarms operate. Responders informed |
| 6 | Emergency stop and isolation test | Equipment isolates safely |
| 7 | Lock-out procedure walk-through with host and operators | Signed |
| 8 | Kenya Power pre-energisation inspection where required | Approval for energisation |
| 9 | Signed electrical safety certificate from the licensed contractor | Certificate on file (tests A1, B1, C1) |

**H5 criteria.** All checks passed, certificate signed, Kenya Power approval received, Site Lead authorises energisation in writing.

### 8.7 Phase 6: Energisation and hardware proof

1. Energise in stages as designed, with Kenya Power and the host informed, and a named person on site with authority to isolate.
2. **OpenEMS is not in command.** Devices run on their own hardware controls. Confirm that BMS limits, inverter anti-islanding, charger limits and breakers act without OpenEMS (B4 design rule 4).
3. Verify communication to every device from the Edge in **read-only mode first**, then verify writes point by point against the register map (tests A2, B2, C2).
4. Verify out-of-range commands are rejected or clamped by the device or Edge (B6 T-COM-07).
5. Run the first charge and discharge cycles at low power and observe temperatures, voltages and alarms.

**H6 criteria.** Hardware protections proven independent of OpenEMS, all read and write points verified, no unresolved alarms, first-cycle behaviour within limits.

### 8.8 Phase 7: OpenEMS commissioning and site acceptance

1. Load the frozen configuration from C4. Record the configuration hash.
2. Set safe states, plausibility limits, SoC window, ramp rates and overrides per Site Agreement Schedule 3.
3. Enable controllers one at a time, in the order given for each pilot in Sections 9 to 11, with a scripted test for each.
4. Run the site acceptance tests in B4 Sections 5.5, 6.7 and 7.6, witnessed by the Site Lead, the host representative and, where agreed, Kenya Power and EPRA. Results are recorded as L4 in the B6 register and stored in the C5 report.
5. Run the common fault tests on every site: device loss, Edge restart, internet loss, power loss and recovery, override and log (B6 T-COM-03 to T-COM-07).
6. Back up the configuration and **test a restore** (B7 6.7).

**Test mode rule.** Control modes are switched only on the schedule in the approved M&V protocol. During acceptance testing the system is marked as "commissioning" in the data record so that test periods are excluded from the baseline and operating datasets.

**H7 criteria.** All acceptance tests passed or passed with approved conditions, results witnessed and signed, safe states and offline operation proven, backup restore tested.

### 8.9 Phase 8: Baseline, training and audit window

**Baseline.** The Research Panel approves the baseline start. The system then runs with storage idle or unmanaged for the agreed baseline period [length to be set in the M&V protocol, not shorter than the Panel requires]. At least [7] days of complete data at full resolution must exist before the baseline starts (tests A10, B10). Confounding changes during the baseline (new loads, tariff changes, outages, maintenance) are logged.

**Training.** Operators and site staff complete training with assessed competence (D4). Training includes security procedures, the override and logging rule, the safe-state behaviour, reset and fault procedures, and the incident contact process (B7 Section 11). Trainees take part in at least one commissioning test.

**Audit window.** The independent security audit runs on the commissioned system while remote access is still disabled (B7 Section 9). Critical findings block go-live. Findings are fixed and retested before Gate 3.

**H8 criteria.** Baseline started and verified as complete, operators assessed competent, audit report received with no open critical findings, handover pack complete.

### 8.10 Phase 9: Gate 3 and handover

1. Compile the handover pack (Section 13) and the Gate 3 evidence pack.
2. Programme Director recommends Gate 3. The Steering Committee authorises operation and remote connection.
3. After Gate 3 only: enable the approved outbound-only, encrypted, multi-factor remote access path, then repeat T-NET-02 and a remote-session logging check (B6, B7 6.2). The baseline and control schedule are not altered by this step.
4. Hold a launch event with the host, community and stakeholders where agreed (Stakeholder Engagement Plan Section 8).

## 9. Pilot A: Industrial park, hub or campus

| Item | Plan |
| --- | --- |
| Configuration | Existing or new PV with about 250 kWh battery, battery or hybrid inverter, grid meter, research meter, Edge (size confirmed by the B4 Section 4 method) |
| Key sequence | Switchboard work and battery room first, then battery and inverter, then Edge and meters, then integration with existing PV inverters |
| Outage planning | Planned shutdowns agreed with the host in writing, kept as short as possible, with notice to staff and neighbouring businesses. No production-critical load is interrupted without host approval |
| Existing PV inverters | Integration only with written warranty permission. Confirm interface before the shutdown window. If an inverter cannot be opened to control, stop and apply the C1 remedy or red-item process |
| Net-metering | Confirm EPRA and Kenya Power approval is in hand before export-capable operation. Set the OpenEMS export limit to the approved figure (test A5) |
| Controller enablement order | 1) monitoring only; 2) self-consumption and feed-in limit; 3) ToU shifting; 4) peak shaving. Each enabled only after its test passes |
| Critical loads | Protected-loads list loaded. Host override tested and logged (test A8) |
| Data sensitivity | Production schedules and tariff terms stay confidential. Installers do not copy host data |
| Baseline | Storage idle or unmanaged. Host keeps bill savings per Site Agreement 8.2 unless otherwise agreed, and the baseline notes any benefit-sharing choice |
| Acceptance tests | A1 to A10 (B4 Section 5.5) |
| Special risks | Fire safety and insurer notification for the battery room, interaction with existing inverter warranties, host IT adjacency |

## 10. Pilot B: Rural microgrid

| Item | Plan |
| --- | --- |
| Configuration | 50 to 100 kW PV, about 200 kWh battery, grid-forming battery inverter if topology requires, Edge, dual-SIM router, feeder and check meters, generator interface if diesel present |
| Topology | Install only to the topology decided before the battery inverter was shortlisted (grid-connected, mini-grid with grid, or isolated). A change of topology is a change request, not a site decision |
| Community | No works begin without the documented informed community agreement. Notice of construction, expected disruption and safety precautions is given before works, in English and Kiswahili (Stakeholder Plan 7.3). Complaints channel active from day one |
| Supply continuity | The pilot must not cause disconnection or price rise to customers served (Site Agreement Pilot B). Any planned supply interruption is agreed with the operator, announced in advance and kept to the minimum. A transfer plan to the existing supply or generator is prepared and rehearsed |
| Logistics | Remote delivery, travel time and spares are planned in the schedule. Allow float for road, weather and rainy-season access [season to be checked] |
| Security | Cabinets and equipment protected against theft and vandalism from the day delivered. Equipment is not left unattended on site before enclosures are locked. Siting reviewed with the community |
| Environment | Lightning, flood, dust, heat and wildlife protections installed and checked in H5. Fencing and signage protect children and livestock |
| Generator | Integration through its own controller or relay, with the generator retaining its own protection. Test start, stop and loss-of-link behaviour |
| Controller enablement order | 1) monitoring and metering; 2) self-consumption and SoC management; 3) generator offset; 4) evening peak dispatch |
| Loss measurement | Check meters and feeder input meter installed and verified before the baseline begins. Metering coverage recorded. The Panel approves the loss-measurement method before data collection (B4 6.4) |
| Offline test | Full control for [72] hours without connectivity, then clean sync (test B5) |
| Operators | Local operator and trained backup complete a reset and fault drill (test B9) |
| Local labour | Prefer qualified local labour and record local hiring (Stakeholder Plan 7.4). Do not promise jobs or assets beyond the host agreement |
| Acceptance tests | B1 to B10 (B4 Section 6.7) |
| Special risks | Remote location and slow service, theft, topology complexity, community expectations, connectivity |

## 11. Pilot C: EV charging site

| Item | Plan |
| --- | --- |
| Configuration | About 10 to 20 fast chargers, transformer and site meters, Edge, network, optional small battery |
| Public safety | The site is a public or fleet site. Works are phased so that the public is separated from construction by barriers and signage. Public liability cover is confirmed before works. Charger outages are announced to users and fleet customers |
| Operator revenue | Planned charger outages are scheduled with the site operator to limit lost revenue. Compensation, if any, follows Site Agreement Schedule 5 |
| Charger preparation | Chargers are installed with their own protection and a configured **fallback limit** before OpenEMS control is enabled. In-session limiting is proven per model and OCPP version (test C2) |
| Transformer data | The Kenya Power data path is read-only. Response time is measured. Loss of the feed triggers the conservative site limit agreed with Kenya Power (tests C6, B7 7.3) |
| Controller enablement order | 1) monitoring only; 2) site-limit enforcement with a high site limit; 3) policy-based balancing (fair-sharing or priority); 4) transformer protection thresholds; 5) battery support if fitted |
| Site limit | Set below the safe transformer limit with Kenya Power approval. Lowered first, raised only on Kenya Power agreement |
| Driver information | Signage or screen message explains throttling and why. The agreed charging policy and maximum wait time are displayed before go-live. Privacy notice displayed (test C10) |
| Security | Customer-accessible ports, screens and payment hardware separated from the control network. Remote access disabled until Gate 3 (test C9) |
| Fleet customers | Briefings on managed charging, expected effect on charging times and the feedback route |
| Acceptance tests | C1 to C10 (B4 Section 7.6) |
| Special risks | Vendor cooperation, vehicle compatibility with limiting, driver complaints, thermal safety, transformer data response time |

## 12. Commissioning and Gate 3 evidence

| Gate 3 requirement | Evidence from this plan | Owner |
| --- | --- | --- |
| Commissioning certificates | Signed per site by the Site Lead and host representative, after H7 and H8 (Appendix B template) | Site Leads |
| Passed cybersecurity audit | Audit report, no open critical findings, high findings fixed or SteerCo-approved with compensating control (B7 9.3) | Cybersecurity Officer |
| Baselines recorded | Baseline data complete and verified, meter accuracy checks complete, Panel confirmation | Research Lead |
| Operators trained | Competence records, attendance, trainees certified against the target set in the Charter risk trigger | Technical Lead |
| Acceptance (L4) | C5 test reports for A1 to A10, B1 to B10 and C1 to C10 | Technical Lead |
| Configuration baseline | C4 repository tag, hashes, SBOM, backup and restore record | Software engineer |
| Security commissioning checklist | B7 Appendix B completed, items signed | Cybersecurity Officer |
| Incident exercise | Tabletop and site drills completed (B7 10.6) | Cybersecurity Officer |
| Regulatory | Licence and permit conditions met, Kenya Power witness records, ODPC and breach process in place (B5 Section 9) | Programme Director |
| Lessons learned | Lessons-learned review held at Gate 3 and shared (Charter Section 23) | Programme Manager |

## 13. Handover pack (per site)

1. As-built drawings, single-line diagram, network diagram (restricted distribution) and equipment list with serial numbers (Site Agreement Schedule 2).
2. Test and commissioning records, electrical safety certificate and signed commissioning certificate.
3. Frozen OpenEMS release, Edge image, device firmware list, configuration files, hashes and SBOM (C4).
4. Safe states, plausibility limits and override rules (Schedule 3), with the override log procedure.
5. Operations and maintenance manual (D3), including routine checks, battery plan, fault handling, escalation and contact list.
6. Safety plan, fire risk assessment, emergency response plan, lock-out procedures and signage list.
7. Security pack: account list, sealed credential record, hardening baseline, backup and restore procedure, incident playbooks (credentials stored separately from the open repository).
8. Warranty documents, vendor local service contacts, spares list and service levels.
9. Training records and competence assessments, and refresher plan.
10. Data pack: meter locations, calibration records, data dictionary, baseline definition and privacy notices.
11. Complaints and feedback channel details.

## 14. Schedule and compression management

Months are relative to programme start and follow the Charter gates. Where documents differ, the Charter prevails and the difference is flagged.

| Activity | Months | Output | Gate link |
| --- | --- | --- | --- |
| Site method statements and safety plans finalised | 6 to 8 | Approved plans | Gate 2 input |
| Pre-mobilisation readiness checks | 7 to 8 | Checklist 6.1 closed | **Gate 2 (Month 8)** |
| Delivery, receipt and lab acceptance | 8 to 11 | H1 per site | |
| Site preparation and civil works | 8 to 10 | H2 per site | |
| Installation (Phases 3 and 4) | 9 to 11 | H3, H4 per site | |
| Pre-energisation, energisation, hardware proof | 10 to 12 | H5, H6 per site | |
| OpenEMS commissioning and site acceptance | 11 to 12 | H7 per site | |
| Baseline start, training, audit | 11 to 12 | H8 per site | |
| **Go-live authorisation** | **12** | **Certificates, audit, baselines, trained operators** | **Gate 3 (Month 12)** |
| Remote access enabled, then operation | 12 to 13 | Operation begins | |
| Lessons-learned review | 12 | Review record | Gate 3 |

**Flagged inconsistencies to resolve.** (1) The Charter shows installation in Months 7 to 12 (deliverable D5), while the Procurement Plan shows installation and commissioning in Months 9 to 12 after award at Month 8. This plan uses Months 8 to 12 and treats Month 7 as preparation only. (2) The baseline period length has to fit before Gate 3 and still leave 12 months of validated operating data in Months 13 to 24. The Research Panel must fix the baseline length in the M&V protocol before Gate 2.

**Compression warning.** From award at Month 8 to Gate 3 at Month 12 there are four months for delivery, installation, commissioning, the baseline, training and the audit. The audit cannot start until the system is commissioned, and critical findings need time to fix and retest. Pilot B is the most likely to slip because of remote logistics.

**Stop-or-extend rule (proposed).** If any site is forecast to miss H7 by more than [4] weeks against plan, the Programme Director raises it at the next PMO review and recommends to the SteerCo one of: extend the Gate 3 date for that site, drop the site to a reserve site, or reduce scope. Any gate date movement needs SteerCo approval (Charter Section 20). The decision considers the loss of validated data months, and the agreed rule is recorded before Gate 2.

**Early-order link.** If bidders' lead times put H1 at risk, the early-order option in C1 Section 4.4 is considered at Gate 1 or Gate 2.

## 15. Safety, health and environment

| Topic | Requirement |
| --- | --- |
| Competence | Licensed electrical contractors and, where required, EPRA-recognised solar contractors [confirm lists with EPRA]. Named supervisors on site every working day |
| Safety plan | Approved before work. Covers working at height, electrical isolation, lock-out and tag-out, manual handling, hot work, excavation, traffic and public interface |
| Battery safety | Fire risk assessment, detection and suppression type set by the assessment [specialist input needed], battery handled and stored as the vendor and insurer require, thermal monitoring during first cycles, emergency response plan agreed with local responders |
| Permit to work | Permits for isolation, hot work and working at height, issued by the Site Lead and closed out daily |
| Daily routine | Toolbox briefing, signed attendance, hazard review, site log |
| Incidents | Reported to the Site Lead within [24] hours (Site Agreement 5.3). Serious incidents are reported to the SteerCo and, as the law requires, to the authorities. Work stops until the cause is understood |
| Emergency | Contact list, first aid, nearest fire station and clinic recorded and displayed. Drills before energisation |
| Environment | Waste segregation, battery transport and storage under applicable hazardous-material rules [confirm], spill control, no burning of waste, protection of drainage. End-of-life and decommissioning route fixed before procurement (Schedule 4) |
| Community | Notice, fencing, signage, protection of children and livestock, noise and dust control, complaints channel |
| Insurance | Equipment all-risks, public liability and transit cover with certificates before delivery (Site Agreement 13) |

## 16. Quality assurance and change control

- Every deliverable and test record is reviewed by someone independent of its author (Charter Section 23).
- Deviations from design are raised as change requests and logged. Safety, security or baseline-affecting changes need Technical Lead approval and, where they alter the specification, TWG review. Schedule, budget and scope tolerances follow Charter Section 20.
- Firmware or software changes during commissioning follow the B6 delta testing rules and the logged change process.
- Non-conformances are recorded with owner, action and due date, and closed before the relevant hold point.
- As-built records are the basis for the configuration baseline and the operations manual.

## 17. Communication and engagement during build

| Audience | Activity | Owner | Timing |
| --- | --- | --- | --- |
| Host staff and neighbours (A) | Notice of works, outage notices, safety briefing | Site Lead A | Before H0, before each outage |
| Community and operator (B) | Construction notice, plain-language updates, complaints channel, training sessions, in English and Kiswahili | Site Lead B, liaison | Before H0, quarterly at minimum |
| Drivers, fleets and operator (C) | Notice of charger outages, managed-charging briefings, signage, privacy notice | Site Lead C | Before H0, before go-live |
| Kenya Power and EPRA | Invitations to witness energisation and commissioning, incident notifications | Programme Director, Technical Lead | H5, H7, Gate 3 |
| Funders and SteerCo | Monthly dashboard, early notice of delay, Gate 3 evidence pack | Programme Director | Monthly, Gate 3 |
| Public and media | Launch events, short factual updates, no performance claims before data exists | Programme Manager | Gate 3 and after |

All public statements stress that this is a research pilot and results are measured, not guaranteed (Stakeholder Engagement Plan 7.2).

## 18. Risks

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| IC1 | Late delivery or long lead times push commissioning past Month 12 | M | H | Early-order option, delivery milestones, liquidated damages, weekly delivery tracking | Programme Manager |
| IC2 | Installer error or unlicensed work causes a safety incident | L | H | Licence checks, method statements, hold points, supervision, permit to work | Site Leads |
| IC3 | Battery fire or thermal event during commissioning | L | H | Fire risk assessment, detection, staged energisation, first-cycle monitoring, emergency plan | Site Leads |
| IC4 | Existing equipment at Pilot A cannot be integrated at site despite lab results | M | M | Early site check of interface, red-item process, remedy package P8 | Technical Lead |
| IC5 | Site behaviour differs from lab (L3 vs L4), for example network or wiring effects | M | M | Test early, spare time for fixes, delta testing rules | Software engineer |
| IC6 | Audit finds critical issues late and delays Gate 3 | M | H | Gate 2 design review, pre-audit scan at commissioning, time reserved between commissioning and audit | Cybersecurity Officer |
| IC7 | Pilot B logistics, weather, theft or community issues delay or damage the build | H | M | Float in schedule, secure storage, early liaison, local labour, spares kit | Site Lead B |
| IC8 | Kenya Power witness or approval delays energisation | M | H | Book witness dates early, named grid engineer, buffer in schedule | Technical Lead |
| IC9 | Baseline is compromised by commissioning tests or confounding changes | M | H | Commissioning flag in data, Panel approval of baseline start, change log | Research Lead |
| IC10 | Supply interruption to customers (B), production loss (A) or revenue loss (C) causes disputes | M | M | Agreed outage windows, transfer plans, compensation terms in Schedule 5, notice | Site Leads |
| IC11 | Vendor leaves an undocumented remote path or weak credentials | M | H | Commissioning checklist, port scans, credential handover, audit check | Cybersecurity Officer |
| IC12 | Insufficient trained local staff at Gate 3 | M | M | Trainees take part in commissioning, assessed competence, backup operator | Technical Lead |
| IC13 | Permits (county, NEMA, fire) not secured by Gate 2 | M | M | Screen at site selection, track in readiness checklist | Site Leads |
| IC14 | Equipment theft or damage in store or on site before locked enclosures are fitted | M | M | Secure store, delivery just in time, guarding, insurance | Site Leads |

These risks are to be merged into the live Risk Register (README A6). A failed compatibility test on a device at site is a Charter escalation trigger.

## 19. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Set the baseline period length in the M&V protocol so it fits before Gate 3 | Gate 2 | Research Lead |
| 2 | Resolve the Charter and Procurement Plan differences on installation start (Month 7 or Month 9) | Schedule | Programme Manager |
| 3 | Agree the stop-or-extend rule and tolerance | Gate 2 | Programme Director, SteerCo |
| 4 | Fix the safe states, plausibility limits and site limits per site | Gate 2 | Technical Lead |
| 5 | Decide whether safe-state changes after Gate 3 need two-person on-site approval | Gate 2 | TWG |
| 6 | Confirm Kenya Power witness arrangements, lead times and inspection requirements | H5, H7 | Technical Lead |
| 7 | Name the battery safety standard and fire design accepted by Kenya Power and the insurer | H5 | Site Leads |
| 8 | Agree outage windows and compensation terms with hosts (Schedule 5) | H0 | Site Leads |
| 9 | Decide the number of operator trainees per site and the competence assessment | Gate 3 | Technical Lead |
| 10 | Confirm access, road and season constraints for Pilot B | Schedule | Site Lead B |
| 11 | Agree whether launch events are held at Gate 3 or after the first data summary | Engagement | Programme Manager |
| 12 | Decide who holds sealed credentials and the break-glass procedure | H4 | Cybersecurity Officer |

## 20. Immediate next steps

1. Technical Lead to circulate this plan for TWG review, including the Kenya Power grid engineer.
2. Draft site method statements and safety plans for each candidate site, to be finalised after Gate 1 site selection.
3. Agree with the Research Panel the baseline start rule and length.
4. Confirm Kenya Power inspection and witness requirements and book provisional dates.
5. Add the commissioning hold points, evidence list and risks IC1 to IC14 to the PMO dashboard and Risk Register.
6. Draft the handover pack structure and the commissioning certificate template with counsel and the host agreements in mind.
7. Plan trainee participation in commissioning with the capacity-building lead.
8. Confirm early-order and lead-time position with the procurement lead before Gate 1.

---

# Appendix A: Hold point register (template)

| Hold point | Site | Criteria met (Y/N) | Evidence reference | Approver | Name and signature | Date |
| --- | --- | --- | --- | --- | --- | --- |
| H0 Site release | [A / B / C] | [ ] | Checklist 6.1 | Programme Director | [ ] | [ ] |
| H1 Equipment release | [ ] | [ ] | Inspection records, B6 match | Technical Lead | [ ] | [ ] |
| H2 Ready to install | [ ] | [ ] | Civil works inspection | Technical Lead or delegate | [ ] | [ ] |
| H3 Ready for pre-energisation checks | [ ] | [ ] | As-builts, punch list | Technical Lead, licensed engineer | [ ] | [ ] |
| H4 Measurement chain verified | [ ] | [ ] | Meter checks, scan, B7 App. B | Research Lead, Cybersecurity Officer | [ ] | [ ] |
| H5 Permission to energise | [ ] | [ ] | Safety certificate, Kenya Power approval | Site Lead, Kenya Power | [ ] | [ ] |
| H6 Permission to enable OpenEMS | [ ] | [ ] | Hardware proof records | Technical Lead | [ ] | [ ] |
| H7 Acceptance | [ ] | [ ] | C5 test report | Technical Lead, host representative | [ ] | [ ] |
| H8 Commissioning certificate | [ ] | [ ] | Baseline, training, audit | Programme Director | [ ] | [ ] |

# Appendix B: Commissioning certificate (template)

| Field | Entry |
| --- | --- |
| Site, pilot and address | [ ] |
| Equipment list reference (Site Agreement Schedule 2) and serial numbers | [ ] |
| OpenEMS release, Edge image hash and configuration hash | [ ] |
| Device firmware versions (match B6) | [ ] |
| Electrical safety certificate reference | [ ] |
| Kenya Power approval and witness reference | [ ] |
| Acceptance tests passed (A1 to A10 / B1 to B10 / C1 to C10), with deviations | [ ] |
| Offline operation test result | [ ] |
| Safe states and limits configured (Schedule 3 reference) | [ ] |
| Baseline start date and Panel confirmation | [ ] |
| Remote access status | **Disabled** (to be enabled only after Gate 3) |
| Operators trained and assessed (names, number) | [ ] |
| Open conditions, owners and due dates | [ ] |
| Signatures | Site Lead [name, date]; Host representative [name, date]; Technical Lead [name, date]; Kenya Power witness (where agreed) [name, date] |

# Appendix C: Punch list and non-conformance log (template)

| ID | Date | Site | Description | Severity (safety-critical / major / minor) | Owner | Due | Closed (date, by) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

**Rule.** Safety-critical items close before the next hold point. Major items close before H7. Minor items close before H8 or carry an owner and date into operation.

# Appendix D: Daily site record (template)

| Field | Entry |
| --- | --- |
| Date, site, weather and access | [ ] |
| Toolbox briefing held and attendance | [ ] |
| Work done and phase | [ ] |
| Permits issued and closed | [ ] |
| Visitors and contractors on site | [ ] |
| Deliveries and equipment movement | [ ] |
| Incidents and near misses | [ ] |
| Complaints received | [ ] |
| Deviations and decisions | [ ] |
| Photos taken (reference) | [ ] |
| Site Lead signature | [ ] |

# Appendix E: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 6, 7, 10, 16, 17, 19, 20, 21, 23) | Deliverable D5, KPIs and baseline, gates, safety governance, change control, commissioning checklist, publication |
| Feasibility Study (Sections 4, 7.2, 8.1, 9, 12) | Technical risks, safety, schedule pressure, stop-or-extend rule |
| Technical Specification per Site (Sections 3.2 to 3.6, 4, 5 to 9) | Design rules, equipment requirements, safe states, acceptance tests, commissioning steps |
| Interoperability and Device Compatibility Register (Sections 2, 3, 6, 10, 12) | L3 and L4 levels, test IDs, delta testing, version pinning |
| Cybersecurity Plan (Sections 6, 8, 9, 10, Appendix B) | Hardening, remote-access rule, audit window, commissioning security checklist, incident exercises |
| Regulatory Compliance Assessment (Sections 5.5, 5.8, 6, 9) | Kenya Power acceptance, permits, licensed contractors, witness arrangements, Gate readiness |
| Procurement Plan and Tender Documents (Sections 4, 11, 13) | Contracts, acceptance conditions, delay terms, early-order option, schedule |
| MoU and Site Agreement templates (Site Agreement Sections 3 to 6, 13, Schedules 2 to 5, Pilot A, B, C terms) | Conditions precedent, commissioning certificate, safe states, insurance, outage and compensation terms |
| Site Survey Reports (A3, A8, B3, B7) | Existing equipment, fire, environment and site constraints |
| Stakeholder Engagement Plan (Sections 7, 8) | Notice of works, community briefings, local labour, launch events |

On completion of the site surveys, tender award and Gate 2 design review, each bracketed value is updated and the document is re-issued as version 1.0 for Gate 2.

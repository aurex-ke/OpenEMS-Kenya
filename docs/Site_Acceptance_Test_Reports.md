# Site Acceptance Test Reports (Pilots A, B, C)

## 1. Purpose and bottom line

The Charter requires evidence that each site meets its specification before it operates (Section 23), and Gate 3 requires commissioning certificates, a passed cybersecurity audit, recorded baselines and trained operators (Section 16). This document defines the **site acceptance test (SAT) report** for each pilot: what is tested, how, what counts as a pass, who witnesses it, and how the result becomes Gate 3 evidence.

**Bottom line.** The reports are built around six rules:

1. **Site proof follows lab proof.** Devices arrive having passed L3 in the lab (B6). The SAT proves **L4**: the same behaviour with real wiring, network, loads and operators.
2. **Hardware protection is proven first.** Tests in Phase 6 of C3 run with OpenEMS not in command. OpenEMS is enabled only after the hardware protections are shown to work on their own (B4 design rule 4).
3. **Every result is evidence.** Each test has a record ID, data files, a tester, a witness and a time stamp from the synchronised time source. A claim without a data reference is not a pass.
4. **Failures are recorded as prominently as passes.** Failed tests, retests and workarounds stay in the report (Charter Section 21).
5. **Commissioning data is not baseline data.** SAT periods are flagged `M0 Commissioning` so they are excluded from the baseline and operating datasets (C3 8.8, C4 6.6).
6. **No pass, no go-live.** A site with an open critical item or an unwitnessed safety test cannot receive its commissioning certificate (H8) or reach Gate 3.

**Status note.** No site is selected, built or visited, and no test has been run. These are therefore **pre-populated report templates**: the programme's test list, criteria, evidence needs and decision rules are filled in from B4, B6 and C3, and every field in square brackets is completed on site. Complete one report per site, and one report per retest campaign where a site is re-verified after a change.

**Numbering note.** "Test B6" in this document means the Pilot B outage-transfer test from B4 Section 6.7. "Register B6" means the Interoperability and Device Compatibility Register. The two are not related.

## 2. Document control and relationships

**Owner:** Technical Lead (README C5). **Contributors:** site engineers, Site Leads, software engineer, Cybersecurity and Data Protection Officer, Research Lead, Kenya Power grid engineer (TWG), licensed electrical contractor, host representatives. **Approval:** method approved by the Programme Director at Gate 2. Individual reports are signed per site at H7 (acceptance) and filed at H8. Reviewed fortnightly in the TWG during build. Changes to the method follow Charter Section 20 change control.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 16, 19, 20, 21, 23) | Gate 3 evidence, safety governance, change control, commissioning checklist, independent review |
| Technical Specification per Site (B4, Sections 3.2 to 3.6, 5.5, 6.7, 7.6, 9) | Source of acceptance tests A1 to A10, B1 to B10, C1 to C10, safe states and commissioning steps |
| Interoperability and Device Compatibility Register (B6, Sections 3, 6, 10, 12) | Source of L3 and L4 levels and test IDs (T-COM, T-PVI, T-BAT, T-MTR, T-EVC, T-GEN, T-EDG, T-NET). Receives L4 results |
| Cybersecurity Plan (B7, Sections 6, 8, 9, Appendix B) | Commissioning security checklist, no-remote-access rule, audit window, incident exercises |
| Regulatory Compliance Assessment (B5, Sections 5.5, 5.8, 9) | Kenya Power witness and acceptance, permits, licensed contractors |
| Installation and Commissioning Plan (C3, Sections 6 to 13, Appendices A to D) | Hold points H0 to H8, phases, punch list, commissioning certificate, handover pack |
| OpenEMS Configuration Baseline (C4, Sections 6, 9, 12) | Configuration hash, manifest, validation checks V1 to V12, mode records |
| Procurement Plan (C1) | Contract acceptance conditions, delay and retention terms linked to SAT results |
| Site Agreement templates (Sections 5.2, 6, Schedules 2, 3, 6) | Commissioning certificate, safe states, equipment list, data roles |
| Site Survey Reports (B3) | Existing-device data, red items, site constraints |
| Monitoring and evaluation plan (D1), Operations and maintenance manual (D3), Incident and change log (D5) | Baseline rules, operator procedures, change records |

## 3. Principles

| Principle | What it means in practice |
| --- | --- |
| Test what will operate | Tests run on the installed system, with the frozen configuration (`v1.0.0`) and the firmware set in the B6 register. A mismatch stops the test until a delta test is done (B6 10.3) |
| Scripted and repeatable | Each test follows a written script. The test runner records every setpoint sent and value returned |
| Witnessed | Safety, protection, limit and offline tests are witnessed by the Site Lead and host representative. Kenya Power and EPRA are invited to witness grid-related tests (C3 H5, H7) |
| Independent review | The report is reviewed by a person independent of its author before sign-off (Charter Section 23) |
| Stop is allowed | Any person may stop a test for safety. A stop is never penalised (C3 Section 4) |
| Honest limits | Where real hardware is unavailable and a simulator is used, the report says so and the result is rated no higher than L1 (B6 6.1) |
| Open by default | Report summaries and non-sensitive results are published after the security and privacy review. Credentials, network maps and host-confidential data are withheld (C4 Section 14) |

## 4. How the reports work

### 4.1 Where SAT sits in the commissioning sequence

| C3 hold point | Meaning | SAT content | Report section |
| --- | --- | --- | --- |
| H4 Measurement chain verified | Meters, logger, time sync, network and remote-access-disabled status checked | Common tests CT-1 to CT-4, tests A9, A10, B7, B10 (data readiness) | 6, 10 |
| H5 Permission to energise | Pre-energisation inspection passed | Tests A1, B1, C1 (electrical safety) | 7 to 9 |
| H6 Permission to enable OpenEMS | Hardware protections proven with OpenEMS not in command | Tests A2, B2, C2 (communication, read then write), CT-5 | 6, 7 to 9 |
| H7 Acceptance | OpenEMS controls, limits, safe states and fault behaviour proven | All remaining A, B and C tests, common tests CT-6 to CT-10 | 6 to 9 |
| H8 Commissioning certificate | Baseline started, training done, audit report received | Sections 10 to 12 of each report | 10 to 13 |

### 4.2 Result codes

| Code | Meaning | Effect |
| --- | --- | --- |
| P | Pass. Criterion met in every run, evidence attached | Counts toward H7 |
| PC | Pass with conditions. Criterion met, but a condition is open | Allowed only if the condition has an owner, cost and due date, and is not safety-critical or baseline-affecting. Needs Technical Lead approval |
| F | Fail. Criterion not met | Non-conformance raised. Retest after fix. Failure on a selected device is a Charter escalation trigger (B6 Section 11) |
| NR | Not run | Counts as not passed. Reason recorded |
| N/A | Not applicable to this site | Reason recorded and approved by the Technical Lead |

**Rule.** "Unknown" is never a pass. A test that cannot be run defaults to NR until it is.

### 4.3 Severity of non-conformances

Non-conformances use the C3 punch-list severities.

| Severity | Definition | Closure rule |
| --- | --- | --- |
| Safety-critical | Could cause injury, fire, unsafe equipment state or loss of protection | Closed and retested before the next hold point |
| Major | Test criterion failed, or a control, limit or data function not working as specified | Closed before H7 |
| Minor | Labelling, documentation or cosmetic items | Closed before H8, or carried into operation with an owner and date |

### 4.4 Retest and delta rules

| Event | Retest |
| --- | --- |
| Failed test | Retest the failed test after the fix, plus any test that shares the changed component |
| Firmware change | Full T-COM and the control test for the class (B6 10.3) |
| OpenEMS release, image or driver change | As B6 10.3, then re-verify configuration hash (C4 V2 to V5) |
| Any change to the safety set (L5) | Tests of safe state, limit enforcement and override for the affected devices (C4 V6, V7) |
| Network or Edge hardware change | T-COM-02, T-COM-06, T-EDG, T-NET and the offline test |

### 4.5 Evidence package per test

Each test record holds: the record ID, the script version, the configuration tag and hash, the firmware list, tester and witness names, start and end time, the data files (logged setpoints and measured values), photographs where relevant, the result code, any deviation, and the link to a non-conformance entry if raised. Records are stored with the C4 baseline and indexed in this report.

**Record ID format:** `SAT-[site ID]-[test ID]-[run number]`, for example `SAT-SSR-A1-A3-01`.

## 5. Roles and sign-off

| Role | Responsibility in the SAT |
| --- | --- |
| Technical Lead | Owns the method and the report. Approves PC results. Signs H7 |
| Software engineer | Loads the frozen configuration, runs scripted tests, records hashes, performs restore test |
| Site engineer | Executes tests, records measurements, photographs, as-built check |
| Site Lead | Authorises each test day, witnesses safety tests, holds stop authority, co-signs the commissioning certificate |
| Licensed electrical contractor | Performs and certifies electrical safety and protection checks |
| Host representative | Witnesses tests, tests the override right, co-signs the certificate |
| Cybersecurity and Data Protection Officer | Verifies security tests and the checklist in B7 Appendix B |
| Research Lead | Verifies meter accuracy, data completeness and baseline readiness |
| Kenya Power grid engineer | Witnesses grid-related tests (limits, protection, transformer data) where agreed |
| EPRA observer | May witness commissioning. Observer only |
| Independent reviewer | Reviews the completed report before H7 |
| Community liaison officer (B, C if needed) | Confirms notice and operator participation |

## 6. Common survey header and common tests (all sites)

### 6.1 Report header (complete for each site)

| Field | Entry |
| --- | --- |
| Report ID | [e.g. SAT-A1] |
| Pilot and candidate site ID (B3 report ID) | [A / B / C], [SSR-ID] |
| Site name, county, GPS | [ ] |
| Test campaign dates | [ ] |
| Configuration baseline tag and hash | [e.g. SSR-A1-v1.0.0], [SHA-256] |
| OpenEMS release, Edge image hash | [ ] |
| B6 register extract (device IDs, firmware, level before SAT) | [ ] |
| Electrical safety certificate reference | [ ] |
| Kenya Power approval and witness reference | [ ] |
| Weather and access conditions during testing | [ ] |
| Mode flag during testing | `M0 Commissioning` |
| Report author and independent reviewer | [ ] |

### 6.2 Pre-test checks

| # | Check | Result | Evidence |
| --- | --- | --- | --- |
| PT-1 | H5 granted in writing. System energised only as the H5 record allows | [ ] | H5 record |
| PT-2 | Installed devices match the B6 tested combination (make, model, firmware). Mismatch means delta test before SAT | [ ] | C4 firmware list, B6 |
| PT-3 | Loaded configuration hash matches the manifest (C4 V2). Component inventory has no extras (V3) | [ ] | Verify tool output |
| PT-4 | Test scripts, tolerances and safe-state table (Schedule 3) approved and attached | [ ] | Script versions |
| PT-5 | Stop authority, emergency contacts, first aid, fire plan and lock-out procedure briefed to all test participants | [ ] | Briefing record |
| PT-6 | Host, staff, neighbours or community notified of test windows and possible short interruptions (Pilot B: supply continuity plan in place) | [ ] | Notice record |
| PT-7 | Test instruments identified, in calibration and recorded (reference meter, insulation tester, earth tester, thermal camera, clamp meters, network scanner) | [ ] | Instrument list |
| PT-8 | Time source synchronised on Edge, loggers and test instruments | [ ] | Sync log |

### 6.3 Common tests (all sites)

These tests apply at every site and map to Register B6 and Plan C3. Site-specific tests follow in Sections 7 to 9.

| ID | Test | Procedure summary | Pass criterion | Maps to |
| --- | --- | --- | --- | --- |
| CT-1 | Measurement chain check | Compare each logged channel with a reference meter at stable and stepped load. Check sign, units and scaling | Agreement within the class limit agreed with the Research Panel. Import and export signs consistent across meters | B6 T-MTR-01 to 04, C3 H4 |
| CT-2 | Time synchronisation | Compare time stamps across Edge, loggers and meters. Induce a source loss | Drift within [x] seconds. Drift alarm raised on loss | C3 8.5 step 6 |
| CT-3 | Network scan and segmentation | Scan from each zone. Attempt a path from host IT to the control network | Only expected ports and services. No route from host IT. No open inbound ports | B6 T-NET-01, B7 App. B item 4 |
| CT-4 | Remote access disabled | Inspect firewall and Edge settings. Scan for tunnels, cloud sync and vendor remote tools | None active. Status recorded as **Disabled** on the commissioning certificate | B7 App. B item 5 |
| CT-5 | Hardware protection proof (OpenEMS not in command) | With OpenEMS read-only, trigger BMS, inverter, charger and breaker protections by the vendor-approved method. Confirm they act independently | Protections operate without OpenEMS. No unresolved alarms | B4 rule 4, C3 H6 |
| CT-6 | Device power cycle and Edge restart | Power cycle each device. Restart the Edge | Automatic reconnection within [x] minutes. Safe state held meanwhile. No manual action | B6 T-COM-03, T-COM-04 |
| CT-7 | Out-of-range command | Send setpoints beyond device and plausibility limits | Rejected or clamped by device or Edge. Never executed unsafely | B6 T-COM-07 |
| CT-8 | Credentials and access | Check default credentials, unused services, named accounts and roles, host access limited to the UI | Defaults removed or neutralised. No unauthenticated write path. Host has no administrator rights | B6 T-COM-08, B7 6.1 |
| CT-9 | Configuration integrity and drift alarm | Alter a non-safety parameter on a test copy. Alter a safety-set value on a spare Edge | Hash mismatch alarm raised. Safety-set mismatch raises the higher-severity alarm | C4 Section 9, B7 6.3 |
| CT-10 | Backup and restore | Take a backup. Restore to a spare Edge or rebuild from the signed image plus tagged configuration | Restored configuration matches the manifest and works. Rebuild time recorded against target [x] hours | B7 6.7, C4 V10 |

**Report rule.** CT-1 to CT-4 are completed before H4. CT-5 is completed before H6. CT-6 to CT-10 are completed before H7.

## 7. Report A: Industrial park, hub or campus

**Purpose.** Confirm that about 250 kWh of battery storage, with existing or new PV, behaves safely and as specified for peak shaving, ToU shifting and net-metering optimisation, and that the data chain can support a defensible baseline. Size and parameters are as confirmed by the B4 Section 4 method for this site, not assumed.

### 7.1 Controller enablement order for testing

1) monitoring only; 2) self-consumption and feed-in limit; 3) ToU shifting; 4) peak shaving. Each controller is enabled only after its scripted test passes (C3 Section 9).

### 7.2 Acceptance tests A1 to A10

| ID | Test | Procedure summary | Pass criterion (from B4 5.5) | Linked tests and evidence | Result | Record ID |
| --- | --- | --- | --- | --- | --- | --- |
| A1 | Insulation, earthing, protection and safety checks | Insulation resistance, continuity, polarity, earth loop impedance, breaker and protection settings, fire detection, emergency stop and isolation, lock-out walk-through | Signed electrical safety certificate. Values recorded. Settings match approved design and Kenya Power requirements | C3 8.6 checks 1 to 9. Safety certificate | [ ] | [ ] |
| A2 | Communication to every device | Read-only first. Then write each setpoint point by point against the register map: PV inverter, battery inverter and BMS, grid meter, research meter | All read and write points verified against the register map. Units and scaling correct | B6 T-COM-01, T-COM-09. Register map check sheet | [ ] | [ ] |
| A3 | Peak shaving trial | Set peak setpoint [kW]. Apply a controlled load step above the setpoint (host-approved load or load bank). Record import, battery power and SoC | Import held at setpoint within [tolerance] during the step. Recharge behaves per threshold. SoC reserve respected | B6 T-BAT-04. Logged 1-minute data | [ ] | [ ] |
| A4 | ToU schedule trial | Load the tariff schedule. Run through off-peak, shoulder and peak windows (accelerated by time offset on a test copy, then real-time check) | Charge and discharge occur in the configured windows. Minimum reserve SoC respected | B6 T-BAT-05. Schedule file hash | [ ] | [ ] |
| A5 | Export limit | Set export limit to the approved figure [kW]. Create surplus PV with low load (or reduce load) and a load step | Export does not exceed the approved limit at any logged interval. Self-consumption controller charges the battery from surplus | B6 T-PVI-02, T-BAT-06. Approval letter reference | [ ] | [ ] |
| A6 | Internet loss | Cut upstream internet for [24] hours | Control continues with no loss of function. Data buffered, then synced on return with no gaps | B6 T-COM-06. Buffer record | [ ] | [ ] |
| A7 | Device loss | Disconnect each device in turn (PV inverter, battery system, meters) | Edge flags the device as lost and applies the defined safe state (battery idle or minimum export). Recovery is clean | B6 T-COM-05, T-BAT-09. Schedule 3 reference | [ ] | [ ] |
| A8 | Override | Host representative exercises the override right on the protected-loads list and the emergency override | Override works. Each override logged with time, person and reason. Normal control resumes as designed | Override log extract | [ ] | [ ] |
| A9 | Meter accuracy check | Compare grid, PV and battery meters with the reference meter at [3] load points | Within the class limits agreed with the Research Panel. Calibration certificates and seals verified | B6 T-MTR-01, T-MTR-04. Calibration records | [ ] | [ ] |
| A10 | Data logging | Run data collection at full resolution for [7] days before the baseline period | Complete data at specified resolution. No unexplained gaps. Local buffer of at least [30] days confirmed | Data completeness report | [ ] | [ ] |

### 7.3 Pilot A additional checks

| # | Check | Result | Evidence |
| --- | --- | --- | --- |
| AX-1 | Existing PV inverter control works without voiding warranty. Written vendor permission on file | [ ] | B6 Section 9 reference |
| AX-2 | Net-metering approval in hand before export-capable operation. Export limit equals the approved figure | [ ] | EPRA and Kenya Power letters |
| AX-3 | Critical loads list loaded. No production-critical load interrupted by any test without host approval | [ ] | Protected-loads list, host note |
| AX-4 | Host IT separation verified. No programme device in the host domain | [ ] | Scan report, network diagram (restricted) |
| AX-5 | Battery room: ventilation, detection, suppression, access control and insurer acceptance verified | [ ] | Fire plan, insurer letter |
| AX-6 | Host confidentiality: no host data copied by installers. Data roles as in Schedule 6 | [ ] | Handover sign-off |
| AX-7 | Conflict test: pairs of controllers acting on the battery resolve as documented, limit controllers take precedence | [ ] | Conflict test record (C4 V8) |

### 7.4 Pilot A report summary

| Item | Entry |
| --- | --- |
| Tests passed (P), passed with conditions (PC), failed (F), not run (NR), N/A | [ ] / [ ] / [ ] / [ ] / [ ] |
| Open non-conformances by severity | [ ] |
| Deviations from the script or specification | [ ] |
| Battery size and power confirmed against measured load (B4 Open item 1) | [ ] |
| Recommendation to the Technical Lead | [Accept / Accept with conditions / Retest / Reject] |

## 8. Report B: Rural microgrid

**Purpose.** Confirm that 50 to 100 kW PV with about 200 kWh battery runs safely and autonomously on the site topology chosen before shortlisting (grid-connected on a long feeder, mini-grid with grid, or isolated), that supply continuity to customers is protected, and that the loss-measurement chain is verified before the baseline begins. This is the hardest site to commission and carries the most community exposure.

### 8.1 Entry conditions specific to Pilot B

| # | Condition | Result | Evidence |
| --- | --- | --- | --- |
| BE-1 | Documented informed community agreement on file. Notice of works and testing given in English and Kiswahili | [ ] | Agreement, notice record |
| BE-2 | Topology matches the decision taken before the battery inverter was shortlisted. A change is a change request, not a site decision | [ ] | C3 Section 10, change log |
| BE-3 | Transfer plan to existing supply or generator prepared and rehearsed. Planned interruptions agreed with the operator and announced | [ ] | Transfer plan, rehearsal record |
| BE-4 | Pilot does not cause disconnection or price rise to customers served (Site Agreement Pilot B). Confirmed with the operator | [ ] | Operator confirmation |
| BE-5 | Equipment secured against theft and vandalism before testing. Enclosures locked | [ ] | Photo log |
| BE-6 | Local operator and trained backup present for testing | [ ] | Attendance |

### 8.2 Controller enablement order for testing

1) monitoring and metering; 2) self-consumption and SoC management; 3) generator offset; 4) evening peak dispatch (C3 Section 10).

### 8.3 Acceptance tests B1 to B10

| ID | Test | Procedure summary | Pass criterion (from B4 6.7) | Linked tests and evidence | Result | Record ID |
| --- | --- | --- | --- | --- | --- | --- |
| B1 | Electrical safety, earthing, lightning protection | Insulation, continuity, earth resistance, lightning and surge protection, protection settings, fire detection, isolation | Signed certificate. Earth resistance within design limit [x] ohm | C3 8.6. Safety certificate | [ ] | [ ] |
| B2 | Communication to all devices | Read-only first, then write points: PV inverters, battery inverter and BMS, generator interface, feeder and check meters | All points verified against register maps | B6 T-COM-01, T-COM-09 | [ ] | [ ] |
| B3 | Evening peak dispatch | Run the configured evening window with measured or representative load | Battery serves the configured window. Reserve SoC for outages respected. Battery limits not exceeded | B6 T-BAT-01, T-BAT-02. Logged data | [ ] | [ ] |
| B4 | Generator offset | Run scenarios: high SoC with PV (generator stays off), low SoC (generator starts correctly), minimum run time and start and stop thresholds | Generator avoided under test conditions. Correct start behaviour on low SoC. Generator retains its own protection | B6 T-GEN-01 to 04. Fuel and run-hour readings | [ ] | [ ] |
| B5 | Offline operation | Disable all connectivity for [72] hours | Full control with no loss of function. Clean data sync on return. Data-gap threshold met | B6 T-COM-06, T-NET-03. Buffer record | [ ] | [ ] |
| B6 | Outage transfer | Simulate loss of the utility supply or generator as the topology allows, with operator and community notified | Behaviour matches the design for the chosen topology (islanding only if approved, grid-forming transfer under specialist supervision) | B6 T-BAT-08. Specialist witness | [ ] | [ ] |
| B7 | Voltage and metering checks | Verify feeder input meter, generator meter and check meters. Install and verify voltage logging at feeder end and transformer secondary | Meters verified against reference. Voltage logging in place. Metering coverage recorded | B6 T-MTR-01 to 04. Loss-measurement method approved by the Panel | [ ] | [ ] |
| B8 | Security and tamper | Inspect cabinets, seals, keys, ports. Verify credentials and tamper alarm where fitted | Cabinets locked. Default credentials removed. Unused ports disabled | B7 App. B items 2, 11. Photo log | [ ] | [ ] |
| B9 | Operator drill | Local operator and backup perform a reset and fault procedure and contact the incident route | Drill completed unaided within [x] minutes using D3 | Drill record, trainee competence form | [ ] | [ ] |
| B10 | Baseline data | Collect data for [7] days at full resolution before the baseline begins | Complete data. Check meters and feeder input meter verified before the baseline | Data completeness report | [ ] | [ ] |

### 8.4 Pilot B additional checks

| # | Check | Result | Evidence |
| --- | --- | --- | --- |
| BX-1 | Mobile coverage measured at the site. Fallback link (second SIM or satellite) tested for failover and outbound-only behaviour | [ ] | B6 T-NET-03 record |
| BX-2 | Generator interface fails safe on loss of link. Generator keeps its own protection and controls | [ ] | B6 T-GEN, T-COM-05 |
| BX-3 | Spares kit on site or within agreed travel time. Service contact verified | [ ] | Spares list, vendor commitment |
| BX-4 | Fencing and signage in place for children and livestock. Wildlife, flood and lightning protections verified | [ ] | Photo log |
| BX-5 | Complaints channel active, with at least two ways to raise a concern | [ ] | Channel record |
| BX-6 | Local labour recorded. No promises made beyond the host agreement | [ ] | Hiring record |
| BX-7 | Conflict test of controllers acting on the battery and generator | [ ] | C4 V8 record |

### 8.5 Pilot B report summary

| Item | Entry |
| --- | --- |
| Tests passed (P), passed with conditions (PC), failed (F), not run (NR), N/A | [ ] / [ ] / [ ] / [ ] / [ ] |
| Topology tested | [grid-connected / mini-grid / isolated] |
| Supply interruptions during testing (number, duration, customers affected) | [ ] |
| Open non-conformances by severity | [ ] |
| Loss-measurement method confirmed by the Panel | [Yes / No] |
| Recommendation to the Technical Lead | [Accept / Accept with conditions / Retest / Reject] |

## 9. Report C: EV charging site

**Purpose.** Confirm that managed charging holds total site power at the agreed limit, applies the agreed policy, produces the data needed for the KPIs, and fails safe on loss of link. OpenEMS protects the transformer by limiting site load behind the connection point, not by controlling Kenya Power assets.

### 9.1 Entry conditions specific to Pilot C

| # | Condition | Result | Evidence |
| --- | --- | --- | --- |
| CE-1 | Public separated from works by barriers and signage. Public liability cover confirmed | [ ] | Site plan, insurance certificate |
| CE-2 | Planned charger outages agreed with the site operator. Notice given to users and fleet customers | [ ] | Notice record |
| CE-3 | Chargers installed with their own protection and the configured fallback limit before OpenEMS control is enabled | [ ] | Charger configuration record |
| CE-4 | Site limit set with Kenya Power approval. Starting value high, lowered first, raised only with Kenya Power agreement | [ ] | Kenya Power letter, Schedule 3 |
| CE-5 | Charging policy and maximum wait time agreed in Schedule 3. Driver information ready for display | [ ] | Schedule 3, signage proof |

### 9.2 Controller enablement order for testing

1) monitoring only; 2) site-limit enforcement with a high limit; 3) policy-based balancing (fair-sharing or priority); 4) transformer protection thresholds; 5) battery support if fitted (C3 Section 11).

### 9.3 Acceptance tests C1 to C10

| ID | Test | Procedure summary | Pass criterion (from B4 7.6) | Linked tests and evidence | Result | Record ID |
| --- | --- | --- | --- | --- | --- | --- |
| C1 | Electrical safety and protection | Insulation, continuity, earthing, protection settings, emergency stop, thermal checks on chargers, isolation | Signed certificate | C3 8.6. Safety certificate | [ ] | [ ] |
| C2 | Charger communication | Connect every charger. Verify status, session start and stop, and change the power limit mid-session on each model | All chargers visible. Status and power limits verified. Each charger applies a changed limit within [x] seconds and the vehicle current follows | B6 T-EVC-01, T-EVC-02. OCPP version recorded | [ ] | [ ] |
| C3 | Limit enforcement | Create full-demand conditions with [N] vehicles or approved test loads. Record total site power against the site limit | Total site power held at the limit during the full-demand test within [tolerance]. No charger exceeds its rating | B6 T-EVC-03. Logged site meter data | [ ] | [ ] |
| C4 | Policy behaviour | Run the agreed policy (fair-sharing or priority) with mixed sessions, including fleet priority if agreed | Charging shares match the agreed policy within [tolerance] | B6 T-EVC-04, T-EVC-05. Session logs | [ ] | [ ] |
| C5 | Wait-time measurement | Run a scripted queue scenario and inspect session logs | Session logs produce waiting-time statistics, including the share of time chargers operate at full capacity | B6 T-EVC-08. Pseudonymised logs | [ ] | [ ] |
| C6 | Transformer data | Measure the transformer data path from Kenya Power or the programme meter. Measure response time. Remove the feed | Loading measured at the required rate and logged. Loss of the feed triggers the conservative site limit [kW, with Kenya Power] | Kenya Power witness. Logged data | [ ] | [ ] |
| C7 | Charger loss of link | Disconnect the link to each charger during a session | Charger drops to the configured fallback limit. Recovery clean | B6 T-EVC-07, T-COM-05 | [ ] | [ ] |
| C8 | Internet loss | Cut upstream internet for [24] hours | Local control continues. Data buffered and synced on return | B6 T-COM-06 | [ ] | [ ] |
| C9 | Security | Verify remote access disabled, credentials changed, charger management interfaces restricted, customer-facing ports separated from the control network | Remote access disabled until Gate 3. No default credentials. Customer-accessible hardware cannot reach the control network | B7 App. B items 2, 4, 5. B6 T-EVC-09, T-NET-01 | [ ] | [ ] |
| C10 | Privacy | Inspect the privacy notice display. Inspect dataset fields | Notice displayed at the site. No payment data in the Programme dataset. Identifiers pseudonymised at source | Photo of notice, dataset field list | [ ] | [ ] |

### 9.4 Pilot C additional checks

| # | Check | Result | Evidence |
| --- | --- | --- | --- |
| CX-1 | Driver message or signage explains throttling and why. Charging policy and maximum wait time displayed before go-live | [ ] | Photo log |
| CX-2 | Vehicle variety: tested with at least [x] locally common vehicle types. Any that reject limiting behaviour are listed | [ ] | B6 T-EVC-06 record |
| CX-3 | Maximum-wait alarm tested. Alarm raised when wait exceeds the agreed limit | [ ] | Alarm log |
| CX-4 | Fleet customers briefed on managed charging and the feedback route | [ ] | Briefing record |
| CX-5 | Charger vendor named contact and cooperation confirmed during testing | [ ] | B6 Section 9 |
| CX-6 | Optional battery (if fitted): setpoint control, SoC reserve, fire safety and insurer acceptance verified | [ ] | B6 T-BAT, fire plan |
| CX-7 | Complaints channel for drivers active | [ ] | Channel record |

### 9.5 Pilot C report summary

| Item | Entry |
| --- | --- |
| Tests passed (P), passed with conditions (PC), failed (F), not run (NR), N/A | [ ] / [ ] / [ ] / [ ] / [ ] |
| Site limit tested and approved by Kenya Power [kW] | [ ] |
| In-session power limiting proven for each charger model and OCPP version | [Yes / No, list] |
| Simulator use (if any) and its stated limits | [ ] |
| Open non-conformances by severity | [ ] |
| Recommendation to the Technical Lead | [Accept / Accept with conditions / Retest / Reject] |

## 10. Baseline readiness (all sites)

The baseline cannot start until the Research and Evaluation Panel approves it. These checks must be complete before the Panel is asked.

| # | Check | Result | Evidence |
| --- | --- | --- | --- |
| BR-1 | Meter accuracy checks complete and within the agreed class limit | [ ] | Tests A9, B7 or CT-1 |
| BR-2 | At least [7] days of complete data at full resolution before baseline start | [ ] | Tests A10, B10 or data report |
| BR-3 | Mode record M1 (monitoring only) signed, with configuration tag, hash and Panel minute reference | [ ] | C4 L7 mode record |
| BR-4 | Commissioning-period data flagged `M0` and excluded from baseline and operating datasets | [ ] | Data flag report |
| BR-5 | Confounding changes during the baseline (new loads, tariff changes, outages, maintenance) logging process in place | [ ] | Change log |
| BR-6 | Benefit-sharing choice recorded and its effect on the baseline noted (Pilot A) | [ ] | Schedule 5 |
| BR-7 | Baseline length set in the M&V protocol and confirmed to fit before Gate 3 and leave 12 months of operating data | [ ] | M&V protocol (C3 open item 1) |

## 11. Security and configuration verification (all sites)

| # | Check | Result | Evidence |
| --- | --- | --- | --- |
| SV-1 | B7 Appendix B commissioning security checklist items 1 to 15 completed and signed | [ ] | B7 checklist |
| SV-2 | Live configuration hashes match the manifest, including the separate safety-set hash (C4 V2) | [ ] | Verify tool output |
| SV-3 | Running release and drivers match the B6 tested set (V4). Firmware equals `firmware.yaml` (V5) | [ ] | Verify tool output |
| SV-4 | Safe state, limit enforcement and conflict tests passed (V6 to V8) | [ ] | SAT records |
| SV-5 | Offline operation passed for the required duration (V9) | [ ] | A6, B5 or C8 |
| SV-6 | Restore test passed (V10). Secrets scan clean (V11) | [ ] | CT-10 record |
| SV-7 | Vendor and installer access removed. Credentials handed over in the sealed handover record | [ ] | Handover sign-off |
| SV-8 | Independent security audit window scheduled with remote access still disabled. Pre-audit scan clean | [ ] | Audit plan, scan report |
| SV-9 | Incident contacts displayed. Tabletop exercise and site drill completed or scheduled before Gate 3 | [ ] | B7 10.6 record |

## 12. Operator training and handover verification

| # | Check | Result | Evidence |
| --- | --- | --- | --- |
| TR-1 | Operators and site staff trained with assessed competence (number, names, scores) | [ ] | D4 records |
| TR-2 | Trainees took part in at least one commissioning test | [ ] | Test attendance |
| TR-3 | Operators can reset, check, follow the override and logging rule, and follow the incident contact process | [ ] | Drill record |
| TR-4 | Operations and maintenance manual (D3) delivered and understood | [ ] | Handover sign-off |
| TR-5 | Handover pack complete: as-builts, certificates, frozen configuration, safe states, O&M manual, safety plan, security pack, warranty and service details, training records, data pack (C3 Section 13) | [ ] | Handover checklist |
| TR-6 | Number of trained operators meets the Charter risk trigger target for Gate 3 | [ ] | Charter Section 18 trigger |

## 13. Acceptance decision and certificate link

### 13.1 Decision rules

| Outcome | Rule |
| --- | --- |
| Accept (H7) | All tests in the site report are P, or PC with approved conditions that are not safety-critical or baseline-affecting. No open safety-critical or major non-conformance. Independent review complete. Witness signatures present for safety, limit and offline tests |
| Accept with conditions | Allowed only for minor items and PC conditions with owner, cost and due date. Conditions listed on the commissioning certificate (C3 Appendix B) |
| Retest | One or more tests F or NR. Fix, then retest per Section 4.4 |
| Reject | A critical safety or integration problem that cannot be fixed within the schedule. Escalate to the Programme Director. Consider the stop-or-extend rule (C3 Section 14) |

### 13.2 Sign-off (per site)

| Role | Name | Signature | Date |
| --- | --- | --- | --- |
| Report author (site engineer) | [ ] | | |
| Independent reviewer | [ ] | | |
| Licensed electrical contractor | [ ] | | |
| Site Lead | [ ] | | |
| Host representative | [ ] | | |
| Cybersecurity and Data Protection Officer | [ ] | | |
| Research Lead (baseline readiness) | [ ] | | |
| Kenya Power witness (where agreed) | [ ] | | |
| Technical Lead (H7 acceptance) | [ ] | | |

### 13.3 Link to the commissioning certificate

The commissioning certificate (C3 Appendix B) cites this report for: acceptance tests passed (A1 to A10, B1 to B10 or C1 to C10) with deviations, offline operation result, safe states and limits configured, baseline start date and Panel confirmation, and open conditions. Remote access status on the certificate remains **Disabled** until Gate 3.

## 14. Non-conformance and deviation log (template)

| ID | Date | Site | Test ID | Description | Severity | Owner | Action and due | Retest record | Closed (date, by) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [ ] | [ ] | [ ] | [ ] | [ ] | [safety-critical / major / minor] | [ ] | [ ] | [ ] | [ ] |

Failed tests on a selected device are reported to the PMO at the next fortnightly review and to the SteerCo in the quarterly report, as a Charter escalation trigger. Failures and workarounds feed the final evaluation report and the replication guide (E3).

## 15. Gate 3 evidence from this document

| Gate 3 requirement (Charter Section 16) | Evidence from the SAT reports | Owner |
| --- | --- | --- |
| Commissioning certificates | Signed per site after H7 and H8 | Site Leads |
| Acceptance (L4) | Completed A, B and C reports, B6 register updated to L4 | Technical Lead |
| Baselines recorded | Section 10 complete, Panel confirmation | Research Lead |
| Operators trained | Section 12 complete | Technical Lead |
| Passed cybersecurity audit | Section 11 prerequisites met, audit report received (not part of this document) | Cybersecurity Officer |
| Configuration baseline verified | SV-2 to SV-6, C4 verification record | Software engineer |
| Lessons learned | Non-conformance log and retest history shared at the Gate 3 review | Programme Manager |

## 16. Schedule

Months follow the Charter gates and C3 Section 14.

| Activity | Months | Output |
| --- | --- | --- |
| Approve the SAT method and test scripts with the TWG | 6 to 8 | Scripts and tolerances approved at Gate 2 |
| Measurement chain and data readiness tests (CT-1 to CT-4, A9, A10, B7, B10) | 10 to 11 | H4 evidence |
| Electrical safety and hardware proof (A1, B1, C1, CT-5) | 10 to 12 | H5, H6 evidence |
| OpenEMS acceptance tests and fault tests | 11 to 12 | H7 evidence |
| Baseline readiness, training verification, audit window | 11 to 12 | H8 evidence |
| Gate 3 evidence pack | 12 | Completed reports |

**Compression warning.** There are about four months between award at Month 8 and Gate 3 at Month 12. Test time is easily lost to late delivery and to fixes found at site. Pilot B is the most likely to slip. Slippage beyond [4] weeks against plan for H7 goes to the stop-or-extend rule in C3 Section 14.

## 17. Risks

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| SA1 | Site behaviour differs from the lab (L3 versus L4) because of wiring, network or loads | M | M | Test riskiest devices first in the lab, reserve time for fixes, delta test rules | Software engineer |
| SA2 | Tests are run on a configuration that differs from the frozen baseline | M | H | Hash check before every test day. Mismatch stops testing | Software engineer |
| SA3 | A safety test is skipped or unwitnessed under schedule pressure | L | H | Hold points, named witnesses, no certificate without signatures | Site Leads |
| SA4 | Test periods contaminate the baseline or operating dataset | M | H | `M0` flag, Panel approval of baseline start, data flag report | Research Lead |
| SA5 | Existing Pilot A inverter cannot be controlled at site despite lab results | M | M | Early interface check, red-item process, remedy package P8 | Technical Lead |
| SA6 | Supply interruption during testing (Pilot B) or revenue loss (Pilot C) causes disputes | M | M | Agreed windows, transfer plans, compensation terms in Schedule 5, notice | Site Leads |
| SA7 | Kenya Power witness or approval dates delay H7 | M | H | Book dates early, named grid engineer, schedule buffer | Technical Lead |
| SA8 | Pilot C cannot prove in-session limiting for a charger model | M | H | Fail per B6, substitute charger or controller, report in Gate 1 evidence | Technical Lead |
| SA9 | Simulators used where real multi-charger hardware is unavailable are over-claimed | M | M | Record the limit, rate at no higher than L1, TWG decision on acceptable use (B6 open item 8) | TWG |
| SA10 | Operators not trained or competent at the time of acceptance | M | M | Trainees take part in tests, assessed drills, backup operator | Technical Lead |
| SA11 | Audit finds critical issues after acceptance and delays Gate 3 | M | H | Design review at Gate 2, pre-audit scan at commissioning, time reserved | Cybersecurity Officer |

These risks are to be merged into the live Risk Register (README A6).

## 18. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Fix numeric tolerances in the tests (peak holding, power response, limit tolerance, response times, drift) | Gate 2 | TWG |
| 2 | Agree load-step method for A3 and C3 (host load, load bank, test vehicles) and who provides it | Gate 2 | Technical Lead, Site Leads |
| 3 | Agree the acceptable simulator use for multi-charger tests and how it is recorded | Pilot C tests | TWG |
| 4 | Set the Pilot B outage-transfer test method for the chosen topology, with specialist support | Pilot B | Technical Lead |
| 5 | Fix the baseline length so the SAT-to-baseline sequence fits before Gate 3 | Gate 2 | Research Lead |
| 6 | Confirm Kenya Power witness arrangements, lead times and inspection requirements | H5, H7 | Technical Lead |
| 7 | Decide whether L5 changes after Gate 3 need two-person on-site approval and how that is tested | Gate 2 | TWG |
| 8 | Agree meter class and accuracy limits with the Research Panel | CT-1, A9, B7 | Research Lead |
| 9 | Decide the number of trainees per site and the competence assessment form | Gate 3 | Technical Lead |
| 10 | Decide how SAT summaries are published and what is withheld | Gate 3 | Cybersecurity Officer, Research Lead |

## 19. Immediate next steps

1. TWG to review this method, including the Kenya Power grid engineer on grid-related tests.
2. Software engineer to turn each test into a script with logged setpoints, expected values and tolerances, and to test the scripts on the lab Edge.
3. Technical Lead to agree numeric tolerances and load-step methods with the Research Panel and Site Leads.
4. Build the record store and record ID scheme alongside the C4 repository.
5. Book Kenya Power and EPRA witness dates provisionally for H5 and H7.
6. Prepare site-specific copies of Reports A, B and C after Gate 1 site selection.
7. Add risks SA1 to SA11 and the open items to the PMO log and Risk Register.
8. Plan trainee participation in the SAT with the capacity-building lead.

---

# Appendix A: Test record template

| Field | Entry |
| --- | --- |
| Record ID | `SAT-[site ID]-[test ID]-[run]` |
| Test ID and title | [ ] |
| Site, pilot and report ID | [ ] |
| Script version and tolerance table version | [ ] |
| Configuration tag and hash, OpenEMS release, Edge image hash | [ ] |
| Device firmware versions (match B6) | [ ] |
| Start and end time (synchronised source) | [ ] |
| Tester and witness (names, roles) | [ ] |
| Steps executed and measured values | [ ] |
| Data files and photographs (references) | [ ] |
| Deviations from the script | [ ] |
| Result (P / PC / F / NR / N/A) | [ ] |
| Condition, owner, cost, due date (if PC) | [ ] |
| Non-conformance ID (if F) | [ ] |
| Level reached for B6 register (L4 if passed) | [ ] |
| Signatures | Tester [ ]; Witness [ ]; Site Lead [ ] |

# Appendix B: Test day checklist

| # | Check | Done |
| --- | --- | --- |
| 1 | Configuration hash matches manifest before the first test | [ ] |
| 2 | Safety briefing delivered and recorded. Stop authority restated | [ ] |
| 3 | Permits issued (isolation, hot work, working at height as relevant) | [ ] |
| 4 | Witnesses present for safety, limit and offline tests | [ ] |
| 5 | Test mode flag `M0` set and recorded | [ ] |
| 6 | Instruments in calibration and time synchronised | [ ] |
| 7 | Host, staff, neighbours, community or users notified of the test window | [ ] |
| 8 | Transfer plan ready (Pilot B), outage plan agreed (A, C) | [ ] |
| 9 | Emergency contacts, first aid and fire plan displayed | [ ] |
| 10 | End of day: system returned to its safe, agreed state. Backup taken. Daily site record signed | [ ] |

# Appendix C: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 7, 16, 18, 19, 20, 21, 23) | KPIs and baseline, gates, risk triggers, safety governance, change control, publication, commissioning checklist and independent review |
| Feasibility Study (Sections 4.4 to 4.6, 7.2, 8.1, 9) | Offline resilience, grid interface limits, safety, schedule pressure |
| Technical Specification per Site (Sections 3.2 to 3.6, 5.5, 6.7, 7.6, 9) | Design rules, safe states, acceptance tests A1 to A10, B1 to B10, C1 to C10, commissioning steps |
| Interoperability and Device Compatibility Register (Sections 2 to 6, 10 to 12) | Compatibility levels, test IDs, delta testing, escalation, vendor commitments |
| Cybersecurity Plan (Sections 6, 8, 9, 10, Appendix B) | Security tests, remote-access rule, audit window, commissioning security checklist, incident exercises |
| Regulatory Compliance Assessment (Sections 5.1, 5.4, 5.5, 5.8, 9) | Export limit source, Kenya Power acceptance and witness, permits, Gate readiness |
| Installation and Commissioning Plan (Sections 6 to 14, Appendices A to D) | Hold points, phases, enablement order, punch list severities, commissioning certificate, handover pack, schedule |
| OpenEMS Configuration Baseline (Sections 6, 9, 11, 12, Appendix A) | Manifest and hashes, safe-state layer, mode records, validation checks V1 to V12, backup and restore |
| Procurement Plan (Sections 8.2, 11) | Acceptance conditions in contracts, retention and delay terms |
| MoU and Site Agreement templates (Site Agreement Sections 5, 6, 9, 10, Schedules 2, 3, 6, Pilot A, B, C terms) | Commissioning certificate, safe states, override rights, data roles, no disconnection or price rise at Pilot B, charging policy at Pilot C |
| Site Survey Reports (A3, A7, A8, B3, B4) | Existing devices, connectivity, safety and site constraints |
| Stakeholder Engagement Plan (Sections 7.3, 8) | Notice of works and tests, community briefings, launch events |

On completion of the site surveys, tender award, Gate 2 design review and the first lab-proven test scripts, each bracketed value is updated and this document is re-issued as version 1.0 for Gate 2. Completed per-site reports are filed at H7 and H8 and reissued with the Gate 3 evidence pack.

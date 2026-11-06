# Interoperability and Device Compatibility Register


## 1. Purpose and status

The Charter lists interoperability with local hardware as a top risk, and the Feasibility Study (D1, Section 4.3) requires every shortlisted device to be tested against OpenEMS before procurement award. This register is the single controlled record of that work. It tells the Steering Committee, procurement and installers which devices are allowed, on what conditions, and with what evidence.

It does four things:

1. Defines **what "compatible" means** for each class of device (Sections 3 to 5).
2. Defines **how devices are tested** and how results are recorded (Sections 6 and 10).
3. Holds the **register itself**: devices, drivers, vendor commitments and test records (Sections 7 to 9).
4. Links results to **gates, escalation and procurement** (Sections 11 and 12).

**Document control.** Owner: Technical Lead (README B6). Contributors: software engineer, site engineers, procurement lead, Cybersecurity and Data Protection Officer, Kenya Power grid engineer (TWG). Reviewed fortnightly in the TWG during build. Entries are append-only: a changed result is a new test record, never an overwrite. Changes to the method follow Charter Section 20 change control.

**Relationship to other documents.**

| Document | Relationship |
| --- | --- |
| Technical Specification per Site (B4) | Sets the equipment requirements and acceptance tests this register verifies |
| Site Survey Reports (B3) | Source of existing-device data (especially Pilot A inverters, Pilot C chargers) |
| Cybersecurity plan (B7) | Receives the security findings from device testing |
| Procurement plan and tender documents (C1) | Uses the register as the compatibility gate: a failure disqualifies |
| OpenEMS configuration baseline (C4) | Receives the tested driver and version set |
| Site acceptance test reports (C5) | Re-verifies on site what was proven in the lab |
| Feasibility Study (D1), Appendix B Q2 | This register answers: which local devices already have OpenEMS drivers? |

## 2. How the register works

### 2.1 Lifecycle of a device entry

| Stage | Status code | What happens | Evidence | When |
| --- | --- | --- | --- | --- |
| 1 | `CAND` | Device identified in market scan or site survey | Datasheet, vendor contact | Months 2 to 3 |
| 2 | `DOCS` | Vendor supplies protocol documents and written commitments (Section 9) | Register map or protocol spec, warranty letter | Months 3 to 4 |
| 3 | `DRVR` | Driver status established: existing, custom needed, or generic route | OpenEMS version check, driver assessment (Section 8) | Months 3 to 5 |
| 4 | `TEST` | Lab or sandbox test scheduled and run | Test record (Section 10) | Months 4 to 6 |
| 5 | `PASS` / `COND` / `FAIL` | Result recorded and approved by the TWG | Signed test record | Before Gate 1 shortlist, finalised before Gate 2 |
| 6 | `SITE` | Re-verified at site acceptance | C5 test report | Months 8 to 12 |
| 7 | `LIVE` | In operation, firmware and driver version frozen under change control | C4 baseline | From Gate 3 |

Other codes: `HOLD` (waiting on vendor or regulator), `WDRN` (withdrawn by vendor or programme).

### 2.2 Rules

1. **No award without a pass.** A device may be named in a tender award only with status `PASS` or `COND` and all conditions closed or costed. A `FAIL` disqualifies the device (Technical Specification Section 8).
2. **Version pinning.** Each result applies only to the tested combination of device model, firmware version, OpenEMS release and driver version. A change to any of these needs a delta test, scaled to the change (Section 10.3).
3. **Test what will be bought.** Existing installed equipment (for example Pilot A PV inverters) is tested on the actual unit or an identical unit and firmware, and the survey records that it is so.
4. **Written commitments count.** A verbal statement that a device "supports OpenEMS" is not evidence. Commitments are recorded in Section 9 with a document reference.
5. **Honest reporting.** Failures and workarounds are recorded with equal prominence to passes and feed the final evaluation report and replication guide.
6. **Open interfaces preferred.** Published, documented protocols score above proprietary links (Technical Specification design rule 6).

## 3. Compatibility levels

A device is rated at the highest level it has demonstrated. Levels build on each other.

| Level | Name | Meaning |
| --- | --- | --- |
| L0 | Paper | Datasheet and protocol documents reviewed. Interface type and control functions appear sufficient |
| L1 | Communication | Edge reads all required points and writes required setpoints in the lab, over the intended protocol, with stable operation over a soak period |
| L2 | Control | The relevant OpenEMS controller (for example peak shaving, SoC management, cluster load balancing) drives the device correctly through a scripted scenario |
| L3 | Resilience | Device behaves correctly under fault conditions: communication loss, Edge restart, internet loss, power cycle, out-of-range setpoints, recovery |
| L4 | Site | Same behaviour re-verified on site at acceptance testing, with the real wiring, network and loads |

**Minimum level for award: L3 in the lab.** L4 is required for go-live (Gate 3). L0 is enough only to enter the shortlist.

## 4. Pass criteria by device class

Requirements restate and extend Technical Specification Section 3.3. Values in brackets are to be confirmed by the TWG.

| Class | Code prefix | Must have (fail if missing) | Should have | Pilots |
| --- | --- | --- | --- | --- |
| PV inverter | `PVI` | Read of power, energy, status and alarms; remote active-power limit over an open interface; written vendor permission for third-party control under warranty | Reactive power control; stable behaviour at setpoint update rate of [x] s | A, B |
| Battery inverter or hybrid inverter | `BAT` | Remote active-power setpoint; documented register map; Kenya Power grid-code acceptance; anti-islanding; defined behaviour on loss of communication | Grid-forming mode (needed for isolated or mini-grid Pilot B); ramp-rate control | A, B, C (optional battery) |
| Battery system and BMS | `BMS` | Reports state of charge, power limits, alarms, temperature; safety certification [standard to be named]; cannot be driven outside BMS limits by any setpoint | Reports state of health; documented warranty throughput limits | A, B, C |
| Energy meter | `MTR` | Revenue-grade, bidirectional, Class 0.5S or better where available [confirm with Kenya Power]; Modbus or pulse output; calibration certificate | Update rate suited to control [x] s; time synchronisation | A, B, C |
| EV charger | `EVC` | OCPP [version to be fixed] or documented vendor interface; **dynamic power limiting during a session**; status and session logs; defined fallback limit on loss of link | Phase balancing; remote firmware update with signed images | C |
| Generator controller | `GEN` | Start and stop signal (digital or Modbus); read of kWh, run hours and status; generator keeps its own protection | Fuel flow meter interface | B |
| Edge computer | `EDG` | Industrial rating, watchdog, clean shutdown on power loss, runs the pinned OpenEMS release for [x] days without fault | Secure boot or equivalent hardening | A, B, C |
| Network equipment | `NET` | VPN capability, VLAN or equivalent segmentation, no open inbound ports by default | Mobile failover (second SIM) for Pilot B | A, B, C |

**Automatic disqualifiers (any class).** Control cannot be exercised without voiding warranty; no documented protocol and vendor will not provide one; hard-coded or unchangeable credentials that cannot be removed or isolated; no local service route in Kenya for a device that cannot be replaced by the programme itself.

## 5. Integration route options

For each device, the Technical Lead records which route applies. The route drives effort and risk.

| Route | Description | Typical risk | Cost driver |
| --- | --- | --- | --- |
| R1 | Existing OpenEMS driver for this exact model family | Low: still needs L1 to L3 testing | Test effort only |
| R2 | Existing driver for a different model of the same vendor or protocol family, adapted by configuration | Medium: behaviour may differ | Configuration and test effort |
| R3 | Generic protocol component (for example generic Modbus or OCPP) with a device-specific mapping | Medium | Mapping, test effort |
| R4 | New custom driver | High | Development, test, maintenance, upstream review |
| R5 | Gateway or protocol converter between device and Edge | Medium to high: extra failure point, extra cost | Hardware, configuration, security review |

*Availability of an existing driver must be checked against the specific OpenEMS release chosen for the pilot (Section 10.1). It must not be assumed from memory or from vendor marketing.*

## 6. Test method

### 6.1 Test environment

| Element | Requirement |
| --- | --- |
| Location | Laboratory or sandbox at [university partner or technology partner site]. Real devices where possible, vendor simulators only as a stated fallback and rated no higher than L1 |
| OpenEMS release | One pinned release for the whole test campaign [version], with commit or build identifier recorded |
| Edge hardware | The shortlisted Edge computer model, so that timing and resource results are representative |
| Network | Isolated test network mirroring the site design (separate VLAN, firewall rules as in the Technical Specification Section 3.5) |
| Instruments | Reference meter for cross-checking device readings; packet capture; logging of all setpoints sent and values returned |
| Time | All loggers on one synchronised time source |
| Safety | Battery and charger tests under a written lab safety plan, with a licensed electrician present for any mains work |

### 6.2 Test sets by device class

Each test has an ID used in the test records. "Pass" means the criterion is met in every run.

**Common to all classes (`T-COM`)**

| ID | Test | Pass criterion |
| --- | --- | --- |
| T-COM-01 | Point verification | Every read and write point in the register map returns or accepts correct values, units and scaling, checked against a reference |
| T-COM-02 | Soak | Continuous polling at the production rate for [72] hours with no unexplained gaps, no memory growth, no device lock-up |
| T-COM-03 | Device power cycle | Device restarts, Edge reconnects automatically within [x] minutes, no manual action |
| T-COM-04 | Edge restart | Edge restarts, resumes control within [x] minutes, device holds a safe state meanwhile |
| T-COM-05 | Link loss | Disconnect the link: the Edge flags the device as lost and applies the defined safe state; device applies its own fallback; recovery is clean |
| T-COM-06 | Internet loss | Cut upstream internet for [24] hours: control continues, data is buffered and synced on return |
| T-COM-07 | Out-of-range command | Setpoints beyond device limits are rejected or clamped by the device or the Edge, never executed unsafely |
| T-COM-08 | Credentials and access | Default credentials removed or neutralised; services not needed are disabled; no unauthenticated write path from the network |
| T-COM-09 | Documentation match | Observed behaviour matches the vendor protocol document. Discrepancies listed |

**PV inverter (`T-PVI`)**

| ID | Test | Pass criterion |
| --- | --- | --- |
| T-PVI-01 | Power limit step | Step the limit across [0, 50, 100%]. Output follows within [x] s and settles within [x]% |
| T-PVI-02 | Export limit control | Under OpenEMS feed-in limit, grid export stays at or below the set limit during load steps |
| T-PVI-03 | Limit release | Removing the limit restores full output. No sticky limit after restart |
| T-PVI-04 | Warranty route | Vendor written confirmation on file (Section 9) |

**Battery inverter, BMS and battery (`T-BAT`)**

| ID | Test | Pass criterion |
| --- | --- | --- |
| T-BAT-01 | Charge and discharge setpoints | Power follows commands within [x] s and tolerance [x]% in both directions |
| T-BAT-02 | State-of-charge limits | Charge stops at the configured upper SoC and discharge at the lower reserve SoC; BMS limits are never exceeded |
| T-BAT-03 | BMS alarm handling | Simulated or vendor-triggered alarm: Edge sees it, stops commanding, and the safe state is applied |
| T-BAT-04 | Peak shaving scenario | With the peak-shaving controller, import is held at setpoint within [tolerance] during a controlled load step |
| T-BAT-05 | ToU scenario | Charge and discharge occur in the configured windows with the reserve SoC respected |
| T-BAT-06 | Self-consumption scenario | Surplus PV charges the battery and export is limited as configured |
| T-BAT-07 | Round-trip efficiency | Measured with reference meters over [x] cycles; recorded as an input to D2 |
| T-BAT-08 | Grid-forming transfer (if required) | Transfer between grid-connected and islanded modes behaves as designed, under specialist supervision |
| T-BAT-09 | Communication loss behaviour | Battery goes to idle or minimum export as specified in the site Schedule 3 |

**Meter (`T-MTR`)**

| ID | Test | Pass criterion |
| --- | --- | --- |
| T-MTR-01 | Accuracy check | Readings agree with a reference within the class limit agreed with the Research and Evaluation Panel |
| T-MTR-02 | Update rate | Values refresh at a rate adequate for the controller [x] s, with timestamps where supported |
| T-MTR-03 | Direction and sign | Import and export signs correct and consistent across all meters |
| T-MTR-04 | Calibration record | Certificate on file, serial recorded |

**EV charger (`T-EVC`)**

| ID | Test | Pass criterion |
| --- | --- | --- |
| T-EVC-01 | OCPP session | Connect, authorise (test mode), start and stop a session with the pinned OpenEMS release, with the OCPP version recorded |
| T-EVC-02 | Dynamic power limit | Limit changed mid-session. The charger applies it within [x] s and the vehicle current follows. **Chargers that cannot accept limits during a session fail** |
| T-EVC-03 | Multi-charger balancing | With [N] chargers (or simulated sessions where hardware is limited, stated in the record), total power is held at the site limit under the chosen policy |
| T-EVC-04 | Policy behaviour | Fair-sharing or priority policy gives the expected shares |
| T-EVC-05 | Minimum current handling | Chargers below minimum current are paused or handled as designed, with no vehicle-side fault |
| T-EVC-06 | Vehicle variety | Tested with at least [x] vehicle types that are common locally, noting any that reject the limiting behaviour |
| T-EVC-07 | Loss of link | Charger drops to the configured fallback limit |
| T-EVC-08 | Session log quality | Logs give start, stop, energy, power and wait data needed for the full-capacity-share KPI, pseudonymised |
| T-EVC-09 | Firmware and security | Firmware version recorded; remote update path assessed; credentials and TLS status recorded |

**Generator controller (`T-GEN`)**

| ID | Test | Pass criterion |
| --- | --- | --- |
| T-GEN-01 | Start and stop command | Generator starts and stops on command through its own controller, which retains its protection |
| T-GEN-02 | Offset logic | On low SoC the generator starts correctly; with PV and battery available it stays off |
| T-GEN-03 | Minimum run time | Start and stop thresholds and minimum run time respected |
| T-GEN-04 | Metering | kWh, run hours and fuel volume readable or loggable by an agreed manual or automatic method |

**Edge computer and network (`T-EDG`, `T-NET`)**

| ID | Test | Pass criterion |
| --- | --- | --- |
| T-EDG-01 | Burn-in | [14] days at representative load with no unplanned restart |
| T-EDG-02 | Power loss | Abrupt power loss followed by a clean restart with no data corruption |
| T-EDG-03 | Temperature | Operates across the expected enclosure temperature range [x to y °C] |
| T-NET-01 | Segmentation | No path from host IT to the control network; no open inbound ports |
| T-NET-02 | Remote access (post-Gate 3 design) | Outbound-only encrypted tunnel with multi-factor authentication works as designed, while remote access stays disabled in operation until the audit is passed |
| T-NET-03 | Mobile failover (Pilot B) | Switches to the backup link and resumes sync |

## 7. Device register

One row per device model and firmware combination per site candidate. Copy rows as needed. Identifiers: `[class]-[pilot letter][number]`, for example `PVI-A01`.

### 7.1 Register columns

| Column | Content |
| --- | --- |
| ID | Unique entry ID |
| Pilot and site | A, B or C and the candidate site ID from the Site Survey Reports |
| Class | PV inverter, battery inverter, BMS, meter, charger, generator controller, Edge, network |
| Origin | New (to be procured), existing (installed at host) |
| Make, model, rating | As on nameplate |
| Firmware or software version | As tested |
| Interface and protocol | For example Modbus TCP, Modbus RTU, OCPP version, MQTT, HTTP, pulse |
| Vendor documents held | Document references |
| Route (R1 to R5) | From Section 5 |
| Driver ID | Link to driver register (Section 8) |
| OpenEMS release tested | Version |
| Highest level reached (L0 to L4) | From Section 3 |
| Status | Code from Section 2.1 |
| Conditions or workarounds | Text |
| Warranty and control confirmation | Reference to Section 9 |
| Local service in Kenya | Contact, response time |
| Owner and date | Technical Lead delegate, date |

### 7.2 Pilot A: Industrial park, hub or campus

| ID | Class | Origin | Make and model | Firmware | Protocol | Route | Driver ID | Level | Status | Conditions | Warranty ref |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| PVI-A01 | PV inverter | Existing [or new] | [ ] | [ ] | [Modbus TCP / RTU] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| PVI-A02 | PV inverter (second model, if any) | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| BAT-A01 | Battery or hybrid inverter | New | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| BMS-A01 | Battery system and BMS (about 250 kWh, size to be confirmed) | New | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| MTR-A01 | Grid-connection meter | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| MTR-A02 | Research-grade meter (separate logger) | New | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| EDG-A01 | Edge computer | New | [ ] | [ ] | n/a | n/a | n/a | [ ] | `CAND` |  | [ ] |
| NET-A01 | Router, firewall, switch | New | [ ] | [ ] | n/a | n/a | n/a | [ ] | `CAND` |  | [ ] |

*Pilot A watch-points:* existing inverters may have locked firmware, no open interface, or warranty terms that forbid third-party control. Record as a red item at survey (Site Survey Report A3) and resolve before the site is shortlisted.

### 7.3 Pilot B: Rural microgrid

| ID | Class | Origin | Make and model | Firmware | Protocol | Route | Driver ID | Level | Status | Conditions | Warranty ref |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| PVI-B01 | PV inverter (50 to 100 kW total) | New | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| BAT-B01 | Battery inverter (grid-forming if topology requires) | New | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| BMS-B01 | Battery system and BMS (about 200 kWh) | New | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| GEN-B01 | Generator controller (if diesel present) | Existing | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| MTR-B01 | Feeder input meter | New | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| MTR-B02 | Transformer or customer-group check meters | New | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| EDG-B01 | Edge computer | New | [ ] | [ ] | n/a | n/a | n/a | [ ] | `CAND` |  | [ ] |
| NET-B01 | Router with dual-SIM or fallback | New | [ ] | [ ] | n/a | n/a | n/a | [ ] | `CAND` |  | [ ] |

*Pilot B watch-points:* the generator may have no digital interface (route R5 or relay control); grid-forming capability and transfer logic need specialist design, and the topology decision (Technical Specification Section 6.1) must be made before the battery inverter is shortlisted; spares and service response in a remote location are part of the pass criteria.

### 7.4 Pilot C: EV charging site

| ID | Class | Origin | Make and model | Firmware | Protocol and OCPP version | Route | Driver ID | Level | Status | Conditions | Warranty ref |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| EVC-C01 | Fast charger model 1 (site has about 10 to 20 units) | [Existing or new] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| EVC-C02 | Fast charger model 2 (if mixed fleet) | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| MTR-C01 | Transformer secondary meter | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| MTR-C02 | Site import meter | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| BMS-C01 | Optional battery (if fitted) | New | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `CAND` |  | [ ] |
| EDG-C01 | Edge computer | New | [ ] | [ ] | n/a | n/a | n/a | [ ] | `CAND` |  | [ ] |
| NET-C01 | Router, firewall, switch | New | [ ] | [ ] | n/a | n/a | n/a | [ ] | `CAND` |  | [ ] |

*Pilot C watch-points:* the charger-side pass criterion is dynamic power limiting during a session, which must be proved per model and OCPP version; the transformer meter feed needs a response time suited to control, which depends on Kenya Power data access (Technical Specification open item 5); charger vendors must cooperate on integration (site agreement Pilot C special conditions).

## 8. Driver register

One row per driver or mapping used by the pilots, whether existing or custom.

### 8.1 Columns

| Column | Content |
| --- | --- |
| Driver ID | `DRV-[number]` |
| Devices covered | Register IDs |
| Source | Upstream OpenEMS, generic component with mapping, or programme-developed |
| OpenEMS release and commit | As tested |
| Route | R1 to R5 |
| Gaps | Points or functions not supported |
| Effort | See scale in 8.2 |
| Owner | Named developer |
| Licence | Apache 2.0 for programme code; upstream components keep their own licence (Eclipse Public License 2.0 for Edge and Backend) |
| Upstream plan | Offer upstream after TWG review: yes, no, later |
| Maintenance plan | Who updates the driver when firmware or OpenEMS changes |
| Status | Planned, in development, in test, accepted, frozen |

### 8.2 Effort scale for custom drivers

Effort in person-days is a placeholder to be calibrated by the software engineer once the first driver has been assessed. The scale is for budgeting inside the 20% software and integration share of the reference cost structure, and for triggering escalation.

| Size | Typical case | Person-days |
| --- | --- | --- |
| S | Configuration of an existing driver or generic component, no code change | [ ] |
| M | Mapping of a documented Modbus device to existing components | [ ] |
| L | New driver for a documented device with standard behaviour | [ ] |
| XL | New driver for a poorly documented device, reverse engineering, or complex control (grid-forming, session-level charger control) | [ ] |

### 8.3 Driver rows

| Driver ID | Devices | Source | Route | Gaps | Effort | Owner | Upstream plan | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| DRV-01 | [ ] | [ ] | [ ] | [ ] | [S/M/L/XL] | [ ] | [ ] | Planned |
| DRV-02 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | Planned |
| DRV-03 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | Planned |
| DRV-04 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | Planned |

**Driver budget roll-up.** Total custom-driver effort [person-days] and cost [KSh], against the software and integration budget line [KSh]. Reported to the PMO monthly; any overrun above the Charter tolerance goes to change control.

## 9. Vendor commitments register

For every device with status above `CAND`, the following written commitments are requested (see the vendor questionnaire in Appendix A). The Technical Specification Section 8 makes these a condition of award.

| Entry | Content |
| --- | --- |
| Register ID | Device |
| Vendor and local agent | Names and contacts |
| Protocol documents supplied | Register map, OCPP profile, version, date, reference |
| Third-party control under warranty | Written confirmation: received / refused / pending, with reference |
| Firmware policy | Update frequency, notification, ability to hold a firmware version |
| Local service | Location, response time, spares held in Kenya |
| Cooperation on integration | Named technical contact, support hours, response commitment (essential for chargers) |
| Security | Vulnerability disclosure contact, default credential policy |
| End of life | Take-back or disposal route for batteries |
| Status | `OK`, `PENDING`, `REFUSED` |

| Register ID | Vendor | Docs | Warranty letter | Firmware policy | Local service | Integration contact | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | `PENDING` |

## 10. Version control and test records

### 10.1 Baseline versions

| Item | Value | Frozen at |
| --- | --- | --- |
| OpenEMS release for the test campaign | [ ] | Start of Month 4 |
| OpenEMS release for production | [ ] | Gate 2 |
| Edge operating system and image | [ ] | Gate 2 |
| Test lab configuration repository | [ ] | Start of testing |

If the production release differs from the test release, the TWG decides which tests are repeated (10.3). The decision is recorded.

### 10.2 Test record template

One record per device, per test run. Records are stored with the configuration baseline (C4) and are public subject to the security and privacy review, in line with the open-by-default principle.

| Field | Entry |
| --- | --- |
| Record ID | `TR-[register ID]-[number]` |
| Device and register ID | [ ] |
| Device firmware | [ ] |
| OpenEMS release and driver version | [ ] |
| Test environment | [Real device / simulator]; location; date |
| Tester and witness | [ ] |
| Tests run (IDs from Section 6.2) | [ ] |
| Results by test | Pass / Fail / Not run, with data file references |
| Deviations from procedure | [ ] |
| Anomalies and workarounds | [ ] |
| Level reached | L[ ] |
| Recommended status | `PASS` / `COND` / `FAIL` |
| Conditions (if any) with owner and due date | [ ] |
| TWG decision and date | [ ] |

### 10.3 Delta testing rules

| Change | Minimum retest |
| --- | --- |
| Device firmware change | Full T-COM and the control test for the class |
| OpenEMS release change | T-COM-01 to T-COM-05 for each device, plus the control scenario for each class |
| Driver change | Full set for the devices it covers |
| Network or Edge hardware change | T-COM-02, T-COM-06, T-EDG, T-NET |
| After Gate 3 (any change) | Logged change process, tested off-site first, rollback plan (Technical Specification Section 3.5) |

## 11. Failure handling and escalation

| Situation | Action | Owner | Escalation |
| --- | --- | --- | --- |
| Test failure on a selected device | Record, root-cause with the vendor, retest or substitute | Technical Lead | **Charter escalation trigger: failed compatibility test on a selected device.** Report to PMO at the next fortnightly review and to SteerCo in the quarterly report |
| Vendor refuses written permission for third-party control | Device `FAIL` unless an alternative route preserves warranty | Technical Lead and procurement lead | PMO |
| Existing installed device cannot be integrated (Pilot A) | Reassess the site or negotiate inverter replacement; do not proceed on an unsupported workaround | Technical Lead | Programme Director. Possible effect on site selection at Gate 1 |
| Custom driver effort exceeds the budget line | Re-scope, simplify the device set, or request reallocation | Programme Manager | SteerCo for any reallocation between sites or use of contingency (Charter Section 20) |
| Device shortlisted for a site is discontinued or unavailable locally | Replace, retest, update register | Technical Lead | PMO |
| Security finding in device or firmware | Log, assess, mitigate by network control or replacement | Cybersecurity and Data Protection Officer | Critical findings block go-live (Gate 3) |
| Charger cannot limit power in-session | `FAIL` for Pilot C use | Technical Lead | Consider charger substitution or hardware controller. Report in Gate 1 evidence |

## 12. Gate evidence

| Gate | Evidence from this register |
| --- | --- |
| Gate 1: Design approval (Month 4 to 6) | Hardware shortlist per pilot at L0 or higher with documents held; driver route and effort estimated for each device; at least one L1 or higher result for the riskiest device in each pilot (the hardest integration: existing PV inverter at A, grid-forming or generator interface at B, charger limiting at C); vendor commitments status. Feeds Feasibility Study Gate 1 condition 4 |
| Gate 2: Build readiness (Month 8) | All devices named in tenders at `PASS` or `COND` with L3 in the lab; conditions closed or costed; production versions frozen; vendor commitments received; compatibility test report issued (D4) |
| Gate 3: Go-live (Month 12) | Site acceptance (L4) completed per B4 acceptance tests; configuration baseline under version control; security audit passed |
| Gate 4: Mid-operation review (Month 18) | Incident and change log summary: any compatibility problems found in operation, firmware changes and retests |
| Gate 5: Closure (Month 24) | Final register, driver licences and upstream status, replication guide input (E3) |

## 13. Schedule

| Activity | Months | Output |
| --- | --- | --- |
| Market scan of locally available devices, with local service check | 2 to 3 | `CAND` entries |
| Vendor questionnaire issued and documents collected | 3 to 4 | Section 9 populated |
| Driver status check against the pinned OpenEMS release | 3 to 5 | Section 8 populated |
| Lab set-up and first tests (riskiest devices first) | 4 to 5 | First test records, Gate 1 evidence |
| Full test campaign | 5 to 7 | Results for all shortlisted devices |
| Compatibility test report (D4) | 7 to 8 | Gate 2 evidence |
| Site re-verification (L4) | 9 to 12 | C5 reports |

Timings follow the Charter deliverable D4 (Months 4 to 8) and the Feasibility Study fieldwork plan (hardware scan and testing in Months 2 to 5). **Test the riskiest devices first,** so that a failure is found while there is still time to substitute.

## 14. Roles

| Role | Responsibility in this register |
| --- | --- |
| Technical Lead | Owns the register, approves routes and results, chairs the TWG decisions |
| Software engineer | Runs tests, writes and maintains drivers, keeps the OpenEMS version baseline |
| Site engineers | Record existing devices at survey; run L4 tests; verify wiring and network |
| Procurement lead | Enforces the compatibility gate in tenders; collects vendor commitments |
| Cybersecurity and Data Protection Officer | Reviews device security findings; approves network design; owns audit scope with B7 |
| Kenya Power grid engineer (TWG) | Reviews grid-code compliance, protection and meter requirements for inverters and meters |
| Research Lead and Panel | Approve meter accuracy criteria and measurement points |
| PMO | Tracks escalations, driver budget and gate evidence |
| University partner | Hosts or supports the lab where agreed, supports student testing and training |

## 15. Open items and dependencies

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Choose and pin the OpenEMS release for the test campaign | Start of testing | Technical Lead |
| 2 | Confirm test lab location, access and safety arrangements | Month 4 | Technical Lead, university partner |
| 3 | Confirm the OCPP version or versions to be required in the Pilot C tender | Pilot C shortlist | Technical Lead |
| 4 | Fix the meter class and calibration requirement with Kenya Power and the Research Panel | Meter shortlist | Technical Lead, Research Lead |
| 5 | Decide Pilot B topology (grid-connected, mini-grid, isolated), which drives battery inverter requirements | BAT-B shortlist | Technical Lead |
| 6 | Name the battery safety standard accepted by Kenya Power and the insurer | BMS entries | Site Leads |
| 7 | Confirm existing-device details from the Pilot A and Pilot C surveys | `PVI-A`, `EVC-C` entries | Site Leads |
| 8 | Agree what counts as acceptable use of simulators where real multi-charger hardware is not available | Pilot C tests | TWG |
| 9 | Calibrate the driver effort scale and costs | Budget reconciliation | Software engineer, Programme Manager |
| 10 | Decide whether the register is also published as a living public table in the open repository | Open publication | Technical Lead, Research Lead |

## 16. Immediate next steps

1. TWG to approve this method (Sections 3 to 6) and the OpenEMS baseline release.
2. Technical Lead to start the market scan, with a local service check as an entry condition.
3. Procurement lead to issue the vendor questionnaire (Appendix A) alongside the market scan.
4. Site Leads to record existing devices at Pilot A and Pilot C candidates in this register as `CAND`, with photographs of nameplates.
5. Software engineer to assess driver routes for the first candidates and calibrate the effort scale.
6. Set up the test lab and test record store, and run the riskiest devices first.
7. Feed progress into the monthly dashboard and into the Gate 1 evidence pack.

## Appendix A: Vendor questionnaire (for each device)

1. Product name, model, firmware version and date of release. Are firmware versions selectable or held?
2. Which communication interfaces and protocols are supported (Modbus TCP or RTU, OCPP and version, MQTT, HTTP, others)? Please supply the full register map or protocol profile.
3. Which functions can be controlled remotely (power limit, setpoint, start and stop, mode)? Update rates and latency?
4. What does the device do on loss of communication? Is the fallback configurable?
5. Does remote control by a third-party energy management system, specifically OpenEMS, affect the warranty? Please confirm in writing.
6. Are there known integrations with OpenEMS? Please supply references. Can you support our test campaign (loan units, technical contact)?
7. For chargers: can the power limit be changed during a session? What are the minimum current and phase behaviours? Which vehicles are known to be problematic?
8. For batteries: BMS limits, alarm outputs, certifications, throughput limits under warranty, ambient operating range.
9. Default credentials and how to change them. Vulnerability disclosure contact. Update mechanism and image signing.
10. Local service: location, response times, spares in Kenya, training offered.
11. End-of-life take-back and disposal.
12. Indicative price and lead time in Kenya.

## Appendix B: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 10, 16, 18, 20) | Interoperability assumption and risk, gates, escalation trigger, change control |
| Feasibility Study (Section 4.3, Section 12.2 condition 4, Appendix B Q2) | Approach, Gate 1 condition, open question |
| Technical Specification per Site (Sections 3.2, 3.3, 3.5, 5 to 8) | Design rules, equipment requirements, device lists, acceptance tests, procurement requirements |
| Site Survey Reports (A3, B3, B4) | Existing devices, interfaces, connectivity |
| MoU and Site Agreement templates | Control authority, warranty and ownership of equipment, remote access |
| Stakeholder Engagement Plan (Section 6.5) | Pre-procurement market briefing, compatibility testing before award, upstream contributions |

# Technical Specification per Site


## 1. Purpose and status

This specification turns the Programme Charter, Feasibility Study (D1) and Site Survey Reports into an engineering baseline for Pilots A, B and C. It covers system sizing logic, OpenEMS controller selection, device and interface requirements, metering, network and security, safety, acceptance tests and open items. It feeds procurement (C1), the compatibility register (B6), the cybersecurity plan (B7), the configuration baseline (C4) and Gate 2 build readiness.

**Important limits.** No site has been selected or surveyed, and no load, tariff or transformer data exists yet. Sizes below are the Charter configurations. They are **confirmed or changed only after** survey data and the techno-economic model (D2). Where this document gives a sizing method, it gives the method, not a result.

**Document control.** Owner: Technical Lead. Reviewers: TWG (including the Kenya Power grid engineer), Cybersecurity and Data Protection Officer, Research and Evaluation Panel (measurement sections). Approval: Programme Director at Gate 1, then frozen as the Gate 2 baseline. Later changes follow Charter Section 20 change control.

## 2. Specification summary

| Item | Pilot A: Industrial park, hub or campus | Pilot B: Rural microgrid | Pilot C: EV charging site |
| --- | --- | --- | --- |
| Charter configuration | Existing or new PV with about 250 kWh battery | 50–100 kW PV with about 200 kWh battery | About 10–20 fast chargers, optional small battery |
| Primary objective | Peak shaving, ToU shifting, net-metering optimisation | Loss reduction, reliability, self-consumption, diesel offset | Transformer protection and charging management |
| Main OpenEMS controllers | Peak shaving, ToU, self-consumption, feed-in limit | Self-consumption, SoC management, generator offset, local control | EV cluster load balancing, transformer limit |
| Grid relationship | Grid-connected, net-metering \[to be confirmed by EPRA\] | Long feeder, mini-grid or isolated \[survey\] | Grid-connected, shared transformer |
| Hardest technical issue | Integrating existing inverters without voiding warranty | Connectivity, theft, loss measurement | OCPP compatibility and transformer data |
| Key measurement | Interval load at grid connection | Feeder energy balance | Transformer loading and charger sessions |
| Remote access | Only after Gate 3 audit | Only after Gate 3 audit | Only after Gate 3 audit |

## 3. Common architecture (all sites)

### 3.1 System layers

| Layer | Specification | Notes |
| --- | --- | --- |
| Edge controller | One OpenEMS Edge instance per site on an industrial-grade, fanless or well-ventilated computer with local storage; \[model to be selected\] | Runs all control logic locally. Must keep controlling during internet loss (tested at commissioning) |
| Field devices | Inverters, battery systems, meters, EV chargers and generator controllers connected over Modbus TCP or RTU, MQTT, HTTP or OCPP | Each device needs an existing OpenEMS driver, or a custom driver costed in the integration budget |
| User interface | OpenEMS UI served from the Edge for the local operator | UI is AGPL 3.0, so any modified version offered over a network must have its source available. Tracked in the licence register |
| Backend (optional) | OpenEMS Backend for multi-site monitoring, possibly hosted by the Ministry of Energy | Not required for control. Data flows are outbound from the Edge, with no inbound control path from the internet |
| Independent metering | Research-grade meters feeding a separate logger | Keeps the evaluation independent of the control system (see 3.4) |

### 3.2 Design rules

1. **Local first.** All safety and protection decisions are made on site. Cloud or remote functions never sit in a protection or control loop.
2. **Behind the connection point only.** OpenEMS controls assets behind the customer connection. It does not control Kenya Power assets and does not change utility protection settings (draft MoU Schedule 1B).
3. **Fail safe.** On loss of communication with a device, the Edge applies a defined safe state: battery to idle or minimum export, chargers to a configured fallback limit, generator under its own controls. Safe states are specified per site in Schedule 3 of the site agreement.
4. **Protection stays in the hardware.** Battery management systems, inverter anti-islanding, breakers and fire detection operate independently of OpenEMS. OpenEMS is a supervisory layer, not a protection device.
5. **Overrides are logged.** Any manual override of OpenEMS control is recorded with time, person and reason.
6. **Open interfaces preferred.** Procurement scores open, documented protocols (published Modbus maps, OCPP) above proprietary links.
7. **Baseline integrity.** Control modes are switched only on the schedule in the M&V protocol (storage idle or unmanaged for the baseline, then controlled).

### 3.3 Equipment requirements (generic)

| Equipment | Minimum requirement | Verification |
| --- | --- | --- |
| Battery system | Lithium-based system with integrated BMS, documented communication interface giving state of charge, power limits, alarms and temperature; certified to recognised safety standards \[IEC or UL standard to be named, confirmed with Kenya Power and insurer\]; rated for local ambient temperature, dust and humidity; local warranty and service | Datasheet, certificates, compatibility test |
| Hybrid or battery inverter | Remote setpoint control via Modbus or equivalent; grid-code compliance accepted by Kenya Power; anti-islanding; documented register map | Compatibility test, Kenya Power acceptance |
| PV inverters (existing or new) | Power-limit and read access over an open interface; control permitted under warranty | Written vendor confirmation |
| Meters | Revenue-grade, Class 0.5S or better where available \[confirm against Kenya Power requirements\], bidirectional, Modbus or pulse output, calibration certificate | Calibration record, accuracy check |
| Edge computer | Industrial rating, watchdog, UPS or supercapacitor-backed clean shutdown, secure boot or equivalent hardening where available | Factory acceptance |
| Networking | Managed switch where needed, firewall or router with VPN capability, isolated VLAN for Programme devices | Security design review |
| Enclosures | Lockable, ingress rating suited to location, surge protection | Site inspection |

### 3.4 Metering and data architecture

The evaluation needs two views that agree with each other.

| Measurement point | Purpose | Resolution | Owner |
| --- | --- | --- | --- |
| Grid connection (import and export) | Peak import, energy cost, net-metering, baseline comparison | 1 minute logged, 15 or 30 minute for billing comparison \[confirm tariff interval\] | Research Panel and Edge |
| PV generation | Self-consumption ratio | 1 minute | Edge |
| Battery AC terminals | Charge and discharge energy, round-trip efficiency | 1 minute | Edge |
| Key controllable loads | Load shifting and critical load protection | 1 to 5 minutes | Edge |
| Generator output and fuel (Pilot B) | Diesel offset | Run hours, kWh, fuel volume | Edge and site log |
| Transformer secondary (Pilots C, and A and B where possible) | Transformer loading, voltage | 1 minute | Research Panel and Kenya Power read access |
| Charger session logs (Pilot C) | Waiting time, throttling, full-capacity share | Per session, pseudonymised | Edge |

**Rules.** Time synchronisation to a common source on all loggers. Local buffering with at least \[30\] days of storage. Data dictionary and version-controlled configuration. The Research Panel approves meter locations and accuracy checks before data collection starts. Customer-level and driver-level data are aggregated or pseudonymised before leaving the site, per the Data Protection Act, 2019 and the host agreements.

### 3.5 Network and cybersecurity baseline

| Control | Requirement |
| --- | --- |
| Segmentation | Programme devices on a separate network from host IT and operational technology. No path from host IT into the control network |
| Remote access | Disabled until the independent security audit is passed (Gate 3). Afterwards, outbound-only encrypted tunnels or VPN with multi-factor authentication. No open inbound ports |
| Accounts | Individual named accounts, role-based access, default passwords removed at commissioning, secrets held outside the repository |
| Encryption | Encrypted transport for all remote and cloud links. Protocol-level security enabled where devices support it, otherwise compensating network controls |
| Patching | Logged change process for Edge and device firmware, tested before rollout, rollback plan |
| Logging | Security and configuration events logged and retained \[period set in the data plan\] |
| Physical | Locked enclosures, tamper evidence, restricted battery-room access |
| Incident response | Named owner, notification to Kenya Power and, where required, EPRA and the Data Protection Commissioner (breach notification within \[48\] hours to the PMO per draft MoU) |
| Audit | Independent audit of architecture and configuration before Gate 3. Critical findings block go-live |

### 3.6 Safety baseline

- Electrical work only by licensed contractors, to applicable Kenyan standards and Kenya Power requirements.
- Site safety plan, battery fire risk assessment and emergency response plan agreed with local responders before installation (Gate 2).
- Insurer notified and acceptance recorded before installation.
- Battery location chosen for ventilation, separation from occupied areas and fuel stores, and emergency access. Detection and suppression type set by the risk assessment \[specialist input needed\].
- Isolation points, signage and lock-out procedures documented for operators.
- End-of-life and decommissioning route for batteries agreed before procurement.

## 4. Sizing method (all sites)

Sizes are checked, not assumed, using survey data.

1. **Baseline analysis.** Build the load profile from at least 12 months of interval data (Pilot A, C) or the best available estimate (Pilot B).
2. **Define the duty.** Energy to shift or shave, peak power to cut, and duration of the peak window.
3. **Size the battery.** Usable energy needed for the duty plus margin for depth-of-discharge limits, efficiency losses and degradation over the pilot. Power rating set by the highest peak reduction that is economic.
4. **Size PV.** Match to daytime load and battery charging, within roof or land limits and the net-metering cap \[confirm with EPRA\].
5. **Check grid limits.** Transformer headroom, protection settings and Kenya Power's maximum export or capacity rules.
6. **Test the economics.** Run the techno-economic model for battery cost ±20%, discount rate 5–12%, export credit at and below 50%, and tariff spread. State break-even conditions per site (Feasibility Study 5.4 and 5.6).
7. **Reconcile with budget.** Site cost against the reconciled budget (open issue in Feasibility Study 5.1).

## 5. Pilot A: Industrial park, hub or campus

### 5.1 Objective and configuration

Test peak shaving, ToU shifting and net-metering optimisation against a baseline with storage idle or unmanaged.

| Parameter | Specification |
| --- | --- |
| Battery energy | About 250 kWh nominal (Charter). **Open question:** the Charter reference site is 100 kW PV plus 300 kWh. Confirm 250 kWh against measured load. Do not change without the sizing method in Section 4 |
| Battery power | \[kW, from peak-shaving duty. Starting range to test: 0.5C to 1C, i.e. about 125–250 kW, subject to inverter and transformer limits\] |
| PV | Existing or new, \[kWp\] |
| Connection | Behind the main incomer, AC-coupled where PV already exists unless the survey favours DC coupling \[decide at survey\] |
| Grid meter | Bidirectional revenue-grade at the connection point, plus separate research meter if the utility meter cannot be shared |

### 5.2 Controllers and control logic

| Function | OpenEMS approach | Parameters to set |
| --- | --- | --- |
| Peak shaving | Discharge to cap grid import at a setpoint | Peak setpoint (kW), recharge threshold, daily review |
| ToU shifting | Charge in off-peak, discharge in peak window | Tariff schedule, minimum reserve SoC |
| Self-consumption | Charge from surplus PV, avoid export where export credit is only 50% | Export limit, priority order |
| Feed-in limit | Cap export to net-metering or Kenya Power limit | \[kW, from interconnection approval\] |
| Critical-load protection | Never curtail production-critical loads. Override right for the host | List of protected loads and override procedure |

**Note on demand charges.** Peak shaving earns money only if the tariff has demand charges, and ToU shifting only if the spread is meaningful. Both are open questions (Feasibility Study Appendix B, Q1). If neither exists, the site becomes a weak economic test and should be reconsidered.

### 5.3 Device integration

| Device | Interface | Requirement | Risk |
| --- | --- | --- | --- |
| Existing PV inverter | Modbus TCP or RTU \[survey\] | Read production, set power limit | Warranty, locked firmware, no open interface |
| New battery inverter and BMS | Modbus or equivalent | Setpoint control, SoC, alarms | Driver availability |
| Grid meter | Modbus or pulse | Real-time import and export | Update rate, accuracy |
| Controllable loads (optional) | Relay or Modbus | Only if agreed with host | Process interference |

### 5.4 Site infrastructure and grid interface

- Space and location for battery room or container, with floor loading, ventilation and drainage checked.
- Switchboard spare capacity and protection coordination reviewed by a licensed engineer.
- Kenya Power interconnection application, protection and anti-islanding settings as required.
- EPRA written confirmation of net-metering eligibility and terms before Gate 1.
- Edge and meters in a secured enclosure, network separated from host IT.

### 5.5 Acceptance tests (Pilot A)

| # | Test | Pass criterion |
| --- | --- | --- |
| A1 | Insulation, earthing, protection and safety checks | Signed electrical safety certificate |
| A2 | Communication to every device | All read and write points verified against the register map |
| A3 | Peak shaving trial | Import held at setpoint within \[tolerance\] during a controlled load step |
| A4 | ToU schedule trial | Charge and discharge occur in the configured windows |
| A5 | Export limit | Export does not exceed the approved limit |
| A6 | Internet loss | Control continues for \[24\] hours with no loss of function and data is buffered then synced |
| A7 | Device loss | Safe state applied when each device is disconnected |
| A8 | Override | Host override works and is logged |
| A9 | Meter accuracy check | Within the class limits agreed with the Research Panel |
| A10 | Data logging | Complete data at specified resolution for \[7\] days before the baseline period |

## 6. Pilot B: Rural microgrid

### 6.1 Objective and configuration

Measure loss reduction, reliability and self-consumption, and displace diesel where present. This is the hardest site to evaluate and has the most community exposure.

| Parameter | Specification |
| --- | --- |
| PV | 50–100 kW (Charter), \[kWp, from load and land\] |
| Battery energy | About 200 kWh (Charter). Size to cover the evening peak and reliability duty, from measured or estimated load \[survey\] |
| Battery power | \[kW, from evening peak\] |
| Network | Grid-connected on a long feeder, mini-grid or isolated \[survey outcome decides the topology\] |
| Diesel generator | Integrated if present. Generator keeps its own protection and controls |
| Operator | Defined operator (cooperative, estate or utility) with tariff arrangement consistent with any EPRA mini-grid or permit requirement |

**Topology options to decide at survey.**

| Topology | Key design implications |
| --- | --- |
| Grid-connected on long feeder | Behind-the-meter or feeder-connected \[Kenya Power decision\]. Islanding capability only if approved |
| Mini-grid with grid | Grid-forming capability, transfer logic and protection need a specialist design |
| Isolated | Battery inverter must form the grid. Generator and PV coordination critical |

### 6.2 Controllers and control logic

| Function | OpenEMS approach | Parameters |
| --- | --- | --- |
| Self-consumption and SoC management | Charge from PV, discharge in evening peak, keep reserve for outages | Reserve SoC, limits for battery life |
| Generator offset | Prefer PV and battery, run generator only when needed | Start and stop thresholds, minimum run time |
| Local control | Full autonomy from the internet | Safe state and fallback rules |
| Loss and reliability measurement | Logging of energy input, outputs and outages | Metering plan in 6.4 |

### 6.3 Device integration

| Device | Interface | Requirement | Risk |
| --- | --- | --- | --- |
| PV inverters | Modbus or equivalent | Power limit and read | Driver availability |
| Battery inverter and BMS | Modbus or equivalent | Setpoint control and grid-forming where needed | Complexity, cost |
| Generator controller | Modbus or relay | Start and stop signal, kWh and run-hour read | Often no digital interface |
| Meters | Modbus or pulse | Feeder and generator metering | Coverage |

### 6.4 Loss measurement design

The central measurement challenge is to separate technical from commercial losses (Feasibility Study Appendix B, Q3). The minimum design:

1. **Energy balance.** Measured energy entering the feeder or network, minus energy billed or metered at customers, before and after OpenEMS control.
2. **Metering coverage.** Record the share of customers metered. Where coverage is low, add check meters on selected transformers or customer groups \[survey decides\].
3. **Technical loss estimate.** Use feeder data (length, conductor, loading) and measured voltage drop to estimate technical losses, stating uncertainty.
4. **Voltage monitoring.** Measure at feeder end and at the transformer secondary at least during peak.
5. **Normalisation.** Account for weather, load growth and any customer changes.
6. **Honest limits.** If separation is not defensible, report total loss change and say so. The Research Panel decides the method before data collection.

### 6.5 Connectivity, security and site resilience

- Measure mobile coverage at site. Consider a second SIM or satellite fallback \[survey\].
- Edge caches data locally and syncs when connected. Data-gap threshold \[to be agreed\].
- Physical protection of cabinets against theft and vandalism, lightning, flood, dust, heat and wildlife.
- Named local operator able to reset and inspect the system, with trained backup.
- Spares kit and agreed service response time.

### 6.6 Community and regulatory conditions

Before procurement: documented informed community agreement, EPRA written position on BESS and mini-grid licensing, land lease or consent, and host agreement wording that the pilot causes no disconnection or price rise for customers served.

### 6.7 Acceptance tests (Pilot B)

| # | Test | Pass criterion |
| --- | --- | --- |
| B1 | Electrical safety, earthing, lightning protection | Signed certificate |
| B2 | Communication to all devices | All points verified |
| B3 | Evening peak dispatch | Battery serves the configured window |
| B4 | Generator offset | Generator avoided under test conditions, with correct start behaviour on low SoC |
| B5 | Offline operation | Full control for \[72\] hours with no connectivity, then clean data sync |
| B6 | Outage transfer | Behaviour matches the design for the chosen topology |
| B7 | Voltage and metering checks | Meters verified, voltage logging in place |
| B8 | Security and tamper | Cabinets locked, default credentials removed |
| B9 | Operator drill | Local operators complete a reset and fault procedure |
| B10 | Baseline data | \[7\] days of complete data before baseline period |

## 7. Pilot C: EV charging site

### 7.1 Objective and configuration

Protect the transformer through managed charging while measuring the effect on charging delay.

| Parameter | Specification |
| --- | --- |
| Chargers | About 10–20 fast chargers (Charter), \[make, model, power rating, connector types, OCPP version\] |
| Battery (optional) | Small battery to shave peaks if economics and space allow \[decide at sizing\] |
| Transformer | \[kVA rating, age, loading, ownership: survey\] |
| Site limit | Programme-set site limit (kW) below the safe transformer limit \[value set with Kenya Power\] |

**Sizing note.** Total charger nameplate power can exceed transformer capacity by a large margin. The managed-charging design must show, from charger session data, how often the site limit would bind and what delay drivers would experience. This is the key output of the design phase.

### 7.2 Controllers and control logic

| Function | OpenEMS approach | Parameters |
| --- | --- | --- |
| EV cluster load balancing | Allocate available site power across active chargers | Site limit, per-charger minimum, policy |
| Charging policy | Fair sharing or priority (for example fleet schedules) | Policy agreed in Schedule 3 and displayed to drivers |
| Maximum wait | Alarm and policy adjustment if wait exceeds the agreed limit | Maximum wait time \[to be agreed\] |
| Transformer protection | Reduce site limit if measured loading approaches threshold | Thresholds \[with Kenya Power\] |
| Battery support (if fitted) | Discharge during charging peaks, recharge off-peak | SoC reserve |

**Verification needed.** OpenEMS supports charger control through specific drivers and OCPP. Whether cluster balancing works with each shortlisted charger model and OCPP version must be proved in the compatibility test (B6) before award. Chargers that cannot accept power limits during a session are not suitable.

### 7.3 Device integration

| Device | Interface | Requirement | Risk |
| --- | --- | --- | --- |
| Chargers | OCPP \[version\] or vendor interface | Dynamic power limiting per session, status, session logs | Vendor cooperation, firmware |
| Transformer meter | Modbus or Kenya Power data feed | Real-time loading with a response time suited to control | Data access, response time |
| Site meter | Modbus | Total site import | Accuracy |
| Optional battery | Modbus | Setpoint control | Space, fire safety |

### 7.4 Data and privacy

- Session data may identify drivers or vehicles. Pseudonymise before sharing.
- No payment data in the Programme dataset.
- Privacy notice displayed to charger users.
- Commercial charging revenue stays with the site operator.

### 7.5 Safety and public interface

Thermal safety for fast chargers, signage, public liability cover, and a clear message on screen or signage when charging is throttled and why. Drivers can raise complaints through the site channel.

### 7.6 Acceptance tests (Pilot C)

| # | Test | Pass criterion |
| --- | --- | --- |
| C1 | Electrical safety and protection | Signed certificate |
| C2 | Charger communication | All chargers visible, status and power limits verified |
| C3 | Limit enforcement | Total site power held at limit during a full-demand test |
| C4 | Policy behaviour | Charging shares match the agreed policy |
| C5 | Wait-time measurement | Session logs produce waiting-time statistics |
| C6 | Transformer data | Loading measured at the required rate and logged |
| C7 | Charger loss of link | Chargers drop to the configured fallback limit |
| C8 | Internet loss | Local control continues, data buffered |
| C9 | Security | Remote access disabled until Gate 3, credentials changed |
| C10 | Privacy | Notice displayed, no payment data in the dataset |

## 8. Compatibility and procurement requirements

| Requirement | Detail |
| --- | --- |
| Pre-award testing | Every shortlisted inverter, battery, meter and charger is tested against OpenEMS in a lab or sandbox before award (Gate 2 evidence) |
| Driver status | For each device record: existing driver (yes or no), version tested, custom driver effort, owner |
| Vendor commitments | Published register maps or protocol documents, written permission for third-party control under warranty, local service response time, spares |
| Tender scoring | Technical compliance and compatibility, local service, price, delivery. Compatibility failure disqualifies |
| Warranty | Control by OpenEMS must not void equipment warranty. Confirm in writing |
| Licensing | Custom drivers and configuration under Apache 2.0, offered upstream where appropriate. OpenEMS components keep their own licences |

## 9. Commissioning and handover

1. Factory or lab acceptance of Edge hardware and configuration.
2. Installation by licensed contractors to the approved design and safety plan.
3. Site acceptance tests in Sections 5.5, 6.7 and 7.6, witnessed by the Site Lead, host representative and, where agreed, Kenya Power and EPRA.
4. Baselines recorded and meter accuracy checks completed.
5. Operator training with competence assessment.
6. Commissioning certificate signed. Gate 3 requires commissioning certificates, a passed cybersecurity audit, baselines recorded and trained operators.
7. Configuration baseline stored under version control (C4) with a change log (D5).

## 10. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Confirm 250 kWh against the 300 kWh Charter reference site, using measured load | Pilot A sizing | Technical Lead |
| 2 | Tariff structure: ToU spread and demand charges at the Pilot A candidates | Pilot A economics | Techno-economic analyst |
| 3 | Inverter, battery and charger compatibility results and driver effort | All pilots | Technical Lead |
| 4 | EPRA position on BESS, mini-grid and charging station licensing, and net-metering terms | All pilots | Programme Director |
| 5 | Kenya Power interconnection requirements, transformer data access and response time | A, C, and B if grid-connected | Technical Lead |
| 6 | Pilot B topology (grid-connected, mini-grid or isolated) and loss measurement method | Pilot B | Technical Lead and Research Lead |
| 7 | Pilot C site limit, charging policy and maximum wait time | Pilot C | Technical Lead and Site Lead |
| 8 | Battery and charger safety standards, fire protection design and insurer acceptance | Gate 2 | Site Leads |
| 9 | Budget reconciliation between site costs and the programme envelope | Gate 1 | Programme Manager |
| 10 | Equipment title and decommissioning responsibility | Before procurement | Programme Sponsor |

## 11. Traceability

| Source | How it is used |
| --- | --- |
| Programme Charter | Configurations, scope, gates, change control |
| Feasibility Study (D1) | Fit by pilot, risks, open questions, break-even logic |
| Site Survey Reports | Data to be collected to confirm this specification |
| MoU and Site Agreement templates | Control authority, remote access, data and safety clauses |
| Stakeholder Engagement Plan | Community and host conditions for Pilots B and C |

On completion of the site surveys, each section marked with a bracketed value is updated and the document is re-issued as version 1.0 for Gate 1.

# Cybersecurity Plan


## 1. Purpose and bottom line

The Charter makes cybersecurity of remotely connected assets a top risk and sets one hard rule: **no site connects remotely until it has passed an independent security audit (Gate 3).** This plan turns that rule into an engineering and governance baseline. It defines what is being protected, from whom, with which controls, how the audit will work, and what happens when something goes wrong.

**Bottom line.** OpenEMS is open source, so its code is public. Security therefore rests on **configuration, patching, access control, network design and operating discipline**, not on obscurity. The programme's design answers this in five ways:

1. **Local first.** All control and protection decisions run on site. The internet is never in a control or protection loop, and Edge keeps working offline.
2. **No inbound path.** Remote access is disabled until Gate 3. Afterwards it is outbound-only, encrypted and multi-factor protected, with no open inbound ports.
3. **Hardware protects, OpenEMS supervises.** Battery management systems, inverter anti-islanding, breakers and fire detection act independently of OpenEMS. A compromised or misbehaving Edge must not be able to push a battery or charger outside its safe limits.
4. **Behind the connection point only.** OpenEMS never controls Kenya Power assets (draft MoU Schedule 1B), which limits the grid-level consequence of any compromise.
5. **Audit before go-live, with a hard stop.** Critical findings block go-live.

**What cannot be settled from desk research.** The real attack surface depends on the devices bought, the OpenEMS release pinned, and each host's network. This plan therefore sets requirements and tests, and the compatibility register (B6) and audit supply the evidence.

## 2. Document control and relationships

**Owner:** Cybersecurity and Data Protection Officer (README B7: "Cybersecurity lead"). **Contributors:** Technical Lead, software engineer, site engineers, Kenya Power ICT and grid engineer (TWG), Research Lead (data integrity), university partner. **Approval:** Programme Director at Gate 1, then frozen as the Gate 2 baseline. Reviewed fortnightly in the TWG during build, monthly in operation. Changes follow Charter Section 20 change control.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 10, 18, 19) | Source of the audit-before-remote-connection rule, incident ownership and notification routes |
| Technical Specification per Site (B4, Section 3.5) | Sets the network and cybersecurity baseline this plan expands |
| Interoperability and Device Compatibility Register (B6) | Receives device security findings; tests T-COM-08, T-EVC-09 and T-NET-01 to 03 feed this plan |
| Regulatory Compliance Assessment (B5, Sections 5.6, 5.7) | Data protection duties, breach notification, open counsel questions |
| MoU and Site Agreement templates | Binding clauses on cybersecurity (MoU Section 8, Site Agreement Sections 6.4 and 10) |
| Data management and privacy plan (D2) | Retention, access and anonymisation rules this plan implements technically |
| Procurement plan (C1) | Uses Appendix A as the security gate in tenders |
| Site acceptance tests (C5) and configuration baseline (C4) | Re-verify and freeze the controls here |

## 3. Security objectives and principles

**Objectives, in priority order.**

| # | Objective | Why it matters here |
| --- | --- | --- |
| S1 | **Safety.** No cyber event can cause an unsafe battery, charger or electrical state | Battery fire and thermal risk is rated low likelihood, high impact (Feasibility Study risk 9) |
| S2 | **Availability and local control.** Sites keep operating and controlling during internet or cloud loss | Required by the Charter and tested at commissioning |
| S3 | **Integrity.** Setpoints, configuration and measurement data cannot be altered without detection | The evaluation depends on trustworthy data and an unaltered baseline |
| S4 | **Confidentiality.** Personal and commercially sensitive data stays protected | Household data (B), driver data (C), production and tariff data (A) |
| S5 | **Trust.** Incidents are handled openly with partners and do not undermine regulators' or communities' confidence | Stakeholder Engagement Plan risk on data or security incidents |

**Principles** (extend Charter Section 12 and B4 Section 3.2):

- **Defence in depth.** No single control is relied on. Network, device, application, physical and process controls overlap.
- **Least privilege and least connectivity.** Every account, device and network path has only what it needs.
- **Secure by default.** Defaults are changed or disabled before commissioning. A device that cannot be secured is a disqualifier.
- **Open and honest.** Security design and non-sensitive findings are published. Sensitive details (credentials, network maps, unpatched vulnerabilities) are withheld until fixed, per the security and privacy review before publication.
- **Proportionate.** Controls scale with risk. A 250 kWh battery site and a school-adjacent village microgrid warrant different physical measures but the same logical baseline.
- **Assume breach.** Design so that a compromised component cannot cascade to safety, other sites or host networks.

## 4. Scope and assets

### 4.1 In scope

All OpenEMS Edge instances, field devices (inverters, battery systems and BMS, meters, EV chargers, generator controllers), site networking, the optional OpenEMS Backend and any cloud or hosted component, programme repositories and build systems, the data logger and research meters, laptops and accounts used by programme staff and contractors, and the remote access path after Gate 3.

### 4.2 Out of scope

Kenya Power's own networks and systems (the programme only exchanges data with them), host IT and operational technology beyond the interface to the programme network, and transmission-level systems. Host IT is treated as **untrusted** from the programme network's point of view.

### 4.3 Asset inventory (by layer)

| Layer | Assets | Criticality | Main concern |
| --- | --- | --- | --- |
| Control | Edge computer, OpenEMS configuration, controller parameters | High | Integrity and availability |
| Field | Battery inverter and BMS, PV inverters, chargers, generator controller | High (safety) | Unsafe commands, firmware tampering |
| Measurement | Grid, battery and transformer meters, research logger, time source | High (evaluation) | Data integrity, baseline integrity |
| Network | Router, firewall, switch, mobile or satellite links, VPN endpoints | High | Segmentation, access path |
| Application | OpenEMS UI, Backend (optional), cloud storage, dashboards | Medium to high | Account takeover, data exposure |
| Data | Load profiles, tariffs, household consumption, charger sessions, utility data | Medium to high | Privacy, commercial sensitivity |
| Development | Repository, CI, dependencies, custom drivers, signing keys, Edge images | High | Supply-chain compromise |
| People | Operators, site staff, contractors, vendors | High | Social engineering, error, insider |

The register of record is held by the Cybersecurity and Data Protection Officer and updated at each survey, commissioning and change.

## 5. Threat model

### 5.1 Trust boundaries

1. Field devices and Edge (site control network).
2. Site control network and host IT/OT.
3. Site and the internet (post Gate 3 only, outbound-only).
4. Site and Kenya Power data interface (read-only unless agreed in a technical annex).
5. Programme staff, contractors and vendors and the systems they can reach.
6. The public (EV drivers at Pilot C, community at Pilot B) and physical access to equipment.

### 5.2 Threat actors

| Actor | Motivation | Plausible capability |
| --- | --- | --- |
| Opportunistic internet attacker or botnet | Scanning for exposed devices, ransomware, resource abuse | Automated, wide, low skill |
| Targeted attacker | Disruption of a high-profile renewable pilot, hacktivism, interest in utility data | Moderate to high |
| Insider or contractor | Error, grievance, financial gain, theft | Legitimate access |
| Malicious or careless vendor | Insecure firmware, backdoors, unannounced updates | Privileged device access |
| Local thief or vandal | Equipment theft, copper and battery theft (Pilot B) | Physical access |
| Dissatisfied driver or customer | Tampering with chargers or throttling | Public physical access (Pilot C) |
| Researcher or curious third party | Probing public code and published designs | Technical, usually benign |

### 5.3 Threat register

Ratings are initial judgements (likelihood L, impact I: H, M, L) for validation in the live risk register and the audit.

| # | Threat | Pilots | L | I | Primary controls (section) |
| --- | --- | --- | --- | --- | --- |
| T1 | Remote takeover of Edge or Backend leading to harmful setpoints | A, B, C | L | H | No remote access before Gate 3; MFA; outbound-only; setpoint limits in hardware (6.2, 6.3, 9) |
| T2 | Compromised or insecure device firmware or default credentials | A, B, C | M | H | Vendor commitments; credential removal; firmware policy; segmentation (6.4, 6.9) |
| T3 | Lateral movement from host IT into the control network, or the reverse | A | M | M | Separate network, firewall, no path from host IT (6.2) |
| T4 | Ransomware or malware on Edge, Backend or staff laptops | A, B, C | M | M | Hardening, backups, offline recovery, endpoint hygiene (6.7, 6.8) |
| T5 | Tampering with meters, logs or baseline configuration to distort results | A, B, C | L | H | Independent research logger, signed logs, change control (6.6, 7) |
| T6 | Manipulation of charger limits, fallback behaviour or session data | C | M | M | OCPP security where supported, authenticated limits, fallback tests (7.3) |
| T7 | Theft or physical tampering with Edge, cabinets or batteries | B, A, C | H (B) | M | Locked enclosures, tamper evidence, siting (6.5, 7.2) |
| T8 | Personal data exposure (household consumption, driver sessions) | B, C | M | H | Minimisation, pseudonymisation, access roles, retention (6.10) |
| T9 | Supply-chain compromise of dependencies, drivers, build tools or images | All | L | H | Pinned versions, review, SBOM, signed artefacts (6.9) |
| T10 | Loss of Edge power or data corruption during outage | A, B, C | M | M | UPS or supercapacitor, clean shutdown, buffered logs (6.7) |
| T11 | Connectivity failover abused or misconfigured (second SIM, satellite) | B | M | M | Same outbound-only design on all links; no public IP (6.2) |
| T12 | Weak operator practice: shared passwords, unlogged overrides, unpatched systems | All | H | M | Named accounts, training, logged changes, drills (6.1, 6.6, 11) |
| T13 | Vendor or integrator leaves a persistent remote maintenance path | A, B, C | M | H | Contract clause, audit check, commissioning handover checklist (6.4, 8) |
| T14 | AGPL or licence non-compliance exposing code or creating disputes | All | L | L | Licence compliance register (6.9) |

**Note on grid impact.** Because OpenEMS acts only behind the customer connection, the realistic worst cases are site-level: unsafe battery operation, charger disruption, loss of site supply or data. A coordinated attack on many sites is unlikely at three sites, but a shared Backend or shared credentials would create exactly that correlation, which is why shared secrets are prohibited (6.1).

## 6. Security architecture and controls

### 6.1 Identity and access management

| Control | Requirement |
| --- | --- |
| Named accounts | Individual accounts only. No shared logins. Contractor accounts are time-limited and removed at handover |
| Roles | At minimum: viewer (host), operator (local), engineer (programme), administrator (Technical Lead delegates), auditor (read-only). Roles per site agreement Schedule 6 |
| Authentication | Strong, unique passwords or keys for all accounts. Multi-factor authentication for any remote access and any administrator access to Backend or cloud |
| Secrets | Held outside the repository in a secrets manager or equivalent. Unique per site, never reused between sites. Rotation at commissioning, on staff change and on any suspected exposure |
| Default credentials | Removed or neutralised on every device before commissioning (acceptance test B8, C9, T-COM-08) |
| Privileged access | Administrator actions logged. Break-glass credentials sealed, stored offline, use triggers an incident review |
| Joiners and leavers | Access granted and removed through the PMO checklist within [1] working day of change |
| Host access | Hosts see their own site data through the OpenEMS UI only (Site Agreement 9.4). No host administrator rights on Edge or devices |

### 6.2 Network security

| Control | Requirement |
| --- | --- |
| Zones | Zone 1: field devices and Edge (control). Zone 2: research logger and meters (measurement, one-way to evaluation). Zone 3: management and remote access, post Gate 3. Host IT/OT is outside all three zones |
| Segmentation | Dedicated physical or VLAN-separated network for Programme devices behind a firewall. No route from host IT into Zone 1 |
| Default deny | Firewall rules default deny inbound and outbound, with allow-lists for named destinations and ports |
| Remote access (pre-Gate 3) | **Disabled.** No VPN, tunnels, cloud sync or remote support tools active. Local data collection only |
| Remote access (post-Gate 3) | Outbound-only encrypted tunnel or VPN initiated from site, with multi-factor authentication. No open inbound ports and no public IP on any programme device. Remote sessions are time-bound and logged |
| Cellular and satellite links | Private APN or equivalent where available [confirm]. Same outbound-only rule as other links. Failover tested (T-NET-03) |
| Wireless | Wi-Fi disabled on programme devices unless needed and then WPA3 or WPA2-Enterprise equivalent, separate SSID, never shared with guests or staff |
| Time | Authenticated or trusted time source distributed to all loggers. Time drift alarmed because it affects data integrity |
| Utility interface | Kenya Power data flows are read-only unless a separate technical annex says otherwise (MoU Schedule 1B). Interface via defined gateway, not a direct route into Zone 1 |
| Scanning | Network scan before commissioning and after any change to confirm no unexpected open ports or services |

### 6.3 Setpoint integrity and safe operation

This section is where cyber and safety meet. OpenEMS is a supervisory layer, not a protection device (B4 design rule 4).

| Control | Requirement |
| --- | --- |
| Hardware limits win | BMS, inverter and charger limits cannot be exceeded by any setpoint (B6 pass criterion). Tested with out-of-range commands (T-COM-07) |
| Plausibility limits in configuration | Edge enforces maximum power, ramp rate, SoC window and rate of change on every setpoint, set per site in Schedule 3 [values to be set from the sizing method] |
| Safe state on loss | Defined per device and per site: battery to idle or minimum export, chargers to configured fallback limit, generator under its own controls (T-COM-05, T-BAT-09, T-EVC-07) |
| Configuration integrity | Edge configuration under version control, with a hash or signature checked at start and on a schedule. Unauthorised change raises an alarm |
| Logged overrides | All overrides recorded with time, person and reason (B4 design rule 5) |
| No remote safety edits | Safe states and plausibility limits cannot be changed remotely. Changing them needs on-site action or a two-person approved change after Gate 3 [decide with TWG] |
| Independent alarms | Fire detection, BMS alarms and breaker trips are hardwired or independent of OpenEMS and the network |

### 6.4 Device and firmware hardening

| Control | Requirement |
| --- | --- |
| Hardening baseline | Per device class, record unused services disabled, management interfaces restricted to Zone 1 or Zone 3, default accounts removed, and logging enabled where supported. Stored in the configuration baseline (C4) |
| Firmware policy | Version pinned and held. Updates only through the logged change process, tested off site first, with a rollback plan. Automatic vendor updates disabled where possible, otherwise vendor must notify in advance (B6 Section 9) |
| Vendor remote access | Prohibited unless specified in the contract with named conditions: time-bound, approved by the Cybersecurity Officer, logged. Any permanent vendor path is an automatic disqualifier or must be physically disabled |
| Edge computer | Industrial rating, watchdog, clean shutdown, secure boot or equivalent hardening where available, disk encryption where practical [confirm for remote sites], minimal installed software, unused ports and services disabled |
| Chargers | OCPP security profile with authenticated, encrypted connection where the charger and version support it [confirm per model]. Otherwise compensating controls (network isolation, private link) are mandatory and the gap is recorded as an accepted risk by the Cybersecurity Officer |
| Meters | Write access to configuration disabled or protected. Calibration seals intact. Meter configuration changes logged |
| Automatic disqualifiers | Hard-coded credentials that cannot be removed or isolated; no documented protocol; vendor refuses written confirmation on remote access and updates (B6 Section 4) |

### 6.5 Physical security

| Control | Requirement |
| --- | --- |
| Enclosures | Lockable, ingress-rated, surge-protected cabinets for Edge, network and meters. Keys controlled and logged |
| Tamper evidence | Seals on cabinets and meter terminals. Door or intrusion sensor reported to Edge where feasible |
| Ports | Unused USB, serial and Ethernet ports disabled or blocked |
| Battery room or container | Restricted access, signage, lock-out procedures. Fire and security siting per B4 Section 3.6 |
| Pilot B | Added protection against theft and vandalism, lightning, flood, dust, heat and wildlife (B4 6.5). Local operator and trained backup. Community engagement is part of physical security |
| Pilot C | Public-facing equipment designed for vandal resistance. Customer-accessible ports and screens separated from the control network |
| Visitors and contractors | Escorted, signed in, inducted on site safety and security |

### 6.6 Logging, monitoring and integrity of evidence

| Control | Requirement |
| --- | --- |
| Events logged | Logins and failures, privilege changes, configuration changes, firmware and driver changes, setpoint rejects and clamps, device loss, overrides, remote sessions, alarms |
| Local storage | Logs stored on Edge and forwarded to the research logger or Backend where permitted. Local buffer at least [30] days (B4 Section 3.4) |
| Tamper resistance | Logs append-only or hashed in chunks. Copies held off the Edge where possible |
| Monitoring | Monthly review in operation by the Cybersecurity Officer. Automated alarms for failed logins, unexpected outbound connections, configuration hash mismatch, time drift, data gaps above threshold |
| Evidence for the evaluation | Meter readings, configuration and control mode changes are time-stamped and traceable so the Research and Evaluation Panel can show the baseline was not altered. No re-baselining without Panel approval (Charter risk 8) |
| Retention | Security log retention [period set in the data plan]. Incident records kept for [3] years or as the data plan requires |

### 6.7 Resilience, backup and recovery

| Control | Requirement |
| --- | --- |
| Offline operation | Control continues during internet loss. Tested [24] hours (A, C) and [72] hours (B) (B4 acceptance tests A6, B5, C8) |
| Power loss | UPS or supercapacitor-backed clean shutdown. Abrupt power loss test (T-EDG-02) |
| Backups | Edge configuration, driver versions and device settings backed up after each approved change, stored offline and off site. Restore tested at commissioning and at Gate 4 |
| Spare Edge | Pre-configured spare at or near each site, or a documented rebuild from the signed image within [x] hours |
| Recovery objectives | Target restore of control within [x] hours of Edge failure. Data loss tolerance defined by local buffer length |
| Ransomware stance | No inbound path, no shared domain with host IT, offline backups, no payment policy decided by Steering Committee in advance [proposal: no payment, escalate to Programme Director] |

### 6.8 Staff and contractor endpoints

Programme laptops used for site access use full-disk encryption, supported operating systems with automatic updates, screen lock, endpoint protection and no local administrator rights for daily use. No programme work on personal or shared devices. Access keys and tokens are never stored in chat tools or email. Removable media is scanned before use at a site.

### 6.9 Supply chain, development and open-source governance

| Control | Requirement |
| --- | --- |
| Pinned versions | OpenEMS release, Edge OS image and dependencies pinned per B6 Section 10.1. Upgrades follow delta testing rules (B6 10.3) |
| Source and provenance | OpenEMS and dependencies obtained from official sources and verified (checksums or signatures) before use |
| Software bill of materials | SBOM generated for the production Edge image and each custom driver, stored with the configuration baseline |
| Vulnerability watch | Technical Lead's team monitors OpenEMS and dependency advisories and vendor notices, assesses relevance within [5] working days and records the decision. Critical issues trigger an out-of-cycle patch review |
| Custom drivers | Developed in the open under Apache 2.0, with code review by a second engineer, input validation on all device data, no hard-coded secrets, unit tests, and TWG review before use. Offered upstream after review (Charter Section 21) |
| Repository security | Branch protection, signed commits or tags for releases, two-factor authentication for maintainers, secret scanning |
| Build and release | Reproducible, logged builds. Production images signed or checksummed and verified on installation |
| Licence compliance | Licence register kept by the Technical Lead, including AGPL 3.0 network-use duties for any modified UI served over a network. Counsel to confirm the licence mix (B5 open question 10) |
| Vendors and installers | Security clauses in tenders and contracts: documentation, default credential policy, vulnerability disclosure contact, no undocumented remote access, notification of firmware changes. Security questionnaire in Appendix A |
| Public code, private operations | Published repositories contain no secrets, network diagrams of live sites or site-specific credentials. Pre-release scan by the Cybersecurity Officer |

### 6.10 Data protection and privacy controls

These controls implement B5 Section 5.6 and the data management plan (D2).

| Control | Requirement |
| --- | --- |
| Minimisation | Collect only what the KPIs and baselines need. No payment data in the Programme dataset. No driver identity unless a lawful basis and notice exist (Site Agreement 9.2) |
| Pseudonymisation | Charger sessions and household data are pseudonymised at source on the Edge or logger before leaving the site, with keys held separately by the Cybersecurity Officer |
| Aggregation | Customer-level data anonymised or aggregated before publication. Small-group re-identification risk checked before release (for example few customers on one transformer) |
| Access roles | Role-based access in Schedule 6 of each site agreement. Utility, university and regulator access defined by data sharing agreements |
| Encryption | Data encrypted in transit on every link outside Zone 1. At rest on Backend, cloud and laptops. Encryption on Edge where practical |
| Location and transfer | Backend or cloud hosted in Kenya or under a transfer basis confirmed by counsel [confirm]. Hosting by the Ministry of Energy is an option under a separate hosting and data agreement |
| Roles | Controller, joint controller or processor roles agreed in writing before any sharing (MoU 7.2). ODPC registration and impact assessment confirmed with counsel |
| Breach handling | Notify the PMO within [48] hours of awareness (MoU 7.4), then meet statutory notification duties to the Office of the Data Protection Commissioner and Kenya Power as applicable |
| Retention and deletion | Per data plan. Deletion or return of data at closure per host agreement Section 16.3 and Schedule 6 |

## 7. Pilot-specific security requirements

### 7.1 Pilot A: Industrial park, hub or campus

| Issue | Requirement |
| --- | --- |
| Host IT/OT adjacency | Treat host network as untrusted. Firewall between host IT and Programme network. No programme device joins the host domain |
| Existing PV inverters | Check for open management interfaces, shared credentials and warranty conditions. If an inverter cannot be isolated or secured, record as a red item at survey (B3 A3) |
| Host IT policy | Obtain and record the host's remote access and third-party device policy (Site Survey A7). Conflicts are resolved before Gate 1 |
| Confidentiality | Production schedules and tariff terms confidential by default (Site Agreement Pilot A). Access and storage controls match this |
| Battery room | Fire detection and access control per B4 5.4. Insurer acceptance recorded |

### 7.2 Pilot B: Rural microgrid

| Issue | Requirement |
| --- | --- |
| Connectivity | Edge autonomy proven at commissioning. Second SIM or satellite fallback where survey shows weak coverage. Outbound-only on all links |
| Physical exposure | Highest theft and tamper risk. Cabinets hardened, equipment tracked, siting reviewed with the community |
| Operators | Named local operator and trained backup. No shared admin credentials, even though operators are few and the site is remote |
| Household data | Pseudonymise and aggregate. Consent and notice at community meetings. Data volumes minimised |
| Generator interface | Relay or gateway links reviewed for safe behaviour on loss of communication. Generator keeps its own protection |
| Support | Remote support only after Gate 3 and only through the approved tunnel. Otherwise on-site visits, with spares and response time in the vendor commitments |

### 7.3 Pilot C: EV charging site

| Issue | Requirement |
| --- | --- |
| Public exposure | Charger physical ports, screens and payment hardware separated from the control network. Vandal and tamper resistance |
| OCPP | Required OCPP version and security profile fixed in the tender (B6 open item 3). Authenticated limit commands. Charger cannot be driven past its rated limit by any command |
| Fallback | Chargers drop to the configured fallback limit on loss of link (T-EVC-07), so a communications attack cannot raise load on the transformer |
| Transformer protection | Site limit enforced locally on Edge. Transformer meter data path from Kenya Power is read-only. Loss of that feed triggers a conservative site limit [value with Kenya Power] |
| Vendor cooperation | Vendor named contact, firmware policy and vulnerability disclosure contact in the site agreement special conditions |
| Driver data | Session data pseudonymised on site. No payment data. Privacy notice displayed (Site Agreement 9.2) |
| Fraud and abuse | Check for tariff, authorisation and session-manipulation abuse in the charger back office. Programme does not integrate with payment systems |

## 8. Security roadmap by stage gate

| Gate | Timing | Security deliverables and evidence |
| --- | --- | --- |
| Gate 0: Mobilise | Month 0 | Cybersecurity and Data Protection Officer appointed. This plan accepted as baseline. Asset and threat register opened. Contracting entity named so data and security roles can be assigned |
| Gate 1: Design approval | Months 4 to 6 | Security architecture and site network designs per candidate site. Host IT policy recorded. Draft audit scope and auditor selection approach. Data roles agreed. Security requirements in tender drafts. At least one security-relevant L1 result for the riskiest device per pilot (B6 Section 12) |
| Gate 2: Build readiness | Month 8 | Independent security design review completed. Hardening baselines per device. Vendor security commitments received. Production versions and SBOM frozen. Auditor appointed and independent of vendors and integrators. Data sharing agreements signed. Incident response plan approved and contact lists verified |
| Build and commissioning | Months 7 to 12 | Hardening applied. Default credentials removed. Network scans clean. Offline operation, safe state and restore tested. Operators trained on security procedures. Local data collection only. **Remote access remains disabled** |
| Gate 3: Go-live | Month 12 | **Independent security audit passed** with no open critical findings. Remote access design verified. Commissioning certificates. Baselines recorded. Incident exercise completed. ODPC and breach processes in place. Only then is remote connection authorised |
| Gate 4: Mid-operation | Month 18 | Security log and incident summary. Patch and firmware change review. Access review. Restore test repeated. Retest of any accepted risks |
| Gate 5: Closure | Month 24 | Final security report with lessons learned (negative findings included). Credentials revoked or handed over. Data retained or deleted per agreements. Custodians named for security duties after the pilot. Decommissioning and secure erase of devices |

## 9. Independent security audit

The audit is the formal gate for remote connection. It is independent of the people who designed, built and installed the system.

### 9.1 Auditor independence and selection

- No commercial relationship with the programme's vendors, integrators or the Technical Lead's organisation in the past [24] months, disclosed under the conflict-of-interest rules (MoU Section 13).
- Demonstrated experience with industrial control systems, energy or battery systems and web application testing. Local presence or knowledge of Kenyan conditions preferred.
- Terms of reference approved by the Programme Director on advice of the TWG and the Research and Evaluation Panel (for data integrity). Kenya Power ICT consulted on scope.
- Budget line: KSh [X] (not yet itemised; flagged under the budget reconciliation issue in Feasibility Study 5.1).

### 9.2 Audit scope

| Area | Examples of what is examined |
| --- | --- |
| Architecture and design | Zones, firewall rules, remote access design, absence of inbound paths, Backend and cloud design, data flows |
| Configuration review | Edge, devices, router and firewall, accounts and roles, logging, backups |
| Technical testing | Network and port scans from each zone, credential and default-account checks, interface and web application testing on the OpenEMS UI and Backend, charger and inverter management interfaces, firmware and update paths |
| Control and safety integrity | Out-of-range setpoint handling, safe state on loss, configuration integrity alarms, override logging |
| Physical and procedural | Cabinet and battery-room access, key control, operator procedures, joiner and leaver process |
| Supply chain and development | Repository settings, release signing, SBOM, dependency review, custom driver code review |
| Data protection | Pseudonymisation, access roles, retention, transfer arrangements, breach process |
| Remote access path | Tunnel design, MFA, session logging, behaviour on link loss, no residual vendor access |

Testing that could affect safety (for example fuzzing a live battery inverter) is performed in the lab or on a de-energised or isolated system, under a written safety plan with a licensed electrician present. Live-site testing of control paths is limited to agreed non-hazardous scenarios.

### 9.3 Severity and go-live rules

| Severity | Definition | Rule |
| --- | --- | --- |
| Critical | Can lead to unsafe equipment state, remote unauthorised control, loss of local control, or exposure of personal data at scale | **Blocks go-live.** Fix and retest before Gate 3 |
| High | Serious weakness exploitable with moderate effort, with limited safety impact | Fix before go-live, or SteerCo-approved compensating control with a dated retest |
| Medium | Weakness needing specific conditions or limited impact | Fix within [90] days or accept with owner and date |
| Low and informational | Hardening and good-practice items | Track in the backlog |

The auditor reports to the Programme Director and the SteerCo. The Cybersecurity Officer owns remediation tracking. The auditor retests every critical and high finding. The final report is shared with Kenya Power ICT and, in a redacted form after the security and privacy review, published with equal prominence for negative findings (Charter Section 21).

### 9.4 Ongoing assurance

A lighter review is held before Gate 4 and again before closure. A new audit or targeted retest is required after any major change: a new remote access path, a new device class, a major OpenEMS upgrade, or a significant incident.

## 10. Incident response

### 10.1 Roles

| Role | Responsibility |
| --- | --- |
| Incident owner | Cybersecurity and Data Protection Officer. Declares and coordinates the incident |
| Incident commander (safety cases) | Site Lead on site, with authority to isolate equipment for safety |
| Technical responder | Technical Lead or delegate. Containment, forensics, recovery |
| Communications | Programme Director for regulators, Kenya Power, funders and media. Site Lead for host and community |
| Legal and data protection | Counsel and the Officer. Statutory notifications |
| Deputy | Named alternate for each role, with 24-hour reachability for [Gate 3 onwards] |

### 10.2 Severity and response targets (proposals for approval)

| Level | Examples | Initial response | Escalation |
| --- | --- | --- | --- |
| S1 Critical | Unsafe equipment behaviour, confirmed unauthorised control, serious personal data breach, fire or injury | Immediate safe state and isolation. Respond within [1] hour | PMO, Programme Director and Kenya Power within [4] hours. SteerCo Chair informed. Insurer as required |
| S2 High | Confirmed compromise of an Edge or account without safety impact, ransomware on a laptop, vendor remote access found | Contain within [4] hours | Programme Director same day |
| S3 Medium | Suspicious activity, failed intrusion attempt, firmware tamper alarm | Investigate within [1] working day | PMO at next review |
| S4 Low | Policy breach, lost non-sensitive device, minor misconfiguration | Within [3] working days | Logged and reviewed monthly |

### 10.3 Notification routes

| Recipient | When | Source |
| --- | --- | --- |
| PMO | Any personal data breach within [48] hours of awareness. All S1 to S3 incidents without delay | MoU 7.4 |
| Kenya Power | Cyber incidents and grid-affecting events at pilot sites | Charter Section 19, MoU Schedule 1B |
| EPRA | Where licensing, a sandbox or exemption conditions, or regulation require | Charter Section 19, MoU Schedule 1A |
| Office of the Data Protection Commissioner | Personal data breaches meeting the statutory threshold, within statutory time [confirm with counsel] | Data Protection Act, 2019 |
| Affected individuals | Where the law or the risk requires, in plain language and Kiswahili where relevant | B5 5.6, Stakeholder Engagement Plan |
| Insurer | As the policy requires | Site Agreement Section 13 |
| Steering Committee | S1 immediately, S2 within [2] working days, all in the quarterly report | Charter Section 15 |
| Law enforcement | Where criminal activity is suspected, through the Programme Director and counsel [confirm Kenyan reporting route] | Counsel |
| Vendor or OpenEMS community | For vulnerabilities in their product, through responsible disclosure and after mitigation | Section 6.9 |

### 10.4 Response phases

1. **Detect and report.** Anyone can report. Contact details are on every cabinet and in the operator manual (D3).
2. **Triage.** The incident owner assigns a level within the targets above.
3. **Contain.** Isolate the affected zone. For any safety-relevant event, put equipment in its safe state first. Preserve logs and images before wiping.
4. **Eradicate and recover.** Rebuild from the signed image and known-good configuration backup. Rotate credentials. Retest before resuming remote access or control.
5. **Notify.** Follow Section 10.3.
6. **Review.** Blameless post-incident review within [10] working days. Update controls, risk register and this plan. Share lessons with partners and publish a sanitised summary where useful.

### 10.5 Playbooks to prepare before Gate 3

| Playbook | Core steps |
| --- | --- |
| Suspected remote compromise of an Edge | Disconnect uplink. Confirm local control and safe state. Capture disk image and logs. Rebuild. Rotate secrets for that site and any shared ones. Review other sites |
| Unsafe or unexpected battery or charger behaviour | Local manual isolation and emergency procedure. Confirm hardware protection acted. Notify Site Lead and Kenya Power. Preserve evidence. Do not resume until root cause is known |
| Personal data breach | Contain access. Assess scope and risk. Notify PMO within [48] hours. Counsel and Officer decide statutory notice. Inform affected people if required |
| Ransomware or malware on staff devices or Backend | Isolate device. Revoke tokens. Restore from offline backup. No payment per pre-agreed stance |
| Vendor or installer remote path discovered | Disable physically or by firewall. Record. Require written explanation and remediation. Consider substitution under B6 rules |
| Loss or theft of equipment (Pilot B especially) | Report to police and Site Lead. Remotely revoke the device's credentials if connected. Check for stored secrets. Replace from spares |
| Compromised repository or release | Freeze releases. Rotate maintainer keys. Verify image hashes in the field. Notify upstream community if relevant |

### 10.6 Exercises

A tabletop exercise before Gate 3 (all roles, including Kenya Power and a site host), a technical drill at each site at commissioning (isolate, restore, recover), and a repeat at Gate 4. Results go into the lessons-learned reviews held at Gates 3 and 5.

## 11. People, training and culture

- **Operator training** (D4) includes: named accounts and password handling, recognising phishing and social engineering, safe use of USB and laptops at site, what to do if a device behaves unexpectedly, the override and logging rule, and the incident contact process. Training is assessed and tracked with the Charter training KPI.
- **Contractor induction** covers site safety and security rules, no undocumented remote access, and no shared credentials.
- **Local ownership.** The programme-level success criterion of a trained local team able to operate OpenEMS without continuous foreign support includes the ability to patch, back up, respond to incidents and rotate credentials.
- **Retention risk.** Loss of trained staff is a stakeholder-plan risk. Security knowledge is documented in the operations and maintenance manual (D3) and refreshed at least [annually].
- **Culture.** Reporting a mistake is encouraged and not penalised. This mirrors the non-retaliation principle in the grievance mechanism.

## 12. Governance, reporting and measures

### 12.1 Responsibilities

| Body or role | Security responsibility |
| --- | --- |
| Steering Committee | Approves this plan at Gate 1, the Gate 3 go-live decision, and any accepted high risks. Receives quarterly security reporting |
| Programme Director | Accountable for audit sign-off (Charter RACI) and regulator and Kenya Power notifications |
| Cybersecurity and Data Protection Officer | Owns this plan, controls, audit scope, monitoring, incident process and data-handling compliance |
| Technical Lead and TWG | Implement controls, run device tests, maintain the configuration baseline, drivers and patching. Kenya Power grid engineer advises on utility interfaces |
| Research Lead and Panel | Data integrity requirements and baseline protection |
| PMO | Tracks actions, risks, incidents and budget. Includes security items in the monthly dashboard |
| Site Leads | Physical security, access control, local incident first response |
| Host representatives | Follow host obligations in Site Agreement Section 10 and report suspected breaches |
| Vendors and installers | Meet contract security clauses and cooperate with testing and audit |

### 12.2 Reporting

Security items appear on the monthly programme dashboard (security incidents are already a Charter dashboard item) and in quarterly SteerCo reports. Open critical and high findings, incidents, patch status and training progress are always shown.

### 12.3 Security indicators (targets to be set at Gate 1)

| Indicator | Measure |
| --- | --- |
| Audit status | Critical findings open at Gate 3 (target: zero). High findings open or accepted, with dates |
| Hardening | Share of devices with default credentials removed and baseline applied before commissioning (target: 100%) |
| Patch and firmware currency | Time from relevant advisory to decision and, where approved, to deployment |
| Access hygiene | Share of accounts that are named and MFA-protected (remote). Joiner and leaver actions completed on time |
| Monitoring | Alarm count by type, time to triage, data-gap hours |
| Resilience | Offline operation and restore tests passed at commissioning and Gate 4 |
| Incidents | Number and severity, time to contain, time to notify, repeat causes |
| Training | Operators trained and assessed competent, retained after [12] months |
| Vendor compliance | Share of devices with written security commitments (B6 Section 9) |

## 13. Compliance and legal mapping

| Topic | Position | Action |
| --- | --- | --- |
| Data Protection Act, 2019 | Applies to household data (B), charger sessions (C) and utility customer data | Controls in 6.10. Roles, registration and impact assessment confirmed with counsel (B5 5.6) |
| Computer misuse and critical-infrastructure rules | Source documents assume no specific statute imposing duties on these installations. May be relevant | Confirm with counsel and Kenya Power ICT [confirm] |
| Sector requirements from EPRA or Kenya Power | Not yet known | Ask in the Month 1 written request (add a question on cybersecurity expectations to Appendix A of B5) |
| Cross-border transfer | Applies if a Backend or cloud sits outside Kenya | Prefer Kenya-based hosting or confirm lawful transfer basis [confirm] |
| Research approvals | NACOSTI and ethics clearance for human-related data | Via the university partner (MoU Schedule 1C) |
| Contracts | MoU Section 8 and Site Agreement Sections 6.4 and 10 already bind parties to cybersecurity duties | Check that tender and vendor contracts mirror them |
| Open-source licences | EPL 2.0 (Edge and Backend), AGPL 3.0 (UI), Apache 2.0 (programme code) | Licence register and counsel review (B5 open question 10) |
| Reference frameworks | Use as checklists, not as certification goals: ISO/IEC 27001 controls, IEC 62443 concepts for industrial and energy systems, NIST Cybersecurity Framework, OWASP guidance for web interfaces | Auditor confirms the criteria set in the terms of reference |

## 14. Risks and open items specific to this plan

### 14.1 Risks to add to the live risk register

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| C1 | Audit finds critical issues late, delaying Gate 3 and shortening the evidence period | M | H | Design review at Gate 2. Early pre-audit scan at commissioning. Reserve time between commissioning and audit | Cybersecurity Officer |
| C2 | Key local devices cannot be secured (default credentials, no OCPP security, locked firmware) | M | M | Compatibility gate, compensating network controls, substitution rule in B6 | Technical Lead |
| C3 | Insufficient local security skills to maintain controls after the pilot | M | M | Training, documented procedures, university partnership, named custodians at closure | Technical Lead |
| C4 | Security work under-budgeted (audit, tools, training, spare units) | M | M | Itemise in the budget reconciliation before Gate 1 | Programme Manager |
| C5 | Host or Kenya Power ICT policies conflict with the design | M | M | Record policies at survey. Agree exceptions in writing before Gate 1 | Cybersecurity Officer |
| C6 | Public repository or documents leak sensitive site details | L | M | Pre-release scan and review by Officer | Cybersecurity Officer |
| C7 | Remote path introduced informally by a vendor or operator for convenience | M | H | Contract clause, commissioning checklist, audit check, periodic scans | Cybersecurity Officer |

### 14.2 Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Confirm whether any Kenyan statute or EPRA or Kenya Power requirement sets cybersecurity duties for these installations | Gate 1 | Cybersecurity Officer, counsel |
| 2 | Decide Backend hosting (none, Ministry of Energy, Kenya-based cloud) and its security and data agreement | Gate 1 | Technical Lead, Programme Director |
| 3 | Set the plausibility limits and safe states per site | Gate 2 (Schedule 3) | Technical Lead |
| 4 | Fix the OCPP version and security profile in the Pilot C tender | Pilot C shortlist | Technical Lead |
| 5 | Decide whether safe-state and limit changes after Gate 3 require two-person on-site approval | Gate 2 | TWG |
| 6 | Appoint the auditor and approve the terms of reference and budget | Gate 2 | Programme Director |
| 7 | Choose the secrets management and log storage tools for low-connectivity sites | Gate 2 | Technical Lead |
| 8 | Agree response targets, on-call arrangements and notification contacts with Kenya Power | Gate 2 | Cybersecurity Officer |
| 9 | Confirm ODPC registration, impact assessment and breach thresholds with counsel | Before any data transfer | Cybersecurity Officer |
| 10 | Decide disk encryption approach for unattended Edge devices | Gate 2 | Technical Lead |
| 11 | Agree the programme position on ransomware payment | Gate 2 | Steering Committee |
| 12 | Define the process for public disclosure of security findings (what and when) | Gate 3 | Cybersecurity Officer, Research Lead |

## 15. Immediate next steps

1. Appoint the Cybersecurity and Data Protection Officer and approve this plan with the Charter at Gate 0.
2. Open the asset and threat register and merge Section 5.3 and 14.1 risks into the live Risk Register.
3. Add a cybersecurity question to the Month 1 written request to EPRA and Kenya Power.
4. Insert Appendix A requirements into the vendor questionnaire and tender drafts.
5. Record host network, remote access and IT policies in each site survey (Report A7, B4).
6. Draft the network designs and firewall rule sets per candidate site for Gate 1.
7. Draft the audit terms of reference and begin auditor selection.
8. Write the incident response plan and notification contact list, and plan the tabletop exercise.
9. Itemise security costs for the budget reconciliation.
10. Set up repository protections, secret scanning and the SBOM process.

## Appendix A: Security requirements for tenders and vendor questionnaire

These supplement the vendor questionnaire in B6 Appendix A. A "no" on a must-have is a disqualifier unless the Cybersecurity Officer approves a documented compensating control.

| # | Requirement | Must-have |
| --- | --- | --- |
| 1 | Default credentials documented and changeable or removable | Yes |
| 2 | No hard-coded or undocumented accounts, backdoors or remote maintenance paths | Yes |
| 3 | Written statement of all inbound and outbound network connections the device makes (including cloud services) and the ability to disable them | Yes |
| 4 | Remote management is optional and can be fully disabled | Yes |
| 5 | Firmware version can be held, updates are announced in advance, and images are signed or verifiable | Yes (signed images: should) |
| 6 | Vulnerability disclosure contact and a published or documented process | Yes |
| 7 | Encrypted communications supported (for example OCPP security profile, TLS for management interfaces), or documented compensating controls | Should |
| 8 | Role-based access on the device or its management interface | Should |
| 9 | Event and audit logging available locally or exportable | Should |
| 10 | Behaviour on loss of communication and out-of-range commands documented and testable | Yes |
| 11 | Cooperation with the programme's security test and the independent audit, including loan units | Yes |
| 12 | Local service route, response time and spares in Kenya | Yes |
| 13 | Secure disposal or take-back, including data erase at end of life | Yes |
| 14 | Installer personnel vetted, no shared accounts, access removed at handover, and written handover of all credentials and configuration | Yes |

## Appendix B: Commissioning security checklist (to be completed per site)

| # | Check | Evidence | Done |
| --- | --- | --- | --- |
| 1 | Asset list matches installed equipment (serial numbers) | Inventory sheet | [ ] |
| 2 | Default credentials removed on all devices | Test record | [ ] |
| 3 | Network diagram and firewall rule set match the approved design | Diagram, config export | [ ] |
| 4 | Port and service scan from each zone shows only expected items | Scan report | [ ] |
| 5 | No remote access, tunnels or cloud sync active (pre-Gate 3) | Firewall and Edge settings | [ ] |
| 6 | Hardening baseline applied per device class | C4 baseline | [ ] |
| 7 | Plausibility limits and safe states configured and tested | Acceptance test records | [ ] |
| 8 | Offline operation test passed for the required duration | A6 / B5 / C8 | [ ] |
| 9 | Configuration backup taken and restore tested | Restore record | [ ] |
| 10 | Logging and time sync verified | Log sample | [ ] |
| 11 | Cabinets locked, seals fitted, keys logged | Photo log | [ ] |
| 12 | Named accounts created, roles assigned, admin accounts MFA-ready | Account list | [ ] |
| 13 | Operators trained and assessed. Incident contacts displayed | Training record | [ ] |
| 14 | Vendor and installer access removed and credentials handed over | Handover sign-off | [ ] |
| 15 | Privacy notice displayed (Pilot C) and consent or notice recorded (Pilot B) | Photo, minutes | [ ] |

## Appendix C: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 10, 16, 18, 19, 20, 21) | Audit-before-remote rule, gates, escalation triggers, incident ownership, change control, publication governance |
| Feasibility Study (Sections 4.4, 4.5, 4.6, 9, 12.2) | Cybersecurity requirements, grid interface limits, risk ratings, Gate 1 conditions |
| Technical Specification per Site (Sections 3.1 to 3.6, 5 to 8) | Architecture, design rules, network baseline, acceptance tests, safe states |
| Interoperability and Device Compatibility Register (Sections 4, 6, 9, 11) | Device security criteria, tests, vendor commitments, escalation |
| Regulatory Compliance Assessment (Sections 5.6, 5.7, 5.11, 7) | Data protection, cybersecurity position, licence compliance, regulatory risks |
| MoU and Site Agreement templates (MoU 7, 8, 11; Site Agreement 6.4, 9, 10) | Binding security and data clauses, breach notification, remote access conditions |
| Site Survey Reports (A7, B4) | Host network, connectivity and physical security data to be collected |
| Stakeholder Engagement Plan (Sections 6.2, 6.7, 12) | Utility and community expectations, trust risk from security incidents |
| Executive Summary and Problem Statement | Cybersecurity of remotely connected assets as a principal risk |

On completion of the site surveys, compatibility testing and the Gate 2 design review, each bracketed value is updated and the document is re-issued as version 1.0 for Gate 2.

# Operations and Maintenance Manual

## 1. Purpose and bottom line

This manual tells the people who run the three pilot sites what to check, when, how to respond when something goes wrong, and who to call. It is written for local operators and their trained backups, Site Leads, site engineers and the host representative. It turns the Technical Specification (B4), the Health, Safety and Environmental Plan (C6), the Cybersecurity Plan (B7), the Configuration Baseline (C4), the Site Acceptance Test Reports (C5), the Monitoring and Evaluation Plan (D1) and the Data Management and Privacy Plan (D2) into day-to-day routines.

**Bottom line.** Operators keep the system safe, available and trustworthy as evidence. They do not tune it. Nine rules follow:

1. **Hardware protects, OpenEMS supervises.** Battery management systems, inverter protection, breakers and fire detection act on their own. If an alarm sounds, operators follow the alarm procedure. They never bypass, reset without a recorded cause, or disable a protection (B4 design rule 4).
2. **Safety first, then data, then savings.** A stop for safety is never penalised. Lost savings or lost data are acceptable. An injury or a fire is not.
3. **Operators do not edit configuration.** Controller parameters, safe states and limits change only through change control (C4 Section 10). The local UI is for viewing and for the logged override described in Section 7.
4. **The operating mode is a research decision.** Baseline mode (M1) and controlled mode (M2) switch only on the signed schedule approved by the Research and Evaluation Panel. Operators never switch mode to "see what happens" (C4 Section 6.6).
5. **Protect the evidence.** Meters, seals, the research logger and the time source are part of the evaluation. A broken seal, a moved meter or a lost data day is reported the same day.
6. **No remote path that the programme did not approve.** Remote access is disabled until Gate 3. Afterwards only the approved outbound-only, encrypted, multi-factor path is used. No vendor, installer or operator may add another (B7 Section 6.2).
7. **Write it down.** If it is not in the logbook, it did not happen. Logs are how overrides, faults and confounders reach the Panel (D1 Section 7.5).
8. **Report early, without blame.** Near misses, mistakes and suspicions are reported and never penalised (B7 Section 11).
9. **Escalate by the table, not by hope.** Section 12 gives who to call, in what order, in what time. When in doubt, escalate.

**What cannot be settled from desk research.** No site is selected, built or surveyed, and the equipment is not yet bought. Device names, alarm codes, battery chemistry, container design, inspection intervals, spare lists and travel times will change the detail. This manual fixes the structure, the minimum routines and the escalation rules, and leaves site values as placeholders to be completed from the vendor manuals, the B6 register and the commissioning records.

## 2. Document control and relationships

**Owner:** Technical Lead (README D3). **Contributors:** site engineers, Site Leads, software engineer, Cybersecurity and Data Protection Officer, Research Lead, licensed electrical contractor, vendors' local service agents, host representatives, university partner (training). **Approval:** Programme Director at Gate 2, issued per site in the handover pack at Gate 3. Reviewed monthly in the TWG during operation and after every Class 1 or 2 incident. Changes follow Charter Section 20 change control. Safety content follows the C6 change route.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 15, 16, 19, 20, 23, 24) | Gates, dashboard, safety governance, change control, closure and custodians |
| Technical Specification per Site (B4, Sections 3 to 7, 9) | Architecture, safe states, controller functions, acceptance tests, commissioning |
| Interoperability Register (B6) | Tested device and firmware set, vendor commitments, delta testing |
| Cybersecurity Plan (B7, Sections 6, 10, 11, Appendix B) | Accounts, physical security, incident response, playbooks, operator training |
| Health, Safety and Environmental Plan (C6) | Permit to work, isolation, battery and fire controls, emergency plan, waste, incident classes |
| Installation and Commissioning Plan (C3, Section 13) | Handover pack that this manual belongs to |
| Configuration Baseline (C4) | Frozen configuration, change classes, backup and restore, drift alarm, operating modes |
| Site Acceptance Test Reports (C5) | Acceptance evidence, operator drills (B9 and similar) |
| Monitoring and Evaluation Plan (D1) | KPI definitions, data quality, confounder log, baseline integrity |
| Data Management and Privacy Plan (D2) | Data handling, privacy notices, breach steps |
| Site Agreement templates (Sections 5, 6, 9, 10, 13, 16, Schedules 3, 4, 5, 7) | Override rules, safe states, equipment title, closure, compensation |
| Stakeholder Engagement Plan (Sections 7, 11) | Community and driver communication, grievance route |
| Training materials and attendance records (D4), Incident and change log (D5), Monthly performance reports (D6) | D4 trains to this manual. D5 receives its records. D6 reports on its outcomes |

## 3. Scope

**In scope.** Routine operation, inspection, preventive and corrective maintenance, fault response, alarm response, emergency response, overrides, data and meter care, spares and service, operator security practice, record keeping, reporting and handover at closure, for Pilots A, B and C from Gate 3 (Month 12) to Gate 5 (Month 24).

**Out of scope.** Changes to configuration, firmware, safe states or limits (change control, C4). Work on Kenya Power assets (the programme never operates or alters them, draft MoU Schedule 1B). Work on host systems unrelated to the pilot. Design changes (TWG). Any live electrical work by operators (Section 5.3).

## 4. Principles

| Principle | What it means in practice |
| --- | --- |
| Safe state is always available | Any person on site can put the system into its agreed safe state using the emergency isolation, without asking permission |
| Competent people only | Operators work within their assessed competence. Electrical and battery work is done by licensed contractors or vendor-authorised technicians |
| Follow the procedure, record the exception | Departures from a procedure are recorded with time, person and reason |
| Local first | The site keeps controlling and protecting itself with no internet. Operators do not depend on remote help to stay safe |
| Least change | Operators fix, replace like-for-like and restore. They do not improve, tune or experiment |
| Evidence is part of the system | Data, seals, logs and mode records are maintained with the same care as equipment |
| Honest records | Faults, failed checks, workarounds and mistakes appear in the log |
| Respect for people | Hosts, customers, drivers and neighbours are told what is happening in plain language, in English and Kiswahili where relevant |

## 5. Roles, authority and limits

### 5.1 Roles

| Role | Operation and maintenance responsibility |
| --- | --- |
| Local operator (primary) and trained backup | Daily and weekly checks, alarm first response, logbook, housekeeping, escort of visitors, first contact for host and community, reports faults |
| Site Lead | Accountable for site safety, schedule and records. Authorises maintenance, permits and returns to service. Holds stop authority. First escalation point |
| Site engineer | Monthly and quarterly inspections, corrective maintenance planning, supervises vendors and contractors, verifies configuration and meters |
| Licensed electrical contractor and vendor service agent | Electrical, battery, inverter and charger repair and servicing under permit to work. Provide service reports |
| Technical Lead and software engineer | Diagnosis beyond operator level, configuration change under change control, restore and rebuild, driver and firmware issues |
| Cybersecurity and Data Protection Officer | Security alarms, accounts, drift reports, incident coordination, data protection |
| Research Lead and data analyst | Data quality feedback, meter checks, confounder log review, mode schedule |
| Host representative | Site rules, access, notice of operational changes, override right on protected loads (Pilot A), co-signature of commissioning and closure records |
| Community liaison officer | Community notices, complaints, feedback at Pilots B and C where appointed |
| Kenya Power grid engineer | Advises on grid-related alarms, limits and utility interface. Operates Kenya Power assets |
| PMO | Tracks faults, spares, service levels, actions and dashboard items |

### 5.2 What operators may do

- View all UI screens, alarms, data and logs available to the operator role.
- Run the routine checks in Section 8 and record the results.
- Acknowledge alarms and follow the alarm card (Section 9). Reset only as the card allows.
- Use the emergency isolation and the emergency override to reach the safe state (Sections 9 and 7).
- Use the logged host override for protected loads where the site agreement gives that right (Pilot A, Section 7).
- Keep the site clean, safe and secure, escort visitors and record visits.
- Replace consumables and fit spares **only** where the procedure and the vendor manual say operators may, with the system isolated.
- Report faults, near misses, suspected security events and complaints.

### 5.3 What operators must not do

- Work on live electrical equipment, open battery enclosures or inverter cabinets, or touch DC circuits.
- Bypass, reset repeatedly, disable or tamper with any protection, alarm, detector, interlock, fuse or breaker.
- Change controller parameters, safety and plausibility limits, safe states, scheduler order, tariff schedules or the mode.
- Edit the Edge configuration, install software or updates, connect laptops or USB drives to programme devices unless the Site Lead and Technical Lead have authorised it and the procedure allows it.
- Add or enable remote access, tunnels, cloud sync, hotspots or vendor remote-support tools.
- Share passwords or use another person's account.
- Move, open, recalibrate or break the seal of any meter or logger.
- Give performance claims, savings figures or results to visitors or media (refer them to the Programme Manager).

Anyone who is unsure whether something is allowed stops and asks the Site Lead first.

## 6. Operating modes in practice

Modes are defined in C4 Section 6.6 and D1 Section 7.2. Operators need to recognise them, not change them.

| Mode | What operators see and do | Data flag |
| --- | --- | --- |
| M0 Commissioning | Not used by operators after Gate 3. Used if a re-commissioning is ordered | M0 |
| M1 Monitoring only (baseline) | Battery idle or unmanaged. Controllers off. Operators run the same checks. They must not "help" by operating the battery manually | M1 |
| M2 Controlled | Controllers on. Normal operation | M2 |
| M3 Fallback or fault | Automatic safe state after device loss, link loss or alarm. Operator follows the alarm card and fault procedure, and logs the start and end | M3 |
| M4 Maintenance | Planned work. Site Lead and Technical Lead set it before work starts, and clear it after the return-to-service checks | M4 |

**Rules.**

1. The operator checks the mode shown on the UI against the latest signed mode record at each weekly check (C4 check V12). A mismatch is reported to the Site Lead the same day.
2. Maintenance is always preceded by an M4 flag and followed by a return-to-service check (Section 10.3).
3. If the system drops into M3, the operator logs the time, the cause shown, and who was told. Return to M2 follows Section 10.3.
4. Control-off weeks, if used in the M&V pattern, are scheduled by the Panel. Operators are told in advance and do not extend or shorten them.

## 7. Overrides

Overrides exist for safety and for protected loads. They are not a convenience.

| Override | Who may use it | When | What happens | Record |
| --- | --- | --- | --- | --- |
| Emergency safe-state or isolation | Anyone on site | Fire, smoke, smell, unusual noise or heat, electric shock, injury, any alarm marked "isolate", or a feeling that something is unsafe | System goes to its safe state or is isolated at the emergency stop or isolator. Everyone moves to the assembly point if the alarm card says so | Logbook, incident report within [24] hours, Site Lead told at once |
| Host override on protected loads (Pilot A) | Host representative or named delegate | A production-critical or protected load would be curtailed or interrupted | Protected loads are released as designed. Normal control resumes when the override ends | Time, person and reason logged automatically and in the logbook. Reported to the Research Lead monthly (D1 Section 10.1) |
| Operator hold | Operator, with Site Lead agreement by phone | A planned event (host shutdown, maintenance, community event, generator service) needs control paused | Controllers paused, M4 flagged | Logbook, M4 record |

**Rules.** Every override is logged with time, person and reason (B4 design rule 5). An override that lasts longer than [x] hours, or is used more than [x] times in a week, is reviewed by the Site Lead and Technical Lead. After any override, the operator confirms the system has returned to its normal mode and the safe state is clear.

## 8. Routine operation and inspection

Routines are minimum requirements. Vendor manuals, the insurer and the site safety plan may add to them. Intervals in brackets are placeholders to be set from the vendor manuals and the first three months of experience. Record every check in the site logbook (Appendix B) and, where the UI allows, in the digital log.

### 8.1 Common routines (all sites)

| Frequency | Check | Who | Standard |
| --- | --- | --- | --- |
| Daily | Walk-round: gates and locks, fencing, signage, enclosures closed, seals intact, no damage, no tampering, no smell, no unusual noise, no standing water, no debris, no animals or nests in cabinets | Operator | Normal. Anything else is logged and reported |
| Daily | UI status: all devices online, mode correct, no open alarms, SoC and power plausible, grid import and export plausible, data logging running, buffer level, clock drift alarm | Operator | All green, or each exception logged with action |
| Daily | Fire and safety: detector panel normal, extinguishers in place, exits and access clear, spill kit present | Operator | Normal |
| Daily | Visitor and contractor log completed, inductions confirmed, permits displayed | Operator | Complete |
| Weekly | Mode check against the signed mode record, override log review, confounder log update (new loads, outages, maintenance, tariff changes) | Operator, Site Lead | Match. Confounders recorded for D1 |
| Weekly | Data completeness check on the research logger and Edge buffer, gap hours since last check | Operator, data analyst | Gaps explained and logged |
| Weekly | Cabinet temperature, ventilation and filters, dust and ingress, cable condition visible from outside, UPS or supercapacitor status | Operator | Within vendor limits |
| Weekly | Site operations check-in (call with Site Lead and PMO) covering uptime, alarms, safety incidents, spares used (Charter Section 15) | Site Lead | Held, minuted |
| Monthly | Site Lead safety walk using the C6 checklist, including fire detection test where the vendor allows an operator test, emergency lighting, signage, first aid kit and contacts | Site Lead | No open safety-critical items |
| Monthly | Site engineer inspection: thermal inspection of cabinets and connections by thermal camera where available, torque marks, corrosion, water ingress, battery room environment, enclosure seals | Site engineer | Within limits. Findings logged |
| Monthly | Drift and access report: configuration hash verify, account list, failed login review, firmware list check (C4 Section 9, B7 Section 6.6) | Cybersecurity Officer or delegate, software engineer | No unexplained drift. Accounts match roster |
| Monthly | Spares and consumables check against the spares list | Operator | Above minimum levels |
| Monthly | Review of complaints and feedback log | Site Lead, PMO | Acknowledged and answered on time |
| Quarterly | Quarterly inspection by the site engineer: electrical connections, protection settings against Schedule 3, earthing continuity check, surge protectors, fire detection and suppression service status, fencing and security, waste and spill kit condition | Site engineer, licensed contractor where needed | Within limits. Report issued |
| Quarterly | Operator refresher or drill (rotating: fire and evacuation, battery alarm, spill, security incident, reset procedure) | Site Lead, Technical Lead | Drill completed and recorded |
| Quarterly | Meter and seal check: seals intact, readings against a reference where available, calibration certificate dates | Site engineer, Research Lead | Seals intact. Readings agree within the agreed limit |
| Annual and at Gate 4 | Restore test, rollback test, offline operation test, meter accuracy recheck, access review, insurer or independent check where required, safety walk with local responders | Technical Lead, software engineer, Site Lead | Tests passed. Records filed (C4 V9, V10, D1 Section 8.2) |

### 8.2 Battery plan (Pilots A and B, and C if a battery is fitted)

The battery is the highest-consequence asset. Its plan has three parts: keep it within limits, watch for early warning, and act fast on alarms. The exact limits, intervals and alarm codes come from the vendor manual and the B6 record.

| Topic | Requirement |
| --- | --- |
| Operating window | Run within the SoC window and power limits in the safety set (L5). Operators do not change them. The BMS limits sit outside the L5 window and are never to be reached in normal operation |
| Temperature | Cell and enclosure temperatures within the vendor range. Ventilation or cooling kept clear. Alarm at [x] °C. Operators log any temperature trend that rises over several days |
| State of health and capacity | Capacity and state of health read from the BMS monthly where reported, and recorded as input to the M&E plan (D1 Section 6.1). A fall faster than the vendor curve is reported to the Technical Lead |
| Cycling and throughput | Cycle count and throughput read monthly and compared with the warranty limits in the vendor commitments (B6 Section 9). Approaching a limit is reported |
| Balancing and calibration | Vendor-prescribed balancing or full-cycle calibration is scheduled by the Technical Lead and the Panel. It may mean a controlled mode interruption flagged M4 |
| Visual and sensory checks | Swelling, leaks, discolouration, corrosion, loose or hot connections, smell, noise. Any one of these means isolate and call the Site Lead (Section 9) |
| Detection and suppression | Detector panel, alarm sounders, communication to the responder path and suppression readiness checked monthly. Service by the licensed provider at the interval the fire assessment sets [x months] |
| Housekeeping | No combustibles, tools or stored goods in or next to the battery area. Vegetation cleared to [x m]. Door kept closed and locked |
| Inactivity and storage | If a battery is idle for more than [x] days, or in extended M4, the vendor storage SoC and temperature guidance applies |
| Firmware and BMS updates | Held at the tested version. Updates only through change control with off-site test and rollback (C4 class C3) |
| Replacement and removal | By vendor-authorised technicians under permit to work. Removed cells and modules are treated as hazardous waste (Section 14) |

### 8.3 Pilot A routines: industrial park, hub or campus

| Frequency | Additional check | Standard |
| --- | --- | --- |
| Daily | Host operating pattern for the day (shutdowns, planned load changes) known and logged | Known |
| Daily | Protected-loads list and override access working | Override reachable |
| Weekly | Existing PV inverter status and alarms. Export against the approved limit | Within limit |
| Weekly | Host IT: no unexpected device on the programme network, no change to the firewall rules | Unchanged |
| Monthly | Tariff and bill documents received for the K3 comparison, and any tariff change reported to the Research Lead | Received |
| Monthly | Battery room fire and ventilation check with host fire officer or facilities lead | Within plan |
| As needed | Before any host shutdown, switchboard work or generator test: notify Site Lead so M4 is set and the system is placed in safe state | Done before work |

### 8.4 Pilot B routines: rural microgrid

| Frequency | Additional check | Standard |
| --- | --- | --- |
| Daily | Supply continuity: any customer complaints, outages or low-voltage reports since yesterday | Logged |
| Daily | Generator: fuel level, oil, leaks, battery, auto-start readiness, last run hours and fuel use read for the diesel offset record | Logged |
| Daily | Mobile signal and fallback link status. Buffer level | Within agreed threshold or reported |
| Daily | Cabinet and fence security, theft or vandalism signs, wildlife, standing water, lightning damage after storms | Normal |
| Weekly | PV array walk: cleanliness, shading, vegetation, bird fouling, loose cables, hotspots visible, mounting condition | Logged. Cleaning per procedure |
| Weekly | Check meters and feeder input meter readings recorded against Edge values for the K6 energy balance | Agreement within [x]% |
| Monthly | Voltage logs at feeder end and transformer secondary reviewed for low-voltage events | Logged |
| Monthly | Spares kit complete. Service agent response confirmed | Complete |
| Quarterly | Community update and safety message. Fence, signage and children and livestock controls reviewed with the community liaison | Done |
| After storms or floods | Walk-round before returning to service. Earthing and lightning protection visual check. Report to Site Lead | Done and logged |

### 8.5 Pilot C routines: EV charging site

| Frequency | Additional check | Standard |
| --- | --- | --- |
| Daily | Each charger: display, status, connector and cable condition, emergency stop, damage, cleanliness, signage and privacy notice legible, lighting working | Normal |
| Daily | Throttling message and charging policy display working. Maximum-wait alarm status | Working |
| Daily | Transformer meter feed alive. Site limit shown on UI equals the Schedule 3 value | Value matches |
| Weekly | Charger fault list and session error review, vehicle types that rejected limiting recorded | Logged |
| Weekly | Charger-vendor and site operator check-in on faults and complaints | Held |
| Monthly | Thermal inspection of chargers, connectors and the distribution board where available. Cable and connector wear | Within limits |
| Monthly | Complaints per 100 sessions and top themes shared with PMO | Reported |
| Quarterly | Fire response familiarisation for site operator staff, public evacuation route check, fire extinguisher service | Done |

## 9. Alarms and first response

### 9.1 Alarm classes

| Class | Meaning | Examples | Operator first response |
| --- | --- | --- | --- |
| A1 Emergency | Possible danger to people or property | Fire or smoke detector, gas alarm, battery over-temperature, BMS critical alarm marked "isolate", electric shock, smell of burning, visible flame | Follow Section 11 emergency procedure at once |
| A2 Safety-relevant | System in a safe state or protection has acted | BMS warning, inverter fault, protection trip, earth fault, safe-state entry, charger over-temperature, transformer threshold reached, loss-of-feed limit applied | Make sure nobody is at risk. Do not reset. Log and call the Site Lead within [15] minutes |
| A3 Operational | Control or data function degraded but safe | Device offline, communication loss, data gap, clock drift, buffer high, configuration hash mismatch, firmware list mismatch, mode mismatch | Log. Follow the fault table (Section 10.1). Report to the Site Lead the same day |
| A4 Advisory | Maintenance or trend | Filter due, spares low, calibration due, cleaning needed | Add to the maintenance plan |

### 9.2 Alarm card (print at each cabinet)

1. **Stay safe.** If there is fire, smoke, smell, heat or any doubt, move away and go to the assembly point. Do not enter the battery area. Call the fire service.
2. **Isolate only if it is safe and you are trained to.** Use the emergency stop or isolator listed on the site emergency sheet.
3. **Call the Site Lead.** Then the next person on the escalation table (Section 12).
4. **Do not reset an alarm** until the cause is known and the Site Lead has agreed. Repeated resets without a recorded cause are not allowed.
5. **Write it down.** Time, alarm text or code, what you saw, what you did, who you told.
6. **Do not try to fix electrical or battery faults.** Wait for the licensed contractor or vendor technician.

### 9.3 Resets

| Alarm type | Who may reset | Condition |
| --- | --- | --- |
| A1 Emergency | Never by operator | Only after root cause, Programme Director release for Class 1 (C6 Section 14.2) |
| A2 Safety-relevant | Site engineer, vendor technician or Technical Lead | After cause is found and recorded, protections checked, return-to-service check done |
| A3 Operational | Operator, as the fault table allows, once | If the alarm returns, escalate instead of resetting again |
| A4 Advisory | Operator | Acknowledge after the task is done |

## 10. Fault handling and corrective maintenance

### 10.1 Fault table (operator level)

Operators do the first checks only. The cause, the fix and the return to service for anything beyond these steps belong to the Site Lead, site engineer, vendor or Technical Lead.

| Symptom | First checks (safe to do) | Escalate to | Time target |
| --- | --- | --- | --- |
| Edge or UI not reachable locally | Check power light, cabinet temperature, network cable seated, UPS status. Do not reboot more than once. Log | Site Lead, then Technical Lead | Same day. [4] hours for Pilot B and C |
| One device offline (meter, inverter, charger, battery) | Check device power and indicator lights, local link cable, device display for fault. Do not reset the device | Site Lead, site engineer | Same day |
| Site in M3 safe state | Read the cause on UI. Check for alarms and smells. Confirm battery idle or chargers on fallback limit. Log | Site Lead, Technical Lead | Within [1] hour |
| Control not following setpoints (import not held, battery not responding) | Record readings and screenshot. Check for active overrides and mode | Technical Lead | Same day |
| Data gap or logger stopped | Check logger power, link, storage level. Record last good time | Research analyst, site engineer | Same day |
| Clock drift alarm | Record difference and time source status. Do not change the clock manually | Technical Lead | Same day |
| Configuration hash mismatch or drift alarm | Do not change anything. Note time and any recent visitors or work | Cybersecurity Officer, Technical Lead | Immediately. Treated as an incident (C4 Section 9) |
| Unknown device, new network traffic, or someone asking for remote access | Do not connect or allow access. Note who and when. Disconnect the uplink only if the playbook or Site Lead says so | Cybersecurity Officer | Immediately |
| Battery temperature high or fan or cooling failure | Check ventilation openings, door closed, ambient. Do not open the enclosure | Site Lead, vendor | Immediately for A1, within [15] minutes for A2 |
| Export limit or site limit exceeded | Record. Do not change the limit | Technical Lead, Kenya Power grid engineer where relevant | Within [1] hour |
| Charger not charging or not limiting (Pilot C) | Check display, cable and connector, vehicle, emergency stop. Inform the driver | Site Lead, charger vendor | Same day |
| Throttling complaints or long waits (Pilot C) | Record the complaint and the time. Explain the policy sign | Site Lead, Technical Lead | Same day |
| Generator fails to start or runs unexpectedly (Pilot B) | Check fuel, stop button, local controller panel. Follow generator manual | Site Lead, Technical Lead | Same day |
| Supply interruption or low-voltage reports from customers (Pilot B) | Record time, location, customers. Check generator and site status. Inform the operator and Site Lead | Site Lead, operator, Kenya Power if grid-connected | Immediately |
| Theft, vandalism or tampering | Do not confront anyone. Secure the area if safe. Photograph | Site Lead, police, Cybersecurity Officer | Immediately |
| Water ingress, flooding, lightning strike | Do not enter if live equipment may be affected. Isolate only if safe and trained | Site Lead, licensed contractor | Immediately |

### 10.2 Preventive and corrective maintenance rules

1. **Permit to work.** Any maintenance beyond routine checks needs a permit with isolation and lock-out (C6 Appendix B). No permit, no work.
2. **Two-person rule.** Electrical and battery tasks are done by two people, at least one of them licensed or vendor-authorised.
3. **Like-for-like.** Replacement parts match the B6 tested model and firmware. A different model or firmware is a change (C4 class C3) and needs a delta test first.
4. **Mode flag.** The Site Lead sets M4 before work and records the start and end.
5. **Service reports.** The vendor or contractor leaves a service report: what was found, what was done, parts used with serial numbers, firmware, settings changed. The site engineer files it with the D5 log and updates the B6 and C4 records where needed.
6. **Warranty.** Work follows the vendor warranty terms. Unauthorised repairs are not made. Written permission for third-party control is on file (B6 Section 9).
7. **Parts and waste.** Faulty parts and batteries are labelled, stored safely and returned or disposed of under the take-back clause (Section 14).
8. **Corrective maintenance on safety layers.** Any repair that touches a protection, the safe state, a limit, or the hardware that enforces them requires the Technical Lead and, where it changes a limit that is grid-related, Kenya Power agreement (C4 class C1).

### 10.3 Return to service checklist

The Site Lead signs this before the system leaves M4 or M3.

| # | Check | Done |
| --- | --- | --- |
| 1 | Cause recorded. Permit closed. Locks removed. Area made safe | [ ] |
| 2 | Hardware protections confirmed working (alarms clear, detectors normal, emergency stops tested where affected) | [ ] |
| 3 | Installed devices match the B6 firmware list. Configuration hash matches the manifest | [ ] |
| 4 | Communication to every affected device verified read-only first, then control enabled | [ ] |
| 5 | Safe state tested for the affected device where the change could alter it | [ ] |
| 6 | Meters, seals and time sync verified, data flowing at full resolution | [ ] |
| 7 | Mode and controller order restored per the signed record. Mode flag updated | [ ] |
| 8 | Host, community or operator told of return to service where relevant | [ ] |
| 9 | Logbook, D5 entry and any confounder note completed | [ ] |
| 10 | Site Lead authorisation, name, time | [ ] |

## 11. Emergency procedures

Site emergency sheets (C6 Appendix D) carry the local numbers and routes. The steps below are the programme minimum.

### 11.1 Fire, smoke or battery thermal event

1. Sound the alarm. Raise the alarm to everyone on site.
2. **Evacuate** to the assembly point. Nobody enters the battery or fire area except trained responders.
3. Call the fire service on the number on the emergency sheet, then the Site Lead.
4. Isolate by the emergency stop only if you can reach it without entering the danger area.
5. At the assembly point, count people, report anyone missing, brief responders on what is stored and the isolation points.
6. Do not re-enter. Do not reset anything. Preserve the scene.
7. The Site Lead notifies the PMO and Programme Director within [1] hour (Class 1, C6 Section 14.1). The Programme Director notifies the SteerCo Chair, Kenya Power, the insurer and statutory bodies as the law requires.
8. At Pilot B, the community alert route is used for households near the site. At Pilot C, the public and fleet drivers are evacuated.

### 11.2 Electric shock or serious injury

1. Make safe: isolate the source if safe, do not touch the casualty until the supply is off.
2. Call the ambulance and first aider. Start first aid. Use the nearest defibrillator where one is available.
3. Report to the Site Lead and follow Class 1 or 2 reporting (C6 Section 14).
4. Keep the equipment and scene unchanged unless that creates danger.

### 11.3 Spill or leak

Stop the source if safe. Contain with the spill kit. Keep clear of drains and water. Report to the Site Lead. Contaminated material is collected and disposed of through licensed handlers (Section 14). Significant releases are Class 2 incidents.

### 11.4 Severe weather, lightning or flood

Stop outdoor work. Move people indoors or to safe shelter. Do not approach arrays, cabinets or the battery area during lightning. After the event, the Site Lead authorises a walk-round before return to service.

### 11.5 Security incident (cyber or physical)

Follow the playbooks in B7 Section 10.5. For operators: do not allow unknown persons near cabinets, do not connect unknown devices, report anything unexpected at once, and disconnect the uplink only if the playbook or Site Lead tells you to. The Cybersecurity Officer owns the incident.

### 11.6 Loss of supply, loss of communications

The Edge continues control offline. Operators log the start of the event, check the safe state, and keep a log of local readings if the UI is unavailable. Pilot B uses the rehearsed transfer plan to existing supply or generator (C3 Section 10). Communications independent of the site network (mobile, radio or satellite) are used to reach the Site Lead.

### 11.7 Evacuation and drills

Assembly points, routes and the emergency sheet are displayed at site entrances and the battery area. Drills are held before energisation, before Gate 3 and at Gate 4, and each quarter on rotation (Section 8.1).

## 12. Escalation

### 12.1 Escalation ladder

| Level | Who | When | How quickly |
| --- | --- | --- | --- |
| 1 | Operator or backup | First response, routine faults, logging | Immediately |
| 2 | Site Lead | Any A1 or A2 alarm, any fault beyond Section 10.1 first checks, any override over limits, any incident, any complaint about safety | Within [15] minutes for A1 and A2. Same day for others |
| 3 | Site engineer, vendor local service, licensed contractor | Repair, inspection, diagnosis on site | Within the service level in the vendor commitments |
| 4 | Technical Lead, software engineer, Cybersecurity Officer | Control or software faults, configuration, security events, drift | Within [1] hour for A1, A2 and S1 to S2. Same day for others |
| 5 | PMO and Programme Director | Class 1 or 2 incident, gate risk, repeated failures, spares or service failure, regulator or Kenya Power matter | Within [1] hour for Class 1. Within [24] hours for Class 2 |
| 6 | Steering Committee Chair | Class 1 incident, accepted high risk, stop or extend decision | Immediately for Class 1, otherwise at the next SteerCo |

### 12.2 External notifications

| Recipient | When | Who notifies |
| --- | --- | --- |
| Kenya Power | Grid-affecting events, cyber incidents, transformer threshold events, any Class 1 or 2 event affecting the connection point | Programme Director, Technical Lead |
| EPRA | Where licence, exemption or sandbox conditions require, or regulation requires | Programme Director |
| Insurer | As the policy requires, always for fire or thermal events | Programme Director, Site Lead |
| Statutory bodies (OSH, fire, environment, police) | As the law requires | Programme Director with counsel |
| ODPC and affected individuals | Personal data breach per D2 Section 12 | Cybersecurity Officer |
| Host representative, operator, community or users | Planned and unplanned outages, safety events, tests, anything affecting them | Site Lead, community liaison officer |

### 12.3 Contact list

Each cabinet and the site emergency sheet carry a current contact list: Site Lead and deputy, Technical Lead, Cybersecurity Officer, PMO, vendor service numbers, licensed contractor, host representative, Kenya Power fault line and grid engineer, local fire, ambulance, police, insurer, community liaison. The Site Lead checks it monthly and after any staff change.

## 13. Security, data and evidence care for operators

### 13.1 Security habits

- Use only your own named account. Never share or write passwords where others can see them.
- Do not plug in USB drives, phones or laptops into programme devices.
- Do not click links or open attachments you do not expect, and do not enter programme credentials anywhere except the official local UI.
- Keep cabinets locked. Keys are logged. Seals are checked weekly.
- Escort visitors and contractors, sign them in and out, and confirm their induction.
- Report suspicious calls, emails, visits or devices at once, even if you are unsure.
- Do not take photographs of screens, network diagrams or credentials, and do not post about the site on social media.

### 13.2 Remote support

Before Gate 3 no remote support is used. After Gate 3, remote sessions are time-bound, approved by the Cybersecurity Officer, logged and run only through the approved path (B7 Section 6.2). An operator never gives a person on the phone control of a programme device or reads out credentials. Anyone who asks for that is reported as a security event.

### 13.3 Meters, seals and data

- Meters and the research logger are not moved, opened or recalibrated by operators.
- Seals are checked weekly. A broken or missing seal is photographed, logged and reported the same day. The affected data period is flagged (D1 Section 8.2).
- The time source is not changed manually. Clock alarms are reported.
- Local data transfer, if used before Gate 3, is done by named staff with a transfer log (D2 Section 7).
- Household and driver data are not read, copied or shared by operators. Questions about data go to the Officer.
- Confounders (new loads, equipment changes, tariff changes, outages, maintenance, holidays, shutdowns, theft or damage) are written in the weekly log. They protect the evaluation (D1 Section 7.5).

### 13.4 Privacy and complaints

Notices are kept displayed and legible (Pilot C privacy notice, Pilot B community notices). Questions about data are referred to the site complaints channel. Complaints are acknowledged within [3] working days and answered within [14] days (Stakeholder Engagement Plan Section 11). Nobody is penalised for asking.

## 14. Spares, service, warranty and waste

### 14.1 Spares and consumables

| Item | Rule |
| --- | --- |
| Spares list | Per site, from the vendor commitments (B6 Section 9). Critical spares at or near each site. Pilot B has a full spares kit including a spare Edge. Pilot C holds charger modules and communication boards |
| Minimum levels | Set per item [x]. Reorder when stock reaches minimum. Operators check monthly |
| Storage | Dry, secure, labelled. Batteries and sensitive items stored as the vendor and C6 require |
| Use | Each use is logged with date, item, serial and reason. Replacement is like-for-like |
| Replenishment | The Site Lead raises the request to the PMO. Expenditure follows the Charter limits (Section 17) |

### 14.2 Service levels and warranty

Service response times, local technicians, spares and training come from the vendor contracts (C1 Section 9). Operators keep a copy of the warranty terms, service numbers and the claim procedure. Faults covered by warranty are reported within the vendor window. The PMO tracks response time against the contract and escalates repeated breaches (C1 Section 11.2).

### 14.3 Waste and end of life

Waste is segregated, logged and handled by approved handlers (C6 Section 11.4). Damaged or end-of-life batteries are hazardous waste, isolated, labelled and stored safely until return to the vendor or collection by licensed handlers. Electronic waste is data-erased and collected by licensed e-waste handlers. No waste is burned or dumped. A waste log records quantity, handler, licence number and destination.

## 15. Records and reporting

### 15.1 Logs kept

| Record | Content | Kept by | Where it goes |
| --- | --- | --- | --- |
| Site logbook (paper or digital) | Daily and weekly checks, visitors, events, overrides, faults, weather, deliveries | Operator | Site engineer weekly. Archive at closure |
| Override log | Time, person, reason, duration | Edge and operator | Research Lead monthly |
| Confounder log | New loads, equipment changes, tariff changes, outages, maintenance | Operator, Site Lead | Data analyst weekly, D1 |
| Maintenance and service log | Work done, permit number, parts, service reports | Site engineer | D5, B6 and C4 updated |
| Incident and near-miss log | Reports, root cause, actions | Site Lead | D5, PMO, C6 Section 14 |
| Complaints and feedback log | Complaint, date, response, closure | Site Lead, liaison | PMO monthly |
| Spares and waste logs | Items used, stock, waste handlers | Operator | PMO monthly |
| Training and drill records | Attendance, assessment, drills | Site Lead | D4 |
| Mode records and configuration manifest | Signed by Panel and Technical Lead | Software engineer | C4 |

### 15.2 Reports

| Report | Frequency | Content |
| --- | --- | --- |
| Weekly site check-in | Weekly | Uptime, alarms, safety incidents, spares, confounders |
| Monthly site report | Monthly | Uptime (K4), faults and response time, maintenance done and due, spares, complaints, safety walk results, drift report, training status. Feeds the dashboard and D6 |
| Quarterly inspection report | Quarterly | Findings, actions, drills, condition of safety systems |
| Incident reports | As they occur | C6 Appendix C template |
| Handover report | At closure | Section 18 |

### 15.3 Performance measures

| Indicator | Measure | Target |
| --- | --- | --- |
| System uptime and availability (K4) | Hours with Edge running and assets under control divided by hours in period, excluding M4 | \[Gate 1\] |
| Mean time to acknowledge | Alarm to operator acknowledgement | [x] minutes |
| Mean time to repair | Fault report to return to service, by device class | [x] hours |
| Planned maintenance completion | Routine and quarterly tasks done on time | [100%] |
| Open safety-critical items | Count | Zero |
| Data completeness | Share of expected intervals present | [x]% |
| Spares availability | Share of critical spares in stock | [100%] |
| Complaints answered on time | Share acknowledged and resolved within agreed times | Per Stakeholder Plan Section 11 |
| Operators trained and retained | Competent operators in post (Charter KPI) | Per Charter risk trigger |

## 16. Training, competence and staffing

| Group | Training and assessment | Timing |
| --- | --- | --- |
| Local operators and backups | This manual, alarm card, emergency procedures, safe state and override rule, logbook, security habits, first-response fire and spill, reset and fault drill (C5 tests B9 and equivalents), assessed competence | Before Gate 3, refresh [annually] and after any major change |
| Site Leads | Permit to work, incident handling, escalation, return to service, first aid | Before Gate 2 |
| Host staff (Pilot A) and site operator staff (Pilot C) | Awareness: what the system does, what to do on alarm, who to call, how to use the override right | At go-live and annually |
| Community liaison officers | Safety messages, complaints handling | Before H0 |
| Local responders | Site familiarisation visit | Before energisation, repeated at Gate 4 |

**Staffing rules.** Each site has a named primary operator and a trained backup, so that cover exists for leave, illness and travel. Retention of trained staff is tracked as a risk (Stakeholder Engagement Plan Section 12). Operators are not asked to work alone in hazardous tasks (C6 Section 9) and are never penalised for stopping work.

## 17. Costs and resources

Operations and maintenance costs come from the first-year O&M share of the reference cost structure (about 15%), the service terms in the vendor contracts and the training line (Charter Section 8, C1 Section 5). Items to itemise in the budget reconciliation before Gate 1 include: operator stipends or host contributions, spares and consumables, service contracts, inspections, thermal imaging and test instruments, fire system servicing, transport to Pilot B, communications costs, insurance premiums, waste and take-back. Amount: KSh \[to be confirmed at Gate 1\]. Use of contingency needs Steering Committee approval (Charter Section 20). After the pilot, a post-pilot operating budget is part of the sustainability plan (Section 18).

## 18. Closure, handover and sustainability

At Gate 5 the programme confirms closure and handover (Charter Section 24).

| Step | Requirement |
| --- | --- |
| Handover decision | Equipment is transferred, removed or decommissioned as Schedule 4 of the Site Agreement says |
| Record transfer | Logbooks, service history, spares list, warranty documents, as-built drawings, configuration baseline, this manual, safety plan and training records go to the named custodian |
| Custodian briefing | Written and on-site briefing on safety duties, end-of-life duties, security and data duties (D2 Section 13) |
| Post-pilot plan | Agreed plan for ongoing support, who operates, who services, who pays, how long, and what is reported to whom |
| Decommissioning | Method statement approved before closure. De-energise, isolate, discharge and remove under vendor guidance and permit. Environmental handover and waste records (C6 Section 17) |
| Data and credentials | Data returned, deleted or archived as agreed. Credentials revoked or handed over. Devices securely erased before disposal |
| Lessons learned | O&M lessons are written into the replication guide (E3), including faults, repair times and what operators found hard |

## 19. Schedule and gate evidence

| Activity | Months | Output | Gate |
| --- | --- | --- | --- |
| Draft method and templates, agree with TWG | 4 to 8 | This document v0.1 reviewed | Gate 1 input |
| Collect vendor manuals, alarm codes, service levels, spares lists | 8 to 11 | Inputs for site copies | Gate 2 |
| Prepare site-specific manuals, alarm cards and emergency sheets | 10 to 12 | Site copies | Gate 3 |
| Train operators and run drills | 10 to 12 | Records in D4 | Gate 3 |
| Routine operation, monthly reporting | 13 to 24 | Monthly site reports | Gate 4 |
| First manual review from operating experience | 15 to 16 | v0.2 | Gate 4 input |
| Closure, handover, custodians briefed | 22 to 24 | Handover report | Gate 5 |

| Gate | Evidence from this manual |
| --- | --- |
| Gate 2 | Method approved. Vendor-manual inputs and service levels in contracts. Alarm card and emergency sheet templates ready |
| Gate 3 | Site-specific manual in the handover pack. Operators trained and assessed. Drills done. Spares on site. Contact lists verified |
| Gate 4 | Monthly reports, uptime, fault and repair statistics, incident and near-miss summary, drill repeat, manual updated from experience |
| Gate 5 | Handover report. Custodians briefed. Post-pilot plan agreed. Lessons in E3 |

## 20. Risks to add to the live Risk Register

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| OM1 | Operator error or bypass of a protection | L | H | Training, limits on tasks, alarm card, no-reset rule, audits | Site Lead |
| OM2 | Trained operators leave or are unavailable | M | M | Backup operator, documentation, refresher training, retention tracking | Technical Lead |
| OM3 | Long vendor or contractor response at remote sites | H | M | Spares kit, service SLA, remote diagnosis after Gate 3, local technician | Site Lead B |
| OM4 | Spares unavailable or delayed (import, duties, lead times) | M | M | Critical spares on site, reorder levels, early orders | Programme Manager |
| OM5 | Maintenance work contaminates data or baseline | M | H | M4 flag, confounder log, Panel notification | Research Lead |
| OM6 | Return to service without proper checks | L | H | Return-to-service checklist, Site Lead signature | Site Lead |
| OM7 | Unauthorised remote access or vendor path introduced during service | M | H | Contract clause, operator rules, monthly scans, drift report | Cybersecurity Officer |
| OM8 | Alarm fatigue or repeated unexplained alarms normalised | M | M | Trend review, root cause on repeats, no repeated resets | Technical Lead |
| OM9 | Theft or vandalism of equipment at Pilot B | H | M | Locks, seals, community engagement, insurance, spares | Site Lead B |
| OM10 | Manual not followed or out of date | M | M | Training, monthly review, update after incidents and changes | Technical Lead |
| OM11 | No funded operator or service plan after Gate 5 | M | H | Post-pilot plan, custodians named, budget line | Programme Sponsor |
| OM12 | O&M under-budgeted | M | M | Itemise in budget reconciliation before Gate 1 | Programme Manager |

These risks are merged into the live Risk Register (README A6). A Class 1 incident is a Charter escalation event.

## 21. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Obtain vendor O&M manuals, alarm code lists, inspection intervals and spares lists for all selected devices | Gate 2 | Technical Lead, procurement lead |
| 2 | Set intervals and thresholds marked [x] from vendor data and insurer conditions | Gate 2 | Technical Lead, Site Leads |
| 3 | Decide operator employment model: host staff, cooperative, vendor, or programme-hired, and stipends | Gate 1 | Programme Director |
| 4 | Decide whether a safety officer is per site or shared (C6 open item 6) | Gate 1 | Programme Director |
| 5 | Agree which resets and consumable replacements operators may do per device | Gate 2 | Technical Lead, vendors |
| 6 | Define digital versus paper logbook, and offline logging at Pilot B | Gate 2 | Technical Lead |
| 7 | Decide whether L5 changes after Gate 3 need two-person on-site approval (B7 open item 5) | Gate 2 | TWG |
| 8 | Agree response and repair targets with vendors (C1 Section 9) | Contracts | Procurement lead |
| 9 | Decide post-pilot operator, service and funding arrangement per site | Gate 4 | Programme Sponsor |
| 10 | Decide whether this manual is published, and what is withheld (credentials, network details, host data) | Gate 3 | Technical Lead, Cybersecurity Officer |
| 11 | Provide Kiswahili and local-language versions of the alarm card and operator summary | Gate 3 | Capacity-building lead |
| 12 | Decide the thermal inspection method and instruments per site | Gate 2 | Site engineer |

## 22. Immediate next steps

1. TWG to review this method, including the Kenya Power grid engineer on utility-interface alarms and isolation.
2. Technical Lead to add vendor manual requirements to the tender and vendor questionnaire so that O&M documents, alarm lists and spares lists are delivered with the equipment.
3. Site engineer to draft site-specific alarm cards, emergency sheets and logbooks in English and Kiswahili.
4. Decide the operator model, backup arrangement and any stipends, and begin operator selection.
5. Plan operator training and drills with the capacity-building lead so they are completed before Gate 3.
6. Agree the confounder log, override log and monthly site report formats with the Research Lead.
7. Add risks OM1 to OM12 and open items to the PMO log and Risk Register.
8. Plan the first manual review from operating experience for Gate 4.

---

# Appendix A: Site-specific manual cover sheet (template)

| Field | Entry |
| --- | --- |
| Site, pilot, address, GPS | [ ] |
| Configuration baseline tag and manifest reference | [ ] |
| Device list with make, model, serial, firmware (match B6) | [ ] |
| Vendor manuals and warranty documents (location) | [ ] |
| Safe states, limits and override rules (Schedule 3 reference) | [ ] |
| Alarm code list and meaning | [ ] |
| Inspection intervals and thresholds (set from vendor data) | [ ] |
| Isolation points and emergency stop locations (map) | [ ] |
| Spares list and minimum levels | [ ] |
| Service agents, response times and warranty claim route | [ ] |
| Named operator, backup, Site Lead, host representative | [ ] |
| Emergency sheet and contact list | [ ] |
| Remote access status | Disabled until Gate 3. After Gate 3: [approved path, change reference] |
| Issue date and approvals | Site Lead [ ]; Technical Lead [ ]; Host representative [ ] |

# Appendix B: Daily and weekly check sheet (template)

| Date | Time | Operator | Walk-round normal (Y/N) | UI status all green (Y/N) | Mode matches record (Y/N) | Open alarms | Data logging and buffer OK (Y/N) | Detector panel normal (Y/N) | Seals intact (Y/N) | Visitors logged (Y/N) | Issues and actions | Reported to |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

*Pilot B adds generator readings, mobile signal, customer complaints and check meter readings. Pilot C adds charger status, display and signage checks, and transformer feed status.*

# Appendix C: Alarm quick card (template, print per cabinet)

| If you see or hear | Do | Do not |
| --- | --- | --- |
| Smoke, flame, strong smell, hissing, bulging, very hot enclosure | Raise the alarm, evacuate, call the fire service, then the Site Lead | Enter the area, open the enclosure, use water unless responders say so |
| Electric shock or injury | Make safe if you can, call ambulance and Site Lead, give first aid | Touch the casualty while live |
| Protection alarm, inverter fault, BMS alarm | Keep away from the equipment, log, call the Site Lead | Reset repeatedly, bypass |
| Device offline, data gap, clock alarm | Run the first checks in the fault table, log, report | Reboot more than once, change the clock |
| Unknown device, strange access request, drift alarm | Do not connect or allow access, note details, call the Cybersecurity Officer | Plug in USB, give out passwords |
| Theft, vandalism, intruder | Stay safe, secure the area if safe, call the Site Lead and police | Confront anyone |

# Appendix D: Maintenance record and service report (template)

| Field | Entry |
| --- | --- |
| Record ID | `MNT-[site]-[number]` |
| Date, start and end time | [ ] |
| Type (routine, preventive, corrective) | [ ] |
| Permit number and isolation points | [ ] |
| Equipment and register ID | [ ] |
| Fault or task description | [ ] |
| Work done, by whom (name, licence or vendor authorisation) | [ ] |
| Parts used (model, serial, firmware) and parts removed (disposal route) | [ ] |
| Settings changed (should be none unless under change control, reference) | [ ] |
| Mode flag start and end (M4 record) | [ ] |
| Return-to-service checklist reference | [ ] |
| Effect on data, baseline or KPIs | [ ] |
| Follow-up actions, owner, due | [ ] |
| Signatures | Operator [ ]; Technician [ ]; Site Lead [ ] |

# Appendix E: Monthly site report outline

1. Period, mode and configuration hash status.
2. Uptime (K4), alarms by class, faults, mean time to acknowledge and repair.
3. Maintenance done and due, service reports, spares used and stock.
4. Battery health summary (temperature trends, capacity, cycles, any warranty limits approached).
5. Safety: inspections, near misses, incidents, drills, open safety-critical items.
6. Security: drift report, account review, suspicious events, seal checks.
7. Data: completeness, gaps, confounders, overrides.
8. Community, host or user feedback and complaints, with closures.
9. Training and staffing status.
10. Issues needing PMO, Technical Lead or SteerCo attention.

# Appendix F: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 15, 16, 17, 19, 20, 21, 23, 24) | Cadence, gates, financial limits, safety and security governance, change control, closure |
| Feasibility Study (Sections 4.4, 7.2, 8.2, 9) | Offline resilience, safety, capacity, risks |
| Technical Specification per Site (Sections 3.2 to 3.6, 5 to 7, 9) | Design rules, safe states, controller functions, acceptance tests |
| Interoperability Register (Sections 4, 9, 10) | Tested device and firmware set, vendor commitments, delta testing |
| Cybersecurity Plan (Sections 6.1 to 6.7, 10, 11) | Accounts, remote access, physical security, incident response, operator training |
| Health, Safety and Environmental Plan (Sections 6, 9, 11, 14, 15, 17, Appendices B to D) | Permit to work, battery and fire controls, emergency plan, incident classes, waste |
| Installation and Commissioning Plan (Sections 8, 10, 11, 13) | Handover pack, enablement order, pilot-specific interfaces |
| OpenEMS Configuration Baseline (Sections 6.4, 6.6, 9, 10, 11) | Safety set, operating modes, drift, change classes, backup and restore |
| Site Acceptance Test Reports (Sections 8, 9, 12) | Operator drills, handover verification |
| Monitoring and Evaluation Plan (Sections 6, 7, 8, 10) | KPIs, confounders, meter and data care |
| Data Management and Privacy Plan (Sections 7, 11, 12, 13) | Data handling, notices, breach steps, custodianship |
| Procurement Plan (Sections 9, 11) | Service levels, spares, warranty and take-back |
| MoU and Site Agreement templates (Site Agreement Sections 5, 6, 9, 10, 13, 16, Schedules 3 to 7, Pilot A, B, C terms) | Overrides, safe states, ownership, closure, compensation |
| Stakeholder Engagement Plan (Sections 7, 11, 12) | Community and driver communication, grievance route, retention risk |

On completion of the tender award, the vendor manuals, the Gate 2 design review and commissioning, each bracketed value is updated, a site-specific copy is issued in each handover pack, and this document is re-issued as version 1.0 for Gate 3.

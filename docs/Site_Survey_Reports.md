# Site Survey Reports

Supports Feasibility Study (D1) Sections 10 and 13, and feeds D4 (site specifications) and Gate 1.

**Important status note.** No candidate site has been selected or visited, and no site data has been collected. These reports are therefore **pre-populated survey reports**: the programme's requirements, pilot configurations, data needs and decision criteria are filled in from the Charter, Feasibility Study and MoU/Site Agreement templates, and every field in square brackets \[ \] is to be completed during the site visit and desk data request. Nothing in a bracket is a finding. Complete one report per candidate site (the Feasibility Study advises at least two candidates per pilot).

## How to use this pack

| Step | Action | Owner |
| --- | --- | --- |
| 1 | Send the data request (Section 4 of each report) to the host 2 weeks before the visit | Site Lead |
| 2 | Visit with a licensed electrical engineer, the Technical Lead or delegate, and (B, C) a community liaison officer | Site Lead |
| 3 | Complete the checklists, photograph all equipment and nameplates, and record sources for every number | Site team |
| 4 | Score the site (Section 12) and state a recommendation | Technical Lead, Programme Manager |
| 5 | Submit to the PMO for the Gate 1 evidence pack; Research Panel reviews the measurement section | PMO |

**Rating key used throughout:** G = meets requirement; A = meets with conditions; R = does not meet or unknown and critical; N/A = not applicable. Unknown critical items default to R until evidenced.

## Common survey header (complete for each site)

| Field | Entry |
| --- | --- |
| Report ID | \[e.g. SSR-A1\] |
| Pilot | \[A / B / C\] |
| Candidate site name and county | \[ \] |
| GPS coordinates | \[ \] |
| Survey date(s) | \[ \] |
| Surveyors (name, role, licence no.) | \[ \] |
| Host representative and contact | \[ \] |
| Land or building owner (if different) | \[ \] |
| Weather and access conditions on the day | \[ \] |
| Photo log reference | \[ \] |

---

# Report A: Industrial Park, Energy Hub or Campus

**Purpose.** Confirm whether the candidate can host about 250 kWh of battery storage with existing or new PV, and test peak shaving, ToU shifting and net-metering optimisation against a defensible baseline.

## A1. Site and host profile

| Item | Entry | Rating |
| --- | --- | --- |
| Host type (factory, data centre, campus, other) | \[ \] |  |
| Operating pattern (shifts, days per week, seasonality) | \[ \] |  |
| Production-critical loads that must never be curtailed | \[list\] |  |
| Host willingness to sign Site Agreement and accept baseline period with storage idle | \[ \] |  |
| Ownership of land and building; owner consent needed | \[ \] |  |
| Insurer and lender constraints on battery installation | \[ \] |  |

## A2. Electrical infrastructure

| Item | Entry | Rating |
| --- | --- | --- |
| Supply voltage and connection point | \[ \] |  |
| Transformer ownership, rating (kVA), age and loading | \[ \] |  |
| Main switchboard: spare capacity, busbar rating, space for new breakers | \[ \] |  |
| Single-line diagram available and current | \[Yes / No\] |  |
| Earthing and lightning protection condition | \[ \] |  |
| Power quality issues (outages, sags, harmonics) | \[ \] |  |
| Backup generator and changeover arrangements | \[ \] |  |

## A3. Existing generation, storage and loads

| Item | Entry |
| --- | --- |
| Existing PV: capacity (kWp), inverter make and model, firmware, commissioning date, warranty terms | \[ \] |
| Inverter communication interface available (Modbus TCP/RTU, other) and whether it can be opened to third-party control without voiding warranty | \[ \] |
| New PV planned (kWp, roof or ground, structural check) | \[ \] |
| Existing storage | \[ \] |
| Major loads and controllable loads (HVAC, compressors, EV chargers, process) | \[ \] |
| Typical peak demand (kW) and base load (kW) | \[ \] |

## A4. Data availability (essential, per Feasibility Study Section 10)

| Data item | Requested | Received | Period and resolution | Quality |
| --- | --- | --- | --- | --- |
| Interval load data (target at least 12 months, 15 or 30 minute) | \[ \] | \[ \] | \[ \] | \[ \] |
| Electricity bills (12 months or more) | \[ \] | \[ \] | \[ \] | \[ \] |
| Tariff category and contract terms | \[ \] | \[ \] |  |  |
| PV generation data | \[ \] | \[ \] | \[ \] | \[ \] |
| Meter make, class, calibration record at grid connection | \[ \] | \[ \] |  |  |

**Tariff questions to answer (Feasibility Study Appendix B, Q1):** Is the customer on a ToU tariff? What are the peak, shoulder and off-peak prices and hours? Are there demand (kVA or kW) charges? \[ \]. Without a meaningful spread or demand charge, bill savings from peak shaving or shifting may be weak.

## A5. Grid interface and net-metering

| Item | Entry | Rating |
| --- | --- | --- |
| Kenya Power account and meter details | \[ \] |  |
| Current net-metering status (none / applied / approved) | \[ \] |  |
| EPRA written confirmation of eligibility and terms (needed before Gate 1) | \[Pending / Received\] |  |
| Interconnection requirements: protection, metering, anti-islanding | \[ \] |  |
| Kenya Power contact and application lead time | \[ \] |  |

Design sensitivity: test export credits below 50% (Charter risk register).

## A6. Proposed OpenEMS configuration

| Item | Proposal / entry |
| --- | --- |
| Controllers | Peak shaving, ToU shifting, self-consumption and feed-in control |
| Battery size | About 250 kWh (note Charter reference site is 100 kW PV plus 300 kWh; confirm size against measured load) \[ \] |
| Edge device location and mounting | \[ \] |
| Grid meter for OpenEMS and for Research Panel (separate or shared) | \[ \] |
| Devices to integrate: inverter, battery, meter (make, model, existing driver? Y/N, custom driver effort) | \[ \] |
| Override rule for critical processes | \[ \] |

## A7. Network and cybersecurity

| Item | Entry | Rating |
| --- | --- | --- |
| Local network available for Edge; separation from host IT/OT | \[ \] |  |
| Internet connectivity (type, reliability, bandwidth) | \[ \] |  |
| Host IT policy on remote access and third-party devices | \[ \] |  |
| Physical access control to Edge and battery room | \[ \] |  |

No remote connection until the independent audit is passed (Gate 3). Local data collection may begin earlier.

## A8. Safety, fire and environment

| Item | Entry | Rating |
| --- | --- | --- |
| Proposed battery location, ventilation, separation from occupied areas and fuel stores | \[ \] |  |
| Fire detection and suppression present | \[ \] |  |
| Insurer notified and response | \[ \] |  |
| Emergency access for responders; nearest fire station | \[ \] |  |
| Floor loading, flood and drainage risk | \[ \] |  |
| County and building permits likely required | \[ \] |  |
| End-of-life and decommissioning route for batteries | \[ \] |  |

## A9. Staff, neighbours and social factors

| Item | Entry |
| --- | --- |
| Staff briefing needs and operator trainees nominated (number) | \[ \] |
| Neighbouring businesses affected by works | \[ \] |
| Data sensitivity: production schedules and tariff terms treated as confidential | \[Agreed / Pending\] |
| Benefit-sharing choice (host keeps savings or shares) and effect on baseline | \[ \] |

## A10. Measurement and verification readiness

| Item | Entry | Rating |
| --- | --- | --- |
| Baseline period possible (storage idle or unmanaged) and its length | \[ \] |  |
| Weather, production and occupancy factors that affect normalisation | \[ \] |  |
| Meter accuracy check scheduled | \[ \] |  |
| Risk of confounding changes during pilot (new loads, tariff change) | \[ \] |  |

## A11. Scoring (weights proposed, to be agreed)

| Criterion | Weight | Score 1 to 5 | Evidence |
| --- | --- | --- | --- |
| 12+ months load, bill and meter data | \[15%\] | \[ \] |  |
| Representativeness (peak-heavy load, ToU or net-metering eligible) | \[15%\] | \[ \] |  |
| Host willingness and agreement readiness | \[15%\] | \[ \] |  |
| Interconnection and licensing path clarity | \[15%\] | \[ \] |  |
| Hardware compatibility and local service | \[10%\] | \[ \] |  |
| Safety and security | \[10%\] | \[ \] |  |
| Community and staff acceptance | \[10%\] | \[ \] |  |
| Replication potential | \[10%\] | \[ \] |  |
| **Weighted total** | 100% | \[ \] |  |

## A12. Findings, risks and recommendation

| Item | Entry |
| --- | --- |
| Key findings (max 5) | \[ \] |
| Red items and how to close them | \[ \] |
| Indicative site cost and break-even check (annual net benefit needed for 8-year payback; see Feasibility Study 5.5) | \[ \] |
| Recommendation | \[Shortlist / Reserve / Reject\] |
| Outstanding actions, owner, date | \[ \] |

**Sign-off:** Surveyor \[name, date\]; Technical Lead \[name, date\]; Host representative acknowledged \[name, date\].

---

# Report B: Rural Microgrid

**Purpose.** Confirm whether the candidate can host 50 to 100 kW PV with about 200 kWh battery on a long-line or isolated network, and measure loss reduction, reliability and self-consumption. This is the hardest site to evaluate and carries the most community exposure.

## B1. Site, operator and community profile

| Item | Entry | Rating |
| --- | --- | --- |
| Setting (village, estate, cooperative) and county | \[ \] |  |
| Network type: grid-connected on long feeder, mini-grid, or isolated | \[ \] |  |
| Defined operator (cooperative, estate, utility) and tariff arrangement, consistent with any EPRA mini-grid or permit requirement | \[ \] |  |
| Number of customers served and mix (households, businesses, institutions) | \[ \] |  |
| Land tenure for PV and battery site; lease or community consent | \[ \] |  |
| Existing diesel generation (kVA, hours, fuel use and cost) | \[ \] |  |
| Security situation (theft, vandalism) | \[ \] |  |

## B2. Network and load survey

| Item | Entry | Rating |
| --- | --- | --- |
| Feeder length, conductor type, voltage level, one-line sketch | \[ \] |  |
| Transformers on the feeder (number, kVA, loading) | \[ \] |  |
| Customer metering coverage (share metered, meter types, prepaid or post-paid) | \[ \] |  |
| Ability to build a before-and-after energy balance (input energy minus billed energy) | \[ \] |  |
| Voltage measurements at feeder end (minimum, at peak) | \[ \] |  |
| Outage history (frequency, duration, causes) over 12 months | \[ \] |  |
| Load profile estimate (evening peak, productive-use loads) | \[ \] |  |

Open question to resolve (Feasibility Study Appendix B, Q3): how can technical losses be separated from commercial losses (theft, unbilled use, metering error)? Record the method proposed: \[ \].

## B3. Proposed generation and storage

| Item | Entry |
| --- | --- |
| PV: roof or ground, area available, shading, soil and structural condition, indicative size 50 to 100 kW \[ \] | \[ \] |
| Solar resource data source and estimated yield | \[ \] |
| Battery location, about 200 kWh, protection from heat, dust, flooding, wildlife and lightning | \[ \] |
| Existing diesel set integration and offset measurement method (fuel meter, run hours) | \[ \] |
| Devices to integrate (make, model, existing OpenEMS driver? Y/N) | \[ \] |
| Spare parts and local service availability (nearest technician, travel time) | \[ \] |

## B4. Connectivity and cybersecurity

| Item | Entry | Rating |
| --- | --- | --- |
| Mobile network coverage and operators at site (signal strength, measured) | \[ \] |  |
| Fallback options (second SIM, satellite) | \[ \] |  |
| Reliance on Edge local control and local caching; data-gap threshold proposed | \[ \] |  |
| Physical security of Edge device and cabinet | \[ \] |  |
| Local operator able to reset and check the system | \[ \] |  |

Poor connectivity is rated high likelihood, low impact in the Feasibility Study provided Edge local control is proven at commissioning.

## B5. Community consultation record

Required before site selection and before procurement (Stakeholder Engagement Plan, Section 7).

| Item | Entry |
| --- | --- |
| Community leaders and institutions consulted (administration, cooperative, school, clinic, faith and women's groups) | \[ \] |
| Separate sessions held for women, youth, small business owners | \[Y/N, dates, numbers\] |
| Participants (numbers by gender and age group) | \[ \] |
| What was explained: research pilot, no guaranteed savings, ownership, end-of-pilot, data use | \[ \] |
| Concerns and expectations raised, and responses | \[ \] |
| Documented informed agreement obtained | \[Yes / No / Pending\] |
| Right to decline explained and any opposition | \[ \] |
| Languages used (English, Kiswahili, local language) | \[ \] |
| Community liaison officer identified | \[ \] |
| Grievance channels agreed (at least two) | \[ \] |

Host agreement must state that the pilot causes no disconnection or price rise for customers served. Confirm with Kenya Power or the operator: \[ \].

## B6. Regulatory and grid interface

| Item | Entry | Rating |
| --- | --- | --- |
| Licence or permit needed for BESS and mini-grid operation (EPRA written position) | \[Pending / Received\] |  |
| Interconnection with Kenya Power if grid-connected | \[ \] |  |
| County permits, land and environmental approvals | \[ \] |  |
| Data sharing with Kenya Power on feeder and transformer data | \[ \] |  |

## B7. Safety, environment and data

| Item | Entry | Rating |
| --- | --- | --- |
| Fire safety plan and distance from dwellings; emergency response agreed with local responders | \[ \] |  |
| Lightning, flood and wildlife risks and protections | \[ \] |  |
| Fencing, signage and risk to children and livestock during works | \[ \] |  |
| Battery handling, waste and decommissioning route | \[ \] |  |
| Household consumption treated as personal data; aggregation and consent approach | \[ \] |  |

## B8. Scoring (weights proposed, to be agreed)

| Criterion | Weight | Score 1 to 5 | Evidence |
| --- | --- | --- | --- |
| Data availability (desirable, not essential) | \[15%\] | \[ \] |  |
| Representativeness (long lines, diesel, measurable loss) | \[15%\] | \[ \] |  |
| Host willingness plus community consent | \[15%\] | \[ \] |  |
| Interconnection and licensing path clarity | \[15%\] | \[ \] |  |
| Hardware compatibility and local service | \[10%\] | \[ \] |  |
| Safety and security | \[10%\] | \[ \] |  |
| Community acceptance and inclusion | \[10%\] | \[ \] |  |
| Replication potential | \[10%\] | \[ \] |  |
| **Weighted total** | 100% | \[ \] |  |

## B9. Findings, risks and recommendation

| Item | Entry |
| --- | --- |
| Key findings (max 5) | \[ \] |
| Red items and how to close them | \[ \] |
| Benefit case: bills, diesel displaced, reliability, loss reduction (state which can be measured) | \[ \] |
| Recommendation | \[Shortlist / Reserve / Reject\] |
| Outstanding actions, owner, date | \[ \] |

**Sign-off:** Surveyor \[name, date\]; Technical Lead \[name, date\]; Community liaison \[name, date\]; Site operator acknowledged \[name, date\].

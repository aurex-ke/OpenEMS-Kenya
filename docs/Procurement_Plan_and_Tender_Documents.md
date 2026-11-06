# Procurement Plan and Tender Documents

## 1. Purpose and bottom line

This document sets out how the programme will buy the equipment and services for Pilots A, B and C, and provides the tender documents to do it. It turns the Charter (Section 17, Financial Governance), the Feasibility Study (D1), the Technical Specification (B4), the Interoperability and Device Compatibility Register (B6), the Cybersecurity Plan (B7) and the Regulatory Compliance Assessment (B5) into one procurement baseline.

**Bottom line.** Procurement is where the programme's three hardest rules meet: *compatibility testing before award*, *no remote access before Gate 3*, and *local service and capacity as a deliverable*. The plan is built around them:

1. **Compatibility is a gate, not a score.** A device that fails L3 lab testing or lacks written permission for third-party control under warranty is disqualified, however cheap (B4 Section 8, B6 Section 2.2).
2. **Two-stage tendering.** Stage 1 pre-qualifies vendors on documents, local service and commitments. Stage 2 invites a shortlist to bid and to supply units for lab testing.
3. **Award is conditional on the gates.** Bids can be evaluated and a preferred bidder named before Gate 2, but contracts become effective and installation funds are released only at Gate 2 (Month 8).
4. **Cost is judged as total cost of ownership,** including integration, service and spares, because the Feasibility Study shows that the real cost of open-source is integration and skills, not licences.
5. **Open by default.** Notices, criteria and award summaries are published, with commercial data protected. Security and local-service requirements are written into every tender.

**Critical-path warning.** Installation runs in Months 7 to 12 and Gate 3 needs commissioning, a passed audit and recorded baselines by Month 12. Battery, inverter and charger lead times are unknown. If tender and testing slip, commissioning slips, and because the evaluation needs at least 12 months of validated data, **late commissioning directly reduces evidence**. Section 13 gives a schedule and a stop-or-extend trigger.

## 2. Document control and relationships

**Owner:** Procurement Lead (README C1). **Contributors:** Technical Lead, software engineer, Cybersecurity and Data Protection Officer, finance lead, Research Lead (meters), Site Leads, Kenya Power grid engineer (TWG), counsel. **Approval:** Programme Director recommends and the Steering Committee approves the plan at Gate 1. Tender issue and award follow the thresholds in Section 6. Changes follow Charter Section 20 change control.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 8, 16, 17, 20) | Budget, contingency, procurement thresholds, gates, change control |
| Feasibility Study (D1, Sections 4.3, 5, 12) | Compatibility approach, budget reconciliation issue, Gate 1 conditions |
| Technical Specification per Site (B4, Sections 3.3, 5 to 8) | Equipment requirements, device lists, acceptance tests, procurement requirements |
| Interoperability and Device Compatibility Register (B6) | Compatibility levels, test method, vendor commitments, pass and fail rules |
| Cybersecurity Plan (B7, Appendix A) | Security requirements for tenders (must-haves and should-haves) |
| Regulatory Compliance Assessment (B5, Sections 5.5, 5.10) | Licensed contractors, interconnection acceptance, duties and taxes, public procurement rules |
| MoU and Site Agreement templates | Equipment title, insurance, host obligations, conditions precedent |
| Stakeholder Engagement Plan (Section 6.5) | Pre-procurement market briefing, no vendor editorial control, upstream contributions |
| Site Survey Reports (B3) | Existing devices and site constraints that define scope |
| Budget and cost tracker (C2), Installation plan (C3), Configuration baseline (C4), Site acceptance tests (C5), HSE plan (C6) | Receive the contracts, delivery dates, versions and acceptance criteria this plan produces |

## 3. Procurement principles

These extend the Charter governance principles to buying.

| Principle | What it means in practice |
| --- | --- |
| Competitive and fair | Competitive procurement for hardware and services (Charter Section 17). Same information to all bidders at the same time. Single-source buying only with written justification approved at the threshold level |
| Compatibility before award | Every shortlisted inverter, battery, meter and charger is tested against the pinned OpenEMS release before award. Failure disqualifies |
| Local service as a requirement | Local service route, response time and spares in Kenya are pass or fail items for devices the programme cannot replace itself |
| Safety and security before speed | Safety certification, written security commitments and no undocumented remote access are mandatory. Remote access remains disabled until Gate 3 |
| Open interfaces preferred | Published, documented protocols score above proprietary links (B4 design rule 6). No vendor lock-in through closed protocols or licence fees on the control layer |
| Total cost, not unit price | Evaluation includes integration effort, service, spares, warranty and end-of-life, not only purchase price |
| Independence of evaluation | Suppliers and funders have no editorial control over evaluation findings. Vendors may not sit on evaluation panels |
| Integrity | Conflicts of interest disclosed to the PMO. No improper inducements (Bribery Act, 2016). Cooling-off for anyone with a vendor relationship |
| Transparency | Tender notices, evaluation criteria and award summaries published, subject to confidentiality and security review |
| Proportionate | Process scales with value and risk. Small items use quotations, large safety-critical items use full tender |

## 4. Procurement strategy

### 4.1 What is being bought

| Package | Content | Pilots | Type | Risk driver |
| --- | --- | --- | --- | --- |
| P1 | Edge computers, networking and security equipment (routers, firewalls, switches, enclosures, UPS or supercapacitor backup) | A, B, C | Goods | Hardening, remote-site resilience, dual-SIM (B) |
| P2 | Metering and research measurement: revenue-grade meters, research logger, time source, transformer and voltage monitoring | A, B, C | Goods and services | Accuracy, calibration, Kenya Power acceptance |
| P3 | PV equipment (modules, inverters, mounting) for new PV | A (if new), B | Goods | Inverter openness and warranty |
| P4 | Battery systems: battery, BMS, battery or hybrid inverter, containers and enclosures | A, B, optional C | Goods | Safety certification, driver availability, grid-forming (B), lead time |
| P5 | EV chargers (about 10 to 20 fast chargers) and optional charger back-office link | C | Goods | OCPP version, in-session power limiting, vendor cooperation |
| P6 | Installation, civil works, electrical work and commissioning support by licensed contractors | A, B, C | Works | Licences, safety, schedule |
| P7 | Services: independent security audit, lab testing support, training delivery, community liaison, translation and printing, insurance, M&V support | All | Services | Independence, budget not yet itemised |
| P8 | Existing-equipment remedies (for example inverter firmware access or gateway) where Pilot A or C survey shows a red item | A, C | Goods or services | Warranty, cost, only if needed |

**Lots.** P1 to P5 are split by pilot where the site design differs, with a framework option so that identical items (Edge computers, meters, routers) are bought once and call-off priced per site. Lots may be awarded to different bidders. Bidders may bid for one or several lots, and combined discounts are allowed but each lot is scored on its own.

### 4.2 Make, buy or donate

The programme buys equipment. Vendor loans of test units and in-kind support are welcomed for the lab campaign (B6 Appendix A, question 6) but never as a condition of award, and are declared in the evaluation record to avoid influence. Donated or discounted equipment is accepted only if it meets the same technical, compatibility, security and service requirements.

### 4.3 Route to market

| Stage | Name | What happens | Output | Timing |
| --- | --- | --- | --- | --- |
| 0 | Market briefing | Public briefing to vendors, installers and the OpenEMS community on requirements, compatibility testing and local service (Stakeholder Plan 6.5). Draft criteria shared for comment | Questions log, vendor interest list | Months 2 to 3 |
| 1 | Pre-qualification (RFPQ) | Vendors submit documents, references, local service evidence and answers to the vendor and security questionnaires (Appendix B). Scored pass or fail plus shortlist ranking | Shortlist per package, `CAND` and `DOCS` entries in B6 | Months 3 to 5 |
| 2 | Invitation to bid (RFP for goods, RFQ for small items) | Shortlisted vendors receive the full tender (Appendix C), supply test units, and submit technical and financial bids | Bids, loan units | Months 5 to 7 |
| 3 | Compatibility and security testing | Lab test campaign at L1 to L3 (B6 Section 6). Results approved by the TWG | `PASS`, `COND` or `FAIL` per device | Months 5 to 8 |
| 4 | Evaluation and preferred bidder | Technical gate, then scoring, then financial opening and ranking. Clarifications and negotiation within limits | Evaluation report, preferred bidder per lot | Months 7 to 8 |
| 5 | Gate 2 and award | Steering Committee releases installation funds. Contracts signed and issued | Signed contracts, notice to proceed | Month 8 |
| 6 | Delivery and acceptance | Factory or lab acceptance, delivery, site acceptance (L4), commissioning | Acceptance certificates | Months 8 to 12 |
| 7 | Close-out | Warranty and service tracking, spares, end-of-life, lessons learned | Close-out report at Gate 5 | Months 13 to 24 |

**Rule.** The tender is issued only after the Steering Committee approves this plan at Gate 1. Stages 0 and 1 may start earlier because they commit no money.

### 4.4 Early-order option

If bidders quote lead times that put Gate 3 at risk, the Programme Director may recommend to the Steering Committee a **conditional early order** for long-lead items (most likely battery systems and chargers) before Gate 2. This needs: a `PASS` or `COND` result at L3, a cancellation clause with a capped liability of [X]% of lot value, and Steering Committee approval as a contingency or reallocation under Charter Section 20. It is an exception, not the default.

## 5. Budget and cost control

### 5.1 Envelope

The indicative programme budget is **KSh 50 to 100 million (about USD 400 to 800k)**, with sites estimated at USD 50 to 150k each, in 2026 prices and with inflation assumed at about 5% a year. These figures are indicative and not yet validated.

**Reconciliation issue carried from the Feasibility Study (5.1).** Three sites at USD 50 to 150k total USD 150 to 450k, below the USD 400 to 800k envelope. The gap must be itemised before Gate 1 as programme-level costs (PMO, security audit, evaluation, training, Backend, community liaison, central contingency). This plan cannot fix package budgets until that reconciliation is done.

### 5.2 Reference cost structure applied to procurement

The Charter reference split (for a 100 kW PV plus 300 kWh site) is a guide only. Applied to the envelope as an illustration, from Feasibility Study 5.2:

| Category | Share | USD 400k | USD 800k | Mainly bought through |
| --- | --- | --- | --- | --- |
| Hardware (PV, BESS, inverters, meters) | 40% | 160k | 320k | P2, P3, P4, P5 |
| Software and integration | 20% | 80k | 160k | P1, P7 and driver development |
| First-year O&M | 15% | 60k | 120k | P6 service terms, P7 |
| Installation and civil works | 10% | 40k | 80k | P6 |
| Contingency (held centrally) | 10% | 40k | 80k | Not procured |
| Training and capacity building | 5% | 20k | 40k | P7 |

### 5.3 Package budget table (to be completed after reconciliation)

| Package | Pilot A | Pilot B | Pilot C | Total | Source line |
| --- | --- | --- | --- | --- | --- |
| P1 Edge and network | KSh [ ] | KSh [ ] | KSh [ ] | KSh [ ] | Software and integration |
| P2 Metering and measurement | KSh [ ] | KSh [ ] | KSh [ ] | KSh [ ] | Hardware |
| P3 PV | KSh [ ] | KSh [ ] | n/a | KSh [ ] | Hardware |
| P4 Battery | KSh [ ] | KSh [ ] | KSh [ ] (optional) | KSh [ ] | Hardware |
| P5 Chargers | n/a | n/a | KSh [ ] | KSh [ ] | Hardware |
| P6 Installation | KSh [ ] | KSh [ ] | KSh [ ] | KSh [ ] | Installation |
| P7 Services | KSh [ ] | KSh [ ] | KSh [ ] | KSh [ ] | Various |
| P8 Remedies | KSh [ ] | n/a | KSh [ ] | KSh [ ] | Contingency, if approved |

### 5.4 Cost control rules

- **Contingency** is held centrally. Release needs a Programme Director recommendation and Steering Committee approval (Charter Section 17). The Executive Summary says 10 to 20% while the reference split carries 10%. The plan must state which applies before tender (open item 4).
- **Budget reallocation.** Reallocation within a site up to 5% is a Programme Director decision. Any reallocation between sites, any contingency use and any increase to the total need Steering Committee approval (Charter Section 20).
- **Currency and inflation.** Bids may be priced in USD or KSh. The tender states the exchange-rate reference and a price-adjustment rule [fixed price for [90] days, then adjustment capped at [x]%]. The PMO reports exchange-rate exposure quarterly (Charter Section 17).
- **Duties and taxes.** Duty and VAT treatment of imported batteries, inverters and chargers, and any relief for research or renewable equipment, is confirmed with advisers before price comparison [confirm, B5 5.10]. Bids are compared on a stated basis (delivered duty paid or duty excluded) so they are like for like.
- **Sensitivity.** Battery cost ±20% is tested in the techno-economic model. A lot priced more than [x]% above estimate goes back to the PMO before award.
- **Replication cost.** Bids are tagged so the PMO can separate pilot-specific cost from the cost a commercial replicator would pay (Feasibility Study 5.4).

## 6. Governance, thresholds and approvals

### 6.1 Approval thresholds

The Charter proposes thresholds to be confirmed with funders. They are reproduced here, with the procurement action each triggers.

| Value of contract or package | Approval | Method (proposed) |
| --- | --- | --- |
| Below KSh [X] | Programme Director | Three written quotations, award record |
| KSh [X] to [Y] | Two PMO signatories | Request for quotation to at least [3] qualified vendors, evaluation record |
| Above KSh [Y] | Steering Committee | Full two-stage tender with pre-qualification, compatibility testing and published award |

Given a total envelope of KSh 50 to 100 million, battery systems, chargers, installation and likely PV and metering lots are expected to exceed KSh [Y] and so go to the Steering Committee. This expectation must be tested once [X] and [Y] are fixed. **Contract splitting to avoid a threshold is prohibited.**

### 6.2 Roles and decision rights

| Decision or activity | SteerCo | Programme Director | PMO and Procurement Lead | Evaluation Committee | TWG | Cybersecurity Officer | Kenya Power and regulators |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Approve procurement plan | A | R | R | I | C | C | C |
| Issue tender | I | A | R | I | C | C | I |
| Technical compliance and compatibility result | I | I | C | C | R, A | C | C |
| Security compliance result | I | C | C | C | C | R, A | C |
| Evaluation and ranking | I | C | C | R, A | C | C | I |
| Award above threshold Y | A | R | R | C | C | C | I |
| Contract variation beyond tolerance | A | R | R | I | C | C | I |
| Contingency release | A | R | R | I | I | I | I |

R = Responsible, A = Accountable, C = Consulted, I = Informed.

### 6.3 Evaluation Committee

| Seat | Member | Voting |
| --- | --- | --- |
| Chair | Programme Manager or delegate independent of the bid | Yes |
| Technical evaluator | Technical Lead or delegate | Yes |
| Software and integration evaluator | Software engineer | Yes |
| Security evaluator | Cybersecurity and Data Protection Officer | Yes |
| Finance evaluator | Finance lead | Yes |
| Measurement evaluator (P2 only) | Research Lead delegate | Yes |
| Grid evaluator | Kenya Power grid engineer | Advisory |
| Site evaluator | Relevant Site Lead | Advisory |
| Observer | EPRA or funder representative, by invitation | Observer |
| Secretary | PMO procurement officer | No |

**Rules.** At least [4] voting members score each bid independently before the committee meets. Each member signs a declaration of interest and confidentiality. Anyone with a commercial relationship with a bidder in the past [24] months withdraws. Vendors, installers and their staff never sit on the committee or on the TWG decision for their own device.

## 7. Technical requirements by package (summary)

The authoritative requirements are in B4 Section 3.3 and B6 Section 4. This table is the tender summary. In any conflict B4 and B6 prevail.

| Package | Must have (fail if missing) | Should have |
| --- | --- | --- |
| P1 Edge and network | Industrial rating, watchdog, clean shutdown on power loss, runs pinned OpenEMS release without fault for [14] days burn-in. VPN-capable router and firewall, VLAN segmentation, no open inbound ports by default, default credentials removable | Secure boot or equivalent, disk encryption where practical, dual-SIM or mobile failover (Pilot B) |
| P2 Metering | Revenue-grade, bidirectional, Class 0.5S or better where available [confirm with Kenya Power], Modbus or pulse output, calibration certificate, write access to configuration protected | Update rate suited to control, time synchronisation |
| P3 PV inverters | Read of power, energy, status, alarms. Remote active-power limit over an open interface. Written vendor permission for third-party control under warranty. Grid-code acceptance by Kenya Power | Reactive power control |
| P4 Battery | Lithium-based with integrated BMS reporting state of charge, power limits, alarms, temperature. Safety certification to a named standard [IEC or UL, confirmed with Kenya Power and insurer]. Cannot be driven outside BMS limits. Remote active-power setpoint, documented register map, anti-islanding, defined behaviour on loss of communication. Rated for local ambient conditions. Local warranty and service | Grid-forming mode (needed if Pilot B is isolated or a mini-grid), state of health reporting, ramp-rate control |
| P5 Chargers | OCPP [version to be fixed] or documented vendor interface. **Dynamic power limiting during a session.** Status and session logs. Defined fallback limit on loss of link. Vendor named contact and cooperation on integration | Phase balancing, signed firmware images, OCPP security profile |
| P6 Installation | Licensed electrical contractors and, where required, EPRA-recognised solar contractors [confirm]. Approved safety plan. Compliance with Kenyan standards and Kenya Power requirements | Local labour and training of local technicians |
| P7 Services | Independence from vendors and integrators for the security audit. Relevant sector experience. Named key staff | Local presence |

**Automatic disqualifiers (any package, from B6 Section 4 and B7 Section 6.4).** Control cannot be exercised without voiding warranty. No documented protocol and the vendor will not provide one. Hard-coded credentials that cannot be removed or isolated. No local service route in Kenya for a device the programme cannot replace itself. Undocumented or permanent vendor remote-access path. Vendor refuses written confirmation on remote access and firmware updates.

## 8. Evaluation methodology

### 8.1 Step 1: Administrative compliance (pass or fail)

Complete submission, signed declarations, eligibility, valid registration and tax compliance [documents to be listed after counsel advice], bid validity, bid security where required, no conflict of interest.

### 8.2 Step 2: Technical and compatibility gate (pass or fail)

| Gate item | Evidence |
| --- | --- |
| Meets all must-have requirements in Section 7 | Compliance matrix, datasheets, certificates |
| Compatibility result of `PASS` or `COND` at L3 in the lab, with conditions costed | Signed B6 test record approved by the TWG |
| Written permission for third-party control under warranty | Vendor letter (B6 Section 9) |
| Written security commitments with no "no" on a must-have in B7 Appendix A, unless the Cybersecurity Officer approves a documented compensating control | Completed questionnaire |
| Local service route, response time and spares in Kenya | Service agreement, agent letter, spares list |
| Safety certification | Certificates for the named standard |

Bids failing the gate are not scored. A `COND` result with open conditions is carried forward only if the condition owner, cost and due date are recorded and the cost is added to the bid price for comparison.

### 8.3 Step 3: Weighted scoring (technical bids passing the gate)

Proposed weights, to be agreed by the Steering Committee at Gate 1. Each criterion is scored 0 to 5 and multiplied by its weight.

| Criterion | What is assessed | Proposed weight |
| --- | --- | --- |
| Technical quality and openness | Documentation, open protocols, control functions beyond the minimum, test performance (response time, accuracy) | [20%] |
| Integration effort and driver route | Route R1 to R5 (B6 Section 5), custom driver effort size, maintenance and upstream plan | [15%] |
| Local service and spares | Response time, technicians in Kenya, spares held, training offered, track record | [20%] |
| Security and firmware policy | Hardening, update policy, vulnerability disclosure, encryption options, logging | [10%] |
| Delivery and schedule | Lead time against the Gate 3 schedule, delivery risk, installation plan | [10%] |
| Warranty, lifetime and end-of-life | Warranty length and scope, throughput limits, take-back, disposal route | [10%] |
| Price and total cost of ownership | Evaluated cost score from Section 8.4 | [15%] |
| **Total** | | **100%** |

Technical scoring is completed and signed **before** financial envelopes are opened.

### 8.4 Total cost of ownership

Evaluated price over the pilot period and a stated replication horizon [x years]:

> Evaluated cost = bid price delivered + custom driver and integration cost + conditional items from `COND` results + first-year O&M and spares + estimated service travel and downtime cost + end-of-life cost − salvage value (if the title transfers to a host)

Price score = 5 × (lowest evaluated cost ÷ bidder's evaluated cost). Abnormally low bids (below [x]% of estimate or of the median) must be explained in writing and may be rejected if they put delivery, safety or service at risk.

### 8.5 Award rule

Award goes to the highest-ranked bidder passing the gate, subject to: Steering Committee approval above threshold Y, Gate 2 funds release, satisfactory contract terms, and any outstanding `COND` items closed or costed. A reserve bidder is named for each lot so a failed or withdrawn award does not restart the process.

### 8.6 Clarification, negotiation and fairness

Clarifications go to all bidders through the Procurement Lead, in writing. Negotiation after ranking is limited to delivery, service terms, conditions closure and price reductions. Bidders may not change technical content after the closing date. Debriefs are offered to unsuccessful bidders, and a challenge procedure is stated in the tender (Appendix C).

## 9. Local service and capacity requirements

Local service is a delivery risk, not a courtesy. Proposed minimums, to be confirmed at Gate 1:

| Requirement | Pilot A | Pilot B | Pilot C |
| --- | --- | --- | --- |
| Service response time (remote diagnosis) | [x] hours | [x] hours | [x] hours |
| On-site response time | [x] working days | [x] working days (remote location, state travel time) | [x] hours (public site) |
| Technician in Kenya trained on the supplied product | Required | Required | Required |
| Spares held in Kenya | Critical spares list | Spares kit at or near site | Charger modules and communication boards |
| Training for local operators and technicians | Included | Included, with trained backup | Included |
| Documentation | English, Kiswahili summaries for operator procedures where relevant | Same | Same |

Bidders state their Kenyan agent, workshop location and staff. A foreign supplier without a local partner must name a local installer and service partner and attach their commitment letter. Bids that rely on foreign-only support for a device the programme cannot easily replace fail the gate.

## 10. Compatibility testing within the procurement

The test method, levels and records are in B6. This section ties them to the tender.

| Step | Procurement action |
| --- | --- |
| 1 | The tender names the pinned OpenEMS release for the test campaign [version] and the required protocols and OCPP version |
| 2 | Each shortlisted bidder supplies one test unit of each offered model, with the firmware to be delivered, by [date]. Units are returned or purchased as stated in the tender |
| 3 | The TWG tests at the lab (T-COM and class tests, B6 Section 6.2). Riskiest devices first |
| 4 | Results are recorded per B6 Section 10.2 and are version-pinned. A firmware change after test needs a delta test (B6 10.3) |
| 5 | A `FAIL` disqualifies. The bidder may offer an alternative device once, within [10] working days, if the schedule allows |
| 6 | Bidders may not influence the test result, and testers are independent of bidders |
| 7 | Site re-verification at L4 is a contract acceptance condition, not a tender stage |

**Where real hardware is unavailable** (for example a multi-charger test), simulators are rated no higher than L1 and the limits are recorded (B6 Sections 6.1 and 15 item 8). The tender states that award for chargers requires a real in-session power-limit test.

## 11. Contract framework

### 11.1 Contract types

| Package | Contract form (proposed) |
| --- | --- |
| P1 to P5 | Supply contract with delivery, factory acceptance, warranty and service schedule. Framework terms for call-off where several sites buy identical items |
| P6 | Works contract with the licensed contractor, fixed price per site with a defined change process |
| P7 | Services contracts (audit, training, community liaison, M&V support) with deliverables and independence clauses |

All contracts are signed by the legal entity named at Gate 0. If no entity is named, **no contract can be signed** (Feasibility Study risk 11, B5 5.10).

### 11.2 Key terms (Appendix E gives the checklist)

| Topic | Term (proposed) |
| --- | --- |
| Equipment title | Follows the site agreement and Schedule 4: Programme Lead, funder or named asset-holder during the pilot, then transfer or removal at closure |
| Delivery and risk | Delivery terms stated (for example DAP site) with risk passing on acceptance |
| Acceptance | Factory or lab acceptance, then site acceptance tests (B4 5.5, 6.7, 7.6) at L4, witnessed by the Site Lead, host and where agreed Kenya Power and EPRA |
| Payment | Milestone-based: [x]% advance against security, [x]% on delivery, [x]% on site acceptance, [x]% on release of retention after Gate 3 and defects period |
| Security for performance | Performance security of [10]% of the contract value, and an advance-payment guarantee if an advance is paid |
| Delay | Liquidated damages of [x]% per week capped at [x]%, because schedule slip reduces evidence |
| Warranty | Minimum warranty [x years] with local service. **Control by OpenEMS must not void the warranty**, confirmed in writing |
| Firmware and updates | Version held. Updates announced in advance, tested off site first, with rollback (B7 6.4) |
| Remote access | No vendor remote access unless specified, time-bound, approved by the Cybersecurity Officer and logged. Permanent paths are prohibited. Remote access to the site is disabled until Gate 3 |
| Documentation and openness | Register maps, protocol documents and configuration data supplied. The programme may publish integration code and configuration under Apache 2.0 without disclosing vendor confidential data |
| Vulnerabilities | Vendor notifies the Cybersecurity Officer of known vulnerabilities within [x] days |
| Licensing | No licence fee for the control layer. Any vendor software must have a licence that allows pilot use and does not restrict publication of evaluation results |
| Evaluation independence | Vendors have no editorial control over results. Performance claims by vendors are not made without Research Lead approval |
| Data | Vendors do not collect or retain programme or personal data unless the contract and a data processing agreement say so (Data Protection Act, 2019) |
| Insurance | Transit and public liability insurance with certificates before delivery |
| Safety | Compliance with the site safety plan, licensed personnel, incident reporting within [24] hours |
| Spares and service | Service levels and spares list as part of the contract. Penalty or termination for repeated breach |
| End of life | Take-back or compliant disposal and data erase |
| Integrity | Bribery Act, 2016 compliance, conflict disclosure, audit and access rights for funders |
| Termination | For breach, insolvency or loss of a licence, and by the programme if a gate is not passed. Capped termination costs if Gate 2 is not approved |
| Disputes | Kenyan law, escalation, mediation, then arbitration under the Arbitration Act, 1995 [forum to be confirmed with counsel] |

### 11.3 Conditions precedent

Contracts take effect only when: Gate 2 funds are released, host agreements and conditions precedent are satisfied (Site Agreement Section 3), Kenya Power design acceptance is received where required, and insurer acceptance of the battery installation is recorded.

## 12. Risk management in procurement

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| PR1 | Few local vendors with OpenEMS-compatible, serviceable devices, leaving thin competition | M | M | Early market briefing, accept regional agents with local partners, loan-unit campaign, framework call-off | Procurement Lead |
| PR2 | Compatibility test failure on the preferred device late in the process | M | H | Test riskiest devices first, keep a reserve bidder per lot, allow one alternative device | Technical Lead |
| PR3 | Vendor refuses written permission for third-party control | M | H | Make it a pre-qualification item, not a late discovery | Procurement Lead |
| PR4 | Long lead times push commissioning past Month 12 | M | H | Lead time scored, early-order option, delivery milestones, liquidated damages | Programme Manager |
| PR5 | Budget does not reconcile with bids | M | M | Itemise programme costs before Gate 1, price sensitivity, scope options in tender | Programme Manager |
| PR6 | Currency movement and duties raise costs | M | M | Price basis and adjustment rule in tender, duty advice, contingency | Finance lead |
| PR7 | Conflict of interest or perceived vendor bias | L | H | Declarations, independent panel, cooling-off, publish criteria and award | Programme Director |
| PR8 | No contracting entity or equipment title agreed at tender time | M | H | Decide at Gate 0, make it a gate for tender issue | Programme Sponsor |
| PR9 | Public procurement law applies and constrains method or timing | L to M | M | Counsel review once entity and funders are known | Programme Manager |
| PR10 | Vendor insecure by default (credentials, remote path) | M | H | B7 Appendix A must-haves, acceptance checklist, audit scan | Cybersecurity Officer |
| PR11 | Installer without proper licence or competence | L | H | Licence check at pre-qualification, safety plan approval, site supervision | Site Leads |
| PR12 | Security work (audit, tools) under-budgeted | M | M | Itemise in budget reconciliation (B7 C4) | Programme Manager |
| PR13 | Pilot B spares or service delays in a remote location | H | M | Spares kit, service SLA, trained local operator, travel time in scoring | Site Lead (B) |

Procurement risks are merged into the live Risk Register (README A6). Any failed compatibility test on a selected device is a Charter escalation trigger.

## 13. Schedule

Months are relative to programme start and follow the Charter gates.

| Activity | Months | Output | Gate link |
| --- | --- | --- | --- |
| Name contracting entity and procurement thresholds | 0 to 1 | Entity decision, X and Y confirmed | Gate 0 |
| Counsel review of this plan and tender templates | 1 to 3 | Reviewed plan | Gate 1 input |
| Market briefing to vendors | 2 to 3 | Questions log, vendor list | |
| Vendor questionnaire and pre-qualification | 3 to 5 | Shortlists, `DOCS` entries | |
| Budget reconciliation and package budgets | 2 to 4 | Package budget table (5.3) | Gate 1 |
| **Steering Committee approves procurement plan** | **4 to 6** | **Approved plan** | **Gate 1** |
| Issue invitation to bid, bid period [4] weeks | 5 to 7 | Bids, test units | |
| Compatibility and security testing | 5 to 8 | Test records, D4 report | Gate 2 input |
| Evaluation and preferred bidder | 7 to 8 | Evaluation report | |
| **Award approval and installation funds release** | **8** | **Contracts effective** | **Gate 2** |
| Factory or lab acceptance, delivery | 8 to 11 | Acceptance certificates | |
| Installation, site acceptance, commissioning | 9 to 12 | Commissioning certificates | Gate 3 |
| Warranty and service tracking | 13 to 24 | Service log | Gate 4 |
| Close-out and asset handover | 22 to 24 | Close-out report | Gate 5 |

**Compression warning.** The window from award in Month 8 to Gate 3 in Month 12 is four months for delivery, installation, commissioning, baselines and the independent audit. If bidders' lead times exceed [x] weeks, the Programme Director raises the early-order option (4.4) or the stop-or-extend rule agreed in advance (Feasibility Study 8.1) at the next PMO review.

## 14. Roles

| Role | Procurement responsibility |
| --- | --- |
| Steering Committee | Approves plan, thresholds, weights, awards above Y, contingency use, early order |
| Programme Director | Recommends award, signs within delegated limits, owns regulator and Kenya Power approvals |
| Programme Manager and PMO | Owns budget control, contract management, risk and change log |
| Procurement Lead | Runs the process, owns tender documents, bidder communications, records |
| Finance lead | Price evaluation, payment control, duty and exchange-rate treatment |
| Technical Lead and TWG | Requirements, compatibility testing, technical evaluation, acceptance |
| Software engineer | Driver route assessment, test runs, integration effort estimate |
| Cybersecurity and Data Protection Officer | Security criteria, vendor commitments, security evaluation, audit procurement |
| Research Lead and Panel | Meter and measurement requirements and accuracy criteria |
| Site Leads | Site constraints, installation supervision, safety, spares logistics |
| Kenya Power grid engineer | Grid-code, protection, metering and acceptance advice |
| Counsel | Review of tender terms, contracts and procurement-law position |
| University partner | Lab support for testing where agreed, student involvement, training |

## 15. Publication and transparency

- Tender notices, pre-qualification criteria, evaluation criteria and weights are published in the open repository and on [channels to be named].
- Award summaries are published with winning bidder, lot, contract value and criteria outcome. Commercially sensitive pricing detail is withheld where the tender says so.
- Compatibility results, including failures, are published after the security and privacy review (B6 Section 10.2), consistent with the open-by-default principle.
- Procurement records (declarations, score sheets, clarification log, award decision) are kept for [x] years and available to funders and auditors (Charter Section 17).
- Debriefs are offered to unsuccessful bidders. A complaint route and timelines are stated in the tender.

## 16. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Name the contracting entity and decide equipment title | Tender issue, all contracts | Programme Sponsor |
| 2 | Confirm threshold values X and Y with funders | Approval routes | Programme Director |
| 3 | Confirm whether public procurement law applies, and its method and timing rules | Tender method | Counsel, Programme Manager |
| 4 | State the contingency policy (10% or 10 to 20%) and reconcile the budget | Package budgets | Programme Manager |
| 5 | Fix the OpenEMS release for testing and the OCPP version for Pilot C | Tender specification | Technical Lead |
| 6 | Name the battery safety standard accepted by Kenya Power and the insurer | P4 criteria | Site Leads |
| 7 | Meter class and calibration requirement | P2 criteria | Technical Lead, Research Lead |
| 8 | Pilot B topology (grid-connected, mini-grid, isolated), which sets battery inverter requirements | P4 for Pilot B | Technical Lead |
| 9 | Duty, VAT and relief treatment of imported equipment | Price basis | Finance lead |
| 10 | Agree weights and scoring scale at Gate 1 | Evaluation | Steering Committee |
| 11 | Agree local service minimums per pilot | P1 to P5 criteria | Technical Lead, Site Leads |
| 12 | Itemise security audit and training budget lines | P7 | Programme Manager |
| 13 | Decide whether vendor loan units are accepted and how declared | Testing | Procurement Lead, TWG |
| 14 | Agree acceptable simulator use for multi-charger tests | P5 tests | TWG |
| 15 | Confirm bid security, performance security and liquidated damages values | Tender and contract | Counsel, Finance lead |
| 16 | Decide publication channels for notices and awards | Transparency | Procurement Lead |

## 17. Immediate next steps

1. Approve this plan in outline with the Charter at Gate 0 and appoint the Procurement Lead and evaluation officer.
2. Name the contracting entity and obtain counsel's view on procurement law.
3. Confirm thresholds X and Y and the contingency policy with funders.
4. Reconcile the budget and complete the package budget table (5.3).
5. Prepare and publish the market briefing, with the draft criteria and local-service requirements.
6. Issue the pre-qualification request and vendor questionnaire (Appendix B) with the B6 and B7 questionnaires.
7. Set up the procurement record store, declaration forms and evaluation score sheets (Appendix D).
8. Agree the evaluation committee and conflict rules.
9. Prepare lot-specific schedules of requirements from B4 and B6 for issue after Gate 1.
10. Schedule test-lab capacity and loan-unit logistics with the university partner.

---

# Appendix A: Market briefing agenda and pack

**Audience.** Inverter, battery, meter, charger, telecom and network vendors, installers, EPC contractors, local agents, universities and the OpenEMS community.

| Item | Content |
| --- | --- |
| 1 | Programme overview: research pilot, three sites, 24 months, open publication |
| 2 | What OpenEMS is and what the programme will and will not control (behind the connection point only, supervisory layer, hardware protects) |
| 3 | Procurement stages, timeline and gate dependency, and how to take part |
| 4 | Compatibility testing: levels L0 to L4, test method, simulator limits, loan units, what counts as a pass |
| 5 | Mandatory commitments: written warranty position on third-party control, protocol documents, firmware policy, vulnerability disclosure, no undocumented remote access |
| 6 | Local service and spares expectations by pilot |
| 7 | Evaluation criteria and weights (draft) and total-cost approach |
| 8 | Integrity rules: conflicts, no inducements, no editorial control over evaluation |
| 9 | Questions and answers, logged and published |

**Pack.** Programme summary, B4 equipment requirements, B6 questionnaire, B7 Appendix A, draft criteria, timeline, contact point. Open to all interested parties, with attendance recorded.

---

# Appendix B: Pre-qualification request (RFPQ) and vendor questionnaire

*Template. Square brackets are placeholders.*

**Title:** Request for Pre-Qualification: [Package or lot] for the Open-Source EMS Pilot Programme Kenya
**Reference:** [RFPQ-C1-xx]  **Issue date:** [ ]  **Closing date and time:** [ ] (East Africa Time)  **Contact:** [Procurement Lead, email]

## B.1 Instructions to applicants

1. Applicants may apply for one or several lots. Joint ventures and agent arrangements must name a lead party and state the role of each.
2. Submit in English. Documents in other languages need a certified translation.
3. Applicants may request clarification in writing up to [x] working days before closing. Answers go to all applicants.
4. The programme is a research pilot. Pre-qualification does not guarantee a bid invitation, and no costs of applying are reimbursed.
5. Applicants must disclose any actual or potential conflict of interest (MoU Section 13) and any relationship with programme staff, hosts, funders or evaluators.
6. False statements disqualify. The programme may verify any claim with referees, the manufacturer or Kenya Power.

## B.2 Eligibility and capacity (pass or fail)

| # | Requirement | Evidence |
| --- | --- | --- |
| 1 | Legal registration and tax compliance in the applicant's country of registration and, for local partners, in Kenya | Certificates |
| 2 | Not debarred, bankrupt, or convicted of fraud or corruption | Declaration |
| 3 | Licences needed for the work (electrical contractor, solar contractor, importer) [confirm lists with EPRA] | Licence copies |
| 4 | Financial capacity | Audited accounts for [2] years, bank reference |
| 5 | Relevant experience: at least [x] comparable supply or installation contracts in the last [5] years | Contract list with referees |
| 6 | Local service capacity in Kenya: agent, workshop, trained technicians | Agent letter, staff list, location |
| 7 | Compliance with health, safety and environmental rules | HSE policy, incident record |

## B.3 Product and compatibility questionnaire (per device)

Use B6 Appendix A (questions 1 to 12) and B7 Appendix A (items 1 to 14) as the mandatory questionnaire, completed per product and firmware version. The following answers are decisive:

| # | Question | Must-have |
| --- | --- | --- |
| 1 | Full register map or protocol profile supplied | Yes |
| 2 | Written confirmation that control by a third-party EMS, specifically OpenEMS, does not affect the warranty | Yes |
| 3 | Known OpenEMS integrations with references | Preferred |
| 4 | Loan units for the lab campaign and a named technical contact | Yes |
| 5 | Chargers: power limit can be changed during a session, minimum current and phase behaviour, known problem vehicles | Yes (P5) |
| 6 | Batteries: BMS limits, alarm outputs, certifications, throughput limits under warranty, ambient range | Yes (P4) |
| 7 | Default credentials and how they are removed. No hard-coded accounts or hidden remote paths | Yes |
| 8 | All network connections the device makes, and ability to disable them | Yes |
| 9 | Firmware version can be held, updates announced, images verifiable | Yes |
| 10 | Local service location, response times, spares in Kenya, training offered | Yes |
| 11 | Take-back or compliant disposal, with data erase | Yes |
| 12 | Indicative price and lead time in Kenya | Yes |

## B.4 Pre-qualification scoring

| Item | Scoring |
| --- | --- |
| Section B.2 | Pass or fail |
| B.3 must-haves | Pass or fail. A "no" on a must-have is a disqualifier unless the Cybersecurity Officer approves a documented compensating control |
| Ranking of remaining applicants | Experience and references [30%], local service [30%], openness and documentation [20%], security posture [10%], lead time [10%] |
| Shortlist | Up to [5] applicants per lot. At least [2] where the market permits |

## B.5 Declaration

I confirm that the information is accurate, that I have no undisclosed conflict of interest, that I will not offer or accept any improper inducement, and that I accept the programme's evaluation independence rules.

Name, title, signature, date, company stamp: [ ]

---

# Appendix C: Invitation to bid (RFP or RFQ) template

*Template for shortlisted bidders. Repeat per lot. All square-bracket items are completed at issue.*

## C.1 Invitation

**Title:** Invitation to Bid: [Lot] for the OpenEMS Kenya Pilot
**Reference:** [ITB-C1-xx]  **Issued to:** shortlisted bidders only  **Issue date:** [ ]  **Clarification deadline:** [ ]  **Test units due:** [ ]  **Bid closing:** [date, time EAT]  **Bid opening:** [technical envelope date; financial envelope date after technical scoring]  **Bid validity:** [90] days from closing

## C.2 Instructions to bidders

| # | Topic | Instruction |
| --- | --- | --- |
| 1 | Programme and nature of contract | Research pilot with open publication. Contract starts at Gate 2 funds release. The programme may cancel the tender or reject all bids |
| 2 | Lots | Bids per lot. Lots may be awarded separately |
| 3 | Submission | Two sealed envelopes or two files: **Technical** (no prices) and **Financial**. A bid with prices in the technical file is rejected |
| 4 | Language and currency | English. Price in [USD or KSh], with FX reference [source and date] and duty basis [DAP, duty included or excluded] |
| 5 | Bid security | [x]% of the bid in a form acceptable to the programme, returned after contract signature or rejection. [Omit for small lots] |
| 6 | Test units | Supply [number] of each offered model, with the firmware to be delivered, for compatibility testing by the due date. Tests are run by the TWG and not by the bidder. Failure disqualifies. Units are [returned / purchased / donated] as stated |
| 7 | Alternatives | One alternative device may be offered, if stated in the bid, with its own test units and questionnaire |
| 8 | Clarifications | In writing to [email]. Answers are sent to all bidders. No contact with evaluators during evaluation |
| 9 | Site visits | A site visit for installation lots on [date], with a safety briefing. Attendance is [mandatory / optional] |
| 10 | Evaluation | As Section 8 of this plan. Technical gate first, then scoring, then financial opening |
| 11 | Award | To the highest-ranked compliant bidder, subject to Steering Committee approval, Gate 2 funds release and contract terms. A reserve bidder is named |
| 12 | Conflicts and integrity | Declarations required. Any attempt to influence evaluation disqualifies. Bribery Act, 2016 applies |
| 13 | Confidentiality | The programme treats marked commercial information as confidential, subject to law, audit and the publication rules below |
| 14 | Publication | The programme publishes the tender criteria and the award summary (winner, lot, value). It does not publish unsuccessful bid prices |
| 15 | Complaints | A bidder may complain in writing within [5] working days of the award notice to [the Programme Director], who responds within [10] working days. Unresolved matters escalate to the Steering Committee Chair |
| 16 | Costs | Bidders bear all bid costs |

## C.3 Schedule of requirements (per lot)

| Item | Quantity | Specification reference | Delivery point | Required delivery date |
| --- | --- | --- | --- | --- |
| [e.g. Edge computer] | [ ] | B4 3.3, B6 4 (`EDG`) | [Site] | [Month] |
| [e.g. Battery system about 250 kWh] | [ ] | B4 3.3, 5.1, B6 4 (`BAT`, `BMS`) | Pilot A | [Month] |
| [e.g. Fast charger] | [ ] | B4 7, B6 4 (`EVC`) | Pilot C | [Month] |
| [Services: installation support, training, spares] | [ ] | Section 9 of C1 | | |

The bidder states quantities that differ from the schedule and the reason.

## C.4 Technical bid contents

| # | Content |
| --- | --- |
| 1 | Compliance matrix against every must-have in Section 7, with page references to datasheets and certificates |
| 2 | Protocol documents: register maps, OCPP profile and version, update rates and latency |
| 3 | Written permission for third-party control under warranty |
| 4 | Completed B6 Appendix A and B7 Appendix A questionnaires for each device and firmware version |
| 5 | Safety and quality certificates for the named standards |
| 6 | Integration plan: driver route (R1 to R5), known OpenEMS integrations, gaps, effort estimate and who bears cost |
| 7 | Security statement: default credentials, hardening, firmware policy, vulnerability contact, network connections, remote-access design |
| 8 | Local service plan: agent, technicians, response times, spares list, training offered |
| 9 | Delivery and installation plan with lead times and a schedule to Gate 3 |
| 10 | Warranty terms, throughput limits, end-of-life and take-back |
| 11 | Key personnel and references |
| 12 | HSE plan for installation lots |
| 13 | Exceptions and deviations from the tender or contract terms |

## C.5 Financial bid contents

| # | Content |
| --- | --- |
| 1 | Price schedule form (C.6), complete and signed |
| 2 | Currency, FX reference and validity, price adjustment rule |
| 3 | Duties and taxes basis, with a statement of which are included |
| 4 | Payment terms offered, within Section 11.2 |
| 5 | Optional items priced separately: spares kit, extended warranty, training, remote-support option (after Gate 3 only) |
| 6 | Any discount for multi-lot award, stated per lot |

## C.6 Price schedule form

| Item | Description | Unit | Qty | Unit price | Total | Duty basis | Lead time (weeks) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| 2 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| Subtotal: goods | | | | | [ ] | | |
| Delivery, insurance, installation support | | | | | [ ] | | |
| First-year service and spares | | | | | [ ] | | |
| Training | | | | | [ ] | | |
| Custom driver or integration cost, if any | | | | | [ ] | | |
| **Bid total** | | | | | **[ ]** | | |

## C.7 Forms to be signed by the bidder

1. Bid submission form (acceptance of tender terms, validity).
2. Declaration of interest and integrity (no conflict, no inducement, Bribery Act, 2016).
3. Evaluation independence and publication acknowledgement (no editorial control by the vendor, and publication of integration results including failures).
4. Local service commitment letter from agent or partner.
5. Security commitments (B7 Appendix A) signed by an authorised person.
6. Manufacturer authorisation, where the bidder is a reseller.
7. Bid security, if required.

---

# Appendix D: Evaluation record templates

## D.1 Bid register

| Bid ID | Bidder | Lot | Received (date, time) | Opened (date, time, witnesses) | Complete? |
| --- | --- | --- | --- | --- | --- |
| [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

## D.2 Technical gate sheet (per bid and device)

| Gate item | Result (Pass / Fail / Conditional) | Evidence reference | Condition, owner, cost, due date |
| --- | --- | --- | --- |
| Must-have requirements met | [ ] | [ ] | |
| B6 test record, level reached (L3 required) | [ ] | TR-[ ] | |
| Written warranty permission | [ ] | [ ] | |
| B7 Appendix A: no failed must-have | [ ] | [ ] | |
| Local service route | [ ] | [ ] | |
| Safety certification | [ ] | [ ] | |
| **Gate result** | [Pass / Fail] | | |

## D.3 Scoring sheet (per evaluator and bid)

| Criterion | Weight | Score 0 to 5 | Weighted | Evidence and comment |
| --- | --- | --- | --- | --- |
| Technical quality and openness | [20%] | [ ] | [ ] | |
| Integration effort and driver route | [15%] | [ ] | [ ] | |
| Local service and spares | [20%] | [ ] | [ ] | |
| Security and firmware policy | [10%] | [ ] | [ ] | |
| Delivery and schedule | [10%] | [ ] | [ ] | |
| Warranty, lifetime and end-of-life | [10%] | [ ] | [ ] | |
| Price and total cost of ownership | [15%] | [ ] | [ ] | |
| **Total** | 100% | | [ ] | |

**Scoring scale.** 0 = no response or fails the intent. 1 = very weak. 2 = weak, with significant gaps. 3 = acceptable, meets the requirement. 4 = good, exceeds in places. 5 = excellent, with evidence of exceeding.

## D.4 Total cost of ownership worksheet

| Component | Bidder 1 | Bidder 2 | Bidder 3 |
| --- | --- | --- | --- |
| Bid price delivered | [ ] | [ ] | [ ] |
| Custom driver and integration cost | [ ] | [ ] | [ ] |
| Conditional (`COND`) items | [ ] | [ ] | [ ] |
| First-year O&M and spares | [ ] | [ ] | [ ] |
| Service travel and downtime estimate | [ ] | [ ] | [ ] |
| End-of-life cost, less salvage | [ ] | [ ] | [ ] |
| **Evaluated cost** | [ ] | [ ] | [ ] |
| Price score | [ ] | [ ] | [ ] |

## D.5 Evaluation report outline

1. Process followed and any deviations. 2. Bids received and compliance. 3. Gate results per device with test record references. 4. Scores and ranking per lot. 5. Total cost comparison and abnormally low bid review. 6. Preferred bidder, reserve bidder and conditions to close. 7. Risks and recommendations. 8. Declarations of interest. 9. Approval signatures: committee chair, Procurement Lead, Programme Director, and Steering Committee decision where required.

---

# Appendix E: Contract key-terms checklist

| # | Clause | Check |
| --- | --- | --- |
| 1 | Parties, legal entity, authorised signatories | [ ] |
| 2 | Scope, schedule of requirements, specification references (B4, B6) | [ ] |
| 3 | Price, currency, FX and price adjustment, duties and taxes | [ ] |
| 4 | Payment milestones, retention, performance security, advance guarantee | [ ] |
| 5 | Delivery terms, risk and title, equipment title consistent with host agreement Schedule 4 | [ ] |
| 6 | Factory or lab acceptance and site acceptance tests (L4), witness arrangements | [ ] |
| 7 | Delay, liquidated damages and cap, link to Gate 3 | [ ] |
| 8 | Warranty, warranty-compatible third-party control, local service SLA, spares list | [ ] |
| 9 | Firmware, version hold, change process, rollback | [ ] |
| 10 | Remote access prohibition, post-Gate 3 conditions, commissioning handover of all credentials | [ ] |
| 11 | Security commitments from B7 Appendix A, vulnerability notification | [ ] |
| 12 | Documentation, open publication of integration code and configuration, confidentiality carve-outs | [ ] |
| 13 | Evaluation independence and no editorial control | [ ] |
| 14 | Data handling and data processing agreement where needed | [ ] |
| 15 | Insurance certificates | [ ] |
| 16 | HSE and incident reporting, licensed personnel, site induction | [ ] |
| 17 | Training and handover, local technician competence record | [ ] |
| 18 | End-of-life, take-back and data erase | [ ] |
| 19 | Integrity, conflicts, audit and access rights for funders | [ ] |
| 20 | Variation, change control, termination, gate-failure termination cap | [ ] |
| 21 | Dispute resolution, governing law, forum confirmed by counsel | [ ] |
| 22 | Conditions precedent (Gate 2, host agreement, Kenya Power acceptance, insurer acceptance) | [ ] |

---

# Appendix F: Lot summary by pilot (for tender schedules)

| Lot | Pilot | Key items | Special points from B4 and B6 |
| --- | --- | --- | --- |
| A-1 | A | Battery system about 250 kWh (size to be confirmed against the 300 kWh Charter reference), battery or hybrid inverter, BMS | Size by the B4 Section 4 method only. Battery power range to test about 125 to 250 kW. Insurer and fire design |
| A-2 | A | Edge, network, grid and research meters | Separate research meter if the utility meter cannot be shared. Host IT segmentation |
| A-3 | A | Existing inverter remedy or new PV inverter | Warranty and open interface are pass or fail. Red item if no open interface |
| A-4 | A | Installation, switchboard and battery room works | Licensed contractor, floor loading, ventilation, county permits |
| B-1 | B | PV 50 to 100 kW, PV inverters | Driver availability and local service |
| B-2 | B | Battery about 200 kWh, battery inverter, BMS | Grid-forming capability if topology requires. Heat, dust, theft protection |
| B-3 | B | Generator interface (relay, gateway or controller) | Often no digital interface (route R5 or relay). Generator keeps its own protection |
| B-4 | B | Edge, dual-SIM router, feeder and check meters | Autonomy 72 hours offline. Check meters for loss measurement design |
| B-5 | B | Installation, civil works, cabinets and security | Lightning, flood, wildlife, local operator training, spares kit |
| C-1 | C | About 10 to 20 fast chargers | In-session power limit proven per model and OCPP version. Vendor cooperation clause |
| C-2 | C | Transformer and site meters, Edge, network | Transformer data path from Kenya Power is read-only. Conservative limit on feed loss |
| C-3 | C | Optional small battery | Only if economics and space allow, decided at sizing |
| C-4 | C | Installation and civil works | Public liability, signage, thermal safety |
| S-1 | All | Independent security audit | Independence from vendors and the Technical Lead's organisation, with a [24]-month look-back |
| S-2 | All | Training, community liaison, translation and printing | English and Kiswahili, competence assessment |
| S-3 | All | Insurance | Equipment all-risks and public liability, certificates before installation |

---

# Appendix G: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 8, 13, 14, 16, 17, 18, 20, 21) | Budget and cost structure, contingency, thresholds, RACI, gates, risks, change control, open publication |
| Feasibility Study (Sections 4.3, 5, 8.1, 9, 12) | Compatibility approach, budget reconciliation, schedule pressure, risks |
| Technical Specification per Site (Sections 3.3, 3.5, 4, 5 to 9) | Equipment requirements, sizing method, acceptance tests, procurement requirements |
| Interoperability and Device Compatibility Register (Sections 2 to 6, 9 to 12, Appendix A) | Compatibility levels, tests, vendor commitments, escalation, questionnaire |
| Cybersecurity Plan (Sections 6.4, 6.9, 9, Appendix A, B) | Vendor security requirements, audit procurement, commissioning checks |
| Regulatory Compliance Assessment (Sections 5.5, 5.8, 5.10, 6) | Licensed contractors, interconnection acceptance, duties, entity, procurement law |
| MoU and Site Agreement templates (Site Agreement Sections 3, 7, 13, 14, Schedules 2 to 5) | Equipment lists, title, insurance, conditions precedent, closure |
| Stakeholder Engagement Plan (Section 6.5) | Market briefing, no vendor editorial control, upstream contributions |
| Site Survey Reports (A3, B3, B4) | Existing devices and site constraints |

On completion of counsel review, the budget reconciliation and the Gate 1 decisions (entity, thresholds, weights, local-service minimums), each bracketed value is updated and the document is re-issued as version 1.0 for Gate 1 approval.

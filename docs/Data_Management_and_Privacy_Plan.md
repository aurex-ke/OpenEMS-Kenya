# Data Management and Privacy Plan

## 1. Purpose and bottom line

The programme collects energy data from three pilot sites, some of which identifies or can identify people: households at Pilot B, drivers and vehicles at Pilot C, and a named host and its commercial terms at Pilot A. This plan defines what is collected, why, who may see it, how long it is kept, how it is protected, how it is shared with utilities, regulators and the university partner, and how it is published without harming the people behind it.

**Bottom line.** The programme is committed both to open publication and to privacy. These pull against each other, so the plan resolves them with seven rules:

1. **Collect only what the KPIs need.** If a field does not feed a KPI, the baseline or safety, it is not collected. No payment data and no driver identity are in the programme dataset.
2. **Pseudonymise at source.** Household and charger-session identifiers are replaced on the Edge or logger, before data leaves the site. Re-identification keys are held separately by the Cybersecurity and Data Protection Officer.
3. **Two views, one record.** Research meter data and Edge control data are kept separately and reconciled. Raw data is immutable. Cleaned data is derived and versioned.
4. **Roles before transfer.** No personal data moves between parties until controller, joint controller or processor roles are agreed in writing (MoU Section 7.2) and any required agreement is signed.
5. **Aggregate before publishing.** Customer-level and driver-level data is anonymised or aggregated before publication, and small-group re-identification risk is checked first.
6. **Local first, no remote path before Gate 3.** Before Gate 3, data moves by local or manual transfer only. Afterwards, only over the approved outbound-only encrypted path (B7 Section 6.2).
7. **Findings are not hostage to privacy claims.** Hosts and partners may delay publication only to protect personal data, security or a legitimate legal interest, for up to \[60\] days (MoU Section 10.3). They cannot block aggregated results.

**What cannot be settled from desk research.** No site is selected, no data flows exist, and the contracting entity is not yet named. Controller and processor roles, registration duties and hosting location therefore depend on decisions at Gate 0 and Gate 1. This plan fixes the method and leaves those values as placeholders.

## 2. Document control and relationships

**Owner:** Data analyst (README D2), under the Research Lead, with the Cybersecurity and Data Protection Officer as accountable reviewer. **Contributors:** Technical Lead, software engineer, university partner, Kenya Power ICT and grid engineer (TWG), Site Leads, counsel, PMO. **Approval:** Programme Director at Gate 1. Frozen at Gate 2. Reviewed fortnightly in the TWG during build, monthly in operation. Changes follow Charter Section 20 change control.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 19, 21, 22) | Data governance, anonymisation before publication, publication rules |
| Regulatory Compliance Assessment (B5, Sections 5.6, 5.9) | Legal position, ODPC registration, NACOSTI and ethics, open counsel questions |
| Cybersecurity Plan (B7, Sections 6.6, 6.10, 10) | Technical controls, pseudonymisation, breach and incident response |
| Technical Specification (B4, Sections 3.4, 7.4) | Measurement points, data resolution, pilot C privacy rules |
| Monitoring and Evaluation Plan (D1) | KPI data needs, data flow, quality checks, publication |
| OpenEMS Configuration Baseline (C4, Section 14) | What configuration is public and what is withheld |
| MoU and Site Agreement templates (MoU 7, 9, 10; Site Agreement 9, Schedule 6) | Binding data clauses and per-site data roles. This plan supplies the content of Schedule 6 |
| Stakeholder Engagement Plan (Sections 7.2, 11, 15) | Honest messaging on data, grievance route, disclosure before publication |
| Installation and Commissioning Plan (C3), Site Acceptance Tests (C5) | Privacy notice and consent checks at acceptance |

## 3. Principles

| Principle | What it means in practice |
| --- | --- |
| Lawfulness, fairness, transparency | Every collection has a stated purpose and a lawful basis, and people are told in plain language, in English and Kiswahili where relevant |
| Purpose limitation | Programme data is used for the pilot, its evaluation and agreed publication. Nothing else without a new basis |
| Minimisation | Collect the least data, at the coarsest resolution and for the shortest time that still answers the evaluation questions |
| Accuracy and integrity | Meter checks, time synchronisation, signed logs and change records protect the evidence (B7 6.6) |
| Storage limitation | Retention periods are fixed in Section 9. Personal data is deleted or anonymised when its purpose ends |
| Security by design | Controls follow B7. A device or tool that cannot protect data is not used |
| Accountability | Each dataset has a named owner, a register entry and a recorded lawful basis |
| Open by default, private for people | Methods, code, anonymised data and findings are published. Credentials, live network details and personal data are not |
| Honest limits | The plan states what anonymisation can and cannot guarantee |

## 4. Legal basis and obligations

The governing law is the **Data Protection Act, 2019** and its regulations \[confirm current regulations with counsel\]. Counsel must also confirm the points below, which Regulatory Compliance Assessment B5 lists as open.

| Obligation | Programme position | Action |
| --- | --- | --- |
| Registration with the Office of the Data Protection Commissioner (ODPC) | Likely required for the contracting entity and any Backend host or processor \[confirm\] | Decide at Gate 0 who registers. Apply before any data transfer |
| Lawful basis for processing | Consent at Pilot B community meetings and for any identifiable driver data. Legitimate research and contract bases for host commercial data \[confirm\] | Record per dataset in the register (Appendix A) |
| Data protection impact assessment | Likely needed for household and driver data \[confirm\] | Complete before data collection (Appendix B) |
| Roles: controller, joint controller, processor | Not yet assigned. The contracting entity is not named | Agree in writing before any sharing (MoU 7.2). Record in Schedule 6 of each site agreement |
| Data subject rights (access, correction, objection, deletion) | Apply to household and driver data, limited where data is truly anonymised | Process in Section 11 |
| Breach notification | Internal notice to the PMO within \[48\] hours (MoU 7.4), then statutory notice to the ODPC within the statutory period \[confirm, commonly understood to be 72 hours\] | Process in Section 12 |
| Cross-border transfer | Applies if the Backend, cloud or any partner sits outside Kenya | Prefer Kenya-based hosting. Otherwise confirm the lawful transfer basis \[confirm\] |
| Research approvals | NACOSTI licence and institutional ethics clearance for data about people | University partner applies in Months 1 to 3 (MoU Schedule 1C) |
| Sector rules | No EPRA or Kenya Power data rule is yet known | Ask in the Month 1 written request (B5 Appendix A) |

## 5. Roles and responsibilities

| Role | Responsibility |
| --- | --- |
| Steering Committee | Approves this plan's publication rules and any accepted high privacy risk |
| Programme Director | Accountable for data sharing agreements and regulator communication |
| Cybersecurity and Data Protection Officer | Owns this plan's compliance. Holds pseudonymisation keys. Reviews every release. Leads breach response |
| Research Lead | Owns research datasets, KPI data, analysis and the integrity of published results |
| Data analyst | Runs the pipeline, quality checks, aggregation and disclosure checks. Keeps the data register |
| University partner | Ethics and NACOSTI approvals, validation, secure research access. May use datasets for research under MoU Schedule 1C |
| Technical Lead and software engineer | Implement pseudonymisation, buffering, access roles and deletion tooling. Do not alter research data |
| Site Leads | Collect site logs and consents, display notices, protect meters and seals, first response to breaches |
| Host representatives | Supply bills and tariff documents, follow Schedule 6, report suspected breaches. Cannot alter research meters |
| Kenya Power | Supplies feeder and transformer data under a data sharing agreement. Read-only access to pilot feeder data |
| Vendors and installers | No access to research data. Process data only if a data processing agreement says so |
| PMO | Tracks data actions, risks and dashboard items |
| Counsel | Confirms the legal points marked \[confirm\] and reviews agreements |

## 6. Data inventory

The full register is in Appendix A. Summary by data family:

| Family | Examples | Pilots | Personal data? | Sensitivity |
| --- | --- | --- | --- | --- |
| Energy measurements | Grid import and export, PV, battery, generator, feeder and transformer readings | All | No at aggregate site level. Possibly at customer level (B) | Low to medium |
| Host commercial data | Bills, tariff terms, load history, production schedules | A | Mostly commercial. May identify the host | High (confidential by default) |
| Household consumption | Per-customer kWh, meter IDs, metering coverage | B | Yes | High |
| Charger session data | Start, stop, energy, power, wait, connector, vehicle or token identifiers | C | Yes if drivers or vehicles can be identified | High |
| Utility data | Feeder and transformer loading, outage records, interconnection details | A, B, C | Possibly at customer level | Medium to high |
| Operational and security logs | Logins, configuration changes, overrides, alarms | All | Yes (user names) | Medium |
| Programme and people data | Stakeholder register, training records, consents, complaints, incident reports | All | Yes | Medium to high |
| Configuration and code | Edge configuration, drivers, manifests | All | No | Public after sanitising (C4 Section 14) |

**Special care.** Complaints and incident reports can include health or safety details and children's information. They are access-restricted and published only in aggregate. Where children may be present at Pilot B, no data about children is collected.

## 7. Data lifecycle and flow

1. **Capture.** Research meters and the independent logger record separately from the Edge, with synchronised time (B4 3.4).
2. **Minimise and pseudonymise at source.** Household and session identifiers are replaced by pseudonyms on the Edge or logger. The key table stays off the Edge, held by the Officer.
3. **Buffer.** At least \[30\] days of local storage. Buffers are encrypted where practical \[confirm for unattended devices, B7 open item 10\].
4. **Transfer.** Before Gate 3, manual or local transfer by named staff, logged. After Gate 3, the approved outbound-only encrypted path. All transfers carry a record of who, when and what.
5. **Validate and store.** Automated checks (D1 Section 9.2). Raw data is immutable and stored with checksums. Cleaned data is derived, versioned and documented in a data dictionary.
6. **Analyse.** Analysts work in the secure environment described in Section 8. Identifiable data is not exported to personal devices.
7. **Share.** Under data sharing agreements and the access matrix. Utility, university and regulator access is defined in writing before the first transfer.
8. **Publish.** Only after the Panel accuracy check and the security and privacy review, using Section 10 rules.
9. **Retain or delete.** Per Section 9. Deletion is logged.
10. **Hand over.** At Gate 5, datasets and code move to named custodians (Section 13).

## 8. Access, storage and security

The controls below implement B7 Sections 6.1, 6.6 and 6.10 for data.

| Control | Requirement |
| --- | --- |
| Access principle | Least privilege, named accounts, role-based access. No shared logins. Quarterly access review |
| Access matrix | Raw identifiable data: Officer and named analysts only. Pseudonymised data: Research Lead, analysts, university researchers under agreement. Aggregated data: Panel, SteerCo, partners. Public: anonymised releases only. Hosts: own site data through the OpenEMS UI (Site Agreement 9.4). Vendors: none |
| Utility access | Kenya Power has read access to pilot feeder and transformer data. No Kenya Power asset is controlled and no data flows back to the control network (MoU Schedule 1B) |
| Storage location | Kenya-based storage preferred. Any Backend or cloud host is chosen at Gate 1 and covered by a hosting and data agreement. Ministry of Energy hosting is an option under a separate agreement |
| Encryption | In transit on every link outside the site control zone. At rest on Backend, cloud, analyst machines and backups |
| Environment | Analysis in a controlled workspace with logging. Laptops use full-disk encryption and screen lock (B7 6.8). No identifiable data in chat tools, email or personal drives |
| Integrity | Checksums on raw files, append-only or hashed logs, off-site copies, time-stamped mode records so the baseline can be shown unaltered (B7 6.6) |
| Backups | Encrypted, tested at Gate 4. Backups follow the same retention and deletion rules as primary data |
| Secrets and keys | Held outside repositories. Pseudonymisation keys stored apart from the data they protect, with two-person access |
| Repositories | Public repositories contain no personal data, no credentials and no live network details. Pre-release scan by the Officer (B7 6.9, C4 14) |
| Third-party tools | Any analytics, survey or storage tool is reviewed by the Officer. A processor agreement is signed before use |

## 9. Retention and deletion

Proposed periods, to be confirmed by counsel and the funders. The default is the shortest period that supports the evaluation, audit and legal duties.

| Data | Retention | Then |
| --- | --- | --- |
| Raw identifiable household or driver data (before pseudonymisation) | Not retained beyond the site buffer. Held for no more than \[x\] days to complete pseudonymisation | Securely deleted |
| Pseudonymisation key tables | Until the final evaluation is accepted at Gate 5, plus \[12\] months for queries | Securely destroyed |
| Pseudonymised research datasets | Pilot period plus \[x\] years for audit and replication | Anonymise for archive or delete |
| Raw energy measurements (site level) | Pilot period plus \[x\] years | Archive with the anonymised release |
| Host commercial data | Per host agreement. Not later than \[x\] months after closure unless the host consents | Return or delete |
| Utility data | Per data sharing agreement | Return or delete |
| Security and access logs | \[Period set here, proposal 12 months in operation\] | Delete |
| Incident and breach records | \[3\] years (B7 6.6) or as the law requires | Delete |
| Consent and notice records, complaints | Pilot period plus \[x\] years | Delete or anonymise |
| Training records | As needed for the Charter training KPI and certification | Delete or anonymise |
| Public anonymised datasets and code | Permanent in the open repository | Custodian reviews yearly |

Hosts, Kenya Power and the university partner receive written confirmation when their data is deleted or returned at closure (Site Agreement 16.3).

## 10. Anonymisation, aggregation and publication

### 10.1 Standards

| Item | Rule |
| --- | --- |
| Pseudonymisation | Reversible only with the key table. Treated as personal data throughout |
| Anonymisation | No reasonable means of re-identification, tested before release. Pseudonymised data is not called anonymous |
| Minimum group size | No published figure is based on fewer than \[k\] customers, sessions or vehicles. Proposal: k = \[5\] for aggregates, with checks for dominant contributors |
| Resolution | Household data is published only at feeder or transformer-group level. Charger data only at hourly or session-distribution level, never with timestamps that single out a vehicle |
| Time and place | Exact timestamps, vehicle, plate, token and meter identifiers are removed. GPS is withheld for private households |
| Rare events | Small-group risk is rechecked for outages, theft and unusual loads, which can identify people |
| Host data | Published in identifiable form only with host consent. Aggregated results cannot be blocked (Site Agreement 9.3) |

### 10.2 Release process

1. The data analyst prepares the release and a disclosure-risk note.
2. The Research Panel checks accuracy.
3. The Officer reviews security and privacy, including a re-identification test and a scan for secrets and network details.
4. Hosts, Kenya Power, EPRA and communities see findings before public release (Stakeholder Plan 15).
5. The Programme Director approves, and the release is logged with its version and checksum.

Negative and inconclusive findings are released with equal prominence. A privacy objection can delay but not reshape a finding (MoU 10.3). Pilot C and Pilot B detailed data may be offered to approved researchers under a data use agreement instead of public release \[decision, Section 16\].

## 11. Notice, consent and data subject rights

| Pilot | Notice and basis | Rights handling |
| --- | --- | --- |
| A | Host agreement and Schedule 6. Staff briefed on what is measured. Commercial data confidential by default | Host contact point. Staff queries to the Site Lead |
| B | Plain-language notice and informed agreement at community meetings, in English, Kiswahili and the local language, before procurement. People can decline. Messages stress this is a research pilot (Stakeholder Plan 7.2) | Complaints and rights requests through at least two channels, with acknowledgement within \[3\] working days and a response within \[14\] days. Anonymous submission allowed |
| C | Privacy notice displayed at the site and on charger screens or signage. No driver identity or payment data in the programme dataset unless a lawful basis and notice exist (Site Agreement 9.2). Fleet customers sign consent where relevant | Operator helpline and site complaints channel. Pseudonymised data cannot be linked back by the programme without the key, which is used only to honour a request |

**Rules.** Consent is specific, informed, recorded and withdrawable without penalty or loss of electricity supply. Withdrawal removes the person from later data collection and from future releases. Already anonymised or aggregated data cannot be withdrawn, and people are told this. Requests are logged and answered within the legal time \[confirm\]. Nobody is penalised for asking.

## 12. Breach and incident handling

Personal data incidents follow the Cybersecurity Plan (B7 Section 10), with these data-specific steps.

1. **Report.** Anyone suspecting a breach tells the Officer or the Site Lead immediately.
2. **Contain and assess.** Isolate access, preserve logs, assess what data, whose, how many and the risk of harm.
3. **Notify the PMO** within \[48\] hours of awareness (MoU 7.4).
4. **Statutory notice.** The Officer and counsel decide whether notice to the ODPC is required and send it within the statutory time \[confirm\]. Kenya Power is notified where its data or grid is involved.
5. **Inform people.** Affected individuals are told in plain language and Kiswahili where relevant when the law or the risk requires.
6. **Review.** Blameless post-incident review within \[10\] working days. Update controls, the register and this plan.

A vendor, university or host that suffers a breach affecting programme data notifies the PMO under the same \[48\]-hour rule.

## 13. Data sharing agreements and governance

| Agreement | Parties | Needed before | Key content |
| --- | --- | --- | --- |
| Data sharing agreement with Kenya Power | Contracting entity, Kenya Power | Gate 3 baselines | Feeder and transformer data, format, update rate, read-only, roles, retention |
| Data processing or hosting agreement | Contracting entity, any Backend or cloud host (possibly Ministry of Energy) | Any hosted data | Processor duties, location, security, audit, deletion |
| University research and data agreement | Contracting entity, university | Data collection | Access, ethics, authorship, secondary use limits, deletion |
| Host Site Agreement, Schedule 6 | Contracting entity, host | Gate 2 | Roles, access, retention, confidential items, privacy notice |
| Vendor contracts | Contracting entity, vendors | Contract signature | No data collection by vendors unless a processing agreement says so (C1 11.2) |
| Data use agreement for approved researchers | Contracting entity, requesters | Any restricted release | Purpose, no re-identification, destruction, citation |

**Custodianship.** At Gate 5 the datasets, code and this plan transfer to named custodians (for example the university partner or Ministry of Energy), with a written privacy and retention handover. The Programme Sponsor names them (D1 open item 11).

## 14. Pilot-specific requirements

### 14.1 Pilot A

Production schedules and tariff terms are confidential. Installers do not copy host data (C5 AX-6). Host IT is treated as untrusted, with no programme device in the host domain. If benefit sharing is chosen, it is recorded so the baseline is not distorted.

### 14.2 Pilot B

Household consumption is personal data. Collect the minimum, pseudonymise at source, and publish only at feeder or transformer-group level. Check re-identification risk where few customers share a transformer. Consent is gathered through inclusive sessions, including separate sessions for women, youth and small businesses. Programme staff and community liaison officers do not carry identifiable customer lists off site.

### 14.3 Pilot C

Session data can identify drivers and vehicles. Pseudonymise on site, exclude payment data, display the privacy notice (test C10) and avoid timestamps that single out vehicles. The charger back office is the operator's system, and the programme does not integrate with payment systems (B7 7.3). Fleet customers see their own aggregated results first.

## 15. Schedule and gate evidence

| Activity | Months | Output | Gate |
| --- | --- | --- | --- |
| Appoint Officer. Name contracting entity and controller roles | 0 to 1 | Roles decided | Gate 0 |
| Counsel review. ODPC registration and DPIA drafted | 1 to 4 | Registration applied for. DPIA v0.1 | Gate 1 input |
| Ethics and NACOSTI applications | 1 to 3 | Applications filed | Gate 1 |
| Data sharing positions with Kenya Power and hosts | 3 to 6 | Draft agreements | Gate 1 |
| Approve method, retention schedule, publication rules | 4 to 6 | This plan v0.2 approved | **Gate 1** |
| Sign data sharing and processing agreements. Fix Schedule 6 per site | 6 to 8 | Signed agreements | **Gate 2** |
| Notices, consents and pseudonymisation tested at commissioning | 10 to 12 | Test records | **Gate 3** |
| Drift and access reviews. Data quality and privacy reporting | 13 to 24 | Monthly dashboard items | Gate 4 |
| Anonymised release, deletion and custodian handover | 22 to 24 | Release, deletion records | **Gate 5** |

| Gate | Evidence from this plan |
| --- | --- |
| Gate 1 | Approved method. Controller and processor roles proposed. ODPC and ethics status. DPIA drafted. Retention proposal |
| Gate 2 | Signed data agreements. Schedule 6 per site. Hosting decision. Notice templates approved |
| Gate 3 | Pseudonymisation and notice tests passed. Access matrix applied. Breach process exercised |
| Gate 4 | Access review, retention and deletion log, privacy incident summary |
| Gate 5 | Anonymised release published. Deletion and return confirmed. Custodians briefed |

## 16. Risks and open items

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| DM1 | Personal data shared before roles and agreements exist | M | H | No-transfer-without-agreement rule, Gate 1 and 2 checks | Programme Director |
| DM2 | Re-identification from published small-group or rare-event data | M | H | k threshold, disclosure checks, restricted access for fine data | Data analyst |
| DM3 | Contracting entity or ODPC registration unresolved | M | H | Decide at Gate 0 | Programme Sponsor |
| DM4 | Cross-border hosting breaches transfer rules | L | M | Kenya-based hosting or confirmed basis | Officer |
| DM5 | Consent not truly informed at Pilot B | M | H | Inclusive sessions, plain language, right to decline, record keeping | Site Lead B |
| DM6 | Data loss at remote sites or through theft | H | M | Buffer, encryption, backups, spares | Site Lead B |
| DM7 | Pressure to delay or soften publication | M | H | MoU 10 limits, Panel independence, equal prominence | Research Lead |
| DM8 | Retention excessive, or deletion not done at closure | M | M | Schedule, deletion log, custodian handover | Data analyst |
| DM9 | Privacy work under-budgeted | M | M | Itemise in budget reconciliation | Programme Manager |

Open items and decisions:

1. Confirm the legal points marked \[confirm\], especially ODPC registration, DPIA duty, breach timelines and cross-border rules (counsel, Gate 1).
2. Name the contracting entity and assign controller and processor roles (Programme Sponsor, Gate 0).
3. Choose the Backend and storage host, and its location (Technical Lead, Gate 1).
4. Set the minimum group size k, retention periods and the audit horizon (Research Lead and Officer, Gate 1).
5. Decide whether fine-grained Pilot B and C data are published or released only under data use agreements (Research Lead, Officer, Gate 3).
6. Decide how pseudonymisation keys are stored at low-connectivity sites (Technical Lead, Gate 2).
7. Name post-pilot data custodians (Programme Sponsor, Gate 5).

## 17. Immediate next steps

1. Appoint the Cybersecurity and Data Protection Officer and the data analyst, and approve this plan in outline at Gate 0.
2. Brief counsel and obtain written advice on the \[confirm\] items.
3. Open the data register (Appendix A) and start the DPIA (Appendix B).
4. University partner to file NACOSTI and ethics applications.
5. Draft the Kenya Power data sharing agreement and Schedule 6 templates.
6. Draft bilingual notices, consent forms and a short data FAQ for Pilots B and C.
7. Specify pseudonymisation and buffering requirements for procurement package P1 and P2.
8. Add risks DM1 to DM9 to the live Risk Register and the dashboard.

## Appendix A: Data register (template)

| ID | Dataset | Pilot | Owner | Purpose and KPI | Personal data? | Lawful basis | Source | Controller and processor | Access roles | Location | Retention | Release status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| DS01 | Grid and PV interval data | A | Research Lead | K1, K2, K3 | No (host-commercial) | \[Host agreement\] | Research meter | \[ \] | Analysts, Panel | \[ \] | \[ \] | Aggregate |
| DS02 | Household consumption (pseudonymised) | B | Research Lead | K6 | Yes | \[Consent\] | Check meters, billing | \[ \] | Analysts | \[ \] | \[ \] | Group-level only |
| DS03 | Charger sessions (pseudonymised) | C | Research Lead | K5 | Yes | \[Notice, consent\] | Edge | \[ \] | Analysts | \[ \] | \[ \] | Aggregate |
| DS04 | Transformer and feeder data | A, B, C | Technical Lead | K5, K6 | Possibly | \[DSA\] | Kenya Power, meters | \[ \] | Kenya Power, analysts | \[ \] | \[ \] | Aggregate |
| DS05 | Access, security and override logs | All | Officer | Integrity, safety | Yes | \[Legitimate interest\] | Edge | \[ \] | Officer, TWG | \[ \] | \[ \] | Not released |
| DS06 | Consents, complaints, incidents | All | PMO | Accountability | Yes | \[Legal duty, consent\] | Site teams | \[ \] | PMO, Officer | \[ \] | \[ \] | Summaries |
| DS07 | Training and participation records | All | Capacity lead | Training KPI | Yes | \[Consent\] | D4 | \[ \] | PMO | \[ \] | \[ \] | Aggregate |

## Appendix B: DPIA outline

1. Description of processing: purposes, data, flows, parties.
2. Necessity and proportionality: why each field is needed, what was dropped.
3. Risks to people: re-identification, loss of supply fears, profiling of drivers, exposure of household patterns, commercial harm to hosts.
4. Measures: pseudonymisation, aggregation, access limits, retention, notices, rights handling.
5. Residual risk and approval by the Officer and Programme Director, with counsel review.
6. Review at each gate and after any incident or change in data flows.

## Appendix C: Privacy notice content (Pilots B and C)

Short, plain-language, bilingual notices state: who runs the pilot and who to contact; that it is a research pilot and results are measured, not guaranteed; what is collected and why; what is not collected (no payment data, no names in published results); who sees it (university, Kenya Power, regulators, in anonymised form for the public); how long it is kept; how to ask, complain, withdraw or see data; and that declining or withdrawing never affects electricity supply or charging service.

## Appendix D: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 19, 21, 22) | Data governance, publication rules, community engagement |
| Feasibility Study (Sections 6, 7.4) | Data protection compliance, privacy at Pilots B and C |
| Regulatory Compliance Assessment (Sections 5.6, 5.9, 7) | Legal position, registration, research approvals, regulatory risks |
| Cybersecurity Plan (Sections 6.1, 6.6, 6.10, 10) | Access, logging, pseudonymisation, breach response |
| Technical Specification (Sections 3.4, 7.4) | Measurement data, session data privacy |
| Monitoring and Evaluation Plan (Sections 8, 9, 13) | Data flow, quality checks, publication |
| OpenEMS Configuration Baseline (Section 14) | What is published and withheld |
| MoU and Site Agreement templates (MoU 7, 9, 10, Schedule 1B, 1C; Site Agreement 9, Schedule 6) | Binding data clauses and roles |
| Stakeholder Engagement Plan (Sections 7.2, 11, 15) | Consent messaging, grievance route, disclosure before publication |

On completion of counsel review, the Gate 0 decisions on entity and roles, and the Gate 1 decisions on hosting and retention, each bracketed value is updated and this document is re-issued as version 1.0 for Gate 2.

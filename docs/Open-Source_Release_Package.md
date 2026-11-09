# Open-Source Release Package

## 1. Purpose and bottom line

The README assigns E5 to the Software engineer, for the open-source community: configurations, scripts and anonymised data under Apache 2.0. The Charter commits the programme to archive code, data and documents in a public repository at closure (Section 24) and to publish methods, code changes, data and findings, subject to security and privacy safeguards (Sections 12 and 21). This document (E5) defines **what is released, under which licence, in what form, after which checks, and who maintains it afterwards**. It also holds the release manifest, checklists and templates the release team uses.

**Status note.** No site is selected, built or measured, and no code, configuration or data exists yet. This version is a **pre-populated plan and template**. The package structure, licence rules, review chain, release gates and templates are fixed now. Every content field is completed from the repositories and the validated record in Months 22 to 24. It must not be used to state or imply a result.

**Bottom line.** The release is where "open by default" meets "safe by review". Nine rules govern it:

1. **Public by design, private by exception.** Templates, schema, tooling, drivers, sanitised configuration, test sets, report templates and anonymised data are released. Credentials, live network details, unpatched vulnerabilities, personal data and host-confidential data are not (C4 Section 14, D2 Section 10).
2. **Nothing leaves without the review chain.** Technical review, Research Lead accuracy check, Cybersecurity Officer security and privacy review, licence check, then Programme Director approval (Charter Section 21).
3. **Pseudonymised is not anonymous.** Only data that passes the disclosure tests in D2 Section 10 is released as open data. Finer data goes to approved researchers under a data use agreement.
4. **Licences are preserved, not overridden.** Programme code is Apache 2.0. OpenEMS Edge and Backend remain Eclipse Public License 2.0 and the UI remains AGPL 3.0. Third-party components keep their own terms (C4 Section 13).
5. **Version-pinned and reproducible.** Every artefact states the OpenEMS release, driver version, device firmware and configuration tag it was tested with (B6, C4). Users are told to retest.
6. **Negative results ship too.** Failed tests, rolled-back changes and null results are included in sanitised form with equal prominence (Charter Section 21).
7. **No history leaks.** A public repository is built from a clean, scanned export, not by flipping a private repository to public. Git history is checked for secrets and personal data before publication.
8. **Upstream first where appropriate.** Custom drivers and fixes are offered to the OpenEMS community after TWG review (Charter Section 21, B6 Section 8).
9. **Someone owns it afterwards.** A named custodian maintains the repository, answers issues and handles vulnerability reports after Gate 5 (Charter Section 24).

**What cannot be settled from desk research.** The actual driver set, the final component list, data volumes, the licence compatibility opinion, the hosting platform and the custodian are not yet known. This document fixes the method and leaves those as placeholders for Gates 1 to 5.

## 2. Document control and relationships

**Owner:** Software engineer (README E5), under the Technical Lead. **Contributors:** Technical Lead, Research Lead and data analyst, Cybersecurity and Data Protection Officer, Legal and regulatory lead, Capacity-building lead, university partner, Programme Manager and PMO, counsel. **Review:** independent reviewer (Charter Section 23), Research and Evaluation Panel for any dataset or claim drawn from results, security and privacy review. **Approval:** Programme Director. Method approved at Gate 1, repositories and tooling ready at Gate 2, release candidate at Month 22, final release at Gate 5 (Month 24). Changes follow Charter Section 20.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 5, 12, 16, 21, 23, 24) | Open by default, Apache 2.0 repository, upstream contribution, publication governance, closure and custodians |
| OpenEMS Configuration Baseline (C4, Sections 5, 8, 13, 14) | Repository structure, what is published and withheld, SBOM, licence register, secrets rules |
| Interoperability Register (B6, Sections 8, 10) | Driver register, test records, version pinning, upstream plan |
| Cybersecurity Plan (B7, Sections 6.9, 6.10, 9) | Repository security, pre-release scan, SBOM, public code and private operations |
| Data Management and Privacy Plan (D2, Sections 9, 10, 13) | Anonymisation standards, minimum group size, release process, data use agreements, custodianship |
| Monitoring and Evaluation Plan (D1) and Monthly Reports (D6) | KPI dictionary, analysis code, data dictionary, restatement rules |
| Final Evaluation Report (E2), Interim Report (E1) | Results the datasets must reproduce and not contradict |
| Lessons Learned and Replication Guide (E3, Section 23) | Reusable artefacts list this package implements |
| Policy Brief (E4), Paper (E6) | Cite the release by version and persistent identifier |
| Site Acceptance Tests (C5), Installation Plan (C3), HSE Plan (C6), O&M Manual (D3), Training Records (D4), Incident and Change Log (D5) | Templates and sanitised records released as reusable documents |
| Procurement Plan (C1), Regulatory Compliance Assessment (B5) | Tender templates and the regulatory question set released as open templates |
| MoU and Site Agreement templates (MoU Sections 9, 10; Site Agreement Sections 9.3, 12) | Open licensing, publication rights, host data limits |
| Risk Register (A6) | Receives release risks |

## 3. Scope and audience

**In scope.** Preparation, review, licensing, packaging, publication, versioning, support and handover of the open release: code, configuration, scripts, test sets, templates, documentation, anonymised datasets and release notes. Period: from repository creation (Month 4) to handover (Gate 5), plus the custodian's maintenance plan.

**Out of scope.** Core development of OpenEMS beyond drivers and configuration (Charter Section 5). Commercial support. Legal advice. Publication of the evaluation findings themselves, which is E2, E4 and E6 (E5 releases the code and data behind them).

| ID | Audience | What they need from E5 |
| --- | --- | --- |
| U1 | OpenEMS community and association | Drivers and fixes with clear licences, upstream pull requests, documented test evidence |
| U2 | Developers, EPCs and integrators in Kenya | Configuration templates, compatibility test method, scripts, example configurations |
| U3 | Utilities (Kenya Power) and regulators | Reproducible KPI code, test scripts, measurement method |
| U4 | Researchers and universities | Anonymised data, data dictionary, analysis code to reproduce E2 |
| U5 | Hosts, operators and trainers | Operator and training templates, alarm cards, checklists |
| U6 | Funders | Evidence that outputs are open, versioned and maintained |

## 4. Principles

| Principle | What it means in practice |
| --- | --- |
| Open by default | Everything not on the withheld list is published. A withholding needs a recorded reason |
| Safe by review | Every public artefact passes the same review chain, with a release record |
| Licence clarity | Each file is covered by one stated licence, with headers and a top-level NOTICE |
| Reproducible | A third party can rebuild the images, rerun the tests and regenerate the published figures from the release, where data allows |
| Honest about limits | Results apply to the tested release, firmware and conditions. The README says so |
| Useful, not just available | Documentation, examples and a quick start are part of the release, not an afterthought |
| Local first | English with Kiswahili summaries for community-facing material. Plain language where possible |
| Proportionate | Small teams can use the templates without adopting pilot-level research governance (E3 Section 4) |
| No endorsement claims | Releases do not state or imply regulator, vendor or host endorsement (MoU Section 12) |

## 5. Roles and responsibilities

| Role | Responsibility in the release |
| --- | --- |
| Steering Committee | Approves publication and handover at Gate 5. Names the custodian with the Programme Sponsor |
| Programme Director | Accountable for release approval. Signs the release record |
| Software engineer (E5 owner) | Builds the package, maintains repositories and tooling, runs scans, prepares release notes, manages upstream contributions |
| Technical Lead | Approves technical content and driver quality. Owns the licence compliance register. Chairs TWG review |
| Research Lead and data analyst | Approve datasets, analysis code and data dictionary. Run disclosure checks. Confirm consistency with E2 |
| Cybersecurity and Data Protection Officer | Security and privacy review, secret and history scan, SBOM check, vulnerability disclosure route, data use agreements |
| Legal and regulatory lead and counsel | Licence compatibility opinion, contributor terms, trademark and naming, data use agreement terms |
| Capacity-building lead | Training materials, Kiswahili versions, community-facing release notes |
| University partner | Hosting or mirroring, persistent identifiers, research data deposit, co-maintenance |
| Independent reviewer | Reviews the release candidate for balance and completeness |
| Programme Manager and PMO | Tracks the release plan, risks, actions and budget |
| Custodian (named at Gate 5) | Maintains the repository, triages issues, handles vulnerability reports, issues updates |
| Hosts, Kenya Power, EPRA, vendors | Review items that name them. May correct facts and request redaction of confidential data. Cannot require removal of evidenced negative findings |

## 6. Package contents

The package has seven components. Each has an ID used in the manifest (Appendix A).

| ID | Component | Content | Source | Licence | Visibility |
| --- | --- | --- | --- | --- | --- |
| P1 | Configuration repository | Templates, schema, sanitised per-site configuration, manifests (sanitised), mode schedule structure, tests, tooling | C4 `openems-kenya-config` | Apache 2.0 | Public, sanitised |
| P2 | Drivers repository | Custom drivers and mappings with unit tests, driver register, upstream status | B6, C4 `openems-kenya-drivers` | Apache 2.0, with upstream component licences preserved | Public |
| P3 | Image build recipe | Edge image build scripts, hardening scripts, SBOM generation. No signing keys, no built production images | C4 `openems-kenya-images` | Apache 2.0 | Public recipe only |
| P4 | Test and acceptance kit | Compatibility test sets (T-COM, T-BAT, T-EVC and others), site acceptance scripts, test record templates, load-step methods | B6, C5 | Apache 2.0 for scripts, documentation licence for text | Public |
| P5 | Evaluation code and data | KPI dictionary, analysis plan, pipeline, report templates, data dictionary, anonymised datasets, restricted-access datasets by agreement | D1, D6, D2 | Apache 2.0 for code, [CC BY 4.0] for data and documentation | Public and restricted |
| P6 | Operational and training templates | Operator manual template, alarm card, logbooks, incident and change registers, permit and emergency sheets, curriculum, assessments, certificate template | D3, D4, D5, C6 | [CC BY 4.0] for text, Apache 2.0 for scripts | Public, site values removed |
| P7 | Planning and governance templates | Tender and pre-qualification templates, vendor and security questionnaires, regulatory question set, host agreement and MoU templates, replication cost model, replication guide | C1, B5, MoU templates, E3, B2 | [CC BY 4.0] | Public, with "not legal advice" notice |

**Release identifiers.** Each component is versioned independently with semantic versions, and the package as a whole has a release tag `E5-v[major].[minor].[patch]`. The first full release is `E5-v1.0.0` at Gate 5. Earlier snapshots (`v0.x`) may be published at Gates 2 to 4 for templates and tooling only, never for data (Section 12).

### 6.1 Included and withheld

| Included | Withheld |
| --- | --- |
| Templates, schema, tooling, mode schedule structure | Credentials, keys, tokens, sealed credential records |
| Sanitised per-site configuration (parameters, controller settings, component list) | Network diagrams of live sites, IP plans, firewall rules, VPN details |
| Custom drivers and mappings, with tests | Host-confidential parameters (production schedules, tariff contract terms) without host consent |
| Device and firmware list (serials removed if the Officer advises) | Unpatched vulnerability details until fixed and disclosed responsibly |
| Test records including failures, in sanitised form | Personal data of any kind, including identifiable training and complaint records |
| Change log summaries, including failed and rolled-back changes | Raw identifiable household and driver data, and pseudonymisation key tables |
| Anonymised and aggregated datasets that pass the disclosure tests | Signing keys, production images with embedded secrets |
| Templates for contracts, tenders and agreements | Executed agreements and vendor-confidential prices |

## 7. Licensing

### 7.1 Licence map

| Material | Licence | Notes |
| --- | --- | --- |
| Programme code, scripts, configuration, tooling | Apache License 2.0 | Headers on every file. Top-level `LICENSE` and `NOTICE` |
| OpenEMS Edge and Backend (not modified or modified) | Eclipse Public License 2.0 | Component licence preserved. Modified files marked. Source-availability duties tracked |
| OpenEMS UI | AGPL 3.0 | Any modified UI offered over a network triggers source-sharing duties. Tracked in the licence register |
| Documentation, templates, curriculum, text and images | [CC BY 4.0] | Decision pending (open item 3). Counsel to confirm |
| Data (anonymised datasets) | [CC BY 4.0] or an open data licence with a no-re-identification term | Decision pending (open item 4) |
| Third-party libraries and tools | Their own licences | Listed in the SBOM and `THIRD_PARTY_LICENSES` |
| Vendor documents and register maps | Vendor terms | Only published where permitted. Otherwise referenced, not copied (C1 Section 11.2) |

### 7.2 Licence rules

1. **Compatibility opinion first.** Counsel confirms that Apache 2.0 programme code, EPL 2.0 components and AGPL 3.0 UI can be distributed together as planned, and how the package is split to avoid combining works unintentionally (B5 open question 10).
2. **Separation by repository.** Programme code lives in Apache 2.0 repositories. Modified OpenEMS components, if any, live in clearly marked forks that keep their licence.
3. **File headers.** Each source file carries an SPDX identifier and copyright line. Scripts and documents without headers are covered by a directory-level `LICENSE`.
4. **No copyleft surprises.** The SBOM is scanned for licences that conflict with the plan. Conflicts are resolved or the component is removed.
5. **Contributor terms.** Contributions follow a Developer Certificate of Origin or an equivalent contributor agreement [decision pending, open item 5]. Employer and university IP positions are confirmed in writing before external contributions are accepted.
6. **Trademarks and names.** The OpenEMS name and any vendor names are used factually. The package does not imply endorsement by the OpenEMS community, vendors or regulators.
7. **Patents.** Counsel notes the Apache 2.0 patent grant and any vendor patent statements in warranty letters [confirm].
8. **Licence change.** Any change to a component licence after release needs Technical Lead and counsel approval and a public note.

### 7.3 Licence compliance register

Maintained by the Technical Lead (C4 Section 13). Template in Appendix C.

## 8. Anonymisation and data release

This section applies D2 Section 10 to the release. If a rule here differs from D2, D2 prevails.

### 8.1 Data tiers

| Tier | Content | Access | Basis |
| --- | --- | --- | --- |
| T0 Open | Site-level and aggregated energy series, KPI series, supporting indicators, anonymised summaries | Public download | Passes all disclosure tests |
| T1 Restricted | Finer-grained or pseudonymised research data (for example household data at transformer-group level with fewer customers, session distributions) | Approved researchers under a data use agreement | D2 Section 13 |
| T2 Internal | Raw identifiable data, key tables, host commercial data, utility customer-level data | Programme and named analysts only. Never released | D2 Section 8 |

### 8.2 Disclosure tests for T0

| Test | Rule |
| --- | --- |
| Minimum group size | No figure based on fewer than [k] customers, sessions or vehicles. Proposal k = [5], with checks for dominant contributors |
| Resolution | Household data only at feeder or transformer-group level. Charger data only at hourly or session-distribution level, never with timestamps that single out a vehicle |
| Identifiers removed | No names, meter IDs, plates, tokens, GPS for private households, exact timestamps that single out people |
| Rare events | Outages, theft and unusual loads rechecked for re-identification risk |
| Host data | Identifiable host commercial data only with host consent. Aggregated results cannot be blocked (Site Agreement 9.3) |
| Linkage risk | A re-identification test is run by someone other than the preparer, including linkage with the published results and public information |
| Reproducibility | Published datasets are sufficient to reproduce the published KPIs, within the stated disclosure limits. Where they cannot be, the release says so |
| Equal prominence | Datasets and notes include periods with gaps, faults and failures, flagged with mode codes, not removed |

### 8.3 Data package contents

| Item | Content |
| --- | --- |
| Data files | Open formats (CSV, Parquet or similar) with checksums |
| Data dictionary | Field names, units, source, mode flags M0 to M4, exclusions, uncertainty notes (D1 Appendix A) |
| Datasheet | Purpose, collection method, known gaps, restatements, disclosure treatment, known limitations |
| Provenance | Link to the monthly report, configuration tag and hash for each period |
| Citation and identifier | Persistent identifier (for example DOI via the university or a research data repository) and a recommended citation |
| Licence and terms | Data licence, no-re-identification term, contact for T1 requests |
| Deletion and return confirmations | Not published. Held internally and confirmed to hosts (Site Agreement 16.3) |

### 8.4 Data use agreement (T1)

Short, plain-language agreement covering: purpose, no re-identification, no linkage to identify people, storage and security, destruction date, citation, no onward sharing, breach notice within [48] hours, and the right of the programme to withdraw access (D2 Section 13). The Cybersecurity Officer approves each request and the data analyst provides the extract.

## 9. Review chain and release gates

### 9.1 Review chain per release

| Step | Owner | Check | Output |
| --- | --- | --- | --- |
| 1. Build clean export | Software engineer | Release candidate built from a clean tree, not from private history. Dependencies pinned | Candidate bundle |
| 2. Technical review | Technical Lead, second engineer | Builds, tests pass, documentation matches code, driver quality, versions pinned | Review note |
| 3. Accuracy check | Research Lead | Datasets and analysis code consistent with E2 and Panel-validated data | Accuracy note |
| 4. Licence check | Technical Lead, counsel | Headers, SBOM, third-party licences, NOTICE, compatibility opinion | Licence note |
| 5. Security and privacy review | Cybersecurity Officer | Secret scan, history scan, network details, vulnerability check, disclosure tests, re-identification test | Release clearance |
| 6. Involved-party review | Programme Manager | Hosts, Kenya Power, EPRA, vendors and communities see items that name them for [14] days. Facts corrected, personal or confidential data redacted | Comments log |
| 7. Independent review | Independent reviewer | Balance, completeness, equal prominence of negative results | Review note |
| 8. Approval | Programme Director | All notes present. Release record signed | Release record (Appendix B) |
| 9. Publish and verify | Software engineer | Publish, verify checksums and signatures, test a fresh install from the public source | Publication record |
| 10. Announce | Programme Manager | Release notes, community notice, upstream notice | Announcement |

A privacy objection may delay a release by up to [60] days and may not reshape an evidenced finding (MoU Section 10.3).

### 9.2 Release schedule by gate

| Gate | Release | Content | Data included? |
| --- | --- | --- | --- |
| Gate 1 (Months 4 to 6) | `v0.1` | Repository structure, schema, templates, compatibility test method, KPI dictionary template | No |
| Gate 2 (Month 8) | `v0.2` | Lab-tested configuration templates, first drivers, test kit, tender and questionnaire templates | No |
| Gate 3 (Month 12) | `v0.3` | Sanitised commissioning scripts, acceptance kit, build lessons, templates for operations and training | No |
| Gate 4 (Month 18) | `v0.4` | Updated drivers and tests, interim aggregated summary (T0) if the Panel and Officer clear it | Aggregated only |
| Month 22 | Release candidate | Full package assembled, review chain started | Candidate T0 and T1 |
| Gate 5 (Month 24) | `v1.0.0` | Full package, data, replication guide, custodian briefed | T0 public, T1 by request |

Early snapshots publish tools, not results. Results are released only after Panel validation (D6 Section 1).

## 10. Repository standards

### 10.1 Required files in each public repository

| File | Content |
| --- | --- |
| `README.md` | What it is, status, supported OpenEMS release, quick start, limits, how to cite, contact |
| `LICENSE` and `NOTICE` | Licence text and attribution, upstream licences listed |
| `THIRD_PARTY_LICENSES` and SBOM | Generated, versioned, checked |
| `SECURITY.md` | How to report a vulnerability, response targets, supported versions, safe-harbour wording [counsel] |
| `CONTRIBUTING.md` | How to contribute, contributor terms, review rules, upstream-first rule, code of conduct |
| `CODE_OF_CONDUCT.md` | Respectful conduct, reporting route |
| `CHANGELOG.md` | Version history including failed and reverted changes |
| `VERSIONS.md` | Pinned OpenEMS release, image, tested firmware (from B6) |
| `CITATION.cff` | Citation metadata with persistent identifier |
| `docs/` | Install, configuration, test, release and maintenance guides, in English with Kiswahili summaries for community-facing parts |
| `CODEOWNERS` | Maintainers and reviewers |

### 10.2 Quality gates (automated where possible)

| Gate | Requirement |
| --- | --- |
| Build and test | All unit and integration tests pass on a clean environment |
| Schema validation | Configuration passes the schema (C4 V1) |
| Secret scanning | No secrets in files, history or logs (C4 V11) |
| Dependency scan | No known critical vulnerabilities without a recorded mitigation |
| Licence scan | No conflicting or unknown licences |
| Link and sanitisation check | No live IPs, hostnames, site coordinates for households, serials where the Officer advises against |
| Reproducibility | Image build and published KPI figures can be regenerated from the release inputs, within data limits |
| Documentation | README quick start tested by a person who did not write it |

### 10.3 Branching, tags and signing

Branching, tagging and versioning follow C4 Section 5.4. Public releases use signed tags and checksummed bundles. Signing keys are held by the Cybersecurity Officer and the custodian, never in a repository, and rotated at handover.

### 10.4 Repository history

The public repositories are created from a scanned, squashed or filtered export. Private history is not published. If private history must be preserved for provenance, it is first scanned with automated tools and reviewed manually, and any secret found is treated as exposed and rotated (B7, C4).

## 11. Documentation and usability

| Item | Requirement |
| --- | --- |
| Quick start | A person with Linux and OpenEMS basics can run the lab configuration and test set in [x] hours using only the public documentation [test with a non-author] |
| Examples | At least one worked example per scenario (C&I, microgrid, EV depot), using synthetic or fully anonymised data |
| Tutorials | Configuration, compatibility testing, acceptance test scripting, KPI calculation |
| Reference | Component naming convention, parameter tables, safe-state and limit layer rules, mode schedule structure |
| Translations | Kiswahili summaries for operator, safety, community and training materials. English prevails unless counsel advises otherwise |
| Accessibility | Plain language, short sentences, diagrams with text alternatives, status not conveyed by colour alone |
| Caveats | Every guide states: research pilot, tested versions only, retest before use, not a substitute for a licensed engineer, insurer or advocate |
| Safety notice | Prominent notice that battery, electrical and charger work needs licensed contractors, hardware protection proof and hold points (C3, C6) |

## 12. Upstream contribution

| Item | Plan |
| --- | --- |
| Candidates | Drivers and mappings with passing L3 tests, bug fixes found in testing, documentation improvements, test tooling |
| Process | TWG review, licence and contributor-terms check, discussion with the OpenEMS community, pull request following upstream guidelines, programme responds to review comments |
| Fork policy | Minimise forks. Where unavoidable, keep patches small, documented and rebased. Mark modified files |
| Status record | The driver register (B6 Section 8) records upstream status: offered, accepted, declined, later |
| Declined contributions | Remain in the programme drivers repository with a note on why and the supported release |
| Credit | Contributors and the programme are credited in release notes and per upstream practice |
| Relationship | Contribution is not conditional on upstream acceptance. The programme does not claim upstream endorsement |

Evidence tag for upstream acceptance expectations: [N] until tested.

## 13. Vulnerability handling and security after release

| Item | Plan |
| --- | --- |
| Disclosure route | `SECURITY.md` names a contact and a response target [x] working days. Reports are handled by the Cybersecurity Officer, then the custodian |
| Coordinated disclosure | Fix first, disclose after mitigation. Vendor and OpenEMS community notified where the issue is theirs (B7 Section 6.9) |
| Withheld detail | Unpatched details are not in public issues or release notes until fixed |
| Patch releases | Security fixes ship as patch releases with advisory text, affected versions and mitigation |
| Dependency watch | The custodian monitors advisories and decides within [5] working days whether a release is needed |
| End of support | Each release states its support window. Unsupported versions are marked clearly |
| Safety link | Any issue that could cause an unsafe battery or charger state is treated as priority one and noted in the advisory |
| Public code, private operations | Published repositories never contain live site secrets or network detail (B7 Section 6.9) |

## 14. Custodianship and sustainability

| Item | Plan |
| --- | --- |
| Custodian | Named at Gate 5 (for example the university partner, the Ministry of Energy, a utility or a community organisation). Decision [ ] |
| Handover content | Repositories, signing and release procedures, secrets for hosting accounts (transferred securely), issue tracker, mailing list, the licence register, the SBOM process, the data request process and the data use agreement template |
| Handover briefing | Written and on-screen briefing with the software engineer. A test release made by the custodian under supervision |
| Maintenance budget | A small annual line [KSh [ ]] in the post-pilot plan (Charter Section 24) |
| Governance | Maintainers list, decision rules, review rules for merges, route for community maintainers to join |
| Review cycle | Yearly review and update after any major OpenEMS release, regulatory change or reported incident |
| Retirement | The custodian states a review date. If no maintainer exists, the repository is marked archived and read-only with a notice, not silently abandoned |
| Hosting | Platform [to be chosen, open item 1]. Mirrors at the university and an archive deposit for the data. Avoid single-vendor lock-in for the only copy |

## 15. Release communication

| Audience | Channel | Content |
| --- | --- | --- |
| OpenEMS community | Community forum or mailing list, upstream issue tracker | What was released, which drivers are offered upstream, known limits |
| Developers and integrators in Kenya | Project web page, workshops with the university and vocational partners | Quick start, examples, training dates |
| Regulators and utilities | Regulatory and Stakeholder Forum, briefing note | What templates and code are available, how to reproduce KPIs, control-boundary statement |
| Hosts and communities | Plain-language English and Kiswahili summary | What is public, what is not, data protection summary |
| Funders and media | Release note and media briefing at Gate 5 | Open outputs, where to find them, honest limits statement |

All communication states that this was a research pilot, results are measured not guaranteed, and the release is not a guarantee of savings or a product warranty. No claims of endorsement by regulators, vendors or hosts.

## 16. Schedule

| Activity | Months | Output | Gate |
| --- | --- | --- | --- |
| Approve method, component list, licence map and review chain | 4 to 6 | This document v0.1 reviewed | **Gate 1** |
| Counsel licence compatibility opinion | 4 to 6 | Opinion | Gate 1 |
| Create repositories, CI, scanning, SBOM tooling, templates | 4 to 8 | Tooling live | **Gate 2** |
| `v0.1` and `v0.2` template and tool snapshots | 6 to 8 | Public snapshots | Gates 1, 2 |
| Capture driver and test artefacts continuously | 4 to 24 | Repositories | |
| `v0.3` commissioning and operations templates | 12 | Public snapshot | **Gate 3** |
| `v0.4` with interim aggregated summary (if cleared) | 18 | Public snapshot | **Gate 4** |
| Data preparation, disclosure tests, re-identification test | 20 to 22 | T0 and T1 candidates | |
| Release candidate and review chain | 22 to 23 | Reviewed candidate | |
| Involved-party comment period | 23 | Comments log | |
| Gate 5 approval, publication, custodian handover | 24 | `v1.0.0`, handover record | **Gate 5** |

| Gate | Evidence from E5 |
| --- | --- |
| Gate 1 | Approved method and licence map. Counsel engaged. Budget for tooling, hosting and review |
| Gate 2 | Repositories and scanners live. First template snapshot published. Review chain tested on a dry run |
| Gate 3 | Commissioning and operations templates published. No secrets found in public history. Licence register current |
| Gate 4 | Driver and test updates published. Upstream status recorded. Interim data decision recorded |
| Gate 5 | Full release published. Checksums verified. Custodian briefed and a test release made. Release record signed |

**Critical path.** The data release depends on Panel-validated results (Months 22 to 24) and the comment period. Tools and templates do not, so they are released early. If data is late, the code and templates release at Gate 5 and the data follows within [x] weeks, stated openly.

## 17. Budget and resources

Costs come from the PMO, the software engineer's time, counsel review, the university partner's budget line and the dissemination share. Items to itemise before Gate 1: repository hosting and mirrors, CI and scanning tools, signing infrastructure, counsel licence opinion, independent review, translation of Kiswahili summaries, documentation and editing, persistent identifier and data deposit, workshops, custodian handover, annual maintenance. Amount: KSh [to be confirmed at Gate 1]. Use of contingency needs Steering Committee approval (Charter Section 20).

## 18. Risks to add to the live Risk Register

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| OS1 | A secret, credential or live network detail is published, in files or history | L | H | Clean export, secret and history scans, pre-release review, rotation procedure | Cybersecurity Officer |
| OS2 | Re-identification from released datasets | M | H | k threshold, tiers, independent re-identification test, data use agreement | Data analyst |
| OS3 | Licence conflict or non-compliance (EPL, AGPL, Apache) | L | M | Counsel opinion, repository separation, SBOM scan, licence register | Technical Lead |
| OS4 | Release read as vendor, regulator or host endorsement, or as a performance guarantee | M | M | Factual wording, no-endorsement rule, caveats in every README | Programme Manager |
| OS5 | Public details enable attacks on pilot sites or future adopters | L | H | Withheld list, coordinated disclosure, patch releases, safe defaults | Cybersecurity Officer |
| OS6 | No custodian or maintenance funding after Gate 5, so the release goes stale | M | H | Name custodian early, maintenance budget line, archive notice if unmaintained | Programme Sponsor |
| OS7 | Pressure to delay or soften release of negative findings or failed tests | M | H | Equal prominence rule, MoU Section 10 limits, independent reviewer | Programme Director |
| OS8 | Users apply tested configurations to different firmware or releases and cause unsafe behaviour | M | H | Version pinning, retest instructions, safety notices, hold points in the guide | Technical Lead |
| OS9 | Upstream declines drivers, leaving the programme to maintain forks | M | M | Small patches, documented fork policy, custodian plan | Software engineer |
| OS10 | Release assembled late, with insufficient time for the review chain | M | M | Release candidate at Month 22, dry runs at Gates 2 to 4 | Software engineer |
| OS11 | Release effort under-budgeted (review, translation, hosting, maintenance) | M | M | Itemise before Gate 1 | Programme Manager |
| OS12 | Contributor IP or employer rights unclear, blocking release of code | L | M | Written IP confirmations before external contributions, university and vendor agreements | Legal and regulatory lead |

These risks are to be merged into the live Risk Register (README A6).

## 19. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Choose the hosting platform, mirrors and data deposit, with access roles and no single point of loss | Gate 1 | Software engineer, Technical Lead |
| 2 | Obtain counsel's opinion on the Apache 2.0, EPL 2.0 and AGPL 3.0 mix and repository split | Gate 1 | Legal and regulatory lead, counsel |
| 3 | Choose the documentation licence (for example CC BY 4.0) | Gate 1 | Technical Lead, counsel |
| 4 | Choose the data licence and the no-re-identification term | Gate 3 | Research Lead, Officer, counsel |
| 5 | Decide contributor terms (DCO or contributor agreement) and the IP positions of the university and vendors | Gate 2 | Legal and regulatory lead |
| 6 | Set minimum group size k and the T0 and T1 boundaries | Gate 1 | Research Lead, Officer |
| 7 | Agree how vendors are named and how their responses are published | Gate 3 | Programme Director, counsel |
| 8 | Decide whether production images are ever published, or only the build recipe | Gate 2 | Cybersecurity Officer, Technical Lead |
| 9 | Decide what is published at Gate 4 (interim aggregated data or tools only) | Gate 4 | Research Lead, Panel, Officer |
| 10 | Agree safe-harbour and disclosure wording for `SECURITY.md` | Gate 2 | Officer, counsel |
| 11 | Decide the persistent identifier route and citation form | Gate 3 | University partner, Research Lead |
| 12 | Decide the upstream approach for each driver with the OpenEMS community | Gate 3 | Technical Lead |
| 13 | Name the custodian, maintainers and annual maintenance budget | Gate 5 | Programme Sponsor |
| 14 | Decide Kiswahili and local-language production route for community-facing material | Gate 4 | Capacity-building lead |

## 20. Immediate next steps

1. TWG and Panel to review this structure, including the Kenya Power grid engineer on what utility-related detail may be public.
2. Engage counsel on the licence compatibility opinion and the documentation and data licences.
3. Software engineer to create the repository skeletons, CI, secret scanning, SBOM generation and licence scanning (C4 Section 19 step 2).
4. Agree the T0, T1 and T2 boundaries and the minimum group size with the Research Lead and Officer.
5. Draft `SECURITY.md`, `CONTRIBUTING.md` and the contributor terms.
6. Plan the dry-run of the review chain at Gate 2 on template content.
7. Open talks with the OpenEMS community about upstream contribution and review practice.
8. Itemise release, hosting, translation and maintenance costs in the budget reconciliation.
9. Add risks OS1 to OS12 and the open items to the PMO log and Risk Register.

---

# Appendix A: Release manifest (template)

```yaml
release:
  id: "E5-v[1.0.0]"
  date: "[YYYY-MM-DD]"
  gate: "[Gate 5]"
  approved_by: ["[Programme Director]", "[Research Lead]", "[Cybersecurity Officer]", "[independent reviewer]"]
  release_record: "[reference]"

platform:
  openems_release: "[version]"
  openems_commit: "[id]"
  edge_image_recipe_tag: "[tag]"
  sbom_ref: "[document ID]"

components:
  - id: "P1"
    name: "openems-kenya-config"
    version: "[x.y.z]"
    licence: "Apache-2.0"
    sha256: "[hash]"
    visibility: "public-sanitised"
  - id: "P2"
    name: "openems-kenya-drivers"
    version: "[x.y.z]"
    licence: "Apache-2.0"
    sha256: "[hash]"
    upstream_status: "[offered | accepted | declined | later]"
  - id: "P3"
    name: "openems-kenya-images (recipe only)"
    version: "[x.y.z]"
    licence: "Apache-2.0"
    sha256: "[hash]"
  - id: "P4"
    name: "test-and-acceptance-kit"
    version: "[x.y.z]"
    licence: "Apache-2.0 / [CC BY 4.0]"
    sha256: "[hash]"
  - id: "P5"
    name: "evaluation-code-and-data"
    version: "[x.y.z]"
    licence: "Apache-2.0 (code) / [data licence]"
    datasets:
      - id: "DS-[ ]"
        tier: "[T0 | T1]"
        k_threshold: "[5]"
        disclosure_test_ref: "[record]"
        reidentification_test_ref: "[record]"
        sha256: "[hash]"
  - id: "P6"
    name: "operational-and-training-templates"
    version: "[x.y.z]"
    licence: "[CC BY 4.0]"
  - id: "P7"
    name: "planning-and-governance-templates"
    version: "[x.y.z]"
    licence: "[CC BY 4.0]"

tested_set:
  devices_and_firmware: "[B6 register extract reference]"
  note: "Results apply only to the tested combination. Retest before use."

withheld:
  confirmed: ["credentials", "live network details", "personal data", "host-confidential data", "unpatched vulnerabilities", "signing keys"]
  scan_reports: ["[secret scan]", "[history scan]", "[licence scan]", "[dependency scan]"]

custodian:
  name: "[ ]"
  handover_record: "[reference]"
  support_window: "[until date]"
```

# Appendix B: Release record and sign-off (template)

| Field | Entry |
| --- | --- |
| Release ID and date | [ ] |
| Components and versions included | [ ] |
| Review notes attached (technical, accuracy, licence, security and privacy, independent) | [ ] |
| Involved-party comments and how handled (dates, redactions) | [ ] |
| Disclosure tests and re-identification test results | [ ] |
| Secret, history, licence and dependency scan results | [ ] |
| Open conditions and owners | [ ] |
| Delay requested under MoU Section 10.3 (Y/N, reason, length) | [ ] |
| Publication record (platform, URL, checksums verified, fresh-install test) | [ ] |

| Role | Name | Signature | Date |
| --- | --- | --- | --- |
| Software engineer (author) | [ ] | | |
| Technical Lead | [ ] | | |
| Research Lead (accuracy) | [ ] | | |
| Legal and regulatory lead (licence) | [ ] | | |
| Cybersecurity and Data Protection Officer (release clearance) | [ ] | | |
| Independent reviewer | [ ] | | |
| Programme Director | [ ] | | |

# Appendix C: Licence compliance register (template)

| ID | Component | Version | Origin | Licence (SPDX) | Modified by programme (Y/N) | Distribution form | Obligations (notice, source, network use) | Compatibility checked (counsel, date) | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| LC-01 | OpenEMS Edge | [ ] | Upstream | EPL-2.0 | [ ] | [ ] | [ ] | [ ] | |
| LC-02 | OpenEMS UI | [ ] | Upstream | AGPL-3.0 | [ ] | [ ] | Source offer for modified versions over a network | [ ] | |
| LC-03 | OpenEMS Backend (if used) | [ ] | Upstream | EPL-2.0 | [ ] | [ ] | [ ] | [ ] | |
| LC-04 | Programme drivers | [ ] | Programme | Apache-2.0 | n/a | [ ] | Notice and headers | [ ] | |
| LC-05 | Programme configuration and scripts | [ ] | Programme | Apache-2.0 | n/a | [ ] | Notice and headers | [ ] | |
| LC-06 | Third-party libraries | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | From SBOM |

# Appendix D: Pre-release checklist (per release)

| # | Check | Evidence | Done |
| --- | --- | --- | --- |
| 1 | Candidate built from a clean export. Dependencies pinned | Build log | [ ] |
| 2 | All tests pass. Schema validation passes | CI record | [ ] |
| 3 | Secret scan clean on files, history and logs | Scan report | [ ] |
| 4 | No live IPs, hostnames, VPN, firewall or site-identifying detail | Sanitisation report | [ ] |
| 5 | SBOM generated. Licence scan clean. THIRD_PARTY_LICENSES complete | SBOM, scan | [ ] |
| 6 | Licence headers and NOTICE present. Counsel opinion on file | Licence note | [ ] |
| 7 | Dependency vulnerability scan reviewed | Scan report | [ ] |
| 8 | Versions, firmware and release pinned in VERSIONS.md and manifest | Manifest | [ ] |
| 9 | Datasets pass disclosure tests. Independent re-identification test done | Test records | [ ] |
| 10 | Data dictionary, datasheet and provenance complete | Documents | [ ] |
| 11 | Datasets consistent with E2 and Panel-validated data | Accuracy note | [ ] |
| 12 | Failed tests, rollbacks and null results included in sanitised form | Content check | [ ] |
| 13 | Safety notices and caveats in every README | Content check | [ ] |
| 14 | Quick start tested by a non-author | Test note | [ ] |
| 15 | Kiswahili summaries ready where required | Documents | [ ] |
| 16 | Involved parties have seen items that name them. Comments handled | Comments log | [ ] |
| 17 | `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `CITATION.cff` present | Files | [ ] |
| 18 | Signing performed. Checksums published | Signature record | [ ] |
| 19 | Independent review complete. Release record signed | Record | [ ] |
| 20 | Fresh-install test from the public source after publication | Publication record | [ ] |

# Appendix E: README template for the public release

| Section | Content |
| --- | --- |
| Title and status | Name, version, date, "research pilot output" statement |
| What this is | Two sentences on OpenEMS Kenya and what the package contains |
| What this is not | Not a product, not a guarantee of savings, not a substitute for a licensed engineer, insurer or advocate, not endorsed by regulators, vendors or hosts |
| Tested set | OpenEMS release, driver versions, device firmware list, conditions. Retest before use |
| Quick start | Steps to run the lab configuration and the test set |
| Safety and security notice | Licensed contractors, hardware protection proof, hold points, no remote access before a security review, no secrets in repositories |
| Data | What data is included, tiers, how to request restricted data, how to cite |
| Licences | Map from Section 7.1 |
| Contributing and upstream | How to contribute, upstream-first rule |
| Reporting issues and vulnerabilities | Public issue tracker, security contact |
| Maintainer and custodian | Names, support window, review date |
| Acknowledgements | Funders, partners, host communities (with consent), contributors |

# Appendix F: Data release record (template, one per dataset)

| Field | Entry |
| --- | --- |
| Dataset ID, title, version | `DS-[ ]` |
| Source datasets (D2 Appendix A IDs) and period | [ ] |
| Tier (T0, T1) | [ ] |
| Pilot and level of aggregation | [ ] |
| Transformation steps (pseudonymisation, aggregation, suppression, rounding, time coarsening) | [ ] |
| Minimum group size applied and suppressions made | [ ] |
| Disclosure test results, tester, date | [ ] |
| Re-identification test (tester independent of preparer), result, date | [ ] |
| Host consent where identifiable host data included | [ ] |
| Mode flags and exclusions included | [ ] |
| Known gaps, restatements, limitations | [ ] |
| Licence and terms | [ ] |
| Checksum and persistent identifier | [ ] |
| Approvals (Research Lead, Officer, Programme Director) | [ ] |

# Appendix G: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 5, 12, 16, 20, 21, 23, 24) | Scope limit on core development, open by default, gates, change control, Apache 2.0 repository, upstream contribution, publication governance, closure |
| Executive Summary and README | Licence statement, E5 definition and owner |
| OpenEMS Configuration Baseline (Sections 5, 8, 9, 13, 14, Appendix C) | Repository structure, secrets rules, integrity, SBOM, licence register, published and withheld lists |
| Interoperability Register (Sections 5, 8, 10) | Driver routes, driver register, upstream plan, version pinning |
| Cybersecurity Plan (Sections 6.1, 6.9, 6.10, 9, 10) | Repository security, supply chain, pre-release scan, disclosure, incident response |
| Data Management and Privacy Plan (Sections 8 to 10, 13, Appendix A) | Access, retention, anonymisation standards, release process, data use agreements, custodianship |
| Monitoring and Evaluation Plan (Appendix A) and Monthly Reports (Sections 8, 11, 12) | KPI dictionary, analysis code, restatements, disclosure rules |
| Final Evaluation Report (E2) and Interim Report (E1) | Results the data must reproduce, publication rules |
| Lessons Learned and Replication Guide (E3, Sections 23 to 25) | Reusable artefacts, custodianship, publication rules |
| Policy Brief (E4) | Citation of the release, evidence tags |
| Procurement Plan, Regulatory Compliance Assessment, Site Acceptance Tests, Installation Plan, HSE Plan, O&M Manual, Training Records, Incident and Change Log | Templates and test sets released as reusable material |
| MoU and Site Agreement templates (MoU Sections 5.2, 9, 10, 12; Site Agreement Sections 9.3, 12) | Open licensing, no-endorsement rule, publication limits, host data |
| Stakeholder Engagement Plan (Sections 6.5, 15) | Upstream relationship, disclosure before publication |

On completion of the Gate 1 decisions (licences, tiers, hosting), counsel's opinion and the final results in E2, each bracketed value is updated, the release record is signed, and this document is re-issued as version 1.0 at Gate 5.

# OpenEMS Configuration Baseline

## 1. Purpose and bottom line

The Technical Specification (B4) says what each site must do. The Interoperability Register (B6) proves which devices can do it. The Installation and Commissioning Plan (C3) says how they are built. This document (C4) is the **single controlled record of exactly what software and settings run on each Edge device**, so that any site can be rebuilt, audited, compared with the evaluation baseline, and handed over without guesswork.

**Bottom line.** For this programme the configuration is part of the evidence, not just an engineering convenience. The evaluation compares each site against a baseline (storage idle or unmanaged) and then with control. If a controller parameter changes silently, the results cannot be trusted. Six rules follow:

1. **Everything that affects behaviour is in version control.** Release, Edge image, component configuration, controller parameters, safe states, limits, schedules and device firmware list. Nothing is changed by hand on a live Edge.
2. **A baseline is a tagged, hashed, signed set.** Each site has a manifest that names the exact versions and hashes. The Edge checks its own configuration against the manifest.
3. **Control modes are configuration states, switched only on the M&V schedule.** The baseline mode (storage idle or unmanaged) and the controlled mode are separate, named configuration sets. Switching between them is a logged change approved by the Research and Evaluation Panel.
4. **Safety limits are never remotely editable.** Safe states and plausibility limits change only through on-site action or a two-person approved change after Gate 3 [decision pending, B7 open item 5].
5. **No secrets in the repository.** The repository is public. Credentials, keys and site network details live elsewhere and are referenced, not stored.
6. **Frozen at Gate 2, changed only through change control.** After freeze, every change is a logged change request, tested off site first, with a rollback.

**What cannot be settled from desk research.** The actual component list, parameters and driver set depend on the devices bought, the topology at Pilot B and the host's network. This document therefore fixes the structure and rules, and gives per-site templates with placeholders to be completed during build.

## 2. Document control and relationships

**Owner:** Software engineer (README C4), under the Technical Lead. **Contributors:** site engineers, Cybersecurity and Data Protection Officer, Research Lead (mode schedule and baseline integrity), Kenya Power grid engineer (limits, via TWG). **Approval:** Programme Director at Gate 1 (method), baselines frozen at Gate 2 and verified at Gate 3. Reviewed fortnightly in the TWG during build, monthly in operation. Changes follow Charter Section 20 change control.

| Document | Relationship |
| --- | --- |
| Programme Charter (Sections 16, 19, 20, 21) | Gates, logged change process for Edge configuration, change control, open-source and publication governance |
| Technical Specification per Site (B4, Sections 3 to 7) | Source of controller functions, parameters to set, safe states and acceptance tests this baseline implements |
| Interoperability and Device Compatibility Register (B6, Sections 5, 8, 10) | Pinned OpenEMS release, driver register, tested firmware set, delta testing rules |
| Cybersecurity Plan (B7, Sections 6.1, 6.3, 6.4, 6.6, 6.7, 6.9) | Configuration integrity, secrets handling, hardening baseline, SBOM, backup and restore |
| Installation and Commissioning Plan (C3, Sections 8.2, 8.8, 13) | Frozen configuration is loaded at Phase 7, hash recorded, handover pack |
| Procurement Plan (C1) | Vendor firmware policy and documentation that feed the manifest |
| Site Agreement templates (Schedule 3) | Control and operating plan: controllers enabled, override rules, safe states, network arrangements |
| Site acceptance test reports (C5) | Evidence that the deployed configuration matches the baseline and behaves as specified |
| Operations and maintenance manual (D3), Incident and change log (D5) | Operators follow the change and restore procedures here. D5 records every change |
| Monitoring and evaluation plan (D1 in README Section D) | Mode schedule and baseline period are defined there and implemented here |

## 3. What the baseline contains

A "configuration baseline" is the complete, reproducible description of one site's running system. It has seven layers. Each layer is pinned and hashed.

| # | Layer | Content | Source of truth | Pinned by |
| --- | --- | --- | --- | --- |
| L1 | OpenEMS release | Edge (and UI, and Backend if used) version, build identifier, commit | B6 Section 10.1 | Release tag and checksum |
| L2 | Edge OS image | Operating system, runtime, packages, hardening settings, service list | B7 Section 6.4 | Signed image and hash |
| L3 | Component configuration | Bridges, device components, meters, battery, charger, generator, sum and scheduler settings | This document, per-site folder | Configuration hash |
| L4 | Controller parameters | Peak setpoints, SoC window, tariff schedule, site limits, policy settings, export limit | B4 Sections 5.2, 6.2, 7.2 | Configuration hash |
| L5 | Safety and plausibility set | Safe states, maximum power, ramp rate, SoC window, fallback limits, override rules | Site Agreement Schedule 3 | Separate hash, protected change route |
| L6 | Device firmware and settings | Firmware version per device, device-side settings that matter (for example inverter limits) | B6 register, vendor documents | Recorded in manifest |
| L7 | Operating mode schedule | Dates and approvals for baseline mode and controlled mode | M&V protocol | Signed mode record |

Plus three companions: the **SBOM** for the production Edge image and each custom driver, the **licence compliance register** entries (B7 Section 6.9), and the **backup and restore record**.

## 4. Principles

| Principle | What it means in practice |
| --- | --- |
| Configuration as code | Text-based, reviewable, diffable files in a repository. No change exists that is not in a commit |
| One source of truth | The repository is authoritative. A live Edge that differs from its manifest is wrong, not the repository |
| Reproducible | A new Edge can be built from the signed image plus the tagged site configuration, with no manual steps beyond secret injection |
| Separation of concerns | Safety limits (L5) are separated from tuning parameters (L4), with different approval and change routes |
| Minimal and explicit | Only components the site needs are enabled. Unused components and services are disabled, not left idle |
| Separation of secrets | Secrets are injected at commissioning from the sealed credential record and never committed (B7 6.1) |
| Open by default, private for sites | Templates, structure, drivers and sanitised examples are published. Live site credentials, network maps and addresses are not (B7 6.9) |
| Evidence integrity | A configuration change that could affect results is time-stamped, approved and visible to the Research Panel (Charter risk 8, B7 6.6) |
| Test before touch | Changes are tested on the lab Edge or a spare first, with rollback prepared |
| Honest records | Failed changes, rollbacks and workarounds are recorded with equal prominence |

## 5. Repository structure and naming

### 5.1 Repositories

| Repository | Content | Visibility |
| --- | --- | --- |
| `openems-kenya-config` | Per-site configuration, templates, manifests, mode schedules, tests, tooling | Public, sanitised (no secrets, no live network details) |
| `openems-kenya-drivers` | Custom drivers and mappings under Apache 2.0, with unit tests | Public, offered upstream after TWG review |
| `openems-kenya-images` | Image build recipe, hardening scripts, SBOM generation | Public recipe. Built images and signing keys held privately |
| `openems-kenya-private` | Site-specific network details, addressing plans, sealed credential record references, host-confidential parameters | Private, access limited to named roles |

The programme repository is released under Apache 2.0. OpenEMS components keep their own licences (Eclipse Public License 2.0 for Edge and Backend, AGPL 3.0 for the UI) and are tracked in the licence compliance register.

### 5.2 Directory layout (public repository)

```
openems-kenya-config/
  README.md
  VERSIONS.md                  # pinned OpenEMS release, image, tested firmware (from B6)
  schema/                      # JSON schema or equivalent for config validation
  templates/
    common/                    # components common to all sites (sum, scheduler, logging)
    pilot-a/  pilot-b/  pilot-c/
  sites/
    SSR-A1/                    # one folder per selected site (survey report ID)
      manifest.yaml            # versions, hashes, approvals (Appendix A)
      components/              # component configuration files (L3)
      controllers/             # controller parameters (L4)
      safety/                  # safe states and limits (L5), protected path
      modes/                   # baseline.yaml, controlled.yaml (L7)
      firmware.yaml            # device firmware list (L6)
      tests/                   # acceptance test scripts and expected results
    SSR-B1/  SSR-C1/
  tools/                       # hash, verify, diff, backup and restore scripts
  CHANGELOG.md
  CODEOWNERS
```

Site folders are created only after Gate 1 site selection. Until then only templates exist.

### 5.3 Component identifier convention

OpenEMS components have an ID that appears in logs, channels and the UI. Consistent IDs make data, tests and support simpler across sites.

| Element | Convention | Example |
| --- | --- | --- |
| Pattern | `[type][index]`, lower camel case, type from a fixed list, index from 0 | `meter0`, `ess0`, `charger0` |
| Controllers | `ctrl[Function][index]` | `ctrlPeakShaving0`, `ctrlTouShift0` |
| Bridges | `modbus[index]`, `ocpp[index]` | `modbus0` |
| Site meters | Role-based, not model-based, so that a device swap keeps the ID | `meterGrid0`, `meterPv0`, `meterTransformer0` |
| Same IDs across sites | Same role gets the same ID at every site | `meterGrid0` at A, B and C |
| Reserved IDs | Core component IDs required by the platform are kept as the release defines them | `[verify against release, for example the sum component]` |

The mapping from register ID in B6 (for example `PVI-A01`) to component ID is recorded in the site manifest.

### 5.4 Branching, tagging and versioning

| Item | Rule |
| --- | --- |
| Branches | `main` (released baselines only), `develop` (work in progress), `site/<ID>/change-<n>` (one branch per change request) |
| Protection | `main` protected. Merge needs two approvals including one independent reviewer. Signed commits for `main`. Two-factor authentication for maintainers (B7 6.9) |
| Tags | `<site>-v<major>.<minor>.<patch>` for example `SSR-A1-v1.0.0`. Signed tags for released baselines |
| Version meaning | Major: change of OpenEMS release, topology or device set. Minor: controller or limit change that alters behaviour. Patch: non-behavioural correction (documentation, comment, label) |
| Frozen baseline | `v1.0.0` is the Gate 2 freeze. Gate 3 verifies that the live Edge matches it |
| Releases | Each tag generates an artefact bundle: configuration, manifest, hashes, SBOM reference, release notes |

## 6. Layer detail

### 6.1 L1 and L2: OpenEMS release and Edge image

| Item | Rule |
| --- | --- |
| Test release | One pinned release for the whole lab campaign, frozen at start of Month 4 (B6 10.1) |
| Production release | Pinned at Gate 2. If it differs from the test release, the TWG decides what is retested (B6 10.3) and records the decision |
| Provenance | Obtained from official sources, checksums or signatures verified before use (B7 6.9) |
| Image build | Reproducible, logged build. Minimal packages, unused ports and services disabled, no default accounts, time sync configured, logging enabled (B7 6.4) |
| Image signing | Production images signed or checksummed. Verified on installation (C3 8.2) |
| Updates | None on live sites outside the logged change process. Automatic updates disabled |
| Spare image | A spare Edge with the same image and the site configuration, or a documented rebuild within [x] hours (B7 6.7) |

### 6.2 L3: Component configuration (common structure)

The component set differs by site, but every site is built from the same layers. Names below are **role descriptions**. Factory identifiers are filled in only after the driver assessment (B6 Section 8) against the pinned release.

| Role | Purpose | Applies to | Factory or driver | Key settings to record |
| --- | --- | --- | --- | --- |
| Core and sum | Aggregates energy flows and system state | A, B, C | `[from release]` | Defaults kept unless justified in the change log |
| Scheduler | Sets the order in which controllers run | A, B, C | `[from release]` | Controller order (Section 7) |
| Communication bridge, Modbus TCP or RTU | Link to inverters, batteries, meters, generator | A, B, (C) | `[from release]` | Host or serial settings, unit IDs, polling interval, timeouts, retries |
| Communication, OCPP | Link to chargers | C | `[from release, OCPP version]` | Version, security profile where supported, heartbeat, timeouts |
| Grid meter | Import and export at the connection point | A, B, C | `[driver ID]` | Meter type, sign convention, interval |
| PV meter or inverter | PV production and limit | A, B | `[driver ID]` | Power limit control mode, read interval |
| Battery system and inverter | Charge and discharge setpoints | A, B, (C) | `[driver ID]` | Max power, SoC limits, start and stop behaviour, alarm handling |
| EV chargers | Session control and logs | C | `[driver ID]` | Min and max current, phases, fallback limit |
| Generator controller | Start and stop and metering | B | `[driver or relay route]` | Start and stop thresholds, minimum run time |
| Transformer meter | Transformer loading | C (A, B where possible) | `[driver ID]` | Read rate, loss-of-feed behaviour |
| Data logging and export | Local persistence and buffering | A, B, C | `[from release]` | Buffer at least [30] days, resolution, retention |
| Time source | Common time reference | A, B, C | OS-level | Source, drift alarm |
| UI and users | Local operator UI and accounts | A, B, C | `[from release]` | Named accounts and roles only (B7 6.1) |

### 6.3 L4: Controller parameters

Parameters are the values that tune behaviour. Each one has an owner, a source and a change route. The first column links to the B4 function.

| Pilot | Function (B4) | Parameters to record | Source of value | Change route |
| --- | --- | --- | --- | --- |
| A | Peak shaving | Peak setpoint (kW), recharge threshold, minimum reserve SoC | Sizing method and baseline analysis (B4 Section 4) | Minor version, Panel notified |
| A | ToU shifting | Tariff schedule (peak, shoulder, off-peak windows), reserve SoC | Tariff documents from host, EPRA tariff | Minor version, Panel approval |
| A | Self-consumption and feed-in limit | Export limit (kW), priority order | EPRA and Kenya Power approval | Protected route (L5), see Section 6.4 |
| A | Critical-load protection | Protected loads list, override procedure | Host agreement | Protected route (L5) |
| B | Self-consumption and SoC management | Reserve SoC for outages, battery life limits | Survey, B4 6.2 | Minor version |
| B | Generator offset | Start and stop thresholds, minimum run time | Generator specification, B4 6.2 | Minor version, protected where it affects generator safety |
| B | Local control and fallback | Fallback rules on loss of link | B4 3.2 rule 3 | Protected route (L5) |
| C | Cluster load balancing | Site limit (kW), per-charger minimum, policy (fair-sharing or priority) | Kenya Power approval, policy in Schedule 3 | Protected route for site limit, minor version for policy |
| C | Maximum wait | Maximum acceptable wait, alarm threshold | Agreed policy | Minor version, Panel notified |
| C | Transformer protection | Thresholds, conservative limit on loss of feed | Kenya Power, B7 7.3 | Protected route (L5) |
| C | Optional battery support | Reserve SoC, charge and discharge windows | Sizing | Minor version |

### 6.4 L5: Safety and plausibility set (protected)

This layer is where cybersecurity and safety meet (B7 6.3). It is stored separately, hashed separately and changes by a stricter route.

| Item | Parameter | Value | Verified by |
| --- | --- | --- | --- |
| Maximum active power per device | kW | `[from device rating and sizing]` | B6 T-COM-07, acceptance tests |
| Ramp rate limit | kW per second | `[x]` | Lab test |
| SoC window | Lower and upper limits, % | `[x]`, `[x]` (must sit inside BMS limits) | T-BAT-02 |
| Rate-of-change limit on setpoints | per interval | `[x]` | Lab test |
| Safe state per device | Battery to idle or minimum export, chargers to fallback limit, generator under own controls | Per Schedule 3 | T-COM-05, T-BAT-09, T-EVC-07 |
| Charger fallback limit | kW or A per charger | `[x]` | T-EVC-07 |
| Site import limit and export limit | kW | `[from Kenya Power and EPRA]` | Acceptance tests A5, C3 |
| Conservative limit on loss of transformer feed (C) | kW | `[with Kenya Power]` | Acceptance test C6 |
| Override rules | Who, how, logging | Per Schedule 3 | Acceptance test A8 |

**Rules for L5.**

1. Values never exceed hardware limits. Hardware protection (BMS, inverter, breakers) acts independently of OpenEMS and is proven before OpenEMS is enabled (C3 Phase 6).
2. L5 is **not editable remotely**, before or after Gate 3. A change needs an on-site action by authorised personnel, or a two-person approved change [decision pending, B7 open item 5, C3 open item 5].
3. Every L5 change is a minor or major version, goes through change control, is tested off site first and is logged in the incident and change log (D5).
4. Lowering a limit is a Technical Lead decision. Raising a grid-related limit needs Kenya Power agreement (for Pilot C, as in C3 Section 11).

### 6.5 L6: Device firmware and device-side settings

| Item | Rule |
| --- | --- |
| Firmware list | `firmware.yaml` per site, listing make, model, serial, firmware version and date, matching the B6 tested combination |
| Match check | At commissioning, installed firmware is compared to the B6 record. A mismatch triggers a delta test before installation (C3 8.2) |
| Held versions | Firmware is held at the tested version. Vendor updates are announced in advance, tested off site, and rolled out through change control (B7 6.4) |
| Device-side settings | Inverter and charger settings that affect behaviour (power limit mode, fallback, minimum current) are recorded in the manifest, because they are outside the Edge file set |
| Vendor access | No vendor remote access to devices unless specified, time-bound, approved by the Cybersecurity Officer and logged |

### 6.6 L7: Operating mode schedule

The evaluation compares each site with and without control. The baseline integrity rule is that **control modes switch only on the M&V schedule** (B4 design rule 7, Charter Section 20).

| Mode | Name | What it means in configuration | Who approves entry |
| --- | --- | --- | --- |
| M0 | Commissioning | Test mode. Data flagged as commissioning so it is excluded from baseline and operating datasets (C3 8.8) | Technical Lead |
| M1 | Monitoring only | All controllers disabled. Battery idle or unmanaged. Measurement running. This is the **baseline mode** | Research and Evaluation Panel |
| M2 | Controlled | Controllers enabled in the sequence in Section 7. This is the **controlled mode** | Research and Evaluation Panel |
| M3 | Fallback or fault | Safe state after device loss, link loss or alarm | Automatic, logged |
| M4 | Maintenance | Planned work, controllers paused, data flagged | Site Lead and Technical Lead |

**Rules.**

- Entry to M1 and M2 is recorded in a signed mode record (date, time, configuration tag and hash, approver) stored with the manifest.
- Where the study uses with and without control periods, each switch is a scheduled, approved event. No re-baselining without Panel approval (Charter risk 8).
- M3 and M4 periods are flagged in the data so analysts can exclude or analyse them separately.
- A configuration change during M1 or M2 that could affect results is treated as a change to the experiment and requires Panel notification, and approval if it alters a KPI-relevant parameter.
- The baseline length and with and without control pattern are set in the M&V protocol before Gate 2 (C3 open item 1).

## 7. Controller order and enablement

The order in which controllers run matters, because several can act on the same battery or charger. The exact priority behaviour is defined by the pinned OpenEMS release and must be **tested**, not assumed [verify against release].

### 7.1 Enablement order (from C3)

Each controller is enabled one at a time, only after its scripted test passes (C3 Sections 8.8, 9 to 11).

| Pilot | Order |
| --- | --- |
| A | 1) monitoring only; 2) self-consumption and feed-in limit; 3) ToU shifting; 4) peak shaving |
| B | 1) monitoring and metering; 2) self-consumption and SoC management; 3) generator offset; 4) evening peak dispatch |
| C | 1) monitoring only; 2) site-limit enforcement with a high limit; 3) policy-based balancing; 4) transformer protection thresholds; 5) battery support if fitted |

### 7.2 Run order and conflict handling

| Rule | Detail |
| --- | --- |
| Single list | The scheduler order for each site is written in the site configuration and reviewed by the independent reviewer |
| Limits first | Controllers that enforce limits (export limit, site limit, critical-load protection) run so that they take precedence over optimisation controllers [verify behaviour in lab] |
| Conflict test | A scripted test runs each pair of controllers that act on the same asset and records which one wins. Result stored in the test record (C5) |
| No hidden controllers | A controller that is installed but unused is disabled and removed from the scheduler |
| Documentation | Scheduler order and the conflict test result are included in the handover pack |

## 8. Secrets, accounts and network details

| Item | Rule |
| --- | --- |
| Secrets | Never committed. Held in the secrets manager or sealed credential record [tool to be chosen, B7 open item 7]. Unique per site, never reused between sites |
| Injection | Secrets are injected on the Edge at commissioning by an authorised person, then the injection step is logged (not the secret) |
| Accounts | Named accounts with roles (viewer, operator, engineer, administrator, auditor). No shared logins. Contractor accounts time-limited (B7 6.1) |
| Default credentials | Removed or neutralised before commissioning. Verified (B7 Appendix B item 2, T-COM-08) |
| Network details | IP plan, VLAN IDs, firewall rules and VPN details held in the private repository. The public repository contains only sanitised examples |
| Pre-Gate 3 | Remote access, tunnels, cloud sync and vendor remote tools are **disabled** in configuration and verified by port scan (B7 6.2, C3 8.5) |
| Post-Gate 3 | Outbound-only, encrypted, multi-factor remote path enabled by a logged change. Baseline and control schedule are not altered by this change (C3 8.10) |
| Secret scanning | Automated secret scanning on every commit. A leaked secret is an S2 incident and the secret is rotated (B7 6.1, 10.2) |

## 9. Integrity, verification and drift detection

| Control | Requirement |
| --- | --- |
| Manifest | Each site has a `manifest.yaml` listing layer versions and SHA-256 (or equivalent) hashes (Appendix A) |
| Start-up check | On start and on a schedule, the Edge computes the hash of its configuration and compares it with the manifest. A mismatch raises an alarm (B7 6.3) |
| Separate hash for L5 | The safety set has its own hash. Any mismatch is a higher-severity alarm |
| Drift report | Monthly, the Cybersecurity Officer or delegate runs the verify tool and records the result for the dashboard. Unexplained drift is an S3 incident, or S2 if L5 changed |
| Signed releases | Tags and bundles are signed. The verify tool checks signatures before applying a configuration |
| Evidence trail | Every change links a change request, a commit, a test record, an approver and a D5 log entry |
| Panel visibility | The Research Panel receives the change log monthly and can inspect the manifest history |
| Time | Configuration hashes and mode records are time-stamped from the synchronised time source |

## 10. Change management

### 10.1 Change classes

| Class | Examples | Approval | Test before deploy | Notify |
| --- | --- | --- | --- | --- |
| C0 Emergency safety | Isolating a device, lowering a limit after an alarm | Site Lead on site (may act first), Technical Lead informed same day | After the fact, with review within [2] working days | PMO, Cybersecurity Officer |
| C1 Safety layer (L5) | Any safe state, plausibility or grid limit change | Technical Lead and Cybersecurity Officer. Kenya Power where grid-related. Two-person on-site approval [pending decision] | Lab or spare Edge, then on-site acceptance subset | Kenya Power, Panel, PMO |
| C2 Behaviour (L4) | Setpoints, tariff schedule, policy | Technical Lead. Panel approval if a KPI-relevant parameter changes during M1 or M2 | Lab or spare Edge | Panel, PMO |
| C3 Platform | OpenEMS release, image, driver, firmware | TWG decision with Cybersecurity Officer. Delta tests per B6 10.3 | Full delta test set | Panel, Kenya Power ICT where relevant, PMO |
| C4 Non-behavioural | Documentation, labels, comments | Maintainer with independent reviewer | Syntax and schema check | None |

Schedule, budget, scope and KPI tolerances follow Charter Section 20. After Gate 1 no KPI or baseline change is allowed without SteerCo approval and Panel advice.

### 10.2 Standard change procedure

1. **Raise.** A change request states the reason, affected layers, site, expected effect on KPIs and baseline, and rollback plan.
2. **Assess.** Technical Lead and, where relevant, Cybersecurity Officer, Research Lead and Kenya Power assess risk.
3. **Branch and edit.** Work on `site/<ID>/change-<n>`. The verify tool and schema check run automatically.
4. **Review.** Independent reviewer approves. Class C1 and C3 need the additional approvers above.
5. **Test.** Run the relevant test subset on the lab or spare Edge (B6 10.3, C3 8.8). Record results.
6. **Schedule.** Choose a time that does not damage data or operations. Notify host or community where behaviour changes. Flag data as M4 if needed.
7. **Deploy.** Apply with the deployment tool, verify the hash, confirm safe states still work, and take a new backup.
8. **Record.** Merge to `main`, tag a new version, update the manifest, and log in D5.
9. **Rollback.** If any check fails, restore the previous tag and record the failed change with equal prominence.

### 10.3 After Gate 3

Every deployment goes through the logged change process, is tested off site first and has a rollback plan (B4 3.5, B7 6.4). Remote deployment is allowed only for classes C2 to C4 through the approved remote path. Class C1 changes follow Section 6.4. Remote sessions are time-bound and logged.

## 11. Backup, restore and rebuild

| Item | Requirement |
| --- | --- |
| What is backed up | Site configuration (L3 to L5), mode records, device settings list, manifest, local data buffer where feasible |
| When | After every approved change, and on a schedule [weekly] |
| Where | On the Edge, on a second local medium, and off site. Offline copy for the sealed set (B7 6.7) |
| Restore test | At commissioning and at Gate 4. Records stored with the baseline (C3 8.8, B7 6.7) |
| Rebuild | From the signed image plus the tagged configuration plus secret injection. Target time [x] hours (B7 6.7) |
| Spare Edge | Pre-configured spare at or near each site, or documented rebuild path. Pilot B spares kit includes a spare Edge |
| Data | The buffer protects data during outages. Backups of the configuration do not replace data backups. Data retention follows the data management plan (D2) |
| Rollback | The previous tagged baseline is always restorable. Rollback is tested at commissioning |

## 12. Validation: proving the deployed system matches the baseline

| # | Check | Pass criterion | When |
| --- | --- | --- | --- |
| V1 | Schema and syntax validation | All configuration files pass the schema | Every commit |
| V2 | Manifest match | Hashes of all layers match the manifest | Install, Gate 3, monthly |
| V3 | Component inventory | Components running equal components in the manifest, no extras | Install, monthly |
| V4 | Driver and release match | Running release and drivers match B6 tested set | Install, after any change |
| V5 | Firmware match | Device firmware equals `firmware.yaml` | Install, after any change |
| V6 | Safe state test | Each device reaches its safe state on link loss and device loss | Commissioning (acceptance tests A7, B6, C7), after C1 and C3 changes |
| V7 | Limit enforcement | Export, site and power limits hold under test (A5, C3) | Commissioning, after relevant change |
| V8 | Conflict test | Controller conflicts resolve as documented | Commissioning, after scheduler change |
| V9 | Offline operation | Control continues for [24] hours (A, C) or [72] hours (B) with no loss of function | Commissioning, Gate 4 |
| V10 | Restore test | Restored configuration matches the manifest and works | Commissioning, Gate 4 |
| V11 | Secrets scan | No secrets in repositories or logs | Every commit, pre-release |
| V12 | Mode record check | Mode in operation matches the latest signed mode record | Monthly |

## 13. Software bill of materials and licence compliance

| Item | Requirement |
| --- | --- |
| SBOM | Generated for the production Edge image and each custom driver. Stored with the baseline and updated on any C3 change (B7 6.9) |
| Licence register | Technical Lead maintains the register. Entries cover OpenEMS Edge and Backend (Eclipse Public License 2.0), UI (AGPL 3.0), and programme code (Apache 2.0) |
| AGPL duties | Any modified UI served over a network triggers source-sharing duties. Modifications are tracked and published where required |
| Counsel review | Counsel confirms the licence mix is acceptable for the planned release (B5 open question 10) |
| Upstream | Custom drivers and fixes are offered upstream after TWG review, with licences preserved (Charter Section 21, B6 8.1) |
| Vendor software | Any vendor software must allow pilot use and publication of evaluation results (C1 Section 11.2) |

## 14. Publication and privacy

The open-by-default principle applies to configuration, with a security and privacy review before release (Charter Section 21, B7 6.9).

| Publish | Withhold |
| --- | --- |
| Templates, schema, tooling, mode schedule structure | Credentials, keys, tokens |
| Sanitised per-site configuration (parameters, controller settings, component list) | Network diagrams of live sites, IP plans, firewall rules, VPN details |
| Custom drivers and mappings | Host-confidential parameters (production schedules, tariff contract terms) until the host agrees |
| Change log summaries, including failed changes | Any unpatched vulnerability details until fixed |
| Device and firmware list (without serial numbers if the Officer advises) | Personal data of any kind |

A pre-release scan by the Cybersecurity Officer checks every public release (B7 C6).

## 15. Roles

| Role | Responsibility |
| --- | --- |
| Technical Lead | Approves the baseline structure and L4 changes. Owns the licence register. Chairs TWG decisions on C3 changes |
| Software engineer | Owns this document and the repositories. Builds images, writes tools and tests, maintains drivers, executes deployments |
| Site engineers | Record as-installed state, apply approved changes on site, run on-site verification |
| Site Leads | Authorise on-site L5 changes with the Technical Lead. First response for C0 emergency actions |
| Cybersecurity and Data Protection Officer | Owns secrets handling, integrity checks, hardening baseline and monthly drift review. Approves C1 and C3 security aspects |
| Research Lead and Panel | Define the mode schedule. Approve entry to M1 and M2 and KPI-relevant changes. Receive the change log |
| Kenya Power grid engineer (TWG) | Reviews and approves grid-related limits (export, site, transformer) |
| Independent reviewer | A person independent of the author who approves merges to `main` (Charter Section 23) |
| PMO | Tracks change requests, risks, escalations and dashboard items |
| Host representative | Informed of behaviour changes. Cannot alter Edge configuration (Site Agreement 6.1) |
| Local operators | Follow D3 for routine checks, restore and fault procedures. Do not edit configuration |

## 16. Schedule and gate evidence

| Activity | Months | Output | Gate |
| --- | --- | --- | --- |
| Approve method, repository structure and schema | 3 to 4 | This document v0.1 approved by TWG | Gate 1 input |
| Pin the test release and lab configuration | 4 | `VERSIONS.md`, lab config tag | |
| Template configurations per pilot, validated on the lab Edge | 4 to 6 | `templates/` tested | Gate 1 evidence |
| Site selection, create site folders | 6 | `sites/<ID>/` created | Gate 1 |
| Site configuration drafted from survey data and B6 results | 6 to 8 | Draft site baselines | |
| Production release and image pinned, SBOM, hashes, mode schedule agreed | 8 | **Frozen baselines `v1.0.0`** | **Gate 2** |
| Load and verify at site (V1 to V12), mode records | 11 to 12 | Verified manifests, C5 reports | |
| Gate 3 verification that live Edge matches `v1.0.0` | 12 | Verification record | **Gate 3** |
| Change log and drift reports | 13 to 24 | Monthly drift report | Gate 4 |
| Final register, licence status, publication package | 22 to 24 | Open-source release package (E5), replication guide input (E3) | Gate 5 |

| Gate | Evidence from this document |
| --- | --- |
| Gate 1 | Approved method and schema. Templates validated on the lab Edge. Pinned test release. Mode schedule structure agreed with the Research Panel |
| Gate 2 | Production release, image and driver set pinned. Frozen baselines `v1.0.0` per site with manifests and hashes. SBOM. L5 sets approved. Mode schedule signed off. Spare and rebuild plan |
| Gate 3 | Live Edge hashes match manifest at each site. Safe state, limit, conflict, offline and restore tests passed. Remote access verified disabled, then enabled by logged change |
| Gate 4 | Change log and drift summary. Restore test repeated. Review of any accepted deviations |
| Gate 5 | Final baselines, licence and upstream status, published sanitised configuration, custodian named for the repository |

## 17. Risks

| # | Risk | L | I | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| CB1 | Configuration drifts from the baseline through manual changes, distorting results | M | H | Hash checks, monthly drift report, no manual edits, named accounts | Software engineer |
| CB2 | Production release differs from the tested release, so lab results do not apply | M | H | Pin test release early, delta test rules, TWG decision recorded | Technical Lead |
| CB3 | Controller conflicts cause unexpected battery or charger behaviour | M | H | Scripted conflict test, limits-first order, staged enablement | Technical Lead |
| CB4 | Secrets leak through the public repository | L | H | Secret scanning, private repository, pre-release scan, rotation | Cybersecurity Officer |
| CB5 | Safety limits changed remotely or without approval | L | H | L5 not remotely editable, separate hash, two-person route | Cybersecurity Officer |
| CB6 | Baseline integrity challenged because mode switches are not documented | M | H | Signed mode records, Panel approval, change log visible to Panel | Research Lead |
| CB7 | Local team cannot maintain the repository and tooling after the pilot | M | M | Simple tooling, documentation, training, named custodian at closure | Technical Lead |
| CB8 | Edge failure at a remote site with no usable backup | M | M | Backups off site and local, spare Edge, tested restore | Site Lead (B) |
| CB9 | Vendor firmware update changes device behaviour without notice | M | H | Firmware hold, vendor notification clause, firmware match check | Technical Lead |
| CB10 | Licence non-compliance (AGPL, EPL, Apache) in published configuration or drivers | L | M | Licence register, counsel review, upstream process | Technical Lead |
| CB11 | Poor connectivity prevents timely remote deployment or verification at Pilot B | H | L | Local verify tool, on-site routine, buffered logs | Site Lead (B) |

These risks are to be merged into the live Risk Register (README A6). An unexplained change to the L5 set is a Charter escalation event and an S2 incident (B7 10.2).

## 18. Open items and decisions

| # | Item | Needed for | Owner |
| --- | --- | --- | --- |
| 1 | Choose and pin the OpenEMS release for the test campaign and for production | Start of testing, Gate 2 | Technical Lead |
| 2 | Verify factory identifiers, file locations and scheduler behaviour against the pinned release | Component tables, conflict tests | Software engineer |
| 3 | Decide whether safe-state and limit changes after Gate 3 need two-person on-site approval | Gate 2 | TWG |
| 4 | Choose the secrets management and signing tools suitable for low-connectivity sites | Gate 2 | Technical Lead, Cybersecurity Officer |
| 5 | Fix the baseline length and with and without control pattern in the M&V protocol | Gate 2 | Research Lead |
| 6 | Set the plausibility limits, safe states and site limits per site | Gate 2 | Technical Lead |
| 7 | Decide the Backend hosting option and whether Backend configuration is in this baseline | Gate 1 | Technical Lead, Programme Director |
| 8 | Agree what is published for each site and what is withheld, with hosts | Gate 3 | Cybersecurity Officer, Research Lead |
| 9 | Decide hash algorithm, signing method and verification tool | Gate 1 | Software engineer |
| 10 | Confirm drift check frequency and alarm routing | Gate 2 | Cybersecurity Officer |
| 11 | Name the custodian of the repositories after closure | Gate 5 | Programme Sponsor |
| 12 | Confirm how often backups run at low-connectivity sites | Gate 2 | Technical Lead |

## 19. Immediate next steps

1. TWG to review this method, including the Kenya Power grid engineer on the limits route.
2. Software engineer to create the repositories, schema and CODEOWNERS, and enable branch protection and secret scanning.
3. Technical Lead to pin the test release and record it in `VERSIONS.md` at the start of Month 4.
4. Build and validate the common and per-pilot templates on the lab Edge.
5. Agree the mode schedule structure and baseline rules with the Research and Evaluation Panel.
6. Cybersecurity Officer to approve the secrets, signing and drift-check approach.
7. Draft the verify, hash, diff, backup and restore tools and test them on the lab Edge.
8. Add the risks CB1 to CB11 to the live Risk Register and the open items to the PMO log.
9. After Gate 1, create site folders and populate from survey and compatibility data.

---

# Appendix A: Site manifest template (`manifest.yaml`)

```yaml
site:
  id: "[SSR-A1]"
  pilot: "[A | B | C]"
  baseline_version: "[SSR-A1-v1.0.0]"
  frozen_at_gate: "[Gate 2, date]"
  approved_by: ["[Technical Lead]", "[Cybersecurity Officer]", "[independent reviewer]"]

platform:
  openems_release: "[version]"
  openems_commit: "[id]"
  edge_image: "[name and version]"
  edge_image_sha256: "[hash]"
  sbom_ref: "[document ID]"

configuration:
  components_sha256: "[hash]"        # L3
  controllers_sha256: "[hash]"       # L4
  safety_set_sha256: "[hash]"        # L5, separate
  scheduler_order: ["[ctrl IDs in run order]"]

devices:                              # L6, matches B6 register
  - register_id: "[PVI-A01]"
    component_id: "[meterPv0 / ess0 ...]"
    make_model: "[ ]"
    firmware: "[ ]"
    driver_id: "[DRV-01]"
    b6_status: "[PASS | COND]"
    b6_level: "[L3 | L4]"
    warranty_ref: "[ ]"

modes:                                # L7
  - mode: "[M1 baseline]"
    start: "[date, time]"
    config_tag: "[tag]"
    approved_by: "[Research Panel minute ref]"
  - mode: "[M2 controlled]"
    start: "[date, time]"
    config_tag: "[tag]"
    approved_by: "[Research Panel minute ref]"

remote_access:
  status: "[disabled | enabled after Gate 3, change ref]"

tests:
  acceptance_report: "[C5 reference]"
  restore_test: "[record ref, date]"
  conflict_test: "[record ref, date]"
```

# Appendix B: Change request and record template

| Field | Entry |
| --- | --- |
| Change ID | `CR-[site]-[number]` |
| Date raised, requester | [ ] |
| Site and baseline version affected | [ ] |
| Class (C0 to C4) | [ ] |
| Layers affected (L1 to L7) | [ ] |
| Reason and expected effect | [ ] |
| Effect on KPIs or baseline (Yes / No, explain) | [ ] |
| Rollback plan | [ ] |
| Test plan and results (B6 test IDs, C5 reference) | [ ] |
| Approvers (names, roles, date) | [ ] |
| Kenya Power or Panel notified or approved | [ ] |
| Deployment date and method (on site or remote) | [ ] |
| Hash before and after | [ ] |
| Outcome (Success / Rolled back) and notes | [ ] |
| D5 log reference | [ ] |

# Appendix C: Configuration review checklist (per release or change)

| # | Check | Done |
| --- | --- | --- |
| 1 | Only needed components are enabled. No unused components or services | [ ] |
| 2 | Component IDs follow the convention (Section 5.3) | [ ] |
| 3 | Scheduler order reviewed. Limit controllers take precedence. Conflict test passed | [ ] |
| 4 | Safe states and plausibility limits within hardware limits and match Schedule 3 | [ ] |
| 5 | Export and site limits match Kenya Power and EPRA approvals | [ ] |
| 6 | Tariff schedule matches current tariff documents (Pilot A) | [ ] |
| 7 | Polling intervals, timeouts and retries tested in the soak test | [ ] |
| 8 | Default credentials removed. Named accounts only. No secrets in files | [ ] |
| 9 | Remote access disabled (pre-Gate 3) or matches approved design (post-Gate 3) | [ ] |
| 10 | Logging, time sync and buffer settings correct | [ ] |
| 11 | Device firmware list matches B6 | [ ] |
| 12 | Mode record matches the M&V schedule | [ ] |
| 13 | SBOM and licence register updated | [ ] |
| 14 | Schema validation, secret scan and hash verification passed | [ ] |
| 15 | Backup taken and restore tested | [ ] |
| 16 | Independent reviewer approval recorded | [ ] |

# Appendix D: Traceability

| Source | Used for |
| --- | --- |
| Programme Charter (Sections 7, 16, 19, 20, 21, 23, risk 8) | KPIs and baseline, gates, logged change process, change control, open-source governance, independent review, no re-baselining |
| Feasibility Study (Sections 4.3 to 4.6, 9) | Interoperability approach, cybersecurity and grid interface limits, risks |
| Technical Specification per Site (Sections 3.2 to 3.5, 4, 5 to 7, 9) | Design rules, safe states, controller functions and parameters, acceptance tests |
| Interoperability and Device Compatibility Register (Sections 5, 8, 10, 12) | Driver routes, driver register, version pinning, delta testing, gate evidence |
| Cybersecurity Plan (Sections 6.1 to 6.9, 10, 14, Appendix B) | Accounts and secrets, setpoint integrity, hardening, logging, backup and restore, SBOM, incident severity |
| Regulatory Compliance Assessment (Sections 5.1, 5.5, 5.11) | Export limit source, Kenya Power control authority, licence obligations |
| Installation and Commissioning Plan (Sections 8, 9 to 11, 12, 13, 14) | Load and verify steps, enablement order, hold points, handover pack, schedule |
| Procurement Plan (Sections 7, 11.2) | Vendor firmware policy, documentation, licensing terms |
| MoU and Site Agreement templates (Site Agreement Sections 6, 9, 10, Schedules 3 and 6) | Control and operating plan, data roles, cybersecurity duties |
| Stakeholder Engagement Plan (Section 7.2) | Research-pilot messaging and honest reporting of changes |

On completion of the compatibility test campaign, the Gate 1 site selection and the Gate 2 design review, each bracketed value is updated, the baselines are frozen as `v1.0.0` per site, and this document is re-issued as version 1.0 for Gate 2.

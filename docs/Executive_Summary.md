# Executive Summary

## 1. Purpose

The Open-Source EMS Pilot Programme Kenya will test whether an open-source energy management system (EMS), OpenEMS, can be deployed in Kenya to stabilise a high-renewable grid, reduce losses, lower energy costs and safely integrate electric vehicle (EV) charging. It will also establish whether doing so is technically, economically and institutionally viable.

## 2. The Challenge

Kenya has one of the cleanest power systems in the world, with over 80% of generation in FY2024/25 from renewables, led by geothermal (39.5%) and hydro (24.2%), with wind (13.2%) and utility solar (3.3%). This success brings new pressures on the grid:

- **Variability.** Wind and solar can reach about 34% of the instantaneous generation mix, increasing swings in net demand.
- **Growing demand.** Peak load reached 2,316 MW in February 2025, up 6.4% year on year, and EV tariff consumption grew 300% to 5.04 GWh.
- **High losses.** System losses averaged 23.4% in FY2024/25 against a regulatory benchmark of 17.5%, so roughly a quarter of generated electricity earns no revenue.
- **Under-used tariffs.** 180.3 GWh was consumed under Time-of-Use (ToU) pricing, saving about KSh 1.44 bn, yet most customers cannot automatically shift load or storage to cheaper periods.
- **Limited rooftop solar value.** The 2024 Net-Metering Regulations credit exports at 50% of each kWh, which rewards self-consumption and storage but offers no easy way to optimise them.
- **Transformer overload risk.** Unmanaged clusters of fast chargers can cause voltage drops and outages at peak times.

Proprietary energy management systems can address these issues but carry licence fees, vendor lock-in and limited local support, which limits adoption at scale.

## 3. The Opportunity: OpenEMS

OpenEMS is a modular, device-agnostic, open-source platform with three layers: an on-site Edge controller, a web user interface and an optional cloud Backend. It connects to inverters, meters, batteries and EV chargers through standard protocols (Modbus, MQTT, HTTP and OCPP) and includes controllers for:

- Peak shaving and load levelling
- Battery state-of-charge management
- Time-of-Use tariff optimisation
- Surplus feed-in and self-consumption under net-metering
- EV charging cluster load balancing

The Edge and Backend are released under the Eclipse Public License 2.0 and the user interface under AGPL 3.0. There are no licence fees and no vendor lock-in, and the Edge can continue local control during internet outages.

## 4. The Research Gap

Public documentation of OpenEMS deployments in Africa is very limited, and no Kenyan study quantifies the effect of EMS-controlled storage or smart EV charging on peak load, losses or bills. International evidence points to energy cost savings of roughly 15–30% for controlled customers, but **these figures have not been validated in Kenya.** Open questions remain on regulatory fit, cybersecurity, interoperability with locally available hardware and local technical capacity.

## 5. Objectives

1. Assess the suitability of OpenEMS against Kenya's grid, tariff and regulatory context.
2. Build a techno-economic framework comparing three scenarios: rural microgrid, commercial and industrial (C&I) facility, and EV charging depot.
3. Identify key risks and mitigation measures.
4. Design and deliver a 24-month, multi-site pilot with defined KPIs.

## 6. Proposed Pilot

The pilot will run for 24 months: the first year for design, procurement, installation and commissioning, and the second for operation, monitoring and data analysis. Three sites are proposed:

| Pilot                            | Setting                                                | Indicative configuration                           | What it tests                                  |
| -------------------------------- | ------------------------------------------------------ | -------------------------------------------------- | ---------------------------------------------- |
| A: Industrial park or energy hub | Factory, data centre or university campus              | Existing or new PV with about 250 kWh battery      | Peak shaving, ToU shifting, net-metering       |
| B: Rural microgrid               | Village or estate on long lines with diesel generation | 50–100 kW PV with about 200 kWh battery           | Loss reduction, reliability, self-consumption  |
| C: EV charging site              | Public station or fleet depot                          | About 10–20 fast chargers, optional small battery | Transformer protection and charging management |

Each site will use an OpenEMS Edge device, smart metering at the grid connection and additional voltage and transformer-loading measurement where needed. Data will be logged continuously and analysed monthly.

## 7. Key Performance Indicators

- Peak grid import reduction (kW and %)
- Renewable self-consumption ratio
- Bill savings (KSh)
- System uptime and availability
- Transformer loading and, for EV sites, the share of time chargers can operate at full capacity

## 8. Budget

The indicative budget for the full pilot is **KSh 50–100 million (about USD 400–800k)**, covering hardware, integration, installation, training and evaluation. Individual sites are estimated at USD 50k–150k depending on scale. OpenEMS itself carries no licence cost. All figures are indicative, in 2026 prices with inflation assumed at about 5% per year, and require validation through a detailed feasibility study.

## 9. Principal Risks and Mitigation

| Risk                                                                | Mitigation                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Regulatory change (net-metering credit, BESS and charger licensing) | Involve the Ministry of Energy and EPRA from the start; test sensitivity to lower export credits |
| Cybersecurity of remotely connected assets                          | Independent security audit, authentication and encryption, clear data-handling protocols         |
| Limited local OpenEMS expertise                                     | Build a local implementation team; train operators; partner with universities                    |
| Interoperability with local hardware                                | Compatibility testing before procurement; budget for custom drivers where needed                 |
| Poor connectivity in rural areas                                    | Rely on Edge local control; cache data and sync when connected                                   |
| Cost overruns or tariff changes                                     | Contingency of 10–20%; sensitivity analysis on battery cost, tariff spreads and discount rate   |

## 10. Stakeholders

The programme will be delivered with the Ministry of Energy (policy support), EPRA (tariffs and standards), Kenya Power (grid interface and data), local utilities and cooperatives (operations), technology partners (batteries, solar and telecoms) and university research partners such as Kenyatta University's Energy Institute. Communities will be engaged early to secure social acceptance.

## 11. Expected Outcomes

- The first documented, locally validated evidence of OpenEMS performance in a Kenyan grid.
- Measured results on peak reduction, losses, bill savings and EV charging management.
- A techno-economic model and risk register for use by regulators, utilities and developers.
- A trained local team and published findings to support wider adoption.

## 12. Next Steps

1. Secure regulatory clarity, including confirmation of net-metering terms.
2. Complete a detailed feasibility study and stakeholder consultation.
3. Establish a local OpenEMS implementation team.
4. Define precise performance targets for each site.
5. Launch the pilot in 2027 and publish results openly.

*Note: Cost figures are indicative and the 15–30% savings range is drawn from international studies. Both will be tested and validated through this programme.*

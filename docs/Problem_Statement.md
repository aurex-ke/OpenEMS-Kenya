# Problem Statement: Open-Source EMS Pilot Programme Kenya

## 1. Background

Kenya has one of the cleanest power systems in the world. Over 80% of generation in FY2024/25 came from renewables, led by geothermal (39.5%) and hydro (24.2%), with wind (13.2%) and utility solar (3.3%) adding to the mix. Demand is rising quickly: peak load reached 2,316 MW in February 2025, up 6.4% year on year, and electric-vehicle tariff consumption grew 300% to 5.04 GWh.

This growth is happening on a distribution network that is under strain. System losses averaged 23.4% in FY2024/25, well above the 17.5% regulatory benchmark, so roughly a quarter of generated electricity never earns revenue. At the same time, the share of variable renewable energy (VRE) can reach about 34% of the instantaneous mix, increasing swings in net demand.

## 2. Problem Statement

Kenya's power sector is moving toward a high share of variable renewables, growing peak demand and clustered EV charging, but the tools needed to manage these changes at the local level are largely absent. Most consumers, businesses and distribution assets have no automated way to coordinate batteries, solar PV, loads and EV chargers in real time. As a result:

- **Grid stability is at risk.** Fast fluctuations in wind and solar output are not buffered by controlled storage at the point of use.
- **Losses remain high.** Power is still delivered over long, lossy lines instead of being generated, stored and consumed locally.
- **Tariffs are under-exploited.** Time-of-Use (ToU) pricing exists (180.3 GWh consumed under ToU, saving about KSh 1.44 bn), yet most customers cannot automatically shift load or storage dispatch to cheaper periods.
- **Rooftop solar is less attractive.** The 2024 Net-Metering Regulations credit exports at only 50% of each kWh, which rewards self-consumption and storage but offers no easy way to optimise it.
- **EV charging can overload local transformers.** Co-located fast chargers, if unmanaged, can cause voltage drops and outages at peak times.

Proprietary energy management systems can address these issues, but they carry licence fees, vendor lock-in and limited local support, which makes them hard to adopt at scale in Kenya. OpenEMS, a fully open-source, device-agnostic platform with controllers for peak shaving, state-of-charge management, ToU optimisation and EV load balancing, is a promising alternative. However, there is currently no documented evidence of whether, how well and at what cost it works under Kenyan grid, regulatory, climatic and skills conditions.

## 3. Research Gap

- Public documentation of OpenEMS deployments in Africa is very limited.
- No Kenyan study quantifies the effect of EMS-controlled storage or smart EV charging on peak load, losses or bills.
- Benefits cited in the report summary (15–30% cost savings) come from international studies and have not been validated locally.
- Open questions remain on regulatory fit, cybersecurity, interoperability with locally available hardware and the availability of local technical capacity.

## 4. Central Research Question

*Can an open-source energy management system such as OpenEMS be deployed in Kenya to stabilise a high-renewable grid, reduce losses, lower energy costs and safely integrate EV charging, and is it technically, economically and institutionally viable to do so?*

### Supporting questions

1. How effectively can battery dispatch under OpenEMS smooth VRE variability and reduce peak demand?
2. How much can locally controlled solar-plus-storage microgrids reduce technical and commercial losses?
3. What bill savings and payback are achievable under ToU tariffs and the 50% net-metering credit?
4. Can OpenEMS EV cluster controllers prevent transformer overload without unacceptable charging delays?
5. What regulatory, cybersecurity, maintenance and capacity risks must be managed?

## 5. Objectives

- Assess the suitability of OpenEMS against Kenya's grid, tariff and regulatory context.
- Build a techno-economic framework to compare three scenarios: rural microgrid, commercial and industrial facility, and EV charging depot.
- Identify the key risks and mitigation measures.
- Design a 24-month, multi-site pilot with defined KPIs (peak import reduction, self-consumption ratio, bill savings, system uptime, transformer loading) and an indicative budget of KSh 50–100 million.

## 6. Scope and Limitations

The study focuses on grid-connected and mini-grid applications at the distribution and customer level in Kenya, using OpenEMS Edge as the control platform. It does not cover transmission-level planning or utility-scale generation. Cost figures are indicative (2026 prices) and require validation through a detailed feasibility study.

## 7. Significance

A validated, low-cost, open-source EMS could help Kenya protect the reliability of its renewable-dominated grid, cut avoidable losses, improve the economics of solar and storage, and prepare distribution networks for rapid EV uptake. A documented local pilot would also provide the evidence that the Ministry of Energy, EPRA, Kenya Power, universities and private developers need to support wider adoption.

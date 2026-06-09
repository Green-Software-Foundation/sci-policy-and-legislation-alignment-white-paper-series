# Bridging the Sustainability Gap: A Standardised Interoperability Layer for Real-Time Data Centre Sustainability Optimisation

**Green Software Foundation — Hardware Standards Working Group**
*White Paper | June 2026*

*greensoftware.foundation*

---

## Abstract

This white paper presents the case for a new, open, vendor-neutral interoperability specification for real-time sustainability optimisation in data centres, developed under the Green Software Foundation (GSF) Hardware Standards Working Group. It defines the problem the specification addresses, examines the regulatory landscape that makes the work urgent, describes the proposed specification in detail, and maps the value it delivers across the data centre ecosystem.

The specification will establish a standardised mechanism through which data centres can receive live grid signals, understand the renewable and non-renewable composition of available power, and dynamically adjust workload consumption in response. It is distinct from — but builds upon — the existing GSF Workload Dynamic Power and Cooling (WDPC) specification, which will serve as a normative reference.

---

## Executive Summary

The data centre industry faces a fundamental and largely unaddressed contradiction: a facility can be highly energy-efficient by conventional measures and yet remain environmentally unsustainable. Power Usage Effectiveness (PUE) — the dominant metric for data centre energy performance — tells operators how efficiently they use the power they draw. It reveals nothing about what that power is, where it originates, or how intelligently their consumption responds to the state of the grid that supplies it.

The proposed specification addresses this gap directly. It will define a standardised mechanism for data centres to receive real-time grid signals, understand the renewable and non-renewable composition of available power, and dynamically adjust workload consumption in response — enabling operators to make intelligent, real-time trade-offs between performance and sustainability.

> **Core proposition:** Sustainability requires knowing not just how much power you consume, but what power you consume — and being able to act on that knowledge in real time.

The regulatory environment makes this work urgent. The EU's Energy Efficiency Directive (EED), now in mandatory annual reporting phase for all data centres above 500 kW, the Corporate Sustainability Reporting Directive (CSRD), and a forthcoming EU Data Centre Energy Efficiency Package collectively require precisely the kind of real-time, source-aware consumption data that this specification is designed to produce. Similar regulatory pressures are emerging in the United States and across the Asia-Pacific region, where projected power demand growth of 165% by 2030 is driving urgent policy responses.

The specification will be developed openly within the GSF, as a standalone standard with WDPC as a normative reference. It is not a product, a monitoring tool, or a prescriptive operational policy. It is the common language that the data centre and the grid currently lack.

---

## 1. The Sustainability Gap: Efficiency Is Not Enough

For more than a decade, PUE has served as the primary lens through which the data centre industry has measured environmental responsibility. A PUE of 1.0 represents a theoretically perfect facility — every watt drawn from the grid goes directly to IT equipment. Hyperscale operators now routinely achieve PUE figures between 1.1 and 1.3, and this progress is real and meaningful.

However, PUE is a ratio of consumption, not a measure of sustainability. Consider two data centres: one draws 10 MW with a PUE of 1.15, powered entirely from a coal-fired grid at peak demand. The other draws 12 MW with a PUE of 1.25, drawing the majority of that power from co-located renewable generation and dynamically reducing its load during grid stress events. By PUE, the first facility is the better performer. By any reasonable measure of environmental impact, it is not.

> *PUE answers the question: "How efficiently am I using the power I draw?" The proposed specification addresses a more fundamental question: "Should I be drawing this power, from this source, at this moment — and what should I do differently?"*

The missing element is not better efficiency within the four walls of the data centre. It is a standardised, real-time connection between the data centre and the grid that supplies it — one that enables the facility to listen to signals about grid state, renewable availability, and carbon intensity, and to respond intelligently by adjusting workload distribution, timing, and volume accordingly.

This connection does not currently exist in any standardised form. Individual operators have developed proprietary approaches, and a small number of large technology companies have run pilots with specific utilities. There is, however, no open, interoperable standard — no common language that allows any data centre, built by any vendor, to communicate meaningfully with any grid operator. This is the gap the proposed specification is designed to close.

---

## 2. The Current State of Data Centre Power Management

### 2.1 How Data Centres Currently Manage Power

Contemporary data centre power management operates primarily at the facility level. Operators monitor total consumption, manage cooling loads, and optimise PUE through infrastructure controls. At the workload level, some operators implement basic demand-shaping — scheduling batch jobs during off-peak hours, for example — but these decisions are typically driven by cost, not by real-time grid signals.

The relationship between a data centre and its grid is, in most cases, a one-way feed: the grid supplies power and the data centre consumes it. The data centre does not receive structured information about grid state, carbon intensity, or renewable mix in any standardised format, and it does not transmit structured information about its own flexibility or consumption intentions. The two systems operate in effective isolation.

### 2.2 The Limitations of Existing Frameworks

The most widely used reference framework for hardware-level power management in this space is the Workload Dynamic Power and Cooling (WDPC) specification, developed within the GSF Hardware Standards Working Group. WDPC establishes open standards for dynamic signalling between software workloads, data centres, and grid operators, and defines data models at the facility, rack, node, and component levels.

The proposed specification builds on — but is explicitly distinct from — WDPC. Where WDPC defines the data model and signalling framework within the facility, the proposed specification addresses the interoperability layer between the facility and the external grid: how grid-side sustainability signals are received, interpreted, and translated into actionable consumption decisions. WDPC will serve as a normative reference; the new specification will stand alone as a distinct standard with clearly delineated scope boundaries.

### 2.3 The Sustainability vs. Performance Dimension

A central insight motivating this specification is that sustainability and performance exist on a spectrum, not as binary alternatives. At any given moment, an operator can choose to prioritise maximum workload performance — drawing whatever power is necessary to serve demand at full capacity — or to prioritise maximum sustainability, constraining consumption to renewable or low-carbon sources even at some cost to performance headroom.

In practice, neither extreme is always appropriate. The specification envisions a configurable, dynamic scale between these two poles — one that can be adjusted in real time, on a time-of-day basis, in response to grid events, or according to pre-defined policy rules. A data centre might run at full performance during business hours, shift toward sustainability optimisation during off-peak periods, and automatically reduce its non-renewable draw during grid stress events that would otherwise trigger fossil-fuel backup generation.

> **The goal is not to compel data centres to sacrifice performance for sustainability. It is to give operators the tools to optimise both — and to demonstrate, with verifiable data, that they have done so.**

---

## 3. The Regulatory Imperative

The proposed specification does not exist in a regulatory vacuum. A convergence of mandatory legislative frameworks — concentrated in the EU but spreading globally — is creating direct and urgent demand for precisely the kind of real-time, source-aware consumption data that this specification is designed to produce. Organisations that cannot demonstrate dynamic, verifiable sustainability management face increasing compliance risk, reporting liability, and competitive disadvantage.

### 3.1 European Union: Mandatory and Tightening

#### Energy Efficiency Directive — Directive (EU) 2023/1791

The EED is the most directly applicable legislation currently in force. Since September 2024, all data centres with an IT power demand of **500 kW or more** are required to submit annual sustainability reports to a European database. Mandatory reporting fields include:

- Total energy consumption and PUE
- Renewable energy usage and source composition
- Waste heat utilisation
- Water consumption
- Server and storage capacity and utilisation

Annual reports are due by 15 May each year. Critically, under Article 12(5) of the Directive, the European Commission is required to assess the submitted data and, where appropriate, introduce **minimum performance standards**. The EED is therefore a precursor to mandatory operational requirements, not merely a reporting framework. Operators who cannot track and manage their real-time grid draw composition will face structural difficulty meeting the performance standards expected within the next regulatory cycle.

Operators cannot credibly report on renewable energy use without the ability to dynamically track and manage their grid draw composition in real time. The proposed specification provides the operational infrastructure that makes meaningful EED compliance possible — not retrospective.

**Regulatory reference:** Directive (EU) 2023/1791; Commission Delegated Regulation (EU) 2024/1364

---

#### Corporate Sustainability Reporting Directive — Directive (EU) 2022/2464

The CSRD, effective from 1 January 2024, requires large companies to publish detailed ESG disclosures aligned with the European Sustainability Reporting Standards (ESRS). The directive replaces the narrower Non-Financial Reporting Directive and dramatically expands scope — approximately **50,000 organisations** fall within its remit, including over 10,000 non-EU entities with significant European operations.

The phased rollout is as follows:

| Wave | Companies in Scope | Reporting From |
|------|--------------------|----------------|
| Wave 1 | Large listed companies (>500 employees) already under NFRD | FY2024 (reports in 2025) |
| Wave 2 | Large companies not previously under NFRD (>250 employees and/or >€40M turnover) | FY2025 (reports in 2026) |
| Wave 3 | Listed SMEs (opt-out until 2028) | FY2026 (reports in 2027) |
| Wave 4 | Non-EU companies with significant EU operations | By 2028 |

For data centre operators and their enterprise tenants, the CSRD requires credible disclosure of Scope 2 emissions from purchased electricity and, increasingly, of Scope 3 emissions attributable to IT infrastructure. Without the ability to track real-time power source composition, CSRD disclosures on infrastructure carbon intensity are estimates at best. The proposed specification provides the data infrastructure that makes verifiable, granular CSRD compliance achievable.

**Regulatory reference:** Directive (EU) 2022/2464; European Sustainability Reporting Standards (ESRS)

---

#### EU Data Centre Sustainability Rating Scheme — Delegated Regulation (EU) 2024/1364

Adopted in March 2024, this delegated regulation establishes the first phase of an EU-wide scheme to rate the sustainability of data centres. It defines the sustainability indicators, performance metrics, and measurement methodology that feed into the European database. The Commission is empowered to introduce a formal sustainability rating system once sufficient data has been collected — an assessment mandated for completion by May 2025.

A sustainability rating creates direct commercial and reputational incentives for operators to actively manage their sustainability profile, not merely report it passively. The proposed specification is the operational mechanism through which favourable ratings can be achieved and maintained.

---

#### European Green Deal, Fit for 55, and the Forthcoming Data Centre Package

The European Green Deal — targeting net-zero emissions by 2050 and a 55% reduction by 2030 — provides the overarching policy architecture within which the EED and CSRD sit. A dedicated **Data Centre Energy Efficiency Package** is expected alongside the EU Strategy Roadmap on Digitalisation and AI in the first half of 2026, signalling continued and accelerating regulatory attention. Operators implementing the kind of real-time grid-responsive management this specification enables will be measurably better positioned when that package arrives.

---

### 3.2 United States: Federal Recommendations and State-Level Action

#### DOE Powering AI and Data Center Infrastructure Recommendations (2024)

The US Department of Energy's 2024 recommendations explicitly identify three federal priorities that align directly with the proposed specification: improving efficiency in AI workloads; codifying **utility-operator flexibility contracts**; and accelerating clean generation and storage tailored for data centre load growth. The DOE's Lawrence Berkeley National Laboratory projected data centre electricity consumption rising from 176 TWh in 2023 to between 325 and 580 TWh by 2028 — a trajectory the federal government is actively seeking to manage through demand-side flexibility, not simply supply-side expansion. The proposed specification provides the interoperability standard that makes utility-operator flexibility contracts technically realisable at scale.

#### EPRI DCFlex Initiative

The Electric Power Research Institute's DCFlex project — involving more than 40 organisations including Google, Meta, Microsoft, Duke Energy, and the PJM Interconnection — is actively piloting demand-response, workload shifting, and UPS-as-grid-resource approaches. DCFlex demonstrates wide industry recognition that the problem is real and that solutions generate value. The proposed GSF specification would provide the open, vendor-neutral interoperability standard that commercial pilots such as DCFlex currently lack.

#### State-Level Renewable and Clean Energy Frameworks

As of mid-2024, 29 US states and the District of Columbia had adopted Renewable Portfolio Standards (RPS) or Clean Energy Standards (CES), with 16 states targeting at least 50% renewable retail electricity sales. Texas enacted Senate Bill 6 (SB6) in June 2025, introducing planning, interconnection, and emergency operations reforms for large data centre loads — reflecting a broader state-level shift from treating data centres as passive grid consumers to requiring them to operate as responsible grid participants.

### 3.3 Asia-Pacific: Urgency at Scale

The Asia-Pacific region confronts the most acute version of the data centre sustainability challenge. Power demand is projected to grow from approximately 320 TWh in 2024 to 780 TWh by 2030 — a **165% increase** — driven by rapid AI infrastructure buildout across Australia, Japan, Singapore, India, South Korea, and Southeast Asia.

Singapore lifted its earlier moratorium on new data centre construction with strict sustainability conditions applied as a prerequisite for approval. Japan has announced plans to co-locate data infrastructure with offshore wind and nuclear sites, embedding grid-proximity sustainability into national infrastructure planning. These precedents signal a clear regional direction of travel toward sustainability-conditional data centre development — one that a standardised interoperability specification can directly underpin.

### 3.4 The Compliance Landscape at a Glance

| Framework | Geography | Relevance to Specification |
|-----------|-----------|---------------------------|
| EED (EU) 2023/1791 + Reg 2024/1364 | EU (500 kW+ DCs) | Mandatory annual reporting on renewable use, PUE, and sustainability KPIs. Precursor to minimum performance standards. Real-time data infrastructure is required to comply credibly. |
| CSRD (EU) 2022/2464 | EU + global (~50,000 orgs) | Requires verifiable ESG disclosure including Scope 2 and Scope 3 infrastructure emissions. Source-level power tracking is essential for accurate compliance. |
| Delegated Regulation 2024/1364 | EU | Establishes EU sustainability rating scheme. Active sustainability management — not passive reporting — will determine outcomes. |
| DOE DC Infrastructure Recommendations (2024) | USA | Federal call for codified utility-operator flexibility contracts. The specification provides the open standard to make this technically interoperable at scale. |
| EPRI DCFlex | USA (industry) | Industry-led pilots demonstrating demand-response value. The specification provides the missing open-standard interoperability layer. |
| Singapore DC Sustainability Conditions | APAC | Sustainability-conditional approvals for new builds. Grid-responsive operation is becoming a market access requirement across the region. |

---

## 4. The Proposed Specification

### 4.1 Objective

The specification defines an open, vendor-neutral interoperability layer that enables any data centre — regardless of vendor, operator, or geography — to receive, interpret, and respond to real-time grid sustainability signals. It is not a product, a proprietary API, or a monitoring tool. It is a standard: a common language and framework that allows the data centre and the grid to communicate, and that empowers operators to act on that communication with intelligence and verifiability.

### 4.2 Core Technical Requirements

The specification addresses the interface between the data centre and the external power grid across five functional areas:

- **Grid signal ingestion:** The data centre receives real-time signals from grid operators regarding available capacity, renewable composition, carbon intensity, and demand constraints.
- **Power source awareness:** The data centre tracks the composition of the power it is drawing — renewable versus fossil — and maintains this as a live operational parameter.
- **Dynamic consumption control:** Operators configure a sustainability-versus-performance parameter and the system translates that parameter into workload-level consumption decisions in real time.
- **Peak demand avoidance:** The system supports logic to prevent drawing beyond grid capacity thresholds, avoiding demand spikes that trigger higher-emission backup generation or destabilise grid supply.
- **ESG data output:** The specification supports generation of real-time, source-level consumption data in the formats required for EED, CSRD, and equivalent compliance reporting.

### 4.3 The Sustainability–Performance Scale

A core architectural concept is a configurable, dynamic parameter representing the operator's chosen position on a spectrum between maximum performance and maximum sustainability. This is not a binary setting — it is a continuously adjustable scale that can be:

- Set manually by operators at any time
- Configured to follow time-of-day or calendar-driven profiles
- Triggered automatically by grid events — such as stress alerts or renewable generation peaks
- Governed by pre-defined policy rules, including minimum sustainability floors

> **Example:** A data centre might run at a performance-optimised setting during business hours, transition to sustainability optimisation during off-peak periods, and automatically reduce non-renewable consumption during grid events — all without manual intervention, driven entirely by the standardised signals the specification defines.

### 4.4 Scope Boundaries and Relationship to WDPC

The specification operates at the layer above the facility interior. WDPC defines the data models and signalling framework within the facility — at the level of racks, nodes, and components. The proposed specification defines the external interface: how grid-side signals enter the facility and how facility-side responses are structured and communicated outward. WDPC is used as a normative reference for internal data models; the two specifications are complementary but distinct.

| GSF Specification / Project | Relationship to Proposed Specification |
|-----------------------------|----------------------------------------|
| WDPC (Workload Dynamic Power & Cooling) | Normative reference for facility-side data models. The proposed specification extends the external interface beyond the facility boundary. |
| Software Carbon Intensity (SCI) | SCI measures software carbon footprint. The proposed specification provides real-time power source data that increases the accuracy of SCI calculations. |
| SCI for Open Telemetry | Open telemetry pipelines may carry the grid signal and sustainability data that the proposed specification generates. |
| Software Energy Efficiency | Software-level optimisation benefits directly from knowing the real-time carbon intensity of the power being consumed — a primary output of this specification. |

### 4.5 What the Specification Is Not

- It is not a proprietary data centre management system or vendor product
- It is not a replacement for PUE measurement or existing energy efficiency frameworks
- It is not a prescriptive operational policy — it defines the interface, not the decisions made through it
- It does not replicate the internal facility-level coverage of WDPC
- It is not a compliance tool in itself — it provides the data infrastructure that compliance tools require

---

## 5. Illustrative Use Cases

### 5.1 Time-of-Day Optimisation

A data centre operator configures a sustainability profile that shifts toward maximum renewable utilisation between midnight and 6:00 AM, when grid demand is low and a high proportion of renewable generation is dispatched. During this window, the system prioritises flexible workloads — batch analytics, model training, backup operations — to absorb renewable generation that would otherwise be curtailed. As the morning demand peak approaches, the system automatically transitions to a performance-priority profile, ensuring latency-sensitive workloads remain unaffected. The sustainability data generated throughout is captured in the format required for EED and CSRD reporting.

### 5.2 Grid Stress Event Response

During a peak demand period, the regional grid operator signals a demand constraint event. The data centre's interoperability layer receives the signal and applies a pre-configured demand reduction profile: non-critical workloads are queued, cooling is optimised, and power draw is reduced by a defined percentage for the duration of the event. The grid operator receives confirmation of the load reduction. The event is logged as a verified sustainability action in the facility's compliance reporting dataset.

### 5.3 Power Source Selection on a Mixed-Source Grid

A data centre is served by a grid that mixes renewable, nuclear, and gas-fired generation, with composition varying hour by hour. The operator has a corporate target of drawing at least 80% of power from zero-carbon sources on a rolling hourly basis. The interoperability layer monitors real-time grid composition against this threshold, dynamically adjusting workload intensity — drawing harder during high-renewable periods and throttling back when gas generation dominates. The system generates verified hourly renewable attribution data for Scope 2 disclosure.

### 5.4 On-Site Renewable Integration

A data centre with an on-site solar array wishes to maximise the proportion of workloads served by its own generation. The specification allows the operator to configure a preference for on-site renewable consumption, automatically scheduling flexible workloads to coincide with peak generation windows and reducing grid draw during those periods. The combination of on-site generation tracking and grid-signal awareness enables a holistic, real-time view of the facility's carbon profile.

---

## 6. Stakeholder Value

| Stakeholder | Value Delivered |
|-------------|----------------|
| **Data Centre Operators** | Real-time control over the sustainability-performance trade-off; verifiable compliance data for EED and CSRD reporting; improved sustainability ratings; reduced exposure to forthcoming minimum performance standards. |
| **Grid Operators** | Data centres become predictable, programmable demand participants. Demand-response capability supports grid stability during stress events and absorbs excess renewable generation. |
| **Regulators and Policymakers** | Open, standardised reporting infrastructure makes EED and CSRD enforcement tractable. A common data model enables consistent cross-border sustainability monitoring and application of forthcoming rating schemes. |
| **Cloud and Colocation Providers** | Differentiation on verifiable sustainability credentials; ability to offer tenants guaranteed sustainability SLAs backed by real-time data; stronger positioning under SEC ESG disclosure requirements. |
| **Enterprise Tenants** | Granular, verified Scope 3 emissions data for hosted infrastructure; ability to verify the sustainability credentials of their provider; measurable support for internal net-zero commitments. |
| **Hardware and Software Vendors** | A common interface standard reduces fragmentation and integration cost. Vendors building to the specification gain interoperability across the GSF ecosystem and with compliant grid operators globally. |

---

## 7. Governance and Development Approach

### 7.1 Green Software Foundation Framework

The specification will be developed within the Green Software Foundation, a non-profit organisation operating under the Linux Foundation. The GSF brings together technology companies, academic institutions, and practitioners to create open standards for sustainable digital infrastructure through a collaborative, consensus-driven process.

The Hardware Standards Working Group, established following the merger of the Sustainable and Scalable Infrastructure Alliance (SSIA) with the GSF in late 2024, provides the governance structure for this specification's development. The Working Group operates under the GSF's seven-stage specification lifecycle, ensuring quality, stakeholder consensus, and real-world validation before any specification reaches public release.

### 7.2 Open Standard Development

The specification will be developed as an open standard, accessible to all GSF members and to organisations that join specifically to contribute to this project. The development process is designed to be inclusive across the full ecosystem: data centre operators, grid operators, hardware and software vendors, and academic research institutions. Academic participation carries no cost within the GSF framework.

The specification will be developed with awareness of, and compatibility with, relevant existing standards, including EN 50600-4-2 (PUE definition), ISO 50001 (energy management systems), and IEEE Power and Energy Society grid standards. Where appropriate, the specification will seek alignment with ISO processes, consistent with the GSF's approach to its Software Energy Efficiency specification.

---

## 8. The Case for Acting Now

Three converging forces make the development of this specification both timely and urgent.

The first is **regulatory acceleration**. The EU's EED reporting requirements are already active. CSRD obligations are rolling out in annual waves, and a further Data Centre Energy Efficiency Package is expected within the first half of 2026. Operators who establish the real-time grid-interface infrastructure that meaningful sustainability reporting requires will be measurably better positioned than those who defer to the point at which minimum performance standards are imposed.

The second is the **infrastructure inflection point**. Global data centre power demand is projected to roughly double between 2023 and 2028, driven primarily by AI workloads. The window for establishing the interoperability standards that will govern the next generation of data centre infrastructure is narrow. Standards embedded in infrastructure from the outset are adopted immediately; those developed after the build is complete face years of retrofit.

The third is the **absence of an open standard**. Industry pilots — including EPRI's DCFlex and various hyperscaler programmes — have demonstrated that grid-responsive data centre operation is technically feasible and economically valuable. They have not, however, produced a vendor-neutral, openly governed standard that any operator can implement. The GSF, building on its proven track record with SCI and WDPC, is positioned to fill that gap.

> **The market has demonstrated that grid-responsive sustainability optimisation is possible. The regulatory environment is increasingly mandating it. What is missing is the open standard that makes it universal. That is what this specification will provide.**

---

## Conclusion

The data centre industry stands at an inflection point. The convergence of accelerating AI-driven power demand, maturing grid-responsive technology, and an increasingly demanding regulatory environment creates both the necessity and the opportunity to establish a new, open standard for real-time sustainability optimisation.

The proposed GSF interoperability specification addresses a gap that is genuine, consequential, and currently unmet by any open standard. It will not replace existing frameworks — it will extend them to the layer where they currently stop: the interface between the data centre and the grid. In doing so, it will give operators the tools to manage their sustainability profile dynamically, give regulators the data infrastructure they need to enforce emerging requirements, and give the market the common language that grid-responsive sustainability at scale demands.

The time to develop this standard is before the next generation of infrastructure is built — not after.

---

## References and Regulatory Citations

- **EU EED:** Directive (EU) 2023/1791 of the European Parliament and of the Council on Energy Efficiency (recast), Articles 12, 25, 26, 33, and Annex VII
- **EU EED Delegated Act:** Commission Delegated Regulation (EU) 2024/1364 of 14 March 2024 — first phase of the establishment of a common Union rating scheme for data centres
- **CSRD:** Directive (EU) 2022/2464 of the European Parliament and of the Council of 14 December 2022
- **ESRS:** European Sustainability Reporting Standards, developed by EFRAG and formally adopted by the European Commission, July 2023
- **European Green Deal:** Communication COM/2019/640 final — The European Green Deal
- **EU Digitalisation Action Plan:** Action Plan for the Digitalisation of the Energy Sector, European Commission, October 2022
- **DOE (2024):** Powering AI and Data Center Infrastructure Recommendations, US Department of Energy, 2024
- **LBNL (2024):** Data Centre Energy Consumption Assessment, Lawrence Berkeley National Laboratory, 2024
- **EPRI DCFlex:** Electric Power Research Institute, DCFlex Project — epri.com
- **Texas SB6:** Texas Senate Bill 6 (SB6), enacted June 2025 — grid planning, interconnection, and emergency operations reforms for large data centre loads
- **Turner and Townsend (2025):** Data Center Construction Cost Index 2025 — APAC power demand projections
- **EN 50600-4-2:** Information technology — Data centre facilities and infrastructures — Part 4-2: Power usage effectiveness
- **ISO 50001:** Energy management systems — Requirements with guidance for use
- **GSF WDPC:** Workload Dynamic Power and Cooling specification, Green Software Foundation Hardware Standards Working Group — greensoftware.foundation
- **GSF SCI:** Software Carbon Intensity specification v1.0, Green Software Foundation, December 2022

---

*This white paper is a publication of the GSF Hardware Standards Working Group. The views and proposals it contains are subject to revision through the GSF's open specification development process.*

*© 2026 Green Software Foundation. Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0).*


# Bridging the Sustainability Gap: A Standardised Interoperability Layer for Real-Time Data Centre Sustainability Optimisation

**Green Software Foundation — Hardware Standards Working Group**
*White Paper | July 2026*

*greensoftware.foundation*

---

## Abstract

This white paper presents the case for a new, open, vendor-neutral interoperability specification for real-time sustainability optimisation in data centres, developed under the Green Software Foundation (GSF) Hardware Standards Working Group. It defines the problem the specification addresses, examines the regulatory landscape that makes the work urgent, describes the proposed specification in detail, and maps the value it delivers across the data centre ecosystem.

The specification will establish a standardised mechanism through which data centres can receive live grid signals, understand the renewable and non-renewable composition of available power, and dynamically adjust workload consumption in response. It is distinct from — but builds upon — the existing GSF Workload Dynamic Power and Cooling (WDPC) specification, which will serve as a normative reference.

---

## Executive Summary

The data centre industry faces a fundamental and largely unaddressed contradiction: a facility can be highly energy-efficient by conventional measures and yet remain environmentally unsustainable. Power Usage Effectiveness (PUE) — the dominant metric for data centre energy performance — tells operators how efficiently they use the power they draw. It reveals nothing about what that power is, where it originates, or how intelligently their consumption responds to the state of the grid that supplies it.

The regulatory environment transforms this gap from an operational blind spot into an urgent compliance liability. The EU's Energy Efficiency Directive (EED), now in mandatory annual reporting phase for all data centres above 500 kW, the Corporate Sustainability Reporting Directive (CSRD), and a forthcoming EU Data Centre Energy Efficiency Package collectively require precisely the kind of real-time, source-aware consumption data that this specification is designed to produce. Similar regulatory pressures are emerging in the United States and across the Asia-Pacific region, where projected power demand growth of 165% by 2030 is driving urgent policy responses.

> **Core proposition:** Sustainability requires knowing not just how much power you consume, but what power you consume — and being able to act on that knowledge in real time.

The proposed specification addresses this challenge directly. It will define a standardised mechanism for data centres to receive real-time grid signals, understand the renewable and non-renewable composition of available power, and dynamically adjust workload consumption in response — enabling operators to make intelligent, real-time trade-offs between performance and sustainability.

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

#### Corporate Sustainability Reporting Directive — Directive (EU) 2022/2464

The CSRD requires large companies to publish detailed ESG disclosures aligned with the European Sustainability Reporting Standards (ESRS). Approximately **50,000 organisations** fall within its remit, including over 10,000 non-EU entities with significant European operations.

For data centre operators and their enterprise tenants, the CSRD requires credible disclosure of Scope 2 emissions from purchased electricity and, increasingly, of Scope 3 emissions attributable to IT infrastructure. Without the ability to track real-time power source composition, CSRD disclosures on infrastructure carbon intensity are estimates at best. The proposed specification provides the data infrastructure that makes verifiable, granular CSRD compliance achievable.

#### EU Data Centre Sustainability Rating Scheme — Delegated Regulation (EU) 2024/1364

Adopted in March 2024, this delegated regulation establishes the first phase of an EU-wide scheme to rate the sustainability of data centres. A sustainability rating creates direct commercial and reputational incentives for operators to actively manage their sustainability profile, not merely report it passively. The proposed specification is the operational mechanism through which favourable ratings can be achieved and maintained.

#### European Green Deal, Fit for 55, and the Forthcoming Data Centre Package

A dedicated **Data Centre Energy Efficiency Package** is expected alongside the EU Strategy Roadmap on Digitalisation and AI in the first half of 2026, signalling continued and accelerating regulatory attention. Operators implementing the kind of real-time grid-responsive management this specification enables will be measurably better positioned when that package arrives.

### 3.2 United States: Federal Recommendations and State-Level Action

The US Department of Energy's 2024 recommendations explicitly identify three federal priorities that align directly with the proposed specification: improving efficiency in AI workloads; codifying **utility-operator flexibility contracts**; and accelerating clean generation and storage tailored for data centre load growth. The proposed specification provides the interoperability standard that makes utility-operator flexibility contracts technically realisable at scale.

At the industry level, the Electric Power Research Institute's DCFlex project is actively piloting demand-response, workload shifting, and UPS-as-grid-resource approaches. The proposed GSF specification would provide the open, vendor-neutral interoperability standard that commercial pilots such as DCFlex currently lack.

### 3.3 Asia-Pacific: Urgency at Scale

Power demand in the APAC region is projected to grow from approximately 320 TWh in 2024 to 780 TWh by 2030 — a **165% increase**. Singapore’s strict sustainability conditions for new data centre builds and Japan’s focus on co-locating infrastructure with clean energy signal a clear regional direction of travel toward sustainability-conditional data centre development.

### 3.4 The Compliance Landscape at a Glance

| Framework | Geography | Relevance to Specification |
|-----------|-----------|---------------------------|
| EED (EU) 2023/1791 | EU (500 kW+ DCs) | Mandatory annual reporting on renewable use. Real-time data infrastructure is required to comply credibly. |
| CSRD (EU) 2022/2464 | EU + global | Requires verifiable ESG disclosure including Scope 2 and Scope 3 infrastructure emissions. |
| Delegated Regulation 2024/1364 | EU | Establishes EU sustainability rating scheme. Active sustainability management will determine outcomes. |
| DOE Recommendations (2024) | USA | Federal call for codified utility-operator flexibility contracts. |
| EPRI DCFlex | USA (industry) | Industry-led pilots demonstrating demand-response value. The specification provides the missing open-standard layer. |
| Singapore DC Conditions | APAC | Sustainability-conditional approvals for new builds. Grid-responsive operation is becoming a market access requirement. |

---

## 4. The Proposed Specification

### 4.1 Objective

The specification defines an open, vendor-neutral interoperability layer that enables any data centre — regardless of vendor, operator, or geography — to receive, interpret, and respond to real-time grid sustainability signals. It is a standard: a common language and framework that allows the data centre and the grid to communicate, and that empowers operators to act on that communication with intelligence and verifiability.

### 4.2 Core Technical Requirements

The specification addresses the interface between the data centre and the external power grid across six functional areas:

- **Grid signal ingestion:** The data centre receives real-time signals regarding available capacity, renewable composition, and carbon intensity.
- **Power source awareness:** The data centre tracks the composition of the power it is drawing and maintains this as a live parameter.
- **Dynamic consumption control:** Operators configure a sustainability-versus-performance parameter that translates into workload-level consumption decisions.
- **Peak demand avoidance:** The system prevents drawing beyond grid capacity thresholds, avoiding demand spikes that trigger higher-emission backup generation.
- **ESG data output:** The specification supports generation of real-time, source-level consumption data in formats required for compliance reporting.
- **Secure data transport:** The specification defines protocol-agnostic, secure, and low-latency transport mechanisms (e.g., MQTT, secure RESTful APIs) ensuring that the two-way grid interface cannot become an attack vector for unauthorized facility control.

### 4.3 The Sustainability–Performance Scale

A core architectural concept is a configurable, dynamic parameter representing the operator's chosen position on a spectrum between maximum performance and maximum sustainability. It is a continuously adjustable scale that can be set manually, configured to follow time-of-day profiles, triggered automatically by grid events, or governed by pre-defined policy rules.

### 4.4 Scope Boundaries and Relationship to WDPC

The specification operates at the layer above the facility interior. WDPC defines the data models and signalling framework within the facility. The proposed specification defines the external interface. WDPC is used as a normative reference for internal data models; the two specifications are complementary but distinct.

### 4.5 What the Specification Is Not

- It is not a proprietary data centre management system or vendor product.
- It is not a replacement for PUE measurement or existing energy efficiency frameworks.
- It is not a prescriptive operational policy — it defines the interface, not the decisions.
- It does not replicate the internal facility-level coverage of WDPC.
- **It is not a loophole for greenwashing — it provides verifiable, immutable data telemetry to prevent the manipulation of sustainability metrics, rather than enabling it.**

### 4.6 Conceptual Data Model Schemas

To ensure vendor-neutrality and broad interoperability, the specification defines a lightweight, protocol-agnostic data model built around three core functional schemas.

#### Schema A: Inbound Grid Telemetry (Grid to Data Centre)
Standardizes the signals the facility receives from the local grid operator or utility market aggregator.

| Field Name | Data Type | Unit | Description |
| :--- | :--- | :--- | :--- |
| `timestamp` | `ISO 8601` | Date/Time | The exact time the grid signal was generated. |
| `grid_node_id` | `String` | None | Unique identifier for the local substation or grid interconnection point. |
| `carbon_intensity` | `Float` | gCO₂eq/kWh | Real-time marginal carbon emissions of the local grid. |
| `renewable_ratio` | `Float` | Percentage | The current proportion of grid power generated by renewable sources. |
| `grid_status` | `Enum` | [NORMAL, PEAK, STRESS, EMERGENCY] | Current operational state of the grid. |
| `capacity_limit` | `Integer` | kW | *Optional.* Maximum power draw permitted during a STRESS event. |
| `forecast_window` | `Array` | Minutes | *Optional.* Projected carbon intensity/grid status for the next 15/30/60 mins. |

#### Schema B: Outbound Facility Intent & Telemetry (Data Centre to Grid/Auditor)
Transmits the facility’s current consumption profile and its intended future draw back to the grid operator, and serves as the foundational record for EED/CSRD reporting.

| Field Name | Data Type | Unit | Description |
| :--- | :--- | :--- | :--- |
| `facility_id` | `String` | None | GSF-compliant unique identifier for the data centre facility. |
| `current_draw` | `Integer` | kW | Total instantaneous facility power consumption from the grid. |
| `renewable_draw` | `Integer` | kW | Calculated renewable consumption. |
| `flexibility_margin` | `Integer` | kW | Power the facility can shed/shift within 5 minutes without dropping critical workloads. |
| `projected_draw_1h` | `Integer` | kW | Estimated power requirement for the next hour. |
| `active_response` | `Boolean` | True/False | Flags whether the facility is actively suppressing demand in response to a grid STRESS signal. |

#### Schema C: The Sustainability-Performance (S-P) Operational State
Translates the conceptual scale into a machine-readable state for internal facility orchestrators.

| Field Name | Data Type | Unit | Description |
| :--- | :--- | :--- | :--- |
| `sp_index` | `Integer` | Scale (1-10) | 1 = Max Performance; 10 = Max Sustainability. |
| `policy_trigger` | `Enum` | [MANUAL, SCHEDULED, GRID_EVENT, CARBON_THRESHOLD] | Indicates why the current `sp_index` is active. |
| `max_carbon_ceiling`| `Float` | gCO₂eq/kWh | Hard policy limit forcing highly sustainable modes if exceeded. |

### 4.7 Integration with WDPC Data Models

The data models defined above intentionally stop at the facility's edge. Once the `sp_index` and grid `carbon_intensity` are ingested, they are passed to the facility's internal management systems. From there, the GSF **Workload Dynamic Power and Cooling (WDPC)** specification takes over. WDPC utilizes these external data points to execute the required hardware-level commands, ensuring a seamless chain of custody from the macroscopic grid signal down to the microscopic CPU instruction.

---

## 5. Illustrative Use Cases

### 5.1 Time-of-Day Optimisation
The system prioritises flexible workloads between midnight and 6:00 AM to absorb renewable generation that would otherwise be curtailed. As the morning demand peak approaches, it automatically transitions to a performance-priority profile.

### 5.2 Grid Stress Event Response
During a peak demand period, the grid operator signals a demand constraint event. The data centre applies a pre-configured demand reduction profile. The event is logged as a verified sustainability action in the facility's compliance reporting dataset.

### 5.3 Power Source Selection on a Mixed-Source Grid
The operator targets drawing at least 80% of power from zero-carbon sources. The interoperability layer dynamically adjusts workload intensity to hit this target based on live grid mixes.

### 5.4 On-Site Renewable Integration
The operator configures a preference for on-site renewable consumption, automatically scheduling flexible workloads to coincide with peak generation windows and reducing grid draw.

---

## 6. Stakeholder Value

| Stakeholder | Value Delivered |
|-------------|----------------|
| **Data Centre Operators** | Real-time control over the sustainability-performance trade-off; verifiable compliance data for EED and CSRD reporting; improved sustainability ratings; reduced exposure to forthcoming minimum performance standards. |
| **Grid Operators** | Data centres become predictable, programmable demand participants. **The specification provides grid operators with standardised, predictable demand elasticity without requiring them to build bespoke API integrations for every single hyperscaler or colocation vendor.** Demand-response capability supports grid stability during stress events and absorbs excess renewable generation. |
| **Regulators and Policymakers** | Open, standardised reporting infrastructure makes EED and CSRD enforcement tractable. A common data model enables consistent cross-border sustainability monitoring. |
| **Cloud and Colocation Providers** | Differentiation on verifiable sustainability credentials; ability to offer tenants guaranteed SLAs backed by real-time data. |
| **Enterprise Tenants** | Granular, verified Scope 3 emissions data for hosted infrastructure; measurable support for internal net-zero commitments. |
| **Hardware and Software Vendors** | A common interface standard reduces fragmentation and integration cost. Vendors building to the specification gain interoperability across the GSF ecosystem. |

---

## 7. Governance and Development Approach

### 7.1 Green Software Foundation Framework

The specification will be developed within the Green Software Foundation, a non-profit organisation operating under the Linux Foundation. The Hardware Standards Working Group, formally established following the integration of the Sustainable and Scalable Infrastructure Alliance (SSIA) principles into the GSF, provides the governance structure for this specification's development. The Working Group operates under the GSF's standard lifecycle, ensuring quality, stakeholder consensus, and real-world validation.

### 7.2 Open Standard Development

The specification will be developed as an open standard, accessible to all GSF members and to organisations that join specifically to contribute to this project. The development process is designed to be inclusive across the full ecosystem: data centre operators, grid operators, hardware and software vendors, and academic research institutions.

---

## 8. The Case for Acting Now

Three converging forces make the development of this specification both timely and urgent.

1. **Regulatory acceleration:** The EU's EED reporting requirements are already active. CSRD obligations are rolling out in annual waves, and a further Data Centre Energy Efficiency Package is expected within the first half of 2026.
2. **Infrastructure inflection point:** Global data centre power demand is projected to roughly double between 2023 and 2028, driven primarily by AI workloads.
3. **Absence of an open standard:** Industry pilots have demonstrated that grid-responsive operation is feasible and valuable, but have not produced a vendor-neutral standard. 

> **The market has demonstrated that grid-responsive sustainability optimisation is possible. The regulatory environment is increasingly mandating it. What is missing is the open standard that makes it universal. That is what this specification will provide.**

---

## Conclusion

The data centre industry stands at an inflection point. The convergence of accelerating AI-driven power demand, maturing grid-responsive technology, and an increasingly demanding regulatory environment creates both the necessity and the opportunity to establish a new, open standard for real-time sustainability optimisation.

The proposed GSF interoperability specification addresses a gap that is genuine, consequential, and currently unmet by any open standard. It will not replace existing frameworks — it will extend them to the layer where they currently stop: the interface between the data centre and the grid. In doing so, it will give operators the tools to manage their sustainability profile dynamically, give regulators the data infrastructure they need to enforce emerging requirements, and give the market the common language that grid-responsive sustainability at scale demands.

The time to develop this standard is before the next generation of infrastructure is built — not after.

---

## References and Regulatory Citations

- **EU EED:** Directive (EU) 2023/1791 of the European Parliament and of the Council on Energy Efficiency (recast)
- **EU EED Delegated Act:** Commission Delegated Regulation (EU) 2024/1364 of 14 March 2024
- **CSRD:** Directive (EU) 2022/2464 of the European Parliament and of the Council of 14 December 2022
- **ESRS:** European Sustainability Reporting Standards, developed by EFRAG, July 2023
- **European Green Deal:** Communication COM/2019/640 final
- **EU Digitalisation Action Plan:** Action Plan for the Digitalisation of the Energy Sector
- **DOE (2024):** Powering AI and Data Center Infrastructure Recommendations
- **LBNL (2024):** Data Centre Energy Consumption Assessment
- **EPRI DCFlex:** Electric Power Research Institute, DCFlex Project
- **Texas SB6:** Texas Senate Bill 6 (SB6), enacted June 2025
- **Turner and Townsend (2025):** Data Center Construction Cost Index 2025
- **EN 50600-4-2:** Information technology — Data centre facilities and infrastructures — Part 4-2: Power usage effectiveness
- **ISO 50001:** Energy management systems — Requirements with guidance for use
- **GSF WDPC:** Workload Dynamic Power and Cooling specification
- **GSF SCI:** Software Carbon Intensity specification v1.0

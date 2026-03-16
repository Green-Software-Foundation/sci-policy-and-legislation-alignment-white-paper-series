# California Climate Disclosure Laws and the GSF SCI Score: A Synergy Analysis

## Exploring How SB 253, SB 261, and the Software Carbon Intensity Framework Can Reinforce Each Other

**Version**: 1.1 **Date**: March 2026 **Author**: GSF Policy Working Group **Status**: Working Draft

---

## Executive Summary

California's climate disclosure laws represent a step change in corporate emissions transparency. SB 253 mandates annual GHG emissions reporting (Scopes 1, 2, and 3) for all entities with over $1 billion in annual revenue doing business in the state, with the first Scope 1 and 2 deadline on August 10, 2026. SB 261 requires biennial TCFD-aligned climate risk reports from entities exceeding $500 million in revenue. Together, these laws affect thousands of companies, including virtually every major technology firm.

The Green Software Foundation's Software Carbon Intensity (SCI) specification, published as ISO/IEC 21031:2024, provides a purpose-built methodology for quantifying the carbon emissions attributable to software systems. Its formula, `SCI = ((E x I) + M) / R`, decomposes emissions into energy consumption, grid carbon intensity, embodied hardware emissions, and a functional unit of work, producing a rate-based metric that enables both absolute reporting and intensity tracking.

**Key findings:**

- **Strong synergy with SB 253 Scope 3 reporting.** The SCI's embodied emissions component (M) and its energy-times-intensity calculation (E x I) map directly to GHG Protocol Scope 3 Categories 1, 2, and 11 --- the categories most material to technology companies. SCI calculations provide the granular, auditable data trail that SB 253's assurance requirements demand.

- **Strong synergy with SB 261 Metrics & Targets pillar.** The SCI provides exactly the kind of quantified, comparable, forward-looking intensity metric that TCFD's Metrics & Targets pillar requires. Its geographic energy data also informs the physical and transition risk assessments central to TCFD's Risk Management and Strategy pillars.

- **The SCI for AI specification addresses a critical gap.** With AI workloads driving rapid growth in technology-sector emissions, the SCI for AI's dual Provider/Consumer scoring model and training amortization methodology fill a gap that neither the GHG Protocol nor TCFD guidance adequately addresses.

- **The GSF Self-Certification Program builds compliance readiness.** Its mandatory disclosure requirements --- software boundary definitions, functional unit rationale, data source documentation, and methodology transparency --- produce documentation that directly supports SB 253's third-party assurance process and SB 261's risk disclosure narratives.

- **Notable gaps remain.** SB 253 requires absolute emissions figures, while the SCI produces intensity metrics. The SCI for Web specification is still under development. SB 261 enforcement is stayed pending Ninth Circuit resolution. And both laws apply across all sectors, not just technology --- limiting the SCI's coverage to software-related emissions only.

**Bottom line:** For technology companies preparing to meet California's August 2026 deadline and the Scope 3 requirements beginning in 2027, implementing SCI calculations across their software portfolio is not just a sustainability exercise --- it is a compliance accelerator. The SCI provides the methodological rigor, documentation discipline, and component-level granularity that transforms software emissions from an opaque Scope 3 estimation into an auditable, defensible disclosure.

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [Regulatory Background: SB 253 and SB 261](#2-regulatory-background-sb-253-and-sb-261)
3. [The GSF SCI Framework](#3-the-gsf-sci-framework)
4. [Mapping SCI to SB 253: GHG Protocol Scope Alignment](#4-mapping-sci-to-sb-253-ghg-protocol-scope-alignment)
5. [Mapping SCI to SB 261: TCFD Pillar Alignment](#5-mapping-sci-to-sb-261-tcfd-pillar-alignment)
6. [Synergy Analysis](#6-synergy-analysis)
7. [Global Regulatory Context](#7-global-regulatory-context)
8. [Implications for California Technology Companies](#8-implications-for-california-technology-companies)
9. [Recommendations](#9-recommendations)
10. [Conclusions](#10-conclusions)
11. [Sources](#11-sources)

---

## 1. Introduction

Technology companies face an unprecedented convergence of climate disclosure obligations. California's SB 253 and SB 261, the EU's Corporate Sustainability Reporting Directive (CSRD), and frameworks from the ISSB are creating overlapping requirements that demand rigorous, consistent approaches to measuring and reporting greenhouse gas emissions.

For the technology sector, this challenge is particularly acute. Software-driven companies generate the majority of their emissions through electricity consumption in data centers (Scope 2) and across complex hardware supply chains (Scope 3). These emissions are diffuse, technically complex to measure, and historically difficult to attribute to specific products or services. A 2024 study by The Guardian found that major technology companies collectively underreported their emissions by an estimated 662%, with Scope 3 supply chain emissions representing the largest gap.

The Green Software Foundation's Software Carbon Intensity (SCI) specification was designed precisely for this problem. First published in 2022 and codified as ISO/IEC 21031:2024 in March 2024, the SCI provides a standardized methodology for calculating the carbon emissions rate of a software system. Unlike broad corporate carbon accounting approaches, the SCI operates at the software-system level, decomposing emissions into measurable components (energy, carbon intensity, embodied emissions) and normalizing them against a functional unit of work.

This paper examines whether and how the SCI framework can serve as a bridge between the technical reality of software emissions and the regulatory requirements of California's disclosure regime. We analyze the alignment between SCI components and GHG Protocol scopes (for SB 253), between SCI metrics and TCFD pillars (for SB 261), and identify both synergies and gaps that technology companies should consider as they build their compliance strategies.

---

## 2. Regulatory Background: SB 253 and SB 261

### 2.1 SB 253: Climate Corporate Data Accountability Act

SB 253, signed by Governor Newsom on October 7, 2023, requires comprehensive greenhouse gas emissions reporting aligned with the GHG Protocol.

**Scope and applicability:**

- **Revenue threshold**: Annual global revenues exceeding $1 billion
- **Entity types**: U.S.-domiciled corporations, LLCs, and partnerships --- both public and private
- **"Doing business in California"**: Defined by reference to California Revenue and Tax Code Section 23101; CARB's proposed regulations set the nexus threshold at approximately $735,019 in California sales
- **Estimated coverage**: Approximately 2,596 entities identified on CARB's preliminary list (September 2025)

**Reporting requirements:**

| Requirement | Details |
| :--- | :--- |
| **Scope 1 & 2** | Annual reporting beginning August 10, 2026 (FY 2025 data) |
| **Scope 3** | Annual reporting beginning 2027 (FY 2026 data); CARB sets exact deadline per SB 219 |
| **GHG Protocol** | Must conform with GHG Protocol Corporate Standard (Scopes 1 & 2) and Corporate Value Chain Standard (Scope 3) |
| **Assurance** | Limited assurance for Scope 1 & 2 from 2026; reasonable assurance from 2030; limited assurance for Scope 3 from 2030 |
| **Penalties** | Up to $500,000 per entity per year in administrative penalties |

**Safe harbor:** Entities face no administrative penalties for Scope 3 misstatements made "with a reasonable basis and disclosed in good faith" from 2027 through 2030. This safe harbor does not protect against failure to file.

**First-year flexibility:** CARB issued an Enforcement Notice (December 5, 2024) confirming no penalties for 2026 non-compliance where companies demonstrate a "good faith effort."

### 2.2 SB 261: Greenhouse Gases: Climate-Related Financial Risk

SB 261 mandates biennial climate-related financial risk reports aligned with the 2017 TCFD recommendations.

**Scope and applicability:**

- **Revenue threshold**: Annual revenues exceeding $500 million
- **Estimated coverage**: Approximately 4,160 entities on CARB's preliminary list
- **Reporting**: Biennial; companies host reports on their own websites and submit URLs to CARB's docket

**TCFD four pillars:**

1. **Governance** --- Board and management oversight structures for climate risk
2. **Strategy** --- Short-, medium-, and long-term climate risks and opportunities; scenario analysis
3. **Risk Management** --- Processes for identifying, assessing, and managing climate-related risks
4. **Metrics and Targets** --- Metrics and targets used to assess and manage material climate-related risks

**Acceptable frameworks**: TCFD (2017), IFRS S2 (ISSB), or other regulated exchange/government frameworks. Penalties are up to $50,000 per year for non-compliance.

**Current status:** On November 18, 2025, the U.S. Court of Appeals for the Ninth Circuit granted an injunction halting enforcement of SB 261 pending appeal. CARB confirmed it will not enforce SB 261 while the injunction holds. The public docket remains open for voluntary submissions; approximately 100 entities had filed voluntarily as of January 2026.

### 2.3 Amendments and Litigation

**SB 219** (signed September 2024) extended CARB's rulemaking deadline to July 1, 2025, granted CARB discretion over the Scope 3 reporting schedule, enabled consolidated parent-subsidiary reporting, and authorized CARB to engage a third-party emissions reporting organization. **AB 154** (signed October 11, 2025) exempted CARB's rulemaking from CEQA review, created the Climate Accountability and Emissions Disclosure Fund, and codified CARB's authority to contract with an emissions reporting organization.

The primary legal challenge is *Chamber of Commerce v. CARB* (filed January 2024), asserting First Amendment compelled speech, federal preemption, and dormant Commerce Clause claims. The district court denied a preliminary injunction in August 2025. The Ninth Circuit granted a partial injunction in November 2025 --- staying SB 261 enforcement while leaving SB 253 intact. Oral arguments on January 9, 2026 revealed significant judicial scrutiny of Scope 3 constitutionality, with California signaling openness to severing Scope 3 provisions if necessary.

**Practical impact:** SB 253 remains fully enforceable with the August 10, 2026 deadline intact. SB 261 enforcement is stayed. The Ninth Circuit's focus on Scope 3 requirements introduces uncertainty for the 2027 timeline, but no current order limits SB 253's scope.

---

## 3. The GSF SCI Framework

### 3.1 The Core SCI Specification

The Software Carbon Intensity (SCI) specification, published as ISO/IEC 21031:2024, provides a methodology for calculating the rate of carbon emissions for a software system.

**Core formula:**

```
SCI = ((E x I) + M) / R
```

| Component | Definition | Unit |
| :--- | :--- | :--- |
| **E** | Energy consumed by the software system | kWh |
| **I** | Location-based carbon intensity of the electricity grid | gCO2eq/kWh |
| **E x I** | Operational emissions (O) | gCO2eq |
| **M** | Embodied emissions from hardware manufacturing, transport, and disposal, allocated by time-share and resource-share | gCO2eq |
| **R** | Functional unit representing a unit of work (e.g., per API request, per user, per training run) | varies |

**Key provisions:**

- **Location-based accounting required**: Market-based measures (offsets, RECs, PPAs) are explicitly excluded. The SCI measures what software *causes*, not what organizations *pay to offset*.
- **Five-step procedure**: Bound (define software boundary) -> Scale (select functional unit) -> Define (choose quantification method) -> Quantify (compute rate per component) -> Report (disclose score, boundary, methodology).
- **Two quantification methods**: Measurement (real-world telemetry) or Calculation (modeled/benchmark).
- **Mandatory disclosure**: Score value, software boundary, functional unit rationale, methodology, assumptions, and limitations.

### 3.2 SCI for AI

Ratified on December 18, 2025, after approximately one year of development involving over 100 organizations, the SCI for AI is the first domain-specific extension of the base SCI methodology. ISO submission is planned for Q2 2026.

The specification bifurcates the AI lifecycle into two independent scores:

- **Provider Score** covers development: inception, design and development, deployment, and retirement. Mandatory functional units include per FLOP (compute efficiency), per training token (data quality/curation efficiency), or per parameter (model architecture efficiency). The boundary encompasses training infrastructure, data collection/preprocessing, synthetic data generation, feature engineering, model evaluation, and optimization systems.

- **Consumer Score** covers operations: inference serving, orchestration, scaling, monitoring, storage, and client-side UX. Functional units align with delivery/billing models --- per token (LLMs), per image (image generation), per workflow execution (agentic AI), per inference (classical ML), etc.

Training emissions are amortized over the entire training duration, including all epochs, steps, parameter updates, intermediate runs, and early stopping phases. For agentic AI composite operations involving multiple model calls, tool invocations, or service integrations, emissions account for all triggered operations.

### 3.3 SCI for Web

The SCI for Web specification is under active development, with the assembly starting on September 16, 2025. The GSF and W3C have announced a formal collaboration: GSF manages the SCI for Web specification through its consensus-driven standards process, while W3C's Sustainable Web Interest Group (chartered October 2024) focuses on the broader Web Sustainability Guidelines (WSG). SCI for Web focuses on *quantitative measurement* (carbon intensity per web interaction), complementing the WSG's *qualitative best practices*.

### 3.4 GSF Self-Certification Program

The GSF Self-Certification Program for ISO/IEC 21031:2024, aligned with the ISO/IEC 17050 framework (Supplier's declaration of conformity), enables organizations to self-certify conformity, disclose all required calculation details for public review, receive a certificate after GSF verifies disclosure completeness, and submit to community validation through a formal challenge process.

The program is free, email-based, and uses manual human review by a committee of 3-5 SCI experts. Certificates are valid for one year. Submissions may use either a web form or the Impact Manifest Protocol (IMP) --- a structured YAML/JSON format that enables automated submission pipelines and CI/CD integration.

The program's mandatory disclosure requirements map directly to SB 253 assurance documentation needs:

| GSF Disclosure Requirement | SB 253 Assurance Need |
| :--- | :--- |
| Score value with units and measurement period | Reported emissions figure with temporal boundary |
| Software boundary (included/excluded with rationale) | Organizational and operational boundary definition |
| Functional unit with rationale and measurement method | Intensity metric denominator; activity data source |
| Energy (E) details: measurement method, PUE, data sources | Scope 2 calculation methodology and data provenance |
| Carbon intensity (I): locations, values, sources | Grid emission factor selection and justification |
| Embodied emissions (M): TE, EL, TiR, RR/ToR | Scope 3 Category 1 and 2 calculation methodology |
| Assumptions, limitations, uncertainties | Uncertainty assessment required by assurance standards |
| Data sources with access dates | Data provenance trail for audit |

A company that has completed the GSF Self-Certification process for its major software systems has, in effect, created the audit working papers for the software-related portions of its SB 253 disclosure.

---

## 4. Mapping SCI to SB 253: GHG Protocol Scope Alignment

### 4.1 Component-to-Scope Mapping

The SCI formula's components map to GHG Protocol scopes as follows:

| SCI Component | GHG Protocol Scope | Category | Rationale |
| :--- | :--- | :--- | :--- |
| **E x I** (owned/controlled data centers) | **Scope 1** | Direct emissions | Emissions from on-premise generators, cooling systems with refrigerants |
| **E x I** (purchased electricity) | **Scope 2** | Purchased electricity | Grid electricity consumed by data centers and offices; this is the primary mapping |
| **M** (purchased hardware) | **Scope 3, Cat 1** | Purchased goods and services | Manufacturing emissions of servers, GPUs, networking equipment |
| **M** (capital equipment) | **Scope 3, Cat 2** | Capital goods | Data center construction, major infrastructure investments |
| **E x I** (cloud provider electricity) | **Scope 3, Cat 1** | Purchased goods and services | Cloud provider's electricity consumption is a purchased service |
| **E x I** (end-user device energy) | **Scope 3, Cat 11** | Use of sold products | Energy consumed by software running on customer devices |
| **M** (end-user device embodied share) | **Scope 3, Cat 11** | Use of sold products | Share of customer hardware embodied emissions attributable to the software |
| **E x I** (upstream data transfer) | **Scope 3, Cat 3** | Fuel- and energy-related activities | Network transmission energy not included in Scope 1 or 2 |

For technology companies, Scope 3 typically constitutes 70-90% of total emissions. The most material categories --- Categories 1 (purchased goods and services), 2 (capital goods), and 11 (use of sold products) --- are all directly covered by SCI components. Category 12 (end-of-life treatment of sold products) is not directly covered.

### 4.2 Absolute vs. Intensity Metrics

SB 253 requires reporting of **absolute** emissions (total tonnes CO2eq per year). The SCI produces **intensity** metrics (gCO2eq per functional unit). This is a fundamental difference, but not an unbridgeable gap:

```
Absolute Emissions = SCI Score x Total Functional Units in Reporting Period
```

For example: an SCI of 349.63 gCO2eq per 1,000 API requests, multiplied by 540 million total requests in FY 2025, yields 188.8 tonnes CO2eq. SB 253 requires both absolute emissions *and* intensity metrics. The SCI provides intensity by design and absolute emissions through multiplication by total usage --- making SCI calculations directly usable for SB 253 reporting.

### 4.3 Location-Based Accounting

The SCI specification *requires* location-based carbon intensity and explicitly excludes market-based instruments (RECs, offsets, PPAs). The GHG Protocol --- and by extension SB 253 --- requires location-based accounting and *permits* market-based reporting as a complement. SCI calculations automatically produce location-based figures that satisfy SB 253's mandatory requirement. Companies wishing to report market-based figures for voluntary purposes can do so separately, but the SCI's conservative location-based approach ensures the regulatory floor is always met.

---

## 5. Mapping SCI to SB 261: TCFD Pillar Alignment

### 5.1 Metrics & Targets Pillar

The TCFD Metrics & Targets pillar requires organizations to disclose the metrics used to assess climate-related risks and the targets used to manage them. The SCI is particularly well-suited here:

| TCFD Requirement | SCI Contribution |
| :--- | :--- |
| Quantified metrics for climate assessment | SCI score provides a precise, reproducible, ISO-standardized metric |
| Cross-industry comparability | Functional units enable within-category comparison (e.g., gCO2eq per API request across services) |
| Forward-looking targets | SCI baseline comparisons enable reduction target-setting with measurable progress tracking |
| Scope 1, 2, and 3 emissions | SCI components decompose into scopes (see Section 4) |

Because the SCI produces a *rate-based* metric, organizations can set intensity reduction targets (e.g., "reduce SCI by 20% per API request by 2028") that are meaningful regardless of business growth --- directly addressing the concern that absolute emissions targets may be unrealistic for rapidly growing technology companies.

### 5.2 Risk Management and Strategy Pillars

The SCI's data contributes to both risk identification and strategic planning:

| Risk Type | SCI Data Contribution |
| :--- | :--- |
| **Transition risk: Policy and legal** | Software-system-level emissions documentation enables rapid response to evolving regulatory requirements |
| **Transition risk: Technology** | The energy component (E) quantifies efficiency improvements from technology transitions (e.g., GPU migration, algorithm optimization) |
| **Transition risk: Market** | SCI tracking enables benchmarking against industry peers, identifying competitive exposure |
| **Physical risk: Acute and chronic** | The carbon intensity component (I) uses location-specific grid data, revealing exposure to grid decarbonization trajectories and extreme weather impacts |

The SCI's geographic granularity is particularly valuable: a company operating across multiple cloud regions can use regional carbon intensity data to quantify exposure to different grid decarbonization pathways and identify regions where grid instability poses operational risk. For scenario analysis, companies can model how different grid decarbonization scenarios (e.g., IEA Net Zero, Stated Policies) would affect SCI scores across their infrastructure.

### 5.3 Governance Pillar

While the SCI does not directly address governance structures, implementing SCI calculations across a software portfolio requires organizational infrastructure --- measurement systems, data collection processes, cross-functional ownership --- that naturally strengthens climate governance capabilities.

---

## 6. Synergy Analysis

### 6.1 Strong Synergies

**Scope 3 data granularity.** SB 253's Scope 3 requirement is the single most challenging obligation for technology companies. The GHG Protocol's Scope 3 categories are broad and conceptually defined; translating them into measurable, auditable figures for software systems requires a purpose-built methodology. The SCI provides exactly this. Its decomposition of software emissions into E (energy), I (carbon intensity), and M (embodied) creates a structured data trail that maps to Scope 3 Categories 1, 2, 3, and 11.

**Anti-greenwashing discipline.** The SCI's prohibition on market-based measures (offsets, RECs, PPAs) means that SCI scores reflect actual emissions, not purchased reductions. This aligns with the regulatory intent of both SB 253 and SB 261 --- and with California's broader anti-greenwashing framework (AB 1305). A company that has been calculating SCI scores is inherently better prepared for the scrutiny that third-party assurance and public disclosure invite.

**Assurance readiness.** SB 253 requires limited assurance for Scope 1 and 2 from 2026 and reasonable assurance from 2030. The SCI's mandatory disclosure requirements --- software boundary definitions, functional unit justification, quantification methodology documentation, data source identification, assumptions, and limitations --- produce exactly the structured, transparent documentation that auditors need to perform assurance engagements. Companies that have been through the GSF Self-Certification process will have a significant head start.

**AI emissions quantification.** AI workloads are the fastest-growing source of technology-sector emissions. The IEA estimates that data center electricity consumption will more than double between 2022 and 2026, driven largely by AI training and inference. The SCI for AI specification addresses this directly with its Provider/Consumer scoring model, training amortization methodology, and coverage of agentic AI composite operations. Neither the GHG Protocol nor TCFD guidance provides comparable specificity for AI workloads. For technology companies required to report Scope 3 emissions from AI infrastructure, the SCI for AI is currently the most rigorous available methodology.

### 6.2 Moderate Synergies

**Location-based accounting alignment.** The SCI's mandatory location-based carbon intensity directly satisfies SB 253's primary accounting requirement. However, many companies also report market-based figures, and some frameworks may require dual reporting. The SCI provides the location-based foundation but does not replace market-based analysis where needed.

**Risk scenario modeling.** SCI calculations with location-specific grid carbon intensity data can support the scenario analysis that SB 261's Strategy pillar requires. However, the SCI is a measurement tool, not a scenario modeling framework --- additional tools and assumptions are needed to produce full TCFD-compliant scenario analysis.

**Supply chain data quality.** The SCI's embodied emissions component (M) requires companies to identify hardware lifecycle assessment data, expected lifespans, and resource allocation shares. This data collection discipline improves the quality of Scope 3 upstream emissions reporting. However, the SCI focuses on hardware directly used by the software system; it does not cover all upstream supply chain emissions (e.g., professional services, travel, office supplies).

### 6.3 Gaps and Limitations

**Absolute vs. intensity metrics.** SB 253 fundamentally requires absolute emissions totals. While SCI intensity scores can be converted to absolute figures by multiplying by total functional units, this conversion requires accurate usage data that the SCI specification does not mandate. Companies must independently track total usage volumes.

**Sector-agnostic law, sector-specific tool.** SB 253 and SB 261 apply to all companies above their revenue thresholds, regardless of industry. The SCI is specific to software systems. A technology company's total emissions include non-software sources (office buildings, employee commuting, business travel) that the SCI does not address. The SCI covers the *software-related portion* of emissions --- often the majority for pure-play tech companies, but not the entirety.

**Litigation uncertainty.** SB 261 enforcement is stayed pending the Ninth Circuit's resolution. The January 2026 oral arguments revealed significant judicial skepticism about Scope 3 requirements under SB 253. If the court limits or delays Scope 3 reporting, the urgency of one of the SCI's strongest value propositions would diminish --- though the underlying business case for measuring software emissions would remain.

**Embodied emissions data availability.** The SCI requires hardware lifecycle assessment data for its embodied emissions component (M), but this data is often unavailable, inconsistent, or based on generic estimates. Cloud providers are gradually improving transparency, but proprietary hardware LCA data remains a significant data quality challenge.

---

## 7. Global Regulatory Context

### 7.1 Comparison of Major Climate Disclosure Regimes

|  | CA SB 253 | CA SB 261 | EU CSRD |
| :--- | :--- | :--- | :--- |
| **Status** | Enforceable; first deadline Aug 2026 | Enforcement stayed (Ninth Circuit injunction) | Phased implementation 2024-2029 |
| **Scope** | Scopes 1, 2, 3 (GHG Protocol) | TCFD four pillars | ESRS E1: Scopes 1, 2, 3; double materiality |
| **Revenue threshold** | $1B globally | $500M globally | EU size criteria (varies by phase) |
| **Assurance** | Limited (2026), reasonable (2030) | None specified | Limited (phased), reasonable (future) |
| **Intensity metrics** | Required alongside absolute | Implied by TCFD Metrics & Targets | ESRS requires intensity ratios |
| **Private companies** | Yes (if threshold met) | Yes (if threshold met) | Yes (large private per size criteria) |
| **SCI relevance** | High (Scope 3 data, intensity metrics) | High (TCFD metrics, risk data) | High (ESRS E1, digital sector) |

The UK Sustainability Disclosure Requirements (FCA-regulated entities) and the SEC Climate Rule (largely stayed/vacated) are also relevant but at earlier stages of development or enforcement.

### 7.2 Convergence Trends

Several trends create additional urgency for standardized software emissions measurement:

**ISSB as a global baseline.** The IFRS S1 and S2 sustainability disclosure standards are being adopted as baseline requirements across jurisdictions. SB 261 explicitly accepts IFRS S2 as an alternative to TCFD. The ISSB standards reference GHG Protocol scopes, creating consistency with SB 253.

**Digital sector focus.** The EU's CSRD includes sector-specific standards under development, with digital and technology companies likely to face tailored disclosure requirements. The European Green Digital Coalition and the EU Energy Efficiency Directive's data center provisions signal regulatory convergence toward mandatory software-level emissions measurement.

**Multinational compliance efficiency.** A technology company headquartered in California with EU operations faces SB 253, SB 261, and CSRD simultaneously. Adopting a standardized methodology like the SCI enables data collection once and reporting across multiple frameworks --- avoiding the cost and inconsistency of jurisdiction-specific approaches. SCI calculations produce component-level data (E, I, M, R) that can be reaggregated for different regimes, while a single ISO-standardized methodology prevents the disclosure inconsistencies that create regulatory and reputational risk.

---

## 8. Implications for California Technology Companies

### 8.1 Practical Compliance Roadmap Using SCI

**Phase 1: Inventory and prioritize (Q1-Q2 2026)**

- Identify all software systems within the organizational boundary
- Classify by emissions materiality (data center workloads, cloud services, client-side applications)
- Prioritize top-10 systems by estimated emissions contribution
- Begin SCI calculations for Scope 1 and 2 dominant systems (supporting the August 10, 2026 deadline)

**Phase 2: Scope 3 preparation (Q3-Q4 2026)**

- Extend SCI calculations to cloud-hosted services (cloud provider energy = Scope 3 Cat 1)
- Begin embodied emissions data collection from hardware vendors and cloud providers
- Calculate SCI for AI workloads using the SCI for AI Provider and Consumer scoring models
- Establish baseline SCI scores for reduction target-setting

**Phase 3: Full Scope 3 reporting (2027)**

- Complete SCI calculations across the software portfolio
- Aggregate SCI data into GHG Protocol Scope 3 categories
- Convert SCI intensity metrics to absolute emissions using total usage data
- Prepare for limited assurance readiness (documentation, data trails, third-party access)

**Phase 4: Assurance and optimization (2028-2030)**

- Engage third-party assurance providers for the Scope 1 and 2 limited-to-reasonable assurance transition
- Pursue GSF Self-Certification for public disclosure and credibility
- Implement continuous SCI monitoring and reduction programs
- Prepare for Scope 3 limited assurance requirements beginning 2030

### 8.2 The Safe Harbor Window

SB 253's Scope 3 safe harbor (2027-2030) creates a strategic opportunity. Companies that begin SCI calculations now --- even with imperfect data and estimated embodied emissions --- are protected from penalties for misstatements if they act "with a reasonable basis and disclosed in good faith." This window allows companies to learn by doing with best-available data, improve methodology with each annual cycle, build the institutional processes needed for reasonable assurance by 2030, and establish foundational baselines for reduction targets.

The SCI's structured methodology --- with its mandatory disclosure of assumptions, limitations, and data sources --- is ideally suited for good-faith safe-harbor reporting because it makes the basis of the calculation transparent and auditable.

---

## 9. Recommendations

### 9.1 For Technology Companies

1. **Begin SCI calculations now.** Do not wait for the August 2026 deadline. Start with your largest software systems and expand. The first calculation is the hardest; subsequent iterations improve rapidly.

2. **Prioritize AI workloads.** AI training and inference are the fastest-growing and least-documented sources of technology emissions. Adopt the SCI for AI specification's Provider/Consumer model to create structured, defensible AI emissions data.

3. **Use the safe harbor strategically.** File Scope 3 disclosures beginning 2027 with current best-available data. The SCI's mandatory transparency about assumptions and limitations is your strongest evidence of good faith.

4. **Pursue GSF Self-Certification.** The documentation discipline and public disclosure create audit-ready materials and demonstrate proactive compliance posture to regulators and investors.

5. **Adopt the IMP format.** Machine-readable SCI calculations enable automated aggregation, CI/CD integration, and efficient multi-jurisdictional reporting (California, EU CSRD, ISSB).

6. **Track both intensity and absolute.** SCI gives you intensity by design. Ensure you also track total functional units to compute the absolute emissions that SB 253 requires.

### 9.2 For Investors and Financial Institutions

1. **Request SCI scores from portfolio companies.** SCI calculations provide more decision-useful data than broad corporate carbon estimates. They enable comparison within technology categories and track genuine efficiency improvements.

2. **Assess compliance readiness.** Companies with GSF Self-Certification demonstrate methodological rigor and documentation discipline that signal readiness for SB 253 assurance requirements.

### 9.3 For Regulators and the Green Software Foundation

1. **Recognize ISO/IEC 21031:2024 as a methodology for software emissions.** CARB's rulemaking for SB 253 should acknowledge sector-specific methodologies that produce GHG Protocol-compatible data.

2. **Develop explicit SB 253 mapping guidance.** The GSF should publish supplementary guidance walking through the conversion from SCI components to GHG Protocol Scope 3 categories, with worked examples.

3. **Accelerate SCI for Web.** California's technology companies include the world's largest web platform operators. A ratified SCI for Web specification would significantly expand the SCI's compliance utility.

4. **Build assurance-provider partnerships.** Work with the audit firms who will be verifying SB 253 disclosures to ensure they understand the SCI methodology and can assess SCI-based submissions.

---

## 10. Conclusions

California's SB 253 and SB 261 create binding disclosure obligations that demand rigorous, auditable approaches to carbon accounting --- precisely the kind of discipline that software emissions have historically lacked. The SCI framework, as an ISO-standardized, component-level methodology purpose-built for software systems, addresses this gap with strong alignment across multiple dimensions.

The strongest synergies lie in Scope 3 data granularity and TCFD Metrics & Targets compliance. The SCI's decomposition of emissions into energy, carbon intensity, and embodied components creates a structured, auditable data trail that maps directly to the GHG Protocol categories most material to technology companies. Its intensity metrics, mandatory location-based accounting, and documentation requirements produce exactly the kind of evidence that third-party assurance providers and regulators need.

The gaps are real but manageable. The SCI produces intensity metrics rather than the absolute figures SB 253 requires --- but the conversion is straightforward given total usage data. The SCI covers software-related emissions only --- but for technology companies, this is typically the majority of their footprint. Litigation uncertainty may delay Scope 3 requirements --- but the underlying measurement capability remains valuable regardless.

For technology companies navigating this new landscape, the strategic calculus is clear: adopting the SCI framework generates data that feeds directly into regulatory compliance, imposes discipline that prepares organizations for third-party assurance, and positions early adopters to meet the converging demands of California, the EU CSRD, and emerging global standards. With the August 2026 deadline approaching and the Scope 3 safe harbor opening in 2027, the window for building this capability is now.

---

## 11. Sources

### California Legislation and Regulatory Materials

- California Senate Bill 253 (2023): Climate Corporate Data Accountability Act. [https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240SB253](https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240SB253)
- California Senate Bill 261 (2023): Greenhouse Gases: Climate-Related Financial Risk. [https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240SB261](https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240SB261)
- California Senate Bill 219 (2024): Amendments to SB 253 and SB 261. [https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240SB219](https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240SB219)
- California Assembly Bill 154 (2025): Climate Accountability and Emissions Disclosure Fund. [https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202520260AB154](https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202520260AB154)
- CARB: California Corporate GHG Reporting Programs. [https://ww2.arb.ca.gov/our-work/programs/california-corporate-greenhouse-gas-ghg-reporting-and-climate-related-financial](https://ww2.arb.ca.gov/our-work/programs/california-corporate-greenhouse-gas-ghg-reporting-and-climate-related-financial)
- CARB Enforcement Advisory (December 2024): Good-faith compliance guidance for SB 253.

### Litigation

- *Chamber of Commerce of the United States of America et al. v. California Air Resources Board*, No. 2:24-cv-00801 (E.D. Cal.).
- *ExxonMobil Corporation v. California Air Resources Board*, No. 2:25-cv-02548 (E.D. Cal.).
- Cooley LLP, "California's SB 253 and SB 261: Developments and Litigation" (January 26, 2026). [https://www.cooley.com/news/insight/2026/2026-01-26-californias-sb-253-and-sb-261-developments-and-litigation](https://www.cooley.com/news/insight/2026/2026-01-26-californias-sb-253-and-sb-261-developments-and-litigation)
- Jones Day, "Ninth Circuit Enjoins SB 261, Declines to Enjoin SB 253" (November 2025). [https://www.jonesday.com/en/insights/2025/11/ninth-circuit-enjoins-sb-261s-climaterelated-risk-reporting-requirements-declines-to-enjoin-sb-253](https://www.jonesday.com/en/insights/2025/11/ninth-circuit-enjoins-sb-261s-climaterelated-risk-reporting-requirements-declines-to-enjoin-sb-253)
- Harvard Law School Forum on Corporate Governance, "SB 261 Injunction Analysis" (December 3, 2025). [https://corpgov.law.harvard.edu/2025/12/03/california-climate-disclosure-law-sb-261-implementation-halted-ninth-circuit-grants-injunction-pending-appeal/](https://corpgov.law.harvard.edu/2025/12/03/california-climate-disclosure-law-sb-261-implementation-halted-ninth-circuit-grants-injunction-pending-appeal/)
- Akin Gump, "Ninth Circuit Oral Argument Recap" (January 2026). [https://www.akingump.com/en/insights/blogs/speaking-sustainability/whats-next-for-sb-253-and-sb-261-ninth-circuit-oral-argument-recap](https://www.akingump.com/en/insights/blogs/speaking-sustainability/whats-next-for-sb-253-and-sb-261-ninth-circuit-oral-argument-recap)

### GSF and SCI Standards

- ISO/IEC 21031:2024: Information technology --- Software carbon intensity (SCI) specification. [https://www.iso.org/standard/86612.html](https://www.iso.org/standard/86612.html)
- Green Software Foundation, SCI Specification v1.1.0. [https://sci.greensoftware.foundation/](https://sci.greensoftware.foundation/)
- Green Software Foundation, SCI for AI Specification (ratified December 2025). [https://sci-for-ai.greensoftware.foundation/](https://sci-for-ai.greensoftware.foundation/)
- Green Software Foundation, SCI for AI GitHub Repository. [https://github.com/Green-Software-Foundation/sci-ai](https://github.com/Green-Software-Foundation/sci-ai)
- Green Software Foundation, Impact Framework. [https://if.greensoftware.foundation/](https://if.greensoftware.foundation/)
- Green Software Foundation, "Establishing Software Carbon Transparency: Why We're Exploring SCI Disclosure Certification." [https://greensoftware.foundation/articles/establishing-software-carbon-transparency-why-we-re-exploring-sci-disclosure-cert/](https://greensoftware.foundation/articles/establishing-software-carbon-transparency-why-we-re-exploring-sci-disclosure-cert/)
- Green Software Foundation and W3C Collaboration Announcement. [https://greensoftware.foundation/articles/the-green-software-foundation-and-world-wide-web-consortium-w3c-collaborate-to-ad/](https://greensoftware.foundation/articles/the-green-software-foundation-and-world-wide-web-consortium-w3c-collaborate-to-ad/)

### W3C Web Sustainability

- W3C Web Sustainability Guidelines (WSG). [https://www.w3.org/TR/web-sustainability-guidelines/](https://www.w3.org/TR/web-sustainability-guidelines/)
- W3C Sustainable Web Interest Group. [https://www.w3.org/groups/ig/sustainableweb/](https://www.w3.org/groups/ig/sustainableweb/)

### GHG Protocol and TCFD

- GHG Protocol Corporate Accounting and Reporting Standard. [https://ghgprotocol.org/corporate-standard](https://ghgprotocol.org/corporate-standard)
- GHG Protocol Corporate Value Chain (Scope 3) Accounting and Reporting Standard. [https://ghgprotocol.org/standards/scope-3-standard](https://ghgprotocol.org/standards/scope-3-standard)
- TCFD Recommendations of the Task Force on Climate-related Financial Disclosures (2017). [https://www.fsb-tcfd.org/recommendations/](https://www.fsb-tcfd.org/recommendations/)

### Regulatory Analyses and Guides

- KPMG, "All About California's Climate Laws" (2025). [https://kpmg.com/us/en/frv/reference-library/2025/california-climate-laws.html](https://kpmg.com/us/en/frv/reference-library/2025/california-climate-laws.html)
- Deloitte, "California Climate Legislation Update" (December 2025). [https://dart.deloitte.com/USDART/home/publications/deloitte/sustainability-spotlight/2025/california-climate-legislation-reporting-updates-2026](https://dart.deloitte.com/USDART/home/publications/deloitte/sustainability-spotlight/2025/california-climate-legislation-reporting-updates-2026)
- Mayer Brown, "Countdown to Disclosure" (October 2025). [https://www.mayerbrown.com/en/insights/publications/2025/10/california-climate-disclosure-laws--countdown-to-disclosure-what-companies-need-to-know-about-reporting-deadlines-carb-guidance-and-ongoing-litigation](https://www.mayerbrown.com/en/insights/publications/2025/10/california-climate-disclosure-laws--countdown-to-disclosure-what-companies-need-to-know-about-reporting-deadlines-carb-guidance-and-ongoing-litigation)
- Katten, "SB 219 Makes Important Updates to California Climate Disclosure Regime." [https://katten.com/sb-219-makes-important-updates-to-california-climate-disclosure-regime](https://katten.com/sb-219-makes-important-updates-to-california-climate-disclosure-regime)
- Watershed, "Guide to California's Climate Disclosure Rules." [https://watershed.com/blog/california-disclosures-a-guide-for-companies](https://watershed.com/blog/california-disclosures-a-guide-for-companies)

### Technology Sector Emissions Research

- The Guardian, "Revealed: Top Carbon Polluters Vastly Undercount Emissions" (2024).
- Google Environmental Report (2024): Emissions increase attributed to AI data center growth.
- Microsoft Sustainability Report (2024): 29% Scope 3 emissions increase.
- IEA, "Electricity 2024" --- Data centre energy consumption projections. [https://www.iea.org/reports/electricity-2024](https://www.iea.org/reports/electricity-2024)

### ISO Standards

- ISO/IEC 21031:2024: Software Carbon Intensity. [https://www.iso.org/standard/86612.html](https://www.iso.org/standard/86612.html)
- ISO/IEC 17050-1:2004: Conformity assessment --- Supplier's declaration of conformity.
- NTT DATA, "Development of a New International Standard Called Software Carbon Intensity" (May 2024). [https://www.nttdata.com/global/en/news/press-release/2024/may/the-development-of-a-new-international-standard-called-software-carbon-intensity](https://www.nttdata.com/global/en/news/press-release/2024/may/the-development-of-a-new-international-standard-called-software-carbon-intensity)

---

**Document Version**: 1.1 **Last Updated**: 2026-03 **Maintained By**: GSF Policy Working Group

# Cloud Region Metadata and the EU Cloud and AI Development Act: A Framework for Standardised Environmental Reporting

**Subtitle:** How the Green Software Foundation's Cloud Region Metadata Specification Supports CADA Reporting Obligations and the Data Centre Energy Efficiency Package

---

| Field | Value |
| :---- | :---- |
| **Version** | 1.2 — Updated Working Draft |
| **Date** | March 2026 |
| **Author** | GSF Standards Working Group |
| **Status** | Working Draft |
| **Specification Referenced** | Cloud Region Metadata Specification (Real-Time Cloud Project) |
| **Policy Referenced** | EU Cloud and AI Development Act (CADA); EU Data Centre Energy Efficiency Package; Energy Efficiency Directive 2024/1791 |

---

## Abstract

Europe's expanding data centre sector faces a paradox: demand for cloud compute is accelerating — driven largely by AI — at precisely the moment that regulatory expectations for environmental transparency are tightening. The European Commission's forthcoming Cloud and AI Development Act (CADA) and its accompanying Data Centre Energy Efficiency Package, both planned for Q1–Q2 2026, will introduce minimum performance standards, a pan-European rating scheme, and enhanced reporting obligations for data centres operating across the EU. These measures build directly on the Energy Efficiency Directive (EED), which since 2024 has required large data centres to submit detailed operational and environmental metrics to a central European database.

A critical gap stands in the way of effective implementation: the absence of a consistent, multi-provider, region-level environmental dataset that policymakers, cloud customers, and regulators can use as a shared reference. Cloud providers publish sustainability data using different methodologies, at different granularities, and on different timescales. Without a common framework, the comparisons that CADA's performance standards depend upon are difficult, or impossible, to make with integrity.

The Green Software Foundation's Cloud Region Metadata specification — developed under the Real-Time Cloud project — directly addresses this gap. Crucially, it bridges the divide between the EED's static, annual reporting baseline and the high-resolution transparency CADA requires. The specification establishes a unified schema for cloud region-level environmental data, including energy efficiency metrics (PUE and WUE), carbon intensity at both location-based and market-based levels, and pathways for carbon-free energy proportions at hourly and annual granularity. It supports both regulatory compliance reporting and real-time carbon-aware computing applications.

This paper argues that the Cloud Region Metadata specification is well-positioned to serve as the open, consensus-built data infrastructure that CADA's reporting framework needs. It maps the specification's framework directly to EED and CADA requirements, identifies where the specification goes beyond current obligations to demonstrate what higher-resolution data already looks like in practice, and makes a series of concrete recommendations for how the European Commission and the GSF Policy Working Group can work together to embed this standard in the legislative framework.

---

## Table of Contents

1. [Context and Problem Statement](#1-context-and-problem-statement)  
2. [Evidence and Technical Analysis](#2-evidence-and-technical-analysis)  
3. [Policy Implications and Regulatory Mapping](#3-policy-implications-and-regulatory-mapping)  
4. [Barriers, Limitations, and Counter-Arguments](#4-barriers-limitations-and-counter-arguments)  
5. [Recommendations](#5-recommendations)  
6. [Conclusions](#6-conclusions)  
7. [Sources](#7-sources)

---

## 1\. Context and Problem Statement

### 1.1 The Data Centre Energy Imperative

Data centres are among the fastest-growing energy consumers in Europe. The International Energy Agency estimates that global data centre electricity consumption stands at approximately 415 TWh per year and projects that this figure will more than double to around 945 TWh by 2030, driven primarily by the rapid growth of energy-intensive AI workloads. Within the EU, electricity consumption by data centres is expected to be 30 per cent higher in 2026 than it was in 2023, as new AI-focused facilities come online across the bloc.

This growth puts direct pressure on Europe's decarbonisation commitments. The EU has legally binding emissions reduction targets under the European Climate Law, and the Green Deal has established a political goal for European data centres to be climate-neutral and energy-efficient by 2030\. The tension between rapidly expanding computational capacity and climate commitments is the defining challenge that the CADA and the Data Centre Energy Efficiency Package are designed to address.

The geographic concentration of data centres adds further complexity. Capacity is heavily concentrated in North-West Europe. Ireland's data centres now account for approximately 22 per cent of national electricity supply. This concentration means that the environmental impacts of cloud workloads are spatially uneven, and the carbon intensity of a given cloud region is highly dependent on where its data centres sit and what electricity mix feeds them.

### 1.2 The Regulatory Landscape

The EU's regulatory response to data centre energy use has developed in layers:

**Energy Efficiency Directive (EED) 2024/1791.** The recast EED, which entered into force in 2024, establishes the foundational reporting framework. Facilities with an installed IT power demand of at least 500 kW are required to submit detailed operational metrics annually to a central European database managed by the European Commission. Mandatory reporting fields include total IT energy consumption, PUE, WUE, energy reuse factor, and renewable energy sourcing.

**Data Centre Energy Efficiency Package (Q1–Q2 2026).** Acting on the EED's assessment mandate, the Commission is preparing a dedicated package to be published alongside CADA. This package is expected to introduce a pan-European rating scheme for data centres and launch formal work on minimum performance standards.

**Cloud and AI Development Act (CADA).** CADA's efficiency pillar is expected to link permitting and public support for new data centres to demonstrable compliance with sustainability criteria — including energy efficiency, water use, and renewable energy sourcing. The Act is planned for April 2026\.

**EU AI Act.** Regulation (EU) 2024/1689 imposes transparency requirements on providers of General-Purpose AI models with systemic risk, including reporting of energy consumption. Energy consumption is a factor that can trigger classification as a systemic-risk model, creating a direct incentive for providers to document and minimise cloud workload carbon intensity.

### 1.3 The Data Problem and the Call for Consistency

Despite the EED's reporting requirements, a fundamental data problem persists: cloud providers do not report environmental performance data in a consistent way.

Providers currently publish efficiency and carbon data using different methodologies, different geographic granularities, and on different timescales. Power Usage Effectiveness is reported on different schedules, and Water Usage Effectiveness data is similarly fragmented.

This inconsistency poses a major risk to upcoming legislation, a fact not lost on industry leaders. Major stakeholders, including Google and Deutsche Telekom, have specifically asked the European Commission to maintain strict consistency with the Energy Efficiency Directive when developing CADA. Because the EED already comprises heavy data centre monitoring and reporting obligations, introducing a divergent set of requirements under CADA would result in administrative gridlock.

If policymakers cannot compare the environmental performance of data centres run by different providers using a unified methodology, they cannot set meaningful minimum performance standards or verify that CADA's sustainability conditions are being met.

---

## 2\. Evidence and Technical Analysis

### 2.1 The Cloud Region Metadata Specification

The Green Software Foundation's Cloud Region Metadata specification, developed under the Real-Time Cloud project, was designed precisely to address this data fragmentation. It establishes a unified data schema that enables cloud providers to publish standardised carbon and energy metadata at the cloud region level.

The project is grounded in the recognition that *"all models are wrong, some models are useful."* It aims to make cloud carbon models significantly less wrong through methodological standardisation, and more useful by having the same metadata schema for all cloud providers.

The specification envisions tiered conformance levels, guiding providers from basic mandatory reporting (PUE, annual location-based grid carbon intensity) toward advanced real-time API integration and full EED-aligned energy reporting fields.

### 2.2 What the Specification Measures

The specification's schema covers categories of measurement with direct relevance to CADA and EED requirements:

**Energy efficiency metrics.** PUE and WUE frameworks standardise formulas and reporting frequencies that are currently inconsistent across providers.

**Carbon intensity.** The schema tracks multiple carbon intensity measures, including location-based grid intensity (`grid-carbon-intensity`) and hourly-weighted consumption profiles (`provider-carbon-intensity-average-consumption-hourly`).

**EED-aligned targets.** The Real-Time Cloud project's trajectory naturally supports specific EED reporting requirements (total IT energy consumption, total water input, and distinct renewable energy sourcing like PPAs and Guarantees of Origin). Integrating these exact fields into the metadata schema ensures it acts as the ideal "bridge" framework to satisfy industry demands for regulatory consistency.

### 2.3 Beyond the EED: Hourly Resolution and Carbon-Aware Computing

The specification's most distinctive contribution relative to the current EED framework is its focus on hourly granularity. The EED collects annual averages; the specification champions hourly-weighted carbon intensity data and integration paths to real-time APIs.

This matters for two reasons. First, the carbon intensity of a power grid varies significantly across hours. A data centre reporting 100% renewable energy annually might still draw heavily from fossil fuels at night. Hourly tracking is increasingly recognised as the appropriate standard for genuine decarbonisation claims.

Second, higher temporal resolution enables *carbon-aware computing* — the practice of scheduling flexible workloads to run when and where the grid carbon intensity is lowest.

---

## 3\. Policy Implications and Regulatory Mapping

### 3.1 CADA and the Data Centre Energy Efficiency Package

CADA's efficiency pillar is expected to condition fast-track permitting and public support on demonstrated sustainability compliance. The practical challenge for regulators is: *measured against what?*

The EED has provided a baseline dataset, but it is a confidential reporting mechanism. It does not provide the public, provider-level dataset that CADA's transparency ambitions require. The Cloud Region Metadata framework provides exactly this schema.

### 3.2 Mapping the Specification to CADA Reporting Pillars

Based on the Commission's call for evidence, CADA's sustainability requirements map neatly to the specification's capabilities:

| CADA Sustainability Pillar | Specification Capability | Notes |
| :---- | :---- | :---- |
| **Energy efficiency** | `power-usage-effectiveness` | Standardises formulas and reporting frequency |
| **Carbon intensity transparency** | `grid-carbon-intensity` | Location-based grid intensity |
| **Carbon-free energy matching** | `provider-carbon-intensity-average-consumption-hourly` | Demonstrates the viability of hourly-weighted tracking |

### 3.3 The Specification as Evidence for Minimum Performance Standards

One of CADA's most significant provisions is the mandate to establish minimum performance standards for EU data centres.

This is where the Real-Time Cloud project is most transformative. It provides empirical evidence that moving beyond annual averages is technically viable. **This strongly supports the argument that granular, time-aware tracking should be a *standard expectation* in any minimum performance framework, rather than an optional aspiration.**

When the Commission considers whether higher-resolution reporting should be required, the specification demonstrates that this granularity of measurement is not just theoretically achievable, but practically standardisable.

### 3.4 Relationship to the EU AI Act

The EU AI Act imposes energy consumption transparency requirements on providers of General-Purpose AI models. A GPAI model provider selecting a cloud region for training workloads can use the specification's data to make carbon-aware placement decisions — and document those decisions for regulatory purposes.

---

## 4\. Barriers, Limitations, and Counter-Arguments

### 4.1 Data Gaps and Provider Inconsistency

The specification's value depends on voluntary provider cooperation. If CADA were to mandate EED-aligned disclosure in a public format — citing the GSF's schema as the recommended format — this dependency would be substantially reduced.

### 4.2 The Scope 1 / Colocation Problem

The current model largely assumes that cloud region power is sourced from the electricity grid (Scope 2). This assumption is increasingly incomplete. Several cloud regions operate gas-powered generation capacity on-site (e.g., the North Europe region in West Dublin, Ireland). This Scope 1 generation is notoriously difficult to capture via APIs, an omission regulators must carefully consider.

### 4.3 Model Simplification vs. Regulatory Precision

The specification makes necessary simplifications to be widely adoptable. Regulators need to be careful about which metrics in the dataset are appropriate as hard regulatory thresholds and which are better understood as directional indicators.

### 4.4 Legal Status and Jurisdictional Scope

The specification is an open standard produced by a non-governmental body; it has no formal legal status in the EU regulatory system. However, established regulatory precedent exists for incorporating industry standards by reference (e.g., ISO 14064, GHG Protocol).

---

## 5\. Recommendations

Based on the analysis above, the GSF Policy Working Group makes the following recommendations:

**Recommendation 1: Reference the Cloud Region Metadata schema in CADA's implementing regulations as a recognised disclosure format.** This satisfies the industry (Google/DT) demand for EED consistency by mapping public disclosures directly to established frameworks.

**Recommendation 2: Require public disclosure of EED-mandated fields in machine-readable format.** The EED database is confidential; CADA should require a public version of this data, leveraging the GSF schema to prevent market fragmentation.

**Recommendation 3: Adopt high-resolution tracking as the reference standard in CADA's rating scheme.** The rating scheme should recognise hourly-weighted tracking as a standard expectation for high performance, moving away from the inadequacy of annual averages.

**Recommendation 4: Require disclosure of Scope 1 emissions from on-site generation.** CADA's framework must close the accountability gap surrounding on-site gas generation and behind-the-meter power.

**Recommendation 5: Engage the Green Software Foundation in CADA's minimum performance standards development process.** The Commission should leverage the Real-Time Cloud insights as an empirical baseline for setting realistic thresholds.

---

## 6\. Conclusions

The EU Cloud and AI Development Act and the Data Centre Energy Efficiency Package represent the most significant regulatory development in European data centre environmental accountability in a generation.

The core challenge facing these frameworks is bridging the gap between the EED's confidential, annual baseline and CADA's need for public, actionable data. Industry stakeholders have clearly signaled that this must be done without creating conflicting reporting methodologies.

The Cloud Region Metadata specification provides the solution. It is a unifying schema that completely aligns with regulatory transparency goals while proving that advanced metrics — like hourly-weighted intensity tracking — are achievable today. By leveraging this open standard, the European Commission can set rigorous, evidence-based performance expectations that drive genuine decarbonisation in the AI era.

---

## 7\. Sources

- Green Software Foundation. *Cloud Region Metadata Specification.* Green Software Foundation Real-Time Cloud Project.  
- European Parliament and Council of the EU. *Energy Efficiency Directive (EED) 2024/1791.* \- European Commission. *Cloud and AI Development Act (CADA).* Commission Work Programme 2026\.  
- Regulation (EU) 2024/1689. *EU AI Act.*  
- World Resources Institute. *GHG Protocol Scope 2 Guidance.*  
- ISO/IEC 21031:2024. *Software Carbon Intensity (SCI) Specification.*


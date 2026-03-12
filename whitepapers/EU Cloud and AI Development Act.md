# Cloud Region Metadata and the EU Cloud and AI Development Act: A Framework for Standardised Environmental Reporting

**Subtitle:** How the Green Software Foundation's Cloud Region Metadata Specification Bridges the Gap Between EED Reporting Obligations and CADA Performance Standards

---

| Field | Value |
|---|---|
| **Version** | 1.1 — Updated Working Draft |
| **Date** | March 2026 |
| **Author** | GSF Policy Working Group |
| **Status** | Working Draft for Commission Review |
| **Specification Referenced** | Cloud Region Metadata Specification v1.1.0 |
| **Policy Referenced** | EU Cloud and AI Development Act (CADA); EU Data Centre Energy Efficiency Package; Energy Efficiency Directive 2024/1791 |

---

## Abstract

Europe's expanding data centre sector faces a paradox: demand for cloud compute is accelerating—driven largely by AI—at precisely the moment that regulatory expectations for environmental transparency are tightening. The European Commission's forthcoming Cloud and AI Development Act (CADA) and its accompanying Data Centre Energy Efficiency Package, both planned for adoption in April 2026, will introduce minimum performance standards, a pan-European rating scheme, and enhanced reporting obligations. These measures build directly on the Energy Efficiency Directive (EED), which since 2024 has required large data centres to submit operational metrics to a central database.

However, a critical gap stands in the way of effective implementation: the absence of a consistent, multi-provider, region-level environmental dataset. Industry stakeholders, including **Google** and **Deutsche Telekom**, have strongly urged the European Commission to maintain consistency with the EED when developing CADA to avoid administrative double-counting. 

The Green Software Foundation's Cloud Region Metadata specification—developed under the Real-Time Cloud project (version 1.1)—effectively bridges this gap. It goes further than the EED's annual reporting baseline by demonstrating what higher-resolution, hourly data looks like in practice. This paper argues that the specification provides the exact evidence regulators need to make hourly carbon matching a standard expectation in any minimum performance framework, serving as the open, consensus-built data infrastructure required for CADA's success.

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

## 1. Context and Problem Statement

### 1.1 The Data Centre Energy Imperative
Data centres are among the fastest-growing energy consumers in Europe. The International Energy Agency estimates that global data centre electricity consumption will more than double to around 945 TWh by 2030. Within the EU, electricity consumption by data centres is expected to be 30 per cent higher in 2026 than it was in 2023. This growth puts direct pressure on Europe's decarbonisation commitments under the European Climate Law. The tension between rapidly expanding AI computational capacity and climate goals is the defining challenge CADA is designed to address.

### 1.2 The Regulatory Landscape
The EU's regulatory response has developed in layers:

* **Energy Efficiency Directive (EED) 2024/1791:** Establishes the foundational reporting framework, requiring facilities over 500 kW to submit annual operational metrics.
* **Data Centre Energy Efficiency Package (April 2026):** Expected to introduce a pan-European rating scheme for data centres and launch formal work on minimum performance standards based on EED data.
* **Cloud and AI Development Act (CADA):** Planned alongside the Energy Efficiency Package, CADA aims to link fast-track permitting and public support for new data centres to demonstrable compliance with sustainability criteria.
* **EU AI Act:** Imposes transparency requirements on providers of General-Purpose AI models, including reporting of energy consumption.

### 1.3 The Data Problem and the Stakeholder Mandate
Despite the EED's requirements, cloud providers do not report environmental performance data consistently. PUE, WUE, and carbon intensity figures are reported using different methodologies and timescales. 

Crucially, major telecommunications and cloud stakeholders, including Google and Deutsche Telekom, have explicitly asked the European Commission to ensure consistency with the EED when developing CADA. If policymakers cannot confidently compare environmental performance across providers without imposing a secondary, conflicting reporting burden, they cannot set equitable performance standards. 

---

## 2. Evidence and Technical Analysis

### 2.1 The Cloud Region Metadata Specification
The GSF's Cloud Region Metadata specification (v1.1.0) was designed to address this fragmentation. It establishes a unified data schema that enables providers to publish standardised carbon and energy metadata at the cloud region level. It defines two conformance levels: Level 1 (Basic annual compliance) and Level 2 (Advanced real-time, hourly compliance).

### 2.2 EED Field Alignment
The specification is deliberately built to mirror EU regulation. It explicitly includes fields such as `total-ICT-energy-consumption-annual`, `power-usage-effectiveness`, `water-usage-effectiveness`, and `renewable-energy-consumption` to perfectly align with EED mandatory reporting requirements.

### 2.3 Beyond the EED: The Bridge to High-Resolution Accountability
The specification's most vital regulatory contribution is its hourly granularity. The EED relies on annual averages—a "low-resolution" look at a high-resolution problem. A data centre reporting 100% renewable energy annually might still draw heavily from fossil fuels during winter nights.

The Real-Time Cloud specification provides hourly-weighted carbon intensity data and integration paths to real-time APIs. It proves that tracking the fluctuating, real-time nature of AI workloads is not just theoretical; it is operational today.

---

## 3. Policy Implications and Regulatory Mapping

### 3.1 CADA and the Data Centre Energy Efficiency Package
CADA will condition fast-track permitting on sustainability compliance, judged against the Data Centre Energy Efficiency Package's rating scheme. The EED database, while helpful, is confidential and aggregated. The Cloud Region Metadata specification provides the public, provider-level, verifiable dataset that CADA’s transparency ambitions require.

### 3.2 Setting the Benchmark: Hourly Matching as a Standard Expectation
One of CADA's most significant provisions is the mandate to establish minimum performance standards. Setting credible thresholds requires empirical evidence. 

The Real-Time Cloud dataset provides exactly this evidence, actively strengthening the case for strict standards. **Hourly carbon matching must become a standard expectation in any minimum performance framework**, rather than an optional aspiration. The specification's region-level hourly data (`provider-cfe-hourly`) proves to regulators that this granularity of measurement is achievable and already in practice by major providers. 

### 3.3 Supporting the EU AI Act
A GPAI model provider selecting a cloud region for training workloads can use the specification's region-level carbon intensity data to make carbon-aware placement decisions. Furthermore, integrating this metadata with the GSF's *Software Carbon Intensity (SCI)* metric creates a complete, compliant methodology for reporting AI workload emissions under the EU AI Act.

---

## 4. Barriers, Limitations, and Counter-Arguments

### 4.1 Data Gaps and Voluntary Disclosure
The specification's value depends on voluntary provider cooperation (e.g., the notable gap in Microsoft Azure's 2024 region-level data). If CADA were to mandate EED-aligned disclosure in a public format—citing the specification's schema as the standard—this vulnerability would be eliminated.

### 4.2 The Scope 1 / Colocation Problem
The current model assumes cloud power is grid-sourced (Scope 2). However, regions using on-site gas generation (e.g., West Dublin, Ireland) introduce Scope 1 emissions invisible to current models. While acknowledged by the working group, regulators must consider addressing Scope 1 disclosures explicitly in CADA.

---

## 5. Recommendations

**Recommendation 1: Adopt the Cloud Region Metadata schema as the official "bridge" to CADA compliance.**
To satisfy stakeholder demands (e.g., Google, Deutsche Telekom) for EED consistency, the Commission should reference the specification as a Recognised Disclosure Format. This ensures public CADA disclosures perfectly map to confidential EED submissions.

**Recommendation 2: Make hourly carbon matching the standard expectation for top-tier ratings.**
The Data Centre Energy Efficiency Package's rating scheme should establish hourly carbon-free energy matching as a baseline expectation for highest-tier performance, using the specification's `provider-cfe-hourly` field as the empirical proof that this is technically feasible today.

**Recommendation 3: Mandate public, machine-readable disclosure of EED metrics.**
CADA should require cloud providers to publish a summary of their EED-mandated metrics in a public, machine-readable format at the region level, utilizing the GSF schema to prevent market fragmentation.

**Recommendation 4: Engage the GSF in the April 2026 performance standard setting.**
The Commission's upcoming work on minimum performance standards would benefit from direct engagement with the GSF Policy Working Group, leveraging the Real-Time Cloud dataset as primary evidence for establishing realistic but ambitious regulatory thresholds.

---

## 6. Conclusions

The EU Cloud and AI Development Act and the Data Centre Energy Efficiency Package represent a generational shift in environmental accountability. However, ambitious policies require actionable data. 

Stakeholders have made it clear: the transition from EED to CADA must be consistent and administratively streamlined. The Cloud Region Metadata specification does exactly this. It serves as the vital bridge between the EED's annual baseline and CADA's high-resolution performance goals, proving that hourly carbon matching is a realistic standard expectation for the future of European compute.

---

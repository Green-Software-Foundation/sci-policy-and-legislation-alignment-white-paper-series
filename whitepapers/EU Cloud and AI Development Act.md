# Cloud Region Metadata and the EU Cloud and AI Development Act: A Framework for Standardised Environmental Reporting

**Subtitle:** How the Green Software Foundation's Cloud Region Metadata Specification Supports CADA Reporting Obligations and the Data Centre Energy Efficiency Package

---

| Field | Value |
|---|---|
| **Version** | 1.0 — Working Draft |
| **Date** | March 2026 |
| **Author** | GSF Standandards Working Group |
| **Status** | Working Draft |
| **Specification Referenced** | Cloud Region Metadata Specification v1.1.0 |
| **Policy Referenced** | EU Cloud and AI Development Act (CADA); EU Data Centre Energy Efficiency Package; Energy Efficiency Directive 2024/1791 |

---

## Abstract

Europe's expanding data centre sector faces a paradox: demand for cloud compute is accelerating — driven largely by AI — at precisely the moment that regulatory expectations for environmental transparency are tightening. The European Commission's forthcoming Cloud and AI Development Act (CADA) and its accompanying Data Centre Energy Efficiency Package, both planned for Q1–Q2 2026, will introduce minimum performance standards, a pan-European rating scheme, and enhanced reporting obligations for data centres operating across the EU. These measures build directly on the Energy Efficiency Directive (EED), which since 2024 has required large data centres to submit detailed operational and environmental metrics to a central European database.

A critical gap stands in the way of effective implementation: the absence of a consistent, multi-provider, region-level environmental dataset that policymakers, cloud customers, and regulators can use as a shared reference. Cloud providers publish sustainability data using different methodologies, at different granularities, and on different timescales. Without a common framework, the comparisons that CADA's performance standards depend upon are difficult, or impossible, to make with integrity.

The Green Software Foundation's Cloud Region Metadata specification — developed under the Real-Time Cloud project — directly addresses this gap. The specification establishes a unified schema for cloud region-level environmental data, including energy efficiency metrics (PUE and WUE), carbon intensity at both location-based and market-based levels, carbon-free energy proportions at hourly and annual granularity, and explicit EED-aligned reporting fields. It supports both regulatory compliance reporting and real-time carbon-aware computing applications. It is already being populated with data from major cloud providers.

This paper argues that the Cloud Region Metadata specification is well-positioned to serve as the open, consensus-built data infrastructure that CADA's reporting framework needs. It maps the specification's fields directly to EED and CADA requirements, identifies where the specification goes beyond current obligations to enable higher-resolution accountability, and makes a series of concrete recommendations for how the European Commission and the GSF Policy Working Group can work together to embed this standard in the legislative framework.

---

## Table of Contents

1. [Context and Problem Statement](#1-context-and-problem-statement)
   - 1.1 [The Data Centre Energy Imperative](#11-the-data-centre-energy-imperative)
   - 1.2 [The Regulatory Landscape](#12-the-regulatory-landscape)
   - 1.3 [The Data Problem](#13-the-data-problem)
2. [Evidence and Technical Analysis](#2-evidence-and-technical-analysis)
   - 2.1 [The Cloud Region Metadata Specification](#21-the-cloud-region-metadata-specification)
   - 2.2 [What the Specification Measures](#22-what-the-specification-measures)
   - 2.3 [EED Field Alignment](#23-eed-field-alignment)
   - 2.4 [Beyond the EED: Hourly Resolution and Carbon-Aware Computing](#24-beyond-the-eed-hourly-resolution-and-carbon-aware-computing)
3. [Policy Implications and Regulatory Mapping](#3-policy-implications-and-regulatory-mapping)
   - 3.1 [CADA and the Data Centre Energy Efficiency Package](#31-cada-and-the-data-centre-energy-efficiency-package)
   - 3.2 [Mapping the Specification to CADA Reporting Pillars](#32-mapping-the-specification-to-cada-reporting-pillars)
   - 3.3 [The Specification as Evidence for Minimum Performance Standards](#33-the-specification-as-evidence-for-minimum-performance-standards)
   - 3.4 [Relationship to the EU AI Act](#34-relationship-to-the-eu-ai-act)
   - 3.5 [Supporting Cloud Customer Scope 2 Reporting](#35-supporting-cloud-customer-scope-2-reporting)
4. [Barriers, Limitations, and Counter-Arguments](#4-barriers-limitations-and-counter-arguments)
   - 4.1 [Data Gaps and Provider Inconsistency](#41-data-gaps-and-provider-inconsistency)
   - 4.2 [The Scope 1 / Colocation Problem](#42-the-scope-1--colocation-problem)
   - 4.3 [Model Simplification vs. Regulatory Precision](#43-model-simplification-vs-regulatory-precision)
   - 4.4 [Legal Status and Jurisdictional Scope](#44-legal-status-and-jurisdictional-scope)
5. [Recommendations](#5-recommendations)
6. [Conclusions](#6-conclusions)
7. [Sources](#7-sources)

---

## 1. Context and Problem Statement

### 1.1 The Data Centre Energy Imperative

Data centres are among the fastest-growing energy consumers in Europe. The International Energy Agency estimates that global data centre electricity consumption stands at approximately 415 TWh per year and projects that this figure will more than double to around 945 TWh by 2030, driven primarily by the rapid growth of energy-intensive AI workloads. Within the EU, electricity consumption by data centres is expected to be 30 per cent higher in 2026 than it was in 2023, as new AI-focused facilities come online across the bloc.

This growth puts direct pressure on Europe's decarbonisation commitments. The EU has legally binding emissions reduction targets under the European Climate Law, and the Green Deal has established a political — though not yet legally binding — goal for European data centres to be climate-neutral and energy-efficient by 2030. The tension between rapidly expanding computational capacity and climate commitments is the defining challenge that the CADA and the Data Centre Energy Efficiency Package are designed to address.

The geographic concentration of data centres adds further complexity. Capacity is heavily concentrated in North-West Europe — Ireland, the Netherlands, Germany, and the UK together host a disproportionate share of European data centre infrastructure. Dublin and Amsterdam have at times imposed moratoriums on new data centre construction due to local grid saturation. Ireland's data centres now account for approximately 22 per cent of national electricity supply. This concentration means that the environmental impacts of cloud workloads are spatially uneven, and the carbon intensity of a given cloud region is highly dependent on where, precisely, its data centres sit and what electricity mix feeds them.

### 1.2 The Regulatory Landscape

The EU's regulatory response to data centre energy use has developed in layers:

**Energy Efficiency Directive (EED) 2024/1791.** The recast EED, which entered into force in 2024, establishes the foundational reporting framework. Facilities with an installed IT power demand of at least 500 kW are required to submit detailed operational metrics annually to a central European database managed by the European Commission. Mandatory reporting fields include total IT energy consumption, PUE, WUE, energy reuse factor, and renewable energy sourcing. The first EED reports were due on 15 September 2024; the second by 15 May 2025. The Commission is required to assess the submitted data and, where appropriate, propose further measures — including minimum performance standards or a rating scheme.

**Data Centre Energy Efficiency Package (Q1–Q2 2026).** Acting on the EED's assessment mandate, the Commission is preparing a dedicated package to be published alongside CADA. This package is expected to: assess the data submitted in the first two EED reporting cycles; introduce a pan-European rating scheme for data centres; and launch formal work on minimum performance standards. The package represents the transition from data collection to performance accountability.

**Cloud and AI Development Act (CADA).** CADA is a broader legislative initiative grounded in Article 114 TFEU, targeting Europe's cloud and AI competitiveness. Its consultation document structures the Act around three pillars: efficiency and sustainability, investment and capacity, and cloud sovereignty. Critically for this paper, CADA's efficiency pillar is expected to link permitting and public support for new data centres to demonstrable compliance with sustainability criteria — including energy efficiency, water use, and renewable energy sourcing. The Act, with its accompanying Data Centre Energy Efficiency Package, is planned for April 2026.

**EU AI Act.** Regulation (EU) 2024/1689 imposes transparency requirements on providers of General-Purpose AI models with systemic risk, including reporting of energy consumption. The Act also requires the Commission to work with standards bodies to develop standards for improving energy efficiency in AI systems. Energy consumption is itself one of the factors that can trigger classification as a systemic-risk GPAI model, creating a direct incentive for providers to document and minimise cloud workload carbon intensity.

These four instruments form an interlocking framework. The EED provides the data; the Energy Efficiency Package translates that data into performance expectations; CADA embeds those expectations into investment and permitting conditions; and the AI Act extends energy transparency requirements specifically to AI workloads. The common thread running through all four is a need for reliable, comparable, region-level environmental data from cloud providers.

### 1.3 The Data Problem

Despite the EED's reporting requirements, a fundamental data problem persists: cloud providers do not report environmental performance data in a consistent way.

Providers currently publish efficiency and carbon data using different methodologies, different geographic granularities, and on different timescales. Power Usage Effectiveness is reported on different schedules: Google provides quarterly and trailing 12-month data for a subset of its facilities; AWS provides annual data for selected regions; Azure previously provided comprehensive regional PUE data in 2022 but has since been less consistent. Water Usage Effectiveness data is similarly fragmented: Azure reported it for all regions in 2022; AWS provides only a global average; Google does not currently publish WUE data at all. Carbon intensity figures are reported using different underlying methodologies — some location-based, some market-based, some using different third-party grid data providers — making direct comparisons between providers unreliable.

This inconsistency is not merely an academic problem. It has direct regulatory consequences: if policymakers cannot compare the environmental performance of data centres run by different providers in different regions, they cannot set meaningful minimum performance standards, design equitable rating schemes, or verify that CADA's sustainability conditions are being met. Cloud customers face the same problem: organisations with legal obligations to report their Scope 2 emissions under the Corporate Sustainability Reporting Directive (CSRD), California's SB 253, or other frameworks often cannot obtain the region-level data they need from their providers directly.

---

## 2. Evidence and Technical Analysis

### 2.1 The Cloud Region Metadata Specification

The Green Software Foundation's Cloud Region Metadata specification (version 1.1.0), developed under the Real-Time Cloud project, was designed precisely to address the data problem described in Section 1.3. It establishes a unified data schema that enables cloud providers to publish comprehensive, standardised carbon and energy metadata at the cloud region level — the geographic unit at which cloud workloads are deployed and at which environmental impacts are most practically attributable.

The specification is grounded in the recognition that "all models are wrong, some models are useful." It does not claim to provide perfect environmental accounting. Instead, it aims to make cloud carbon models *significantly less wrong* through methodological standardisation, and *more useful* through consistent metadata disclosure. This is an honest and appropriate framing for a standards document operating at the frontier of a genuinely complex measurement problem.

The specification defines two conformance levels. Level 1 (Basic) requires mandatory reporting of region identifier, location, PUE, annual location-based grid carbon intensity, and carbon-free energy proportion. Level 2 (Advanced) adds real-time API integration, hourly carbon intensity data, market-based carbon intensity, water usage effectiveness, and full EED-aligned energy reporting fields. This tiered structure allows providers to start with basic compliance and progress toward advanced transparency, which is aligned with how regulators typically phase in requirements.

### 2.2 What the Specification Measures

The specification's schema covers the following categories of measurement, each of which has direct relevance to CADA and EED requirements:

**Energy efficiency metrics.** PUE (Power Usage Effectiveness) and WUE (Water Usage Effectiveness) are mandatory fields, standardising formulas and reporting frequencies that are currently inconsistent across providers.

**Carbon intensity.** The schema captures six distinct carbon intensity measures:
- Location-based grid carbon intensity (annual average) — the primary metric for EED compliance and SCI calculations
- Location-based grid carbon intensity (hourly weighted average) — supporting real-time and 24×7 carbon-free energy matching
- Market-based carbon intensity — accounting for PPAs, RECs, and carbon offsets
- Marginal carbon intensity — for applications requiring emissions-at-the-margin calculations
- Annual average consumption-based intensity — using Electricity Maps data
- Hourly weighted consumption-based intensity — for carbon-aware workload scheduling

**Carbon-free energy.** Both annual and hourly proportions of energy consumption matched with carbon-free sources (including nuclear) are captured. This distinction matters: annual CFE matching is less demanding and more commonly reported; hourly (24×7) CFE matching is a higher bar that the GSF has publicly identified as the more meaningful measure for genuine decarbonisation.

**EED-aligned fields.** The schema explicitly includes fields to support EED reporting requirements: `total-ICT-energy-consumption-annual`, `total-water-input`, `renewable-energy-consumption`, `renewable-energy-consumption-goe` (Guarantees of Origin), `renewable-energy-consumption-ppa`, and `renewable-energy-consumption-onsite`. These fields were incorporated specifically to align with the EU regulatory framework.

**Grid mapping identifiers.** Each region record includes zone identifiers for Electricity Maps (`em-zone-id`) and WattTime (`wt-region-id`), enabling users to access real-time grid data from third-party providers and linking the static annual dataset to live carbon intensity APIs.

### 2.3 EED Field Alignment

The following table maps the specification's data fields to the EED's mandatory reporting requirements, demonstrating direct alignment.

| EED Mandatory Reporting Requirement | Specification Field | Notes |
|---|---|---|
| Annual IT energy consumption | `total-ICT-energy-consumption-annual` | Exact EED requirement; in kWh |
| Power Usage Effectiveness (PUE) | `power-usage-effectiveness` | Annual average across all facilities in region |
| Water Usage Effectiveness (WUE) | `water-usage-effectiveness` | L/kWh; aligns with The Green Grid definition |
| Renewable energy consumption | `renewable-energy-consumption` | Total renewable energy in kWh |
| Renewable energy — Guarantees of Origin | `renewable-energy-consumption-goe` | RECs/GoOs |
| Renewable energy — PPAs | `renewable-energy-consumption-ppa` | Power Purchase Agreements |
| Renewable energy — on-site | `renewable-energy-consumption-onsite` | Behind-the-meter generation |
| Total water input | `total-water-input` | In litres |
| Grid carbon intensity | `grid-carbon-intensity` | Location-based; required for SCI-o and regulatory calculations |

This alignment is deliberate. The specification was developed with EED compliance in mind, and its inclusion of dedicated EED fields makes it a practical tool for cloud providers navigating their first reporting cycles.

### 2.4 Beyond the EED: Hourly Resolution and Carbon-Aware Computing

The specification's most distinctive contribution relative to the current EED framework is its hourly granularity. The EED collects annual averages; the specification provides hourly-weighted carbon intensity data and integration paths to real-time APIs updated at minute-to-hourly intervals.

This matters for two reasons. First, the carbon intensity of a power grid varies significantly across hours and seasons. A data centre that runs predominantly on renewable energy during daylight hours but draws from fossil fuel sources at night has a very different environmental profile from one running on a consistent low-carbon mix — but annual averages will not capture this difference. Hourly matching is increasingly recognised as the appropriate standard for 24×7 carbon-free energy claims.

Second, higher temporal resolution enables *carbon-aware computing* — the practice of scheduling flexible workloads to run when and where the grid carbon intensity is lowest. This is a significant lever for reducing cloud workload emissions without changing the underlying hardware, and it requires exactly the kind of region-level, real-time carbon data that the specification provides. The Green Software Foundation has published extensively on carbon-aware computing and its contribution to software sustainability, and the Real-Time Cloud dataset is the operational foundation for this approach.

The European Commission's own analysis of EED implementation has noted the limitations of annual data for capturing the operational realities of data centre energy use. The specification's higher temporal resolution is therefore not just a technical feature; it represents a forward-looking contribution to what *better* data centre environmental accountability should look like under CADA and its successors.

---

## 3. Policy Implications and Regulatory Mapping

### 3.1 CADA and the Data Centre Energy Efficiency Package

CADA's efficiency pillar is expected to condition fast-track permitting and public support for new data centres on demonstrated compliance with sustainability criteria. The Data Centre Energy Efficiency Package will introduce the rating scheme and minimum performance standards against which this compliance will be measured. The practical challenge for regulators designing these instruments is: *measured against what?*

The EED has provided a baseline dataset through its first two reporting cycles. However, the EED database is a confidential reporting mechanism — data is submitted to the Commission and published only in aggregated form at EU and Member State levels. It does not provide the public, provider-level, region-level dataset that CADA's transparency ambitions would require, nor does it enable cloud customers to compare the environmental performance of specific regions from different providers.

The Cloud Region Metadata specification fills exactly this gap. It is a public dataset, built through an open, multi-stakeholder process, and structured to enable meaningful cross-provider, cross-region comparisons. It has already collected data from major providers including Google Cloud, AWS, and Azure (noting the current Azure 2024 data gap, discussed in Section 4.1). It is maintained on GitHub under a Creative Commons licence, with documented versioning and an open contribution process.

### 3.2 Mapping the Specification to CADA Reporting Pillars

Based on the Commission's call for evidence and the European Parliament's briefing on CADA, the Act's sustainability requirements are expected to address four core areas. The following table maps each to the specification's relevant capabilities.

| CADA Sustainability Pillar | Specification Capability | Notes |
|---|---|---|
| **Energy efficiency** — PUE and WUE performance benchmarks | `power-usage-effectiveness`, `water-usage-effectiveness` | Standardised formulas and reporting frequency; enables benchmarking across providers |
| **Renewable energy sourcing** — proportion of clean energy | `provider-cfe-annual`, `provider-cfe-hourly`, `renewable-energy-consumption` | Both annual and hourly (24×7) CFE matching supported |
| **Carbon intensity transparency** — location-based grid intensity | `grid-carbon-intensity`, `grid-carbon-intensity-average-consumption-annual` | Mapped to Electricity Maps and WattTime zones for verification |
| **Carbon-free energy matching** — hourly granularity | `provider-carbon-intensity-average-consumption-hourly`, `em-zone-id`, `wt-region-id` | Enables integration with live grid APIs for real-time verification |

The specification also supports the Commission's stated interest in comparing European data centre performance with that of US and Asian facilities — a dimension of the competitiveness argument in CADA that requires internationally consistent measurement standards.

### 3.3 The Specification as Evidence for Minimum Performance Standards

One of CADA's most significant provisions is the mandate to establish minimum performance standards for EU data centres. These standards require threshold values — measurable benchmarks below which a facility cannot operate or qualify for public support. Setting credible thresholds requires empirical data on the current distribution of performance across the industry.

The Cloud Region Metadata dataset provides exactly this. By collecting PUE, WUE, CFE proportions, and carbon intensity values across hundreds of cloud regions from multiple providers, the dataset establishes a factual basis for understanding where the industry currently sits and what realistic improvement trajectories might look like. This is the kind of evidence that minimum performance standard-setting processes depend on, and it is currently unavailable in any other public, multi-provider form.

The specification also demonstrates, in practice, what hourly CFE matching looks like as a data point — moving it from a theoretical aspiration to a measurable standard. When the Commission and the working group convening the CADA workshops consider whether hourly matching should be required rather than merely annual, the Real-Time Cloud dataset is the primary evidence that this is technically achievable and already being done by at least one major provider.

### 3.4 Relationship to the EU AI Act

The EU AI Act imposes energy consumption transparency requirements on providers of General-Purpose AI models with systemic risk. The Act mandates that the Commission develop standards for energy efficiency in AI systems and requires codes of conduct on data centre energy efficiency. AI workloads are not just any cloud workloads: they are among the most energy-intensive, and their geographic placement has an outsized impact on carbon outcomes.

The Cloud Region Metadata specification is directly relevant here. A GPAI model provider selecting a cloud region for training or inference workloads can use the specification's region-level carbon intensity and CFE data to make carbon-aware placement decisions — and to document those decisions for regulatory purposes. As the AI Act's transparency requirements develop into specific standards, the specification provides a ready-made data infrastructure for demonstrating compliance.

There is also a direct link to the GSF's *SCI for AI* specification, which applies the Software Carbon Intensity metric specifically to AI workloads. The SCI calculation requires region-level grid carbon intensity data — exactly what the Cloud Region Metadata specification provides via its `grid-carbon-intensity` field. Taken together, the two specifications offer a complete methodology for measuring and reporting the carbon intensity of AI workloads under the EU AI Act.

### 3.5 Supporting Cloud Customer Scope 2 Reporting

CADA's reporting requirements extend beyond data centre operators to their customers. Organisations using cloud services to run workloads covered by CSRD or other corporate reporting frameworks need region-level carbon intensity data to calculate their Scope 2 (and potentially Scope 3) emissions from cloud use.

The GHG Protocol's Scope 2 Guidance requires organisations to use the location-based method — the average emission factor of the grid where consumption occurs — as their primary reporting metric. The specification's `grid-carbon-intensity` field is precisely this: the annual average location-based marginal grid carbon intensity for the cloud region where a workload runs. For organisations that cannot obtain verified region-level data directly from their cloud provider (a common situation, particularly for smaller customers), the Real-Time Cloud dataset provides a credible, open, industry-body-sourced secondary data source that is explicitly permitted under GHG Protocol guidance.

---

## 4. Barriers, Limitations, and Counter-Arguments

This paper's argument is that the Cloud Region Metadata specification can meaningfully support CADA implementation. That case is strong, but it requires honest engagement with its limitations and the counter-arguments.

### 4.1 Data Gaps and Provider Inconsistency

The specification's value depends on the quality and completeness of the data it contains. At the time of writing, there is a notable gap in Microsoft Azure's 2024 region-level data. Azure's sustainability team appears to have experienced turnover that interrupted the continuity of data publication, and the previously available region-level metrics are no longer accessible through their original sources. The working group is actively engaging with Azure to restore this data.

This gap illustrates a broader vulnerability: the dataset's completeness is dependent on voluntary provider cooperation. The specification cannot compel disclosure; it can only standardise the format for disclosure that providers choose to make. If CADA were to mandate EED-aligned disclosure in a public, machine-readable format — citing the specification's schema as the required format — this voluntary dependency would be substantially reduced.

### 4.2 The Scope 1 / Colocation Problem

The specification's current model assumes that cloud region power is primarily sourced from the electricity grid, attributable as Scope 2 emissions. This assumption is increasingly incomplete.

Several cloud regions operate gas-powered generation capacity on-site — behind the meter — that constitutes Scope 1 emissions from the cloud provider's perspective. A specific example identified by the working group is the North Europe region in West Dublin, Ireland, where permits indicate that reciprocating gas engines located on the campus may operate for a significant portion of the day to support local grid stability. If this generation is occurring, it would affect the effective carbon intensity of workloads running in that region — but it is not captured in the current dataset.

Similarly, the specification's model does not yet account for the fact that some cloud regions now span multiple physical locations, potentially in different grid zones with meaningfully different carbon intensities. GPU workloads may be directed to a physical location that differs from the nominal region designation, introducing carbon intensity differences that are invisible to customers using the specification's data.

These are real limitations. They are acknowledged as areas for future development in the working group, and they do not invalidate the current dataset — the specification's authors are explicit that "all models are wrong, some models are useful." But they should be disclosed in any regulatory context where the data is cited, and the Commission should consider whether CADA's reporting requirements should explicitly address Scope 1 disclosures from data centre operators.

### 4.3 Model Simplification vs. Regulatory Precision

The specification is designed to be useful and widely adoptable. This means it makes simplifications: it uses annual averages for some metrics, it aggregates multiple physical sites into a single region-level figure, and it relies on third-party grid data providers (Electricity Maps, WattTime) whose own methodologies have boundaries and uncertainties.

Regulators designing minimum performance standards need to be careful about which metrics in the dataset are appropriate as regulatory thresholds and which are better understood as directional indicators. For example, the market-based carbon intensity figure — which accounts for PPAs and RECs — will typically be lower than the location-based figure, potentially by a large margin for providers with ambitious renewable energy commitments. Using market-based intensity as a regulatory threshold without specifying that it excludes the location-based metric risks incentivising creative carbon accounting over genuine decarbonisation.

The specification is aware of this risk and explicitly distinguishes between location-based and market-based methods. Any regulatory use of the dataset should respect and reinforce this distinction.

### 4.4 Legal Status and Jurisdictional Scope

The Cloud Region Metadata specification is an open standard produced by a non-governmental multi-stakeholder body. It has no formal legal status in the EU regulatory system. CADA and the EED are binding EU law; this specification is not.

This is not, however, a reason to exclude the specification from the regulatory conversation. Established regulatory precedent exists for incorporating industry standards by reference — either as sufficient methods of compliance or as evidentiary standards for measurement. The ISO 14064 series, the GHG Protocol, and the IPCC emissions factors are all examples of non-binding standards that have been incorporated into binding regulatory frameworks. The Cloud Region Metadata specification — particularly once it progresses through ISO submission via its alignment with the Software Carbon Intensity standard — is a plausible candidate for similar treatment.

In the near term, the more achievable goal is for the Commission to reference the specification's schema in CADA's implementing regulations as a voluntary but recognised format for the public disclosure of cloud region environmental data, creating an incentive for providers to adopt it without mandating it.

---

## 5. Recommendations

Based on the analysis above, the GSF Policy Working Group makes the following recommendations, addressed to the European Commission and relevant stakeholders in the CADA development process.

**Recommendation 1: Reference the Cloud Region Metadata schema in CADA's implementing regulations as a recognised disclosure format.**

CADA's implementing measures should specify that cloud providers choosing to make public, machine-readable environmental disclosures at the region level may do so in compliance with the Cloud Region Metadata schema. This does not mandate the schema, but gives it formal recognition and creates a clear pathway for providers to adopt a single consistent format rather than developing proprietary alternatives.

**Recommendation 2: Require public disclosure of EED-mandated fields in machine-readable format.**

The EED currently requires disclosure to a confidential central EU registry. CADA should introduce a complementary obligation for cloud providers to publish a machine-readable summary of their EED-mandated metrics at the region level in a public format. The Cloud Region Metadata specification already includes all of the relevant EED fields and provides a ready-made schema for this purpose.

**Recommendation 3: Adopt hourly carbon matching as the reference standard in CADA's rating scheme.**

The Data Centre Energy Efficiency Package's rating scheme should distinguish between annual and hourly carbon-free energy matching. The Cloud Region Metadata specification already captures both (`provider-cfe-annual` and `provider-cfe-hourly`). A rating scheme that recognises hourly matching as a higher tier of performance — rather than treating annual averages as sufficient — would incentivise providers to move toward genuine 24×7 carbon-free energy and provide a transparent basis for the distinction.

**Recommendation 4: Require disclosure of Scope 1 emissions from on-site generation in data centre facilities.**

CADA's reporting framework should explicitly address Scope 1 emissions from data centre operators — including on-site generation from gas reciprocating engines or other non-grid sources. The current EED framework does not clearly capture this, and the omission creates a material accountability gap as behind-the-meter generation becomes more significant. A future version of the Cloud Region Metadata specification should incorporate a Scope 1 reporting field once consistent provider disclosure practices are established.

**Recommendation 5: Engage the Green Software Foundation as a stakeholder in CADA's minimum performance standards development process.**

The GSF's working group has three years of experience aggregating, analysing, and publishing cloud region environmental data. The Real-Time Cloud dataset represents the most comprehensive multi-provider, multi-region environmental dataset currently available in the public domain. The Commission's workshops on minimum performance standards would benefit from direct engagement with the working group as a source of empirical evidence on the current distribution of provider performance and the technical achievability of proposed thresholds.

**Recommendation 6: Maintain and expand the Cloud Region Metadata dataset, with priority on closing the Microsoft Azure 2024 data gap.**

The GSF Policy Working Group commits to continuing to maintain and publish the Cloud Region Metadata dataset and to resolving the current Azure 2024 data gap as a priority. The working group will also pursue engagement with AWS on local zone data disclosure, and will advocate for all major providers to adopt Level 2 conformance with the specification, including real-time API integration.

---

## 6. Conclusions

The EU Cloud and AI Development Act and the Data Centre Energy Efficiency Package represent the most significant regulatory development in European data centre environmental accountability in a generation. They will set minimum performance standards, introduce a pan-European rating scheme, and link public investment and permitting to demonstrated sustainability — all of which depend on reliable, comparable, region-level environmental data.

That data problem is not solved by the EED alone. The EED creates a confidential reporting obligation; it does not create a public, machine-readable, multi-provider dataset against which regulators and cloud customers can benchmark performance. The Cloud Region Metadata specification does.

The specification is not a perfect instrument. It has data gaps, model simplifications, and limitations in its treatment of Scope 1 emissions and multi-location regions. These are honest limitations, acknowledged by the working group, and they are consistent with where the industry is today. What the specification offers is the best currently available public evidence base for what standardised cloud region environmental reporting looks like in practice, at the granularity that modern carbon-aware computing and regulatory accountability require.

The case for embedding this specification in CADA's implementing framework is both practical and principled. Practically, it provides regulators with a ready-made, field-tested schema that aligns with EED requirements and supports the transparency that minimum performance standards need. In principle, it demonstrates that a multi-stakeholder, open-process standards body can produce technically credible infrastructure that serves the public interest — the kind of approach that the EU regulatory framework has long recognised and built upon in other domains.

The Green Software Foundation Policy Working Group is ready to engage with the European Commission, the Data Centre Energy Efficiency Package working group, and CADA's implementing process to advance these recommendations. The 24 March 2026 European Commission workshop on data centre minimum performance standards is an immediate opportunity to do so.

---

## 7. Sources

### Standards and Regulatory Sources

- Green Software Foundation. *Cloud Region Metadata Specification, v1.1.0.* Green Software Foundation Real-Time Cloud Project. [https://github.com/Green-Software-Foundation/real-time-cloud](https://github.com/Green-Software-Foundation/real-time-cloud)
- European Parliament and Council of the EU. *Energy Efficiency Directive (EED) 2024/1791.* Entered into force 2024.
- European Commission. *Cloud and AI Development Act (CADA).* Commission Work Programme 2026, Q1 2026. Legislative Train Schedule: [https://www.europarl.europa.eu/legislative-train/theme-a-new-plan-for-europe-s-sustainable-prosperity-and-competitiveness/file-cloud-and-ai-development-act](https://www.europarl.europa.eu/legislative-train/theme-a-new-plan-for-europe-s-sustainable-prosperity-and-competitiveness/file-cloud-and-ai-development-act)
- European Commission. *Call for Evidence: EU Cloud and AI Development Act.* April–July 2025. [https://ec.europa.eu/info/law/better-regulation/have-your-say/initiatives/14628-Cloud-and-AI-Development-Act_en](https://ec.europa.eu/info/law/better-regulation/have-your-say/initiatives/14628-Cloud-and-AI-Development-Act_en)
- European Commission. *Energy Performance of Data Centres — EU Database and Policy Overview.* Energy DG. [https://energy.ec.europa.eu/topics/energy-efficiency/energy-efficiency-targets-directive-and-rules/energy-efficiency-directive/energy-performance-data-centres_en](https://energy.ec.europa.eu/topics/energy-efficiency/energy-efficiency-targets-directive-and-rules/energy-efficiency-directive/energy-performance-data-centres_en)
- European Parliament Research Service. *Cloud and AI Development Act — Legislative Briefing.* EPRS_BRI(2025)779251. December 2025. [https://www.europarl.europa.eu/thinktank/en/document/EPRS_BRI(2025)779251](https://www.europarl.europa.eu/thinktank/en/document/EPRS_BRI(2025)779251)
- Regulation (EU) 2024/1689. *EU AI Act.* Entered into force August 2024.
- World Resources Institute and WBCSD. *GHG Protocol Corporate Accounting and Reporting Standard.* [https://ghgprotocol.org](https://ghgprotocol.org)
- World Resources Institute. *GHG Protocol Scope 2 Guidance.* 2015.
- ISO/IEC 21031:2024. *Software Carbon Intensity (SCI) Specification.*
- Green Software Foundation. *Policy Working Group Whitepaper Process, v1.0.* March 2026. [https://github.com/Green-Software-Foundation/sci-policy-and-legislation-alignment-white-paper-series](https://github.com/Green-Software-Foundation/sci-policy-and-legislation-alignment-white-paper-series)

### Institutional and Industry Reports

- International Energy Agency. *Energy and AI.* IEA, 2024. [https://www.iea.org](https://www.iea.org)
- European Commission. *Assessment of the Energy Performance and Sustainability of Data Centres in the EU.* July 2025.
- European Commission. *Assessment of Next Steps to Promote the Energy Performance and Sustainability of Data Centres in the EU, Including the Establishment of an EU-Wide Rating Scheme.* October 2025.
- Draghi, M. *The Future of European Competitiveness: A Competitiveness Strategy for Europe.* September 2024.
- White & Case LLP. *Data Centres and Energy Consumption: Evolving EU Regulatory Landscape and Outlook for 2026.* [https://www.whitecase.com/insight-alert/data-centres-and-energy-consumption-evolving-eu-regulatory-landscape-and-outlook-2026](https://www.whitecase.com/insight-alert/data-centres-and-energy-consumption-evolving-eu-regulatory-landscape-and-outlook-2026)
- White & Case LLP. *Energy Efficiency Requirements under the EU AI Act.* [https://www.whitecase.com/insight-alert/energy-efficiency-requirements-under-eu-ai-act](https://www.whitecase.com/insight-alert/energy-efficiency-requirements-under-eu-ai-act)
- Simon, J. *The EU Cloud and AI Development Act (CADA): A Last Shot at Cloud Sovereignty, or Another Expensive Debacle?* Medium, February 2026. [https://julsimon.medium.com/the-eu-cloud-and-ai-development-act-cada](https://julsimon.medium.com/the-eu-cloud-and-ai-development-act-cada)
- Bird & Bird. *EU: A Bid for Tech Sovereignty Drives Commission's Work Programme for 2026.* [https://www.twobirds.com/en/insights/2025/eu-a-bid-for-tech-sovereignty-drives-commissions-work-programme-for-2026](https://www.twobirds.com/en/insights/2025/eu-a-bid-for-tech-sovereignty-drives-commissions-work-programme-for-2026)

### Green Software Foundation Publications

- Green Software Foundation Policy Working Group. *Leveraging the Software Carbon Intensity (SCI) Standard for CSRD Compliance.* 2025.
- Green Software Foundation. *SCI for AI Specification.* Green Software Foundation.
- Green Software Foundation. *Software Energy Efficiency (SEE) Specification.* Approved 2026; ISO submission pending.

---

*This paper is a working draft and is subject to review and approval by the GSF Policy Working Group. Comments should be submitted via the working group's GitHub repository or raised at the next scheduled meeting on 24 March 2026.*

# Software Carbon Intensity and the EU Corporate Sustainability Due Diligence Directive

## How the SCI Framework Can Support Environmental Due Diligence for Technology Supply Chains

**Version**: 1.0 **Date**: March 2026 **Author**: GSF Policy Working Group **Status**: Working Draft

---

## Abstract

The EU Corporate Sustainability Due Diligence Directive (CSDDD, Directive 2024/1760) requires large companies to conduct risk-based environmental due diligence across their operations and value chains. The Omnibus I simplification package, published in February 2026, raised scope thresholds to 5,000 employees and €1.5 billion turnover, removed the mandatory climate transition plan obligation, and shifted to a risk-based methodology using "reasonably available information." However, the core environmental due diligence duty — including the obligation to identify and address adverse environmental impacts linked to emissions — remains intact.

For technology companies and their customers, a material share of environmental impact originates in software operations: the energy consumed by software systems, the carbon intensity of the grids they run on, and the embodied emissions of the hardware they use. The Software Carbon Intensity (SCI) standard (ISO/IEC 21031:2024), developed by the Green Software Foundation, provides a structured methodology for identifying, measuring, and monitoring these impacts at the level of individual software systems — precisely the granularity that risk-based environmental due diligence requires.

This paper examines the alignment between the SCI framework and the post-Omnibus CSDDD. We find that SCI is a useful supporting tool for the environmental due diligence process, particularly for technology supply chains, but it is not a direct compliance mechanism. The CSDDD's environmental obligations centre on the specific international conventions listed in its Annex — prohibitions on mercury, persistent organic pollutants, hazardous waste, and biodiversity harm — rather than on general carbon accounting. The most natural regulatory connection point for SCI was the mandatory climate transition plan, which the Omnibus removed. What remains is a supporting role: SCI can help companies identify emission-intensive software in their supply chains, prioritise due diligence efforts, and generate the structured data needed for CSRD sustainability reporting — which continues to require climate transition plan disclosure even after the CSDDD transition plan obligation was deleted.

---

## Table of Contents

1. [The CSDDD: What It Requires After the Omnibus](#1-the-csddd-what-it-requires-after-the-omnibus)
2. [Environmental Due Diligence: Scope and Methodology](#2-environmental-due-diligence-scope-and-methodology)
3. [Where Software Meets the Value Chain](#3-where-software-meets-the-value-chain)
4. [Mapping SCI to the Due Diligence Process](#4-mapping-sci-to-the-due-diligence-process)
5. [The Climate Transition Plan Gap](#5-the-climate-transition-plan-gap)
6. [Limitations and Counter-Arguments](#6-limitations-and-counter-arguments)
7. [Recommendations](#7-recommendations)
8. [Conclusions](#8-conclusions)
9. [Sources](#9-sources)

---

## 1. The CSDDD: What It Requires After the Omnibus

### 1.1 Overview

The Corporate Sustainability Due Diligence Directive (Directive 2024/1760) was adopted on 13 June 2024 and entered into force on 25 July 2024. It establishes a corporate duty to conduct risk-based human rights and environmental due diligence across a company's own operations, its subsidiaries, and its business partners' activities within the value chain ([EUR-Lex, 2024](https://eur-lex.europa.eu/eli/dir/2024/1760/oj/eng)).

The Omnibus I simplification package, which received trilogue agreement in December 2025 and was published in the Official Journal on 26 February 2026, made significant changes ([Council of the EU, 2025](https://www.consilium.europa.eu/en/press/press-releases/2025/12/09/council-and-parliament-strike-a-deal-to-simplify-sustainability-reporting-and-due-diligence-requirements-and-boost-eu-competitiveness/)):

| Element | Original CSDDD | Post-Omnibus |
| :--- | :--- | :--- |
| **Scope (EU companies)** | >1,000 employees and >€450m turnover | >5,000 employees and >€1.5bn turnover |
| **Scope (non-EU companies)** | >€450m EU turnover | >€1.5bn EU turnover |
| **Climate transition plan** | Mandatory: adopt and implement | Deleted entirely |
| **Due diligence methodology** | Tier-based supply chain assessment | Risk-based, using "reasonably available information" |
| **Civil liability** | Mandatory EU-wide regime | Removed; deferred to national law |
| **Maximum penalties** | Not specified | 3% of net worldwide turnover |
| **Transposition deadline** | 26 July 2027 | 26 July 2028 |
| **Application date** | Staggered from 2027 | Unified: 26 July 2029 |

### 1.2 What Remains

Despite the simplification, the core environmental due diligence duty is preserved. Companies in scope must still:

1. **Integrate** due diligence into policies and risk management systems
2. **Identify and assess** actual or potential adverse environmental impacts
3. **Prevent and mitigate** potential adverse impacts
4. **Bring actual adverse impacts to an end** and minimise their extent
5. **Establish** notification mechanisms and complaints procedures

Due diligence must cover the company's own operations, subsidiaries, and — where related to the value chain — business partners' activities. The obligation to identify and address impacts linked to emissions in the chain of activities specifically remains ([Inside Energy & Environment, 2026](https://www.insideenergyandenvironment.com/2026/02/eu-csddd-csrd-omnibus-published-in-official-journal-transposition-delegated-acts-and-guidelines-are-next/)).

---

## 2. Environmental Due Diligence: Scope and Methodology

### 2.1 The Annex: Convention-Based Environmental Obligations

The CSDDD defines adverse environmental impacts by reference to the international conventions listed in its Annex, Part II. These include ([Verfassungsblog, 2024](https://verfassungsblog.de/new-wine-in-old-bottles-csddd/)):

| Convention | Subject Matter |
| :--- | :--- |
| **Minamata Convention** | Mercury trade and waste management |
| **Stockholm Convention** | Persistent organic pollutants (POPs) |
| **Rotterdam Convention** | Import/export of hazardous chemicals |
| **Basel Convention** | Transboundary movement of hazardous waste |
| **Convention on Biological Diversity** (+ Cartagena and Nagoya Protocols) | Biodiversity, biosafety, access and benefit-sharing |
| **CITES** | Endangered species trade |
| **World Heritage Convention** | Natural heritage protection |
| **Ramsar Convention** | Wetlands conservation |

The Annex also covers broader environmental degradation — harmful soil changes, water and air pollution, excessive water consumption, deforestation — assessed by reference to measurable degradation that substantially impairs natural resources or ecosystems.

**This is important for understanding the SCI's role.** The CSDDD's environmental obligations are anchored in specific international instruments, not in general carbon accounting frameworks. The Directive does not require companies to measure or reduce operational carbon emissions per se. It requires them to identify and address adverse impacts defined by reference to these conventions.

### 2.2 The Post-Omnibus Risk-Based Approach

The Omnibus replaced tier-based supply chain assessment with a two-step risk-based methodology:

**Step 1 — Scoping.** Companies identify general areas where adverse impacts are most likely to occur and be most severe, using only "reasonably available information" — data from internal or existing external sources, without contacting business partners. Risk factors include whether partners are subject to comparable laws, geographic enforcement levels, and sector-specific contexts.

**Step 2 — In-depth assessment.** Detailed evaluation of areas identified as highest-risk. Companies may prioritise direct business partners where impacts are equally likely across multiple areas. Information requests to partners are limited to what is "necessary" and further restricted for partners with fewer than 5,000 employees ([Inside Energy & Environment, 2026](https://www.insideenergyandenvironment.com/2026/02/eu-csddd-csrd-omnibus-published-in-official-journal-transposition-delegated-acts-and-guidelines-are-next/)).

This risk-based approach means that companies need structured, comparable data to perform scoping efficiently. Where environmental impacts are diffuse and embedded in complex technology supply chains — as with software — standardised measurement frameworks become particularly valuable.

### 2.3 The Commission Guidelines

The Commission must publish due diligence guidelines by 26 July 2027, covering due diligence processes, stakeholder engagement, data sources, **digital tools**, model contract clauses, and risk factor assessment. A second set of guidelines is due by 26 July 2028, covering resource and information sharing. The explicit reference to "digital tools" signals that the Commission expects technology-enabled approaches to play a role in compliance ([Inside Energy & Environment, 2026](https://www.insideenergyandenvironment.com/2026/02/eu-csddd-csrd-omnibus-published-in-official-journal-transposition-delegated-acts-and-guidelines-are-next/)).

---

## 3. Where Software Meets the Value Chain

### 3.1 The Technology Supply Chain as an Environmental Vector

For companies in scope of the CSDDD, software and cloud services are increasingly material components of the value chain. Enterprise technology procurement involves complex supply chains spanning cloud infrastructure providers, SaaS vendors, AI model providers, data center operators, and hardware manufacturers — each carrying environmental impacts.

These impacts are substantial. Data centers consumed approximately 415 TWh globally in 2024, projected to exceed 945 TWh by 2030 ([IEA, 2025](https://www.iea.org/reports/energy-and-ai/executive-summary)). For companies whose operations depend heavily on cloud computing, AI services, or large-scale data processing, the environmental footprint of their technology supply chain may represent a significant — and growing — share of their total value chain impact.

### 3.2 The Identification Problem

The CSDDD's first due diligence step requires companies to identify where adverse environmental impacts are most likely and most severe. For technology supply chains, this is challenging because:

- **Emissions are embedded and opaque.** A company using a cloud-based AI service cannot easily determine the energy consumption, grid carbon intensity, or hardware lifecycle emissions of the infrastructure serving its workloads.
- **Variability is high.** The same computation performed in different cloud regions, at different times, on different hardware generations, produces radically different environmental impacts.
- **No standardised disclosure exists.** Unlike physical supply chains where environmental data (however imperfect) flows through established frameworks, digital supply chains lack comparable measurement and disclosure standards.

This is where the SCI framework becomes relevant — not as a compliance mechanism for the CSDDD's convention-based obligations, but as a tool for identifying and assessing the environmental characteristics of software in the value chain.

---

## 4. Mapping SCI to the Due Diligence Process

### 4.1 The SCI Framework

The Software Carbon Intensity specification (ISO/IEC 21031:2024), developed by the Green Software Foundation, measures the carbon emissions of a software system per unit of useful work ([SCI Specification](https://sci.greensoftware.foundation/)):

```
SCI = ((E × I) + M) per R
```

Where E is energy consumed, I is location-specific grid carbon intensity, M is embodied hardware emissions, and R is a functional unit of work. SCI mandates location-based accounting and excludes market-based instruments (offsets, RECs, PPAs), measuring what a workload actually causes on the grid.

Domain-specific extensions include SCI for AI (ratified December 2025), which defines standardised functional units for AI systems (per token, per image, per inference), and the proposed SCI-C (Software Carbon Intensity — Circular), which measures hardware circularity.

### 4.2 Alignment with Due Diligence Steps

The CSDDD's due diligence process maps to SCI capabilities as follows:

| CSDDD Obligation | SCI Capability | Fit Assessment |
| :--- | :--- | :--- |
| **Identify and assess** adverse environmental impacts | SCI scores quantify the carbon intensity of individual software systems, enabling comparison across vendors and regions | **Moderate.** SCI identifies carbon impacts, not the specific convention-based harms in the Annex. However, for climate-related due diligence (which remains post-Omnibus), SCI provides granular identification. |
| **Prevent and mitigate** potential adverse impacts | SCI's three levers — energy efficiency, carbon awareness, hardware efficiency — provide actionable reduction pathways | **Moderate.** SCI identifies *what* to improve but does not itself prevent or mitigate impacts. It informs decisions; it does not implement them. |
| **Risk-based scoping** using "reasonably available information" | SCI scores, where available from suppliers, constitute structured, comparable environmental data for technology supply chain scoping | **Strong.** This is SCI's clearest contribution. Where cloud and software suppliers report SCI scores, companies can scope their technology supply chain risks efficiently without bespoke data collection. |
| **Monitoring** over time | SCI is a rate-based metric designed for tracking improvement or regression across versions and operational periods | **Strong.** SCI's design as a rate (not an absolute) makes it well-suited to monitoring trends in software environmental performance. |
| **Notification and complaints** | Not directly relevant | **Weak.** SCI does not address grievance mechanisms. |

### 4.3 The Supply Chain Transparency Use Case

The most practical application of SCI in the CSDDD context is **technology procurement due diligence**. A company subject to the CSDDD that procures significant cloud computing, AI services, or enterprise software could:

1. **Request SCI scores** from technology suppliers as part of the Step 1 scoping exercise — using them as "reasonably available information" to identify which parts of the technology supply chain carry the highest environmental impact.
2. **Compare suppliers** on a standardised basis. SCI's functional units (per token, per API call, per user) enable meaningful comparison that raw energy consumption figures do not.
3. **Set procurement thresholds.** Include SCI score requirements in technology procurement criteria, creating market incentives for suppliers to measure and reduce their software carbon intensity.
4. **Monitor supplier performance** over time, tracking whether SCI scores improve or degrade as software versions and infrastructure change.

This is not compliance with the Annex-based environmental obligations. It is a practical tool for performing environmental due diligence on the technology supply chain — one that the CSDDD's risk-based methodology, with its emphasis on using reasonably available information, is well-suited to accommodate.

---

## 5. The Climate Transition Plan Gap

### 5.1 What Was Lost

The original CSDDD's Article 22 required companies to adopt and implement climate transition plans aligned with the Paris Agreement's 1.5°C target, including time-bound absolute emission reduction targets for Scopes 1, 2, and 3, decarbonisation strategies, investment details, and governance arrangements — updated annually ([Article 22, CSDDD](https://www.corporate-sustainability-due-diligence-directive.com/CSDDD_Article_22.html)).

This was the most natural connection point between the CSDDD and the SCI framework. SCI's component structure maps directly to the emissions accounting a transition plan requires: operational emissions (E × I) correspond to Scope 2; embodied emissions (M) correspond to Scope 3 (purchased goods); and the functional unit (R) provides the intensity metric needed for efficiency-based targets. A company using SCI across its software portfolio would have had structured, granular data feeding directly into its CSDDD transition plan.

The Omnibus fully deleted this obligation. This is a significant loss — not just for the SCI's regulatory relevance, but for climate accountability more broadly. As Green Central Banking observed, removing the implementation requirement does not mean companies can credibly maintain transition plans without implementing them; it means they no longer have to have plans at all under the CSDDD ([Green Central Banking, 2026](https://greencentralbanking.com/2026/02/25/climate-transition-plans-eu-omnibus/)).

### 5.2 What Remains Elsewhere

The deletion is not total across the EU regulatory landscape. Companies subject to the Corporate Sustainability Reporting Directive (CSRD) must still disclose climate transition plans under the European Sustainability Reporting Standards (ESRS). Banks face transition plan requirements under the Capital Requirements Directive. Green bond issuers require Paris-aligned plans. The CSDDD transition plan requirement was the enforcement mechanism that gave teeth to these disclosure obligations; its removal weakens the regime without eliminating it.

For companies using SCI, the practical implication is that SCI-generated data continues to support CSRD reporting obligations even after the CSDDD transition plan was deleted. SCI scores contribute directly to the emissions intensity metrics that ESRS climate disclosures require. The measurement infrastructure is the same; the regulatory hook has shifted from "mandatory plan" to "mandatory disclosure."

---

## 6. Limitations and Counter-Arguments

### 6.1 The Annex Problem

The CSDDD's environmental obligations are defined by reference to specific international conventions — mercury, POPs, hazardous waste, biodiversity, endangered species. SCI measures carbon intensity. These are different things. A company could have excellent SCI scores across its software portfolio while its technology supply chain involves hardware manufactured using processes that violate the Basel Convention or Stockholm Convention prohibitions. SCI does not capture these impacts and should not be presented as if it does.

The honest assessment is that SCI addresses one dimension of environmental impact — carbon — in one segment of the value chain — software operations. It is a useful tool for that specific purpose, but it is not a comprehensive environmental due diligence framework.

### 6.2 Scope Narrowing Reduces Relevance

The Omnibus raised the scope threshold to 5,000 employees and €1.5 billion turnover, reducing the number of in-scope EU companies to approximately 1,000 (from roughly 6,000 under the original thresholds) and non-EU companies to approximately 500. The GSF's membership includes organisations above these thresholds, but many technology companies — particularly mid-tier SaaS providers, specialist AI companies, and green IT firms — will fall outside scope. SCI's value for these companies is as a voluntary tool and a competitive differentiator in procurement, not as a compliance requirement.

### 6.3 Data Availability

SCI adoption is still early-stage. Most software and cloud suppliers do not yet report SCI scores. Until SCI reporting becomes widespread, its utility as "reasonably available information" for Step 1 scoping is limited. This is a chicken-and-egg problem: CSDDD due diligence would benefit from SCI data, but SCI data will not become widespread until there is demand — including from companies performing due diligence.

### 6.4 The Omnibus's Direction of Travel

The Omnibus reflects a political shift toward simplification and competitiveness over environmental stringency. The deletion of the climate transition plan, the removal of civil liability, the narrowing of scope — these signal that the Commission's immediate priority is reducing compliance burden. Advocating for SCI adoption in this context requires realism: the regulatory tailwind is weaker than it was when the original CSDDD was adopted.

However, the Omnibus includes a review clause (Article 36) requiring the Commission to assess the Directive by July 2031 and every five years thereafter, with the possibility of legislative proposals to expand scope or strengthen requirements. SCI adoption now positions organisations for potential future tightening.

---

## 7. Recommendations

### 7.1 For Technology Companies in Scope of the CSDDD

1. **Include technology supply chain in Step 1 scoping.** Software and cloud services carry material environmental impact that should not be excluded from risk-based environmental due diligence because it is intangible.

2. **Request SCI scores from technology suppliers.** Use SCI as structured "reasonably available information" for identifying emission-intensive software in the value chain. Where suppliers do not yet report SCI, this request itself creates market pressure for adoption.

3. **Integrate SCI data into CSRD reporting.** Even though the CSDDD transition plan was deleted, CSRD reporting obligations require climate disclosure. SCI scores provide the granular, software-level emissions data that ESRS climate standards require.

### 7.2 For Technology Suppliers (Including Those Below CSDDD Thresholds)

1. **Adopt SCI measurement proactively.** Customers in scope of the CSDDD will increasingly require environmental data from their technology supply chain. SCI provides a standardised, ISO-backed framework that is more credible and comparable than bespoke sustainability claims.

2. **Report SCI scores publicly.** Voluntary SCI disclosure positions suppliers as due-diligence-ready, reducing friction for customers performing environmental assessments and creating competitive advantage in enterprise procurement.

### 7.3 For the European Commission (Guidelines Development)

1. **Reference SCI in the due diligence guidelines.** The Commission's guidelines on digital tools and data sources for due diligence (due July 2027) should reference ISO/IEC 21031 as a relevant measurement standard for environmental due diligence in technology supply chains.

2. **Clarify the treatment of software supply chain emissions.** The guidelines should address whether and how software and cloud services fall within the "chain of activities" for environmental due diligence purposes, and what constitutes "reasonably available information" for digital services.

### 7.4 For the GSF and Standards Community

1. **Pursue inclusion of SCI in the Commission's guidelines process.** The GSF should engage with the Commission's guideline development to ensure SCI is considered as a digital tool for environmental due diligence.

2. **Develop guidance on SCI for CSDDD due diligence.** Practical guidance showing companies how to use SCI scores in Step 1 scoping and Step 2 assessment of technology supply chains would lower the barrier to adoption.

3. **Track the Article 36 review.** The Omnibus review clause creates an opportunity for future scope expansion or requirement strengthening. Evidence of SCI adoption in voluntary due diligence today strengthens the case for regulatory recognition in future iterations.

---

## 8. Conclusions

The SCI framework has a real but bounded role in supporting compliance with the post-Omnibus CSDDD.

**Where it helps.** SCI provides structured, comparable data for identifying and assessing the carbon intensity of software in the technology supply chain. Its design as a rate-based metric, with location-specific carbon accounting and standardised functional units, makes it well-suited to the CSDDD's risk-based scoping exercise. For companies performing environmental due diligence on cloud computing, AI services, or enterprise software procurement, SCI is the most relevant measurement framework available.

**Where it does not help.** SCI does not address the convention-based environmental obligations that form the core of the CSDDD's Annex — mercury, persistent organic pollutants, hazardous waste, biodiversity. It measures carbon intensity, not compliance with the Minamata or Stockholm Conventions. It should not be presented as a comprehensive environmental due diligence tool.

**What was lost.** The Omnibus's deletion of the mandatory climate transition plan removed the CSDDD's most natural integration point with SCI. The transition plan's requirement for Scope 1, 2, and 3 emission reduction targets, updated annually, would have created direct demand for the granular emissions data SCI provides. That regulatory hook is gone. What remains is the CSRD reporting obligation, which continues to require climate transition plan disclosure, and the CSDDD's broader environmental due diligence duty, which now operates on a risk-based methodology that SCI can support but does not satisfy alone.

**The practical case.** Despite these limitations, the practical case for SCI in the CSDDD context is straightforward. Companies in scope must perform environmental due diligence on their value chains. Technology supply chains carry material environmental impact. SCI is the international standard for measuring that impact at the software level. As enterprise technology procurement increasingly incorporates environmental criteria — driven by the CSDDD, CSRD, and commercial pressure — SCI provides the measurement infrastructure that makes informed decisions possible.

The regulatory environment is weaker than it was before the Omnibus. The climate transition plan is gone. The scope is narrower. The direction of travel favours simplification over stringency. But the core environmental due diligence duty remains, the CSRD reporting obligation remains, and the Commission's upcoming guidelines will address digital tools and data sources. SCI is positioned to be part of that conversation — not as a silver bullet, but as a practical, standards-backed tool for a specific and growing need.

---

## 9. Sources

### EU Legislative Sources

- European Parliament and Council (2024). Directive (EU) 2024/1760 on corporate sustainability due diligence. [EUR-Lex](https://eur-lex.europa.eu/eli/dir/2024/1760/oj/eng)

- Council of the EU (2025). "Council and Parliament strike a deal to simplify sustainability reporting and due diligence requirements and boost EU competitiveness." Press release, 9 December 2025. [Link](https://www.consilium.europa.eu/en/press/press-releases/2025/12/09/council-and-parliament-strike-a-deal-to-simplify-sustainability-reporting-and-due-diligence-requirements-and-boost-eu-competitiveness/)

- European Parliament (2025). "Simplified sustainability reporting and due diligence rules for businesses." Press release, December 2025. [Link](https://www.europarl.europa.eu/news/en/press-room/20251211IPR32164/simplified-sustainability-reporting-and-due-diligence-rules-for-businesses)

- European Commission (2024). "Corporate sustainability due diligence." [Link](https://commission.europa.eu/topics/business-and-industry/doing-business-eu/sustainability-due-diligence-responsible-business/corporate-sustainability-due-diligence_en)

### Legal Analysis

- Inside Energy & Environment (2026). "EU CSDDD/CSRD Omnibus Published in Official Journal: Transposition, Delegated Acts, and Guidelines Are Next." [Link](https://www.insideenergyandenvironment.com/2026/02/eu-csddd-csrd-omnibus-published-in-official-journal-transposition-delegated-acts-and-guidelines-are-next/)

- Greenberg Traurig (2025). "EU Omnibus Package Trilogue Agreement on EU CSRD and CSDDD." [Link](https://www.gtlaw.com/en/insights/2025/12/eu-omnibus-package-trilogue-agreement-on-eu-csrd-and-csddd)

- Verfassungsblog (2024). "New Wine in Old Bottles: Environmental and Climate Aspects of the EU's Corporate Sustainability Due Diligence Directive." [Link](https://verfassungsblog.de/new-wine-in-old-bottles-csddd/)

- Green Central Banking (2026). "What happens to climate transition plans after the EU omnibus?" [Link](https://greencentralbanking.com/2026/02/25/climate-transition-plans-eu-omnibus/)

- Corporate Sustainability Due Diligence Directive (reference site). "Article 22: Combating Climate Change." [Link](https://www.corporate-sustainability-due-diligence-directive.com/CSDDD_Article_22.html)

- PwC (2026). "'Omnibus' directive finalised." [Link](https://viewpoint.pwc.com/gx/en/pwc/in-briefs/ib_int202527.html)

- ClientEarth (2026). "CSDDD after the Omnibus I: Legal risks, maladministration, and the future of due diligence." [Link](https://www.clientearth.org/latest/news/csddd-after-omnibus-i-legal-risks-maladministration-and-the-future-of-due-diligence/)

### Standards and Specifications

- ISO/IEC 21031:2024. "Information technology — Software Carbon Intensity (SCI) specification." [Link](https://www.iso.org/standard/86612.html)

- Green Software Foundation. SCI Specification v1.1.0. [Link](https://sci.greensoftware.foundation/)

- Green Software Foundation. SCI for AI Specification (ratified December 2025). [Link](https://sci-for-ai.greensoftware.foundation/)

### Institutional Reports

- IEA (2025). "Energy and AI." [Link](https://www.iea.org/reports/energy-and-ai/executive-summary)

---

**Document Version**: 1.0 **Last Updated**: 2026-03

# SCI-C: Software Carbon Intensity \- Circular

## A Standard for Measuring Hardware Circularity

**Status:** Draft Proposal v0.1 **Date:** 2026-02-03 **Authors:** \[TBD\]

---

## 1\. Problem Statement

Current sustainability frameworks for computing infrastructure focus primarily on operational energy consumption and, to a lesser extent, embodied carbon. The Software Carbon Intensity (SCI) standard, developed by the Green Software Foundation, represents significant progress by including an embodied carbon term (M) that accounts for the hardware on which software runs.

However, existing frameworks do not adequately capture **hardware circularity**—the degree to which hardware achieves its full useful life potential across one or more use cycles. This gap matters because:

- **Embodied carbon is substantial.** For many workloads, especially in efficient data centers, embodied carbon represents 50% or more of total lifecycle emissions. Extending hardware life is often the highest-leverage decarbonization action.   
    
- **Functional obsolescence outpaces physical obsolescence.** Hardware is frequently retired not because it fails, but because software requirements have grown beyond its capabilities, support has ended, or it no longer meets performance expectations.  
    
- **Circularity is not recycling.** Recycling is the last resort in a circular economy. Higher-value interventions—extended use, repair, refurbishment, remanufacturing—are undervalued because we lack metrics to capture them.  
    
- **Software decisions affect hardware lifespan.** Software updates that increase resource requirements can functionally obsolete working hardware at scale. This externality is currently invisible.

SCI-C aims to fill this gap with a complementary standard that measures hardware circularity, creating accountability for the decisions that determine whether hardware reaches its full useful life.

---

## 2\. Relationship to SCI

SCI-C is designed as a **standalone standard** that is **interoperable with SCI**.

### Why Standalone?

- **Different audiences.** SCI primarily serves software teams measuring carbon intensity. SCI-C serves a broader audience: hardware manufacturers, procurement teams, IT asset managers, refurbishment organizations, and policy makers.  
    
- **Different units.** SCI outputs carbon intensity (gCO2eq per functional unit). SCI-C outputs a circularity/longevity score. Forcing circularity into carbon units would distort its meaning.  
    
- **Independent adoption.** Organizations can adopt SCI-C without using SCI, and vice versa. This lowers barriers to adoption.

### Interoperability

For organizations using both standards, SCI-C can inform SCI calculations in several ways.

#### Recap: The SCI Formula

The SCI standard calculates carbon intensity as:

```
C = ((E × I) + M) per R
```

Where:

- **E** \= Energy consumed by the software (kWh)  
- **I** \= Carbon intensity of electricity (gCO2eq/kWh)  
- **M** \= Embodied carbon of hardware, amortized over expected lifespan (gCO2eq)  
- **R** \= Functional unit (API call, user, transaction, etc.)

The M term currently uses a simple linear amortization:

```
M = (Total Embodied Carbon) / (Expected Lifespan × Time Share)
```

Where "Expected Lifespan" is typically a fixed assumption (e.g., 4 years for servers).

#### Integration Pattern 1: Circularity-Adjusted Amortization

SCI-C can replace the fixed lifespan assumption with an evidence-based expected lifespan derived from circularity factors.

**Current SCI approach (fixed assumption):**

```
M = 1000 kgCO2eq / 4 years = 250 kgCO2eq/year
```

**SCI \+ SCI-C approach (circularity-informed):**

The SCI-C is the metric (score out of 100), and it can be transformed into a conversion factor for refining an M value (embodied carbon in SCI) by dividing by 50\. 

```
Expected Lifespan = Baseline Lifespan × Circularity Factor
Circularity Factor = L / 50
```

**Why divide by 50?** So that the SCI-C score (0-100) maps linearly to a lifespan multiplier (0× to 2×)\! This means it can directly update an M value in an SCI calculation \- this is the magic that makes SCI-C interoperable with SCI:

| SCI-C Score (L) | Multiplier (circularity factor) | Meaning |
| :---- | :---- | :---- |
| 0 | 0× | Hardware is immediately obsolete |
| 25 | 0.5× | Poor circularity — retired at half the baseline lifespan |
| 50 | 1× | Baseline — industry average lifespan achieved |
| 80 | 1.6× | Good circularity — 60% longer than baseline |
| 100 | 2× | Maximum circularity — double the baseline lifespan |

The conversion is: **Multiplier \= SCI-C / 50**

We divide by 50 because the multiplier range (0× to 2×) is spread across a score range (0 to 100). Since 100 ÷ 2 \= 50, dividing the score by 50 gives the multiplier.

The larger the SCI-C, the larger the multiplier. This increases the denominator in the M calculation, leading to a lower SCI score.

The "baseline lifespan" (e.g., 4 years for servers) represents what typical hardware achieves today under average conditions — this corresponds to an SCI-C score of 50\.

**WHY?** This circularity factor creates a DIRECT INCENTIVE for organisations to use high-circularity strategies because this directly reduces their reported SCI score (because it spreads their emissions over a larger timespan).

```
Expected Lifespan = Baseline Lifespan × Circularity Factor
Circularity Factor = L / 100  (where L is SCI-C score, 0-100)

Example with high-circularity hardware (L = 80):
Expected Lifespan = 4 years × 1.6 = 6.4 years
M = 1000 kgCO2eq / 6.4 years = 156 kgCO2eq/year

Example with low-circularity hardware (L = 50):
Expected Lifespan = 4 years × 1.0 = 4 years
M = 1000 kgCO2eq / 4 years = 250 kgCO2eq/year
```

This rewards organizations that invest in circular hardware with lower M allocations, reflecting the reality that their hardware's embodied carbon is spread over more useful work.

#### 

#### 

#### Integration Pattern 2: Component-Level Attribution

When calculating M for a software application, SCI-C component scores can help attribute circularity responsibility.

**Scenario:** A SaaS application runs on cloud infrastructure. The overall SCI-C score is constrained by the S component (the application's increasing resource requirements).

```
Hardware (H): 80
Software (S): 55  ← limiting factor (application bloat)
Operations (O): 70
SCI-C Score (L): 55 (minimum)
```

In this case, the software team owns the circularity constraint. Their M allocation should reflect this:

```
M_software_adjusted = M_baseline × (100 / S)
                    = M_baseline × (100 / 55)
                    = M_baseline × 1.82
```

The software team's SCI score increases because their efficiency decisions are shortening hardware life.

#### Integration Pattern 3: Procurement Decisions Feeding SCI

Organizations can use SCI-C during hardware procurement to predict future SCI scores.

**Example: Comparing two server options**

| Factor | Server A | Server B |
| :---- | :---- | :---- |
| Purchase price | $10,000 | $12,000 |
| Embodied carbon | 800 kgCO2eq | 850 kgCO2eq |
| H score | 60 | 85 |
| Expected lifespan | 4 years | 6.8 years |
| Amortized M | 200 kgCO2eq/yr | 125 kgCO2eq/yr |

Server B has higher upfront embodied carbon but better circularity, resulting in lower annual M allocation. Over a 6-year planning horizon, Server B delivers lower total carbon intensity despite the higher initial footprint.

#### Integration Pattern 4: Second-Life Hardware Credits

When hardware is refurbished and redeployed, SCI-C can inform how to allocate embodied carbon across life cycles.

**Scenario:** A server with 1000 kgCO2eq embodied carbon serves two owners.

```
First life: 4 years at Company A
Second life: 3 years at Company B (purchased refurbished)

Option A: Split by time
- Company A: 1000 × (4/7) = 571 kgCO2eq
- Company B: 1000 × (3/7) = 429 kgCO2eq

Option B: Attribute to first owner, second life is "bonus"
- Company A: 1000 kgCO2eq (full allocation)
- Company B: 0 kgCO2eq (circularity benefit)

Option C: SCI-C informed split
- Company A's O4 (end-of-life pathway) score improves for choosing refurbishment
- Company B's embodied carbon = Refurbishment carbon only (~50 kgCO2eq)
- Original embodied carbon is fully amortized by extended total lifespan
```

SCI-C enables Option C by providing the framework to track and credit circularity actions.

#### Integration Pattern 5: Software Release Decisions

Software teams can use projected S component changes to forecast SCI impact before shipping updates.

**Example: Evaluating a proposed update**

```
Current state:
- Application supports hardware generations: N, N-1, N-2
- Sa2 (Requirements Trajectory): 70

Proposed update:
- Drops support for N-2
- Increases minimum RAM from 8GB to 16GB
- Projected Sa2: 45

SCI Impact Assessment:
- S component drops from 68 to 52
- Overall SCI-C drops from 65 to 52
- M_adjusted increases by 25%
- Estimated hardware retirement acceleration: 18 months across user base
```

This gives product teams a concrete sustainability cost for efficiency-reducing decisions.

#### Summary: Integration Options

| Pattern | Use Case | Who Benefits |
| :---- | :---- | :---- |
| Circularity-Adjusted Amortization | Accurate M calculation | SCI practitioners |
| Component-Level Attribution | Accountability for limiting factors | Software teams, operators |
| Procurement Decisions | Forward-looking SCI optimization | IT procurement |
| Second-Life Credits | Refurbishment value quantification | ITAD, refurbishers, buyers |
| Software Release Decisions | Pre-release impact assessment | Product teams |

This integration is optional. SCI-C provides value independently, but organizations using both standards gain more accurate carbon accounting and clearer accountability.

---

## 3\. Core Concepts

### 3.1 What is Circularity?

Circularity refers to maximizing the useful life extracted from hardware before end-of-life. The circular economy hierarchy, applied to hardware:

1. **Reduce** — Avoid acquiring unnecessary hardware  
2. **Extend** — Maximize useful life with current owner  
3. **Repair** — Fix failures to continue use  
4. **Refurbish** — Restore to good condition for continued/new use  
5. **Remanufacture** — Rebuild with mix of new and recovered components  
6. **Repurpose** — Deploy for a different function  
7. **Recycle** — Recover materials (last resort before disposal)

SCI-C focuses on measuring factors that enable or inhibit movement up this hierarchy.

### 3.2 The H-S-O Model

SCI-C uses a three-component model reflecting the three parties with agency over hardware circularity:

| Component | Name | Responsible Party | What It Captures |
| :---- | :---- | :---- | :---- |
| **H** | Hardware | Manufacturer | Design decisions affecting longevity, repairability, and support |
| **S** | Software | Platform & Application Developers | Software decisions affecting hardware requirements over time |
| **O** | Operations | Operator / Owner | Operational practices affecting utilization and maintenance |

The composite SCI-C score is a function of these three components:

```
L = f(H, S, O)
```

Each component is scored independently, enabling:

- Accountability for each party's contribution  
- Identification of which factor limits overall circularity  
- Targeted interventions

### 3.3 Lifecycle Awareness

The same hardware may have different SCI-C scores at different lifecycle stages:

- **First life (original deployment):** H from manufacturer, S from platform/app vendors, O from original operator  
- **Second life (refurbished):** H unchanged, but O score reflects refurbisher's contribution to extending life; S may change based on new workload

This enables refurbishment organizations to demonstrate the circularity value they create.

---

## 4\. Specification

### 4.1 H Component: Hardware Design

The H component measures manufacturer decisions that affect hardware longevity and circularity potential.

#### Factors

| Factor | Description | Measurement Approach |
| :---- | :---- | :---- |
| **H1: Repairability** | Ease of diagnosing and repairing failures | Repairability index (e.g., French repairability index, iFixit scores), parts availability commitment, repair documentation quality |
| **H2: Modularity** | Ability to upgrade/replace individual components | Number of user-replaceable components, use of standard interfaces (vs. proprietary/soldered) |
| **H3: Durability** | Physical build quality and expected lifespan | Design life specification, MTBF data, warranty period |
| **H4: Support Longevity** | Commitment to firmware, drivers, and security updates | Guaranteed support period (years), track record on previous products |
| **H5: Interoperability** | Use of open standards vs. proprietary lock-in | Standards compliance, vendor-neutral component compatibility |

#### Scoring

Each factor is scored 0-100. The H component score is a weighted average:

```
H = w1(H1) + w2(H2) + w3(H3) + w4(H4) + w5(H5)
where w1 + w2 + w3 + w4 + w5 = 1
```

Default weights: \[TBD based on empirical impact analysis\]

### 4.2 S Component: Software

The S component measures how software decisions affect hardware longevity. This component distinguishes between:

- **Platform software (Sp):** Operating systems, firmware, drivers, hypervisors—often controlled or influenced by hardware vendors  
- **Application software (Sa):** Workloads, applications, services—controlled by developers and operators

#### Platform Software Factors (Sp)

| Factor | Description | Measurement Approach |
| :---- | :---- | :---- |
| **Sp1: Support Duration** | How long the platform supports a given hardware generation | Years of support from hardware release date |
| **Sp2: Requirements Stability** | Whether platform updates increase hardware requirements | Resource delta between major versions (CPU, RAM, storage) |
| **Sp3: Backward Compatibility** | Ability to run on older hardware | Number of hardware generations supported |

#### Application Software Factors (Sa)

| Factor | Description | Measurement Approach |
| :---- | :---- | :---- |
| **Sa1: Efficiency Trend** | Whether updates improve or degrade resource efficiency | Resource consumption delta between versions for equivalent functionality |
| **Sa2: Requirements Trajectory** | Direction of minimum hardware requirements over time | Slope of min-spec requirements over release history |
| **Sa3: Graceful Degradation** | Ability to run in reduced mode on constrained hardware | Availability of "lite" modes, configurable quality/performance tradeoffs |
| **Sa4: Backward Compatibility Window** | How many hardware generations / OS versions are supported | Explicit support matrix breadth |

#### Scoring

```
Sp = weighted average of Sp1, Sp2, Sp3
Sa = weighted average of Sa1, Sa2, Sa3, Sa4
S = (Sp + Sa) / 2  [or weighted based on context]
```

### 4.3 O Component: Operations

The O component measures operational practices that affect hardware circularity.

#### Factors

| Factor | Description | Measurement Approach |
| :---- | :---- | :---- |
| **O1: Utilization** | How fully the hardware is used during its operational life | Average utilization rate over deployment period |
| **O2: Maintenance Practice** | Proactive maintenance to extend life | Preventive maintenance schedule adherence, component refresh practices |
| **O3: Lifespan Achieved** | Actual deployment duration vs. industry baseline | Years in production use / baseline expectation |
| **O4: End-of-Life Pathway** | Disposition at retirement | Hierarchy score: reuse \> refurbish \> recycle \> dispose |
| **O5: Refresh Policy** | Criteria for hardware retirement decisions | Whether retirement is needs-based vs. calendar-based |

#### Scoring

```
O = weighted average of O1, O2, O3, O4, O5
```

### 4.4 Composite Score Calculation

The overall SCI-C score combines the three components:

```
L = f(H, S, O)
```

#### Option A: Weighted Average

```
L = wH(H) + wS(S) + wO(O)
```

Simple, but masks which component is the limiting factor.

#### Option B: Minimum Component (Limiting Factor Model)

```
L = min(H, S, O)
```

Reflects that circularity is constrained by the weakest link. Hardware with excellent H but poor S (unsupported software) still has poor circularity.

#### Option C: Geometric Mean

```
L = (H × S × O)^(1/3)
```

Balances between average and minimum, penalizes low scores in any component.

**Recommendation:** Option B (minimum component) for the headline score, with all three component scores reported separately for actionability. This reflects the reality that a single low-scoring component can negate otherwise good circularity potential.

---

## 5\. Use Cases

### 5.1 Data Center Operators

**Scenario:** A cloud provider evaluating server procurement.

**Application:** Compare SCI-C scores (particularly H component) across vendors. Factor circularity into TCO calculations. Set procurement thresholds (e.g., "minimum H score of 70").

### 5.2 Hardware Manufacturers

**Scenario:** A server manufacturer designing next-generation hardware.

**Application:** Use H component factors as design requirements. Market circularity credentials with verifiable scores. Identify competitive differentiation opportunities.

### 5.3 Software Developers

**Scenario:** An application team planning a major update.

**Application:** Assess Sa score impact of proposed changes. Set efficiency budgets for updates. Report software circularity alongside other sustainability metrics.

### 5.4 Refurbishment Organizations

**Scenario:** An IT asset disposition (ITAD) company refurbishing enterprise hardware.

**Application:** Quantify the circularity value created by extending hardware life (improvement in O3, O4). Provide customers with circularity certificates. Demonstrate impact to sustainability-focused buyers.

### 5.5 Enterprise IT / Procurement

**Scenario:** A corporation managing end-user device fleet.

**Application:** Set device refresh policies based on SCI-C rather than arbitrary timelines. Evaluate repair vs. replace decisions. Choose software vendors partly based on Sa scores.

### 5.6 Policy Makers

**Scenario:** A regulator developing right-to-repair or sustainability disclosure requirements.

**Application:** Reference SCI-C as a measurement framework. Set minimum thresholds for public procurement. Require disclosure of H scores for hardware sold in jurisdiction.

---

## 6\. Areas to Explore

The following questions require further research, stakeholder input, and deliberation:

### 6.1 S Component Structure

- **Platform vs. Application distinction:** Is the Sp/Sa split the right model? Should firmware be separated from OS? How do we handle tightly integrated platform/application combinations (e.g., iOS)?  
    
- **Accountability boundaries:** When platform software is controlled by the hardware vendor (e.g., Dell firmware, Apple macOS), should this roll into H rather than S?  
    
- **Measuring software bloat:** How do we objectively measure "efficiency trend" when functionality also changes between versions? Need methodology for equivalent-function comparison.

### 6.2 Weighting and Aggregation

- **Factor weights:** What empirical basis should determine weights within each component? Should weights vary by hardware category (server vs. laptop vs. phone)?  
    
- **Aggregation method:** Is "minimum component" (Option B) the right headline approach, or does it create perverse incentives (neglecting non-limiting components)?  
    
- **Normalization:** How do we ensure scores are comparable across hardware categories?

### 6.3 Data Availability

- **Manufacturer data:** Will manufacturers provide the data needed for H scoring? What verification mechanisms are needed?  
    
- **Software telemetry:** How do we measure Sa factors without intrusive monitoring? Can we use benchmark-based approaches?  
    
- **Self-reporting vs. third-party verification:** What's the assurance model?

### 6.4 Scope Boundaries

- **Component-level scoring:** Should SCI-C apply at the device level, or should components (CPU, RAM, SSD) have individual scores?  
    
- **Supply chain:** Does H extend to component sourcing (e.g., conflict minerals, supplier labor practices), or is that out of scope?  
    
- **Network effects:** How do we handle hardware whose circularity depends on ecosystem factors (e.g., EV chargers, IoT devices)?

### 6.5 Temporal Dynamics

- **Score evolution:** Should SCI-C scores be static (assigned at manufacture) or dynamic (updated as support periods end, efficiency data emerges)?  
    
- **Forecasting vs. actuals:** H and S scores are partly predictive (support commitments). How do we handle vendors who don't meet commitments?

### 6.6 Relationship to Existing Frameworks

- **French Repairability Index:** How does SCI-C's H component relate to existing repairability regulations? Harmonization opportunities?  
    
- **EPEAT:** Relationship to existing green electronics certification?  
    
- **EU Circular Economy Action Plan:** Alignment with regulatory direction?

### 6.7 Gaming and Perverse Incentives

- **Cheap longevity:** Could a vendor score well on H by building hardware that lasts but performs poorly? Do we need performance/efficiency floors?  
    
- **Support theater:** How do we distinguish genuine long-term support from nominal commitments that aren't honored?

---

## 7\. Governance and Next Steps

### 7.1 Proposed Development Path

1. **Socialize concept** — Share this proposal with stakeholders for initial feedback  
2. **Form working group** — Recruit representatives from hardware manufacturers, cloud providers, software developers, refurbishment industry, and sustainability experts  
3. **Empirical research** — Study factor weights, validate measurement approaches, pilot with willing participants  
4. **Draft specification v1.0** — Formalize based on learnings  
5. **Pilot program** — Test with early adopters, refine based on implementation experience  
6. **Publication** — Release as open standard

### 7.2 Governance Questions

- **Home organization:** Should SCI-C live under the Green Software Foundation (alongside SCI), a hardware-focused body, or independently?  
    
- **Maintenance model:** How are updates to the standard governed? What's the change process?  
    
- **Certification/verification:** Is there a certification program, or is it self-assessed with optional third-party verification?

---

## 8\. Glossary

| Term | Definition |
| :---- | :---- |
| **Circularity** | The degree to which a product's full useful life potential is realized, through extended use, repair, refurbishment, or reuse |
| **Embodied carbon** | Greenhouse gas emissions from manufacturing, transporting, and disposing of hardware (as distinct from operational emissions) |
| **Functional obsolescence** | Hardware retirement due to inability to meet current requirements (performance, compatibility, support), despite physical functionality |
| **Physical obsolescence** | Hardware retirement due to physical failure or degradation |
| **SCI** | Software Carbon Intensity, a Green Software Foundation standard measuring carbon emissions per unit of software work |
| **SCI-C** | Software Carbon Intensity \- Circular, this proposed standard for measuring hardware circularity |

---

## Appendix A: Example Scoring (Illustrative)

*This example is illustrative only and does not represent actual scores.*

### Example: Enterprise Server (First Life)

**H Component (Hardware):**

| Factor | Score | Notes |
| :---- | :---- | :---- |
| H1: Repairability | 75 | Good parts availability, documentation could improve |
| H2: Modularity | 85 | Standard DIMMs, NVMe, CPU socketed |
| H3: Durability | 80 | 5-year design life, good MTBF |
| H4: Support Longevity | 70 | 5-year firmware commitment |
| H5: Interoperability | 90 | Standard interfaces throughout |
| **H Total** | **80** |  |

**S Component (Software):** 

| Factor | Score | Notes |
| :---- | :---- | :---- |
| Sp1: Support Duration | 65 | OS vendor support tied to vendor agreement |
| Sp2: Requirements Stability | 70 | Modest increases in recent versions |
| Sp3: Backward Compatibility | 75 |  |
| Sa1: Efficiency Trend | 60 | Primary workload has become heavier |
| Sa2: Requirements Trajectory | 55 | Min specs increasing \~15%/year |
| Sa3: Graceful Degradation | 70 | Some configurability |
| Sa4: Backward Compatibility | 65 | 3 generations supported |
| **S Total** | **66** |  |

**O Component (Operations):** 

| Factor | Score | Notes |
| :---- | :---- | :---- |
| O1: Utilization | 45 | Average 30% utilization |
| O2: Maintenance Practice | 80 | Good PM program |
| O3: Lifespan Achieved | 60 | 4 years vs 5-year baseline |
| O4: End-of-Life Pathway | 75 | Sold to refurbisher |
| O5: Refresh Policy | 50 | Calendar-based 4-year refresh |
| **O Total** | **62** |  |

**Composite Score:**

- Weighted average: 69  
- Minimum (limiting factor): 62 (Operations)  
- Geometric mean: 69

**Interpretation:** Operations is the limiting factor. Despite reasonable hardware and software scores, calendar-based refresh policies and low utilization constrain circularity. Recommended interventions: utilization optimization, needs-based refresh criteria.

---

*Document version: 0.1 draft* *Feedback welcome: \[contact TBD\]*  

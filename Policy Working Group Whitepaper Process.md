# Policy Working Group Whitepaper Process

## A Guide to Topic Selection, Drafting, Review, and Publication

**Version**: 1.0 **Date**: March 2026

---

## 1\. Purpose

This document describes the process by which Green Software Foundation working groups produce whitepapers. It covers the structure of a whitepaper, how topics are selected, how papers are drafted and approved, how authorship works, and how papers are published and promoted.

The aim is a repeatable two-week cadence from approved topic to published paper, with enough structure to maintain quality and consistency across working groups while leaving room for variation in format and depth depending on the subject.

---

## 2\. Whitepaper Structure

### 2.1 Common Elements

Every whitepaper will have its own specific requirements and the appropriate aper structure may vary, but as a heuristic, a whitepaper is expected to include the following elements, with ordering and relative weight varying by topic:

| Element | Purpose | Notes |
| :---- | :---- | :---- |
| **Title and subtitle** | Identifies the paper and frames its scope | Title should be concise. Subtitle provides context (e.g., jurisdiction, standard, use case). |
| **Metadata block** | Version, date, authoring working group, status | See Section 5 on authorship. Status is either "Working Draft" or "Published". |
| **Abstract or executive summary** | Self-contained summary of the paper's argument and conclusions | Should be readable standalone. 200–400 words. State the problem, the argument, key evidence, and the conclusion. |
| **Table of contents** | Navigation | Numbered sections with anchor links. |
| **Body sections** | The argument | See 2.2 below. |
| **Conclusions** | Summary of the argument and its implications | Should echo the abstract but with the benefit of the evidence presented. Not merely a restatement — add the "so what." |
| **Sources** | Full references | Grouped by category (see 2.3). |

### 2.2 Body Structure

The body should ideally follow a **problem → evidence → analysis → implications** arc. This might not work universally for all topics, but the following patterns have worked well and should be used as a starting point:

**For policy-facing papers** (e.g., regulatory responses, position papers):

1. Context and problem statement  
2. Evidence and technical analysis  
3. Policy implications or regulatory mapping  
4. Barriers, limitations, and counter-arguments  
5. Recommendations

**For technical papers** (e.g., new standards, measurement frameworks):

1. Problem statement  
2. Relationship to existing standards or frameworks  
3. Core concepts and specification  
4. Use cases  
5. Open questions and areas to explore  
6. Governance and next steps

**For landscape or comparative papers** (e.g., technology comparisons, market analysis):

1. Framing and context  
2. Taxonomy or comparative framework  
3. Detailed analysis by category  
4. Critical assessment  
5. Implications and recommendations

These are templates, not rigid requirements. The right structure is the one that serves the argument.

### 2.3 Style and Tone

The following principles are drawn from the existing portfolio and should guide all papers:

**Evidence-first.** Claims should be supported by citations. Where the evidence is strong, say so. Where it is early-stage, contested, or limited, say that too. Do not overstate.

**Balanced and honest.** Every paper should acknowledge counter-arguments, limitations, and open questions. A paper that presents only the favourable case for a position undermines the GSF's credibility as a standards body. The phrase "necessary but not sufficient" captures the tone well — advocate for the position, but be honest about its boundaries.

**Accessible to a mixed audience.** Papers will be read by both policymakers and technical practitioners. Use plain language where possible. Define technical terms on first use. Use tables to make comparisons concrete.

**Specific and actionable.** Recommendations should be concrete enough to act on. "Ofgem should consider flexibility as a readiness criterion" is better than "regulators should think about sustainability." Where possible, suggest thresholds, timelines, or mechanisms.

**Properly cited.** All factual claims and data points should have inline citations with hyperlinks. The sources section at the end should group references by type:

- Peer-reviewed papers  
- Preprints and working papers  
- Institutional and industry reports  
- Standards and regulatory sources

### 2.4 Formatting Conventions

- Markdown format throughout  
- Numbered sections (1, 1.1, 1.1.1) with heading levels matching depth  
- Tables for comparisons, data summaries, and structured arguments  
- **Bold** for key terms and emphasis; *italics* for titles and nuance  
- British English spelling for UK-facing papers; American English acceptable for US-facing papers  
- Metadata block on every paper: Version, Date, Author (working group name), Status

---

## 3\. Topic Selection

### 3.1 How Topics Are Identified

Topics come from two sources:

1. **GSF staff proposals.** Staff monitor the regulatory, standards, and industry landscape and propose topics to relevant working groups. This is expected to be the primary source in the early phase of the programme, but we aim to phase this out over time in favour of topics proposed by members themselves, especialy in response to new policies, regulations or other moments int he software space.  
     
2. **Working group member proposals.** Over time, WG members will identify topics themselves — opportunities, gaps in the literature, emerging policy questions. Members propose topics during WG meetings or asynchronously. We want this to become the primary source of topics over time.

### 3.2 Criteria for a Good Topic

A whitepaper topic should meet at least two of the following:

- **Timely**: responds to a live regulatory consultation, policy development, or industry debate  
- **Relevant to GSF standards**: connects to SCI, SCI for AI, SCI-C, or other GSF specifications  
- **Useful to members**: addresses a question that GSF members are actually facing  
- **Gap-filling**: provides analysis or a framework that doesn't exist elsewhere  
- **Credible for the WG**: falls within the authoring working group's domain expertise

### 3.3 Approval and Backlog

Topics are approved by a motion of the relevant working group. Once approved, they go onto the **whitepaper backlog** — a simple ordered list maintained by GSF staff. The backlog is worked in priority order, with one paper in active production at a time per working group. Working groups may reprioritise the backlog at any meeting.

---

## 4\. Drafting, Review, and Approval

### 4.1 Target Cadence

The target is **two weeks from approved topic to published paper**. This is achievable for most papers but should not be treated as a hard deadline — quality matters more than speed. Complex papers (e.g., new standard proposals, multi-jurisdiction regulatory analysis) may take longer.

### 4.2 Process Steps

| Step | Owner | Duration | Output |
| :---- | :---- | :---- | :---- |
| **1\. Topic approved** | Working group (motion) | WG meeting | Topic added to backlog |
| **2\. Research and first draft** | GSF staff | 3–5 working days | Complete first draft in markdown |
| **3\. WG review period** | Working group members | Until next WG call | Comments: proposed changes and discussion points |
| **4\. WG call: resolve comments** | Working group (on call) | WG meeting | Changes merged or rejected; open points resolved |
| **5\. Approval** | Working group (motion) | Same call or next | Paper approved for publication |
| **6\. Publication and promotion** | GSF staff \+ comms | 1–2 working days | Live on website, promoted |

### 4.3 Step Details

**Step 2: Research and first draft.** GSF staff produce a complete first draft, including research, evidence gathering, and structuring the argument. AI tools may be used to assist with research, drafting, and synthesis. The draft should be complete enough for the WG to review substantively — not an outline or skeleton.

**Step 3: WG review period.** The draft is shared with the working group via the group's usual collaboration channel. Between calls, members review the draft and submit comments. Comments should take one of two forms:

- **Proposed changes**: specific edits, additions, or deletions the member wants made to the text. These should be concrete enough to action directly (e.g., "replace paragraph X with Y" or "add the following sentence after section Z").  
- **Discussion points**: questions, concerns, or areas of disagreement that require group deliberation before a change can be proposed.

**Lack of feedback is interpreted as tacit endorsement.** Members who do not comment on the draft are taken to have no objections to its content.

**Step 4: WG call — resolve comments.** All comments are addressed on the next working group call:

- **Proposed changes** are reviewed one by one. A change is **merged into the draft if there are no objections** from any member present. If a member objects, the point becomes a discussion item and the group seeks resolution — which may mean amending the change, dropping it, or deferring it.  
- **Discussion points** are debated on the call and either resolved (resulting in a specific change or a decision to leave the text as-is) or deferred for further input.

If all comments are resolved and the group is satisfied, the paper moves directly to approval. If significant changes are needed, the revised draft goes through another review cycle before the next call.

**Step 5: Approval.** The working group approves the final paper by motion. This can happen at the same call where comments are resolved or, if a further review cycle was needed, at the following call.

---

## 5\. Authorship

### 5.1 The Working Group Is the Author

All whitepapers are authored by the working group, never by named individuals. The metadata block should read:

**Author**: GSF \[Working Group Name\]

For example:

- **Author**: GSF Policy Working Group  
- **Author**: GSF Software Standards Working Group  
- **Author**: GSF Hardware Standards Working Group

### 5.2 Rationale

Working group authorship reflects several principles:

- **Collective ownership.** The paper represents the working group's consensus position, not any individual's view.  
- **Member protection.** Members contribute freely knowing their individual names will not be attached to positions that may be commercially sensitive.  
- **Institutional credibility.** The GSF's working groups carry authority as multi-stakeholder bodies.

### 5.3 Acknowledgements

Where individuals or organisations make substantial contributions (e.g., providing data, drafting specific sections, or conducting specialist review), they may be acknowledged in a brief acknowledgements note at the end of the paper, before the sources section. This is optional and at the WG's discretion.

### 5.4 The GSF Is Not the Author

Papers are authored by their working groups, not by the GSF itself. This distinction matters: a working group position is the consensus of its participating members on a specific topic. It does not necessarily represent the GSF's institutional position on that topic or any other.

---

## 6\. Publication

### 6.1 Publication Venue

Papers are published on the GSF website in a dedicated section accessible from the main navigation. This section should list all published whitepapers with:

- Title and subtitle  
- Authoring working group  
- Publication date  
- Abstract or one-line summary  
- Link to the full paper (rendered markdown or PDF)

Papers may also be submitted directly to external recipients where relevant (e.g., regulatory consultations, standards bodies). In such cases, the website publication serves as the canonical version.

### 6.2 Format

Papers are authored in markdown and published in two formats:

- **Web**: rendered on the GSF website for online reading  
- **PDF**: downloadable version for offline reading and formal submissions

Both should preserve formatting, tables, and hyperlinks.

### 6.3 Promotion

Once published, GSF staff coordinate promotion through some or all of the following channels:

| Channel | Action | Owner |
| :---- | :---- | :---- |
| **GSF website** | Publish to whitepapers section | Staff / web team |
| **Member newsletter** | Include in next newsletter with summary and link | Staff / comms |
| **LinkedIn (GSF account)** | Post with key findings and link | Staff / comms |
| **LinkedIn (WG members)** | Encourage members to share via their own networks | WG members (voluntary) |
| **Working group channels** | Notify all WGs of publication | Staff |
| **Relevant external audiences** | Share with cited organisations, regulators, or media as appropriate | Staff / comms |

For papers responding to regulatory consultations, the submission to the regulator takes priority and should happen before or simultaneously with public promotion.

---

## 7\. Quick Reference

```
Topic proposed → WG approves by motion → Backlog
                                            ↓
                              GSF staff produces first draft (3-5 days)
                                            ↓
                              WG members comment with proposed changes
                              and discussion points (until next call)
                                            ↓
                              WG call: resolve all comments
                              Changes merged if no objections
                              No comment = tacit endorsement
                                            ↓
                              WG approves by motion
                                            ↓
                              Publish to website + promote
```

**Target cadence**: 2 weeks, topic to publication

**Author**: Always the working group, never individuals or the GSF

**Quality bar**: Evidence-based, balanced, honest about limitations, specific in recommendations

**Review principle**: Changes merge only if no member objects. Silence is consent.

---

**Document Version**: 1.0 **Last Updated**: 2026-03  

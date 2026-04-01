# Campaign Brief Skill — Input Guide

This file defines how to handle every input type the campaign-brief skill
may receive. It covers how to read each input, what to extract from it,
and how to behave when inputs are missing or incomplete.

---

## Input Types and What to Extract

### 1. Research Notes

**Format:** Pasted text, uploaded document, summarized findings

**What to extract:**
- Market context (size, trends, shifts)
- Customer language (exact phrases customers use to describe the problem)
- Behavioral data (what customers do, how they buy)
- Sentiment or frustration signals
- Any quotes, verbatims, or stated preferences

**How to use it:**
- Mine for the Core Insight (Section 3) — research notes are the primary
  source for identifying what is genuinely true about the audience or market
- Use exact customer language in the messaging framework where possible
- Flag any claim from research that lacks a clear source as [ASSUMPTION]

**If not provided:**
- Note in Input Summary: "Research notes: Not provided"
- Label all audience and insight content [ASSUMPTION]
- Add to Section 9: "No research provided — audience insights and core
  insight are assumed. Recommend customer interviews or survey data before
  finalizing campaign direction."

---

### 2. Campaign Goals

**Format:** Written objectives, OKRs, stated outcomes, business targets

**What to extract:**
- Primary campaign objective (what success looks like)
- Business goal this campaign serves (revenue, retention, awareness)
- Measurable targets if stated (signup numbers, revenue, leads)
- Timeline or launch window
- Any constraints (budget cap, geographic limits, excluded audiences)

**How to use it:**
- Populate Section 1 (Campaign Overview) directly
- Use the objective to filter channel recommendations — only include
  channels that plausibly serve the stated goal
- Use the goal to make the CTA direction specific

**If not provided:**
- This is the one input worth pausing for. If no campaign goal is stated
  at all, ask one focused question: "What is the primary goal of this
  campaign — e.g., drive trial signups, increase sales, build awareness,
  re-engage lapsed customers?"
- Do not proceed with a completely goalless brief — it will produce
  generic output that cannot be evaluated for effectiveness

---

### 3. Audience Data

**Format:** Personas, customer segments, survey results, interview notes,
CRM data descriptions, behavioral profiles

**What to extract:**
- Who the primary audience is (role, industry, life stage, behavior)
- What they care about (goals, values, ambitions)
- What frustrates them (pain points, friction)
- What motivates a purchase or conversion decision
- Objections or barriers they commonly have
- Where they spend time (platforms, communities, media channels)

**How to use it:**
- Populate Section 2 (Audience Summary) directly
- Use audience motivations to shape the emotional angle in messaging
- Use platform behavior to inform channel selection
- Use objections to ensure the messaging framework addresses barriers

**If not provided:**
- Label all of Section 2 with: "Based on available inputs — audience
  not explicitly provided. All content in this section is [ASSUMPTION]."
- Add to Section 9: "No audience data provided — audience profile is
  assumed from product/offer context. Validate with customer research
  before committing to this targeting."

---

### 4. Product / Offer Information

**Format:** Product description, feature list, pricing, launch announcement,
landing page copy, sales deck, offer details

**What to extract:**
- What the product or service does
- The primary differentiator or most compelling capability
- Specific proof points (speed, cost, results, features)
- The offer structure (free trial, discount, demo, launch price)
- Any technical or functional constraints that affect messaging

**How to use it:**
- Use differentiators to build the Positioning Direction (Section 4)
- Use specific features or results as proof points in the Messaging
  Framework (Section 5)
- Use the offer structure to write a specific CTA direction
- Avoid overstating what the product does — stay within what was provided

**If not provided:**
- Note in Input Summary: "Product / offer info: Not provided"
- Use whatever product context can be inferred from goals or other inputs
- Label all product claims [ASSUMPTION]
- Add to Section 9: "No product details provided — messaging framework
  lacks specific proof points. Add feature specifics or customer results
  before writing ad copy."

---

### 5. Competitor Insights

**Format:** Competitive analysis, notes on competitor positioning, SWOT
observations, market gap descriptions, user-provided comparisons

**What to extract:**
- What competitors are saying / how they position
- What they are NOT saying (gaps or whitespace)
- Common themes in competitor messaging (what to avoid or differentiate from)
- Any perceived weaknesses or user complaints about competitors

**How to use it:**
- Use whitespace to sharpen Positioning Direction (Section 4)
- Inform tagline options — make sure recommended taglines do not echo
  competitor language
- Use weaknesses to strengthen proof points in the Messaging Framework

**If not provided:**
- Do not invent competitive context
- Note in Section 9: "Competitor positioning not reviewed — positioning
  direction may inadvertently overlap with competitor messaging. Recommend
  a brief competitive scan before campaign launch."

---

## Handling Combinations of Inputs

| Inputs Provided | Expected Quality | Key Instructions |
|----------------|-----------------|-----------------|
| All 5 types | Full brief, minimal assumptions | Label only inferences; produce complete brief |
| Goals + Product + Audience | Strong brief | Core insight and positioning may need inference; label clearly |
| Goals + Research only | Solid foundation | Audience and product sections will need [ASSUMPTION] labels |
| Goals + Product only | Workable brief | Audience, insight, and channel fit will be assumed heavily |
| Research + Audience only | Good insight quality; weak execution | Objectives unclear — ask for campaign goal before writing |
| Only product info | Thin brief | Ask for at least one goal; everything else [ASSUMPTION] |
| Only goals stated | Skeletal brief | Almost everything will be [ASSUMPTION]; brief is a starting scaffold |

---

## Input Formatting Notes

- **Pasted text:** Read as-is. Do not reformat or summarize before
  extracting. Quote relevant sections directly in the brief.
- **Uploaded documents:** Process in full before extracting. Note document
  title or type in the Input Summary.
- **Bullet lists:** Treat each bullet as a discrete data point. Do not
  assume connections between bullets that are not stated.
- **Contradictory inputs:** If two inputs conflict (e.g., different audience
  descriptions), note both and choose the more specific or recent one.
  Label the choice: "Using [description] from [input source]; [other
  description] noted but not used — reconcile before finalizing."
- **Very long inputs:** Summarize the most strategically relevant sections
  in the brief. Do not reproduce entire documents.

---

## What This Skill Does Not Accept

This skill is not designed for the following — redirect to appropriate tools:

| Input Type | What to Do Instead |
|-----------|-------------------|
| Meta Ads CSV / performance data | Use the campaign-report skill |
| Analytics dashboard exports | Use the campaign-report skill |
| Raw survey data requiring statistical analysis | Summarize first, then use this skill |
| Financial models or pricing analysis | Outside this skill's scope |
| Technical product specs (API docs, engineering specs) | Extract relevant messaging-friendly content first |

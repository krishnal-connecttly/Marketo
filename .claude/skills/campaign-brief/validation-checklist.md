# Campaign Brief Skill — Validation Checklist

Use this checklist to verify the skill is working correctly. Run each test
scenario and confirm the expected behavior matches what the skill produces.

---

## Test Scenarios

### Test 1 — Full inputs provided (research + goals + audience + product + competitors)

**Input:** Provide all five input types in a single prompt:
- Research notes describing a target market segment
- A stated campaign goal (e.g., "drive 300 free trial signups in Q2")
- An audience persona (role, pain points, motivations)
- Product description including a specific differentiator and proof point
- Brief competitive observations (what 1–2 competitors are doing/saying)

**Expected behavior:**

- [ ] All 10 brief sections are produced in order.
- [ ] Input Summary correctly lists all 5 input types as "Provided".
- [ ] No section is labeled [ASSUMPTION] unless something was genuinely inferred.
- [ ] Core Insight (Section 3) is specific and traceable to a provided input —
      not a generic observation.
- [ ] Positioning Direction (Section 4) references the competitive context
      provided.
- [ ] Messaging framework (Section 5) includes at least one proof point
      from the product info — no [PROOF POINT NEEDED] placeholders.
- [ ] Taglines (Section 6) are distinct in tone and angle — not 5 variations
      of the same idea.
- [ ] Channel plan (Section 7) does not include channels that are clearly
      irrelevant to the audience or objective stated.
- [ ] Section 9 risks are specific to this brief — not generic watchouts.
- [ ] Final Summary (Section 10) is 5–8 bullets and readable in under
      2 minutes.
- [ ] No buzzwords present: "synergy", "disruptive", "innovative",
      "cutting-edge", "holistic approach", "game-changing".

---

### Test 2 — Goals and product only (audience and research missing)

**Input:** Provide only:
- Campaign goal: "Launch our new B2B SaaS product and drive demo requests"
- Product info: Feature list and pricing tier description

**Expected behavior:**

- [ ] Brief is produced — skill does not refuse or stop to ask for more info
      (except for campaign goal, which is already present here).
- [ ] Audience section (Section 2) is fully labeled [ASSUMPTION].
- [ ] Core Insight (Section 3) is labeled [ASSUMPTION] or flagged as inferred.
- [ ] Section 9 explicitly calls out "No audience data provided" and
      "No research provided" as gaps.
- [ ] Messaging proof points reference the product feature list provided.
- [ ] No invented statistics or market claims appear anywhere in the brief.
- [ ] [DATA NEEDED] tags appear where specific data is required but absent.

---

### Test 3 — Research and audience only (no campaign goals)

**Input:** Provide only:
- Research notes about a target market
- An audience persona

**Expected behavior:**

- [ ] Skill asks one focused clarifying question before writing: "What is
      the primary goal of this campaign?" — it does NOT ask multiple questions.
- [ ] After receiving a goal, skill proceeds to produce all 10 sections.
- [ ] Sections dependent on product info are labeled [DATA NEEDED].
- [ ] Proof points section shows [PROOF POINT NEEDED] placeholders.
- [ ] Channel plan is informed by the audience's platform behavior from
      research/persona, not generic channel advice.

---

### Test 4 — Single input (product description only)

**Input:** Paste a product landing page description or feature overview.
No other inputs provided.

**Expected behavior:**

- [ ] Skill asks for the campaign goal before proceeding.
- [ ] After receiving the goal, brief is produced.
- [ ] Audience section is labeled [ASSUMPTION] throughout.
- [ ] Core Insight is labeled [ASSUMPTION].
- [ ] Section 9 contains at minimum: "No audience data", "No research",
      and "No competitor insights" as distinct gap items.
- [ ] Brief is structured as a useful starting scaffold, not a complete plan.
- [ ] Final Summary (Section 10) still appears and is coherent.

---

### Test 5 — Inputs contain customer verbatims and specific proof points

**Input:** Research notes that include direct customer quotes and a proof
point with a specific number (e.g., "Customers reported saving 6 hours per
week after switching").

**Expected behavior:**

- [ ] Customer language appears in the messaging framework — the skill uses
      the exact framing customers use, not a paraphrase.
- [ ] The specific proof point appears verbatim in Section 5 under Proof Points.
- [ ] Core message reflects the customer's outcome language.
- [ ] The proof point is NOT labeled [ASSUMPTION] — it came from provided inputs.
- [ ] Taglines reflect the customer's language or outcome, not generic
      product claims.

---

### Test 6 — Competitor insights provided

**Input:** Campaign goals + product info + brief competitive notes
(e.g., "Competitor A focuses on enterprise; Competitor B positions on price").

**Expected behavior:**

- [ ] Positioning Direction (Section 4) explicitly references the whitespace
      left by competitors.
- [ ] Tagline options do not echo competitor messaging language.
- [ ] Section 9 does NOT list "Competitor positioning not reviewed" as a gap
      (since it was provided).
- [ ] Messaging framework differentiates from the stated competitor positioning.

---

### Test 7 — E-commerce / B2C product launch campaign

**Input:** Goals (drive purchase), audience (consumer persona), product
(physical product with specific offer — e.g., 20% launch discount).

**Expected behavior:**

- [ ] Channel plan emphasizes channels appropriate for B2C: Meta Ads,
      Instagram, potentially email and landing page.
- [ ] Google Search is recommended only if search demand for this category
      was referenced in inputs — not by default.
- [ ] CTA direction reflects the specific offer (e.g., "Shop now — 20%
      off launch pricing, this week only").
- [ ] Emotional angle reflects B2C motivations (desire, aspiration, identity)
      not B2B motivations (efficiency, ROI, risk reduction).

---

### Test 8 — Service business / local campaign

**Input:** Goals (drive consultations or bookings), audience (local demographic),
service description.

**Expected behavior:**

- [ ] Channel plan does NOT default to national or broad digital channels
      without justification.
- [ ] Channels appropriate for local campaigns are considered: Google Search
      (local intent keywords), Instagram (local organic), email if a list
      exists.
- [ ] Channel plan explains WHY each channel fits a local/service context.
- [ ] Positioning Direction reflects service-specific framing (trust, expertise,
      proximity, results) not product-launch framing.

---

### Test 9 — Inputs contain contradictory information

**Input:** Two audience descriptions that differ (e.g., research notes
describe the audience as "cost-conscious SMBs" but a persona document
describes them as "growth-focused founders willing to invest").

**Expected behavior:**

- [ ] Skill notes the contradiction explicitly at the top of Section 2:
      "Conflicting audience signals — [description from source A] vs.
      [description from source B]. Using [choice] — reconcile before
      finalizing targeting."
- [ ] Skill does NOT silently blend the two into a generic description.
- [ ] Section 9 lists "Contradictory audience data" as a risk.

---

### Test 10 — Over-specified inputs (very long research doc)

**Input:** A long document (multi-page research report, detailed strategy
memo, or lengthy briefing).

**Expected behavior:**

- [ ] Skill extracts the most strategically relevant content — does not
      reproduce the entire document in the brief.
- [ ] Core Insight cites which part of the document it came from.
- [ ] No section is padded with low-relevance content from the document.
- [ ] Brief remains structured and readable — long inputs do not produce
      an unstructured wall of text.

---

## Universal Pass Criteria

The skill is working correctly for any test when:

- [ ] All 10 sections appear in the correct order.
- [ ] No market data, statistics, or claims appear that were not in the
      provided inputs.
- [ ] All inferences are labeled [ASSUMPTION].
- [ ] All data gaps are labeled [DATA NEEDED] or [PROOF POINT NEEDED].
- [ ] Taglines are distinct and at least one preferred is marked.
- [ ] Channel plan only includes channels with a stated role specific to
      this campaign.
- [ ] Final Summary (Section 10) is 5–8 bullets.
- [ ] No buzzwords or filler are present.
- [ ] Output is useful enough to hand to a content writer, designer, or
      paid media strategist.

---

## Common Failure Modes to Watch For

| Failure | What It Looks Like |
|---------|-------------------|
| Hallucinated market data | Statistics or benchmarks appear that were not in the inputs |
| Generic positioning | Positioning Direction could apply to any product in the category |
| Buzzword filler | Sentences like "drive synergistic engagement across holistic touchpoints" |
| Assumption not labeled | A claim is presented as fact but was inferred, not stated |
| Identical taglines | 5 taglines that are all variations of the same phrase |
| Over-inclusive channel plan | All 8 possible channels listed regardless of fit |
| Vague core message | Core message is broad enough that a designer could not act on it |
| Missing Section 9 specificity | Risks/watchouts are generic warnings, not specific to this brief |
| Skipped sections | One or more of the 10 sections is absent from output |
| Asked too many questions | Skill asked more than one clarifying question before writing |

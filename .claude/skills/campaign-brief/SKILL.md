---
description: >
  Use this skill when a user wants to turn research, campaign context, or
  brand inputs into a structured campaign brief. Trigger when: (1) a user
  provides research notes, audience data, campaign goals, product info, or
  competitor insights and wants a campaign plan; (2) a strategist needs
  messaging direction, tagline options, and a channel plan in one document;
  (3) a user needs a structured campaign brief before creating content, ads,
  or strategy decks; (4) the user says "create a campaign brief", "build a
  campaign plan", "turn this research into a brief", or "I need a messaging
  framework". Primary audience: internal marketing teams including
  strategists, content writers, designers, and paid media specialists.
  Output style: full structured document, all 10 sections, optimized for
  handoff to creative, content, and paid media teams.
  Do NOT trigger for: campaign performance reporting, ad data analysis,
  dashboards, or analytics requests — use the campaign-report skill instead.
---

# Campaign Brief Skill

## Purpose

Turn research, audience data, campaign goals, product information, and
competitor insights into a complete, actionable campaign brief. This skill
produces a structured document that marketing teams can use as the planning
foundation for content, ads, creative direction, and strategy decks.

This is a **strategy and planning skill**. It synthesizes inputs into
decisions. It does not produce analytics reports, dashboards, or performance
summaries.

---

## Step 1 — Ingest and assess the inputs

When the user provides inputs (research notes, pasted text, audience summaries,
product descriptions, competitor observations, campaign goals, or any
combination), do the following before writing the brief:

1. **Identify what has been provided.** List the input types present:
   research notes, audience data, campaign goals, product info, competitor
   insights. Note what is present and what is missing.

2. **Assess completeness.** A strong brief needs at minimum: a product or
   offer, a target audience, and a campaign objective. If any of these three
   are absent, note it clearly at the top of the brief as a gap — but still
   produce the brief using what is available.

3. **Separate facts from assumptions.** Anything stated directly in the
   provided inputs is a fact for purposes of this brief. Anything you infer
   or extrapolate must be labeled `[ASSUMPTION]`. Never present an assumption
   as a confirmed fact.

4. **Handle partial inputs.** If the user provides only partial information,
   generate the brief using what is available. Label all sections that rely
   on assumptions with a note at the top of that section: `Based on
   available inputs — assumptions marked below.`

5. **Do not invent market data.** Do not cite statistics, benchmarks, or
   market figures that were not provided by the user. If a claim would
   strengthen the brief but no data supports it, write `[DATA NEEDED]`
   instead.

6. **Competitor insights.** If competitor information is provided, use it to
   sharpen positioning and identify whitespace. If it is not provided, note
   this as a gap in Section 9 (Key Risks / Watchouts) but do not fabricate
   competitive observations.

---

## Step 2 — Write the campaign brief

Use the output template in `brief-template.md`. Follow every section in order.
Apply these rules throughout:

### General rules

- **Ground everything in the inputs.** Every strategic recommendation must
  trace back to something the user provided — research, a stated goal, an
  audience insight, or product information. If a recommendation is your
  inference from the inputs, label it `[ASSUMPTION]`.
- **Be decisive.** Do not hedge every sentence. Make clear strategic
  recommendations. Where evidence is strong, say so. Where it is weak, label
  it and say so — then still make the recommendation.
- **No buzzwords.** Avoid vague marketing language: "synergy", "disruptive",
  "innovative", "cutting-edge", "game-changing", "holistic approach". Use
  plain strategic language instead.
- **No generic filler.** Every section must be specific to the inputs
  provided. Generic copy-paste advice that could apply to any campaign is
  prohibited.
- **Prefer specificity.** "Email nurture sequence targeting users who
  visited the pricing page" is better than "email marketing". "Drive free
  trial signups from SMB founders" is better than "increase awareness".
- **Separate facts, assumptions, and recommendations.** Use these labels
  consistently throughout:
  - `[FACT]` — stated directly in the provided inputs
  - `[ASSUMPTION]` — inferred from the inputs; needs validation
  - `[RECOMMENDATION]` — strategic direction based on available context
  - `[DATA NEEDED]` — a specific gap that should be filled before launch

### Messaging rules

- The core message must be a single, clear statement of what the campaign
  communicates to the audience. It should be specific enough that a designer
  or copywriter could act on it.
- Supporting messages should ladder up to the core message, not repeat it.
- Emotional angle must reflect something real about the target audience's
  psychology — grounded in audience data or research if provided.
- Proof points must come from the user's inputs (product features, results,
  testimonials, data). If none are available, write `[PROOF POINT NEEDED]`.

### Tagline rules

- Generate 3–5 tagline options.
- Each tagline must be distinct in tone and angle — do not produce 5
  variations of the same idea.
- Recommend 1 preferred tagline and explain concisely why it is the
  strongest choice.
- Taglines should be short (under 10 words), memorable, and specific to
  this campaign — not generic slogans.

### Channel plan rules

- Only recommend channels that make strategic sense for the provided inputs.
  Do not list all possible channels by default.
- For each channel, state its specific role in this campaign — not a generic
  description of what the channel does.
- If the user has specified a budget, audience size, or targeting constraints,
  reflect these in channel selection.
- If channel fit is uncertain given available inputs, note it rather than
  force a recommendation.

---

## Step 3 — Handle missing or incomplete information

| Missing Input | How to handle |
|--------------|---------------|
| No product/offer info | Note at top as critical gap; use whatever is provided |
| No audience data | Label audience section as assumed; note gap in Section 9 |
| No campaign goals | Ask the user for at minimum one primary objective before writing |
| No competitor info | Note as gap in Section 9; do not invent competitive context |
| No budget/timeline | Skip budget-dependent recommendations; note gap |
| No proof points | Write `[PROOF POINT NEEDED]` in messaging framework |
| Only one input type | Generate the brief, heavily label assumptions, list gaps in Section 9 |

**Exception:** If no campaign goals are provided at all, ask one focused
clarifying question before writing the brief. All other missing inputs should
be handled inline without stopping to ask.

---

## Step 4 — Quality check before outputting

Before finalizing the brief, verify:

- [ ] All 10 sections are present and in order.
- [ ] No facts are stated that were not in the provided inputs.
- [ ] All inferences are labeled `[ASSUMPTION]`.
- [ ] All data gaps are labeled `[DATA NEEDED]`.
- [ ] Taglines are distinct from each other; one preferred is clearly marked.
- [ ] Channel plan only includes channels that fit the inputs.
- [ ] Each channel entry specifies its role in THIS campaign, not a generic
      description.
- [ ] Messaging framework has a core message specific enough to act on.
- [ ] Section 9 (Key Risks / Watchouts) flags the most important gaps and
      weak assumptions.
- [ ] Section 10 (Final Brief Summary) is 5–8 bullets, concise enough to
      read in under 2 minutes.
- [ ] No buzzwords or vague filler present.
- [ ] The brief is useful for handoff to content, design, and paid media teams.

---

## Reference files

- `brief-template.md` — the 10-section output structure to fill in
- `input-guide.md` — how to handle different input types and combinations
- `validation-checklist.md` — test scenarios for verifying skill quality
- `deck-handoff-guide.md` — how to use this brief as a foundation for a strategy deck

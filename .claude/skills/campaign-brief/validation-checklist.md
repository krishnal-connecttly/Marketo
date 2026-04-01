# Campaign Brief Skill — Validation Checklist

Use this checklist to verify the skill is working correctly. Run each test
scenario and confirm the expected behavior.

---

## Test Scenarios

### Test 1 — Standard Meta Ads CSV export

**Input:** Upload a CSV exported directly from Meta Ads Manager with columns:
Campaign name, Ad set name, Amount spent, Impressions, Reach, Link clicks,
CTR (link click-through rate), CPC (cost per link click), CPM, Results,
Cost per result.

**Expected behavior:**

- [ ] All 6 brief sections are produced.
- [ ] Reporting period is extracted from the file (date range in headers or
      filename) or flagged as "Not available".
- [ ] Spend, Impressions, Reach, Link Clicks, CTR, CPC, CPM, Results, and
      Cost Per Result all appear with exact values from the CSV.
- [ ] ROAS and Purchase Value are listed as "Not available" (not in this file).
- [ ] "What is working" names at least one specific campaign or ad set from
      the data.
- [ ] "What is underperforming" names at least one specific weak area or
      states explicitly that no clear underperformer was found.
- [ ] All 3+ next-step suggestions cite a specific metric and value.
- [ ] No numbers in the brief differ from the source CSV.

---

### Test 2 — XLSX with multiple sheets

**Input:** Upload an Excel file with two sheets: one for Campaign-level data
and one for Ad Set-level data.

**Expected behavior:**

- [ ] The brief lists both sheets under "Data Sources" and explains how
      they were combined.
- [ ] Campaign-level totals are sourced from the Campaign sheet.
- [ ] Ad Set breakdowns in sections 3 and 4 reference the Ad Set sheet.
- [ ] No numbers are double-counted from both sheets.
- [ ] If date ranges differ between sheets, the discrepancy is flagged.

---

### Test 3 — Missing critical metrics

**Input:** Upload a CSV that contains Campaign name, Impressions, and Reach,
but no spend, clicks, CTR, CPC, CPM, results, or cost per result columns.

**Expected behavior:**

- [ ] Spend is listed as "Not available in uploaded data" — not estimated.
- [ ] Link Clicks, CTR, CPC, CPM, Results, Cost Per Result are all listed
      as "Not available in uploaded data".
- [ ] "What is working" and "What is underperforming" sections note that
      performance analysis is limited due to missing metrics.
- [ ] Next-step suggestions are omitted or clearly limited to what the
      available data supports.
- [ ] The skill does NOT invent or estimate any missing values.

---

### Test 4 — Screenshot of Meta Ads Manager

**Input:** Paste or upload a screenshot of the Meta Ads Manager campaigns
table showing campaign names, spend, results, and cost per result.

**Expected behavior:**

- [ ] The brief correctly reads values from the screenshot without OCR errors.
- [ ] Any partially visible or cut-off numbers are flagged, not guessed.
- [ ] Metrics not visible in the screenshot are labeled "Not available".
- [ ] The brief does not invent data that is not clearly readable in the image.

---

### Test 5 — Non-Meta Ads data (e.g., Google Ads export)

**Input:** Upload a CSV from Google Ads with columns like: Campaign, Clicks,
Impressions, CTR, Avg. CPC, Cost, Conversions, Cost / conv.

**Expected behavior:**

- [ ] The brief notes that the data does not appear to be a Meta Ads export.
- [ ] Google Ads column names are used as-is (not forced into Meta terminology).
- [ ] "Campaign" maps correctly; "Ad group" is used instead of "Ad Set".
- [ ] "Conversions" and "Cost / conv." are used instead of "Results" and
      "Cost per result".
- [ ] All 6 sections are still produced using the available data.

---

### Test 6 — Ambiguous or unknown columns

**Input:** Upload a CSV with several standard Meta Ads columns plus two
unrecognized columns: `custom_event_7` and `attribution_model_v2`.

**Expected behavior:**

- [ ] The two unknown columns are listed at the top of the brief as
      "Unrecognized columns: custom_event_7, attribution_model_v2".
- [ ] Their values are not used in any metric in the brief.
- [ ] The skill asks the user what these columns represent before using them
      (or notes that clarification is needed).

---

### Test 7 — No reporting period available

**Input:** Upload a CSV with no date columns and a generic filename like
`export.csv`.

**Expected behavior:**

- [ ] Reporting period is listed as "Not available in the uploaded data".
- [ ] The brief does not infer or assume a date range.

---

### Test 8 — Single campaign, single row of data

**Input:** Upload a CSV with exactly one campaign and one row of data.

**Expected behavior:**

- [ ] The brief still produces all 6 sections.
- [ ] Sections 3 and 4 (working / underperforming) note there is only one
      campaign and no relative comparison is possible.
- [ ] Key takeaways are based only on the one row of data.
- [ ] No fabricated comparisons are made.

---

## Pass Criteria

The skill is working correctly when all checked items pass for each scenario.
If any test fails, identify which rule in SKILL.md was violated and fix the
prompt or template accordingly.

## Common failure modes to watch for

| Failure | What it looks like |
|---------|-------------------|
| Number hallucination | A metric in the brief does not match the source data |
| Silent omission | A missing metric is skipped rather than labeled "Not available" |
| Invented causation | Brief says a metric is high/low "because of" something not in the data |
| Fabricated suggestions | Next steps are generic advice, not tied to a specific data point |
| Wrong terminology | "Ad group" used for Meta Ads data; "Results" used for Google Ads data |
| Merged totals error | Multi-sheet numbers are double-counted |
| Screenshot over-reading | Numbers that are cut off in the image are guessed instead of flagged |

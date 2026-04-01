---
description: >
  Use this skill when a user uploads Meta Ads campaign data (CSV, XLSX, Google
  Sheets, or screenshots) and wants a clear campaign performance report. Trigger
  when: (1) the user uploads or pastes Meta Ads campaign export data and asks
  for a summary or analysis; (2) the user says "create a campaign report",
  "summarize my ad performance", or "what do these results mean"; (3) the user
  needs a stakeholder-friendly or client-ready summary instead of raw
  spreadsheet analysis. Primary audience: media buyers and marketers who want
  full metric detail with strong/weak breakdowns and data-backed optimization
  signals. Output style: medium length, all structured sections, suitable for
  weekly reports and client check-ins.
---

# Campaign Report Skill

## Purpose

Produce a concise, structured campaign report from uploaded paid media data.
Optimized for Meta Ads exports. Works on other paid media datasets when column
names are similar.

---

## Step 1 — Ingest and assess the data

When the user provides data (CSV, XLSX, Google Sheets link, screenshot, or
pasted table), do the following before writing the report:

1. **Identify the source format.** Note whether it is a CSV, Excel file,
   screenshot, pasted table, or link. If multiple files or sheets are provided,
   list each one and explain how you will combine them.

2. **Scan the column headers.** Use the column map in `column-map.md` to
   identify which Meta Ads metrics are present. Note any columns you cannot
   map to a known metric.

3. **Identify the reporting period.** Look for date columns, a date range in
   the file name, or header rows. If no reporting period can be determined,
   state "Reporting period: not available in the uploaded data."

4. **Count structural entities.** Count the number of distinct campaigns,
   ad sets, and ads if those columns are present.

5. **Check for missing critical metrics.** If spend, impressions, clicks,
   CTR, CPC, CPM, results, or cost per result are absent, note each one
   explicitly as "Not available in uploaded data" — do not estimate or infer.

6. **Handle ambiguity.** If the data structure is unclear (e.g., unlabeled
   columns, merged cells in a screenshot, mixed date formats), ask one focused
   clarifying question before proceeding. Do not guess.

7. **Screenshots.** Read values from the screenshot exactly as shown. Do not
   interpolate numbers that are cut off or partially obscured; flag them
   instead.

---

## Step 2 — Write the campaign report

Use the output template in `brief-template.md`. Follow every section in order.
Apply these rules throughout:

### General rules

- **Exact numbers only.** Quote metric values exactly as they appear in the
  data. Do not round unless the source data is already rounded.
- **No hallucinated causation.** Do not state why a metric is good or bad
  unless the data directly supports it. Phrases like "likely due to" or
  "probably caused by" are prohibited.
- **No invented recommendations.** The next-step suggestions section must be
  derived only from patterns visible in the uploaded data. Every suggestion
  must cite the specific metric or row that supports it.
- **Missing = missing.** If a metric is not in the data, write
  "Not available" — never substitute a similar metric or omit the field
  silently.
- **Plain business language.** Translate metric values into business meaning
  for a media buyer audience: what is performing, what is not, and what the
  numbers indicate about efficiency.
- **No padding.** Do not add generic marketing advice, industry benchmarks,
  or best-practice commentary that is not grounded in the uploaded data.

### Meta Ads terminology priority

Use this terminology when the data is from Meta Ads:
- Campaign, Ad Set, Ad (not "ad group")
- Results, Cost Per Result (not "conversions", "CPA")
- Outbound CTR or Link CTR (note which is available)
- Frequency (if present)
- ROAS or Purchase ROAS (if present)
- Reach (distinct from Impressions)

When the data source is not Meta Ads but column names are similar, use the
column names from the file and note the source is not confirmed as Meta Ads.

---

## Step 3 — Multi-file or multi-sheet handling

If more than one file or sheet is uploaded:

1. List each file/sheet at the top of the brief under "Data Sources".
2. Explain whether totals were summed across sheets, or each sheet represents
   a separate time period or account.
3. Flag any rows that appear duplicated across files.
4. If date ranges conflict or overlap between files, call it out explicitly
   rather than silently merging.

---

## Step 4 — Quality check before outputting

Before finalizing the brief, verify:

- [ ] Every number cited in the brief exists verbatim in the uploaded data.
- [ ] No metric field is silently omitted; missing ones are labeled
      "Not available".
- [ ] Reporting period is stated or explicitly flagged as unavailable.
- [ ] "What is working" and "What is underperforming" sections reference
      named campaigns, ad sets, or creatives from the data — not generic
      observations.
- [ ] Next-step suggestions each cite a specific data point.
- [ ] No causal or attributional language without data support.
- [ ] Report fits the medium-length target: all 6 sections present, no section
      is padded beyond what the data supports.

---

## Reference files

- `report-template.md` — the output structure to fill in
- `column-map.md` — Meta Ads column name variants for header detection
- `validation-checklist.md` — checklist for testing the skill

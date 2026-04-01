# Meta Ads Column Map

Reference for detecting and mapping Meta Ads export column headers to
standardized metric names. Used by the campaign-brief skill during Step 1
header scanning.

Matching is case-insensitive. Partial matches are noted where safe.

---

## Structural / Entity columns

| Standardized name | Known column variants |
|-------------------|-----------------------|
| Campaign Name | `Campaign name`, `Campaign`, `campaign_name` |
| Ad Set Name | `Ad set name`, `Ad Set`, `Adset name`, `adset_name` |
| Ad Name | `Ad name`, `Ad`, `ad_name` |
| Account Name | `Account name`, `account_name` |
| Account ID | `Account ID`, `account_id` |
| Campaign ID | `Campaign ID`, `campaign_id` |
| Ad Set ID | `Ad set ID`, `adset_id` |
| Ad ID | `Ad ID`, `ad_id` |
| Objective | `Objective`, `Campaign objective` |
| Status | `Delivery`, `Status`, `Ad set delivery` |
| Bid Strategy | `Bid strategy`, `Budget type` |
| Budget | `Budget`, `Daily budget`, `Lifetime budget` |

---

## Date / Reporting period columns

| Standardized name | Known column variants |
|-------------------|-----------------------|
| Reporting Start | `Reporting starts`, `Start date`, `Date start`, `report_start` |
| Reporting End | `Reporting ends`, `End date`, `Date stop`, `report_end` |
| Date | `Day`, `Date`, `Week`, `Month` |

---

## Spend

| Standardized name | Known column variants |
|-------------------|-----------------------|
| Spend | `Amount spent`, `Spend`, `Cost`, `amount_spent`, `spend` |
| Currency | `Currency`, `currency` |

---

## Impressions, Reach, Frequency

| Standardized name | Known column variants |
|-------------------|-----------------------|
| Impressions | `Impressions`, `impressions` |
| Reach | `Reach`, `reach` |
| Frequency | `Frequency`, `frequency` |

---

## Clicks

| Standardized name | Known column variants |
|-------------------|-----------------------|
| Link Clicks | `Link clicks`, `link_clicks` |
| Outbound Clicks | `Outbound clicks`, `outbound_clicks` |
| All Clicks | `Clicks (all)`, `clicks_all` |
| Unique Link Clicks | `Unique link clicks`, `unique_link_clicks` |
| Unique Outbound Clicks | `Unique outbound clicks`, `unique_outbound_clicks` |

**Priority:** Prefer `Link clicks` or `Outbound clicks` over `Clicks (all)`.
Note in the brief which click column was used.

---

## CTR

| Standardized name | Known column variants |
|-------------------|-----------------------|
| CTR (Link) | `CTR (link click-through rate)`, `Link CTR`, `ctr_link` |
| CTR (Outbound) | `Outbound CTR (link click-through rate)`, `Outbound CTR`, `ctr_outbound` |
| CTR (All) | `CTR (all)`, `ctr_all` |

**Priority:** Prefer `CTR (link)` or `CTR (outbound)` over `CTR (all)`.

---

## CPC / CPM

| Standardized name | Known column variants |
|-------------------|-----------------------|
| CPC (Link) | `CPC (cost per link click)`, `CPC (link)`, `cpc_link` |
| CPC (All) | `CPC (all)`, `cpc_all` |
| CPM | `CPM (cost per 1,000 impressions)`, `CPM`, `cpm` |

**Priority:** Prefer `CPC (link)` over `CPC (all)`.

---

## Results / Conversions

| Standardized name | Known column variants |
|-------------------|-----------------------|
| Results | `Results`, `results`, `Conversions` |
| Result Type | `Result indicator`, `result_indicator`, `Conversion event` |
| Cost Per Result | `Cost per result`, `cost_per_result`, `CPA`, `Cost per conversion` |
| Purchases | `Purchases`, `Website purchases`, `purchases` |
| Purchase Value | `Purchase conversion value`, `Revenue`, `purchase_value` |
| ROAS | `Website purchase ROAS`, `ROAS`, `roas`, `Purchase ROAS` |
| Leads | `Leads`, `leads`, `Website leads` |
| Add to Cart | `Adds to cart`, `add_to_cart` |
| Initiate Checkout | `Checkouts initiated`, `initiate_checkout` |
| Cost Per Purchase | `Cost per purchase`, `cost_per_purchase` |
| Cost Per Lead | `Cost per lead`, `cost_per_lead` |

---

## Video metrics (secondary — include if present)

| Standardized name | Known column variants |
|-------------------|-----------------------|
| Video Views | `Video plays`, `3-second video plays`, `ThruPlay` |
| Video Play % | `Video average play time`, `Video percentage watched` |

---

## Engagement metrics (secondary — include if present)

| Standardized name | Known column variants |
|-------------------|-----------------------|
| Post Reactions | `Post reactions`, `Reactions` |
| Post Comments | `Post comments`, `Comments` |
| Post Shares | `Post shares`, `Shares` |
| Landing Page Views | `Landing page views`, `landing_page_views` |

---

## Columns to ignore (system / internal Meta columns)

The following columns are metadata, not performance metrics. Skip them
during analysis unless specifically asked:

- `Ad ID`, `Campaign ID`, `Ad set ID`, `Account ID`
- `Preview link`, `Ad preview link`
- `Delivery`, `Ad set delivery`, `Campaign delivery`
- `Attribution setting`, `Attribution window`
- `Reporting starts`, `Reporting ends` (use for period detection, then skip)

---

## Unknown columns

If a column header cannot be matched to any entry above:

1. Note it at the top of the brief as "Unrecognized column: [name]".
2. Do not use its values in any metric calculation.
3. If the column looks like a key metric (e.g., a custom conversion), ask the
   user what it represents before proceeding.

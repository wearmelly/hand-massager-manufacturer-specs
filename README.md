---
license: cc-by-4.0
language:
- en
pretty_name: "Hand-care product specifications as stated by manufacturers: heated hand massagers and adjacent products (Oct 2026)"
tags:
- product-specifications
- hand-massager
- consumer-products
- return-policy
- warranty
- manufacturer-claims
size_categories:
- n<1K
configs:
- config_name: default
  data_files: heated-hand-massager-specs.csv
---

# Hand-care product specifications as stated by manufacturers: heated hand massagers and adjacent products (Oct 2026)

Compiled by Wearmelly (wearmelly.com), which sells Melly, a heated hand massager not included in this dataset.

## What this is

For each of 19 products, this table records what the **manufacturer itself** says on its own web pages: product page, product JSON (where the store exposes it), return or warranty policy, FAQ and support pages, and manuals where they were available. Nothing comes from retailers, marketplaces or customer reviews. There are no scores, rankings or verdicts. The table says what a page states, and where it does not, it says "not-stated".

**Claims quoted are the manufacturers', not ours.** Some quotes contain the manufacturers' own health, regulatory or performance wording. They are kept verbatim so each cell can be checked. This dataset makes no medical claims and gives no medical advice.

## Contents

- `heated-hand-massager-specs.csv`: 447 rows in long format (one row per model and field): 11 heated hand massagers x 37 fields = 407 rows, plus 8 adjacent products x 5 fields = 40 rows. The file has 41 distinct fields in total.
- Models: 11 heated hand massagers and 8 adjacent products (3 compression gloves, 3 wrist braces, 2 paraffin baths) that people may compare them with. The `product_category` column separates them. The file name keeps the shorter name of the first group.
- Cells: stated 226, not-stated 201, conflict 11, inaccessible 9.
- Page access date: 2026-10-18 (column `access_date`).
- Rows with a verbatim quote: 237. Rows with a short English note: 111.

### Models

| model_id | brand | model_name | model_code | product_category |
|---|---|---|---|---|
| cincom026h | CINCOM | Hand Massager with Heat | CM-026H | heated-hand-massager |
| bobbradh50 | Bob and Brad | HandSpa Pro | H50 | heated-hand-massager |
| comfier4403 | COMFIER | Wireless Hand Massager | CF-4403 | heated-hand-massager |
| comfier4803 | COMFIER | Wireless Hand Massager with Heat | CF-4803 | heated-hand-massager |
| lunixlx3 | Lunix | LX3 Cordless Hand Massager (Lunar White) | LX3 | heated-hand-massager |
| lunixlx7 | Lunix | LX7 Touchscreen Hand Massager (Lunar White) | LX7 | heated-hand-massager |
| medcursorhm | Medcursor | Hand Massager with Heat and Compression | — | heated-hand-massager |
| nekteckcw | Nekteck | Cordless Hand and Wrist Massager | — | heated-hand-massager |
| snailax489 | Snailax | Hand Massager with Heat | SL-489 | heated-hand-massager |
| reathletedextra | REATHLETE | DEXTRA Cordless Hand Massager | DEXTRA | heated-hand-massager |
| lifeprolegra | LifePro | Legra (Standard) | — | heated-hand-massager |
| v3imak | IMAK (Brownmed) | Compression Arthritis Gloves | — | compression-glove |
| v3coppergl | Copper Compression | Half Finger Compression Gloves | — | compression-glove |
| v3vivegl | Vive | Arthritis Gloves (compression) | — | compression-glove |
| v3featol | FEATOL | Wrist Brace with Ergonomic Aluminum Splint | — | wrist-brace |
| v3mueller | Mueller | Green Fitted Wrist Brace | 86271X | wrist-brace |
| v3copperwr | Copper Compression | Wrist Brace | — | wrist-brace |
| v3homedics | HoMedics | ParaSpa Plus Paraffin Bath | PAR-350 | paraffin-bath |
| v3therabath | Therabath | Professional Paraffin Bath TB6 (Classic) | TB6 | paraffin-bath |

Notes: for LifePro the row is the Legra Standard (the Plus is a separate product and is not included). Prices are USD list prices seen on the manufacturer's US store at the access date; compare-at prices, when shown, are in the `note` column and no coupons were applied.

## How it was collected

1. For each model, the manufacturer's own US-facing pages were saved on the access date: product page, product JSON where available, return or warranty policy, FAQ or support pages and, where found, a manual. Site rules (robots.txt) were respected, with a delay between requests. Where automated access was blocked, the page was recorded from a normal browser session instead (the LifePro product and return pages and the Therabath product page); where no readable text could be obtained the cell is marked `inaccessible`.
2. Values were extracted by language models in two independent passes using one fixed schema, then compared. The two passes agreed on 358 of 407 cells for the first 11 models and on 20 of 40 cells for the adjacent-product fields; differences and suspected gaps were then checked against the saved page copies and resolved. Agreement is not accuracy: please check the quote.
3. Every `stated` and `conflict` cell has a `verbatim_quote` copied from the saved page (some quotes are raw HTML fragments, kept as found). Quotes are at most 300 characters.
4. No inference: values come only from the manufacturer's own pages. A value found only on a retailer page, an Amazon page or a customer review is not used.

## Status values

| status | meaning |
|---|---|
| `stated` | A manufacturer page states the value; the quote is in `verbatim_quote`. |
| `not-stated` | None of the pages read states it. It is **not** a claim that the product lacks the feature. |
| `conflict` | Two pages from the same manufacturer give different values; both values are in `value`/`note`. |
| `inaccessible` | The page could not be read (blocked or empty). |

## Columns

| column | meaning |
|---|---|
| `model_id` | short slug for the model |
| `brand`, `model_name`, `model_code` | brand, product name as the maker writes it, model code when the maker gives one |
| `product_category` | `heated-hand-massager`, `compression-glove`, `wrist-brace` or `paraffin-bath` |
| `field` | one of 41 fields (snake_case, listed below) |
| `value` | normalized value (numbers as numbers; temperatures in °F; durations in minutes) |
| `status` | stated / not-stated / conflict / inaccessible |
| `source_url` | page the value was taken from |
| `source_type` | product-page, product-json, policy-page, faq-or-support-page, manual, manual-archive, image-text |
| `verbatim_quote` | exact passage from the page |
| `access_date` | date the page was read (YYYY-MM-DD) |
| `note` | short English note: price variants, source differences, conversions. Empty when there is nothing to add. |

Fields: `auto_shutoff_min`, `battery_runtime_min`, `box_contents`, `certification_claim`, `charge_time_min`, `charging_port`, `control_type`, `cordless`, `finger_coverage`, `has_heat`, `heat_levels`, `heat_only_mode`, `inner_dimensions`, `intensity_levels`, `max_heat_f`, `mode_count`, `noise_db`, `numbness_neuropathy_warning`, `other_deductions`, `packaging_required`, `pressure_numeric`, `price_usd`, `refund_timing`, `required_consumables`, `restocking_fee`, `return_address_country`, `return_days`, `return_shipping_cost`, `return_shipping_payer`, `return_window_starts`, `separate_finger_chambers`, `setup_instructions`, `size_chart`, `sleep_warning`, `thumb_covered`, `use_while_charging`, `used_item_return`, `warranty`, `weight`, `wrist_heat`, `wrist_mentioned`.

Derived values are never invented: for example battery runtime is the maker's stated figure converted to minutes, and conversions are mentioned in `note`.

## Limits

- Pages were read once, on the access date. Manufacturers change prices, policies and specifications; check the source before relying on a value.
- Manuals (PDF) were mostly not read, so some `not-stated` cells (for example weight, certifications, numeric pressure) may be stated in a manual or on a page that was not read.
- 19 models are a convenience sample, not the whole market.
- Return terms are those on the manufacturer's own US site; other sales channels may differ.
- Some pages state the same thing two ways. Where they disagree the cell is `conflict`.
- The quotes are excerpts from manufacturers' public web pages and remain the property of their owners.

## License

CC BY 4.0 (see `LICENSE`). The license covers our compilation; the quoted passages remain the manufacturers'.

## Citation

See `CITATION.cff`. Suggested: Erin, M. V. (2026). *Hand Massager Specs (Manufacturer-Stated)*. Wearmelly. https://wearmelly.com. CC BY 4.0.

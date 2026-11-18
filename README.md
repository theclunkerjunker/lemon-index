# The Lemon Index: open data on what junk cars sell for

Real prices paid for used, broken and end-of-life cars in the United States:
a monthly index from 2015, median offers for 223 models by model year and
condition, and figures for every state. Free to use under
[CC BY 4.0](LICENSE).

**Release of November 17, 2026, covering sales through October 2026.** The
figures come from 690,000+ vehicle purchases made since 2013 by The Clunker
Junker, LLC, the company that operates [Lemondrove](https://lemondrove.com/).
Lemondrove publishes them, and plans to update them monthly, at
[lemondrove.com/data](https://lemondrove.com/data/).

## Files

### `data/lemon-index-monthly.csv`

The Lemon Index, monthly. Average offer for vehicles that do not drive, and the scrap car price per ton, by month, 2015 to October 2026. 142 rows.

| Column | Meaning |
|---|---|
| `month` | Calendar month, YYYY-MM. |
| `lemon_index_usd` | The Lemon Index: the average offer, in nominal U.S. dollars, for vehicles bought that month that did not drive. |
| `scrap_car_usd_per_ton` | Price per ton paid for scrap cars, nominal U.S. dollars. |
| `scrap_measured` | "yes" when the scrap price was measured from that month's purchases; "no" when too few old cars were bought to measure it and it was estimated from the U.S. Bureau of Labor Statistics scrap index (series WPU1012). |

### `data/offers-by-model.csv`

Offers by make, model and model year. Median offers for 223 models by model year, over every sale and by the condition the seller reported, with sample sizes. Purchases since 2021. 3,153 rows.

| Column | Meaning |
|---|---|
| `make` | Vehicle make. |
| `model` | Vehicle model. |
| `model_year` | Model year. |
| `sample_size` | Number of purchases of that model and model year. |
| `median_offer_all_conditions_usd` | Median offer over every purchase, nominal U.S. dollars. |
| `median_offer_runs_and_drives_usd` | Median offer where the seller reported the car runs and drives. Empty where fewer than 5 sold in that condition. |
| `median_offer_not_driving_body_intact_usd` | Median offer where the car did not drive and the seller reported no body damage. Empty where fewer than 5 sold in that condition. |
| `median_offer_not_driving_body_damage_usd` | Median offer where the car did not drive and the seller reported body damage. Empty where fewer than 5 sold in that condition. |

### `data/offers-by-state.csv`

Offers by state. For each state and the District of Columbia: purchases, the average offer for cars that do not drive, and pickup and payment figures. Each row covers the last 90 days, or the last 12 months in states with few sales; the window is in the file. 51 rows.

| Column | Meaning |
|---|---|
| `state` | Two-letter postal abbreviation. |
| `window_days` | How many days the row covers: 90, or 365 for states with few sales. |
| `purchases_in_window` | Purchases in that window. |
| `average_offer_not_driving_usd` | Average offer for vehicles that did not drive, nominal U.S. dollars. |
| `median_days_to_scheduled_pickup` | Median calendar days from the seller accepting to the scheduled pickup date. |
| `pickups_scheduled_within_2_days_pct` | Share of pickups scheduled within two days of accepting, percent. |
| `paid_as_first_accepted_pct` | Share of sales paid exactly the amount the seller first accepted, percent. |

### `data/lemon-index.json`

The monthly series again as JSON, for charts and scripts: `m` (month),
`index`, `steel` (scrap car price per ton) and `steelMeasured`.

## Read this before using the numbers

- **It is one buyer's data, not the whole market.** These are prices paid
  through one buying network. Private sales, trade-ins and other buyers may
  differ.
- **It skews old and broken.** The cars in this record are mostly near the end
  of their lives. The condition figures are not a reliability ranking.
- **Condition is self-reported.** Sellers describe their own cars, and the
  answers are published as given. Nobody records why a car was sold or what
  failed.
- **Averages hide spread.** The Index is a mean across very different
  vehicles.
- **Small states are noisy.** A handful of sales can move a state's figures.
- **The long-run trend is not only the market.** The Index is what was paid,
  and the mix of cars bought has changed over the years. Use it to compare
  months within a year or two.
- **The newest month and the newest 90 days are provisional.** Cars from the
  latest month are still being picked up at release, so its figures settle in
  the next release.
- **Dollars are nominal.** Adjust for inflation yourself when comparing years.

The full method, with definitions for every figure, is at
[lemondrove.com/about/data-methodology](https://lemondrove.com/about/data-methodology/).

## Using and citing it

Use it for anything, commercial or not. In return, credit "Lemondrove" and
link to [lemondrove.com/data](https://lemondrove.com/data/) or to the page you
used.

> Lemondrove, "The Lemon Index," October 2026 release, lemondrove.com/value/.

Browse the same data with charts: [the Lemon Index](https://lemondrove.com/value/),
[scrap prices](https://lemondrove.com/value/scrap-prices/) and
[research](https://lemondrove.com/research/). Questions, or a cut of the data
you need for a story: press@lemondrove.com.

# Sales & Customer Analytics Dashboard

A Power BI dashboard tracking revenue, orders, customers, and product
performance across an Executive summary, a Customer view, a Product view,
and a Maps/geography view.

## Pages

- **Executive Dashboard**. Top-line KPIs (Total Revenue, Quantity Returned,
  Quantity Sold, Return Rate, Top Subcategory), a revenue-vs-goal callout,
  Total Revenue by Category, a table of product-level performance, and a
  Total Revenue trend with a rolling forecast band.
- **Customer Dashboard**. Total Customers, Average Revenue per Customer,
  Top Customer, a customer-growth trend, and a Total Orders donut broken
  down by Occupation.
- **Product Dashboard**. Total Revenue trend, a Total Revenue-and-goal
  gauge (current month vs. previous month), Total Orders by Category, and
  a Total Revenue area chart, with Product and Category filters.
- **Maps**. Total Orders by Country on a map, with a Continent slicer.
- **Navigation Buttons**. A landing page linking out to the four
  dashboards above.

## Notes from building this

- The Product dashboard's "Total Orders by Category" chart originally only
  showed one category (Accessories). Root cause was a stray
  `ProductName is "Mountain Bottle Cage"` condition (paired with a
  `top 10 by Total Orders` filter) that didn't show up in the visual,
  page, or report-level Filters pane, wasn't a synced slicer, and wasn't a
  hidden Selection-pane object, rebuilding the page from scratch on a new
  tab resolved it. If this resurfaces, check drillthrough filters next.
- Color choices for every chart are documented in
  [`docs/color-palette.md`](docs/color-palette.md), including which were
  validated for colorblind-safe separation and why.
- The revenue gauge's conditional (green-above / red-below) coloring is
  documented in
  [`docs/gauge-conditional-formatting.md`](docs/gauge-conditional-formatting.md).

## Screenshots

Add exported screenshots of each page under `screenshots/` (e.g.
`screenshots/executive-dashboard.png`, `screenshots/customer-dashboard.png`,
`screenshots/product-dashboard.png`, `screenshots/maps.png`) so the README
can reference them directly.

## Data source

_Add a short note here on where the underlying data comes from (e.g. AdventureWorks
sample data, a specific source system, or a refresh schedule), since that context isn't
captured elsewhere in this repo._

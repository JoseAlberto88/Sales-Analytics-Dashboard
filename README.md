# Sales & Customer Analytics Dashboard. Power BI Project

A multi-page Power BI dashboard built on a bike/outdoor-retail sales dataset
(AdventureWorks-style. Categories, Products, Customers, Occupation
demographics, Geography), covering revenue performance, customer behavior,
product/category breakdown, and order geography. This project demonstrates
report/dashboard development end-to-end: DAX measure design, conditional
formatting, accessibility-conscious color design, and cross-page navigation.

Dataset is sample/course-provided retail sales data, used here for
demonstration purposes only.

## What this project covers

- **Report/Dashboard Development**. Four report pages (Executive, Customer,
  Product, Maps) plus a Navigation page, using KPI cards, a gauge, bar/area/
  line charts, a donut chart, a matrix table, a map, and interactive
  slicers.
- **DAX**. Measures for Total Revenue, Previous Month Revenue, Return Rate,
  and a conditional-formatting measure (`GaugeColor`) that switches a
  gauge's color based on current vs. prior-month performance. See
  [`docs/gauge-conditional-formatting.md`](docs/gauge-conditional-formatting.md).
- **Filter & interaction debugging**. Diagnosed a case where a category bar
  chart silently showed only one category despite no visible filter or
  slicer selection; traced it through visual/page/report filters, synced
  slicers, and the Selection pane before resolving it by rebuilding the
  page.
- **Accessibility-conscious color design**. Every chart's palette was
  built in OKLCH color space and validated against colorblind simulation
  (protanopia/deuteranopia) and normal-vision separation thresholds, rather
  than chosen by eye. Full palette and method in
  [`docs/color-palette.md`](docs/color-palette.md).

## Key figures (Executive Dashboard)

- Total Revenue: **$24.9M** across **15,587** total orders.
- Quantity Sold: **84K** units; Quantity Returned: **2K** units (**2.17%**
  return rate).
- Top subcategory by revenue: **Tires and Tubes**.
- Current month revenue **$1.83M** vs. prior month **$1.77M** (**+3.31%**).

## Key insights

## Key insights

- **Bikes drive almost all revenue despite fewer orders.** Bikes generated
  $23.6M of the $24.9M total (≈95%) from 13,929 orders, while Accessories
  produced more orders (16,983) but only $907K in revenue. That implies an
  average order value of roughly $1,700 for Bikes versus ~$53 for
  Accessories and Clothing,  a >30x gap, so category mix, not order
  volume, is the real revenue lever here.
- **Professional and Skilled Manual customers dominate order volume.**
  Together they account for 55% of all orders (31% + 24%), with
  Management, Clerical, and Manual splitting the remaining 44%. Any
  retention or marketing push aimed at growing order volume should
  prioritize these two segments.
- **Revenue and customer growth both inflect around mid-2021.** The
  customer-count trend jumps sharply starting around Jul 2021, and the
  revenue trend accelerates in the same window — worth digging into what
  changed operationally around that point (new channel, campaign,
  seasonality) since it's the clearest structural shift in either series.
- **Returns are a minor drag overall.** A 2.17% return rate across 84K
  units sold is low in absolute terms, but it's worth checking whether
  returns concentrate in a specific category (e.g. Bikes, given their
  outsized share of revenue) rather than assuming it's evenly spread.
- **Short-term momentum is positive.** Current-month revenue ($1.83M) is
  running 3.31% ahead of the prior month ($1.77M), consistent with the
  longer upward trend rather than a one-off spike.

## Report pages

- **Executive Dashboard**. Total Revenue, Quantity Returned, Quantity Sold,
  Return Rate, and Top Subcategory KPI cards; revenue-vs-goal callout with
  trend sparkline; Total Revenue by Category; a product-level performance
  table; Total Revenue trend with a forecast band.
- **Customer Dashboard**. Total Customers, Average Revenue per Customer,
  and Top Customer KPI cards; a customer-growth trend; a Total Orders donut
  by Occupation.
- **Product Dashboard**. Total Revenue trend; a Total Revenue-vs-goal gauge
  (current vs. previous month, conditionally colored); Total Orders by
  Category; a Total Revenue area chart; Product and Category filters.
- **Maps**. Total Orders by Country on a map, with a Continent slicer.
- **Navigation Buttons**. Landing page linking to the four dashboards
  above.

## Tools & techniques

`Power BI` · `DAX` · `Conditional Formatting` · `Data Visualization` ·
`Color Accessibility (OKLCH / CVD simulation)` · `Dashboard Navigation`

## Repository contents

```
├── screenshots/                          # Dashboard page exports
├── docs/
│   ├── color-palette.md                  # Validated color palette + method, per chart
│   └── gauge-conditional-formatting.md   # DAX measure + Power BI setup for the gauge
└── README.md
```

**Note:** the `.pbix` file is not included in this repository, as it
contains coursework/sample data provided under a course license.

## About the Author

**Jose Alberto Martinez Morales**

Master's student in Data Analytics at the University of Niagara Falls, and holder of a Master's degree in Mathematics from UNAM (Universidad Nacional Autónoma de México). Passionate about applying analytical and statistical thinking to real-world data problems, with a growing focus on business intelligence and healthcare analytics.

🔗 [LinkedIn](https://www.linkedin.com/in/josemartinez88/)

**Beyond data:** science fiction, Vietnamese culture, video games, dance machines, learning French, and following scientific topics in AI, mathematics, statistics, and physics/cosmology.

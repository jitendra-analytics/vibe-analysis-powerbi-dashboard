# Vibe Analysis — Power BI dashboard

Author: Jitendra More | Data Analyst Portfolio Project (2026)

## Open the report
1. Close the previous project without saving over the download. Extract this revised ZIP into a NEW folder on your Windows computer; do not merge it with the earlier extracted copy.
2. Open `VibeAnalysis.pbip` with a current Power BI Desktop release. Keep the Report and SemanticModel folders together. If prompted by an older Desktop version, enable Power BI Project/PBIR support or update Desktop.
3. Select **Home → Refresh** to load the embedded data snapshot. The project has no prebuilt Desktop cache. Visual frames and the page title should already be present; KPI values require Refresh. A completely empty canvas is not expected.
4. Use the Year, Region and Category dropdown slicers. Clear a slicer using its eraser icon. Selections filter all KPI cards and charts. Clicking chart data points also uses Power BI's built-in interactions.
5. Optionally use **File → Save as** to save a `.pbix` copy after refresh.

## Included report
One editable Power BI report page with Revenue, Recorded Profit, Orders, Customers and Profit Margin cards; monthly revenue trend; revenue by category; recorded profit by region; and a dynamic top-ten products chart.

## Data and calculations
The semantic model has FactSales and DimCustomer, DimProduct, DimRegion and DimDate. Four active, single-direction many-to-one relationships filter the fact table. `date_key` is YYYYMMDD and remains null on the ten undated orders. DimDate includes month_year sorted by year_month_key. No surrogate unknown date is invented.

- Revenue: sum of signed sales_amount, already after discount.
- Recorded Profit: sum of the supplied profit; provisional.
- Orders: distinct order_id, including returns.
- Customers: distinct purchasing customer_id from FactSales, so all slicers affect this KPI.
- Profit Margin: Recorded Profit / Revenue; a ratio of totals.
- Top products: top ten by Revenue within selected filters, with product name breaking ties.

The unfiltered check totals are 24,905 orders, 2,000 customers, 29,374,086.19 revenue and 6,732,332.30 recorded profit (22.92% margin). Currency is not supplied, so no currency symbol is assumed.

## Data quality and interpretation
- The 50 duplicate orders and 95 orders missing customer/product IDs were removed previously.
- All 15 negative-quantity return records are retained. Their cost/profit signs remain inconsistent; this report does not silently change financial values.
- Ten orders have null dates. Their revenue (9,812.41) and profit (2,357.49) remain in unfiltered totals. The monthly chart excludes them, and a specific year selection excludes them from all visuals. Dated monthly points alone therefore do not equal the unfiltered totals.
- Customer signup chronology remains unresolved; no cohort metrics are presented.
- Regional analysis uses the order region. City values are placeholders and are not used.
- The 12 product-category corrections approved in this conversation are included.

## Portable snapshot and future updates
Clean CSV snapshots are included in Data. The semantic model also embeds their bytes in Power Query M, so initial refresh needs no external credentials or machine-specific path. Refresh reloads this snapshot; it does not pick up edits made to Data/*.csv automatically. For live or changing sources, replace each table's Power Query Source with your local CSV/database source and refresh.

## Verification and limits
Source row counts, keys, joins, revenue and profit were checked programmatically. Report metadata is checked against Microsoft's public JSON schemas where available. The user supplied screenshots of the populated report and model in Power BI Desktop. Automated checks here do not independently test every slicer combination. No report has been published to Power BI Service.

## Format references
- https://learn.microsoft.com/en-us/power-bi/developer/projects/projects-overview
- https://learn.microsoft.com/en-us/power-bi/developer/projects/projects-report
- https://learn.microsoft.com/en-us/power-bi/developer/projects/projects-dataset

## Compatibility repair (13 October 2026)
The initial delivery displayed a blank canvas for the user. This revision sets definition/version.json to the 2.0.0 report-definition format used in Microsoft's sample (distinct from definition.pbir version 4.0), adds Report and SemanticModel .platform metadata, and updates page metadata to 1.1.0 with an explicit active page. The user subsequently supplied screenshots showing the populated report and model in Power BI Desktop.

If the canvas remains empty, open VibeAnalysis.Report/definition.pbir directly and select the Commerce overview page. Send a screenshot of the full window and the Power BI Desktop version from Help/About. If visual frames are visible but values are blank, run Home/Refresh and report any refresh error.

Microsoft powerbi-report-authoring-cli 0.5.0 validation passed with zero errors and zero warnings after the repair, including remote schema checks. Theme names and resource registrations were also corrected. This does not replace testing the report in Desktop.

# Financials Executive Dashboard

An executive finance dashboard built with Power BI Desktop and stored as a
source-controlled PBIP project. The report turns transaction-level financial
data into a concise view of sales performance, profitability, operating
efficiency, and business mix.

## Dashboard

The **Executive Finance Overview** page provides:

- KPI cards for total sales, total profit, total units, profit margin, discount
  rate, and profit per unit
- Monthly sales and profit trend analysis
- Sales performance by segment
- Profit performance by country
- Profit performance by product
- Slicers for year, country, product, and segment

All visuals respond to the active slicer selections, allowing users to move
from an overall executive view to a focused market, product, or segment
analysis.

## Key measures

| Measure | Definition |
| --- | --- |
| Total Sales | Sum of `Sales` |
| Total Profit | Sum of `Profit` |
| Total COGS | Sum of `COGS` |
| Total Units | Sum of `Units Sold` |
| Profit Margin | Total Profit divided by Total Sales |
| Discount Rate | Total Discounts divided by Gross Sales |
| Profit per Unit | Total Profit divided by Total Units |

## Data model

The project uses a star-style model centered on the `financials` table. The
model includes:

- Product, country, segment, and discount-band dimensions in the financials
  table
- Sales, cost, discount, unit, and profit fields
- Date, month, and year fields for time analysis
- A date relationship between `financials[Date]` and the generated local date
  table
- Measures defined in the semantic model using DAX

## Project structure

```text
Financials.pbip
├── Financials.Report/
│   └── definition/
├── Financials.SemanticModel/
│   └── definition/
├── Financials Overview.html
└── README.md
```

The report and semantic model are stored separately using the Power BI Project
(PBIP) format, making report definitions, measures, and model metadata easier
to review in GitHub.

## Open the project

1. Install Power BI Desktop with PBIP support enabled.
2. Clone or download this repository.
3. Open `Financials.pbip` in Power BI Desktop.
4. If Power BI reports a missing data source, update the source in Power Query
   to point to your copy of the Financial Sample workbook.
5. Refresh the model and interact with the slicers.

## Data-source note

The current sample model uses the Microsoft Power BI Desktop Financial Sample
workbook through a local Power Query file path. That path is specific to the
author's machine and is intentionally not committed to the repository. For a
portable deployment, replace it with a relative or parameterized source, such
as a workbook stored in a `data/` folder or a documented cloud connection.

## Portfolio value

This project demonstrates:

- Power BI report and semantic-model development in PBIP format
- DAX measure creation and financial KPI design
- Interactive filtering and cross-visual analysis
- Executive dashboard composition and visual hierarchy
- Git-friendly organization of Power BI artifacts

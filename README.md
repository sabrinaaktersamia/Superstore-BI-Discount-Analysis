# Superstore BI: Does a Bigger Market Mean Bigger Profit?

A two-page Power BI solution that combines Superstore sales transactions with U.S. state GDP data to find out why high-sales areas do not always produce profit, and what is actually driving the losses.

**Tools:** Power BI, data cleaning and integration, correlation analysis, diagnostic analytics, dashboard design

## Dashboards

![Consolidated Dashboard](images/01-consolidated-dashboard.png)
*Consolidated dashboard: sales, profit and state GDP overview with Region > Category > Segment filters.*

![Diagnostic Analysis](images/02-diagnostic-analysis.png)
*Diagnostic view: discount policy and regional/state profit loss.*

## Business problem

Sales were high, but profit margin was only 12.47%. Which sub-categories and states are losing money despite strong sales, and why?

## Data

| Source | Description |
|---|---|
| Superstore sales transactions | Orders with sales, profit, discount, region, category and segment |
| U.S. Bureau of Economic Analysis (BEA) | GDP by state and year |

## Method

1. **Data preparation:** checked both datasets for duplicates, missing values and logic errors.
2. **Data integration:** joined the datasets on State-Year pairs, so each transaction carries the GDP of its own year. Referential integrity was confirmed, with no orphan State-Year pairs.
3. **Consolidated dashboard:** KPI cards, sales and profit by region and category, monthly trend, sub-category profitability table, and a sales vs state GDP scatter plot.
4. **Diagnostic analysis:** drill-downs and segmentation by discount level, sub-category, region and state.

## Key findings

**Consolidated view**
- Total sales: **$2.30M**, total profit: **$286.40K**, profit margin: **12.47%**.
- Sales follow state GDP closely (**r = 0.95**), but profit does not (**r = 0.52**).
- Tables (-$17.7K) and Bookcases (-$3.5K) lose money despite high sales.
- Furniture is the top-selling category by sales ($742.0K) but earns only $18.5K profit, compared with $122.5K for Office Supplies and $145.5K for Technology.

**Diagnostic view**
- **Discount drives the losses on Tables and Bookcases.** Both are profitable at 0% discount (average profit $184 and $101) and turn negative beyond roughly 20-30% discount.
- **Texas is unprofitable because of its discounting practice, not its market size.** It has the third-largest state GDP but lost $25.7K. Every Texas order was discounted (average 37%), compared with California's average discount of 7.3%. Orders at an 80% discount in Texas Office Supplies lost $20.9K.

## Recommendations

| Priority | Recommendation |
|---|---|
| High | Require manager approval for discounts above 20-30% on Tables and Bookcases |
| High | Review Texas's discount policy against comparable high-GDP states |
| Medium | Extend the diagnostic dashboard with a Discount vs Profit page for all states and sub-categories |
| Medium | Run recurring data quality and referential integrity checks as new data is added |
| Low | Add on-dashboard guidance for first-time users |

## Limitations

- Both datasets are static extracts, not a live refresh.
- The diagnostic stage focused on two follow-up questions and one state (Texas).
- The dashboard assumes some familiarity with Power BI slicers and drill-downs.

## Author

**Samia Akter**, MSc Data Science, Universiti Teknologi Malaysia (UTM)
GitHub: [sabrinaaktersamia](https://github.com/sabrinaaktersamia)

*Built as part of a Business Intelligence and Analytics course project.*

# Subscription-Based OTT Platform Analytics Dashboard

A Power BI portfolio project demonstrating an executive-level, multi-function analytics dashboard across **Sales, Finance, HR, and Operations**. It includes synthetic CSV datasets, a proposed relational model, DAX KPI measures, and an executive summary with actionable recommendations.

> **Data note:** This repository's data is synthetically generated for learning and demonstration. Metrics are not real company results and should not be presented as actual business performance. The `.pbix` / `.pbip` dashboard must be authored and saved in Power BI Desktop; the supporting data model, datasets, DAX measures, KPI definitions, documentation, and dashboard layout guide are supplied here.

## Business questions
- Which plans, acquisition channels, and countries contribute most to subscription revenue?
- How are net revenue, month-over-month revenue growth, discounts, refunds, and failed payments trending?
- What is the operating contribution margin proxy after recorded operating costs?
- Which departments and employee groups show higher attrition?
- Which content genres, content types, and devices correlate with completion and watch-time?
- Is cloud spend growing faster than viewing hours?

## Dashboard pages
1. **Executive Overview** — Net Revenue, Revenue Growth %, Operating Contribution Margin % (proxy), Active Subscribers, Attrition %, Efficiency %, monthly trends and key recommendations.
2. **Sales & Subscription** — revenue by plan, geography, acquisition channel, cohort/sign-up period, subscription status and billing frequency.
3. **Finance** — gross billings, discounts, refunds, net revenue, operating costs by department, contribution trend, failed-payment rate.
4. **People / HR** — active headcount, hires, exits, attrition by department/job level/tenure/location.
5. **Operations & Content** — viewing hours, completion efficiency, device mix, genre/content performance, cloud cost per watch hour.

## Repository structure
```text
ott-platform-analytics/
├── data/                  # Synthetic CSV datasets
├── dax/measures.md        # Suggested DAX measures
├── docs/                  # Executive summary and model documentation
├── images/                # Add exported dashboard screenshots here
├── powerbi/               # Power BI authoring guide / saved PBIP or PBIX
└── README.md
```

## Data files
| File | Grain |
|---|---|
| `Customers.csv` | One row per customer |
| `Plans.csv` | One row per plan |
| `Subscriptions.csv` | One row per subscription agreement |
| `Billing.csv` | One row per invoice |
| `ContentCatalog.csv` | One row per content item |
| `ViewingEvents.csv` | One row per viewing session |
| `OperatingCosts.csv` | One row per month and department |
| `Employees.csv` | One row per employee |
| `Date.csv` | One row per calendar date |

## KPIs
- **Revenue Growth %** = (Current period Net Revenue − Prior period Net Revenue) / Prior period Net Revenue.
- **Operating Contribution Margin % (proxy)** = (Net Revenue − recorded actual operating costs) / Net Revenue. This is not audited profit margin.
- **Attrition %** = employee exits during period / average headcount during period.
- **Efficiency %** = completed views / all views; a product-engagement proxy.
- **Cloud Cost per Watch Hour** = technology and cloud operating costs / viewing hours.

Use `dax/measures.md` for starter measures and `docs/data_model.md` for relationships and modeling caveats.

## How to build in Power BI Desktop
1. Import every CSV file from `data/`.
2. Configure data types and create relationships according to `docs/data_model.md`.
3. Add DAX measures from `dax/measures.md` and format them appropriately.
4. Build the five pages outlined above; use slicers for Date, Country, Plan, Device, and Department.
5. Add the executive narrative from `docs/executive_summary.md` and an `images/` screenshot after validation.
6. Save the final project in PBIP format if supported by your Power BI Desktop release; also save a PBIX copy for convenient review if desired.

Microsoft resources: [Power BI samples](https://learn.microsoft.com/en-us/power-bi/create-reports/sample-datasets), [Power BI Desktop projects (PBIP)](https://learn.microsoft.com/en-us/power-bi/developer/projects/projects-overview/), and [Git integration for Power BI projects](https://learn.microsoft.com/en-us/power-bi/developer/projects/projects-git).

## Recommendations to consider
- Investigate cancellation concentration by plan, tenure, geography and acquisition channel before offering retention discounts.
- Use content completion and subsequent subscription behavior to inform licensing decisions.
- Improve payment recovery on failed invoices and quantify refund reasons.
- Compare cloud cost per watch hour with service quality and completion rate.
- Use department- and tenure-level attrition analysis to focus HR interventions.

## Limitations
This is a simulated educational dataset. Some measures are starter definitions and must be reviewed with the course instructor/business owner, especially finance accounting treatment, period-specific HR attrition, and annual subscription revenue recognition.

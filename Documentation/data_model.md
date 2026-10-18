# Data Model & Relationships

Use a star/snowflake-friendly model with single-direction filtering from dimensions to facts. Avoid joining billing and viewing fact tables directly.

| One side | Many side | Columns | Active? |
|---|---|---|---|
| Customers | Subscriptions | CustomerID | Yes |
| Customers | Billing | CustomerID | Yes |
| Customers | ViewingEvents | CustomerID | Yes |
| Plans | Subscriptions | PlanID | Yes |
| Plans | Billing | PlanID | Yes |
| ContentCatalog | ViewingEvents | ContentID | Yes |
| Date | Billing | Date -> InvoiceDate | Yes |
| Date | ViewingEvents | Date -> ViewDate | Yes |
| Date | OperatingCosts | Date -> CostMonth | Yes (Date to month-start) |
| Date | Employees | Date -> ExitDate | No / inactive (recommended for exits) |
| Date | Employees | Date -> HireDate | No / inactive (recommended for hires) |

Recommended: create a dedicated `DimMonth` table with unique month-start values for `OperatingCosts[CostMonth]`, and a proper role-playing date dimension for Employee Hire Date and Exit Date. `Date[Date]` is daily grain, while OperatingCosts is monthly grain; the date key should match month-start.

## Dataset grain and purpose
- `Customers`: one row per customer.
- `Plans`: one row per subscription plan.
- `Subscriptions`: one row per subscription agreement.
- `Billing`: one row per monthly invoice, with gross, discount, tax, refund and status.
- `ContentCatalog`: one row per content title.
- `ViewingEvents`: one row per viewing session/event.
- `OperatingCosts`: one row per month and cost department (synthetic amounts).
- `Employees`: one row per employee, with hiring/exit attributes.
- `Date`: daily calendar with month labels.

All data is generated and synthetic for educational/portfolio use.

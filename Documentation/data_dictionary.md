# Data Dictionary

All source records are synthetic. ID columns should be loaded as text. Date columns should be loaded as Date.

- **Customers**: CustomerID, SignupDate, Country, AcquisitionChannel, CustomerSegment, AgeBand.
- **Plans**: PlanID, PlanName, MonthlyPrice (INR), QualityTier, ScreensAllowed.
- **Subscriptions**: SubscriptionID, CustomerID, PlanID, StartDate, EndDate, BillingFrequency, SubscriptionStatus.
- **Billing**: InvoiceID, SubscriptionID, CustomerID, PlanID, InvoiceDate, BillingFrequency, GrossAmount, DiscountAmount, TaxAmount, RefundAmount, PaymentStatus.
- **ContentCatalog**: ContentID, Title, Genre, ContentType, Seasons, ReleaseDate, OriginMarket, ContentOwnership.
- **ViewingEvents**: ViewID, CustomerID, ContentID, ViewDate, SessionNumber, MinutesWatched, CompletionRate, CompletedFlag, DeviceType, DiscoverySource.
- **OperatingCosts**: CostID, CostMonth, Department, CostAmount, CostBehavior, RecordType.
- **Employees**: EmployeeID, JobLevel, Department, Location, HireDate, ExitDate, EmploymentStatus, IsManager, PerformanceRating, AnnualSalary.
- **Date**: Date, Year, Quarter, MonthNumber, MonthName, YearMonth, MonthStart.

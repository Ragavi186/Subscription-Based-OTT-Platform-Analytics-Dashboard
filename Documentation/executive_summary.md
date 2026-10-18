# Executive Summary (Synthetic Demo Data)

This is a synthetic OTT subscription business dataset created for a Power BI portfolio project. It is not actual company performance. Billing and operating expenses are simulated to demonstrate dashboard modeling and KPI logic.

- Paid invoice net revenue in latest month (Dec 2025): ₹1,343,622.
- Month-over-month revenue growth (Dec 2025 vs Nov 2025): 3.5%.
- Operating contribution proxy (revenue less recorded operating costs) in Dec 2025: 27.9%. This is a simplified proxy, not audited accounting profit margin.
- The data supports Sales, Finance, HR, and Operations views including subscription plans, acquisition channels, billing status, viewing engagement, workforce attrition, and operating costs.

## Recommendations to validate from the dashboard
1. **Retention:** Segment churn/ending subscriptions by plan, acquisition channel, geography, and customer tenure. Test save offers against a control group rather than discounting all cancellations.
2. **Monetization:** Compare net revenue per subscriber and upgrade/downgrade behavior by plan. Prioritize cohorts with strong engagement but a high share of Basic-plan users.
3. **Content investment:** Relate genre and title completion rates to paid subscriber retention before expanding licensing spend. Watch cost per completed hour, not views alone.
4. **Payment recovery:** Trend failed payments and refunds by plan, payment month, and cohort; test retry timing and customer notifications.
5. **Workforce:** Review attrition by department, job level, and tenure. Use headcount-weighted denominators and treat incomplete periods carefully.
6. **Cost efficiency:** Monitor cloud cost per viewing hour and marketing cost per active subscriber alongside revenue and margin so efficiencies do not degrade customer experience.

## Metric caveats
- Revenue Growth % = current month net recognized billing amount / prior month net billing amount - 1. For this demo, annual plans are recognized as full billed invoice amounts; use deferred-revenue allocation if your accounting policy requires it.
- Profit Margin % shown in the dashboard should be labeled **Operating Contribution Margin (proxy)** unless all cost/revenue accounting inputs have been reconciled.
- Attrition % should be computed as employee exits during period / average headcount during period.
- Efficiency % is defined here as completed views / total views; this is a product-engagement proxy rather than an operational productivity measure.

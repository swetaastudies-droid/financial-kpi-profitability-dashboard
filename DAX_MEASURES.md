# DAX Measures Starter Pack

Assumes your imported fact table is named `FactFinancials` and you have created a proper `DimDate` table related to `FactFinancials[Date]`.

```dax
Total Revenue =
SUM ( FactFinancials[Revenue] )

Total COGS =
SUM ( FactFinancials[Cost of Goods Sold] )

Total Operating Expenses =
SUM ( FactFinancials[Operating Expenses] )

Total Cost =
[Total COGS] + [Total Operating Expenses]

Gross Profit =
[Total Revenue] - [Total COGS]

Net Profit =
[Gross Profit] - [Total Operating Expenses]

Net Profit Margin % =
DIVIDE ( [Net Profit], [Total Revenue] )

Gross Profit Margin % =
DIVIDE ( [Gross Profit], [Total Revenue] )

Budgeted Revenue =
SUM ( FactFinancials[Budgeted Revenue] )

Actual Revenue =
SUM ( FactFinancials[Actual Revenue] )

Budget Variance =
[Actual Revenue] - [Budgeted Revenue]

Budget Variance % =
DIVIDE ( [Budget Variance], [Budgeted Revenue] )

Budget Achievement % =
DIVIDE ( [Actual Revenue], [Budgeted Revenue] )

Total Sales Volume =
SUM ( FactFinancials[Sales Volume] )

Revenue Previous Month =
CALCULATE (
    [Total Revenue],
    DATEADD ( DimDate[Date], -1, MONTH )
)

Revenue MoM Growth % =
DIVIDE (
    [Total Revenue] - [Revenue Previous Month],
    [Revenue Previous Month]
)
```

## Formatting
- Format revenue/cost/profit measures as INR currency.
- Format margin, variance percentage, budget achievement, and MoM growth as Percentage.
- Keep the DAX percentage measures as decimal ratios; do not multiply by 100.
- If previous month revenue is blank or zero, growth may be blank; consider this when interpreting the first month.

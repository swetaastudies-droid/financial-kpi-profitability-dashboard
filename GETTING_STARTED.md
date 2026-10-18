# Getting Started (Beginner Guide)

## 1. Prepare
1. Open `01_Dataset/financial_kpi_sample_dataset.xlsx`.
2. Review the `Financial Data` and `Data Dictionary` sheets.
3. Install Power BI Desktop on Windows from Microsoft's official Power BI Desktop download page or Microsoft Store.

## 2. Import the data
1. Open Power BI Desktop.
2. Select **Get data > Excel workbook**.
3. Choose the Excel file in `01_Dataset/`.
4. Select the `Financial Data` sheet.
5. Choose **Transform Data** first to inspect column types and values.
6. When ready, select **Close & Apply**.
7. Rename the imported table to `FactFinancials` in the Data/Model pane.

## 3. Save the report
Save the Power BI report as:
`02_PowerBI/Financial_KPI_Monitoring_Dashboard.pbix`

The ZIP includes the dataset and project scaffolding, not a finished `.pbix` report. Create the report in Power BI Desktop as you work through the project.

## 4. Suggested pages
- Executive Overview: KPI cards, monthly trend, revenue by region, profit by category, matrix.
- Profitability Analysis: category, product, region and channel profitability.
- Cost & Expense Analysis: COGS, operating expenses and net profit.
- Budget vs Actual: actual revenue, budget, variance and achievement.

## 5. Important percentage note
The source column `Profit Margin %` stores percentage points (for example, 25.50 means 25.50%). Do not directly format that raw column as a Power BI Percentage unless you divide it by 100 first. Prefer a DAX measure:
`Net Profit Margin % = DIVIDE([Net Profit], [Total Revenue], 0)`
Format this measure as Percentage; do not multiply it by 100.

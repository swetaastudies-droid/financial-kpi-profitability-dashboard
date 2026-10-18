# Financial KPI Monitoring & Profitability Dashboard

## Project Overview

The **Financial KPI Monitoring & Profitability Dashboard** is an interactive Power BI project designed to analyze financial performance and monitor key performance indicators (KPIs). It helps users evaluate revenue, costs, profitability, and budget achievement across regions, departments, product categories, and sales channels.

## Objective

The objective of this project is to transform financial data into actionable insights through interactive visualizations and financial KPIs. The dashboard supports performance monitoring, profitability analysis, budget comparison, and data-driven decision-making.

## Tools Used

- **Power BI Desktop** — Dashboard development and visualization
- **Power Query** — Data cleaning and transformation
- **DAX** — Calculated measures and KPI analysis
- **Microsoft Excel / CSV** — Dataset storage and input
- **GitHub** — Project versioning and portfolio presentation

## Dataset Description

The project uses a fictional financial dataset containing transaction-level records for demonstration and learning purposes.

Key fields include:

- Date, Month, Quarter, and Year
- Region and Department
- Product Category and Product Name
- Revenue and Cost of Goods Sold
- Operating Expenses
- Gross Profit and Net Profit
- Profit Margin
- Sales Volume
- Budgeted Revenue and Actual Revenue
- Budget Variance
- Customer Segment and Sales Channel

**Data note:** The dataset is synthetic and should not be interpreted as real company financial information. Actual Revenue matches Revenue in this sample dataset, and budget values are provided for practice analysis.

## Power Query Steps

The dataset was prepared using Power Query through the following steps:

1. Imported the financial dataset into Power BI Desktop.
2. Reviewed column names and data types.
3. Converted the Date column to the Date data type.
4. Checked numeric fields for appropriate data types.
5. Reviewed missing values and data consistency.
6. Confirmed the structure of the financial and categorical fields.
7. Loaded the cleaned data into the Power BI data model.

*Only retain the steps that were actually completed in your project.*

## Data Model

- Created a date dimension table named `DimDate`.
- Connected `DimDate[Date]` to `FactFinancials[Date]`.
- Used the date dimension for time-based analysis.
- Created DAX measures for reusable financial calculations.

## DAX Measures

### Total Revenue

```dax
Total Revenue =
SUM ( FactFinancials[Revenue] )
```

### Total Cost

```dax
Total Cost =
SUM ( FactFinancials[Cost of Goods Sold] )
    + SUM ( FactFinancials[Operating Expenses] )
```

### Gross Profit

```dax
Gross Profit =
[Total Revenue]
    - SUM ( FactFinancials[Cost of Goods Sold] )
```

### Net Profit

```dax
Net Profit =
[Gross Profit]
    - SUM ( FactFinancials[Operating Expenses] )
```

### Net Profit Margin %

```dax
Net Profit Margin % =
DIVIDE ( [Net Profit], [Total Revenue] )
```

### Budget Variance

```dax
Budget Variance =
SUM ( FactFinancials[Actual Revenue] )
    - SUM ( FactFinancials[Budgeted Revenue] )
```

### Budget Achievement %

```dax
Budget Achievement % =
DIVIDE (
    SUM ( FactFinancials[Actual Revenue] ),
    SUM ( FactFinancials[Budgeted Revenue] )
)
```

## Dashboard Features

- KPI cards for Total Revenue, Total Cost, Gross Profit, Net Profit, Net Profit Margin %, and Budget Achievement %.
- Regional revenue comparison.
- Net profit analysis by product category.
- Monthly revenue and net profit trend analysis.
- Revenue distribution by sales channel.
- Financial performance matrix by region.
- Interactive slicers for region, department, product category, sales channel, and month.
- Date-range filtering for time-based analysis.

## Key Insights

The following findings are based on the supplied fictional sample dataset and should be checked against the final dashboard before publication:

- North recorded the highest revenue among the regions in the sample.
- Electronics generated the highest net profit among the product categories.
- Overall budget achievement was approximately 98.99%, indicating revenue below the sample budget target.
- Monthly profit margins varied, with August showing the highest and May the lowest margin in the sample.
- Direct Sales recorded the highest net profit among the sales channels, while Retail Partner had the highest net profit margin.

These findings demonstrate how the dashboard can help users identify performance differences, review budget gaps, and compare profitability.

## Screenshots

### Dashboard Overview

![Financial KPI Dashboard Overview](Screenshots/dashboard_overview.png)

### Dashboard Details

![Financial KPI Dashboard Details](Screenshots/dashboard_details.png)

*Replace these image paths with the exact names and locations of your screenshot files. If you have only one screenshot, keep only the Dashboard Overview section.*

## Conclusion

This project demonstrates the use of Power BI, Power Query, and DAX to develop an interactive financial dashboard. It combines KPI monitoring, profitability analysis, budget comparison, and time-based reporting in one report.

The project showcases practical skills in data preparation, data modeling, DAX calculations, visualization, and communicating business insights.

## Project Files

- `.pbix` file — Interactive Power BI report
- `Dataset/` — Sample dataset
- `Screenshots/` — Dashboard images
- `Documentation/` — Project summary and DAX reference
- `Exports/` — Optional PDF export

## Author

**[K B SWETAA]**

Power BI | Data Analytics | Business Intelligence

---

**Disclaimer:** This project is intended for educational and portfolio purposes. All sample financial data is fictional.

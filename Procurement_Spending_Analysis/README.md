# Procurement Spending Analysis

## Project Overview

This project analyzes procurement transaction data to understand total procurement spend, supplier concentration, category distribution, monthly spending trends, and high-spend items.

The project uses both Python and Excel Power Query for data cleaning, validation, aggregation, and dashboard creation.

## Business Objectives

- Understand total procurement spend and transaction volume
- Identify high-spend suppliers and procurement categories
- Analyze monthly procurement spend trends
- Measure supplier and category spend concentration
- Identify high-spend items and basic cost-control opportunities
- Compare Python and Power Query workflows for procurement analysis

## Tools Used

- Python
  - pandas
  - Jupyter Notebook
- Excel
  - Power Query
  - Pivot Tables
  - Pivot Charts
  - Dashboard
- Markdown
  - Project documentation
  - Business rules
  - KPI definitions
  - Case study documentation

## Project Workflow

1. Prepare and document the original CSV data.
2. Check data structure, missing values, duplicates, dates, and numeric fields.
3. Clean the data using Python.
4. Create Spend and Month analysis fields.
5. Export Python outputs to Excel.
6. Build an Excel Dashboard using Python-cleaned data.
7. Repeat the cleaning workflow using Excel Power Query.
8. Create Power Query-based pivot tables and a dashboard.
9. Cross-validate Python and Power Query results.
10. Document findings, business rules, KPI definitions, and recommendations.

## Repository Structure

```text
Procurement_Spending_Analysis/
│
├── 01_Raw_Data/
│   ├── spend_analysis_dataset.csv
│   └── README.md
│
├── 02_Excel/
│   ├── Python_Cleaned_Version/
│   ├── Power_Query_Version/
│   └── Comparison.md
│
├── 03_Python/
│   ├── Procurement Spending Analysis.ipynb
│   └── README.md
│
├── 04_PowerBI/
│
├── 05_Report/
│   ├── Executive_Summary.md
│   └── Procurement_Spending_Report.rtf
│
├── 06_Case_Study/
│   └── Case_Study_CN.md
│
├── 07_Presentation/
│
└── 08_Documentation/
    ├── Project_Scope.md
    ├── Business_Questions.md
    ├── Business_Rules.md
    ├── KPI_Definitions.md
    └── Data_Validation_Evidence.md

## Key Analyses

- Total Spend analysis
- Supplier Spend ranking
- Category Spend ranking
- Monthly Spend trend analysis
- Top 10 item ranking
- Supplier and category Spend Share
- Cumulative Spend Share
- Pareto analysis
- High-value transaction review
- Python and Power Query result comparison

## Data Validation

- No missing values were found.
- No duplicate TransactionIDs were found.
- Quantity minimum value is 1.
- UnitPrice minimum value is 1.06.
- PurchaseDate was converted from text to date format.
- Supplier and Category fields were trimmed for leading and trailing spaces.
- All 500 records satisfy `Quantity × UnitPrice = TotalCost`.
- Python and Power Query produced the same core KPI results.
- Supplier, Category, and Monthly Spend summaries reconcile to Total Spend.

## Current Status

- [x] Raw data preparation
- [x] Python data cleaning
- [x] Excel analysis — Python cleaned version
- [x] Excel analysis — Power Query version
- [ ] Power BI dashboard
- [ ] Final business report
- [ ] Final case study
- [ ] Presentation

## Key Findings

- Total procurement spend is **1,240,580.53** across 500 transactions.
- TechMart Inc. is the highest-spend supplier, accounting for **26.50%** of total spend.
- The top four suppliers account for **83.87%** of total procurement spend.
- Electronics is the largest category, accounting for **56.25%** of total spend.
- Electronics and Software together account for **83.33%** of total spend.
- Laptop is the highest-spend item, followed by Annual Software License.
- September has the highest monthly spend, while July has the lowest monthly spend.
- High-value transactions are mainly associated with Laptop purchases.

## Future Improvements

- Create an interactive Power BI dashboard.
- Add budget-versus-actual spend analysis.
- Add supplier performance, delivery, quality, and contract data.
- Add purchase order status to identify cancelled orders.
- Add more years of data for year-over-year comparison.
- Add supplier risk and concentration scoring.
- Automate refresh and reporting workflows.
- Create a final presentation summarizing findings and recommendations.
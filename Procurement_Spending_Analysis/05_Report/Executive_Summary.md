# Executive Summary

## Objective

This project analyzes procurement spending data to understand overall spend, supplier concentration, category distribution, monthly purchasing trends, and high-spend items.

The analysis supports basic procurement cost control, supplier management, and purchasing planning.

## Dataset

- Source file: `spend_analysis_dataset.csv`
- Data type: Simulated procurement transaction data
- Time range: 2024-01-01 to 2024-12-30
- Transaction records: 500
- Suppliers: 5
- Categories: 6
- Main fields: TransactionID, ItemName, Category, Quantity, UnitPrice, TotalCost, PurchaseDate, Supplier, Buyer

Data was cleaned and validated using both Python and Excel Power Query.

## Key KPIs

| KPI | Result |
|---|---:|
| Total Spend | 1,240,580.53 |
| Transaction Count | 500 |
| Supplier Count | 5 |
| Category Count | 6 |
| Average Order Value | 2,481.16 |
| Top Supplier Share | 26.50% |

## Top Findings

- TechMart Inc. is the highest-spend supplier, with 328,761.73 in procurement spend and a 26.50% share.
- The top four suppliers account for 83.87% of total procurement spend.
- Electronics is the largest procurement category, representing 56.25% of total spend.
- Electronics and Software together account for 83.33% of total procurement spend.
- Laptop is the highest-spend item, with 472,284.81 in total spend.
- Annual Software License is the second highest-spend item, with 336,018.00 in total spend.
- September has the highest monthly spend at 125,187.25.
- July has the lowest monthly spend at 76,055.66.
- High-value transactions are mainly related to Laptop purchases and should be reviewed as part of normal procurement controls.

## Recommendations

- Prioritize cost-control reviews for Electronics and Software because they represent more than 80% of total spend.
- Review pricing, contracts, and demand planning for Laptop and Annual Software License purchases.
- Establish focused supplier-management actions for the top four suppliers, including price negotiations, delivery performance reviews, and backup supplier planning.
- Review purchasing plans before expected high-spend periods, especially around March and September.
- Investigate high-value Laptop transactions to confirm business need, quantity, and pricing.

## Limitations

- The dataset is simulated and does not represent a real organization.
- The analysis covers only one year of transaction data.
- There is no information about budgets, contracts, purchase approval, delivery performance, payment terms, or supplier quality.
- No order status field is available, so cancelled orders cannot be identified separately.
- The analysis identifies spend patterns but cannot independently explain the business reasons behind spending changes.
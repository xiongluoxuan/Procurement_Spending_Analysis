# Business Rules

## 1. Total Spend Calculation

For each transaction:

`Total Spend = Quantity × Unit Price`

In the dataset, the `TotalCost` field represents the transaction-level procurement spend.

The analysis creates a `Spend` field based on `TotalCost`. All 500 records were validated to confirm that:

`Quantity × UnitPrice = TotalCost`

## 2. Supplier Ranking Rule

Supplier ranking is based on total procurement spend.

For each supplier:

`Supplier Spend = Sum of Spend`

Suppliers are ranked from highest to lowest total Spend.

## 3. Monthly Trend Rule

Monthly procurement spend is grouped by `PurchaseDate`.

The `Month` field is derived from `PurchaseDate` and represents the first day of each month. For reporting purposes, it is displayed in `YYYY-MM` format.

For each month:

`Monthly Spend = Sum of Spend`

## 4. Duplicate Record Rule

Duplicate transactions are identified using `TransactionID`.

A transaction is considered duplicated when the same `TransactionID` appears more than once.

The cleaning workflow removes duplicate TransactionIDs and retains one record per transaction. In the current dataset, no duplicate TransactionIDs were found.

## 5. Missing Supplier Name Rule

Supplier names are required for supplier-level analysis.

Records with missing Supplier values would be flagged for data-quality review and excluded from supplier ranking until the supplier name is corrected.

In the current dataset, no Supplier values are missing, so no records were excluded.

## 6. Cancelled Order Rule

The dataset does not contain an order status, cancellation flag, or cancellation date field.

Therefore, cancelled orders cannot be identified separately. All 500 records are included in the analysis under the assumption that they represent valid procurement transactions.

If an Order Status field is added in the future, records marked as cancelled should be excluded from Total Spend, supplier ranking, category analysis, and monthly trend analysis.
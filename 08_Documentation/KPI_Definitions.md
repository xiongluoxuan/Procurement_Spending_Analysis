# KPI Definitions

## Total Spend

**Definition:**  
采购记录中全部采购金额的总和。

**Calculation:**  
`Total Spend = Sum of Spend`

**Result:**  
1,240,580.53

---

## Supplier Count

**Definition:**  
清洗后数据中不重复供应商的数量。

**Calculation:**  
`Supplier Count = Distinct Count of Supplier`

**Result:**  
5

---

## Average Order Value

**Definition:**  
每笔采购交易的平均采购金额。

**Calculation:**  
`Average Order Value = Total Spend ÷ Distinct Transaction Count`

**Result:**  
`1,240,580.53 ÷ 500 = 2,481.16`

---

## Top Supplier Share

**Definition:**  
采购金额最高供应商的采购金额占总采购金额的比例。

**Calculation:**  
`Top Supplier Share = Top Supplier Spend ÷ Total Spend`

**Result:**  
最高支出供应商为 TechMart Inc.，采购金额为 328,761.73。

`328,761.73 ÷ 1,240,580.53 = 26.50%`

---

## Cumulative Spend Percentage

**Definition:**  
将供应商按采购金额从高到低排序后，逐项累计采购金额占总采购金额的比例。

**Calculation:**  
`Cumulative Spend Percentage = Cumulative Supplier Spend ÷ Total Spend`

**Result:**

| Supplier | Spend Share | Cumulative Spend Percentage |
|---|---:|---:|
| TechMart Inc. | 26.50% | 26.50% |
| QuickDeliver Ltd. | 23.00% | 49.50% |
| OfficeSupplies Co. | 18.02% | 67.52% |
| FurniWorks Ltd. | 16.35% | 83.87% |
| CloudSoft Corp. | 16.13% | 100.00% |

**Business Use:**  
该指标用于 Pareto 分析，识别少数核心供应商是否贡献了大部分采购支出。
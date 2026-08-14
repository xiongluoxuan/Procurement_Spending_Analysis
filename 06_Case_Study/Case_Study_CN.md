# Procurement Spending Analysis

## 1. Project Overview

本项目基于采购交易数据，对采购支出规模、供应商结构、品类分布、采购项目和月度趋势进行分析。

项目分别使用 Python（pandas）和 Excel Power Query 完成数据清洗、汇总分析和 Dashboard 制作，并对两种工具的结果进行交叉验证。

## 2. Business Context

采购支出通常涉及多个供应商、不同采购品类和不同时间周期。企业需要识别主要支出来源、监控采购集中度，并找到优先优化的成本控制方向。

本项目旨在模拟采购分析师的基础工作流程，为采购成本管理、供应商管理和预算规划提供数据支持。

## 3. Business Questions

- 总采购支出是多少？
- 主要采购支出来自哪些供应商？
- 哪些采购品类占用了最多预算？
- 采购支出在不同月份如何变化？
- 是否存在供应商或品类支出过度集中的情况？
- 哪些采购项目应优先进行成本控制或供应商谈判？

## 4. Dataset Description

- 数据文件数量：1 个
- 数据文件：`spend_analysis_dataset.csv`
- 数据性质：模拟采购交易数据
- 时间范围：2024-01-01 至 2024-12-30
- 原始记录数：500 条
- 原始字段数：9 个

主要字段包括：

- TransactionID
- ItemName
- Category
- Quantity
- UnitPrice
- TotalCost
- PurchaseDate
- Supplier
- Buyer

## 5. Data Cleaning

数据清洗分别在 Python 和 Power Query 中完成，主要包括：

- 检查缺失值
- 检查重复交易记录
- 将 PurchaseDate 转换为日期类型
- 检查 Quantity 和 UnitPrice 是否存在负数
- 去除 Supplier 和 Category 的首尾空格
- 创建 Spend 字段
- 创建 Month 字段，用于月度趋势分析

清洗后数据保留 500 条交易记录，并新增 Spend 和 Month 两个分析字段。

## 6. Data Validation

进行了以下验证：

- 所有字段缺失值均为 0
- TransactionID 没有重复值
- Quantity 最小值为 1，没有负数量
- UnitPrice 最小值为 1.06，没有负单价
- 500 条记录均满足 Quantity × UnitPrice = TotalCost
- Python 与 Power Query 的核心 KPI 一致
- 供应商、品类和月度汇总金额均与 Total Spend 对账一致

## 7. Analysis Approach

分析过程分为四步：

1. 使用 Python 和 Power Query 清洗原始 CSV 数据。
2. 创建 Spend 和 Month 分析字段。
3. 按 Supplier、Category 和 Month 汇总 Spend。
4. 使用 Excel 数据透视表和图表制作 Dashboard。

核心 KPI 包括：

- Total Spend
- Transaction Count
- Supplier Count
- Category Count

## 8. Key Findings

### Overall Spend

- Total Spend：1,240,580.53
- Transaction Count：500
- Supplier Count：5
- Category Count：6

### Supplier Findings

- TechMart Inc. 是最大供应商，支出为 328,761.73，占总支出的 26.50%。
- 前四家供应商累计占总支出的 83.87%。
- 采购支出主要集中于四家核心供应商，但没有单一供应商占比超过 30%。

### Category Findings

- Electronics 是最大采购品类，支出为 697,805.23，占总支出的 56.25%。
- Software 支出为 336,018.00，占总支出的 27.09%。
- Electronics 和 Software 两个品类累计占总支出的 83.33%。

### Monthly Trend Findings

- 2024 年 9 月采购支出最高，为 125,187.25。
- 2024 年 7 月采购支出最低，为 76,055.66。
- 3 月和 9 月出现采购高峰。
- 6 月至 8 月采购支出下降，9 月明显回升。

### Item Findings

- Laptop 是支出最高的采购项目，支出为 472,284.81。
- Annual Software License 支出为 336,018.00。
- Laptop 和 Annual Software License 是最需要优先关注的采购项目。

## 9. Recommendations

- 优先对 Electronics 和 Software 开展成本控制与合同审查，因为两者合计占总支出的 83.33%。
- 对 TechMart Inc.、QuickDeliver Ltd.、OfficeSupplies Co. 和 FurniWorks Ltd. 建立重点供应商管理机制。
- 对 Laptop 和 Annual Software License 开展价格谈判、需求审核和采购计划管理。
- 针对 3 月和 9 月等采购高峰月份，提前进行预算规划和采购需求确认。
- 为核心供应商建立替代供应商清单，以降低供应中断风险。

## 10. Limitations

- 数据为模拟数据，不代表真实企业采购情况。
- 数据没有合同期限、付款条件、采购审批、交付质量和供应商绩效等信息。
- 无法进一步判断高支出是否合理，或是否存在价格异常。
- 月度趋势只能描述变化，不能单独解释变化原因。
- 数据仅覆盖一年，无法分析长期趋势或年度同比变化。

## 11. Future Improvements

- 增加供应商绩效、交付及时率和质量评分数据。
- 增加合同、预算和采购审批数据。
- 增加上一年度数据，进行同比分析。
- 建立采购预算与实际支出的差异分析。
- 建立自动刷新流程，使 CSV 更新后自动更新 Dashboard。
- 使用 Python 处理多个数据文件、数据库或 API 数据源。
- 建立更完整的供应商风险评分模型。

## 12. What I Learned

通过本项目，我学习了完整的数据分析基础流程：

- 从原始 CSV 文件读取和理解数据
- 进行数据质量检查和数据清洗
- 创建分析字段
- 使用 Python pandas 完成可复现的数据处理
- 使用 Power Query 创建可刷新清洗流程
- 使用数据透视表汇总 Supplier、Category 和 Monthly Spend
- 使用 Excel Dashboard 展示核心 KPI 和趋势
- 使用交叉验证确认 Python 与 Power Query 的结果一致

我也理解了两种工具的适用场景：

- Power Query 更适合业务用户、Excel 报表和可视化刷新流程。
- Python 更适合复杂规则、多文件处理、端到端自动化和更深入的数据分析。
# Procurement Spending Analysis Report

## 1. 项目背景

本项目基于采购交易数据，对采购支出结构、供应商集中度、品类分布、采购项目和月度趋势进行分析，为采购成本控制、供应商管理及采购风险识别提供基础依据。

本项目分别使用 Python（pandas）和 Excel Power Query 完成数据清洗与分析，并对两种方法的结果进行了交叉验证。

## 2. 分析目标

- 了解整体采购支出规模
- 识别高支出供应商和采购品类
- 分析采购金额随时间的变化
- 检查采购支出集中度
- 识别潜在采购风险与优化空间
- 对比 Python 与 Power Query 两种数据处理方法

## 3. 数据范围

- 数据文件数量：1 个
- 数据文件：`spend_analysis_dataset.csv`
- 时间范围：2024-01-01 至 2024-12-30
- 原始记录数：500 条采购交易
- 原始字段数：9 个
- 主要字段：TransactionID、ItemName、Category、Quantity、UnitPrice、TotalCost、PurchaseDate、Supplier、Buyer
- 数据性质：模拟采购交易数据，用于作品集与学习分析流程

## 4. 数据处理说明

### 4.1 缺失值处理

对全部字段进行了缺失值检查。结果显示所有字段缺失值均为 0，因此不需要删除或填补记录。

### 4.2 重复记录处理

以 TransactionID 作为交易唯一标识进行重复检查。结果显示共有 500 个唯一 TransactionID，没有发现重复交易记录。

Python 和 Power Query 均保留了删除重复交易的处理步骤，以确保未来更新数据时仍能自动处理重复记录。

### 4.3 字段类型修正

- Quantity 设置为整数类型
- UnitPrice、TotalCost 和 Spend 设置为十进制数类型
- PurchaseDate 从文本类型转换为日期类型
- 创建 Month 字段，用于月度趋势分析
- Supplier 和 Category 字段执行首尾空格清理

### 4.4 Quantity × UnitPrice 复核

对 Quantity × UnitPrice 与 TotalCost 进行了复核。

结果显示 500 条交易均满足：

`Quantity × UnitPrice = TotalCost`

因此，采购金额字段计算一致，没有发现计算异常。

### 4.5 Python 与 Power Query 交叉验证

Python 和 Power Query 两个版本使用同一份原始 CSV 文件，并得到一致的核心 KPI：

- Total Spend：1,240,580.53
- Transaction Count：500
- Supplier Count：5
- Category Count：6

两种方法的供应商、品类和月度汇总金额均与 Total Spend 对账一致。

## 5. 分析结果

### 5.1 Overall Spend

| KPI | Result |
|---|---:|
| Total Spend | 1,240,580.53 |
| Transaction Count | 500 |
| Supplier Count | 5 |
| Category Count | 6 |

### 5.2 Supplier Ranking and Spend Share

| Rank | Supplier | Spend | Spend Share | Cumulative Spend Share |
|---:|---|---:|---:|---:|
| 1 | TechMart Inc. | 328,761.73 | 26.50% | 26.50% |
| 2 | QuickDeliver Ltd. | 285,353.59 | 23.00% | 49.50% |
| 3 | OfficeSupplies Co. | 223,580.85 | 18.02% | 67.52% |
| 4 | FurniWorks Ltd. | 202,810.72 | 16.35% | 83.87% |
| 5 | CloudSoft Corp. | 200,073.64 | 16.13% | 100.00% |

供应商支出最高的是 TechMart Inc.，占总支出的 26.50%。

前四家供应商累计占总采购支出的 83.87%，说明采购支出主要集中在四家核心供应商。虽然单一供应商占比未超过 30%，但应重点关注这四家供应商的价格、交付稳定性和替代方案。

### 5.3 Category Ranking and Spend Share

| Rank | Category | Spend | Spend Share | Cumulative Spend Share |
|---:|---|---:|---:|---:|
| 1 | Electronics | 697,805.23 | 56.25% | 56.25% |
| 2 | Software | 336,018.00 | 27.09% | 83.33% |
| 3 | Furniture | 172,818.61 | 13.93% | 97.26% |
| 4 | Accessories | 20,857.24 | 1.68% | 98.95% |
| 5 | Stationery | 6,753.18 | 0.54% | 99.49% |
| 6 | Office Supplies | 6,328.27 | 0.51% | 100.00% |

Electronics 是最大采购品类，占总支出的 56.25%；Software 位居第二，占 27.09%。

前两个品类累计占总支出的 83.33%，采购支出存在明显的品类集中度。成本控制工作应优先聚焦 Electronics 和 Software。

### 5.4 Monthly Trend

月度采购支出呈现波动走势：

- 2024 年 9 月支出最高，为 125,187.25
- 2024 年 7 月支出最低，为 76,055.66
- 3 月和 9 月出现较高采购峰值
- 6 月至 8 月支出下降，9 月明显回升
- 10 月至 12 月整体逐步回落

月度波动可能与软件许可采购、电子设备采购或集中采购周期有关；实际业务中应结合采购计划、预算周期和合同信息进一步确认原因。

### 5.5 Top 10 Items by Spend

| Rank | Item | Spend |
|---:|---|---:|
| 1 | Laptop | 472,284.81 |
| 2 | Annual Software License | 336,018.00 |
| 3 | Monitor | 130,072.59 |
| 4 | Printer | 95,447.83 |
| 5 | Desk Chair | 91,857.82 |
| 6 | Whiteboard | 80,960.79 |
| 7 | Laptop Bag | 20,857.24 |
| 8 | Stapler | 6,328.27 |
| 9 | Printer Ink | 5,753.89 |
| 10 | Notepad | 999.29 |

Laptop 和 Annual Software License 是最主要的采购项目，两者合计占整体采购支出的较大部分，应作为采购谈判、预算控制和合同管理的优先对象。

### 5.6 Pareto Analysis

供应商 Pareto 分析显示，前四家供应商累计支出占比为 83.87%，超过 80% 阈值。

品类 Pareto 分析显示，Electronics 和 Software 两个品类累计支出占比为 83.33%，超过 80% 阈值。

因此，采购成本优化应优先关注：

1. Electronics 和 Software 的采购需求、价格和合同条款；
2. 前四家核心供应商的议价、绩效和替代供应商策略；
3. 3 月和 9 月等采购高峰月份的预算与采购计划。

## 6. 结论

本项目的采购支出高度集中于 Electronics、Software 和四家核心供应商。建议优先对高支出品类及核心供应商开展采购谈判、合同审查和替代供应商评估。

Python 版本适合复杂规则、批量处理和端到端自动化；Power Query 版本更适合业务用户在 Excel 中快速刷新数据、更新数据透视表和 Dashboard。
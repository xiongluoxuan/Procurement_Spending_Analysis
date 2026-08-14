# Python vs. Power Query Comparison

## 1. 两个版本使用的数据是否一致？

一致。两个版本均使用：

- 原始文件：`01_Raw_Data/spend_analysis_dataset.csv`
- 交易记录：500 条
- 原始字段：9 个
- 时间范围：2024-01-01 至 2024-12-30

两个版本都创建了 `Spend` 和 `Month` 字段。

## 2. 两种清洗方法的区别

| 对比项 | Python（pandas） | Excel Power Query |
|---|---|---|
| 操作方式 | 编写代码 | 点击式清洗步骤 |
| 清洗记录 | Notebook 中的代码 | Power Query 的“应用的步骤” |
| 刷新方式 | 重新运行代码并导出 | Excel 中点击“全部刷新” |
| 适合场景 | 复杂规则、多文件、API、深度分析 | CSV/Excel 清洗、日常报表与 Dashboard |

两种版本都完成了：缺失值检查、重复交易处理、数据类型处理、文本去空格、创建 Spend 和 Month、负数检查。

## 3. 最终 KPI 是否一致？

一致。

| KPI | 结果 |
|---|---:|
| Total Spend | 1,240,580.53 |
| Transaction Count | 500 |
| Supplier Count | 5 |
| Category Count | 6 |

Supplier Spend、Category Spend 和 Monthly Spend 的汇总金额也应与 Total Spend 一致。

## 4. 哪一种更适合业务用户？

Excel Power Query 更适合业务用户。

它是可视化操作，不需要写代码；替换 CSV 后，通过“数据 → 全部刷新”即可更新清洗数据、数据透视表和 Dashboard。

## 5. 哪一种更适合自动化？

Python 更适合端到端自动化。

当任务涉及定时运行、大量文件、数据库或 API、复杂规则、自动输出文件或高级分析时，Python 的灵活性更强。

Power Query 也支持 Excel 内部刷新，但通常仍依赖用户打开工作簿并刷新。
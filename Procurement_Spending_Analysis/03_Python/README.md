# Python Analysis Documentation

## 清洗了什么

- 检查所有字段的缺失值
- 检查 TransactionID 是否重复
- 检查 Quantity 和 UnitPrice 是否存在负数
- 将 PurchaseDate 从文本转换为日期类型
- 去除 Supplier 和 Category 的首尾空格
- 从 TotalCost 创建 Spend
- 从 PurchaseDate 创建 Month（YYYY-MM）

## 删除或修正了什么

- 清洗流程具备删除重复交易的步骤。
- 本数据没有缺失值、重复交易或负数，因此没有删除记录。
- PurchaseDate 已从文本修正为日期类型。
- Supplier 和 Category 已执行文本去空格标准化。

## 输出文件给谁使用

Python 输出 Excel 工作簿，供业务用户和 Dashboard 使用者查看。

输出工作表包括：

- Cleaned Data：清洗后的交易明细
- Supplier Spend：供应商支出汇总
- Category Spend：类别支出汇总
- Monthly Spend：月度支出汇总

## 如何验证结果

- 清洗后共有 500 条交易记录。
- 原始 9 个字段，加上 Spend 和 Month 两个分析字段。
- Total Spend：1,240,580.53
- Transaction Count：500
- Supplier Count：5
- Category Count：6
- Supplier、Category 和 Monthly 三张汇总表的金额均应与 Total Spend 对账一致。

## Python 输出如何进入 Excel

1. Python 使用 pandas 的 `pd.ExcelWriter()` 创建 Excel 文件。
2. 将清洗数据和三张汇总表写入不同工作表。
3. 打开生成的 `.xlsx` 文件。
4. 在 Excel 中使用这些工作表制作 KPI 和 Dashboard 图表。
# Data Cleaning and Validation Evidence

| 问题 | 发现数量 | 处理方法 | 处理工具 | 验证结果 |
|---|---:|---|---|---|
| 缺失值 | 0 | 检查全部字段的空值；无缺失记录，因此不删除或填补数据。 | Power Query Column Quality | 所有字段有效值 100%，错误值 0%，空值 0%。 |
| 重复 TransactionID | 0 | 以 TransactionID 为唯一交易标识，执行删除重复项步骤。 | Power Query | 清洗后保留 500 条记录，Supplier、Category 和 Monthly 汇总金额可与总金额对账。 |
| PurchaseDate 为文本类型 | 1 个字段，500 条记录 | 将 PurchaseDate 转换为日期类型，并据此创建 Month 字段。 | Power Query | PurchaseDate 可用于按月汇总；Month 共 12 个非重复月份。 |
| Supplier 与 Category 首尾空格 | 未发现明显空格问题 | 对 Supplier 和 Category 执行文本修剪，建立标准化步骤。 | Power Query | 供应商汇总为 5 家，品类汇总为 6 类，没有因空格产生的重复名称。 |
| Quantity 为负数 | 0 | 查看 Quantity 最小值，确认数值有效。 | Power Query Column Profile | Quantity 最小值为 1。 |
| UnitPrice 为负数 | 0 | 查看 UnitPrice 最小值，确认数值有效。 | Power Query Column Profile | UnitPrice 最小值为 1.06。 |
| TotalCost 计算一致性 | 0 条不一致 | 复核 Quantity × UnitPrice 是否等于 TotalCost。 | Python / Power Query 交叉验证 | 500 条交易均满足 Quantity × UnitPrice = TotalCost。 |
| Spend 字段缺失 | 1 个分析字段需创建 | 以 TotalCost 创建 Spend，用于统一汇总分析。 | Power Query | Spend 设置为十进制数，可用于供应商、品类和月度汇总。 |
| Month 字段缺失 | 1 个分析字段需创建 | 从 PurchaseDate 创建 Month（月初日期）。 | Power Query | 月度趋势表覆盖 2024 年 1 月至 12 月。 |
| Python 与 Power Query 结果差异 | 0 | 对比两个版本的核心 KPI 和汇总金额。 | Python、Power Query、Excel | Total Spend 为 1,240,580.53；交易数 500；供应商数 5；品类数 6，结果一致。 |


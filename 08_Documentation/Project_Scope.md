# Project Scope

## 1. Project Purpose

本项目是一个初级采购支出分析项目，旨在通过采购交易数据了解整体采购支出规模、支出结构、供应商分布、品类分布和月度变化趋势。

项目重点是建立完整、清晰、可复现的基础采购分析流程，并使用 Python、Power Query 和 Excel Dashboard 展示分析结果。

## 2. In Scope

本项目包含以下分析内容：

### 2.1 Procurement Spend Analysis

- 计算 Total Spend
- 计算 Transaction Count
- 识别整体采购支出规模
- 创建 Spend 分析字段

### 2.2 Supplier Analysis

- 按供应商汇总采购支出
- 计算供应商 Spend Share
- 计算供应商累计 Spend Share
- 识别高支出供应商
- 进行供应商 Pareto 分析

### 2.3 Category Analysis

- 按采购品类汇总采购支出
- 计算品类 Spend Share
- 计算品类累计 Spend Share
- 识别高支出采购品类
- 进行品类 Pareto 分析

### 2.4 Monthly Trend Analysis

- 按月份汇总采购支出
- 识别采购支出的月度波动
- 识别采购高峰与低谷月份
- 通过折线图展示月度趋势

### 2.5 Top N Ranking

- 识别 Top Supplier by Spend
- 识别 Top Category by Spend
- 识别 Top Item by Spend
- 展示主要采购对象的排序结果

### 2.6 Spend Share and Cumulative Spend Share

- 计算供应商支出占比
- 计算品类支出占比
- 计算累计支出占比
- 使用 Pareto 原则识别主要支出来源

### 2.7 Basic Procurement Recommendations

- 针对高支出供应商提出重点管理建议
- 针对高支出品类提出成本控制建议
- 针对采购高峰月份提出预算规划建议
- 提出替代供应商和合同审查等基础建议

## 3. Out of Scope

为保持项目处于初级采购分析的合理复杂度范围内，本项目不包括以下内容：

- 需求预测
- 机器学习模型
- 复杂供应商风险评分模型
- 库存优化算法
- 自动补货模型
- 财务预测
- 采购价格预测
- 多年度预算预测
- 实时数据接口或生产级自动化系统

## 4. Project Boundary

本项目的分析基于单一采购交易数据文件，并聚焦于描述性分析和基础业务洞察。

项目结论用于识别支出结构、采购集中度和潜在优化方向，不用于直接替代采购审批、供应商准入、合同决策或财务预测。

## 5. Complexity Level

本项目定位为初级采购数据分析项目。

重点能力包括：

- 数据质量检查
- 数据清洗
- 分析字段创建
- 支出汇总
- 数据透视表
- Excel Dashboard
- Python 与 Power Query 的交叉验证
- 基础业务建议

通过明确项目范围，可以避免在缺少业务数据与复杂模型支持的情况下，过度扩展分析结论。
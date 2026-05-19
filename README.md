# 竞赛项目名称 | GoDaddy - Microbusiness Density Forecasting
**比赛链接 Competition Link**：https://www.kaggle.com/competitions/godaddy-microbusiness-density-forecasting
**最终排名 Final Rank**：225/3547
**赛事分数 Final Score**：4.0927
**赛事等级 Competition Level**：铜牌 Bronze

# GoDaddy 微型企业密度预测 | GoDaddy Microbusiness Density Forecasting

**比赛链接 Competition Link**：https://www.kaggle.com/competitions/godaddy-microbusiness-density-forecasting  
**最终排名 Final Rank**：（待填写）  
**赛事分数 Final Score**：（待填写）  
**赛事等级**：时序预测竞赛 / Time Series Forecasting

---

## 一、赛事简介 | Competition Overview

### 中文
本次竞赛由域名与互联网服务巨头 GoDaddy 主办，属于**时序预测类**数据挖掘赛事。目标是基于美国 3135 个县级行政区的历史月度数据，预测未来数月的**微型企业密度（microbusiness_density）**，即每 100 名成年人口中的小微企业数量。

微型企业通常指雇员少于 10 人的小型经营实体，它们在传统经济统计中难以被完整捕捉。赛事希望通过数据科学手段，帮助政府与机构更清晰地理解小微经济动态，为创业政策、地方经济扶持提供依据。

### English
This competition is hosted by GoDaddy, a global provider of domain and online business services. It is a **time series forecasting** challenge, aiming to predict future monthly **microbusiness density** for 3135 U.S. counties. Microbusiness density is defined as the number of microbusinesses per 100 adults in a given region.

A microbusiness is generally defined as a small enterprise with fewer than 10 employees. These businesses are often underrepresented in traditional economic data. The competition hopes to provide policymakers and organizations with clearer insights into small business trends, supporting entrepreneurship policy and local economic development.

---

## 二、数据集介绍 | Dataset Introduction

### 中文
- **训练集**：包含美国各县 41 个月的历史数据（时间序列）。
- **测试集**：无标签，用于未来 3–5 个月预测提交。
- **核心字段**：
  - `cfips`：县唯一编码（州+县 FIPS 码）
  - `first_day_of_month`：当月第一天（时间索引）
  - `microbusiness_density`：微型企业密度（**预测目标**）
  - `active`：活跃小微企业数量（训练集可见，测试集不提供）
- **数据特点**：稀疏性、长尾分布、部分县长期接近零；存在缺失与异常值。

### English
- **Train set**: 41 months of historical time-series data for U.S. counties.
- **Test set**: Unlabeled data for 3–5 months ahead prediction.
- **Key columns**:
  - `cfips`: Unique county FIPS code (state + county)
  - `first_day_of_month`: First day of the month (time index)
  - `microbusiness_density`: Microbusiness density (**target variable**)
  - `active`: Count of active microbusinesses (train only)
- **Data characteristics**: Sparse, long-tailed, near-zero counties; missing values and outliers.

---

## 三、评价指标 | Evaluation Metric

### 中文
本次竞赛使用 **SMAPE（对称平均绝对百分比误差）** 作为唯一评价指标，分数越低越好。
目标：对未来 3/4/5 个月分别预测，整体 SMAPE 最小化。

### English
The competition uses **SMAPE (Symmetric Mean Absolute Percentage Error)** as the sole evaluation metric; lower values are better.
Goal: Predict 3/4/5 months ahead and minimize overall SMAPE.

---

## 四、技术栈与模型 | Tech Stack & Models

### 中文
- **编程语言**：Python
- **数据处理**：Pandas、NumPy、SciPy
- **可视化**：Matplotlib、Seaborn
- **时序模型（常用）**：
  - 统计模型：ARIMA、SARIMA、Prophet
  - 机器学习：LightGBM/XGBoost（时序特征工程）
  - 深度学习：LSTM、GRU、TCN
- **主要思路**：时间序列分层建模、比率/对数差分转换、滞后特征+滚动统计、县级分组训练/预测。

### English
- **Language**: Python
- **Data processing**: Pandas, NumPy, SciPy
- **Visualization**: Matplotlib, Seaborn
- **Models (common)**:
  - Statistical: ARIMA, SARIMA, Prophet
  - ML: LightGBM/XGBoost with time-series features
  - DL: LSTM, GRU, TCN
- **Approach**: Hierarchical time series, ratio/log-diff transformation, lag & rolling features, county-grouped training.


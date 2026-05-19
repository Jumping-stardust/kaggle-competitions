# NFL Big Data Bowl 2026 - Prediction | NFL 2026 大数据碗预测赛

**比赛链接 Competition Link**：https://www.kaggle.com/competitions/nfl-big-data-bowl-2026-prediction
**最终排名 Final Rank**：184/1899
**赛事分数 Final Score**：0.57020
**赛事类型 Competition Type**：时序 / Time-series

---

## 一、赛事简介 | Competition Overview

### 中文
本竞赛由美国国家橄榄球联盟NFL联合AWS共同举办，是Kaggle平台极具含金量的年度体育数据分析赛事。本次赛事核心任务，是依托四分卫传球出手前采集到的全场球员追踪数据，精准预测球在空中飞行阶段里，目标接球手与周边防守球员每一时刻的场上平面坐标及运动轨迹。

赛事所用数据均来源于职业橄榄球正式赛事真实运动采集数据，研究成果可应用于球队战术布局推演、球员跑动习惯分析、赛场攻防局势预判等实际体育竞技场景，具备极高的行业实用价值。

### English
Co-hosted by NFL and AWS, this is a high-value annual sports data analytics competition on Kaggle. The core task is to predict the real-time on-field coordinates and movement trajectories of targeted receivers and nearby defensive players while the ball is in the air, based on complete player tracking data collected before the quarterback releases the ball.

All datasets are sourced from real official professional football matches. Relevant research results can be practically applied to team tactical arrangement research, player running habit analysis and on-field offensive and defensive situation prediction, owning great practical value in sports industry.

---

## 二、数据集介绍 | Dataset Introduction

### 中文
- **训练集**：过往赛季正式赛事完整球员追踪时序数据，包含多场比赛全部球员动态运动信息
- **测试集**：未公开赛事脱敏运动数据，仅保留出手前有效特征，用于完成轨迹预测提交
- **核心字段**：比赛编号、对局编号、球员唯一编号、时间帧序列、平面横纵坐标、移动速度、行进方向、球员赛场身份标签等
- **数据特点**：高频率时序采样、多名球员存在空间位置联动规律、运动轨迹贴合真实赛场战术行为

### English
- **Train set**: Complete time-series player tracking data from past official seasons, covering dynamic motion information of all players in various matches
- **Test set**: Desensitized motion data of unreleased matches, only valid pre-release features are reserved for trajectory prediction submission
- **Key columns**: Game ID, play ID, unique player ID, frame index, horizontal and vertical coordinates, moving speed, moving direction and player role labels
- **Data features**: High-frequency time series sampling, obvious spatial correlation among multiple players, motion trajectories conforming to real on-field tactical behaviors

---

## 三、评价指标 | Evaluation Metric

### 中文
赛事统一采用**RMSE均方根误差**作为官方评判指标，通过计算模型预测坐标与球员真实赛场坐标之间的欧式距离完成精度打分，最终数值越低，代表轨迹预测精准度越高。
评测范围涵盖指定目标接球手，以及传球瞬间距离接球手指定范围内的全部防守球员。

### English
The competition officially adopts **RMSE (Root Mean Square Error)** as the evaluation metric. It scores prediction accuracy by calculating the Euclidean distance between predicted coordinates and real player coordinates. Lower scores stand for higher trajectory prediction accuracy.
The evaluation objects include designated receivers and all defenders within the specified range of receivers at the moment of passing.

---

## 四、技术栈与模型 | Tech Stack & Models

### 中文
- **编程语言**：Python
- **数据处理**：Pandas、NumPy、SciPy
- **可视化工具**：Matplotlib、Seaborn、轨迹动态可视化工具
- **主流建模方案**：时序循环网络、时空注意力Transformer、运动特征融合模型
- **解题核心思路**：挖掘球员历史运动时序规律、融合赛场空间位置关系、区分攻防球员行为特征、搭建多目标同步轨迹预测框架

### English
- **Programming Language**: Python
- **Data Processing**: Pandas, NumPy, SciPy
- **Visualization Tools**: Matplotlib, Seaborn, dynamic trajectory visualization tools
- **Main Modeling Solutions**: Time series recurrent network, spatio-temporal attention Transformer, motion feature fusion model
- **Core Ideas**: Explore the rules of players’ historical movement, integrate on-field spatial positional relations, distinguish behavioral features of offensive and defensive players, build a multi-objective synchronous trajectory prediction framework

---

1. 一键安装项目所需依赖库
```bash
pip install -r requirements.txt

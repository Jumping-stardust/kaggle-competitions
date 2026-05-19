# Map Charting Student Math Misunderstandings | 学生数学误解映射图表征

**比赛链接 Competition Link**：https://www.kaggle.com/competitions/map-charting-student-math-misunderstandings
**最终排名 Final Rank**：153/1857
**赛事分数 Final Score**：0.94589
**赛事类型 Competition Type**：文本分类 / Text Classification

---

## 一、赛事简介 | Competition Overview

### 中文
本竞赛是教育领域的**文本分类任务**，目标是自动识别并分类学生在解答数学应用题时，文字作答中出现的**数学误解类型**。
数据集来自真实学生作答文本，包含多种典型错误：概念混淆、逻辑错误、计算失误、题意误读、推理偏差等。模型需要将每段学生回答归类到预设的**误解类别标签**中，帮助教育者快速定位学生薄弱点、精准干预教学、优化课程设计。

### English
This competition is an **educational text classification task**, aiming to automatically identify and categorize **student math misunderstandings** in written responses to word problems.
The dataset consists of real student answers with typical errors: concept confusion, logical flaws, calculation mistakes, misinterpretation, and reasoning biases. Models must classify each response into predefined **misunderstanding labels**, helping educators diagnose weaknesses, personalize interventions, and improve curriculum design.

---

## 二、数据集介绍 | Dataset Introduction

### 中文
- **训练集**：学生数学作答文本 + 对应**误解标签**（多分类）
- **测试集**：无标签学生作答文本，需预测标签
- **核心字段**：
  - `id`：样本唯一编号
  - `text`：学生作答原文（英文）
  - `label`：数学误解类型（**预测目标**）
- **数据特点**：短文本、口语化、表达不规范、类别分布可能不平衡

### English
- **Train set**: Student written responses + **misunderstanding labels** (multi-class)
- **Test set**: Unlabeled student responses for prediction
- **Key columns**:
  - `id`: Unique sample ID
  - `text`: Student written answer (English)
  - `label`: Math misunderstanding type (**target**)
- **Data characteristics**: Short text, informal language, ungrammatical, possible class imbalance

---

## 三、评价指标 | Evaluation Metric

### 中文
采用**宏平均 F1（Macro F1）**作为评价指标，平衡各类别（含少数类）的分类表现，分数越高越好。

### English
Evaluation uses **Macro F1**, balancing performance across all classes (including minority ones); higher scores are better.

---

## 四、技术栈与模型 | Tech Stack & Models

### 中文
- **编程语言**：Python
- **数据处理**：Pandas、NumPy、NLTK、spaCy
- **文本表示**：TF-IDF、词嵌入、BERT/Tokenizer
- **常用模型**：
  - 传统机器学习：Logistic Regression、SVM、XGBoost
  - 预训练语言模型：BERT、RoBERTa、DistilBERT
- **核心思路**：文本清洗、低质过滤、文本向量化、微调预训练模型、类别不平衡处理

### English
- **Language**: Python
- **Data processing**: Pandas, NumPy, NLTK, spaCy
- **Text representation**: TF-IDF, word embeddings, BERT/Tokenizer
- **Common models**:
  - Traditional ML: Logistic Regression, SVM, XGBoost
  - PLMs: BERT, RoBERTa, DistilBERT
- **Approach**: Text cleaning, noise filtering, vectorization, fine-tuning, class imbalance mitigation

---

## 五、项目结构 | Project Structure

### 中文
- `notebooks/`：EDA、文本清洗、特征工程、模型训练、预测
- `data/`：数据说明、字段释义（不上传原始数据）
- `submissions/`：历次提交 CSV
- `src/`：文本预处理、模型工具、评估函数
- `requirements.txt`：依赖包

### English
- `notebooks/`: EDA, cleaning, feature engineering, training, inference
- `data/`: Data description, field glossary (no raw data)
- `submissions/`: All submission CSVs
- `src/`: Text preprocessing, model utils, metrics
- `requirements.txt`: Dependencies

---

## 六、运行方式 | How to Run

### 中文
1. 安装依赖
```bash
pip install -r requirements.txt

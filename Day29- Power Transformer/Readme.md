# ⚡ Power Transformer in Machine Learning
### Handling Skewed Data with Box-Cox & Yeo-Johnson Transformations

---

## 📌 Project Overview
This project demonstrates how to use Power Transformation techniques to reduce skewness in numerical features and improve machine learning model performance.
The notebook applies `PowerTransformer` from Scikit-Learn and compares model results before and after transformation.

#### The focus is on understanding:
- Why skewed data affects models
- When to use Box-Cox vs Yeo-Johnson
- How transformation impacts different algorithms

---

## 🎯 Objectives
- Detect skewed features using visualizations
- Apply Power Transformation
- Compare model performance before and after transformation
- Understand impact on linear vs tree-based models

---

## 📂 Dataset
The notebook uses selected numerical features from the Titanic dataset:

| Feature | Description |
|---|---|
| `Age` | Passenger age |
| `Fare` | Ticket fare |
| `Survived` | Target variable |

---

## 🛠 Technologies & Libraries
- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- scipy
- scikit-learn

---

## 📊 Exploratory Data Analysis
The notebook includes:
- Distribution plots
- Q-Q plots
- Skewness analysis

#### Observations
- `Fare` shows strong right skewness
- `Age` has moderate skewness
- Linear models may struggle without normalization

---

## 🔄 Power Transformation

```python
from sklearn.preprocessing import PowerTransformer
```

#### Methods Used

| Method | Description |
|---|---|
| Box-Cox | Works only with strictly positive data |
| Yeo-Johnson | Works with positive and negative data |

By default, `PowerTransformer` uses Yeo-Johnson, making it more flexible.

---

## 🤖 Models Compared
Two models are trained and evaluated:

#### 1️⃣ Logistic Regression
Sensitive to distribution and scaling.

#### 2️⃣ Decision Tree Classifier
Generally robust to monotonic transformations.

#### Evaluation Metrics
- Accuracy Score
- Cross-validation

---

## 📈 Results Summary

| Model | Before Transformation | After Power Transformation |
|---|---|---|
| Logistic Regression | Moderate | Improved |
| Decision Tree | Similar | Similar |

#### Key Insight
- Power transformation improves performance for linear models
- Tree-based models show minimal change
- Feature normalization is crucial for algorithms assuming normality

---

## 🧠 Key Learnings
- Skewed features can negatively affect linear models
- Power transformations reduce skewness and stabilize variance
- Yeo-Johnson is safer for real-world datasets
- Always validate transformation impact using cross-validation
- Not all models benefit equally from transformations

---

## 🚀 How to Run
1. Clone the repository
2. Install required libraries
3. Open the notebook
4. Run all cells sequentially

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn
```

---

## 📌 Conclusion
This project highlights the importance of feature preprocessing in machine learning pipelines. Power Transformation is a powerful technique for improving model performance when dealing with skewed numerical features, especially for linear algorithms.

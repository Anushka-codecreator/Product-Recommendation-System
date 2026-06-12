# 🛍️ Personalized Product Recommendation System

A machine learning recommendation system that generates personalized product suggestions using collaborative filtering.

Built as part of an ML portfolio project using transaction data and matrix factorization.

---

## 📌 Project Overview

This project recommends products to customers based on historical purchase behavior.

Since explicit ratings were unavailable, purchase quantities were transformed into implicit feedback and used for collaborative filtering.

The system predicts customer preference scores and recommends products not previously purchased.

---

## Dataset

Online Retail Dataset

Features:
- CustomerID
- StockCode
- Description
- Quantity
- InvoiceDate

---

## Methodology

### 1. Data Cleaning

- Removed null values
- Removed invalid transactions
- Converted CustomerID
- Removed duplicates

### 2. Feature Engineering

Purchase quantities were aggregated and transformed using:

```python
np.log1p(quantity)
```

This reduces skewness while preserving preference information.

---

### 3. Exploratory Data Analysis

Performed:

- Purchase distribution
- Product popularity
- Customer analysis
- Sparsity analysis

---

### 4. Recommendation Models

Multiple recommendation approaches were explored:

- Popularity-based Baseline
- KNN Collaborative Filtering
- SVD Collaborative Filtering (selected final model)
  
Hyperparameters were optimized using GridSearchCV and evaluated using RMSE.

---

### 5. Recommendation Generation

For each customer:

1. Identify purchased products
2. Exclude purchased products
3. Predict preference for unseen products
4. Rank products
5. Return Top-N recommendations

---

## Example Output

```
Customer: 13047

• GIRLS ALPHABET IRON ON PATCHES
(Predicted Preference: 6.18)

• ASSORTED INCENSE PACK
(Predicted Preference: 4.98)

• POPART WOODEN PENCILS ASST
(Predicted Preference: 4.86)
```

---

## Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- Surprise
- Gradio
- Matplotlib
- Seaborn

---

## Dataset Setup and Running the Notebook

This project uses the **Online Retail Dataset** containing historical e-commerce transactions.

Dataset includes:
- CustomerID
- StockCode
- Description
- Quantity
- InvoiceDate

Download the dataset before running the notebook:

Dataset source:  
https://archive.ics.uci.edu/dataset/352/online+retail

After downloading:

1. Rename file to:

```
Online Retail.xlsx
```

2. Upload it into Google Colab

3. Run notebook cells sequentially

Expected folder structure:

```
Project/
│── Amazon_Product_Recommendation_System.ipynb
│── Online Retail.xlsx
```

Note:
Dataset is not included in this repository due to file size and external hosting.

## Future Scope

- Hybrid recommendation systems
- Content-based filtering
- Real-time recommendation serving

---

# 🎬 Movie Recommendation System  
User-Based Collaborative Filtering with Cosine Similarity

![User Similarity Heatmap](heatmap.jpg)

---

## 📌 Project Overview

This project implements a **User-Based Collaborative Filtering Recommendation System** using cosine similarity.

The system:

- Loads a movie ratings dataset (wide format)
- Transforms it into a long format
- Builds a user-item matrix
- Computes user-to-user similarity
- Generates personalized recommendations
- Compares collaborative filtering with a content-based popularity baseline
- Visualizes similarity using a heatmap

---

## 📂 Dataset Format

The dataset is initially in **wide format**:

| userId | Movie1 | Movie2 | Movie3 | ... |
|--------|--------|--------|--------|-----|
| User1  | 5      | 0      | 3      | ... |

It is transformed into **long format**:

| userId | movieId | rating |
|--------|---------|--------|
| 1      | 1       | 5      |
| 1      | 3       | 3      |

Rows with rating `0` are removed (treated as not watched).

---

## ⚙️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Seaborn
- Matplotlib

---

## 🧠 Methodology

### 1️⃣ Data Transformation

- Rename user column
- Melt wide dataset into long format
- Extract numeric movieId
- Remove zero ratings
- Create user-item matrix

---

### 2️⃣ User Similarity Matrix

Cosine similarity is computed using:

```python
from sklearn.metrics.pairwise import cosine_similarity

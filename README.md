# 🛒 Amazon Product Recommendation System

This project implements an **item-based collaborative filtering** recommendation system for Amazon products using **Python**, **pandas**, **numpy**, **TextBlob**, **scikit-learn**, and **scipy**.  
The system recommends products based on the **similarity of user ratings** and **sentiment analysis** of review titles.

---

## 📘 Overview

The goal of this project is to build a **recommendation system** that suggests similar products to users based on:
- Their past interactions (ratings)
- Sentiment expressed in their reviews  

The system combines **Collaborative Filtering** and **Sentiment Analysis** to generate more accurate and personalized recommendations.

---

## 🧠 Project Workflow

1. **Data Loading**  
   Load the Amazon product data from a CSV file.

2. **Sentiment Analysis**  
   Use **TextBlob** to calculate the **sentiment polarity** of each review title.

3. **Weighted Score Calculation**  
   Create a new feature `Updated_score` = `Rating × Sentiment Polarity`.

4. **User ID Encoding**  
   Encode `user_id` values into numerical labels for easier model processing.

5. **Score Classification**  
   Convert `Updated_score` into 5 categories (1–5) and store in a new column `New_score`.

6. **Pivot Table Creation**  
   Create a pivot table with:
   - Rows → `product_id`
   - Columns → `user_id`
   - Values → `New_score`  
   Fill missing values with **0**.

7. **Sparse Matrix Conversion**  
   Convert the pivot table into a **sparse matrix** for memory efficiency.

8. **Model Training**  
   Train a **Nearest Neighbors** model using **cosine similarity** on the sparse matrix.

9. **Recommendation Generation**  
   Given a product ID, the model retrieves the most similar products.

---



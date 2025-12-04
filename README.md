# 🏠 Housing Price Prediction (Thane Real Estate Dataset)

This project builds a **Machine Learning model** to predict **housing prices in Thane** based on features such as carpet area, floor, location, transaction type, facing, and more.
It uses a real-estate dataset scraped from online property listings and includes extensive **data cleaning**, **feature engineering**, and **model training** using **Random Forest Regressor**.

---

## 📌 Project Overview

The dataset contains 21 columns including property information like:

* Title & Description
* Amount (in rupees) — *e.g., “42 Lac”, “1.40 Cr”*
* Price (in rupees) — *price per sq.ft*
* Carpet Area — *e.g., “500 sqft”*
* Floor — *e.g., “10 out of 11”*
* Property Status
* Transaction Type
* Facing / Overlooking
* Society Name
* Ownership
* And more...

Since the dataset contains a mix of **text**, **categorical**, **numeric**, and **mixed-format fields**, preprocessing is a significant part of this project.

---

## 🧼 Data Cleaning & Preprocessing

### ✔ 1. Convert “Amount(in rupees)” into numeric

Handles formats like:

* `42 Lac` → `4200000`
* `1.4 Cr` → `14000000`
* `98 Lac` → `9800000`

### ✔ 2. Extract Carpet Area

From:
"500 sqft" to:500

### ✔ 3. Extract Floor Info

Split:"10 out of 11"
      into:
Floor Number = 10  
Total Floors = 11

### ✔ 4. Handle missing values

Numeric columns → filled with median
Categorical columns → label encoded

### ✔ 5. Drop irrelevant high-text columns

Such as Title, Description, Society Name, Dimensions, etc.

## 🧠 Machine Learning Model

We use **Random Forest Regressor** because the dataset contains many categorical values and nonlinear patterns.

### Steps:

1. Prepare feature matrix `X`
2. Set target variable `y = Amount(in rupees)`
3. Train-test split
4. Train the model
5. Evaluate with:

   * RMSE (Root Mean Squared Error)
   * R² Score
6. Make predictions on new property samples

---

## 📊 Model Evaluation

The model prints:

* **RMSE** – error in rupees
* **R² Score** – how well features explain the price
* **Predicted price** for test samples

You can use the model to estimate the total cost of a flat in Thane based on input parameters.

---

## 🧪 Example Prediction Code

```python
sample = X_test.iloc[0:1]
model.predict(sample)
Output example:
array([13800000.])  # predicted price ≈ 1.38 Cr


## 🚀 How to Run the Project (Google Colab)

1. Upload the dataset to Colab
2. Install dependencies:

   python
   pip install pandas numpy scikit-learn seaborn matplotlib
3. Run the full pipeline:
   * preprocessing
   * feature engineering
   * model training
   * prediction

## 📈 Future Improvements

* Use XGBoost / CatBoost for higher accuracy
* Hyperparameter tuning
* Deploy using Streamlit
* Add location-based geospatial encoding
* Use NLP on title/description fields

## 🧑‍💻 Author

**Anushika**
Engineering (Computer Science – Computational & Data Science)

## ⭐ If you like this project

Give the repo a **star ⭐** on GitHub!


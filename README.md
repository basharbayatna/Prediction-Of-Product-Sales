<img width="1200" height="628" alt="image" src="https://github.com/user-attachments/assets/48f302f7-c034-4a7d-afc3-6dcf40c52569" />


# Prediction of Product Sales 🍎🛒
## Sales Prediction for Food Items

This project focuses on predicting the sales of multiple items across various stores. The goal is to help retailers understand which product and store characteristics drive sales. Additionally, the analysis aims to answer **critical business questions** to guide strategic decisions, such as which outlet types and locations maximize sales, which outlets are most reliable, and where to focus expansion or marketing efforts for optimal profitability.

---

## 📊 Project Overview
- **Objective:** Build a predictive model for `Item_Outlet_Sales` based on product and store characteristics.  
- **Data Source:** [Download Dataset](https://drive.google.com/file/d/1syH81TVrbBsdymLT_jl2JIf6IjPXtSQw/view)  
- **Key Tasks:**
  1. Data loading and cleaning  
  2. Exploratory Data Analysis (EDA)  
  3. Feature engineering and modeling  

---

## 📂 Dataset Information
The dataset contains information about products and outlets, with the target variable being **Item_Outlet_Sales**.  
It contains **8,523 rows** and **12 columns**.

### Data Dictionary

| Variable Name               | Description |
|------------------------------|-------------|
| `Item_Identifier`           | Product ID |
| `Item_Weight`               | Weight of product |
| `Item_Fat_Content`          | Low-fat or regular |
| `Item_Visibility`           | % of display area allocated to the product |
| `Item_Type`                 | Product category |
| `Item_MRP`                  | Maximum Retail Price (list price) |
| `Outlet_Identifier`         | Store ID |
| `Outlet_Establishment_Year` | Year the store was established |
| `Outlet_Size`               | Store size (ground area covered) |
| `Outlet_Location_Type`      | Type of city in which store is located |
| `Outlet_Type`               | Type of outlet (grocery, supermarket, etc.) |
| `Item_Outlet_Sales`         | **Target variable**: Sales of the product |

---

## 🛠️ Data Cleaning
Using **Pandas**, the dataset was prepared for analysis by:

1. Checking the number of rows and columns  
2. Inspecting datatypes of each variable  
3. Removing duplicates  
4. Identifying missing values and replacing them with placeholder values  
5. Ensuring no missing values remain after cleaning  
6. Standardizing categorical entries (e.g., fixing inconsistencies in `Item_Fat_Content`)  
7. Generating summary statistics for numerical features  

---

## 📈 Exploratory Data Analysis (EDA)
Using **Matplotlib** and **Seaborn**:

- **Histograms** → visualize distributions of numerical features  
- **Boxplots** → show statistical summaries and detect outliers  
- **Countplots** → check frequency distributions of categorical features  
- **Heatmap** → examine correlations between numerical variables  

### 📌 Business Questions

1. Which outlet types are most common?  
2. Which outlet types generate the highest sales?  
3. How does location impact sales?  
4. How do outlet type and location interact to affect sales?  
5. Which outlets are consistently reliable?  
6. Where should a business focus to maximize profitability?  

---

## 🔍 Key Insights

### Outlet Location Type

<img width="589" height="390" alt="image" src="https://github.com/user-attachments/assets/4fec295c-21b2-4925-9cdb-2d09e9e194fc" />


- The Outlet_Type is the most significant factor influencing sales performance. Both Supermarket Type3 and Supermarket Type1 demonstrate the highest average sales and substantial potential for peak sales. Conversely, Grocery Stores consistently show a drastically lower average and maximum sales, indicating they are the weakest-performing outlet category.


### Outlet Type

<img width="589" height="390" alt="image" src="https://github.com/user-attachments/assets/628d0087-b65a-43ac-a5bf-3cdb09bf6ceb" />


- The Outlet_Location_Type has little effect on an item's typical sales value, as the average sales are remarkably consistent across Tier 1, Tier 2, and Tier 3 locations. However, Tier 3 locations are associated with the highest individual sales points, suggesting that while they don't boost average performance, they do host the most successful, high-volume transactions.
 

### Outlet Type & Location Interaction
<img width="762" height="518" alt="image" src="https://github.com/user-attachments/assets/c3363036-2b67-479a-a399-d196a759e9e4" />



---

## 💡 Strategic Recommendation
- Focus on **Supermarket Type 3 in Tier 3 locations** for maximum sales  
- Use **Supermarket Type 1** for stable sales across all tiers  
- Avoid **Grocery Stores**  

---

# 🔍 Feature Inspection
Before modeling, features were inspected for:

- Data type  
- Missing values  
- Cardinality  
- Relationship with target variable (`Item_Outlet_Sales`)  

**Examples:**
- **Outlet_Size:** Ordinal, some missing values, mild predictor  
- **Outlet_Location_Type:** Ordinal, no missing values, slight predictor  

---

# 🧠 Machine Learning: Item Outlet Sales Prediction

## 1. Data Preprocessing
- Dropped unnecessary columns (`Item_Identifier`)  
- Handled missing values (`Outlet_Size`)  
- Train-test split with fixed random state  
- Feature transformation pipelines:  
  - Numerical → median imputation + standard scaling  
  - Ordinal → most frequent imputation + ordered encoding + scaling  
  - Categorical → constant imputation + one-hot encoding  
- Unified preprocessing using `ColumnTransformer`  

---

## 2. Model Development

### Linear Regression
| Dataset | MAE | RMSE | R² |
|----------|------|------|------|
| Train | 847.15 | 1139.13 | 0.562 |
| Test | 804.09 | 1092.73 | 0.567 |

*Baseline model, interpretable but underfits.*

### Random Forest Regressor
| Dataset | MAE | RMSE | R² |
|----------|------|------|------|
| Train | 296.23 | 426.54 | 0.939 |
| Test | 765.91 | 1102.14 | 0.560 |

*Overfitted model; excellent training performance but weak generalization.*

### Tuned Random Forest Regressor
| Dataset | MAE | RMSE | R² |
|----------|------|------|------|
| Train | 755.44 | 1073.75 | 0.610 |
| Test | 728.49 | 1046.52 | 0.603 |

*Hyperparameter tuning improved generalization and reduced overfitting.*

---

## 3. Model Comparison Summary
| Model | Train R² | Test R² | Test MAE | Test RMSE | Notes |
|:------|:---------:|:--------:|:---------:|:-----------:|:------|
| Linear Regression | 0.562 | 0.567 | 804.09 | 1092.73 | Baseline, underfits |
| Random Forest | 0.939 | 0.560 | 765.91 | 1102.14 | Overfits |
| Tuned Random Forest | 0.610 | 0.603 | 728.49 | 1046.52 | Best balance |

---

## 4. Evaluation & Recommendations
- Linear Regression → simple baseline, cannot capture complex patterns  
- Untuned Random Forest → overfits, poor test performance  
- Tuned Random Forest → best generalization, explains ~60% of variance  

**Final Recommendation:**  
Deploy the **Tuned Random Forest Regressor**. Future improvements:  
- Additional feature engineering (interactions, seasonality, regional trends)  
- More cross-validation folds for stability  
- Explore advanced ensemble models (Gradient Boosting, XGBoost, LightGBM)  

---

## ✅ Summary
The **Tuned Random Forest Regressor** achieved the best performance and generalization, making it the most reliable model for predicting item outlet sales.

---

## ℹ️ Contact
- **Bashar Bayatna**, Mechatronics Engineer | Junior Data Scientist  
- Email: [Basharbayatna11@gmail.com](mailto:Basharbayatna11@gmail.com)

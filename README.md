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


- The Outlet_Location_Type has little effect on an item's typical sales value, as the average sales are remarkably consistent across Tier 1, Tier 2, and Tier 3 locations. However, Tier 3 locations are associated with the highest individual sales points, suggesting that while they don't boost average performance, they do host the most successful, high-volume transactions.

### Outlet Type

<img width="589" height="390" alt="image" src="https://github.com/user-attachments/assets/628d0087-b65a-43ac-a5bf-3cdb09bf6ceb" />




 - The Outlet_Type is the most significant factor influencing sales performance. Both Supermarket Type3 and Supermarket Type1 demonstrate the highest average sales and substantial potential for peak sales. Conversely, Grocery Stores consistently show a drastically lower average and maximum sales, indicating they are the weakest-performing outlet category.


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
| Train | 296.57 | 428.06 | 0.938 |
| Test | 774.17 | 1110.36 | 0.553 |

*Overfitted model — excellent fit on training data but poor generalization to unseen data.*

---

### Tuned Random Forest Regressor
| Dataset | MAE | RMSE | R² |
|----------|------|------|------|
| Train | 749.24 | 1061.17 | 0.619 |
| Test | 727.15 | 1046.34 | 0.603 |

*Hyperparameter tuning reduced overfitting and improved generalization performance.*

---

## 3. Model Comparison Summary
| Model | Train R² | Test R² | Test MAE | Test RMSE | Notes |
|:------|:---------:|:--------:|:---------:|:-----------:|:------|
| Linear Regression | 0.562 | 0.567 | 804.09 | 1092.73 | Baseline, underfits |
| Random Forest | 0.938 | 0.553 | 774.17 | 1110.36 | Overfits (high train R², weaker test performance) |
| Tuned Random Forest | 0.619 | 0.603 | 727.15 | 1046.34 | Best balance between bias and variance |

---

## 4. Evaluation & Recommendations
- Linear Regression → simple baseline, cannot capture complex patterns  
- Untuned Random Forest → overfits, poor test performance  
- Tuned Random Forest → best generalization, explains ~60% of variance

--- 
## 4. Feature Importance & Coefficients Visualization

### 🔹 Top 15 Largest Coefficients (Linear Regression)
<img width="700" height="460" alt="Top 15 Coefficients" src="https://github.com/user-attachments/assets/48f302f7-c034-4a7d-afc3-6dcf40c52569" />

The plot above displays the top coefficients from the **Linear Regression** model.  
These coefficients represent how much each feature affects the predicted sales —  
positive values **increase** the prediction, while negative ones **decrease** it.

#### 📈 Interpretation:
- The **3 largest coefficients** are:
  - **Outlet_Identifier_OUT027** → if the item belongs to this outlet, the predicted sales increase by **≈1519**.  
  - **Outlet_Type_Supermarket Type3** → if the item is sold in this outlet type, sales increase by **≈1519**.  
  - **Outlet_Type_Supermarket Type1** → if the item is sold in this outlet type, sales increase by **≈1260**.  

These indicate that items from specific outlet categories have a notably higher sales impact.

---

### 🔹 Top 10 Most Important Features (Random Forest)
<img width="900" height="520" alt="Top 10 Feature Importances" src="https://github.com/user-attachments/assets/b6a4679c-def0-4aab-b373-450614360430" />

The chart above highlights the most influential features identified by the **Random Forest Regressor**.  
Feature importance measures how much each variable contributed to reducing prediction error during training.

#### 🧠 Key Insights:
The **5 most important features** are:
- **Item_MRP**
- **Item_Visibility**
- **Outlet_Type_Supermarket Type1**
- **Outlet_Type_Supermarket Type3**
- **Item_Weight**

These were the most used by the model during the learning process to make accurate predictions.  
However, it’s important to note that **feature importance does not indicate directionality** —  
it shows how influential a variable is, but not whether it increases or decreases sales.

---

## 5. Evaluation & Recommendations
- **Linear Regression** → simple baseline; limited in capturing nonlinear patterns.  
- **Untuned Random Forest** → strong training results but clear overfitting.  
- **Tuned Random Forest** → best balance between bias and variance, with improved generalization (≈60% variance explained).  

**✅ Final Recommendation:**  
Deploy the **Tuned Random Forest Regressor** as the production model.  

**Future improvements:**
- Add more engineered features (e.g., interactions, regional or seasonal trends).  
- Use cross-validation for better model stability.  
- Explore ensemble or boosting methods like **XGBoost** or **LightGBM** for potential performance gains.

--- 


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

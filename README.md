![logan-voss-WRmoJBqzXNA-unsplash](https://github.com/user-attachments/assets/1ca668a3-0af5-405f-ac8a-a79af6434c11)
# Prediction-Of-Product-Sales
#  Sales Prediction for Food Items

This project focuses on predicting the sales of food items across various stores.  
The goal is to help retailers understand the properties of products and outlets that play a crucial role in increasing sales.  

---

## 📊 Project Overview
- **Objective**: Build a predictive model for `Item_Outlet_Sales` based on product and store characteristics.  
- **Data Source**: https://drive.google.com/file/d/1syH81TVrbBsdymLT_jl2JIf6IjPXtSQw/view  
- **Key Tasks**:
  1. Data loading and cleaning.
  2. Exploratory Data Analysis (EDA).
  3. Feature engineering and modeling.

---

## 📂 Dataset Information
The dataset contains information about products and outlets, with the target variable being **Item_Outlet_Sales**.
for this Dataset there is 8523 Rows and 12 Columns
## Data Dictionary

| Variable Name              | Description |
|-----------------------------|-------------|
| `Item_Identifier`           | Product ID |
| `Item_Weight`               | Weight of product |
| `Item_Fat_Content`          | Whether the product is low-fat or regular |
| `Item_Visibility`           | % of display area allocated to the product |
| `Item_Type`                 | Category of the product |
| `Item_MRP`                  | Maximum Retail Price (list price) |
| `Outlet_Identifier`         | Store ID |
| `Outlet_Establishment_Year` | Year the store was established |
| `Outlet_Size`               | Store size (ground area covered) |
| `Outlet_Location_Type`      | Type of city in which store is located |
| `Outlet_Type`               | Type of outlet (grocery, supermarket, etc.) |
| `Item_Outlet_Sales`         | **Target variable**: Sales of the product |

---

## 🛠️ Part 2: Data Cleaning
Using **Pandas** to prepare the dataset for analysis:
1. Checked the number of rows and columns.  
2. Inspected datatypes of each variable.  
3. Removed duplicate.  
4. Identified missing values and replaced them with placeholder values.  
5. Ensured there are no missing values after cleaning.  
6. Standardized categorical entries (e.g., fixing inconsistencies in `Item_Fat_Content`).  
7. Generated summary statistics for numerical features (min, max, mean, etc.).  

---

## 📈 Part 3: Exploratory Data Analysis (EDA)
Created different plots to explore the dataset: 
Using **Matplotlib** and **Seaborn** Wrapper 

- **Histograms** → to view distributions of numerical features.  
- **Boxplots** → to visualize statistical summaries and outliers.  
- **Countplots** → to check frequency distributions of categorical features.  
- **Heatmap** → to see correlations between numerical variables.  

---

## 🔍 Key Insights from Visuals

### 1️⃣ Product Sales Distribution (Target)
<img width="764" height="525" alt="image" src="https://github.com/user-attachments/assets/968c675b-859d-4bc6-aa24-7d32c685b4f2" />

[plot.html](https://github.com/user-attachments/files/22300171/plot.html)

[Copy_of_Prediction_Of_Product_Sales.ipynb - Colab.html](https://github.com/user-attachments/files/22300244/Copy_of_Prediction_Of_Product_Sales.ipynb.-.Colab.html)

The distribution of product sales is positively skewed. The majority of products record low to moderate sales (mostly under 2000 units), while a smaller number reach much higher sales values.  


---
### 2️⃣ Distribution of `Item_Weight`
<img width="580" height="455" alt="Distributions of Items Weight" src="https://github.com/user-attachments/assets/b957dfeb-37cf-45e8-bd00-0602163b0a97" />


Most items weigh between **5–20 kg**, with a peak around **-1 kg** due to the missing values.  


---

### 3️⃣ Correlation Heatmap
<img width="1273" height="836" alt="Heatmap" src="https://github.com/user-attachments/assets/e7636b8f-f367-414c-829e-3f08700ddf7a" />


 
`Item_MRP` has the strongest positive correlation with `Item_Outlet_Sales`, indicating that price plays a significant role in sales prediction.  

---



## 🚀 Next Steps
- Feature engineering to improve data quality.  
- Training predictive models to estimate sales.  
- Evaluating performance with regression metrics.  

---
##  Information 
 For any Questions or Recommendations:
  - Bashar Bayatna Mechatronics Engineer|Junior Data Scientist
  - Basharbayatna11@gmail.com

---




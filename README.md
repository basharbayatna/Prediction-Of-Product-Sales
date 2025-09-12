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

### 1️⃣ Invistegating the Outlet Location Type 



<img width="589" height="390" alt="image" src="https://github.com/user-attachments/assets/4fec295c-21b2-4925-9cdb-2d09e9e194fc" />














<img width="762" height="524" alt="image" src="https://github.com/user-attachments/assets/217d97bf-775a-4492-




[plot.html](https://github.com/user-attachments/files/22300171/plot.html)


The distribution of product sales is positively skewed. The majority of products record low to moderate sales (mostly under 2000 units), while a smaller number reach much higher sales values.  


---
### 2️⃣ Invistegating the Outlet Type 
<img width="590" height="390" alt="image" src="https://github.com/user-attachments/assets/8fc51bcf-e67a-4c99-8a08-20c97ef8b818" />

<img width="589" height="390" alt="image" src="https://github.com/user-attachments/assets/67a5c883-c62f-49a8-9289-bbd35d1558cf" />





---

### 3️⃣ Invistegating the Relation between the Location & Type Vs. Item Outlet sales  
<img width="590" height="390" alt="image" src="https://github.com/user-attachments/assets/43e60c2b-e7a2-4c96-b4b8-1ec8957d0528" />

 
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




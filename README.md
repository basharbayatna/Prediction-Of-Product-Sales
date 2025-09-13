![logan-voss-WRmoJBqzXNA-unsplash](https://github.com/user-attachments/assets/1ca668a3-0af5-405f-ac8a-a79af6434c11)

# Prediction of Product Sales 🍎🛒
## Sales Prediction for Food Items

This project focuses on predicting the sales of food items across various stores.  
The goal is to help retailers understand the properties of products and outlets that play a crucial role in increasing sales.  
Additionally, this analysis aims to answer some **critical business questions** to guide strategic decisions, such as which outlet types and locations maximize sales, which outlets are most reliable, and where to focus expansion efforts for optimal profitability.

---

## 📊 Project Overview
- **Objective**: Build a predictive model for `Item_Outlet_Sales` based on product and store characteristics.  
- **Data Source**: [Download Dataset](https://drive.google.com/file/d/1syH81TVrbBsdymLT_jl2JIf6IjPXtSQw/view)  
- **Key Tasks**:
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

## 🛠️ Part 2: Data Cleaning
Using **Pandas** to prepare the dataset for analysis:
1. Checked the number of rows and columns  
2. Inspected datatypes of each variable  
3. Removed duplicates  
4. Identified missing values and replaced them with placeholder values  
5. Ensured there are no missing values after cleaning  
6. Standardized categorical entries (e.g., fixing inconsistencies in `Item_Fat_Content`)  
7. Generated summary statistics for numerical features (min, max, mean, etc.)  

---

## 📈 Part 3: Exploratory Data Analysis (EDA)
Using **Matplotlib** and **Seaborn** to explore the dataset:

- **Histograms** → visualize distributions of numerical features  
- **Boxplots** → show statistical summaries and detect outliers  
- **Countplots** → check frequency distributions of categorical features  
- **Heatmap** → examine correlations between numerical variables  

---
### 📌 Business Questions To Answer  

1. **Which outlet types are most common?**  

2. **Which outlet types generate the highest sales?**  

3. **How does location impact sales?**  

4. **How do outlet type and location interact to affect sales?**  

5. **Which outlets are consistently reliable?**  

6. **Where should a business focus to maximize profitability?**  

## 🔍 Key Insights from Visuals

### 1️⃣ Investigating the Outlet Location Type

#### Plot 1: Outlet_Location_Type Count
<img width="590" height="390" alt="image" src="https://github.com/user-attachments/assets/43e60c2b-e7a2-4c96-b4b8-1ec8957d0528" />

- **Tier 3:** ~3,400 outlets (highest)  
- **Tier 2:** ~2,800 outlets  
- **Tier 1:** ~2,400 outlets (lowest)  

> **Insight:** Tier 3 outlets are the most common, but this plot doesn’t indicate sales performance.

---

#### Plot 2: Outlet_Location_Type vs. Item_Outlet_Sales
<img width="589" height="390" alt="image" src="https://github.com/user-attachments/assets/4fec295c-21b2-4925-9cdb-2d09e9e194fc" />

- **Tier 3:** Highest median sales, wide spread, some outliers > $12,000  
- **Tier 1 & Tier 2:** Lower median sales, fewer extreme outliers  

> **Insight:** Tier 3 outlets not only are most frequent but also tend to generate the **highest sales**, showing a strong link between location tier and performance.

---

### 2️⃣ Investigating the Outlet Type

#### Plot 1: Outlet Type Count
<img width="590" height="390" alt="image" src="https://github.com/user-attachments/assets/8fc51bcf-e67a-4c99-8a08-20c97ef8b818" />

- **Supermarket Type 1:** most common, >5,000 outlets  
- **Supermarket Type 2, Grocery Store, Supermarket Type 3:** ~1,000 each  

> **Insight:** The dataset is heavily skewed towards Supermarket Type 1 outlets.

---

#### Plot 2: Outlet Type vs. Item_Outlet_Sales
<img width="589" height="390" alt="image" src="https://github.com/user-attachments/assets/67a5c883-c62f-49a8-9289-bbd35d1558cf" />

- **Grocery Stores:** lowest sales, tight distribution, median near $0  
- **Supermarket Type 3:** highest median sales, wide range  
- **Supermarket Type 1:** second-highest median sales, wide range  
- **Supermarket Type 2:** similar range to Type 1 & 3 but lower median  

> **Insight:** While Supermarket Type 1 is the most frequent, **Supermarket Type 3** achieves the highest average sales, and Grocery Stores perform the lowest.

---

### 3️⃣ Investigating the Relationship between Outlet Type, Location & Sales
<img width="762" height="518" alt="image" src="https://github.com/user-attachments/assets/c3363036-2b67-479a-a399-d196a759e9e4" />  

[View interactive heatmap](https://github.com/user-attachments/files/22300171/plot.html)

#### Heatmap Analysis: Average Product Sales by Outlet Type and Location

**Key Observations:**

- **Supermarket Type 3** in **Tier 3** locations: highest average sales **$3,694**  
- **Supermarket Type 1:** consistent across all tiers **$2,299–$2,324**  
- **Supermarket Type 2:** appears only in Tier 3, avg. sales **$1,995**  
- **Grocery Stores:** extremely low sales in Tier 1 (**$340**) and Tier 3 (**$339**)  

**Location Insights:**

- Tier 3: high potential; performance depends on outlet type  
- Tier 1: mix of high-performing Type 1 and low-performing Grocery Stores  
- Tier 2: only Type 1 outlets present; avg. sales **$2,324**  

**Strategic Recommendation:**  
Focus on **Supermarket Type 3 in Tier 3 locations** for maximum sales. Avoid Grocery Stores in any tier.  

---

### 📌 Business Questions Answered

1. **Which outlet types are most common?**  
   Supermarket Type 1 is the most frequent outlet.

2. **Which outlet types generate the highest sales?**  
   Supermarket Type 3 achieves the highest average and median sales.

3. **How does location impact sales?**  
   Tier 3 locations show the potential for very high sales.

4. **How do outlet type and location interact to affect sales?**  
   The combination of **Supermarket Type 3 in Tier 3** yields the highest sales.

5. **Which outlets are consistently reliable?**  
   Supermarket Type 1 shows stable sales across all tiers.

6. **Where should a business focus to maximize profitability?**  
   Prioritize **Supermarket Type 3 in Tier 3**; avoid Grocery Stores.

---

## 🚀 Next Steps
- Feature engineering to improve predictive power  
- Training regression models to estimate sales  
- Evaluating model performance using metrics like RMSE and R²  

---

## ℹ️ Contact Information
For any questions or recommendations:  
- **Bashar Bayatna**, Mechatronics Engineer | Junior Data Scientist  
- Email: [Basharbayatna11@gmail.com](mailto:Basharbayatna11@gmail.com)

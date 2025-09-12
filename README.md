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
## 1️⃣ Invistegating the Outlet Location Type 

### Plot 1: Outlet_Location_Type Count
<img width="590" height="390" alt="image" src="https://github.com/user-attachments/assets/43e60c2b-e7a2-4c96-b4b8-1ec8957d0528" />

- Shows the number of outlets in each tier.  
- **Tier 3:** ~3,400 outlets (highest)  
- **Tier 2:** ~2,800 outlets  
- **Tier 1:** ~2,400 outlets (lowest)  

> **Insight:** Tier 3 outlets are the most common, but this plot doesn’t indicate sales performance.

---

### Plot 2: Outlet_Location_Type vs. Item_Outlet_Sales


<img width="589" height="390" alt="image" src="https://github.com/user-attachments/assets/4fec295c-21b2-4925-9cdb-2d09e9e194fc" />


- Combines a strip plot (individual sales) with a box plot (distribution summary).  
- **Tier 3:** Highest median sales, wide spread, some outliers > $12,000  
- **Tier 1 & Tier 2:** Lower median sales, fewer extreme outliers  

> **Insight:** While Tier 3 outlets are the most frequent, they also tend to generate the **highest sales**, showing a strong link between outlet type and performance.







 


---
### 2️⃣ Invistegating the Outlet Type 
## Plot 1: Outlet_Type Count

<img width="590" height="390" alt="image" src="https://github.com/user-attachments/assets/8fc51bcf-e67a-4c99-8a08-20c97ef8b818" />
## Outlet Analysis

This bar chart shows the frequency of each outlet type in the dataset:

- **Supermarket Type 1** is by far the most common, with a count of over 5,000.
- **Supermarket Type 2**, **Grocery Store**, and **Supermarket Type 3** are much less common, each with counts around 1,000.

> **Insight:** The dataset is heavily skewed towards Supermarket Type 1 outlets.

## Plot 2: Outlet_Type vs. Item_Outlet_Sales

<img width="589" height="390" alt="image" src="https://github.com/user-attachments/assets/67a5c883-c62f-49a8-9289-bbd35d1558cf" />

This plot combines a strip plot with a box plot overlay to show the relationship between outlet type and sales:

- **Grocery Stores** have the lowest sales, with a very tight distribution and median sales close to zero, indicating low performance.
- **Supermarket Type 3** has the highest median sales and a wide range of sales, with some outlets achieving very high sales.
- **Supermarket Type 1** has the second-highest median sales and a wide distribution, performing better than Supermarket Type 2 and Grocery Stores, but not as well as Supermarket Type 3.
- **Supermarket Type 2** has a similar sales range to Supermarket Type 1 and Type 3, but its median sales are lower.

> **Insight:** Although Supermarket Type 1 is the most frequent outlet, **Supermarket Type 3** achieves the highest sales on average, while **Grocery Stores** perform the lowest.





---

### 3️⃣ Invistegating the Relation between the Location & Type Vs. Item Outlet sales  

<img width="762" height="518" alt="image" src="https://github.com/user-attachments/assets/c3363036-2b67-479a-a399-d196a759e9e4" />

 [plot.html](https://github.com/user-attachments/files/22300171/plot.html)
## Heatmap Analysis: Average Product Sales by Outlet Type and Location

This heatmap combines insights from **Outlet_Type** and **Outlet_Location_Type** to provide a more integrated view of average product sales. It helps us understand how outlet type and location interact to influence sales performance.

---

### 1. The Impact of Outlet_Type

- **Supermarket Type 3** in **Tier 3** locations has the highest average sales at **$3,694**, confirming our earlier observation from the sales distribution plot where Type 3 had the highest median sales. The heatmap specifies that this peak performance is tied to Tier 3 locations.
- **Supermarket Type 1** shows consistently high average sales across all tiers, ranging from **$2,299 to $2,324**, reinforcing its role as a reliable high-volume performer.
- **Supermarket Type 2** appears only in Tier 3 locations, with average sales of **$1,995**.
- **Grocery Stores** have extremely low average sales in both Tier 1 (**$340**) and Tier 3 (**$339**), confirming they are the lowest-performing outlet type.

---

### 2. The Impact of Outlet_Location_Type

- **Tier 3 locations** show a wide range of performance:
  - Grocery Stores perform poorly.
  - Supermarket Type 2 and Type 3 achieve very high sales, with Type 3 peaking.  
  **Insight:** Tier 3 locations have high potential, but performance depends heavily on outlet type.
- **Tier 1 locations** have a mix of high-performing Supermarket Type 1 outlets and low-performing Grocery Stores. No Supermarket Type 2 or 3 outlets are present, so the range of performance is narrower.
- **Tier 2 locations** only show Supermarket Type 1 outlets, with average sales of **$2,324**, consistent with other tiers. The absence of other outlet types may reflect sample size or strategic business placement.

---

### 3. Conclusion and Strategic Insights

- Tier 3 locations drive the highest sales, thanks to **Supermarket Type 2 and Type 3** outlets.
- **Supermarket Type 1** is the most common outlet type and consistently performs well across all locations.
- **Grocery Stores** perform poorly in all locations, indicating low profitability regardless of placement.

**Strategic Recommendation:** To maximize sales, businesses should focus on opening **Supermarket Type 3 outlets in Tier 3 locations**. Conversely, opening a Grocery Store in any tier is unlikely to be profitable.

By combining insights from frequency plots, sales distribution plots, and this heatmap, we get a comprehensive understanding of which outlet types and locations are most critical for high sales performance.

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




# Retail Sales Exploratory Data Analysis (EDA)

## Project Overview

This project performs an in-depth **Exploratory Data Analysis (EDA)** on a retail sales dataset to uncover patterns in:

- Customer purchasing behavior  
- Regional sales performance  
- Product demand  
- Payment preferences  

The goal is to transform raw transactional data into actionable business insights that support decision-making in **marketing, inventory management, and revenue optimization**.

The analysis covers:

- Data cleaning  
- Feature engineering  
- Statistical exploration  
- Data visualization  

**Tools used:** Pandas, Matplotlib, Seaborn  

---

## 1. Dataset Overview

The dataset contains **5,050 retail transactions** with 9 variables describing transaction details.

| Variable         | Description                    |
|-----------------|--------------------------------|
| TransactionID    | Unique transaction identifier |
| CustomerID       | Customer identifier           |
| ProductID        | Product purchased             |
| Quantity         | Number of items purchased     |
| UnitPrice        | Price per unit                |
| Discount         | Discount applied              |
| Region           | Sales region                  |
| PaymentMethod    | Method of payment             |
| InvoiceDate      | Transaction date              |

**Initial Dataset Size:**  
- Rows: 5,050  
- Columns: 9  

---

## 2. Descriptive Statistics

| Metric                    | Value |
|----------------------------|-------|
| Average Quantity Purchased | 5 units |
| Average Unit Price         | 252.89 |
| Minimum Unit Price         | 5.08 |
| Maximum Quantity           | 9 units |

**Insight:**  
- Wide range in unit prices indicates a diverse product catalog with both low-cost and high-value items contributing to revenue.

---

## 3. Missing Value Analysis

| Column         | Missing Values |
|----------------|----------------|
| Region         | 1,114          |
| PaymentMethod  | 1,042          |
| UnitPrice      | 100            |

**Data Cleaning Actions:**

- Missing `UnitPrice` values imputed using **median**.  
- **48 duplicate rows removed**.  

**Updated Dataset Size:** 5,002 transactions  

---

## 4. Feature Engineering

**Time-Based Features:**  

- `Year` – extracted from `InvoiceDate`  
- `Month` – seasonal trend analysis  
- `Weekday` – weekly purchasing patterns  

**Revenue Feature:**  

- `TotalSales = Quantity × UnitPrice × (1 ? Discount)`  
- Represents **actual revenue per transaction after discounts**  

---

## 5. Outlier Detection

- Outliers in `TotalSales` identified using **IQR method**.  
- **64 records removed**  
- **Final dataset size:** 4,938 transactions  

**Insight:** Removing extreme values prevents distortion in summary statistics and trends.  

---

## 6. Revenue Analysis

| Metric                     | Value |
|----------------------------|-------|
| Total Revenue              | 5,121,515.48 |
| Average Revenue per Transaction | ? 1,037.16 |

**Insight:** Average customer spends ~?1,037 per transaction, useful for **customer value segmentation and pricing strategies**.

---

## 7. Regional Sales Performance

| Region         | Total Sales |
|----------------|------------|
| Port Harcourt  | 2,206,349  |
| Abuja          | 1,016,012  |
| Kano           | 958,664    |
| Lagos          | 940,490    |

**Insight:**  

- Port Harcourt contributes over **43% of total revenue**, the dominant market.  
- Suggests **stronger customer demand**, higher penetration, and better-performing product mix.  

---

## 8. Payment Method Analysis

| Payment Method | Transactions |
|----------------|-------------|
| Cash           | 2,028       |
| Transfer       | 1,002       |
| Card           | 957         |
| POS            | 951         |

**Insight:**  

- Cash accounts for over 40% of transactions  
- Opportunity to **increase digital payment adoption**

---

## 9. Monthly Sales Trends

| Month      | Sales   |
|-----------|---------|
| January   | 478,139 |
| February  | 368,437 |
| March     | 450,553 |
| April     | 381,932 |
| May       | 393,291 |
| June      | 408,456 |
| July      | 460,073 |
| August    | 465,030 |
| September | 455,175 |
| October   | 432,957 |
| November  | 406,964 |
| December  | 420,507 |

**Average Monthly Sales:** ? 426,793  

**Insight:** Peak sales periods: **January, July, August**, reflecting post-holiday spending and mid-year purchasing cycles.  

---

## 10. Product Performance

| ProductID | Sales  |
|-----------|--------|
| 365       | 53,790 |
| 216       | 41,222 |
| 283       | 40,143 |
| 367       | 39,652 |
| 286       | 39,215 |

**Insight:** Small number of products generate a **disproportionate share of revenue**, highlighting opportunities for targeted promotions.

---

## 11. High-Value Customers

| CustomerID | Total Spending |
|-----------|----------------|
| 1038      | 17,333         |
| 1735      | 17,204         |
| 1276      | 16,833         |
| 1935      | 15,981         |
| 1516      | 15,776         |

**Insight:** Revenue is partially driven by **premium customers**, suggesting opportunities for loyalty programs.

---

## 12. Regional Product Demand

| ProductID | Abuja | Kano | Lagos | Port Harcourt |
|-----------|-------|------|-------|---------------|
| 200       | 7     | 23   | 30    | 22            |
| 201       | 19    | 18   | 13    | 63            |
| 202       | 4     | 17   | 35    | 35            |

**Insight:**  

- Product demand varies by region  
- Supports **region-specific inventory planning and marketing strategies**  

---

## 13. Key Business Insights

1. **Regional dominance:** Port Harcourt drives most revenue  
2. **Cash-based economy persists:** Over 40% of transactions  
3. **Seasonal demand patterns:** Peaks in January and mid-year  
4. **Revenue concentration:** Few products and customers drive most revenue  

---

## 14. Business Recommendations

1. **Focus on high-performing regions:** Increase marketing in Port Harcourt  
2. **Promote digital payments:** Incentivize card/POS adoption  
3. **Optimize inventory:** Stock top-performing products  
4. **Customer retention strategy:** Implement loyalty programs for high-value customers  

---

## 15. Tools and Technologies

- Python  
- Pandas  
- Matplotlib  
- Seaborn  
- Jupyter Notebook  

---

## 16. Repository Structure

retail-sales-eda/
¦
+-- data/
¦ +-- retail_sales_raw.csv
¦
+-- notebooks/
¦ +-- retail_sales_eda.ipynb
¦
+-- images/
¦ +-- Discount_Distribution.png
¦ +-- Monthly_Sales_Trend.png
¦ +-- Outlier_Detection.png
¦ +-- Product_by_Region_Heatmap.png
¦ +-- Quantity_Distribution.png
¦ +-- Sales_by_Region.png
¦ +-- UnitPrice_Distribution.png
¦
+-- outputs/
¦ +-- data_preprocessed.csv
¦
+-- README.md

---

## 17. Future Improvements

1. **Advanced Customer Segmentation:** Apply RFM analysis or clustering  
2. **Predictive Analytics:** Build models to forecast sales and customer behavior  
3. **Time Series Forecasting:** Use ARIMA or Prophet for trends and seasonality  
4. **Enhanced Data Cleaning:** Advanced imputation and missing data investigation  
5. **Dashboard Integration:** Real-time business insights via Power BI or Tableau  
6. **Profitability Analysis:** Incorporate cost data to evaluate high-profit products  
7. **Regional Strategy Optimization:** Optimize pricing and product distribution  

---

## Author

**Adedayo Adebayo**  
Data Scientist | Business Analyst


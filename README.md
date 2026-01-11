# 📦 Flipkart Ecommerce Insights — Power BI Dashboard

A complete end-to-end Power BI analytics project designed using Flipkart ecommerce transaction data.  
The goal: convert raw retail numbers into actionable business intelligence using Power BI, DAX, and clean visual storytelling.

---

## 📂 Dataset Overview
Dataset includes the following fields:

- category  
- brand  
- seller  
- seller_city  
- discount_percent  
- final_price  
- rating  
- review_count  
- stock_available  
- units_sold  
- listing_date  
- delivery_days  
- return_policy_days  
- is_returnable  
- payment_modes  
- product_score  
- seller_rating  

---

## 🧹 Data Preparation (Power Query)
Data cleaning steps performed:

- Removed duplicates  
- Corrected inconsistent naming of categories/brands  
- Ensured date type formatting for listing_date  
- Numeric conversion for prices & units_sold  
- Added calculated fields for delivery status & return grouping  

---

## 📊 Power BI Dashboard Structure

### **Page 1 — Main Dashboard**
- KPI Cards (Revenue, Orders, Units Sold, Rating)
- Yearly Revenue Trend
- Category Contribution Overview

![Main_dashboard](https://github.com/user-attachments/assets/970915c4-79d2-4d4a-a036-b67e929b7bf7)

### **Page 2 — Sales Dashboard**
- Revenue by Month
- Orders Trend Line
- Units Sold by Category

![Sales_dashboard](https://github.com/user-attachments/assets/6c6fedd9-8da9-42eb-85f5-8a18b68fe48a)

### **Page 3 — Product & Brand Performance**
- Brand Revenue Breakdown
- Brand Ratings Comparison
- Units Sold by Brand

![Product_Brand_performance](https://github.com/user-attachments/assets/cf702210-ae4d-463c-94c0-efc9ba1c3ebc)

### **Page 4 — Brand & Category Insights**
- Revenue & Volume Matrix
- Quality & Experience Matrix
- Category share visualization

![Brand_Category_insights](https://github.com/user-attachments/assets/9fdbd10d-36a8-4027-9a0f-2b4c360642a5)

### **Page 5 — Category & Return Analysis**
- Return % by Categories
- Returnable vs Non-returnable Chart
- Avg Delivery Days by Category

![Category Return Analysis](https://github.com/user-attachments/assets/9131a9ba-9f37-4bac-aa3e-c4dc0b3d99f4)

### **Page 6 — Brand Analytics Review**
- Deep dive per brand
- Revenue, Returns, Ratings, Units Sold, Delivery Days
- Drill-through enabled page

![Brand Analytics View](https://github.com/user-attachments/assets/ca9ab16a-a20c-42e7-856e-850b61f2399b)

---

## ⚙️ DAX Measures Used

### **📌 Sales KPIs**

```Total Revenue
-- Total Revenue = SUM('flipkard1'[final_price])

-- Total Orders = COUNTROWS('flipkard1')

-- Total Units Sold = SUM('flipkard1'[units_sold])
```

### **📌 Rating Metrics**

```Total revenue
- Average Rating = AVERAGE('flipkard1'[rating])

- Rating Category =
 IF(
 [Average Rating] >= 4, "High",
 IF([Average Rating] >= 3, "Medium", "Low")
  )
```


### **📌 Return Calculations**

```text
-- Return Orders =
CALCULATE(
COUNTROWS('flipkard1'),
'flipkard1'[is_returnable] = TRUE()
)

-- Return % =
DIVIDE([Return Orders], [Total Orders], 0)

```


---

## 🏁 Summary
This project demonstrates:

- Data cleaning  
- Power BI modeling  
- DAX measure creation  
- Dashboard design  
- Business insight extraction  

A full analytics workflow from raw CSV ➝ polished insights.









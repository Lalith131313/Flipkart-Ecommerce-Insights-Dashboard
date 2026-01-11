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
- Monthly Revenue Trend
- Category Contribution Overview

### **Page 2 — Sales Dashboard**
- Revenue by Month
- Orders Trend Line
- Units Sold by Category

### **Page 3 — Product & Brand Performance**
- Brand Revenue Breakdown
- Brand Ratings Comparison
- Units Sold by Brand

### **Page 4 — Brand & Category Insights**
- Revenue & Volume Matrix
- Quality & Experience Matrix
- Category share visualization

### **Page 5 — Category & Return Analysis**
- Return % by Categories
- Returnable vs Non-returnable Chart
- Avg Delivery Days by Category

### **Page 6 — Brand Analytics Review**
- Deep dive per brand
- Revenue, Returns, Ratings, Units Sold, Delivery Days
- Drill-through enabled page

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









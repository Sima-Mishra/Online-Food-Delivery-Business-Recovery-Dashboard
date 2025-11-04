# 🥡 Online Food Delivery Business Recovery Dashboard

### 📊 *Analyzing customer, restaurant, and delivery recovery trends during the crisis period*

---

## 🚀 **Project Overview**

This Power BI project provides a detailed business recovery analysis for an **Online Food Delivery Platform** across India, highlighting **pre-crisis (Jan–May 2025)** and **crisis (Jun–Sep 2025)** performance trends.

The dashboard helps identify:

* Customer churn & recovery behavior
* Restaurant and cuisine performance changes
* Delivery efficiency & cancellation trends
* Customer sentiment shifts from reviews

---

## 🧩 **Key Objectives**

| Primary Questions                                                             | Secondary Questions                                                         |
| ----------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| How did total orders, revenue, and active customers change during the crisis? | Which cities and cuisines faced the steepest decline or recovery?           |
| Which customer segments were most affected?                                   | Which restaurants retained or lost customers?                               |
| How did delivery times, cancellations, and payments impact business recovery? | What was the overall customer sentiment shift before and during the crisis? |

---

## 🗂️ **Dashboard Pages**

### 🟣 **Page A – Executive Overview**

High-level summary of key business metrics.

**Visuals:**

* Total Orders, Net Revenue, Avg Rating, Cancellation %, On-time Delivery %
* Monthly Orders & MoM Change Chart
* Top Cities by Order Decline %
* Top 5 Cuisines by Orders
* Revenue, Cancellation & Rating Trend

📸 **Preview:**
![Executive Overview](https://github.com/user-attachments/assets/5ee7503b-4d11-42a7-bd56-5f241774084f)


---

### 🟢 **Page B – Customer Overview**

Tracks customer recovery, churn, and engagement patterns.

**Visuals:**

* Active Customers by City and Segment
* Churned vs Recovered vs New Customers (Stacked Bar)
* Top 5% High-Value Churned Customers Table
* Pre vs Crisis Order Count per City

📸 **Preview:**
![Customer Overview](https://github.com/user-attachments/assets/711a24ae-1d11-40ee-8ce3-59d56e89b23e)


---

### 🔵 **Page C – Delivery Overview**

Analyzes delivery performance and cancellations during the crisis.

**Visuals:**

* Avg Delivery Time Trend
* On-Time Delivery % by City
* Cancellation Rate by Month
* Delivery Mode & Payment Method Breakdown

📸 **Preview:**
![Delivery Overview](https://github.com/user-attachments/assets/7eab7e69-114d-46e4-a0c1-9a4a5bf08cb4)

---

### 🟠 **Page D – Restaurant Overview**

Examines restaurant performance and cuisine revenue trends.

**Visuals:**

* Top 10 Restaurants – Pre vs Crisis Revenue
* Cuisine-Wise Revenue Change %
* Top Menu Items by Volume
* Restaurant Summary Table (Pre vs Crisis Metrics)

📸 **Preview:**
![Restaurant Overview](https://github.com/user-attachments/assets/924427f0-de4f-4d45-918f-ca67141edc9e)

---

### 🔴 **Page E – Sentiment Overview**

Analyzes customer feedback and sentiment recovery patterns.

**Visuals:**

* Avg Sentiment Trend (Pre vs Crisis)
* Negative Reviews % by City
* Word Cloud from Review Texts
* Sentiment Bucket Share (Positive / Neutral / Negative)
* Sample Review Table

📸 **Preview:**
![Sentiment Overview](https://github.com/user-attachments/assets/4a659ffb-e292-4d3a-b2f9-d1d4a7762e0b)

---

## 🧮 **Data Model**

**Fact Tables:**

* `fact_orders` → order details
* `fact_ratings` → ratings & review text
* `fact_delivery` → delivery & payment data

**Dimension Tables:**

* `dim_customer` → customer demographics
* `dim_restaurant` → restaurant & cuisine info
* `dim_date` → calendar & phase classification

**Relationships:**

* One-to-many between all `dim_` tables and corresponding `fact_` tables.

📸 **Data Model:**
![Data Model](https://github.com/user-attachments/assets/9730e40e-16e5-4934-873c-57b53c8bb467)

---

## 🧠 **Key DAX Measures**

```DAX
-- Total Orders
Total Orders = COUNTROWS(fact_orders)

-- Revenue Pre vs Crisis
Revenue_Pre = CALCULATE([Total Revenue], 'dim_date'[Phase] = "Pre-Crisis")
Revenue_Crisis = CALCULATE([Total Revenue], 'dim_date'[Phase] = "Crisis")

-- % Decline in City Orders
%Decline_City = 
DIVIDE(([PreCrisisOrders] - [CrisisOrders]), [PreCrisisOrders]) * 100

-- Sentiment Score
Avg_Sentiment = AVERAGE(fact_ratings[sentiment_score])
```

---

## 🎯 **Key Insights**

✅ Orders dropped by **~70%** during the crisis period.
✅ **Bengaluru** & **Mumbai** showed the most significant recovery post-crisis.
✅ **South Indian cuisine** remained the most resilient category.
✅ Top 5% high-value customers contributed to over **40% revenue loss** due to churn.
✅ Sentiment recovery improved post-crisis, indicating **better customer experience**.

---

## ⚙️ **Tools & Techniques Used**

* **Microsoft Power BI** – Dashboard design, DAX modeling, interactions
* **Power Query** – Data cleaning and transformation
* **DAX** – Calculations for KPIs, phase-based comparisons, sentiment measures
* **Excel / CSV** – Data source integration
* **Text Analytics (NLP)** – Sentiment scoring for review text

---

## 🧭 **Interactivity & Navigation**

* Consistent **slicers**: `City`, `Month`, `Phase` synced across all pages.
* Custom **buttons and bookmarks** for page navigation.
* Smart **edit interactions** to control which visuals respond to slicers.

---

## 📈 **How to Use**

1. Download `.pbix` file from this repository.
2. Open in **Power BI Desktop**.
3. Use the slicers to explore city, cuisine, and sentiment trends.

---

## 🏆 **Conclusion**

The dashboard gives management a **360° view** of recovery performance across customers, restaurants, deliveries, and sentiments — helping identify focus areas for strategic actions in post-crisis recovery.


---

## 👩‍💻 **Author**

**Sima Mishra**
📧 [LinkedIn](https://www.linkedin.com/in/sima-analyst/)
•📊 Power BI & Data 

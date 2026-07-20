# credit_card_financial_analytics
# Credit Card Financial & Customer Analytics Dashboard (Power BI Portfolio Project)

A comprehensive, production-grade Power BI business intelligence solution designed to analyze credit card transaction metrics, portfolio revenue, and customer demographics. This end-to-end project converts raw financial data into actionable business insights, helping stakeholders optimize card portfolios, mitigate risk, and understand consumer behavior.

---

## 📊 Business Problem & Project Overview
Financial institutions require deep visibility into credit card usage patterns, revenue streams, and customer retention to drive growth and manage risk. 

This project delivers two synchronized reporting views to solve this problem:
1. **Credit Card Transaction Report:** Focuses on operational efficiency, revenue distribution, and purchasing modes.
2. **Credit Card Customer Report:** Focuses on demographic segmentation, user retention, satisfaction profiles, and account delinquency risk.

---

## 🛠️ Dashboard Architecture & Key Visuals

### 1. Credit Card Transaction Report (Financial View)
* **Core KPIs:** Monitors portfolio metrics including **$10M Total Revenue**, **45M Total Transactions**, **$8M Total Interest**, and **656K Transaction Volume**.
* **Revenue by Channel (Use):** Highlights transaction entry methods, showing *Swipe* as the dominant driver ($6.3M) over *Chip* ($2.9M) and *Online* ($0.6M).
* **Portfolio Segmentation:** Details revenue performance by card tier, identifying *Blue* tier cards as the highest portfolio revenue generator ($8.3M).
* **Expense & Seasonal Trends:** Categorizes consumer behavior across expense types (Bills, Entertainment, Fuel) and cross-references quarterly revenue fluctuations with overall transaction volumes to track seasonal performance.

### 2. Credit Card Customer Report (Demographic & Risk View)
* **Demographic Breakdown:** Segments active clients by age group (identifying the **40–50 age bracket** as the primary user base) and evaluates gender and marital status revenue generation.
* **Risk & Delinquency Management:** Features a risk chart mapping account delinquency against consumer satisfaction scores to pinpoint potential churn or default triggers.
* **Temporal Trend Analysis:** Includes a 52-week rolling line chart tracking total revenue generated across genders to discover long-term usage trends.

---

## 💾 Data Modeling & Advanced DAX Measures
This project utilizes an optimized star schema data model with dedicated dimension tables (Customer, Card Tiers) linked to central fact tables (Transactions). Advanced Time Intelligence and analytical reporting were enabled using **Data Analysis Expressions (DAX)**.

### Key DAX Formula Examples Implemented:

* **Total Revenue Calculation:**
  ```dax
  Total_Revenue = SUM('Credit_Card_Data'[Annual_Fees]) + SUM('Credit_Card_Data'[Total_Trans_Amt]) + SUM('Credit_Card_Data'[Interest_Earned])
  ```

* **Total Transaction Volume:**
  ```dax
  Total_Transaction_Count = COUNT('Credit_Card_Data'[Trans_No])
  ```

* **Age & Income Group Segmentation (Calculated Columns for Clustering):**
  ```dax
  Age_Group = 
  SWITCH(
      TRUE(),
      'Customer_Data'[Customer_Age] < 30, "20-30",
      'Customer_Data'[Customer_Age] >= 30 && 'Customer_Data'[Customer_Age] < 40, "30-40",
      'Customer_Data'[Customer_Age] >= 40 && 'Customer_Data'[Customer_Age] < 50, "40-50",
      'Customer_Data'[Customer_Age] >= 50 && 'Customer_Data'[Customer_Age] < 60, "50-60",
      "60+"
  )
  ```

---

## 🎛️ Interactive Insights & Slicers
To provide an intuitive, self-service BI environment, both dashboard views utilize fully synchronized filters:
* **Card Tier Toggles:** Dynamically drill down into Blue, Gold, Platinum, and Silver performance profiles.
* **Temporal Slicers:** Interactive quarterly buttons (Q1–Q4) paired with granular week-start dropdown filters.
* **Demographic Toggles:** High-visibility binary selectors for Male (M) and Female (F) populations to dynamically filter demographic charts on the fly.

---

## 🚀 Technical Skills Demonstrated
* **Data Visualization & UX/UI Design:** Developed high-density, easily scannable operational dashboards built with a clean, cohesive layout.
* **Analytical Modeling:** Managed complex metrics including financial streams, age distribution, and account delinquency risk modeling.
* **Business Acumen:** Structured metrics to align with retail banking KPIs (Revenue, Interest Earned, Delinquent Accounts).

---


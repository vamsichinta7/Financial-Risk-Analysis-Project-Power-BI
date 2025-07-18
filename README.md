# Financial-Risk-Analysis-Project-Power-BI

## 📊 Overview
This project presents a comprehensive **Power BI dashboard** that analyzes credit card transaction data and customer demographics to uncover financial risks, customer behavior, and business performance. It enables real-time tracking of KPIs to support strategic decision-making and proactive risk mitigation.

---

## 🚀 Features
- 🎯 **Interactive Dashboard** – Built with Power BI for rich visual storytelling and cross-filtering across transaction trends, customer segments, and risk categories.  
- ⚙️ **Data Processing & Modeling** – Cleaned, transformed, and modeled relational SQL data using Power Query and DAX.  
- 📈 **Real-Time Business Insights** – Delivered actionable insights to business stakeholders on delinquency, utilization, and customer segmentation.

---

## 🗃️ Data Source
- PostgreSQL database with:
  - `cust_detail` – Customer demographics & income  
  - `cc_detail` – Credit card transactions, interest, revenue

---

## 📌 Key Metrics Tracked
- ✅ Total Revenue (Annual Fees + Transactions + Interest)
- 👥 Customer Demographics (Age, Income, Gender)
- 💳 Credit Utilization Ratio
- 📍 State-wise and Card Type-wise Contributions
- 📅 Week-over-Week Growth & Year-to-Date Summaries
- 🚨 Delinquency & Activation Rates

---

## 🧠 DAX Measures (Sample)
```DAX
AgeGroup = SWITCH(TRUE(),
  [customer_age] < 30, "20-30",
  [customer_age] < 40, "30-40",
  [customer_age] < 50, "40-50",
  [customer_age] < 60, "50-60",
  "60+")

IncomeGroup = SWITCH(TRUE(),
  [income] < 35000, "Low",
  [income] < 70000, "Med",
  "High")

Revenue = [annual_fees] + [total_trans_amt] + [interest_earned]

Current_Week_Revenue = CALCULATE(SUM([Revenue]),
  FILTER(ALL('cc_detail'), [week_num2] = MAX([week_num2])))

Previous_Week_Revenue = CALCULATE(SUM([Revenue]),
  FILTER(ALL('cc_detail'), [week_num2] = MAX([week_num2]) - 1))
```

---

## 🔍 Insights Extracted

### 📅 Weekly Trend Analysis:
- 📈 Revenue increased by **28.8%**
- ⬆️ Transaction Amount and Count increased significantly
- 🧍‍♂️ Customer count also showed healthy growth

### 📆 Year-to-Date Overview:
- 💰 **Total Revenue:** $57M  
- 💳 **Total Transaction Amount:** $46M  
- 🏦 **Total Interest Earned:** $8M  
- 🧑‍🤝‍🧑 **Gender Contribution:** Male $31M | Female $26M  
- 🏷️ **Card Usage:** Blue & Silver cards drive 93% of transactions  
- 📍 **Top Regions:** TX, NY & CA contribute 68% of transactions  
- 📊 **Activation Rate:** 57.5%  
- 🚩 **Delinquency Rate:** 6.06%

---

## 📌 Risk Analysis Summary

| Risk Type                    | Observations                                                                 |
|-----------------------------|------------------------------------------------------------------------------|
| Default Risk                | Delinquency rate at **6.06%** – moderate risk of default                     |
| Credit Utilization Risk     | Avg. utilization **74.21%** – indicates over-reliance on credit              |
| Interest Rate Risk          | Avg. interest rate **18.5%** – potential debt accumulation concern           |
| Geographic Concentration    | 68% revenue from TX, NY, CA – regional dependency risk                       |
| Age & Income Distribution   | 44% aged 20–30 & 34% earning < $35K – higher chance of default               |

---

## ✔️ Recommendations
- Implement stricter credit monitoring for high-risk age and income groups  
- Diversify customer base across states and card types  
- Provide financial literacy & credit management guidance  
- Optimize interest rate strategy based on credit behavior  
- Introduce balance transfer and utilization alert features

---

## 📸 Power BI Dashboard Preview

### 👤 Customer Overview  
![Customer Dashboard](https://github.com/user-attachments/assets/c690453a-1a5d-44e5-946b-ef8bfbdc0450)

### 💳 Transaction Insights  
![Transaction Dashboard](https://github.com/user-attachments/assets/c23e1c3d-ac6a-4fdb-b165-0ec77575da2e)

---

## 🛠️ Tools & Technologies
- Power BI  
- DAX  
- Power Query  
- PostgreSQL / SQL  
- Data Modeling & Business Intelligence

---

## 📎 Conclusion
This dashboard empowers financial institutions to monitor and reduce risks associated with credit card usage. By leveraging insightful visual analytics, stakeholders can identify risky customer segments, track revenue drivers, and implement data-driven risk management strategies.

## 🏬 Superstore Sales & Profit Analytics Dashboard (Excel + Power BI)



![Power BI](https://img.shields.io/badge/PowerBI-Dashboard-yellow)
![Excel](https://img.shields.io/badge/Excel-DataCleaning-green)
![DAX](https://img.shields.io/badge/DAX-Formulas-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-green)

An **interactive analytics dashboard** built using **Power BI**, with **Excel-based data cleaning** and **DAX formulas** for advanced metrics.  
The project uncovers insights into **sales, profit, returns, and customer performance** across product categories, regions, and time.  
📊 Business KPIs • 💸 Profit Drivers • 📦 Returns Optimization • 🌍 Regional Insights  

---

## 📈 Dashboard Preview  

<img width="1411" height="795" alt="Screenshot 2025-09-04 235057" src="https://github.com/user-attachments/assets/ff3810c3-0cf2-45f5-be4c-d2b1e3ca661c" />



## 📖 Introduction  
The **Superstore dataset** contains detailed information about orders, sales, profit, and returns.  
This project uses **Excel for data cleaning** and **Power BI for interactive dashboards with DAX formulas** to analyze business performance.  

The goal: provide **actionable insights** on **sales growth, profitability, returns, and customer trends**.  

---

## 🧹 Data Cleaning (Excel)  
Before importing into Power BI, the dataset (`Sample - Superstore.xls`) was cleaned in Excel by:  
- ✅ Removing duplicates and invalid entries  
- ✅ Handling missing values (e.g., null profits/returns)  
- ✅ Standardizing column names (`Sales`, `Profit`, `Order Date`, etc.)  
- ✅ Creating derived fields like **Profit Ratio** for preliminary analysis  

---

## 🧮 DAX Modeling (Power BI)  

Power BI was used to create **key measures and calculations** for analysis:  

- **Base KPIs**  
```DAX
Sales = SUM('Orders'[Sales])
Profit = SUM('Orders'[Profit])

% Retruned Orders = 
VAR total_ordrs =DISTINCTCOUNT(Orders[Order ID])
VAR Returned_orders =DISTINCTCOUNT(Returns2[Order ID])
VAR _Prec = DIVIDE(Returned_orders,total_ordrs)
RETURN
_Prec
```

- **Previous Year (PY) Metrics**  
```DAX
Sales PY = CALCULATE(SUM('Orders'[Sales]), SAMEPERIODLASTYEAR('Date'[Date]))
Profit PY = CALCULATE(SUM('Orders'[Profit]), SAMEPERIODLASTYEAR('Date'[Date]))
%Retruned Orders PY = CALCULATE([% Retruned Orders],SAMEPERIODLASTYEAR('Date Table'[Date]))

- **Year-over-Year (vs PY) Calculations**  
```DAX
vs PY - Sales = [Sales] - [Sales PY]
vs PY - Profit = [Profit] - [Profit PY]
vs PY - % Returned Orders = 
[% Retruned Orders] -[%Retruned Orders PY]

- **Date Table for Time Intelligence**  
```DAX
Date Table = ADDCOLUMNS(CALENDAR(MIN(Orders[Order Date]),MAX(Orders[Order Date])),"Start of Month ",EOMONTH([Date],-1)+1)
```

---

## ❓ Research Questions & Findings  

1. 📈 **How are sales & profits trending?**  
   - Total Sales = **$2.33M**  
   - Total Profit = **$292K**  
   - Growth vs PY → **+47% Sales**, **+49% Profit**  

2. 🎯 **Which categories drive profitability?**  
   - **Top Performers**: Copiers, Phones, Accessories  
   - **Loss-Makers**: Tables, Bookcases, Supplies  

3. 🌍 **Which states/regions perform best/worst?**  
   - Profit concentration in **Technology products**  
   - Losses in **Binders & Envelopes**  

4. 📅 **What seasonal patterns exist?**  
   - Clear **Q4 demand spikes** in both Sales & Profit  

5. 💸 **How do returns impact performance?**  
   - Return Rate = **5.79%** (improved from **8.74% PY**)  

---

## 🛠️ Recommendations  

- 🔧 **Fix Loss-Making Categories**: Investigate **Tables, Bookcases, Supplies** pricing & supply chain.  
- 🚀 **Double-Down on Growth Drivers**: Focus investment on **Technology sub-categories** (Phones, Copiers).  
- 📅 **Seasonal Strategy**: Align campaigns & inventory with **Q4 spikes**.  
- ⚡ **Returns Reduction**: Target categories with high return % for **quality & logistics improvement**.  

---

## 📈 Business Impact  

- ✅ **+47% Sales Growth** YoY  
- ✅ **+49% Profit Growth** YoY  
- ✅ **-2.9% Returns improvement**  
- 📊 Clear visibility into **top vs loss-making products**  
- 🌍 Geographic-level insights for **regional strategy**  

---

## 📦 Deliverables  

- 📊 Dashboard → `Super_store_analytics_dashboard_2.pbix`  
- 📂 Dataset → `Sample - Superstore.xls`  
- 🖼️ Screenshot → Dashboard preview  
- 📑 REPORT.md → This report file  

---

## ✅ Conclusion  

By combining **Excel-based data cleaning** with **Power BI DAX modeling**, this project delivers a **robust analytics framework** for retail insights.  

The findings enable stakeholders to:  
- Identify **profit-driving vs loss-making products**  
- Capture **seasonal sales opportunities**  
- Reduce the impact of **returns**  
- Make **data-driven strategic decisions** for sustainable growth.  

📌 This approach can be scaled to **real-world retail & e-commerce analytics** for pricing, supply chain, and customer segmentation. 

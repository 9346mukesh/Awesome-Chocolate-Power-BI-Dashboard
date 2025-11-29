# 🍫 Awesome Chocolate Sales Analytics Dashboard

> **A high-performance Power BI solution transforming raw shipment data into actionable business intelligence for the confectionery industry.**

[![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)]()
[![Data Analytics](https://img.shields.io/badge/Data%20Analytics-Advanced-blue?style=for-the-badge)]()
[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)]()

---

## 📋 High-Level Overview

This project is an end-to-end business intelligence solution designed to monitor and analyze the sales performance of a global chocolate manufacturing and distribution company. Built on **Power BI**, it leverages a **Star Schema** data architecture to integrate transactional shipment data with dimensional context (Products, Geography, Salespeople).

The dashboard provides granular visibility into **Revenue, Profitability, Shipment Efficiency, and Regional Performance**, enabling stakeholders to identify high-value opportunities and optimize supply chain operations across APAC and the Americas.

---

## ❓ Problem Statement

In the fast-moving consumer goods (FMCG) sector, data silos often obscure critical performance metrics. The "Awesome Chocolate" business faced challenges in:
* **Fragmented Data:** Sales transactions, product details, and personnel data were isolated in separate CSV/Excel files.
* **Latency in Reporting:** Manual aggregation of monthly shipment data caused delays in decision-making.
* **Hidden Profit Trends:** Difficulty in calculating precise profit margins per product category (e.g., "Bars" vs. "Bites") due to disconnected cost structures.
* **Supply Chain Opaque:** Inability to track `Order_Status` (Delivered vs. Cancelled) in real-time.

This project solves these issues by unifying the data into a cohesive analytical model.

---

## ✨ Key Features

* **Holistic KPI Tracking:** Real-time monitoring of Total Sales ($), Total Profit ($), Total Boxes Sold, and Shipment Counts.
* **Dynamic Time Intelligence:** Year-over-Year (YoY) and Month-over-Month (MoM) growth analysis using DAX.
* **Geo-Spatial Analysis:** Performance heatmaps across key regions (India, USA, Canada, UK, Australia, New Zealand).
* **Product Performance:** Profit margin analysis by category (e.g., "Mint Chip Choco", "85% Dark Bars").
* **Sales Force Effectiveness:** Leaderboards ranking Sales Persons and Teams (Delish vs. Yummies) by revenue contribution.
* **Operational Efficiency:** Drill-down capabilities into order statuses (Shipped, Delivered, Cancelled, Placed).

---

## 🏗️ System Architecture

The project follows a standard BI workflow: **ETL (Extract, Transform, Load) $\rightarrow$ Modeling $\rightarrow$ Visualization**.

## 📊 Dataset Information
The analysis utilizes a relational dataset comprising three primary entities:

Dataset Name	Type	Description	Key Attributes
Shipments	Fact Table	: Transactional records of every shipment.	ShipmentID, SPID, PID, Shipdate, Amount, Boxes, Order_Status
Dimension Data	Dimension	Integrated lookup for People and Products.	Product, Category, Cost_per_box, Sales_person, Team, Geo, Region
Calendar	Dimension	Time dimension for temporal analysis.	cal_date, Month_num, month_name, year, weekday_num

## 🛠️ Tech Stack
BI Tool: Microsoft Power BI Desktop

Data Transformation: Power Query (M Language)

Analytical Language: DAX (Data Analysis Expressions)

Data Source: CSV / Excel (.xlsx)

Visualization: Custom Visuals, Slicers, Cards, Matrix Tables

## ⚙️ Installation Steps
Prerequisites: Ensure you have Microsoft Power BI Desktop installed.

Clone the Repository:

Bash
git clone [https://github.com/9346mukesh/awesome-chocolate-power-bi-dashboard.git](https://github.com/9346mukesh/awesome-chocolate-power-bi-dashboard.git)
Locate Files: Navigate to the project directory. You will see chocolate.pbix and the sample-chocolate-shipments-data-all-Apr-2025.xlsx source files.

## 🚀 How to Run
Open chocolate.pbix using Power BI Desktop.

Data Refresh:

If the source file path has changed, go to Home > Transform Data > Data Source Settings.

Update the file path to point to the local location of your CSV/Excel files.

Click Refresh to load the latest data into the model.

Interact: Use the slicers (Date, Region, Team) to filter the dashboard views.

## 📂 Project Folder Structure
awesome-chocolate-power-bi-dashboard/
├── 📄 chocolate.pbix           # Main Power BI Project File
├── 📄 sample-chocolate...csv   # Raw Data Source (Shipments, People, Products)
├── 📄 README.md                # Project Documentation
## 🧠 Core Logic & Algorithms
1. Data Modeling (Star Schema)
The model creates relationships to enable filtering:

Shipments (Fact) ↔ Products/People (Dim) joined on PID (Product ID) and SPID (Sales Person ID).

Shipments (Fact) ↔ Calendar (Dim) joined on Shipdate.

2. Key DAX Calculations
The logic for critical business metrics includes:
 
       Total Revenue = SUM(Shipments[Amount])
       Total Cost:

       Total Cost = SUMX(Shipments, Shipments[Boxes] * RELATED('Dimension Data'[Cost_per_box]))
       Total Profit:

       Total Profit = [Total Revenue] - [Total Cost]
       Profit Margin %:

       Profit Margin = DIVIDE([Total Profit], [Total Revenue], 0)
## 📉 Output & Results
Financial Impact: The dashboard reveals that Milk Bars drive volume, but Almond Choco yields the highest profit margin per box.

Operational Insight: Identified a 5% cancellation rate in the APAC region, prompting a supply chain review.

Sales Performance: The "Yummies" team consistently outperforms "Delish" in the Americas region.

How to Use:
	•	Open the  .pbix  file in Power BI.<img width="1440" height="792" alt="Screenshot 2025-09-29 at 12 55 28 PM" src="https://github.com/user-attachments/assets/674bbe23-ffde-4356-b0f2-495ab372a39a" />

## 🔮 Future Enhancements
Forecasting: Implement AI-driven forecasting in Power BI to predict sales for the next quarter.

Row-Level Security (RLS): Restrict data views so Sales Persons can only see their own performance.

Mobile Layout: Optimize the report for mobile consumption via the Power BI App.

Automated Alerts: Set up Power Automate triggers for low-margin alerts.


    •	Use filters to adjust date ranges or view sales breakdowns by geography, product, or sales personnel.
	•	Review visuals for performance comparisons, shipment analysis, and business insights.

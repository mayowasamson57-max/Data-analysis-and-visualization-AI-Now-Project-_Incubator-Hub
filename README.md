
# 📊 D LITE Electronics Sales Analysis
*Excel & Power BI Project Report*


**Author:** Mayowa Samson Popoola

**Date:** January 2026  
**Tools:** Microsoft Excel, Power BI  
**Dataset:** `Sales_Details.xlsx`

---

## 📌 Project Overview

D LITE Electronics operates across major regions in Nigeria. However, the company’s sales data is inconsistent and contains errors.  
This project focuses on:

- Cleaning messy and inconsistent data  
- Analyzing sales performance by Zones, product category,channel, and promotion  
- Visualizing insights using **Excel**   
- Producing management-ready insights for decision-making  

The goal is to transform raw data into **actionable business intelligence**.

---

## 🗂 Dataset Description

The dataset contains the following key fields:

| Column | Description |
|--------|-------------|
| Order ID | Unique order identifier |
| Order Date | Date of transaction |
| Unit Cost | Cost per unit |
| Price | Selling price per unit |
| Order Qty | Quantity sold |
| Sales | Total sales amount |
| Channel | Sales channel |
| Promotion Name | Promotion applied |
| Product Name | Product sold |
| Product Sub Category | Detailed category |
| Product Category | Main category |
| State | Nigerian state |
| Zone | Nigerian region |

---

## 🧹 Data Cleaning (Excel)

### Issues Identified
- Sales column contained text and errors  
- Inconsistent naming (e.g., `north`, `NORTH`, `North`)  
- Extra spaces and mixed formatting  
- Duplicate rows  

### Cleaning Steps in Excel

1. Converted dataset into a **Table**  
2. Standardized text using:
   ```excel
   =PROPER()
   =TRIM()
````

3. Fixed invalid Sales values:

   ```excel
   =IF(ISNUMBER([@Sales]),[@Sales],[@Price]*[@[Order Qty]])
   ```
4. Removed duplicates:
   `Data → Remove Duplicates`
5. Ensured correct data types:

   * Dates → Date format
   * Sales → Currency
   * Quantities → Number

> 📸 **Screenshot Placeholder – Raw vs Cleaned Data**
> `![Raw vs Cleaned Data](screenshots/excel_cleaning.png)`

---

## 📈 Analysis in Excel (Pivot Tables)

### Key Pivot Tables Created

1. **Total Sales by Zone**

   * Rows: Zone
   * Values: Sum of Sales

2. **Sales by Product Category**

   * Rows: Product Category
   * Values: Sum of Sales

3. **Top Products by Revenue**

   * Rows: Product Name
   * Values: Sum of Sales

4. **Monthly Sales Trend**

   * Added column:

     ```excel
     =TEXT([@Order Date],"MMMM")
     ```
   * Rows: Month
   * Values: Sum of Sales

5. **Promotion Effectiveness**

   * Rows: Promotion Name
   * Values: Sum of Sales

> 📸 **Screenshot Placeholder – Pivot Tables**
> `![Excel Pivot Tables](screenshots/excel_pivots.png)`

---

## 📊 Visualization in Excel

Charts created from PivotTables:

| Analysis               | Chart Type   |
| ---------------------- | ------------ |
| Sales by Zone          | Column Chart |
| Product Category Share | Pie Chart    |
| Monthly Trend          | Line Chart   |
| Top Products           | Column Chart |
| Promotion Performance  | Bar Chart    |

All charts were arranged on a **Dashboard Sheet**.

> 📸 **Screenshot Placeholder – Excel Dashboard**
> `![Excel Dashboard](screenshots/excel_dashboard.png)`

---

## 📊 Power BI Implementation

### Steps in Power BI

1. Imported the cleaned Excel file
2. Opened **Power Query Editor**:

   * Trimmed text columns
   * Standardized Zone and Product fields
   * Ensured Sales column is numeric
3. Created Measures using DAX:

   ```DAX
   Total Sales = SUM(Sales_Details[Sales])
   Total Orders = COUNT(Sales_Details[Order ID])
   Avg Order Value = DIVIDE([Total Sales],[Total Orders])
   ```
4. Built interactive visuals:

   * Bar chart: Sales by Zone
   * Pie chart: Sales by Product Category
   * Line chart: Monthly Sales Trend
   * Table: Top Products
   * Slicer: Zone, Product Category, Month

> 📸 **Screenshot Placeholder – Power BI Model**
> `![Power BI Data Model](screenshots/powerbi_model.png)`

> 📸 **Screenshot Placeholder – Power BI Dashboard**
> `![Power BI Dashboard](screenshots/powerbi_dashboard.png)`

---

## 🔍 Key Insights

* **Top Performing Zone:** South East
* **Lowest Performing Zone:** North Central
* **Best Product Category:** Cameras and Camcorders
* **Top Product:** Digital SLR Cameras
* **Peak Sales Months:** March & December
* **Most Effective Promotions:** Revenue, 85

---

## 💡 Recommendations

1. Increase marketing investment in **high-performing zones**.
2. Stock more **top-performing products** (Digital SLR Cameras).
3. Replicate successful promotions in low-performing regions.
4. Plan inventory around **peak months**.
5. Maintain a **data quality process** for future sales records.

---

## 🏁 Conclusion

This project demonstrates how raw, inconsistent data can be transformed into meaningful insights using **Excel and Power BI**.
Through systematic cleaning, structured analysis, and clear visualization, management can now:

* Understand regional performance
* Identify profitable products
* Plan promotions strategically
* Make data-driven decisions

This workflow reflects real-world **Data Analyst** practices.

---

## 📁 Repository Structure

```
D-LITE-Sales-Analysis/
│
├── data/
│   └── Sales_Details_Cleaned.xlsx
│
├── excel/
│   └── D_LITE_Excel_Analysis.xlsx
│
├── powerbi/
│   └── D_LITE_Sales.pbix
│
├── screenshots/
│   ├── excel_cleaning.png
│   ├── excel_pivots.png
│   ├── excel_dashboard.png
│   ├── powerbi_model.png
│   └── powerbi_dashboard.png
│
└── README.md
```

---







#

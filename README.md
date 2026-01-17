
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
- Visualizing insights using **Excel**  and **Power BI**
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
   excel
   =PROPER()
   =TRIM()
   

3. Fixed invalid Sales values:

   excel
   =IF(ISNUMBER([@Sales]),[@Sales],[@Price]*[@[Order Qty]])

   
4. Removed duplicates:
   `Data → Remove Duplicates`
5. Ensured correct data types:

   * Dates → Date format
   * Sales → Currency
   * Quantities → Number


> `![Screenshot AI Now Excel  Project _ETL 1](https://github.com/user-attachments/assets/37c781d5-2c38-4a49-ba09-9d8166c47aee)


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
   * Values: Sum of Sale
     
> ![Screenshot AI Now Excel Project _Pivot 1](https://github.com/user-attachments/assets/08edf653-60cc-4bc2-ab76-2cc6c05b8eef)
`





---



## Steps in Power BI

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
![Screenshot AI NOW CARDS 1](https://github.com/user-attachments/assets/a7c1c4f7-9a41-478c-b135-2c685bb82238)

![Screenshot AI Now Power BI Measure Table](https://github.com/user-attachments/assets/87d09226-170f-466c-8aac-1869d44828f5)

   ![Screenshot AI Now power bi project data modelling](https://github.com/user-attachments/assets/10fd6279-cb94-4165-bb75-04df51a48f45)

   
4. Built interactive visuals:

   

> ![Screenshot AI NOW CARDS 1](https://github.com/user-attachments/assets/1033edd0-2e88-4fd9-9f88-28400f4b1711)
> 
![Screenshot AI Now Power BI Measure Table](https://github.com/user-attachments/assets/03d0a2a7-089b-4edc-84a6-732350996e4a)



> `![Power BI Dash![Screenshot AI Now analytical visuals 1](https://github.com/user-attachments/assets/89ff44ce-c80e-4a5c-aac3-2c12f6f142ce)
board]

![Screenshot AI Now analytical 2](https://github.com/user-attachments/assets/43d11b19-70a5-466d-84cd-d4f534082572)

---

## 🔍 Key Insights

Computers lead in sales, followed by Cameras and camcorders and TV and Video
The distribution of sales across different product categories shows that Computers have the highest sales, followed by Cameras and camcorders, and TV and Video. Here are the key metrics:
Total Sales: $56,254,053.53
Number of Product Categories: 6
Highest Sales Category: Computers with $21,629,438.98
Lowest Sales Category: Audio

### The top three categories by sales are:
Computers: $21,629,438.98
Cameras and camcorders: $17,330,823.95
TV and Video: $9,257,732.55.

### Key Insights from Sales by Product Category

The chart reveals the distribution of total sales across various product categories, highlighting which areas are driving revenue and which may need attention.
Top Performers
Computers lead with 21,629,438.98 units sold, indicating strong demand and possibly high customer satisfaction in this segment.
Cameras and camcorders follow closely with 17,330,823.95 units, suggesting a robust market for photography equipment.

### Moderate Performers
TV and Video show solid sales with 9,257,732.55 units, reflecting consistent consumer interest in home entertainment systems.
Cell phones have 5,918,974.28 units sold, which, while lower than the top two categories, still represents a significant revenue stream.

### Underperformers
Music, Movies and Audio Books with 1,072,826.4 units and Audio with 1,044,257.37 units are the lowest performers. This may indicate either market saturation, lack of innovative products, or stiff competition.

## Business Implications
Focus marketing and promotional efforts on Computers and Cameras and camcorders to capitalize on their high sales.
Analyze the underperformance in Music, Movies and Audio Books and Audio to identify potential market gaps or opportunities for product innovation.
Consider bundling or cross-selling strategies between high and low performers to boost overall sales.

### Insights on Sales Distribution by Product Category and Promotion

#### Key Trends
The 'No Discount' promotion leads in total sales across all product categories, indicating a strong customer preference for non-discounted items.
The 'Computers' category significantly outperforms other categories in sales, suggesting a high demand and potential market saturation.
The 'Adventist Promotion' and 'Winners Promotion' show notable sales in 'Cameras and camcorders' and 'TV and Video', hinting at effective targeting or seasonal demand.




### Key trends by channel, product, category, and zone across quarters
Summary Insight: - The 'Store' channel leads in sales with 32,189,608.4 currency units, followed by the top-selling product, the 'Kekule Projector 1080p X980 Black', with sales of 452,115.0 currency units. The South East zone shows the highest sales at 15,655,458.1 currency units.
Supporting Metrics: - Total sales across all channels, products, categories, and zones amount to 56,254,053.53 currency units. - There are 10 unique channels, 1643 unique products, 6 unique categories, and 7 unique zones.
Visuals:


---

## 💡 Recommendations

1. Increase marketing investment in **high-performing zones**.
2. Stock more **top-performing products** (Computers).
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









#

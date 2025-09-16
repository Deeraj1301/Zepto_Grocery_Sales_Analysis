# 🛵 Zepto Groceries Sales Performances

[![View Dashboard](https://img.shields.io/badge/View%20Dashboard-black.svg?style=for-the-badge&logo=Codeforces&logoColor=gold&labelColor=%black&color=%23000000)](https://app.powerbi.com/view?r=eyJrIjoiNjkzY2VkNmQtOTk4ZS00MzdlLWE3ZGMtZTM2NzMwNDYyMGJkIiwidCI6IjU3ZmJiOTI1LWVmMWEtNDAzOC1hMGJmLTVlOTM1YTMzYzk2MiJ9)

  <a href="https://datascienceportfol.io/deerajS" target="_blank">
  <img width="300" height="250" alt="Image" src="https://github.com/user-attachments/assets/e5c51953-e920-4b31-8c91-cf8227ad7185" />
  </a>

## Table of Contents
  1. [Problem Statement](#problem-statement)
  2. [Project Planning using Star Method](#project-planning-using-star-method)
  3. [Data Source](#data-source)
  4. [Data Preprocessing \& ETL](#data-preprocessing--etl)
  5. [Data Modelling](#data-modelling)
  6. [Data Analysis](#data-analysis)
  7. [Dashboard](#dashboard)
  8. [Findings](#findings)
  9. [Tools and Software](#tools-software-and-libraries)

## Problem Statement
<details>
<summary>
View Statement ⬇️
</summary> <br/>

**Zepto, a quick-commerce grocery delivery company, struggles to analyze sales across diverse outlets, item categories, and city tiers.The leadership lacks clarity on outlet performance, product sales trends, and customer satisfaction.Key challenges include tracking revenue by outlet type, establishment growth, and consumer preferences like fat content.**

</details>


## Project Planning using Star Method
<details>

<summary>
View Stratergy ⬇️
</summary>

- Understand key KPIs: Overall Sales, Units, Seller Count
- Build hierarchical view: State → City → Product → Product Details
- Enable drilldowns: from overview → product listings → product-level insights
- Design dashboards with clear filters and interactions

### S - Situation
Amazon’s apparel sales data was scattered, making it hard for stakeholders to track performance across sellers, cities, and products. A unified, interactive view was needed for better decision-making.

### T - Task
- The main objective was to design a centralized BI solution that:

  - Consolidates sales and customer data into a single, interactive platform

  - Highlights key KPIs:

    - Total Sales
    - Average Sales
    - Number of Items
    - Average Rating
  
- Provides performance breakdown by:

  - Outlet Type (Supermarket, Grocery Store, etc.)
  - Outlet Size (Small, Medium, Large)
  - Location Tier (Tier 1, Tier 2, Tier 3)
  - Item Category (Fruits, Snacks, Dairy, etc.)
  - Fat Content (Regular vs. Low Fat)

- Enables leadership to track trends, compare outlets, and identify growth opportunities

### A - Action

  - Collected, cleaned, and transformed raw sales data for consistency.
  - Designed a star schema model with fact and dimension tables in Power BI.
  - Built DAX measures for KPIs and advanced calculations.
  - Developed an interactive dashboard with slicers for outlet location, size, and item type.
  - Visualized insights on sales trends, outlet establishment growth, and customer ratings.

### R - Result

- The Power BI dashboard enabled Zepto to gain clear, data-driven visibility into its grocery sales performance. Key outcomes include:
- Identified $1.20M in total sales with an average sale of $141 across 8,523 items.
- Found that Regular fat content items contributed more revenue compared to Low Fat items.
- Highlighted Fruits, Snacks, and Dairy as the top-selling product categories, guiding inventory prioritization.
- Discovered that Medium-sized outlets and Tier 3 locations generated the highest sales share, outperforming Tier 1 and Tier 2.
- Mapped outlet establishment trends (2011–2018) to show consistent business expansion and growth.
- Outlet Type comparison revealed Supermarket Type 2 as the most profitable, with higher sales and customer ratings.
- Integrated customer feedback (Avg Rating 3.9) into the performance view, enabling insights into customer satisfaction levels.
- Delivered a 360° interactive dashboard that allows leadership to filter by outlet, location, size, and category for strategic decision-making.

</details>


## Data Source
<details>
<summary>
View Source ⬇️
</summary><br>

- Imported raw data from [Kaggle.in](https://www.kaggle.com/)
- Format: CSV / Excel
- Records Include:
  - Outlet details
  - Sales values
  - Item categories
  - Fat content (Regular vs. Low Fat)
  - Outlet size (Small, Medium, Large)
  - Outlet establishment year
  - Outlet location type (Tier 1, Tier 2, Tier 3)
  - Item rating

</details>


## Data Preprocessing & ETL
<details>
<summary>
View ETL Process ⬇️
</summary><br>

**Our data is initially import from the Excel/CSV file into Power BI, and then the subsequent Extract, Transform, and Load (ETL) is executed in Power Query**
<br>

1. Cleaned nulls, formatted dates, ensured proper data types. 

2. Data Import

   - Loaded data from Excel workbook: Zepto Grocery Data.xlsx

3. Header & Data Type Fixes

   - Promoted the first row as headers

   - Converted columns to appropriate data types (Text, Int64, Number, etc.)

4. Data Standardization

    - Cleaned Item Fat Content column for consistency:

      - Replaced LF → Low Fat
      - Replaced low fat → Low Fat
      - Replaced reg → Regular

5. Data Quality Handling

    - Filled missing values in Item Weight column using Fill Down method

     - Ensured no duplicate or empty records remained

6. Null and Zero Handling 
  
    - Applied up/down fill in Power BI to handle missing or zero values in the Price of Product columns.

7. Final Output

    - Produced a clean, structured dataset with standardized categories, corrected types, and complete records ready for modeling in Power BI


</details>


## Data Modelling
<details>
<summary>
View Modeling ⬇️
</summary>

<img width="727" height="495" alt="Image" src="https://github.com/user-attachments/assets/093914be-3fe2-474b-8bd9-ba4b87e03b2d" /> 

</details>


## Data Analysis
<details>
<summary>
View Analysis ⬇️
</summary><br>

DAX Measures Used In DashBoards:

1. Total Sales
```
Total Sales = SUM('Zepto Grocery Data'[Sales])
```

2. Average Sale
```
Avg Sale = AVERAGE('Zepto Grocery Data'[Sales])
```

3. Number of Items
```
 No of Items = COUNTROWS('Zepto Grocery Data')
```

4. Average Rating
```
 Avg Rating = AVERAGE('Zepto Grocery Data'[Rating])
```

5. Matrix Calculated for Slicer
```
 Matrix = { ("Total Sales", NAMEOF('Zepto Grocery Data'[Total Sales]), 0),      
            ("Avg Sale", NAMEOF('Zepto Grocery Data'[Avg Sale]), 1), 
            ("No of Items", NAMEOF('Zepto Grocery Data'[No of Items]), 2), 
            ("Avg Rating", NAMEOF('Zepto Grocery Data'[Avg Rating]), 3) 
          }

```

</details>

## Dashboard
<details>
<summary>
View Images ⬇️
</summary>

> ### 1. Zepto Analytics
  1. Total Sales

  2. Average Sales

  3. Number of Items

  4. Average Rating

  5. Outlet Type (Supermarket, Grocery Store, etc.)
  6. Outlet Size (Small, Medium, Large)
  7. Location Tier (Tier 1, Tier 2, Tier 3)
  8. Item Category (Fruits, Snacks, Dairy, etc.)
  9. Fat Content (Regular vs. Low Fat)

  <a href="https://app.powerbi.com/view?r=eyJrIjoiNjkzY2VkNmQtOTk4ZS00MzdlLWE3ZGMtZTM2NzMwNDYyMGJkIiwidCI6IjU3ZmJiOTI1LWVmMWEtNDAzOC1hMGJmLTVlOTM1YTMzYzk2MiJ9" target="_blank">

  <img width="1188" height="724" alt="Image" src="https://github.com/user-attachments/assets/6baf88a0-7629-415c-ab15-0e7ed13add83" />
</a>

>
</details>

## Findings
<details>
<summary> 
View Findings ⬇️
</summary>

- Total Sales: $1.20M generated from 8,523 items, with an Average Sale of $141 and an Average Rating of 3.9.

- Fat Content Analysis:

    - Regular items contributed the majority of sales (~$750K).

    - Low Fat items accounted for the remaining (~$450K).

- Item Type Performance:

    - Fruits, Snacks, and Dairy emerged as the top 3 categories, contributing the highest share of sales.

- Outlet Establishment Timeline (2011–2018):

    - Outlets established after 2013 showed stronger sales growth compared to earlier years.

- Outlet Size Contribution:

    - Medium outlets dominated, accounting for ~43% of total sales.

    - Small and Large outlets contributed less significantly.

- Location Tier Performance:

    - Tier 3 outlets outperformed Tier 1 & Tier 2, generating the largest sales share (~$500K+).

- Outlet Type Analysis (Matrix View):

    - Supermarket Type 2 was the most profitable outlet type, leading in sales, number of items sold, and customer ratings.

    - Grocery Stores were the lowest performers in terms of revenue and satisfaction.

</details>


## Tools, Software and Libraries
<details>
<summary> 
View tools ⬇️
</summary>

- Power BI → data modeling & dashboard creation
- DAX → calculated measures (sales, AVG Sales, AVG Rating, Number Of Items)
- Excel → dataset handling
- Icons/Images → used for product visuals

</details>

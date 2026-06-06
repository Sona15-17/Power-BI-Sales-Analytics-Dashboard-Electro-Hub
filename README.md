# Power-BI-Sales-Analytics-Dashboard-Electro-Hub


## Project Overview

The Electro Hub Sales Analytics Dashboard is an interactive Power BI project developed to analyze sales performance, profitability, product performance, discounts, and customer purchasing trends.
The project focuses on data modeling concepts, data transformation, relationship management, and dashboard development using Power BI. A Star Schema data model was implemented using Fact and Dimension tables to enable efficient reporting and analysis.
The dashboard provides insights into sales trends over time, top and bottom performing products, profit analysis, promotion effectiveness, city-wise sales distribution, and comparison of key business metrics across different time periods.
This project was built by applying Power BI concepts such as Data Profiling, Data Transformation, Primary and Foreign Keys, Cardinality, Star Schema Modeling, DAX Measures, Filters, Slicers, and Visual Interactions.


## Business Requirements

The dashboard was developed to address the following business requirements:

1. Identify the Top 5 and Bottom 5 Products based on:
   - Sales
   - Profit
   - Quantity Sold
  
2. Analyze Sales Trends over different time periods:
   - Daily
   - Monthly
   - Quarterly
   - Yearly

3. Analyze the relationship between Sales and Profit.

4. Compare Sales, Profit, and Quantity Sold between any two user-selected periods.

5. Analyze the Average Discount offered across different Promotion Categories.

6. Track the Total Number of Orders.

7. Enable interactive analysis using filters such as:
   - Product
   - Date
   - Customer
   - Promotion Category

8. Analyze Sales performance across different Cities.


## Dataset Information

The dataset used in this project consists of sales transaction data along with supporting dimension tables.

### Tables Used

#### Fact Table

Contains transactional sales data including:
- Customer ID
- Order ID
- Product ID
- Promotion ID
- Date
- Discount
- Discount Percentage
- Net Sales
- Price Per Unit
- Profit
- Total Sales
- Units Sold

#### Dimension Tables

**Dim Customers**
- Customer-related information

**Dim Product**
- Product-related information

**Dim Promotion**
- Promotion and discount-related information

**Date Table 1**
- Used for primary date analysis

**Date Table 2**
- Used for comparative period analysis

**Measures Table**
- Stores DAX measures used in the dashboard

  ### Data Source

The data was loaded into Power BI from Excel files and used for sales analysis, data modeling, and dashboard development.


## Project Files

The repository contains the following files:

- Power BI Dashboard File (.pbix)
- Dataset Files (.xlsx)
- Project Documentation (README.md)
- Dashboard Screenshots

### Repository Structure

```text
Electro-Hub-Sales-Analytics-Dashboard
│
├── Electro_Hub_Sales_Analytics_Dashboard.pbix
├── Dataset.xlsx
├── README.md
│
└── images
    ├── overview-dashboard.png
    ├── top-bottom-analysis.png
    ├── comparison-dashboard.png
    ├── edit-interactions-dashboard.png
    └── detailed-data-view.png
```

## Data Profiling & Data Transformation

Data profiling and transformation were performed using Power Query Editor in Power BI to prepare the dataset for analysis.  

### Data Profiling

The following profiling techniques were used to understand the quality and structure of the data:

- Column Distribution
- Distinct Values Analysis
- Unique Values Analysis
These techniques helped identify data inconsistencies and understand the characteristics of each column.

### Data Transformation

The following transformations were performed:

- Identified and handled null values in the Fact Table.
- Merged the Fact Table with the Product Dimension table using Product ID.
- Created calculated columns required for business analysis.
- Calculated Total Sales using:
   Total Sales = Units Sold × Price Per Unit

- Calculated Discount Amount based on discount percentage.
- Calculated Net Sales after applying discounts.
- Prepared and cleaned the dataset for reporting and dashboard development.
  
### Outcome

The transformed dataset was optimized for data modeling and analytical reporting in Power BI.

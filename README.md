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


## Data Modeling

A structured data model was created in Power BI to establish relationships between transactional and dimension tables, enabling efficient analysis and reporting.

Implemented a Star Schema data model using Fact and Dimension tables.

Concepts applied:
- Primary Key & Foreign Key
- Cardinality
- Relationship Management
- Star Schema.

#### Fact Table
The central table containing transactional sales data.

#### Dimension Tables
- Dim Customers
- Dim Product
- Dim Promotion
- Date Table 1
- Date Table 2
The Fact Table is connected to the Dimension Tables through relationships, creating a Star Schema structure that supports efficient filtering, aggregation, and analysis.


### Data Model Overview

The final data model consists of:
- 1 Fact Table
- Customer Dimension
- Product Dimension
- Promotion Dimension
- Two Date Tables
- Measures Table

This model enables interactive reporting, time-based comparisons, and advanced analytical calculations using DAX.


## DAX Measures

The following DAX measures were created to support comparative analysis of Sales, Profit, and Quantity Sold across different time periods.

```DAX
Quantity Sold =
CALCULATE(
    SUM('Fact table'[Units Sold]),
    ALL('Date Table 1'),
    USERELATIONSHIP(
        'Date Table 2'[Date],
        'Fact table'[Date (dd/mm/yyyy)]
    ))

### Sum Of Net Sales

DAX
Sum Of Net Sales =
CALCULATE(
    SUM('Fact table'[Net Sales]),
    ALL('Date Table 1'),
    USERELATIONSHIP(
        'Date Table 2'[Date],
        'Fact table'[Date (dd/mm/yyyy)]
    ))

### Total Profit

DAX
Total Profit =
CALCULATE(
    SUM('Fact table'[Profit]),
    ALL('Date Table 1'),
    USERELATIONSHIP(
        'Date Table 2'[Date],
        'Fact table'[Date (dd/mm/yyyy)]
    ))

### Date Tables

DAX
Date Table 1 = CALENDARAUTO()


DAX
Date Table 2 = CALENDARAUTO()

### Purpose of the Measures

- Calculated Total Quantity Sold.
- Calculated Total Net Sales.
- Calculated Total Profit.
- Enabled comparison between different date periods.
- Used `USERELATIONSHIP()` to activate an alternate date relationship for comparative analysis.
- Used `ALL()` to remove filters from the primary date table when comparing selected periods.



## Dashboard Pages & Features

### 1. Overview Dashboard

![Overview Dashboard](images/overview-dashboard.png)

The Overview Dashboard provides a high-level summary of overall business performance.

#### Key Visuals

- Sales by City (Map Visual)
- Number of Orders (KPI Card)
- Average Discount by Promotion Categories
- Profit vs Net Sales Analysis (Scatter Chart)
- Sales Trends Over Time (Line Chart)

#### Purpose

- Monitor overall sales performance.
- Analyze sales distribution across cities.
- Evaluate discount and promotion effectiveness.
- Understand the relationship between sales and profit.
- Track sales trends over time.

### 2. Top & Bottom 5 Products Analysis

![Top Bottom 5 Analysis](images/top-bottom-analysis.png)

This dashboard identifies the best and worst performing products based on different business metrics.

#### Key Visuals

##### Sales Analysis
- Top 5 Products by Sales
- Bottom 5 Products by Sales

##### Quantity Analysis
- Top 5 Products by Quantity Sold
- Bottom 5 Products by Quantity Sold

##### Profit Analysis
- Top 5 Products by Profit
- Bottom 5 Products by Profit

#### Purpose

- Identify high-performing products.
- Detect underperforming products.
- Analyze product profitability.
- Support data-driven business decisions.

### 3. Sales, Profit & Quantity Comparison Dashboard

![Sales Profit Quantity Comparison](images/comparison-dashboard.png)

This dashboard compares key business metrics across two user-selected time periods.

#### Key Visuals

- Sales Comparison
- Profit Comparison
- Quantity Sold Comparison
- Dual Date Slicers

#### Purpose

- Compare business performance between different periods.
- Measure growth or decline in sales.
- Analyze profit trends.
- Evaluate quantity sold across selected periods.

### 4. Edit Interactions Dashboard

![Edit Interactions Dashboard](images/edit-interactions-dashboard.png)

This dashboard demonstrates the implementation of Edit Interactions functionality in Power BI.

#### Features

- Customized visual interactions
- Controlled filtering behavior
- Improved dashboard usability

#### Purpose

- Prevent unwanted visual filtering.
- Enhance report interactivity.
- Improve user experience while analyzing data.

### 5. Detailed Data View

![Detailed Data View](images/detailed-data-view.png)

This dashboard provides a detailed transactional view of the dataset.

#### Information Displayed

- Customer Details
- Product Details
- Promotion Information
- Units Sold
- Sales Amount
- Discount Amount
- Net Sales
- Profit

#### Purpose

- Enable detailed record-level analysis.
- Validate dashboard calculations.
- Support business reporting requirements.


### Interactive Features Used

- Filters Pane
- Slicers
- Cross Filtering
- Edit Interactions
- KPI Cards
- Map Visuals
- Scatter Charts
- Bar Charts
- Line Charts
- Table Visuals
overview-dashboard.png
top-bottom-analysis.png
comparison-dashboard.png
edit-interactions-dashboard.png
detailed-data-view.png

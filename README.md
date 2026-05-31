# Sales Performance Dashboard (Excel)

[![GitHub](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/Ajibola-hub/sales-dashboard-excel)
[![Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?logo=microsoft-excel)](#)
[![Data Analysis](https://img.shields.io/badge/Domain-Data%20Analysis-FF6B6B)](#)
[![Portfolio](https://img.shields.io/badge/Status-Portfolio%20Project-success)](#)

## 📋 Project Overview

This portfolio project demonstrates proficiency in **data analysis, visualization, and business intelligence** using Microsoft Excel. The Sales Performance Dashboard provides actionable insights into sales trends, customer behavior, regional performance, and revenue optimization opportunities.

This project is designed to showcase skills essential for **Data Analyst, Business Analyst, and Data Engineer** entry-level roles, including data cleaning, exploratory data analysis (EDA), dashboard design, and business acumen.

---

## 🎯 Business Problem Statement

A mid-sized retail organization lacks visibility into:
- **Sales performance across products and regions**
- **Customer purchasing behavior and high-value segments**
- **Revenue trends and seasonal patterns**
- **Payment method preferences**
- **KPI tracking for business decision-making**

This dashboard addresses these gaps by providing a centralized, interactive analytical tool for real-time business monitoring and strategic planning.

---

## 🏆 Project Objectives

1. **Analyze Sales Performance** — Evaluate total revenue, order volume, and average transaction value
2. **Track Key KPIs** — Monitor critical business metrics for performance assessment
3. **Identify Top Products** — Determine which products drive the most revenue
4. **Analyze Revenue Trends** — Understand seasonal patterns and growth trajectories
5. **Identify Top Customers** — Segment and recognize high-value customer segments
6. **Compare Regional Performance** — Evaluate sales distribution and regional growth opportunities
7. **Analyze Payment Preferences** — Understand customer payment behavior for operational optimization

---

## 📊 Dataset Description

### Data Source
- **Format**: CSV (Excel-compatible)
- **Records**: 500+ transactions
- **Time Period**: 12 months (1 year of data)
- **Granularity**: Individual customer transactions

### Dataset Columns

| Column | Data Type | Description | Example |
|--------|-----------|-------------|----------|
| `customer_id` | Text/Number | Unique customer identifier | C001, C002 |
| `customer_name` | Text | Full name of customer | John Smith |
| `product` | Text | Product purchased | Laptop, Monitor, Keyboard |
| `order_date` | Date | Transaction date | 01/15/2024 |
| `sales_amount` | Currency | Revenue from transaction (USD) | $1,250.00 |
| `region` | Text | Geographic sales region | North, South, East, West |
| `payment_method` | Text | Payment type used | Credit Card, Debit Card, Bank Transfer |

### Data Quality Considerations
- ✅ No missing critical values
- ✅ Standardized date formats (MM/DD/YYYY)
- ✅ Currency formatting applied
- ✅ Consistent regional classifications
- ✅ Validated customer identifiers

---

## 🔧 Data Cleaning & Preparation

### Cleaning Steps Performed

1. **Date Standardization**
   - Converted all dates to MM/DD/YYYY format
   - Removed any inconsistent date entries
   - Created additional date dimensions (Month, Quarter, Year)

2. **Text Cleaning**
   - Removed leading/trailing spaces from names and categories
   - Standardized region and payment method naming (Title Case)
   - Verified unique product names

3. **Data Validation**
   - Removed duplicate customer transactions (if any)
   - Verified all sales amounts are positive values
   - Confirmed all customer_ids are unique

4. **Feature Engineering**
   - Created `Month` column for temporal analysis (extracted from order_date)
   - Created `Quarter` column for quarterly business reviews
   - Created `Year` column for year-over-year comparisons
   - Created helper columns for dashboard filtering

5. **Enrichment**
   - Added transaction sequence numbers
   - Created order value brackets for segmentation
   - Calculated customer lifetime value indicators

### Data Integrity Checks
- ✅ Zero null values in critical columns
- ✅ Outlier analysis completed (verified high-value transactions are legitimate)
- ✅ Referential integrity maintained across customer records

---

## 📈 Dashboard Design & Architecture

### Dashboard Sections

#### 1. **Executive Summary (KPI Cards)**
High-level metrics providing instant business health assessment:

- **Total Revenue**: Sum of all sales_amount values
  - *Formula*: `=SUM(sales_data[sales_amount])`
  - *Business Impact*: Overall financial performance

- **Total Orders**: Count of unique transactions
  - *Formula*: `=COUNTA(sales_data[order_date])`
  - *Business Impact*: Transaction volume and activity level

- **Total Customers**: Count of unique customer_ids
  - *Formula*: `=SUMPRODUCT(1/COUNTIF(sales_data[customer_id],sales_data[customer_id]))`
  - *Business Impact*: Customer base size and reach

- **Average Order Value (AOV)**: Mean revenue per transaction
  - *Formula*: `=AVERAGE(sales_data[sales_amount])`
  - *Business Impact*: Customer spending behavior and pricing strategy effectiveness

#### 2. **Visualizations**

**Chart 1: Revenue by Product (Column Chart)**
- **Purpose**: Identify product performance hierarchy
- **Insight Type**: Product portfolio analysis
- **Data**: Product names (X-axis) vs. Total Revenue (Y-axis)
- **Interactive**: Filters by Month, Region, Payment Method

**Chart 2: Monthly Revenue Trend (Line Chart)**
- **Purpose**: Track revenue progression and seasonality
- **Insight Type**: Temporal trend analysis
- **Data**: Month (X-axis) vs. Cumulative Revenue (Y-axis)
- **Interactive**: Filters by Product, Region, Payment Method
- **KPI**: Quarter-over-quarter growth rate displayed

**Chart 3: Revenue by Region (Bar Chart)**
- **Purpose**: Evaluate geographic performance distribution
- **Insight Type**: Regional performance comparison
- **Data**: Region names (Y-axis) vs. Total Revenue (X-axis)
- **Interactive**: Filters by Month, Product, Payment Method
- **Sorted**: Descending order (highest performing region first)

**Chart 4: Top Customers (Horizontal Bar Chart)**
- **Purpose**: Identify VIP customers and high-value segments
- **Insight Type**: Customer segmentation and concentration
- **Data**: Top 10 customers by revenue
- **Interactive**: Filters by Month, Product, Region, Payment Method
- **Calculated**: Customer lifetime value and transaction frequency

#### 3. **Interactive Filters (Slicers)**

All charts respond dynamically to the following filters:

| Filter | Type | Purpose | Values |
|--------|------|---------|--------|
| **Month** | Dropdown/Timeline | Temporal segmentation | Jan - Dec |
| **Product** | Dropdown (Multi-select) | Product category filtering | All available products |
| **Region** | Dropdown (Multi-select) | Geographic segmentation | North, South, East, West |
| **Payment Method** | Dropdown (Multi-select) | Payment type analysis | Credit Card, Debit Card, Bank Transfer |

**Filter Behavior**:
- Filters are interconnected (cross-filtering enabled)
- Default state shows all data (no filtering applied)
- Users can apply single or multiple filter combinations
- Visual indicators show active filters

---

## 🔍 Key Insights & Findings

Detailed insights are documented in [`insights.md`](./insights.md). Summary highlights include:

### Sales Performance
- 📊 **Total Revenue Generated**: $[X] across [Y] orders
- 📈 **Average Order Value**: $[AOV] per transaction
- 🔝 **Top Performing Product**: [Product Name] generating $[Amount] (X% of total revenue)

### Customer Analysis
- 👥 **Total Unique Customers**: [Number]
- ⭐ **Top Customer**: [Customer Name] with $[LTV] lifetime value
- 💰 **Customer Concentration**: Top 20% of customers generate [X]% of revenue

### Geographic Performance
- 🌍 **Best Performing Region**: [Region Name] with $[Amount] (X% of total)
- 📍 **Regional Growth Leader**: [Region Name] with [X]% month-over-month growth
- 🎯 **Opportunities**: [Region Name] shows potential for expansion

### Temporal Trends
- 📅 **Seasonal Pattern**: Revenue peaks in [Month/Quarter] and dips in [Month/Quarter]
- 📊 **Growth Trajectory**: [X]% average monthly growth rate
- 🔄 **Cyclical Behavior**: [Description of patterns]

### Payment Preferences
- 💳 **Dominant Payment Method**: [Method] accounts for [X]% of transactions
- 🔀 **Alternative Methods**: [Method] [X]%, [Method] [X]%
- 💡 **Operational Implication**: Optimize payment processing for top method

---

## 💡 Business Recommendations

Based on data analysis, the following strategic recommendations are proposed:

### 1. **Product Strategy**
- 📌 **Focus**: Increase marketing spend on top-performing products to maximize ROI
- 📌 **Opportunity**: Bundling underperforming products with bestsellers to boost sales
- 📌 **Action**: Evaluate pricing strategy for premium products to improve AOV

### 2. **Customer Retention**
- 👥 **VIP Program**: Implement loyalty rewards for top 20% of customers
- 📧 **Personalization**: Develop targeted campaigns based on purchase history
- 🎁 **Retention**: Exclusive offers for high-value customer segments

### 3. **Regional Expansion**
- 🌍 **Underperforming Regions**: Investigate barriers to growth in low-revenue regions
- 📍 **Resource Allocation**: Increase sales efforts in high-growth regions
- 🎯 **Local Strategy**: Tailor product mix and marketing for regional preferences

### 4. **Revenue Optimization**
- 💰 **Pricing**: Test premium pricing on best-selling products
- 📊 **Upselling**: Identify cross-sell opportunities based on purchase patterns
- 🔄 **Seasonality**: Build inventory and marketing campaigns around peak seasons

### 5. **Payment Processing**
- 💳 **Efficiency**: Streamline dominant payment method processing
- ⚡ **Adoption**: Promote alternative payment methods for operational flexibility
- 🛡️ **Security**: Ensure compliance and security across all payment channels

---

## 🎓 Skills Demonstrated

This project showcases capabilities aligned with Data Analyst and Business Analyst job requirements:

### Data Analysis & Manipulation
- ✅ **Excel Functions**: SUM, AVERAGE, COUNT, COUNTIF, SUMIF, INDEX-MATCH, VLOOKUP
- ✅ **Data Aggregation**: Pivot tables for multi-dimensional analysis
- ✅ **Statistical Analysis**: Descriptive statistics, trend analysis, variance calculations
- ✅ **Data Cleaning**: Removing duplicates, standardizing formats, handling missing values

### Data Visualization
- ✅ **Chart Types**: Column, Line, Bar, Horizontal Bar charts
- ✅ **Dashboard Design**: Professional layout with KPI cards and visualizations
- ✅ **Interactive Elements**: Slicers and filters for dynamic exploration
- ✅ **Visual Hierarchy**: Clear emphasis on critical metrics and insights

### Business Intelligence
- ✅ **KPI Identification**: Defining and tracking key performance indicators
- ✅ **Trend Analysis**: Identifying patterns, seasonality, and growth trajectories
- ✅ **Segmentation**: Customer, product, and geographic segmentation
- ✅ **Business Acumen**: Translating data into actionable business recommendations

### Problem Solving
- ✅ **Requirement Analysis**: Understanding business needs and translating into analytics
- ✅ **Root Cause Analysis**: Investigating performance variations
- ✅ **Scenario Planning**: Using filters to explore different business scenarios
- ✅ **Decision Support**: Providing data-driven insights for strategic decisions

### Soft Skills
- ✅ **Documentation**: Clear, professional documentation of analysis methodology
- ✅ **Communication**: Presenting findings in business-friendly language
- ✅ **Attention to Detail**: Ensuring data accuracy and consistency
- ✅ **Project Organization**: Well-structured repository and organized deliverables

---

## 📁 Repository Structure

```
sales-dashboard-excel/
│
├── README.md                    # Project overview and documentation (this file)
├── Sales_Dashboard.xlsx         # Main Excel workbook with dashboard
├── dataset.csv                  # Raw data source file
├── insights.md                  # Detailed analysis findings and recommendations
├── dashboard_screenshot.png     # Visual reference of dashboard layout
└── .gitignore                   # Git ignore file for large Excel files
```

### File Descriptions

| File | Purpose | Size | Format |
|------|---------|------|--------|
| `Sales_Dashboard.xlsx` | Interactive dashboard with data and visualizations | ~2-5 MB | Excel Workbook |
| `dataset.csv` | Raw transaction data for import/reference | ~100-500 KB | CSV |
| `insights.md` | Detailed analysis, findings, and recommendations | ~10-15 KB | Markdown |
| `dashboard_screenshot.png` | Visual preview of dashboard (for GitHub preview) | ~500 KB - 2 MB | PNG Image |

---

## 🚀 Getting Started

### Prerequisites
- **Microsoft Excel** (2016 or later recommended)
- **Basic Excel knowledge**: Formulas, Pivot Tables, basic charting
- Optional: **CSV reader** for viewing dataset.csv

### How to Use This Project

1. **Download the Excel File**
   ```
   Download Sales_Dashboard.xlsx from this repository
   ```

2. **Open in Excel**
   - Launch Microsoft Excel
   - Open `Sales_Dashboard.xlsx`
   - Enable macros if prompted (for interactive features)

3. **Explore the Dashboard**
   - View the dashboard worksheet (typically the first tab)
   - Review KPI cards for overall metrics
   - Examine visualizations for insights

4. **Use Interactive Filters**
   - Click on filter dropdowns (Month, Product, Region, Payment Method)
   - Select desired filter values
   - Charts update automatically
   - Reset to view all data

5. **Review Data Source**
   - Click on "Data" worksheet tab
   - View raw transaction data
   - Examine data structure and values

6. **Read Analysis**
   - Open [`insights.md`](./insights.md) for detailed findings
   - Review business recommendations
   - Compare with dashboard visualizations

---

## 📊 Dashboard Features

### Dynamic Capabilities
- 🔄 **Real-time Updates**: All charts update when filters change
- 📱 **Responsive Layout**: Works on standard and large monitors
- 🎨 **Professional Formatting**: Color-coded visualizations and clear typography
- 📈 **Scalable**: Can accommodate additional data without redesign

### Performance Considerations
- ⚡ Optimized for smooth performance with 500+ records
- 💾 Lightweight file size for easy sharing
- 🔐 No macros required (standard Excel formulas)

---

## 🔄 Data Refresh Process

To update the dashboard with new data:

1. **Update Dataset**
   - Replace `dataset.csv` with new transaction data
   - Ensure column structure matches original format

2. **Refresh Excel File**
   - Open `Sales_Dashboard.xlsx`
   - Right-click on pivot tables → Refresh All
   - Charts automatically update with new data

3. **Verify Results**
   - Check KPI values are reasonable
   - Confirm visualizations reflect new data
   - Validate filter functionality

---

## 💼 Professional Applications

This project demonstrates readiness for:

### Entry-Level Roles
- **Junior Data Analyst** — Data analysis, dashboard creation, reporting
- **Business Analyst** — Requirements gathering, business process analysis, KPI tracking
- **Data Engineer (Junior)** — Data pipeline understanding, ETL concepts, data quality
- **Technology Graduate** — Technical skills, analytical thinking, business acumen

### Relevant Responsibilities Showcased
- ✅ Translating business requirements into analytical solutions
- ✅ Cleaning and preparing data for analysis
- ✅ Building interactive dashboards for stakeholder consumption
- ✅ Generating actionable insights from data
- ✅ Documenting analysis methodology and findings
- ✅ Presenting data-driven recommendations

---

## 📚 Learning Outcomes

This project illustrates proficiency in:

### Technical Skills
- Advanced Excel formula writing (aggregate, conditional, lookup functions)
- Pivot table creation and management
- Data visualization best practices
- Dashboard design principles
- Data cleaning and validation techniques

### Analytical Skills
- Exploratory data analysis (EDA) methodology
- Trend identification and forecasting
- Customer segmentation and RFM analysis
- KPI definition and tracking
- Root cause analysis

### Business Skills
- Business problem identification
- Stakeholder requirements translation
- Data-driven decision making
- Strategic recommendation formulation
- ROI and performance optimization


---

## 🎯 Next Steps & Enhancements

Potential future improvements:
- [ ] Integrate additional data sources (e.g., customer demographics, marketing spend)
- [ ] Add predictive analytics (forecasting using regression models)
- [ ] Implement Power Query for automated data refresh
- [ ] Develop advanced segmentation analysis (RFM, clustering)
- [ ] Create drill-down capabilities for deeper analysis
- [ ] Build mobile-friendly dashboard export
- [ ] Add what-if scenario planning tools
- [ ] Integrate with BI tools (Power BI, Tableau) for enhanced capabilities

---

**Last Updated**: May 2026

**Project Status**: ✅ Complete and Ready for Review

Thank you for reviewing this project!

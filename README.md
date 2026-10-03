# Exploratory Data Analysis for an Online Store

## Project Overview

This project presents an exploratory data analysis (EDA) of online-store sales data covering the period from **2010 to 2017**.

The goal of the analysis was to clean and combine several related datasets, calculate key business metrics, explore sales and profitability patterns, analyze geographic and product-level performance, investigate shipping times, and identify trends that could support business decision-making.

The analysis was performed in **Python** using **Pandas, NumPy, Matplotlib, and Seaborn**.

---

## Business Questions

The project focuses on the following questions:

- Which product categories generate the highest revenue and profit?
- Which countries and regions contribute most to sales?
- How do Online and Offline sales channels compare?
- How long does it take to ship orders after they are placed?
- Is shipping time related to order profitability?
- How do revenue and sales patterns change over time?
- Are there noticeable weekly patterns in profitability?
- What data-quality issues could affect business reporting?

---

## Dataset

The analysis uses three related tables:

- `events.csv` — order and sales information
- `products.csv` — product reference data
- `countries.csv` — country and regional reference data

The tables were joined using:

- `Product ID` → product `id`
- `Country Code` → country `alpha-3` code

After cleaning, the main sales dataset contained **1,328 orders**.

---

## Data Cleaning

The data-cleaning process included:

- checking missing values;
- handling missing country codes;
- removing two records with missing `Units Sold`;
- correcting the missing ISO alpha-2 code for Namibia;
- handling missing region information for Antarctica;
- converting order and shipping dates to datetime format;
- checking for duplicate rows;
- standardizing inconsistent categorical values in `Order Priority` and `Sales Channel`;
- checking logical consistency, including shipping dates and unit costs.

A total of **82 missing country codes (6.17%)** were retained as `Unknown` so that the associated sales information would not be lost.

---

## Feature Engineering

Several business metrics were calculated from the original data:

- **Revenue** = Units Sold × Unit Price
- **Total Cost** = Units Sold × Unit Cost
- **Profit** = Revenue − Total Cost
- **Shipping Time** = Ship Date − Order Date

Additional time-based features were created for year and day-of-week analysis.

---

## Key KPIs

- **Orders:** 1,328
- **Revenue:** $1.70B
- **Total Cost:** $1.20B
- **Profit:** $501.43M
- **Units Sold:** 6.58M
- **Known Countries:** 45
- **Average order-to-shipment time:** 24.8 days

---

## Key Findings

### Product Performance

**Office Supplies** generated the highest revenue at approximately **$400M**, representing about **24% of total revenue**, and also had the highest number of units sold at approximately **620K units**.

**Cosmetics** generated the highest profit at approximately **$93M**, showing that the most frequently purchased category is not necessarily the most profitable one.

Categories such as **Beverages** and **Fruits** had relatively high unit sales but comparatively low revenue and profit.

---

### Geographic Performance

**Europe** was the dominant market, accounting for approximately:

- **$1.5B in revenue**
- **$450M in profit**
- **5.8M units sold**
- **89% of total revenue**
- **88% of all units sold**

Among countries with known location data, the highest revenue came from:

- Czech Republic — approximately $54M
- Ukraine — approximately $53M
- Bosnia and Herzegovina — approximately $50M

The `Unknown` geographic group generated approximately **$103M in revenue**, highlighting the business importance of improving country-code completeness.

---

### Sales Channels

Online and Offline sales contributed almost equally:

- **Offline:** approximately $870M in revenue (51%)
- **Online:** approximately $830M in revenue (49%)

This suggests that both channels play a significant role in overall business performance.

---

### Shipping-Time Analysis

Average order-to-shipment time was approximately **24.8 days**.

At the product-category level, average shipping time was generally between **21 and 27 days**.

The largest differences were observed at the country level. **Hungary** had the longest average shipping time at approximately **32 days**.

---

### Shipping Time vs Profit

The Pearson correlation between shipping time and profit was **0.060**, indicating almost no linear relationship between the two variables.

Within the available data, longer or shorter order-to-shipment time did not appear to be a meaningful driver of order profitability.

---

### Sales Trends Over Time

Europe remained the main source of revenue throughout the analyzed period.

However, the data did not show consistent long-term growth. Instead, revenue varied from year to year across regions, countries, and product categories.

The 2017 data covers only part of the year, so lower values for that year should not be interpreted as evidence of a confirmed decline.

---

### Weekly Profit Patterns

The highest total profit was observed on **Friday ($79.3M)**, while the lowest was observed on **Thursday ($64.3M)**.

Several categories showed stronger day-of-week patterns, especially:

- Cosmetics
- Household
- Cereal
- Clothes

For example, Cosmetics generated approximately **$24.6M in profit on Fridays**, almost three times its Sunday result.

---

## Business Recommendations

Based on the analysis:

- Maintain sufficient inventory for **Office Supplies**, the largest revenue-generating category.
- Pay particular attention to **Cosmetics**, the most profitable category, including its strong Friday performance.
- Improve the completeness of **Country Code** data to increase the accuracy of geographic reporting.
- Continue supporting both **Online and Offline** sales channels because their contributions are nearly equal.
- Investigate the lower sales volume and slightly longer shipping time in **Asia** to identify potential growth or operational opportunities.

---

## Tools and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- Google Colab

---

## Repository Structure

```text
Exploratory-data-analysis-for-online-store/
│
├── README.md
├── online_store_eda.ipynb
└── data/
    ├── events.csv
    ├── products.csv
    └── countries.csv
```

> If the original datasets cannot be shared publicly, the `data/` folder can be omitted and the data source can be described instead.

---

## Skills Demonstrated

This project demonstrates practical experience with:

- exploratory data analysis;
- data cleaning and validation;
- handling missing values;
- joining multiple datasets;
- feature engineering;
- KPI calculation;
- aggregation and segmentation;
- correlation analysis;
- time-series exploration;
- data visualization;
- translating analytical results into business insights and recommendations.

---

## Note

This project is intended as a portfolio project demonstrating an end-to-end exploratory data analysis workflow in Python.

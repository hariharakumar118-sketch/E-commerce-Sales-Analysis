# E-commerce Sales Analysis Dashboard (Excel)

A descriptive analysis of a multi-channel e-commerce business, built in Microsoft Excel with pivot tables, slicers and an interactive dashboard. It answers one question: **what happened in sales, and where are the opportunities?**

<img width="1482" height="526" alt="image" src="https://github.com/user-attachments/assets/b53e92a2-bf38-423a-9fda-387db448f6ab" />


---

## Project overview

| | |
|---|---|
| **Goal** | Understand sales by channel, region, customer group, product and payment type |
| **Type** | Descriptive analysis |
| **Tool** | Microsoft Excel (pivot tables, slicers, charts, lookup formulas) |
| **Period** | Oct 2023 to Oct 2025 |
| **Output** | 1 dashboard, 3 pivot tables, 1 descriptive statistics sheet, 1 written report |

---

## How the business runs

The business sells products to customers through three types of stores across four regions.

```
Products (100 items, 5 categories)
      -> Stores (20 stores: Flagship / Online / Outlet, in East / North / South / West)
      -> Customers (500, grouped in Bronze / Silver / Gold / Platinum tiers)
      -> Orders (product + quantity + unit price - discount)
      -> Payment (COD / Credit Card / PayPal)
      -> Revenue
```

| Part | Description |
|---|---|
| **Products** | Beauty, Clothing, Electronics, Home and Sports, each with a cost and stock level |
| **Channels** | Flagship, Online and Outlet stores |
| **Regions** | East, North, South, West |
| **Customers** | Different ages and genders, with four loyalty tiers |
| **Payments** | Cash on Delivery, Credit Card, PayPal |
| **Revenue** | Quantity x Unit_Price x (1 - Discount) |

---

## Dataset

Four related tables, linked by ID columns:

```
Customer --(Customer_ID)--+
Product  --(Product_ID)---+-- Sales
Store    --(Store_ID)-----+
```

| Table | Rows | Main columns |
|---|---|---|
| **Sales** | 2,000 | Sales_ID, Order_Date, Customer_ID, Product_ID, Store_ID, Quantity, Unit_Price, Discount, Payment_Type, Total_Amount |
| **Customer** | 500 | Customer_ID, Name, Age, Gender, City, State, Loyalty_Level, Total_Amount |
| **Product** | 100 | Product_ID, Product_Name, Category, Sub_Category, Brand, Cost, Stock |
| **Store** | 20 | Store_ID, Store_Name, Region, City, Store_Type |

**Data cleaning:** columns ending in **CL** are the cleaned versions (blank values handled, names and cities standardised, loyalty levels cleaned). All analysis uses the CL columns.

---

## What is in the workbook

| Sheet | Content |
|---|---|
| Data sheets | Sales, Customer, Product, Store (raw and cleaned columns) |
| Descriptive Analysis | Mean, median, standard deviation, skewness and kurtosis for Product Cost, Sales Unit Price and Customer Purchase Total, plus a loyalty-wise customer table |
| Pivot 1 | Loyalty Tier vs Payment Type: Quantity and Average Unit Price |
| Pivot 2 | Orders by Gender and Region |
| Pivot 3 | Orders and Average Unit Price by Store Type, Quarter and Year |
| Dashboard | 5 charts, slicers and an insights panel |

### Dashboard charts

| # | Chart | What it shows |
|---|---|---|
| 1 | Payment Type Share of Revenue | COD, Credit Card and PayPal split |
| 2 | Product Cost and Stock by Category | Cost and stock for Sports, Home, Electronics, Clothing and Beauty |
| 3 | Revenue by Store Type and Region | Channel performance in each region |
| 4 | Revenue by Loyalty Tier and Quarter | Bronze, Silver, Gold and Platinum by quarter |
| 5 | Customer Count and Spend by Age Group and Gender | Who the customers are and what they spend |

### Screenshots

| Descriptive analysis | Pivot 1 |
|---|---|
| <img width="880" height="476" alt="image" src="https://github.com/user-attachments/assets/5f0e4e75-3ebe-4153-a3b8-60e3a4945dab" />
 | <img width="1398" height="402" alt="image" src="https://github.com/user-attachments/assets/962a03b7-6a8a-492d-8747-01614c904917" />
 |

| Pivot 2 | Pivot 3 |
|---|---|
| <img width="1334" height="265" alt="image" src="https://github.com/user-attachments/assets/342748e4-75c0-4d8c-8d94-ca5d3b7106c7" />
 | <img width="1338" height="500" alt="image" src="https://github.com/user-attachments/assets/d7d98c9a-898b-4991-85c6-8b58c8f39d8c" />
|

---

## Techniques used

- **Descriptive statistics:** central tendency, spread and shape (skewness, kurtosis)
- **Lookup formulas:** `XLOOKUP` (or `INDEX/MATCH`) to bring Region, Store_Type, Gender and Loyalty into the Sales table
- **Aggregation formulas:** `SUMIFS`, `COUNTIFS`, `IFS` (age groups)
- **Pivot tables and pivot charts** with slicers connected through Report Connections
- **Data cleaning** with cleaned (CL) columns

---

## Key findings

1. **Online and Flagship generate 81% of revenue** (1.76M of about 2.17M). Online has the highest average order value (1,112).
2. **The West contributes only 12% of revenue** and has no Outlet sales.
3. **Each region has a weaker channel:** North in Online, South in Flagship.
4. **Platinum is the largest loyalty tier** (30% of customers), and spend per customer is similar across tiers.
5. **Female customers contribute more:** 55% of orders and about 17% higher spend per customer.
6. **Customer spend is uneven:** mean 1,134 vs median 950, skewness 0.88.
7. **Sales are steady:** Q1 to Q3 had 748 orders in 2024 and 752 in 2025.

Full details, numbers and recommendations are in **[Ecommerce_Sales_Analysis_Report.md](Ecommerce_Sales_Analysis_Report.md)**.

---

## Future scope

- Margin analysis (Unit_Price minus Cost) by category and brand
- Customer segmentation (RFM: recency, frequency, monetary value)
- Sales forecasting and seasonality analysis
- Power Pivot data model with DAX measures

---

## Folder structure

```
ecommerce-sales-analysis/
├── README.md
├── Ecommerce_Sales_Analysis_Report.md
├── Ecommerce_Sales_Dashboard.xlsx
└── images/
    ├── dashboard.png
    ├── descriptive_analysis.png
    ├── pivot1.png
    ├── pivot2.png
    └── pivot3.png
```

---

## Author

_Add your name, role and LinkedIn link here._

# Customer Sales & Segmentation Analysis — Power BI

An end-to-end customer analytics project built with **Excel, Power Query, Power BI and DAX** to understand customer value, segmentation, profitability, RFM behavior, retention risk, membership performance and regional sales.

The project converts customer and transaction data into a five-page interactive Power BI dashboard designed to support customer-management and retention decisions.

---

## Dashboard Preview

### 1. Customer Overview

![Customer Overview](PNG/Dashboard%201.PNG)

Provides a high-level view of customer volume, active customers, net sales, net profit, repeat customer rate, monthly sales trends, acquisition channels, customer segments and membership performance.

---

### 2. Customer Segmentation

![Customer Segmentation](PNG/Dashboard%202.PNG)

Analyzes customer value and profitability across customer segments and membership levels, including customer distribution, average customer value, segment profitability and segment-level sales performance.

---

### 3. Customer Value & RFM Analysis

![Customer Value & RFM Analysis](PNG/Dashboard%203.PNG)

Uses **Recency, Frequency and Monetary Value (RFM)** to classify customers by engagement and value, identify customers requiring retention attention and evaluate revenue contribution by RFM segment.

---

### 4. Customer Geography

![Customer Geography](PNG/Dashboard%204.PNG)

Examines customer distribution, sales and profitability across regions and states to identify geographic concentration and performance opportunities.

---

### 5. Customer Insights & Management

![Customer Insights & Management](PNG/Dashboard%205.PNG)

Combines customer risk, high-value customer analysis, profitability and membership performance to support management-level retention and customer-prioritization decisions.

---

## Project Overview

**Customer Sales & Segmentation Analysis** is a Power BI business intelligence project focused on answering a practical question:

> Who are the most valuable customers, how do different customer groups contribute to revenue and profit, and which customers require retention attention?

The dashboard combines customer information, order transactions, product attributes, regional information and target data into an interactive analytical environment.

### Business Flow

**Customer Data → Customer Value → Customer Behavior → Customer Risk → Management Action**

---

## Business Problem

Customer and sales information can become difficult to interpret when customer profiles, transactions, products and geographic information are analyzed separately.

Management needs to understand:

- Which customer segments generate the most revenue?
- Which segments are most profitable?
- Which customers have the highest monetary value?
- Which customers are frequent and recently active?
- Which customers may be at risk of becoming inactive?
- Which acquisition channels contribute the largest customer base?
- Which membership levels generate the most sales?
- Which regions and states perform best?
- Where should retention and customer-management efforts be prioritized?

This project addresses these questions through interactive Power BI reporting.

---

## Project Objectives

1. Analyze overall customer and sales performance.
2. Measure customer value and profitability.
3. Compare customer segments and membership levels.
4. Analyze customer acquisition channels.
5. Apply RFM analysis to understand customer behavior.
6. Identify customers requiring retention attention.
7. Analyze geographic customer and sales performance.
8. Provide management-oriented customer insights.
9. Build an interactive multi-page Power BI dashboard using reusable DAX measures.

---

## Key Business Questions

### Customer
- How many customers are present?
- How many customers are active?
- What is the repeat customer rate?
- Which acquisition channels bring the most customers?

### Segmentation
- Which customer segment has the largest customer base?
- Which segment generates the highest sales?
- Which segment generates the highest profit?
- Which segment has the highest average customer value?

### RFM
- Which customers are Champions?
- Which customers are Loyal Customers?
- Which customers are At Risk?
- Which customers are Lost Customers?
- Which customer groups contribute the most revenue?

### Geography
- Which regions have the highest customer concentration?
- Which regions generate the highest sales?
- Which regions generate the highest profit?
- Which states are the strongest sales contributors?

### Management
- Which high-value customers deserve priority?
- Which customers should receive retention or re-engagement campaigns?
- How can membership and customer-segment performance guide customer strategy?

---

## Dataset Overview

The project workbook contains six main sheets:

| Sheet | Purpose | Records |
|---|---|---:|
| Customers | Customer profile and segmentation information | 2,000 |
| Orders | Customer transaction and order information | 20,000 |
| Products | Product, category, brand and pricing information | 100 |
| Regions | Geographic mapping | 30 |
| Targets | Monthly regional sales and customer targets | 720 |
| Project_Info | Project metadata | 8 |

### Customer Data

Key fields include:

- Customer_ID
- Customer_Name
- Gender
- Age
- Region_ID
- Customer_Segment
- Acquisition_Channel
- Membership_Level
- City
- State
- Registration_Date

### Order Data

Key fields include:

- Order_ID
- Order_Date
- Customer_ID
- Product_ID
- Quantity
- Unit_Price
- Discount
- Payment_Mode
- Order_Status

### Product Data

Key fields include:

- Product_ID
- Product_Name
- Category
- Sub_Category
- Brand
- Cost_Price
- Selling_Price

### Regional Data

Key fields include:

- Region_ID
- Region
- State
- City

### Target Data

Key fields include:

- Month
- Region_ID
- Sales_Target
- Customer_Target

The target framework contains **720 records covering 30 regions across 24 months**. Actual transaction activity in the dashboard runs from **January 2025 through August 2026**, while the target framework extends through December 2026.

---

## Data Preparation

Data preparation was performed using Excel and Power Query before building the Power BI report.

### Main preparation steps

1. Imported workbook tables into Power BI.
2. Reviewed column names and data types.
3. Validated customer and product identifiers.
4. Checked relational keys such as Customer_ID, Product_ID and Region_ID.
5. Prepared date fields for time-based analysis.
6. Reviewed order-status values.
7. Created analytical calculations for sales and profit.
8. Prepared customer-level metrics for segmentation and RFM analysis.
9. Loaded the prepared tables into the Power BI data model.

---

## Data Model

The project uses customer, transaction, product and geographic information to create a connected analytical model.

```text
                    ┌─────────────────┐
                    │    Customers    │
                    │                 │
                    │ Customer_ID     │
                    │ Segment         │
                    │ Membership      │
                    │ Region_ID       │
                    └────────┬────────┘
                             │
                             │ Customer_ID
                             ▼
                    ┌─────────────────┐
                    │     Orders      │
                    │                 │
                    │ Order_ID        │
                    │ Customer_ID     │
                    │ Product_ID      │
                    │ Quantity        │
                    │ Unit_Price      │
                    │ Discount        │
                    │ Order_Status    │
                    └──────┬──────┬───┘
                           │      │
             Product_ID ───┘      └── Region_ID
                    │                    │
                    ▼                    ▼
          ┌─────────────────┐   ┌─────────────────┐
          │    Products     │   │     Regions     │
          │                 │   │                 │
          │ Product_ID      │   │ Region_ID       │
          │ Category        │   │ Region          │
          │ Brand           │   │ State           │
          │ Cost_Price      │   │ City            │
          │ Selling_Price   │   └─────────────────┘
          └─────────────────┘

                    ┌─────────────────┐
                    │     Targets     │
                    │                 │
                    │ Month           │
                    │ Region_ID       │
                    │ Sales_Target    │
                    │ Customer_Target │
                    └─────────────────┘
```

**Primary customer identifier:** `Customer_ID`

For customer-level analysis, `Customer_ID` should be treated as the unique identifier rather than `Customer_Name`, because customer names can repeat.

---

## KPI Framework

The dashboard focuses on the following business KPIs:

| KPI | Purpose |
|---|---|
| Total Customers | Measures the overall customer base |
| Active Customers | Measures customers with transaction activity |
| Net Sales | Measures sales after discount |
| Net Profit | Measures profitability after product cost |
| Average Customer Value | Estimates sales value generated per customer |
| Repeat Customer Rate | Measures repeat purchasing behavior |
| Customer Frequency | Measures purchase activity |
| Customer Recency | Measures how recently customers purchased |
| Customer Monetary Value | Measures customer spending value |
| RFM Score | Combines recency, frequency and monetary behavior |

### Core Sales Logic

```text
Net Sales = Quantity × Unit Price × (1 − Discount)
```

```text
Net Profit = Net Sales − Quantity × Cost Price
```

---

## Customer Segmentation

The dashboard analyzes five primary customer segments:

| Segment | Customers | Net Sales | Net Profit |
|---|---:|---:|---:|
| Regular | 750 | ₹214.40M | ₹38.54M |
| Loyal | 446 | ₹183.41M | ₹32.35M |
| Occasional | 387 | ₹79.38M | ₹14.18M |
| Premium | 242 | ₹126.04M | ₹22.40M |
| New | 175 | ₹40.01M | ₹7.02M |
| **Total** | **2,000** | **₹643.23M** | **₹114.50M** |

### Customer Value by Segment

| Segment | Average Customer Value |
|---|---:|
| Premium | ₹0.52M |
| Loyal | ₹0.41M |
| Regular | ₹0.29M |
| New | ₹0.23M |
| Occasional | ₹0.21M |

The analysis shows that **Premium customers have the highest average customer value**, while **Regular customers form the largest customer segment and contribute the highest total segment sales**.

---

## RFM Analysis

RFM stands for:

- **Recency** — How recently a customer purchased.
- **Frequency** — How often a customer purchased.
- **Monetary Value** — How much a customer spent.

The dashboard groups customers into RFM-based behavioral segments.

| RFM Segment | Customers | Revenue Contribution |
|---|---:|---:|
| Champions | 808 | ₹261M |
| Loyal Customers | 483 | ₹240M |
| At Risk | 237 | ₹72M |
| Lost Customers | 211 | ₹29M |
| New Customers | 160 | ₹20M |
| Other | — | ₹12M |
| Potential Loyalists | 30 | ₹9M |

### RFM Management Interpretation

**Champions**
- Reward and retain.
- Offer VIP experiences.
- Provide early access to products or promotions.

**Loyal Customers**
- Strengthen loyalty.
- Cross-sell and upsell relevant products.
- Encourage continued engagement.

**Potential Loyalists**
- Increase engagement.
- Use targeted offers to encourage repeat purchases.

**At Risk**
- Launch re-engagement campaigns.
- Identify reasons for declining activity.
- Provide personalized incentives where appropriate.

**Lost Customers**
- Run win-back campaigns.
- Test targeted offers and communication strategies.

**New Customers**
- Improve onboarding.
- Encourage the second purchase.
- Introduce relevant products and membership benefits.

---

## Dashboard Pages

### Page 1 — Customer Overview

Key analysis:

- Total Customers
- Active Customers
- Net Sales
- Net Profit
- Repeat Customer Rate
- Monthly Net Sales Trend
- Customers by Acquisition Channel
- Customers by Segment
- Sales by Membership Level
- Top 10 Customers by Sales

Primary filters:

- Year
- Region
- Customer Segment

---

### Page 2 — Customer Segmentation

Key analysis:

- Sales by Segment & Membership
- Customer Segment Performance
- Customer Distribution
- Average Customer Value by Segment
- Profit by Customer Segment
- Sales by Customer Segment

Primary filters:

- Year
- Region
- Membership Level

---

### Page 3 — Customer Value & RFM Analysis

Key analysis:

- Customer Recency vs Monetary Value
- RFM Customer Count
- Revenue Contribution by RFM Segment
- Top Customers by Monetary Value
- Customers Requiring Retention Attention

Primary filters:

- RFM Segment
- Region
- Membership Level

---

### Page 4 — Customer Geography

Key analysis:

- Customer Distribution by Region
- Net Sales by Region
- Net Profit by Region
- Net Sales by State

Primary filters:

- Year
- Region
- State
- Customer Segment

---

### Page 5 — Customer Insights & Management

Key analysis:

- Sales by Membership Level
- Customer Risk & Value Distribution
- Profitability by Customer Segment
- Priority Retention Customers
- Top High-Value Customers

Primary filters:

- RFM Segment
- Region
- Membership Level

---

## Key Business Insights

### 1. Strong overall customer value

The dashboard reports approximately:

- **2K total customers**
- **2K active customers**
- **₹643M net sales**
- **₹114M net profit**
- **322K average customer value**
- **99.40% repeat customer rate**

---

### 2. Regular customers drive the largest total segment contribution

Regular customers represent the largest customer segment with **750 customers** and contribute approximately **₹214.40M in net sales** and **₹38.54M in net profit**.

---

### 3. Premium customers have the highest average customer value

Premium customers show the highest average customer value at approximately **₹0.52M**, followed by Loyal customers at approximately **₹0.41M**.

This suggests that customer strategy should consider both **segment size** and **value per customer**.

---

### 4. Champions are the largest RFM group

Champions account for approximately **808 customers**, representing **40.4%** of the customer base in the RFM analysis, and contribute approximately **₹261M** in revenue.

---

### 5. At-risk customers represent a meaningful retention opportunity

The RFM analysis identifies approximately **237 At Risk customers**, contributing approximately **₹72M** in revenue.

This group is particularly important for retention and re-engagement strategies because losing high-value customers can negatively affect future revenue.

---

### 6. South is the strongest region

South has the highest customer count at approximately **523 customers** and generates approximately **₹177M in net sales** and **₹31.7M in net profit**.

---

### 7. Madhya Pradesh is the leading state by sales

Madhya Pradesh contributes approximately **₹69M in net sales**, followed by Maharashtra at approximately **₹49M** and Karnataka at approximately **₹46M**.

---

### 8. Organic Search is the largest acquisition channel

Organic Search contributes approximately **460 customers**, followed by Social Media with **429 customers** and Paid Ads with **350 customers**.

---

### 9. Silver membership contributes the highest total sales

Silver membership generates approximately **₹264M in net sales**, followed by Basic at **₹190M**, Gold at **₹139M** and Platinum at **₹50M**.

This should be interpreted alongside membership population size rather than assuming that the highest membership tier automatically produces the highest total revenue.

---

## Business Recommendations

### Customer Retention

- Prioritize At Risk customers for re-engagement.
- Build targeted win-back campaigns for Lost Customers.
- Create loyalty programs for Champions and Loyal Customers.
- Monitor high-value customers separately from the general customer base.

### Customer Growth

- Strengthen Organic Search because it currently contributes the largest customer volume.
- Evaluate Social Media and Paid Ads based on customer quality and downstream value, not only acquisition volume.
- Develop onboarding journeys for New Customers.

### Customer Value

- Create premium offers for high-value customers.
- Cross-sell relevant products to Loyal and Champions customers.
- Use customer value metrics to prioritize marketing budgets.

### Regional Strategy

- Continue strengthening the South region while identifying growth opportunities in lower-performing regions.
- Investigate state-level performance to identify geographic expansion opportunities.

### Membership Strategy

- Compare membership size against revenue contribution.
- Identify opportunities to move high-value customers into stronger loyalty tiers.
- Evaluate membership performance together with customer profitability and RFM behavior.

---

## Data Quality & Modeling Considerations

The project contains unique customer identifiers through `Customer_ID`, while customer names may repeat.

For production-quality customer ranking visuals, the recommended display convention is:

```text
Customer_ID + Customer_Name
```

rather than relying on `Customer_Name` alone.

This prevents repeated customer names from being interpreted as different customers and preserves customer-level analytical accuracy.

---

## Project Workflow

```text
Excel Workbook
      ↓
Power Query
      ↓
Data Cleaning & Transformation
      ↓
Power BI Data Model
      ↓
DAX Measures
      ↓
Customer Segmentation
      ↓
RFM Analysis
      ↓
Interactive Dashboard
      ↓
Business Insights
      ↓
Management Recommendations
```

---

## Tools & Technologies

| Tool | Usage |
|---|---|
| Microsoft Excel | Source workbook and data preparation |
| Power Query | Data cleaning and transformation |
| Power BI Desktop | Data modeling and dashboard development |
| DAX | Measures, KPIs, segmentation and analytical calculations |
| GitHub | Project documentation and portfolio presentation |

---

## Skills Demonstrated

- Business Intelligence
- Power BI Dashboard Development
- Power Query
- DAX
- Customer Analytics
- Customer Segmentation
- RFM Analysis
- Customer Retention Analytics
- Customer Value Analysis
- Profitability Analysis
- Regional Analysis
- Data Modeling
- KPI Development
- Business Reporting
- Data Storytelling
- Management Insights

---

## Repository Structure

```text
Customer-Sales-Segmentation/
│
├── Customer_Sales_Segmentation_Day2.pbix
├── Customer_Sales_Segmentation_Day2.xlsx
├── README.md
│
├── Background/
│   ├── 1.png
│   ├── 2.png
│   ├── 3.png
│   ├── 4.png
│   └── 5.png
│
└── PNG/
    ├── Customer_Sales_Segmentation_Day2.pdf
    ├── Dashboard 1.PNG
    ├── Dashboard 2.PNG
    ├── Dashboard 3.PNG
    ├── Dashboard 4.PNG
    └── Dashboard 5.PNG
```

---

## Project Information

| Item | Details |
|---|---|
| Project | Customer Sales & Segmentation Analysis |
| Project Type | Power BI Portfolio Project |
| Primary Tools | Power BI, Power Query, Excel, DAX |
| Dashboard Pages | 5 |
| Customers | 2,000 |
| Orders | 20,000 |
| Products | 100 |
| Regions | 30 |
| Target Records | 720 |
| Actual Transaction Period | January 2025 – August 2026 |

---

## Limitations

- Customer-level visuals should use `Customer_ID` together with `Customer_Name` to avoid ambiguity from repeated names.
- The target framework extends beyond the actual transaction period.
- The analysis is intended as a portfolio/business intelligence project and does not represent live operational reporting.
- RFM classifications depend on the selected RFM scoring logic and analysis date.

---

## Future Improvements

Potential future development includes:

- Customer lifetime value analysis
- Cohort analysis
- Customer churn prediction
- Product affinity analysis
- Customer purchase-frequency forecasting
- Campaign-level ROI analysis
- Automated refresh pipelines
- Power BI Service deployment
- Row-level security
- Drill-through customer profiles
- What-if retention scenarios
- Advanced customer scoring

---

## Portfolio Value

This project demonstrates the ability to move from raw business data to actionable customer intelligence:

**Data Preparation → Data Modeling → DAX → Segmentation → RFM → Visualization → Business Recommendations**

It is designed to demonstrate practical skills relevant to:

- Data Analyst
- Business Analyst
- BI Analyst
- Power BI Developer
- Customer Analytics Analyst

---

## AI Assistance

AI tools were used as development and documentation assistance during the project workflow, including support with planning, troubleshooting, documentation structure and analytical guidance.

The final dashboard, data model, calculations and project presentation were developed and reviewed as part of the project workflow.

---

## Author

**Altamash Nizamuddin**

Data Analyst  
Power BI • Python • MySQL

Mumbai, India

GitHub: [@altamash-analyst](https://github.com/altamash-analyst)

Open to remote opportunities in:

- Data Analytics
- Business Analysis
- Business Intelligence
- Power BI Development

---

## GitHub Repository Description

```text
Power BI customer analytics dashboard analyzing customer sales, segmentation, RFM behavior, customer value, retention risk, profitability, membership, acquisition channels and regional performance using Excel, Power Query and DAX.
```

---

## GitHub Topics

```text
power-bi
power-query
dax
excel
customer-analytics
customer-segmentation
rfm-analysis
customer-retention
retail-analytics
business-intelligence
data-analysis
power-bi-dashboard
```

---

## SEO Keywords

`Altamash-Analyst` · `Power BI Customer Analytics` · `Customer Segmentation` · `RFM Analysis` · `Customer Retention` · `Customer Value Analysis` · `Power BI Dashboard` · `DAX` · `Power Query` · `Excel Analytics` · `Business Intelligence` · `Retail Analytics` · `Data Analyst Portfolio` · `Customer Analytics Dashboard`

---

## Conclusion

The **Customer Sales & Segmentation Analysis** project demonstrates how customer and transaction data can be transformed into a practical business intelligence solution.

By combining customer segmentation, customer value analysis, RFM scoring, profitability analysis and geographic performance, the dashboard provides management with a structured view of **customer value, customer risk and retention opportunities**.

The project emphasizes a complete analytical workflow rather than visualization alone:

**Raw Data → Transformation → Modeling → DAX → Customer Intelligence → Business Action**

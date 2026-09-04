# Retail Customer Sales & Segmentation Analysis

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=flat&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-Data%20Source-217346?style=flat&logo=microsoftexcel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-ETL-5C2D91?style=flat)
![DAX](https://img.shields.io/badge/DAX-Analytics-0078D4?style=flat)
![Figma](https://img.shields.io/badge/Figma-Design-F24E1E?style=flat&logo=figma&logoColor=white)

## Project Overview

**Retail Customer Sales & Segmentation Analysis** is a Power BI business intelligence project focused on understanding customer value, purchasing behavior, segmentation, geographic performance, membership contribution, and customer retention risk.

The project transforms customer and transaction data into an interactive five-page Power BI dashboard designed to support customer-focused business decisions.

Instead of looking only at total sales, the analysis answers a more important business question:

> **Who are the customers creating value, how valuable are they, and which customers require management attention?**

The project combines:

- Customer segmentation
- Customer value analysis
- RFM analysis
- Customer retention analysis
- Membership analysis
- Acquisition channel analysis
- Geographic analysis
- Revenue and profitability analysis
- Customer risk identification

This project was developed as part of the **Altamash-Analyst Data Analytics portfolio**.

---

# Table of Contents

1. [Business Problem](#business-problem)
2. [Business Objectives](#business-objectives)
3. [Key Business Questions](#key-business-questions)
4. [Project Information](#project-information)
5. [Technology Stack](#technology-stack)
6. [Dataset Overview](#dataset-overview)
7. [Data Dictionary](#data-dictionary)
8. [Data Preparation](#data-preparation)
9. [Data Model](#data-model)
10. [KPI Framework](#kpi-framework)
11. [Customer Segmentation](#customer-segmentation)
12. [RFM Analysis](#rfm-analysis)
13. [Dashboard Pages](#dashboard-pages)
14. [Key Business Insights](#key-business-insights)
15. [Business Recommendations](#business-recommendations)
16. [Data Quality Considerations](#data-quality-considerations)
17. [Project Workflow](#project-workflow)
18. [Repository Structure](#repository-structure)
19. [Skills Demonstrated](#skills-demonstrated)
20. [Limitations](#limitations)
21. [Future Improvements](#future-improvements)
22. [Project Conclusion](#project-conclusion)
23. [Resume Project Description](#resume-project-description)
24. [LinkedIn Project Description](#linkedin-project-description)
25. [AI Assistance](#ai-assistance)
26. [Credits](#credits)
27. [Author](#author)
28. [GitHub SEO Keywords](#github-seo-keywords)

---

# Business Problem

Retail businesses often have large amounts of customer and transaction data but struggle to convert that information into actionable customer intelligence.

The business needs to understand:

- Which customers generate the most revenue?
- Which customer segments are the most valuable?
- Which customers are highly engaged?
- Which customers may be at risk of becoming inactive?
- Which membership levels contribute the most sales?
- Which acquisition channels attract the largest customer base?
- Which regions and states generate the strongest performance?
- Which customers should receive retention or re-engagement campaigns?

A conventional sales dashboard can show revenue and order trends, but it does not necessarily explain **customer behavior and customer value**.

This project addresses that gap by combining sales analytics with customer segmentation and RFM-based customer intelligence.

---

# Business Objectives

The primary objectives of this project were to:

1. Analyze customer sales performance.
2. Understand customer segment distribution.
3. Identify high-value customer groups.
4. Compare customer segments based on revenue and profitability.
5. Analyze membership-level performance.
6. Evaluate customer acquisition channels.
7. Analyze customer distribution across regions and states.
8. Calculate customer value metrics.
9. Segment customers using RFM methodology.
10. Identify customers requiring retention attention.
11. Provide management-oriented recommendations.
12. Build an interactive Power BI dashboard for decision support.

---

# Key Business Questions

The dashboard was designed around the following business questions:

### Customer

- How many customers are in the customer base?
- How many customers are active?
- Which customer segments are largest?
- Which customers contribute the most sales?

### Customer Value

- Which segments generate the highest revenue?
- Which segments generate the highest profit?
- Which segments have the highest average customer value?

### Customer Behavior

- How recently are customers purchasing?
- How frequently do customers purchase?
- Which customers have high monetary value?
- Which customers are at risk?

### Membership

- Which membership levels generate the most revenue?
- Does a higher membership level necessarily mean higher total sales?

### Acquisition

- Which acquisition channels bring the most customers?

### Geography

- Which regions generate the highest sales?
- Which regions generate the highest profit?
- Which states contribute the most revenue?

### Retention

- Which customers should receive retention campaigns?
- Which customers should receive win-back campaigns?
- Which customers should be prioritized for loyalty initiatives?

---

# Project Information

| Attribute | Details |
|---|---|
| Project Name | Retail Customer Sales & Segmentation Analysis |
| Project Type | Business Intelligence / Customer Analytics |
| Status | Completed |
| Duration | 3 Days |
| Role | Data Analyst |
| Project Category | Personal Portfolio / Analytics Project |
| Data Period | January 2025 – August 2026 |
| Dashboard Pages | 5 |
| Primary Tool | Microsoft Power BI |
| Data Preparation | Excel + Power Query |
| Analytical Language | DAX |
| Design Tools | Figma + GIMP |
| Data Source | Confidential |
| Python | Not Used |
| SQL | Not Used |

---

# Technology Stack

## Microsoft Excel

Used for working with the underlying structured datasets.

## Power Query

Used for:

- Data transformation
- Data cleaning
- Data type handling
- Query preparation
- Data integration
- Preparing tables for Power BI

## Power BI

Used for:

- Data modeling
- Interactive visualization
- Dashboard development
- Filtering and slicing
- KPI presentation
- Customer analytics

## DAX

Used for:

- KPI calculations
- Customer metrics
- Revenue calculations
- Profit calculations
- Customer value analysis
- RFM-related calculations

## Figma

Used for dashboard design and visual layout planning.

## GIMP

Used for supporting graphical and dashboard design assets.

---

# Dataset Overview

The project workbook contains six primary sheets:

| Sheet | Records | Purpose |
|---|---:|---|
| Customers | 2,000 | Customer master information |
| Orders | 20,000 | Customer transaction information |
| Products | 100 | Product and pricing information |
| Regions | 30 | Geographic reference data |
| Targets | 720 | Monthly regional target framework |
| Project_Info | 8 | Project metadata |

The actual transaction activity covers:

**January 2025 – August 2026**

The target framework covers:

**January 2025 – December 2026**

The target period therefore extends beyond the current transaction period and should be interpreted as a planning/target framework rather than actual historical performance.

---

# Data Dictionary

## Customers

| Column | Description |
|---|---|
| Customer_ID | Unique customer identifier |
| Customer_Name | Customer name |
| Gender | Customer gender |
| Age | Customer age |
| Region_ID | Geographic region identifier |
| Customer_Segment | Customer classification |
| Acquisition_Channel | Customer acquisition source |
| Membership_Level | Customer membership tier |
| City | Customer city |
| State | Customer state |
| Registration_Date | Customer registration date |

---

## Orders

| Column | Description |
|---|---|
| Order_ID | Unique order identifier |
| Order_Date | Transaction date |
| Customer_ID | Customer identifier |
| Product_ID | Product identifier |
| Quantity | Quantity purchased |
| Unit_Price | Price per unit |
| Discount | Discount applied to transaction |
| Payment_Mode | Payment method |
| Order_Status | Completed, Cancelled or Returned |

---

## Products

| Column | Description |
|---|---|
| Product_ID | Unique product identifier |
| Product_Name | Product name |
| Category | Product category |
| Sub_Category | Product sub-category |
| Brand | Product brand |
| Cost_Price | Product cost |
| Selling_Price | Product selling price |

---

## Regions

| Column | Description |
|---|---|
| Region_ID | Unique region identifier |
| Region | Region name |
| State | State |
| City | City |

---

## Targets

| Column | Description |
|---|---|
| Month | Target month |
| Region_ID | Region identifier |
| Sales_Target | Monthly sales target |
| Customer_Target | Monthly customer target |

---

# Data Preparation

Data preparation was performed using **Excel and Power Query** before building the Power BI model.

The preparation workflow included:

1. Importing the Excel workbook.
2. Loading the individual business tables.
3. Reviewing table structures.
4. Validating column data types.
5. Checking customer identifiers.
6. Checking product identifiers.
7. Checking regional relationships.
8. Preparing date fields.
9. Reviewing transaction status values.
10. Preparing customer and transaction tables for modeling.
11. Loading the prepared queries into Power BI.

The objective was to create a consistent analytical layer before developing measures and visuals.

---

# Data Model

The Power BI model combines customer, transaction, product, geographic and target information.

Conceptually, the model follows a customer-sales analytical structure:

```text
                    ┌─────────────────┐
                    │    Customers    │
                    │                 │
                    │ Customer_ID     │
                    │ Segment         │
                    │ Membership      │
                    │ Acquisition     │
                    │ Region_ID       │
                    └────────┬────────┘
                             │
                             │ Customer_ID
                             │
                    ┌────────▼────────┐
                    │     Orders      │
                    │                 │
                    │ Order_ID        │
                    │ Customer_ID     │
                    │ Product_ID      │
                    │ Order_Date     │
                    │ Quantity        │
                    │ Unit_Price      │
                    │ Discount        │
                    │ Status          │
                    └───────┬─────────┘
                            │
                            │ Product_ID
                            │
                    ┌───────▼─────────┐
                    │    Products     │
                    │                 │
                    │ Product_ID      │
                    │ Category        │
                    │ Brand           │
                    │ Cost_Price      │
                    │ Selling_Price   │
                    └─────────────────┘

                    ┌─────────────────┐
                    │     Regions     │
                    │                 │
                    │ Region_ID       │
                    │ Region          │
                    │ State           │
                    │ City            │
                    └─────────────────┘

                    ┌─────────────────┐
                    │     Targets     │
                    │                 │
                    │ Month           │
                    │ Region_ID       │
                    │ Sales_Target   │
                    │ Customer_Target│
                    └─────────────────┘

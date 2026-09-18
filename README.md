# E-Commerce Business Intelligence Platform

A production-style analytics platform built on real-world e-commerce data, combining **PostgreSQL** for scalable data storage and query optimization with **Power BI** for interactive, decision-ready reporting.

## Description / Purpose

This project was built to turn a large, multi-table e-commerce operational dataset into fast, reliable, decision-ready reporting. It consolidates and cleans **1,016,300+ records across 9 relational tables** into an optimized analytical layer, then surfaces business-critical KPIs — revenue, delivery performance, category trends, and customer sentiment — through an interactive, multi-page Power BI dashboard. It's designed for business analysts, operations teams, and stakeholders who need fast, reliable visibility into sales performance, logistics, and customer experience without digging through raw data.

## Table of Contents

- [Tech Stack](#tech-stack)
- [Data Source](#data-source)
- [Features & Highlights](#features--highlights)
- [Technical Deep Dive](#technical-deep-dive)
- [How to Run / Reproduce](#how-to-run--reproduce)
- [Screenshots / Demo](#screenshots--demo)
- [Author](#author)

## Tech Stack

| Tool | Role |
|---|---|
| PostgreSQL | Relational database storing and structuring raw e-commerce data |
| SQL | Data validation, view creation, B-Tree indexing for performance |
| Power BI Desktop | Main platform for data modeling and report building |
| Power Query | Data transformation and cleaning layer |
| DAX | Calculated measures, KPIs, and time intelligence logic |

## Data Source

- **9 base relational tables**: Customers, Geolocation, Products, Sellers, Orders, Order Items, Order Payments, Order Reviews, Product Category Name Translation
- **~1,016,300+ total rows**, including a ~1,010,000-row geolocation table
- **~70+ raw columns**, consolidated to **~20 optimized columns** at the reporting layer
- **Dataset**: [Link](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

## Features & Highlights

**Business problem:** Raw, multi-table transactional data was too large and unstructured for stakeholders to query or interpret directly — slow joins, inconsistent formatting, and no unified view of sales, logistics, or customer sentiment.

**Goal:** Build a single, fast, reliable reporting layer that lets non-technical stakeholders explore sales, delivery, and customer data without needing to touch the database.

**Key visuals (7 report pages):**
1. Executive Overview
2. Sales Trends
3. Category & Product Analysis
4. Customer Geographics
5. Delivery & Logistics
6. Reviews & Sentiment Analysis
7. Payments & Installments
8. Drill Through

*(Plus a drill-through page for category/state-level diagnostics.)*

**Business impact & insights:**
- Delivered **15–20+ DAX measures** — including YoY/YTD growth, 30-day rolling revenue, on-time delivery %, and review sentiment — giving stakeholders trend visibility without manual reporting
- Enabled fast, lag-free exploration of a 1M+ row dataset directly in Power BI
- Consolidated fragmented operational data into a single source of truth for sales, logistics, and customer experience reporting

## Technical Deep Dive

**Database Design & Optimization**
- Ingested and validated raw e-commerce data into a normalized PostgreSQL schema
- Applied B-Tree indexes on high-frequency lookup and filter columns, eliminating multi-table join lag and import timeouts at scale
- Removed empty/invalid string values during ingestion to improve data quality

**Analytical View Layer**
- Flattened the 9-table relational structure into **1 core fact view** (`fact_sales`) and **4 dimension views**
- Reduced ~70 raw columns to ~20 optimized, reporting-ready columns

**Import Method**
- **DirectQuery** for large, frequently updated operational tables

## How to Run / Reproduce

1. Restore the PostgreSQL database using the provided schema/data dump
2. Open the `.pbix` file in Power BI Desktop (aslo available in .pbip format)
3. Update the PostgreSQL connection details under **Transform Data → Data Source Settings**
4. Refresh the model to load DirectQuery/Import tables
5. Explore the 7 report pages via the navigation panel

## Screenshots / Demo
#### Executive Overview Dashboard
![Executive Overview Dashboard](https://github.com/Ashwin550/Postgresql-Powerbi-E-commerce-analytics-dashboard/blob/6bd9520b2791a043b3ed2695fef0dccf98bd1e35/Overview%20Executive%20Dashboard%20Image.png)

#### Sales Trend Analysis
![Sales Trend Image](https://github.com/Ashwin550/Postgresql-Powerbi-E-commerce-analytics-dashboard/blob/main/Sales%20trend%20image.png)

## Author

**Ashwin Jawale** — [LinkedIn](https://linkedin.com/in/ashwinjawale01)

# Myntra Sales Dashboard

A Power BI dashboard analyzing e-commerce order data modeled after Myntra, covering revenue trends, customer behavior, product performance, and delivery/payment patterns across two report pages.

## Data model

The report runs on a star schema with one fact table and three dimension tables:

- `fact` — order-level transactions (revenue, discount, rating, delivery days, order status, etc.)
- `dim-product` — category and brand attributes
- `dim-Customer` — customer name, ID, and membership tier
- `Calender` — date table for month/year time intelligence

This keeps the model lean and makes the slicers and visuals responsive even as the fact table grows.

## Pages

### 1. Overview
The landing page — a quick pulse check on the business.

| Visual | What it shows |
|---|---|
| KPI cards | Total Revenue, Total Orders, Average Rating, Average Discount, Avg Delivery Days, Unique Customers |
| Monthly Revenue (area chart) | Revenue trend across the year, useful for spotting seasonality |
| Top 5 Customers (column chart) | Highest-spending customers by revenue |
| Revenue by State (funnel) | Geographic contribution to total revenue |
| Membership Tier Split (donut) | Revenue/order share across membership tiers |
| Order detail table | Row-level order data for drill-down |

### 2. Products
A deeper look at what's selling and how.

| Visual | What it shows |
|---|---|
| Category Wise Revenue (column chart) | Revenue split across product categories |
| Top Selling Brands (treemap) | Brand-level revenue, sized by contribution |
| Order Status Breakdown (bar chart) | Delivered / cancelled / returned / pending split |
| Revenue by Payment Mode (pie chart) | UPI vs card vs COD vs wallet, etc. |
| Discount vs Revenue Impact (scatter chart) | Whether heavier discounting actually correlates with higher revenue |

Both pages share a slicer panel — filter by Year, Month, Category, Brand, State, Order Channel, Payment Mode, and Membership Tier, and every visual on the page updates together.

## Why I built this

Wanted a project that went past "just make some charts" and actually forced some decisions — how to structure a star schema instead of one flat table, when a KPI card is more useful than a chart, and how to lay out two pages so someone skims the Overview and digs into Products only if they need to. The discount-vs-revenue scatter plot on the Products page was the one I went back and forth on most — a bar chart would've hidden the outliers that the scatter makes obvious.

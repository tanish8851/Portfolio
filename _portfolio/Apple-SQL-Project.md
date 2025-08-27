---
title: "Apple SQL Project"
excerpt: "In-depth SQL project analyzing Apple Store sales and warranty claims data."
collection: portfolio
---

[Download full project report (PDF)](files/Apple%20Store%20Sales%20Analysis.pdf)



An end‑to‑end SQL analysis of Apple Store sales and warranty claims to uncover trends in product performance, store efficiency, and after‑sales reliability.

## Tech Stack
- **SQL (PostgreSQL):** complex joins, CTEs, window functions, subqueries
- **Excel/CSV:** preprocessing, validation, and ad‑hoc exploration

## Dataset
- **Size:** 1M+ sales rows with multi‑year history
- **Coverage:** Global Apple retail stores, products, sales, and warranty claims

## Schema (Core Tables)
- **stores**(`store_id`, `store_name`, `city`, `country`)
- **category**(`category_id`, `category_name`)
- **products**(`product_id`, `product_name`, `category_id`, `launch_date`, `price`)
- **sales**(`sale_id`, `sale_date`, `store_id`, `product_id`, `quantity`)
- **warranty**(`claim_id`, `claim_date`, `sale_id`, `repair_status`)

## What I Built
- Reproducible SQL workflows for cleansing, joining, and aggregating 1M+ rows
- Parameterized time‑window analyses (YTD, last 12/24/36 months)
- Robust date handling and calendar tables for monthly/weekly rollups
- Self‑service query pack for business questions (sales, warranty, store performance)

## Key Objectives & Queries
1. **Stores per country** – distribution of outlets
2. **Units by store** – total and time‑bounded
3. **Sales in Dec‑2023** – period filter and quality checks
4. **Stores with zero claims** – left join anti‑match logic
5. **% Warranty Void** – status segmentation
6. **Top store (last year)** – rank by total units
7. **Unique products sold (last year)** – distinct counts
8. **Avg price by category** – product mix insight
9. **Claims in 2020** – yearly claim volume
10. **Best‑selling day per store** – peak operational load
11. **Least‑selling product by country & year** – tail analysis
12. **Claims within 180 days of sale** – early‑life failure signal
13. **Claims on products launched in last 2 years** – new‑launch reliability
14. **USA months > 5,000 units (last 3 years)** – demand spikes
15. **Most claimed category (last 2 years)** – quality hotspots
16. **% chance of claim post‑purchase by country** – post‑sale risk
17. **Year‑over‑year growth by store** – trend health
18. **Price ↔ claims correlation (5‑year, by price band)** – reliability vs. price
19. **Store with highest % Paid Repaired** – service effectiveness
20. **Monthly running totals per store (4 years)** – momentum & seasonality

## Representative SQL Patterns
- **Window functions:** `ROW_NUMBER()`, `RANK()`, `SUM() OVER(PARTITION BY ... ORDER BY ...)`
- **CTEs & modular queries:** readable, testable transformations
- **Conditional aggregation:** status and country‑level splits
- **Date math:** `AGE`, `INTERVAL`, rolling windows, launch‑relative filters
- **Anti‑joins:** identify never‑claimed stores/products

## Outcomes
- Identified high‑performing stores and products for targeted inventory
- Flagged categories with elevated claim rates for QA follow‑up
- Quantified early‑life failures to refine warranty policies
- Produced ready‑to‑share charts/tables from SQL exports for stakeholders

## GitHub
- Full SQL scripts, query pack, and documentation: `github.com/tanish8851/Apple-SQL-Project`

---

> **Tip for reviewers:** See the **ERD** above for table relationships and open the **PDF** for methodology, assumptions, and result summaries.

![Entity Relationship Diagram (ERD)](images/image.png)



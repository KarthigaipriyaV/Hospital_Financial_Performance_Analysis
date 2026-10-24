# Healthcare Financial Risk Analysis | SQL & Power BI

## Overview

This project demonstrates end-to-end healthcare analytics using SQL Server and Power BI. The objective is to transform raw encounter, patient, procedure and payer data into insights about uncovered costs, high-cost patients and financial risk, through SQL cleaning and analysis queries and an interactive dashboard.

## Tools & Technologies

- SQL Server (T-SQL)
- Power BI
  

## Project Objectives

- Clean and validate healthcare encounter and procedure data
- Measure uncovered cost (claim cost minus payer coverage)
- Identify patients with frequent high-cost encounters
- Find the diagnoses and demographics that drive cost
- Assess payer contributions across procedure types
- Analyze encounter duration by organization and encounter class
- Build a KPI dashboard for ongoing monitoring

## Current Progress

### SQL

- ✅ Database setup
- ✅ Data cleaning and validation
- ✅ Uncovered cost analysis
- ✅ High-cost patient analysis
- ✅ Risk factors by demographics and reason code
- ✅ Payer contribution by procedure
- ✅ Encounter duration analysis

### Power BI

- ✅ Dashboard developed (see below)
- 🚧 Business insights documentation

## Data Model

| Table | Purpose |
|---|---|
| `Encounters` | Visits with class, dates, payer, reason code, base cost, total claim cost and payer coverage |
| `Patients` | Demographics: gender, race, ethnicity, marital status, city |
| `Procedures` | Procedures performed per encounter, with base cost |
| `Payers` | Insurance payers |
| `Organizations` | Healthcare organizations |

## SQL Analysis

| Section | Focus |
|---|---|
| 1–2 | Database setup and data cleaning: row counts, data types, `START`/`STOP` → `DATETIME2`, cost columns → `DECIMAL(18,2)`, nulls, duplicates, negative values, coverage above claim cost, invalid dates |
| 3 | Uncovered cost per encounter and by reason code |
| 4–6 | Patients table exploration, joins, uncovered cost by reason code and gender |
| 7 | Patients with more than 3 encounters over $10,000 in a year |
| 8 | Risk factors: top reason codes and demographic breakdown of high-cost encounters |
| 9 | Payer contributions: base cost, coverage and gap by procedure and payer |
| 10 | Patients with repeat procedures for the same reason code |
| 11 | Average encounter duration and encounters over 24 hours, by organization and class |

### SQL Topics Covered

- SELECT, WHERE, ORDER BY
- GROUP BY, HAVING
- INNER JOIN, LEFT JOIN
- Aggregate functions (COUNT, SUM, AVG)
- Date functions (YEAR, DATEDIFF)
- CASE expressions
- Subqueries
- Data type conversion (CAST, ALTER COLUMN)
- Data quality checks (nulls, duplicates, orphaned records, logical consistency)
- Business KPI queries

## Power BI Dashboard

**Patient Encounter Cost and Risk Analysis in Healthcare Systems**

The dashboard includes:

- Encounter cost distribution by encounter class (average, maximum and minimum claim and base cost)
- High-cost patient identification (top 10% share of total cost)
- Total cost and encounter count per patient
- Covered vs uncovered cost by payer
- Uncovered cost by reason description
- Average procedure cost trend over time
- Average procedure cost by diagnosis
- Patient traffic and average encounter cost by city

## Repository Structure

```
healthcare-financial-risk-analysis/
│
├── README.md
├── sql/
│   └── healthcare_financial_risk_analysis.sql
└── powerbi/
    └── Healthcare_Dashboard.pbix
```

## How to Use

1. Load the source tables into SQL Server.
2. Run the script in `sql/` section by section.
3. Open the `.pbix` file in Power BI Desktop and update the data source if needed.

## Upcoming Updates

- Business insights documentation
- Advanced SQL (CTEs, window functions)
- Dashboard screenshots
- Performance optimization

## About

Designed a SQL-based healthcare analytics project using joins, subqueries, aggregations and date functions to evaluate uncovered costs, high-cost patients, payer contributions and encounter duration, with a Power BI dashboard for monitoring.

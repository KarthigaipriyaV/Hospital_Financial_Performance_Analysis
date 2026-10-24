# Hospital_Financial_Performance_Analysis
Healthcare financial risk analysis using SQL Server and Power BI. Uncovers uncovered costs, high-cost patients, risk factors and payer contributions across encounters.
# 🏥 Healthcare Financial Risk Analysis

Analyzing healthcare encounter, patient, procedure and payer data to uncover financial risk, using SQL Server and Power BI.

---

## 📌 Objective

Evaluate financial risk by identifying uncovered costs, high-cost patients, key risk factors and payer contributions across healthcare encounters.

## 🛠 Tech Stack

| Category | Tools |
|---|---|
| Database | SQL Server (T-SQL) |
| Visualization | Power BI |

## 📁 Repository Structure

```
healthcare-financial-risk-analysis/
├── sql/
│   └── healthcare_financial_risk_analysis.sql   # Cleaning + analysis queries
├── powerbi/
│   └── Healthcare_Dashboard.pbix                # Power BI dashboard
├── .gitignore
└── README.md
```

---

## 🗄 SQL Analysis

Database: `Healthcare_Financial_risk` (tables: `Encounters`, `Patients`, `Procedures`, `Payers`, `Organizations`)

| Section | What it does |
|---|---|
| 1–2. Setup & cleaning | Row counts, data types, `START`/`STOP` → `DATETIME2`, cost columns → `DECIMAL(18,2)`, null counts, duplicates, negative values, coverage > claim cost, invalid dates |
| 3. Uncovered cost | `TOTAL_CLAIM_COST - PAYER_COVERAGE` per encounter and by reason code |
| 4–6. Demographics | Joins encounters with patients; uncovered cost by reason code and gender |
| 7. High-cost patients | Patients with more than 3 encounters over $10,000 in a year |
| 8. Risk factors | Top reason codes and demographic breakdown of high-cost encounters |
| 9. Payer contributions | Procedure base cost, payer coverage and gap by procedure and payer name |
| 10. Repeat procedures | Patients with the same reason code across multiple encounters |
| 11. Encounter duration | Average duration and encounters over 24 hours by organization and class |

> Run the script against SQL Server (uses `TOP`, `DATEDIFF`, `INFORMATION_SCHEMA`). Load the source tables before running.

---

## 📊 Power BI Dashboard

Open with Power BI Desktop to explore the dashboard. If it connects to a live SQL Server source, update the data source settings first.

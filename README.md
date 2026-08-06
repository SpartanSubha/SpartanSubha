<div align="center">

# Hey, I'm Subhabrata 👋

### Business Analyst · Data Analyst · Turning Messy Data into Clear Decisions

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/subhabrata99)
[![Email](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:kitusahoo@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/SpartanSubha)

</div>

---

## 🧠 My Story

Most people learn analytics through courses.
I learned it **while running real business operations.**

> Managing 100+ OYO properties and ₹10M+ revenue didn't just teach me operations —
> it taught me that **bad data costs money, and good analysis saves it.**

Somewhere between SQL queries, Power BI dashboards, and late-night business reviews, I made a decision:

> **I don't just want to run operations. I want to solve business problems using data.**

That's what this profile is about.

---

## 🏆 Real Impact (Not Just Projects)

| Metric | Result |
|---|---|
| 🥇 Regional Rank | **#1 among 50+ managers** |
| 📊 KPI Achievement | **404% of targets** |
| 🤝 Partner Retention | **72% → 87%** |
| ⏱️ Issue Resolution | **20% faster (48 → 38 hrs)** |
| 💰 Cost Reduction | **15% operational cost savings** |
| 📦 Portfolio Managed | **1,500+ properties, ₹10M+ revenue** |

---

## 🚀 Featured Projects

---

### 💻 1. Apple Retail Store — SQL Analysis Project

> **Business Problem:** With 75 global stores and 1M+ transactions, Apple's retail operations generate enormous data — but without proper querying infrastructure, answering even basic business questions takes minutes. The challenge: build a clean, optimized SQL foundation from scratch and extract actionable insights from raw, uncleaned data.

[![GitHub Repo](https://img.shields.io/badge/GitHub-View%20Repo-181717?style=flat-square&logo=github)](https://github.com/SpartanSubha/Apple-Retail-Store-SQL-Analysis)

**What I Built:**
An end-to-end SQL analytics project on **1,040,201 sales transactions** across **75 stores in 20+ countries** — covering database design, bulk data import, index-based performance optimization, business-rule-driven data cleaning, and 23 advanced SQL queries.

**Key Findings:**
- Identified and removed **493,143 invalid sales records** (sold before product launch) and **2,511 impossible warranty claims** (claimed before purchase) — using cascading deletes to preserve referential integrity
- Discovered **hidden \r\n characters** in `repair_status` silently corrupting all `GROUP BY` aggregations — fixed with `REPLACE()` before any analysis was run
- Query performance improved by **34–70%** across all major query patterns using targeted indexes and virtual computed columns — date range queries improved by **95%** over function-based filtering
- Warranty claim probability varies significantly by country — surfacing geographic risk concentration
- Products in the **medium price band ($750–$1,500)** generate the highest warranty claim volume — not the most expensive segment
- Year-over-year growth ratios per store (via `LAG` window function) revealed which locations are scaling vs. plateauing

**Architecture:**

| Layer | Approach | Detail |
|---|---|---|
| Database Design | Normalized schema | 5 tables, PKs, FKs, referential integrity enforced |
| Import | `LOAD DATA LOCAL INFILE` | FK checks disabled during load, re-enabled after |
| Performance | `EXPLAIN ANALYZE` + Indexes | 5 single-column + 4 composite indexes + virtual columns |
| Data Cleaning | Business rule validation | Audit-first: detect → cascade delete → validate |
| Analysis | 23 SQL queries | Easy / Medium / Advanced tiers |

**ERR Diagram:**

<img width="1116" height="573" alt="ERR Diagram" src="https://github.com/user-attachments/assets/16a8c3cd-2f8b-430b-ac5d-6f800f520710" />


**SQL Concepts Used:**
- Window Functions: `RANK()`, `DENSE_RANK()`, `LAG()`, Running `SUM() OVER()`
- CTEs (`WITH` clause) for multi-step analytical queries
- `TIMESTAMPDIFF`, `DATEDIFF`, `DATE_FORMAT` for lifecycle and trend analysis
- `CASE` logic for price segmentation and conditional aggregation
- `NOT EXISTS` for anti-join patterns

`MySQL` `CTE` `Window Functions` `Indexing` `EXPLAIN ANALYZE` `Data Cleaning` `Aggregation` `Subqueries`

---

### 🏦 2. Aurora Bank — Customer Risk & Spend Intelligence

> **Business Problem:** Aurora Bank had no systematic way to flag at-risk customers before problems surfaced. Rising personal debt levels were increasing default exposure — but the risk team couldn't see *who* was at risk, *how* they were spending, or *what* the early behavioral signals looked like.

[![GitHub Repo](https://img.shields.io/badge/GitHub-View%20Repo-181717?style=flat-square&logo=github)](https://github.com/SpartanSubha/Aurora-Bank-Customer-Risk-Spend-Intelligence)
[![Live Dashboard](https://img.shields.io/badge/Power%20BI-Live%20Dashboard-F2C811?style=flat-square&logo=powerbi&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiYWQzNzExMWYtMzVlNy00NzBiLWFhNjUtMTEyYzM2YTQ1YzJhIiwidCI6IjQyZjRkOWVkLTBiYmItNGU5NS1hYmRjLTM5OGM1M2QzNjkxZCJ9&pageName=9e32f33b4754dab4d229)

**What I Built:**
An end-to-end analytics solution across **157,224 transactions and 2,000 customers** — from raw data engineering in Python through to a multi-role Power BI dashboard with Row Level Security.

**Key Findings:**
- **22% of customers (440/2,000) classified as High Risk** — collectively carrying $22M in debt exposure
- Average DTI ratio: **139.36%** — with some customers carrying debt nearly **5× their annual income**
- **70.3% of customers fall in the Low income band** — the majority of the portfolio is financially vulnerable by income alone
- **Insufficient Balance** is the dominant transaction error type — signaling genuine financial stress, not fraud
- **Mastercard carries disproportionate risk** — highest credit limit exposure ($47M) + highest share of failed transactions (49.96%)
- **71.3% of transactions are online** — card-not-present, aligning with missing merchant location data confirmed during cleaning

**Architecture:**

| Layer | Tool | Purpose |
|---|---|---|
| Data Engineering | Python (Pandas) | Currency string cleaning, corruption investigation, null classification |
| Data Model | Star Schema (4 tables) | `TransactionData` fact + `UsersData`, `CardsData`, `MccData` dimensions |
| BI & Governance | Power BI + DAX + RLS | KPI measures, risk segmentation, 3-role access control |

**Row Level Security — 3 Roles:**
- **Executive** → Full portfolio view
- **Risk Analyst** → High-risk customers only
- **Relationship Manager** → Low and Medium risk customers only

<img width="8000" height="4564" alt="image" src="https://github.com/user-attachments/assets/808991d7-f911-4f2e-803b-155af55bade6" />


`Python` `Pandas` `Power BI` `DAX` `MySQL` `Star Schema` `Row Level Security` `Risk Analytics`

---

### 📊 3. E-Commerce User Journey Funnel & Revenue Leakage Analysis

> **Business Problem:** An e-commerce platform's revenue was underperforming — but no one knew *where* in the funnel customers were dropping off, or *how much* it was costing the business at each stage.

[![GitHub Repo](https://img.shields.io/badge/GitHub-View%20Repo-181717?style=flat-square&logo=github)](https://github.com/SpartanSubha/E-Commerce-User-Journey-Funnel-Revenue-Leakage-Analysis)
[![Live Dashboard](https://img.shields.io/badge/Power%20BI-Live%20Dashboard-F2C811?style=flat-square&logo=powerbi&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiNzBlZWUwMTMtMDkwMS00ZTZlLWFmNGMtMjk3YTViYjlkNzM0IiwidCI6IjQyZjRkOWVkLTBiYmItNGU5NS1hYmRjLTM5OGM1M2QzNjkxZCJ9)

**What I Built:**
Analyzed **10,000 users** across the full purchase funnel — Browse → Add to Cart → Checkout → Purchase — quantifying revenue leakage at every stage and building a live scenario simulator for business planning.

**Key Findings:**
- Only **10.04%** of visitors completed a purchase — well below industry benchmarks
- **Cart → Checkout is the single biggest leak:** ~₹9.64L lost at this one stage alone
- **Mobile** converts at just **9.47%** — a UX problem, not a traffic problem
- **Organic traffic** converts at just **9.45%** — landing page relevance likely the culprit
- **South region** leads in geographic revenue leakage
- **Total revenue leakage identified: ₹24.8 Lakhs**

**Dashboard — 4 Pages:**

| Page | Business Question |
|---|---|
| Executive Overview | What's the health of our funnel? |
| Funnel Leakage Diagnostics | Who's dropping off, and where? |
| Revenue Opportunity Simulator | What's the upside if we fix this? (1–20% What-If) |
| Strategic Recommendations | What should we actually do — mapped by Impact vs Effort? |

<img width="1593" height="898" alt="image" src="https://github.com/user-attachments/assets/e19bb0bd-9161-460d-9d65-3e062dfc0e09" />


`Power BI` `DAX` `What-If Analysis` `Funnel Analytics` `KPI Design` `Executive Reporting`

---

### 📦 4. Global Freight Cost Intelligence Dashboard

> **Business Problem:** Sea and air freight costs surged 36% post-COVID. Leadership needed to understand whether this was a temporary spike or a structural shift — and what it meant for margins.

[![GitHub Repo](https://img.shields.io/badge/GitHub-View%20Repo-181717?style=flat-square&logo=github)](https://github.com/SpartanSubha/Profit-Impact-of-Freight-Cost-Surge)

**What I Built:**
An end-to-end BI pipeline ingesting **20+ years of sea and air freight data** via the FRED API, modeled in Power Query, and delivered as an executive-ready strategic planning report with scenario modeling.

**Key Findings:**
- **36% structural freight cost shift** above pre-COVID baselines — not a temporary spike
- Air freight is **~87% higher in cost** relative to sea freight trends during shock periods
- **Margin compressed from 20% → 7.65%** — a 60% compression — for affected product categories
- Delivered scenario modeling to support pricing strategy and supplier renegotiation decisions

**Dashboard Includes:**
- Historical freight trend analysis — sea vs air, 20+ years
- Cost escalation vs 2019 baseline (MoM volatility mapped)
- Margin impact calculator by product category
- Executive strategic planning report with action recommendations

<img width="1862" height="775" alt="image" src="https://github.com/user-attachments/assets/e896a2a3-bad4-4b00-94fd-5e911d5ff48a" />


`Excel` `Power Query` `FRED API` `Pivot Tables` `Business Scenario Modeling` `SCM Analytics`

---

## 🛠️ Tech Stack

### 📊 Analytics & BI
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

### 🗄️ Data & Databases
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)

### ⚙️ Tools & Platforms
![Odoo](https://img.shields.io/badge/Odoo%20ERP-714B67?style=for-the-badge&logo=odoo&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

### 🧠 Business & Analytics Skills
![KPI Design](https://img.shields.io/badge/KPI%20Design-1F4E79?style=for-the-badge)
![Funnel Analysis](https://img.shields.io/badge/Funnel%20Analysis-1F4E79?style=for-the-badge)
![Revenue Analytics](https://img.shields.io/badge/Revenue%20Analytics-1F4E79?style=for-the-badge)
![Risk Analytics](https://img.shields.io/badge/Risk%20Analytics-1F4E79?style=for-the-badge)
![Data Modeling](https://img.shields.io/badge/Data%20Modeling-1F4E79?style=for-the-badge)
![Row Level Security](https://img.shields.io/badge/Row%20Level%20Security-1F4E79?style=for-the-badge)
![Stakeholder Reporting](https://img.shields.io/badge/Stakeholder%20Reporting-1F4E79?style=for-the-badge)
![Supply Chain Analytics](https://img.shields.io/badge/Supply%20Chain%20Analytics-1F4E79?style=for-the-badge)
![Business Storytelling](https://img.shields.io/badge/Business%20Storytelling-1F4E79?style=for-the-badge)
![Process Improvement](https://img.shields.io/badge/Process%20Improvement-1F4E79?style=for-the-badge)

---

## 🌱 Currently Building

| Project | What I'm Learning |
|---|---|
| 📐 Advanced SQL | Window functions · recursive CTEs · query optimization |
| 🐍 Python depth | NumPy · statistical analysis · automation scripting |
| 🧩 Case frameworks | Consulting-style structured problem solving |

---

## 🤝 Let's Connect

If you're here because you're looking for someone who understands **both business and data** — you're in the right place.

[![LinkedIn](https://img.shields.io/badge/Connect%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/subhabrata99)
[![Email](https://img.shields.io/badge/Send%20an%20Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:kitusahoo@gmail.com)

---

<div align="center">

*⭐ Data is only useful when it drives action. Let's build something that does.*

</div>

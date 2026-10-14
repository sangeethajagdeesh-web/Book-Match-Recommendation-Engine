# Book-Match-Recommendation-Engine
Personalised book recommendation engine built using Excel, Python, MySQL and Power BI

A full-stack data analytics project that processes 433K+ book ratings from 77K+ users to deliver personalised book recommendations — built using Excel, Python, MySQL, Power BI, Databricks (PySpark), and Google BigQuery.

---

## Dashboard Preview

### Page 1 — Overview
![Overview](Screenshots/Overview.PNG)

### Page 2 — Book Analytics
![Book_Analytics](Screenshots/Book_Analytics.PNG)

### Page 3 — Personalised Picks
![Personalized_Picks](Screenshots/Personalized_Picks.PNG)

---

## Tools Used

- **Microsoft Excel** — Raw data cleaning and standardisation
- **Python** (pandas, SQLAlchemy, PyMySQL) — ETL pipeline and MySQL import automation
- **MySQL 8.0** — Relational database design and SQL query development
- **Power BI Desktop + DAX** — 3-page interactive dashboard and custom measures
- **Databricks (PySpark)** — Large-scale data reprocessing and anomaly validation
- **Google BigQuery** — Cloud data warehouse migration and cross-platform query validation

---

## Project Scale

- Total Books — 2,71,030
- Total Users — 2,77,611
- Total Ratings Processed — 4,33,671
- Dashboard Pages — 3
- Custom DAX Measures — 8
- Invalid Records Removed — 7,16,109 (62% of raw dataset)

---

## Project Workflow

**Step 1 — Excel:** Cleaned raw Kaggle CSV files — fixed ISBN encoding, removed duplicates, standardised text using TRIM and PROPER, resolved UTF-8 character corruption in author and publisher names

**Step 2 — Python:** Built an ETL pipeline using pandas and SQLAlchemy to clean and import all three datasets into MySQL — removed 700K placeholder zero ratings, fixed column names, handled BOM encoding errors, used chunked batch insertion for large files

**Step 3 — MySQL:** Designed a 3-table relational schema (Books, Users, Ratings) and wrote 11 SQL queries using INNER JOIN, LEFT JOIN, GROUP BY, HAVING, and subqueries to extract analytical insights and power the recommendation engine

**Step 4 — Power BI:** Built a 3-page interactive dashboard with 8 custom DAX measures, conditional formatting, gradient colour scales, page navigation buttons, and a dynamic User ID slicer for personalised recommendations

**Step 5 — Databricks:** Reprocessed the 4,33,671-row ratings dataset using PySpark to replicate distribution and anomaly analysis — validated 100% consistency with 
original Pandas-based results

**Step 6 — BigQuery:** Migrated the ratings dataset to Google BigQuery and validated core aggregation and join queries — confirmed identical results to on-prem MySQL across row counts, averages, distribution, and active user metrics

---

## Dashboard Pages

Page 1 — Overview
Shows 4 KPI cards (Active Users, Total Ratings, Best Rating, Average Rating), Top User Location bar chart, Publisher Market Share donut chart, and Books Published by Year area chart 

Page 2 — Book Analytics Detailed View
Shows Most Rated Authors bar chart, Top Rated Books matrix table with green conditional formatting, Most Popular Books treemap, and Rating Distribution column chart with red-to-green gradient

Page 3 — Personalised Picks
Shows a User ID dropdown slicer — selecting any user instantly displays their Books Rated, Average Rating, Rater Type (Balanced / Generous / Strict), User Rank, Top 10 Recommended Books table, Top Recommended Authors, and Top Recommended Publishers

---

## Key Features

- Dynamic User ID slicer — select any user to instantly see their personalised top 10 book recommendations
- Rater Type classification — DAX nested IF automatically classifies each user as Balanced, Generous, or Strict
- User Rank — every user ranked by total books rated using RANKX
- Community-based recommendation logic — recommends books the user has NOT yet read, ranked by community average rating
- Page navigation buttons — seamless switching between all 3 report pages
- PySpark validation — distribution and anomaly analysis rerun in Databricks, confirming 100% consistency with Pandas results
- BigQuery portability — all core queries validated in Google BigQuery, confirming cross-platform compatibility

---

## Cloud Extensions

### Databricks — PySpark Validation
Reprocessed the 4,33,671-row ratings dataset in Databricks using PySpark to replicate distribution and anomaly analysis — validated 100% row count and average rating consistency with original Pandas-based results.

**Results:**
- Total records loaded: 4,33,671 ✅
- Anomalies outside 1–10 rating range: 0 ✅
- Null values: 0 ✅
- PySpark avg rating: 7.6 — matches Pandas result ✅
- Match: True ✅

Full notebook with all cell outputs:
[BookMatch_PySpark_Analysis.ipynb](Cloud_Extensions/Databricks/BookMatch_PySpark_Analysis.ipynb)

### Validation Match
![PySpark Validation](Cloud_Extensions/Databricks/pyspark_validation_match.png)

### Google BigQuery — Cross-Platform Migration
Migrated the ratings dataset to Google BigQuery and validated core aggregation and join queries for cross-platform portability — confirmed identical results to on-prem MySQL across row counts, averages, distribution, and active user metrics.

**Results:**
- Total records: 4,33,671 — matches MySQL ✅
- Overall average rating: 7.6 — matches MySQL ✅
- Rating distribution: identical pattern to MySQL results ✅
- Active user rankings: consistent with MySQL query output ✅

### Row Count
![BigQuery Row Count](Cloud_Extensions/BigQuery/bigquery_row_count.png)

### Distribution
![BigQuery Distribution](Cloud_Extensions/BigQuery/bigquery_distribution.png)

### Active Users
![BigQuery Active Users](Cloud_Extensions/BigQuery/bigquery_active_users.png)

### Consistency Check
![BigQuery Consistency](Cloud_Extensions/BigQuery/bigquery_consistency_check.png)

## Files in This Repository

- **Python** — Jupyter notebook for data cleaning and MySQL import
- **SQL** — BookMatch_Queries.sql with all 11 analytical queries
- **Screenshots** — PNG images of all 3 dashboard pages
- **Cloud_Extensions/Databricks** — PySpark notebook (with full cell outputs) and consistency validation screenshot
- **Cloud_Extensions/BigQuery** — Query result screenshots validating cross-platform consistency

---

## Certification

Microsoft Certified: Power BI Data Analyst Associate — Exam PL-300


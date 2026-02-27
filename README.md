# 📊 Sales Performance Analytics

> **Data-driven sales performance analysis using Python | KPI calculation, data cleaning, trend analysis, and interactive dashboards for business development decision-making.**


---

## 📌 Project Overview

This project was completed as a **3-day Data Science Internship Task** focused on KPI-based business development analysis. The goal was to take a raw, uncleaned sales dataset, process it, calculate key performance indicators, visualize trends, and generate actionable business recommendations.

The analysis covers **683 leads** across **5 lead sources**, **5 regions**, and **6 sales representatives** over an **18-month period (January 2023 – June 2024)**.

---

## 🎯 Objectives

- Clean and preprocess a raw, messy business development dataset
- Define and calculate 6 key KPIs relevant to sales performance
- Identify trends, gaps, and performance bottlenecks
- Provide actionable insights backed by data
- Visualize KPI performance using Python charts and Power BI dashboard

---

## 📁 Repository Structure

```
sales-performance-analytics/
│
├── data/
│   ├── raw/
│   │   └── BD_KPI_Raw_Dataset.csv          ← Original uncleaned dataset (700 records)
│   └── cleaned/
│       └── BD_KPI_Cleaned_Dataset.csv       ← Cleaned dataset (683 records, 13 columns)
│
├── notebooks/
│   ├── Day1_Data_Cleaning.ipynb             ← Data cleaning & KPI identification
│   ├── Day2_KPI_Calculation.ipynb           ← KPI calculation & visualization
│   └── Day3_Insights_Report.ipynb           ← Insight generation & recommendations
│
├── reports/
│   ├── KPI1_Lead_Conversion_Rate.png
│   ├── KPI2_CAC.png
│   ├── KPI3_Revenue_Per_Client.png
│   ├── KPI4_Monthly_Growth_Rate.png
│   ├── KPI5_Sales_Cycle_Duration.png
│   ├── KPI6_Lead_Source_Performance.png
│   ├── Insight1_Conversion_Rate.png
│   ├── Insight2_Lead_Source_Performance.png
│   ├── Insight3_CAC_Analysis.png
│   ├── Insight4_Sales_Rep_Performance.png
│   ├── Insight5_Revenue_Trend.png
│   ├── Insight6_Cycle_vs_Conversion.png
│   ├── Insight7_Regional_Performance.png
│   └── Sales_Performance_KPI_Report.docx   ← Final summary report
│
├── dashboard/
│   └── Sales_Performance_Dashboard.pbix    ← Power BI dashboard file
│
└── README.md
```

---

## 🗓️ Project Timeline

| Day | Task | Status |
|-----|------|--------|
| Day 1 | Data Cleaning & KPI Identification | ✅ Complete |
| Day 2 | KPI Calculation & Visualization | ✅ Complete |
| Day 3 | Insight Generation & Final Report | ✅ Complete |

---

## 📦 Dataset Overview

### Raw Dataset
- **File:** `data/raw/BD_KPI_Raw_Dataset.csv`
- **Records:** 700 rows × 9 columns
- **Issues:** Duplicate rows, mixed date formats, inconsistent casing, missing values, invalid revenue entries, ambiguous status labels

### Dataset Fields

| Field | Description |
|-------|-------------|
| `Lead_ID` | Unique identifier for each lead |
| `Lead_Source` | Origin channel (Social Media, Referral, Website, Email Campaign, Direct) |
| `Lead_Date` | Date the lead was generated |
| `Conversion_Status` | Converted / Not Converted |
| `Conversion_Date` | Date of conversion (converted leads only) |
| `Revenue_Value` | Revenue generated from the lead ($) |
| `Marketing_Cost` | Marketing spend attributed to the lead ($) |
| `Sales_Representative` | Assigned sales representative |
| `Region` | Geographic region (North, South, East, West) |

### Cleaned Dataset
- **File:** `data/cleaned/BD_KPI_Cleaned_Dataset.csv`
- **Records:** 683 rows × 13 columns
- **Added Columns:** `Sales_Cycle_Days`, `Lead_Month`, `Lead_Year`, `Is_Converted`

---

## 🧹 Day 1 — Data Cleaning Summary

| Issue | Records Affected | Action Taken |
|-------|-----------------|--------------|
| Duplicate rows | 17 | Removed |
| Missing Lead_IDs | 10 | Auto-generated sequential IDs |
| Inconsistent Lead_Source casing | 14 variants | Standardized to Title Case |
| Mixed date formats | 5 different formats | Parsed to YYYY-MM-DD |
| Ambiguous Conversion_Status | 10 variants | Mapped to Converted / Not Converted |
| Invalid Conversion Dates | 17 records | Set to NaT |
| Revenue with $ symbols / zero | Multiple | Stripped symbols; replaced with median |
| Missing Marketing_Cost | 18 records | Imputed with median ($2,639.44) |
| Inconsistent Region / Rep casing | Multiple | Standardized to Title Case |
| Missing Sales Representative | 130 records | Filled as 'Unassigned' |
| Missing Region | 82 records | Filled as 'Unknown' |

---

## 📈 Day 2 — KPI Results

| KPI | Formula | Result |
|-----|---------|--------|
| **Lead Conversion Rate** | (Converted ÷ Total Leads) × 100 | **39.82%** |
| **Customer Acquisition Cost** | Total Marketing Cost ÷ Converted Leads | **$6,506.17** |
| **Revenue per Client** | Total Revenue ÷ Converted Leads | **$24,790.74** |
| **Avg Monthly Lead Growth** | MoM % change in lead volume | **3.63%** |
| **Avg Monthly Revenue Growth** | MoM % change in revenue | **8.83%** |
| **Avg Sales Cycle Duration** | Avg(Conversion Date − Lead Date) | **67.7 days** |

### Lead Source Performance Summary

| Lead Source | Total Leads | Converted | Conv. Rate | CAC | ROI % |
|-------------|-------------|-----------|------------|-----|-------|
| Website | 98 | 47 | 47.96% ⭐ | $5,438 ⭐ | 341.02% ⭐ |
| Social Media | 151 | 69 | 45.70% | $5,698 | 340.81% |
| Direct | 143 | 59 | 41.26% | $6,005 | 304.40% |
| Referral | 99 | 36 | 36.36% | $7,301 | 236.51% |
| Email Campaign | 154 | 51 | 33.12% | $7,973 | 217.77% |
| Unknown | 38 | 10 | 26.32% | $9,716 | 181.36% |

---

## 💡 Day 3 — Key Business Insights

1. **Conversion Rate Below Benchmark** — At 39.82%, the rate falls short of the 45–55% industry standard. Improving to 50% would yield ~69 additional conversions worth **$1.71M**.

2. **Website & Social Media Are Top Channels** — Website delivers the best conversion rate (47.96%), lowest CAC ($5,438), and highest ROI (341%) despite being the lowest-volume source. Email Campaign (highest volume) underperforms significantly.

3. **CAC Is High But ROI Is Positive** — Overall ROI of 281% is healthy (3.8x revenue-to-CAC ratio), but East region's CAC ($7,569) is 35.7% higher than North ($5,576), indicating inefficient spend.

4. **Sales Rep Speed vs Value Tradeoff** — Frank Miller generates the highest revenue per client ($28,896) but takes longest to close (75 days). Carol White closes fastest (58.2 days). 50 unassigned leads represent **$410,741** in recoverable revenue.

5. **Revenue Is Highly Volatile** — Month-over-month swings of 50–140% indicate an unstable pipeline. Best month (May 2023: $580K) was 223.7% higher than worst month (Jan 2024: $179K).

6. **Fastest Cycle ≠ Best Conversion** — Email Campaign closes in 57.8 days (fastest) but converts at only 33.12%. Website takes 78.1 days (slowest) but achieves 47.96% conversion and 341% ROI.

7. **North Region Outperforms East** — North leads all regions with 44.32% conversion and $5,576 CAC. East has the lowest conversion (34.97%) and highest CAC ($7,569), representing a **$619,768** revenue gap.

---

## ✅ Recommendations

| # | Recommendation | Priority | Expected Impact |
|---|----------------|----------|-----------------|
| 1 | Implement lead scoring to boost conversion rate to 45%+ | 🔴 High | +$1.71M revenue |
| 2 | Reallocate 20–30% of Email Campaign budget to Website/Social Media | 🔴 High | Higher ROI on spend |
| 3 | Investigate & reduce East region CAC using North region strategies | 🟡 Medium | Save ~$113K on acquisitions |
| 4 | Assign all 50 unassigned leads to top performers immediately | 🔴 High | Recover ~$410K revenue |
| 5 | Set monthly quotas & pipeline reviews to stabilize revenue | 🟡 Medium | Reduce MoM volatility |
| 6 | Blended sales training combining Carol's speed + Frank's deal value | 🟡 Medium | Improve team-wide metrics |
| 7 | Scale Website lead generation (SEO, landing pages) | 🔴 High | Best ROI channel (341%) |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Python 3.8+** | Data processing and KPI calculation |
| **Pandas** | Data cleaning and transformation |
| **NumPy** | Numerical computations |
| **Matplotlib & Seaborn** | Data visualization and chart generation |
| **Jupyter Notebook** | Interactive analysis environment |
| **Power BI Desktop** | Interactive KPI dashboard |
| **GitHub** | Version control and project hosting |

---

## ⚙️ How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/nisansalasandu/sales-performance-analytics.git
cd sales-performance-analytics
```

### 2. Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn jupyter openpyxl
```

### 3. Launch Jupyter Notebook
```bash
jupyter notebook
```

### 4. Run Notebooks in Order
```
notebooks/Day1_Data_Cleaning.ipynb      → Run first
notebooks/Day2_KPI_Calculation.ipynb    → Run second
notebooks/Day3_Insights_Report.ipynb    → Run third
```

### 5. Open Power BI Dashboard
Open `dashboard/Sales_Performance_Dashboard.pbix` in Power BI Desktop and connect to `data/cleaned/BD_KPI_Cleaned_Dataset.csv`

---

## 📊 Dashboard Preview

The Power BI dashboard consists of 2 interactive pages:

**Page 1 — KPI Overview**
- 6 KPI Cards (Total Leads, Converted Leads, Conversion Rate, Revenue, CAC, Revenue per Client)
- Conversion split donut chart
- Conversion rate by lead source
- Revenue and CAC comparisons

**Page 2 — Trends & Analysis**
- Monthly lead volume and revenue trends
- Month-over-month growth rate
- Sales cycle duration by source
- Regional performance breakdown
- Full lead source performance table

> Slicers: Date Range | Region | Lead Source — all synced across both pages

---

## 📄 Deliverables

- [x] Raw dataset (700 records) — `data/raw/`
- [x] Cleaned dataset (683 records) — `data/cleaned/`
- [x] Day 1 notebook — Data Cleaning & KPI Identification
- [x] Day 2 notebook — KPI Calculation & Visualization
- [x] Day 3 notebook — Insights & Recommendations
- [x] 13 visualization charts — `reports/`
- [x] Power BI dashboard (2 pages) — `dashboard/`
- [x] Final summary report (Word) — `reports/`

---

## 👤 Author

**Nisansala Ruwan Pathirana**
- GitHub: [nisansalasandu](https://github.com/nisansalasandu)

---

## 📝 License

This project was completed as part of a Data Science Internship task. For educational and portfolio purposes only.

---

*Analyzed 683 leads | $6.74M Total Revenue | 18-month period | January 2023 – June 2024*

# 📊 Business-Insights-360-Dashboard
End-to-end Power BI dashboard designed to analyze sales, finance, marketing, and supply chain data, enabling data-driven decision-making through interactive visualizations and key performance insights.

## 📁 Quick Access

| Resource | Link |
|----------|------|
| 📄 Full Dashboard PDF | [View PDF](attached in repo) |
| 🎥 Video Walkthrough | *Coming soon* |



## 🏢 Project Background

AtliQ Hardware is a fast-growing global electronics manufacturer selling Notebooks, Accessories, Peripherals, Desktops, Networking devices, and Storage products — through Retailers, Direct, and Distributor channels across APAC, EU, NA, and LATAM.

As the company scaled rapidly, leadership faced a critical problem: **decisions were being made on gut feeling and scattered Excel reports**, with no unified view of performance across departments.

This project simulates the role of a **junior Data Analyst** tasked with building a single, unified analytics platform — empowering every function from Finance to the C-Suite to make confident, data-driven decisions.

> 🎓 Built as part of the **Codebasics Data Analytics Bootcamp**

---

## 🎯 Problem Statement

> *"AtliQ Hardware's leadership could not get a clear, real-time picture of how the business was performing — across regions, customers, products, and time periods — leading to reactive rather than proactive decision-making."*

**Goals of this dashboard:**
- Replace siloed Excel reporting with a single Power BI platform
- Enable comparison of performance vs Last Year (LY) and vs Targets
- Surface critical risks in Supply Chain before they impact revenue
- Give the C-Suite a one-page executive summary of business health

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Dashboard design, data modelling, report building |
| **SQL** | Data extraction, joins, and transformation from source tables |
| **DAX** | All KPI measures and calculated columns |
| **Power Query (M)** | Data cleaning, shaping, and loading |
| **Data Modelling** | Star schema design connecting fact and dimension tables |

---

## 📐 DAX Measures Built

This dashboard required building a comprehensive library of DAX measures. Below are the key measures powering the dashboard:

### 💰 Financial Measures
```dax
Gross Margin % 

Net Profit % 

Net Sales

Gross Margin 
```

### 📅 Year-over-Year & Benchmark Comparisons

-- YoY Change %
-- vs Benchmark


### 🎯 Target vs Actual
```

### 🚚 Supply Chain Measures
```dax
Forecast Accuracy % 

Net Error 
Net Error % 

Absolute Error % 
```

### 📈 Market Share
---

## 📋 Dashboard Pages — Detailed Walkthrough

---

### 🏠 Page 1: Home

![Home View](screenshots/Home.png)

**Purpose:** Central navigation hub — the first thing any user sees.

**Visuals on this page:**
- Navigation icons linking to each of the 5 views (Finance, Sales, Marketing, Supply Chain, Executive)
- Company logo and dashboard title
- Last Refresh Date stamp — so users always know how current the data is

**Design decision:** Kept intentionally minimal so users can orient themselves quickly and navigate to their relevant view without cognitive overload.

---

### 💰 Page 2: Finance View

![Finance View](screenshots/Finance View.png)

**Purpose:** Give Finance teams and leadership a complete picture of revenue, costs, and profitability — sliceable by customer, region, segment, and year.

**Visuals on this page:**

| Visual | What it shows |
|--------|--------------|
| **KPI Cards** | Net Sales ($823.85M), Gross Margin % (35.87%), Net Profit % (-12%) vs Benchmark and Target |
| **P&L Statement Table** | Full waterfall from Gross Sales → Pre Invoice Deductions → Net Invoice Sales → Post Discounts → Net Sales → COGS → Gross Margin → Operating Expenses → Net Profit |
| **Net Sales Performance Line Chart** | Monthly trend of Selected Year vs Benchmark, Sep 2020 – Aug 2021 |
| **Market P&L Table** | Country-wise P&L Values and Chg% (Australia, Austria, Bangladesh, Brazil, Canada, China...) |
| **Region P&L Table** | APAC ($441.98M), EU ($200.77M), NA ($177.94M), LATAM ($3.16M) |

**DAX measures powering this page:**
`Net Sales` · `Gross Margin %` · `Net Profit %` · `NS $ LY` · `NS YoY Chg %` · `BM Chg %` · `GM % vs Target` · `NP % vs Target`

**Key Insight:**
> Net Sales exploded to **$823.85M in 2021** — 207% above benchmark. However, **Net Profit remained at -12%** because Total Operational Expenses ($355M) exceeded Gross Margin ($295M). Revenue growth is strong, but cost structure needs urgent attention.

---

### 🚚 Page 3: Supply Chain View

![Supply Chain View](screenshots/Supply Chain View.png)

**Purpose:** Help Supply Chain teams identify forecast gaps, excess inventory, and out-of-stock risks before they damage customer relationships and revenue.

**Visuals on this page:**

| Visual | What it shows |
|--------|--------------|
| **KPI Cards** | Forecast Accuracy % (80.31% vs goal 81%), Net Error (-139.68K), Absolute Error (2116.82K) |
| **Combo Chart** | Monthly Net Error (bars) + Forecast Accuracy % (line) vs LY — Jun to Aug 2021 |
| **Customer Risk Table** | Forecast Accuracy %, FA% LY, Net Error, Net Error %, Abs Error %, and RISK flag per customer |
| **Segment Risk Table** | Same metrics broken down by product segment |

**DAX measures powering this page:**
`Forecast Accuracy %` · `Net Error` · `Net Error %` · `Absolute Error %` · `FA % LY`

**Key Insights:**
> ⚠️ **Keyboard** segment has a forecast accuracy of only **56%** with a net error of **-941,775 units** — a severe out-of-stock risk that could cause significant lost sales.

> **Saturn** customer has the lowest forecast accuracy at **21.75%** — a critical relationship risk.

> **Networking (88.73%)** and **Mouse (88.58%)** are the best-performing segments for forecast accuracy.

---

### 📣 Page 4: Marketing View

![Marketing View](screenshots/Marketing.png)

**Purpose:** Help Marketing understand which products and regions are driving profitable growth — and where spend is not converting to margin.

**Visuals on this page:**

| Visual | What it shows |
|--------|--------------|
| **Product Performance Scatter Plot** | Net Sales $ (x-axis) vs GM % (y-axis), bubble size = sales volume, colored by division (N&S, P&A, PC) |
| **Segment Performance Matrix** | Net Sales $, GM $, GM %, Net Profit $, Net Profit %, Total Operational Expense per segment |
| **Region Performance Matrix** | Same metrics broken down by APAC, EU, LATAM, NA |
| **Unit Economics Donut Chart** | Split of Total COGS (64.21%) vs Gross Margin (35.79%) |
| **Waterfall Chart** | Gross Margin → Operational Expense → Net Profit showing the profitability gap |

**DAX measures powering this page:**
`Gross Margin %` · `Net Profit %` · `Net Sales` · `GM $` · `Net Profit $` · `Total Operational Expense`

**Key Insights:**
> All product segments deliver a **consistent GM% of ~35.5–36%** — product pricing and COGS are well managed across the board.

> **EU is the only profitable region at +1% net profit.** NA (-19%) and India (-32%) are the biggest profitability drains despite high revenue volumes.

> The scatter plot reveals **Notebook has the highest revenue ($57.49M)** but sits at average GM% — Networking and Storage deliver better margins at lower volumes.

---

### 🤝 Page 5: Sales View

![Sales View](screenshots/Sales View.png)

**Purpose:** Give Sales teams a granular view of customer and segment performance — to prioritize high-value relationships and flag underperformers.

**Visuals on this page:**

| Visual | What it shows |
|--------|--------------|
| **Customer Performance Table** | Net Sales $, GM $, GM % per customer |
| **Customer-Region Scatter Plot** | Net Sales $ vs GM %, colored by region (APAC, EU, NA) with gap tolerance slider |
| **Segment Performance Table** | Net Sales $, GM $, GM % for all 6 segments |
| **Revenue Waterfall Donut** | Gross Sales → Pre Invoice Deduction (29.23%) → Post Invoice Deduction (33.38%) → Net Sales (37.4%) |
| **COGS vs GM Donut** | Total COGS (64.13%) vs Gross Margin (35.87%) |

**DAX measures powering this page:**
`Net Sales` · `GM $` · `Gross Margin %` · `Pre Invoice Deduction` · `Post Invoice Deduction` · `Total COGS`

**Key Insights:**
> **Notebillig has the lowest GM% at just 17.43%** — well below the company average of 35.87%. This customer relationship is likely unprofitable after operational costs.

> **Accessories ($244.85M) and Notebooks ($266.48M)** together account for over 62% of total net sales — heavy revenue concentration worth monitoring.

> The scatter reveals **Amazon** appearing across multiple regions at high net sales but varying GM% — indicating inconsistent margin management geographically.

---

### 👔 Page 6: Executive View

![Executive View](screenshots/executive.png)

**Purpose:** Give the C-Suite a single-page summary of everything that matters — revenue, profitability, market share, and regional performance — without needing to navigate other views.

**Visuals on this page:**

| Visual | What it shows |
|--------|--------------|
| **Top KPI Cards** | Net Sales ($823.85M), GM% (35.87%), Net Profit% (-12%), Forecast Accuracy (80.21%) all vs Benchmark |
| **Revenue by Division Donut** | P&A (49.93%), PC (37.98%), N&S (12.09%) |
| **Revenue by Channel Donut** | Retailer (71.85%), Direct (16.93%), Distributor (11.22%) |
| **NS $ & GM% Trend Chart** | Annual trend of Net Sales, GM%, Net Profit%, AtliQ Market Share % from 2018–2022EST |
| **Market Share Area Chart** | AtliQ vs competitors (bp, dale, innovo, pacer) from 2018–2022 |
| **Sub-zone Performance Table** | NS $, RC%, GM%, Net Profit%, AtliQ MS%, Net Error%, RISK flag per sub-zone |
| **Top Customers by GM%** | AltiQ Exclusive (45.40%), Sorefoz (43.30%), Zone (43.28%) |
| **Top Products by GM%** | AQ 5000 Series variants, AQ Aspiron |

**DAX measures powering this page:**
`AtliQ Market Share %` · `Net Sales` · `Gross Margin %` · `Net Profit %` · `Forecast Accuracy %` · `Net Error %` · All BM comparison measures

**Key Insights:**
> AtliQ's market share grew from **7.77% (2018) to 9.92% (2022)** — the highest in 5 years, showing strong competitive momentum against bp, dale, innovo, and pacer.

> **Retailers dominate at 71.85% of revenue** — heavy channel concentration is a strategic risk if key retail relationships deteriorate.

> **India (25.57% of revenue, -32% net profit)** is the single biggest concern. The largest market by revenue is also the most loss-making region.

> **ROA and ANZ are both Out of Stock** — supply chain gaps are actively costing revenue in key APAC markets right now.

---

## 💡 Top Business Insights Summary

| # | Insight | Signal |
|---|---------|--------|
| 1 | Net Sales grew 207% vs benchmark to $823.85M | 🟢 Strong growth |
| 2 | Net Profit is -12% — operational expenses exceed gross margin | 🔴 Critical issue |
| 3 | India & NA are high revenue but deeply loss-making (-32%, -19%) | 🔴 Needs strategy |
| 4 | Keyboard: 56% forecast accuracy, -941K unit net error | 🔴 Supply chain risk |
| 5 | AtliQ market share hit 9.92% in 2022 — highest in 5 years | 🟢 Positive trend |
| 6 | EU is the only profitable region at +1% net profit | 🟡 Benchmark for others |

---

## 📂 Repository Structure

```
📦 business-insights-360
 ┣ 📄 README.md
 ┣ 📄 Business_Insights_360_AtliQ.pdf
 ┗ 📁 screenshots
    ┣ 🖼️ home.png
    ┣ 🖼️ finance.png
    ┣ 🖼️ supply_chain.png
    ┣ 🖼️ marketing.png
    ┣ 🖼️ sales.png
    ┗ 🖼️ executive.png
```

---

## 👩‍💻 About Me

Aspiring Data Analyst passionate about turning raw data into business decisions. Skilled in Power BI, SQL, DAX, and data storytelling. Currently completing the **Codebasics Data Analytics Bootcamp**.

📧 *[Your Email]*
🔗 *[Your LinkedIn URL]*
🐙 *[Your GitHub Profile URL]*

---

*This project was built for educational purposes as part of the Codebasics Data Analytics Bootcamp using a fictional dataset modelled on real-world business scenarios.*

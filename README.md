# Automated Weekly Business Report (n8n)

A fully automated weekly reporting pipeline built with n8n that pulls sales data from Google Sheets every Monday, calculates 10 business KPIs using a JavaScript code node, and delivers a formatted HTML report directly to Gmail — with zero manual intervention.

---

## Workflow Preview

![n8n Workflow](workflow-screenshot.png)

## Report Output Preview

![Email Report](report-screenshot.png)

---

## How It Works

```
Schedule Trigger (Every Monday)
        ↓
Google Sheets (Pull 80 sales records)
        ↓
JavaScript Code Node (Calculate 10 KPIs)
        ↓
Gmail (Send formatted HTML report)
```

The entire pipeline runs automatically every Monday. No human touches it between the data source and the stakeholder's inbox.

---

## Dataset

**Source:** Google Sheets — Nigerian Sales Data  
**Fields:** Date, Order ID, Product, Category, Units Sold, Unit Price, Revenue, Region, Sales Rep  
**Records:** 80 transactions across Electronics, Fashion, Home & Kitchen and Beauty categories  
**Regions:** Lagos, Abuja, Kano, Ibadan, Port Harcourt

---

## KPIs Calculated

The JavaScript code node computes all 10 KPIs programmatically from raw row data:

| KPI | Description |
|-----|-------------|
| Total Revenue | Sum of all revenue across all records |
| Total Orders | Count of all transactions |
| Average Order Value | Total Revenue / Total Orders |
| This Month Revenue | Revenue filtered to current month |
| Last Month Revenue | Revenue filtered to previous month |
| MoM Change | Month-over-Month revenue % change with directional indicator |
| Best Product | Highest revenue-generating product |
| Best Category | Highest revenue-generating category |
| Best Region | Highest revenue-generating region |
| Best Sales Rep | Highest revenue-generating sales representative |

---

## Report Output

The email report includes:

- Report date (auto-generated)
- Revenue Summary section with all financial KPIs
- Top Performers section showing best product, category, region and rep
- MoM change with trend arrow (up / down)
- Branded footer: "Powered by Samuel Makanjuola — Data & Automation"

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| n8n (Cloud) | Workflow automation and orchestration |
| Google Sheets | Data source |
| JavaScript | KPI calculation logic in code node |
| Gmail | Report delivery |

---

## Business Value

Before automation, generating this report would require manually opening Google Sheets, writing formulas for each KPI, formatting and composing an email, then sending it to stakeholders every single week.

This pipeline eliminates all of that. Every Monday at the scheduled time, stakeholders receive a clean, accurate, consistently formatted business report automatically.

---

## Files in This Repo

```
n8n-Weekly-Business-Report/
├── README.md
├── workflow-screenshot.png       <- n8n canvas showing the 4-node pipeline
├── report-screenshot.png         <- sample email report output
└── workflow.json                 <- exported n8n workflow (importable)
```

---

## How to Import the Workflow

1. Download `workflow.json`
2. Open your n8n instance
3. Click **New Workflow** then the menu icon
4. Select **Import from file**
5. Upload `workflow.json`
6. Connect your own Google Sheets and Gmail credentials
7. Activate the workflow

---


---

## 🛡️ License
This project is licensed under the MIT License. You are free to use, modify, 
and share this project with proper attribution.

---

## 🌟 About Me
Hi, I'm Samuel Ayomide Makanjuola — an Analytics Engineer and BI Analyst 
based in Abuja, Nigeria.

I build end-to-end data solutions, from structured data warehouses and SQL 
pipelines to Power BI dashboards and automated reporting workflows. My work 
sits at the intersection of data engineering, business intelligence and 
workflow automation — I care about building things that actually work in 
practice, not just in theory.

I document everything I build here on GitHub so others can learn from it, 
use it and improve on it. If something I built helped you, a star on the 
repo goes a long way.

[Portfolio](https://samuel-ayomide-makanjuola-portfolio.netlify.app/) • 
[LinkedIn](http://www.linkedin.com/in/samuel-ayomide-makanjuola-78443937a) • 
[GitHub](https://github.com/Jahsmine00001)

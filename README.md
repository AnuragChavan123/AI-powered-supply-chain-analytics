# AI-Powered Supply Chain Analytics

An end-to-end, AI-assisted data analytics pipeline that automates the full journey from raw sales data to supply chain KPI insights — built using **n8n**, **PostgreSQL (Supabase)**, and **Quadratic**.

---

## 📌 Project Overview

This project simulates a real-world supply chain analytics workflow for a fictional organic food company facing inventory and order fulfillment challenges. Instead of relying on manual Excel work or traditional BI tools, the entire pipeline — from data ingestion to analysis to insight generation — is automated and AI-assisted.

The goal was to build a portfolio-worthy, production-style analytics system that mirrors how modern analytics teams are starting to combine automation, cloud databases, and AI-powered tools to move faster without losing analytical rigor.

---

## 🎯 Objectives

- Automate ingestion of incoming sales data with zero manual file handling
- Centralize transactional data in a structured, queryable PostgreSQL database
- Use an AI-powered spreadsheet tool to clean, transform, and analyze data via natural language prompts
- Calculate and interpret key supply chain KPIs to support business decision-making
- Build a repeatable workflow that can scale to real incoming data feeds

---

## 🏗️ Technical Architecture

```
Email (Gmail) → n8n → PostgreSQL (Supabase) → Quadratic → AI-Generated Analysis & Insights
```

1. **Ingestion:** CSV sales files arrive as Gmail attachments
2. **Automation:** n8n monitors the inbox, extracts and converts CSV data to structured JSON
3. **Storage:** Transformed data is inserted into PostgreSQL tables hosted on Supabase
4. **Analysis:** Quadratic connects directly to the PostgreSQL database and pulls in live tables
5. **Insight Generation:** AI prompts inside Quadratic clean, merge, and analyze the data — generating calculations, charts, and summaries

---

## 🛠️ Tools & Technologies

| Category | Tools |
|---|---|
| Workflow Automation | n8n |
| Database | PostgreSQL, Supabase |
| AI-Powered Analysis | Quadratic |
| Programming | Python, SQL |
| Data Source | Gmail (CSV attachments), Exchange Rate API |

---

## ⚙️ Workflow Breakdown

### 1. Data Ingestion (n8n)
- Monitored Gmail inbox for incoming sales data emails
- Automatically extracted CSV attachments
- Converted CSV rows into JSON format
- Inserted records into PostgreSQL tables via automated workflow nodes

### 2. Database Setup (Supabase / PostgreSQL)
- Hosted a PostgreSQL instance on Supabase
- Designed fact and dimension tables to support relational analysis
- Loaded transactional supply chain data (orders, line items, fulfillment status)

### 3. AI-Powered Analysis (Quadratic)
- Connected Quadratic directly to the PostgreSQL database
- Imported and previewed database tables
- Generated a date dimension table using AI prompts
- Pulled historical USD–INR exchange rates via API integration
- Used AI-generated Python code to clean, join, and transform datasets within the spreadsheet environment

### 4. Supply Chain KPI Analysis
Calculated and interpreted key operational metrics, including:

- **Order Count** – total number of orders placed
- **Order Lines** – total number of individual line items across orders
- **Line Fill Rate** – percentage of order lines fulfilled completely
- **Volume Fill Rate** – percentage of total ordered volume/quantity fulfilled
- **On-Time Delivery (OTD) %** – percentage of orders delivered by the promised date
- **In-Full (IF) %** – percentage of orders delivered with the full ordered quantity
- **OTIF (On-Time In-Full) %** – combined metric capturing orders delivered both on time and in full
- **Reliability Metrics** – supporting measures used to assess overall fulfillment consistency

---

## 💡 Business Value

This project demonstrates how a multi-tool, AI-assisted pipeline can replace slower manual reporting cycles:

- Eliminates manual data entry and file handling through automated ingestion
- Provides a single, queryable source of truth for supply chain transactions
- Surfaces fulfillment bottlenecks (fill rate gaps, late deliveries) that directly affect customer satisfaction and cost
- Shows how AI tools can accelerate data cleaning, transformation, and analysis — while still requiring SQL, Python, and domain knowledge to validate outputs and catch AI errors

---

## 📂 Project Structure

```
AI-Powered-Supply-Chain-Analytics/
│── n8n-workflow/              # Exported n8n workflow (JSON)
│── sql/                       # Table creation & transformation scripts
│── quadratic/                 # Quadratic sheet / exported analysis
│── images/                    # Screenshots of pipeline and dashboard
│── README.md                  # Project documentation
```

---

## 📸 Screenshots

### n8n Automation Workflow
![n8n Workflow](images/n8n_workflow.png)

### PostgreSQL / Supabase Schema
![Database Schema](images/supabase_schema.png)

### Quadratic AI-Powered Analysis
![Quadratic Analysis](images/quadratic_analysis.png)

### KPI Summary / Insights
![KPI Dashboard](images/kpi_summary.png)

---

## 🚀 How to Reproduce

1. Set up a Gmail account to receive sales data CSV files
2. Import the n8n workflow and configure Gmail + PostgreSQL credentials
3. Create the required tables in Supabase using the scripts in `/sql`
4. Connect Quadratic to your Supabase PostgreSQL instance
5. Use AI prompts in Quadratic to generate the date dimension, pull exchange rates, and calculate KPIs

---

## 🔮 Future Improvements

- Add automated alerting for KPI thresholds (e.g., OTIF dropping below target)
- Expand to multi-supplier / multi-warehouse fulfillment tracking
- Build a live-refreshing dashboard layer on top of the Quadratic analysis
- Add error handling and logging to the n8n ingestion workflow

---

## 🙌 Acknowledgements

Project architecture and workflow inspired by the tutorial *"Data Analysis using AI Tools | Quadratic | N8N | Supply Chain."* Built and extended independently as a hands-on learning project.

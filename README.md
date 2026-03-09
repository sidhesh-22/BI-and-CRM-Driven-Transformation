# 🛒 Revitalizing Customer Engagement and Operational Efficiency: A BI & CRM-Driven Transformation

> **Gadget Geeks** | Electronics Retail | Salesforce · Tableau · Python · Mockaroo

<!-- [![Tableau](https://img.shields.io/badge/Tableau-Public-blue?logo=tableau)](https://rb.gy/pv00ow)
[![Salesforce](https://img.shields.io/badge/CRM-Salesforce-00A1E0?logo=salesforce)](https://www.salesforce.com/)
[![Python](https://img.shields.io/badge/Python-Preprocessing-yellow?logo=python)](https://www.python.org/)
[![Video](https://img.shields.io/badge/Demo-YouTube-red?logo=youtube)](https://youtu.be/DjvjojIPceE) -->

---

## 📋 Table of Contents
- [Executive Summary](#-executive-summary)
- [Business Problem](#-business-problem)
- [Methodology](#-methodology)
- [Skills & Tools](#-skills--tools)
- [Results & Business Recommendations](#-results--business-recommendations)
- [Next Steps](#-next-steps)
- [Dashboards & Links](#-dashboards--links)

---

## 📌 Executive Summary

Gadget Geeks is an emerging electronics retailer operating across Ireland and India, offering smartphones, laptops, smart home devices, and accessories. Despite a strong offline presence, the company lacked any integrated data infrastructure — customer data was fragmented across POS systems, spreadsheets, and emails, and there was no centralized way to monitor sales, marketing performance, or customer service quality.

This project designed and implemented a full BI and CRM transformation using **Salesforce** for customer relationship management and **Tableau** for business intelligence dashboards. Three synthetic datasets (1,000+ support tickets, 200 marketing campaigns, 3,000 sales transactions) were created to simulate real business operations, and the resulting dashboards enabled data-backed decisions across customer support, marketing, and sales functions.

Key outcomes included an average ticket resolution time of **3.5 hours**, a **42% higher weekend conversion rate** discovery, and an estimated **18% reduction in cost per acquisition (CPA)** through optimized campaign targeting.

---

## 🧩 Business Problem

Gadget Geeks was preparing to launch an online platform but faced critical operational gaps that threatened scalability:

| Gap | Impact |
|---|---|
| Fragmented customer data across POS, emails, and spreadsheets | No unified customer view; poor support tracking |
| Reactive customer service with no SLA tracking | High escalation rates; low CSAT scores |
| Manual marketing processes with no automation | Missed follow-ups; poor campaign ROI visibility |
| No centralized BI infrastructure | Decision-makers lacked real-time KPI visibility |

**Core business goals targeted:**
- Achieve 80%+ ticket resolution within 24 hours
- Improve marketing ROI through automated, segmented campaigns
- Attain a 360-degree customer view for personalization
- Drive a 30% increase in online sales over the next fiscal year

---

## 🔬 Methodology

### 1. Discovery & Planning
- Conducted a gap analysis and SWOT assessment of current operations
- Mapped stakeholder pain points to three focus areas: **customer support**, **marketing automation**, and **sales performance**
- Planned the system architecture connecting the website/app → CRM (Salesforce) → Data Warehouse → BI Platform (Tableau)

### 2. Data Design & Generation
- Designed a relational data model with five core entities: `Customer`, `Support_Ticket`, `Sales`, `Marketing_Campaign`, and `Campaign_Response`
- Generated three synthetic datasets using **Mockaroo**:
  - `Customer_Support_Tickets.csv` — 1,000 rows
  - `Enhanced_Marketing_Campaign.csv` — 200 rows
  - `Irish_Sales_Data.csv` — 3,000 rows
- Preprocessed all datasets in **Python (pandas)**:
  - Standardised date formats to `YYYY-MM-DD`
  - Removed duplicates via `.drop_duplicates()`
  - Filled nulls with defaults or median values
  - Cast numeric fields to `float` for Tableau compatibility
  - Cross-validated foreign keys (`Customer_ID`, `Campaign_ID`) across all files

### 3. CRM Configuration (Salesforce)
- Configured the **Campaigns** object with custom fields: `Budgeted Cost`, `Actual Cost`, `Campaign Type`, `Campaign Status`
- Set up the **Cases** object with custom fields: `Issue Priority`, `Resolution SLA`, `Product Affected`
- Built **Record-Triggered Flows** to automate:
  - Confirmation email on new ticket creation
  - Closure email when a ticket is marked "Closed"
- Applied **role-based permissions** (Marketing Executives vs. Sales Staff vs. Managers)
- Added **picklist dependencies** (e.g., "Escalated" status only selectable when priority = "High")

### 4. Dashboard Development (Tableau)
- Imported and blended all three datasets in Tableau via foreign key relationships
- Built **calculated fields** for derived metrics: average resolution time, CTR, campaign ROI, CPA
- Designed three role-specific, interactive dashboards with dynamic filters (date range, region, segment, priority)

---

## 🛠 Skills & Tools

| Category | Tools / Skills |
|---|---|
| **CRM** | Salesforce (Campaigns, Cases, Flows, Email Templates, Permission Sets) |
| **BI & Visualisation** | Tableau (calculated fields, blended data sources, interactive filters) |
| **Data Engineering** | Python · pandas (cleaning, deduplication, type casting, date formatting) |
| **Data Modelling** | Relational schema design, ERD, foreign key mapping, data dictionary |
| **Data Generation** | Mockaroo (synthetic dataset creation with realistic distributions) |
| **Project Planning** | Miro (system architecture, wireframing) |
| **Analytics** | Descriptive analytics, KPI design, funnel analysis, demographic segmentation |

---

## 📊 Results & Business Recommendations

### Customer Support
- **Avg. resolution time: 3.5 hours** — a strong result against the 24-hour SLA target
- **70%+ first-contact resolution rate** — reduced escalation burden on senior agents
- CSAT scores ranged from **2.8 to 3.2** across all support channels (Email, Chat, Phone, Social Media)

> **Recommendation:** Prioritise "Technical Issue" and "Billing Inquiry" ticket types, which showed the longest resolution times in the dashboard. Assign specialist agents to these categories during peak hours to push CSAT above 3.5.

### Marketing
- Identified **Top 5 converting campaigns** by engagement score: Summer Sale, Spring Clearance, Halloween Spooktacular, New Year's Celebration, Cinco de Mayo Fiesta
- **~18% reduction in CPA** achieved through targeted audience segmentation and channel optimisation
- Marketing funnel revealed **48.3M clicks from 49.3M impressions** but only **50.7K conversions** — indicating a significant drop-off at the conversion stage

> **Recommendation:** Investigate the gap between click and conversion rates. A/B test landing pages for the top 3 campaigns and consider retargeting flows in Salesforce for users who clicked but didn't convert.

### Sales
- **Total revenue: €26M | Total profit: €1.86M** across the analysis period
- Top-selling product: **MacBook Pro** (€6.05M), followed by iPhone and ThinkPad Laptop
- **Weekend sales were 42% higher** than weekday sales in conversion rate
- **Dublin leads** all counties in total sales volume

> **Recommendation:** Align future campaign launch dates to weekends and use geo-targeted promotions for Dublin and Clare (top 2 counties). Explore underperforming regions like Leitrim and Monaghan for expansion opportunities.

### CRM Automation Impact
- Automated email flows eliminated manual follow-up delays, closing a critical communication gap
- Ticket-creation and ticket-closure emails improved perceived responsiveness and are expected to contribute to improved NPS scores in live deployment

---

## 🚀 Next Steps

1. **Real-time CRM–Tableau integration** via API connectors, replacing manual CSV uploads for live dashboard updates
2. **AI-based sentiment analysis** on support ticket text to proactively flag churn-risk customers before escalation
3. **Predictive analytics** in Tableau using time-series forecasting to project future ticket volumes and sales trends
4. **Expand CRM use cases** to include lead nurturing pipelines, upselling workflows, and loyalty programme tracking
5. **Migrate to a cloud data warehouse** (e.g., Snowflake or Google BigQuery) for improved scalability, automation, and multi-source integration

---

## 🔗 Dashboards & Links

| Resource | Link |
|---|---|
| 📊 Customer Support Tickets Dashboard | [View on Tableau](https://rb.gy/smgisk) |
| 📈 Marketing Performance Dashboard | [View on Tableau](https://rb.gy/77ly11) |
| 💰 Sales Dashboard | [View on Tableau](https://rb.gy/pv00ow) |
| 🗺 Project Miro Whiteboard | [View on Miro](https://rb.gy/tmrotp) |
<!-- | 🎥 Video Presentation | [Watch on YouTube](https://youtu.be/DjvjojIPceE) | -->



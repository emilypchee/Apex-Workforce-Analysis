# Apex Systems — People & Workforce Analytics Dashboard

![Dashboard 1 Overview](images/Apex_Workforce_Analysis_1.png)

## Overview
This Power BI dashboard analyzes workforce health across **Apex Systems**, a mid-size B2B tech company. Built on a synthetic HR dataset modeled after real enterprise People Analytics use cases, the project surfaces insights across the full employee lifecycle from hiring pipeline to attrition root causes.

The dashboard was designed to answer the kind of questions a VP of People would bring to a Monday morning leadership meeting: where are our hiring bottlenecks, who are our flight risks, and is our L&D spend actually moving the needle on performance?

## Business Question
> *"How healthy is our workforce, and where should we invest to reduce attrition, accelerate hiring, and build a high-performance culture?"*

## Dashboard Objectives

The report is organized into three analytical domains:

**1 · Headcount & Org Health**
- How many active employees does each department have vs. its headcount cap?
- Which departments have the most employees on leave right now?
- Which departments have consistently scored 4 or 5 over the past 3 years?
- How does average performance score vary across departments?

**2 · Learning & Development**
- What % of employees have completed all required compliance courses?
- How much has been spent on training per department this year?
- Is there a relationship between training completions and performance score?

**3 · Attrition & Flight Risk**
- What is the voluntary attrition rate by department?
- What are the top reasons employees give for leaving?
- Are there departmental patterns in tenure length at time of exit?

## Data Model
Built on a database (10 tables).
See [data/data-dictionary.md](data/data-dictionary.md) for
column-level documentation.

## SQL
Exploratory queries used to validate and shape the analysis
are in [/sql](/sql). Each file is self-documented with a
comment block explaining the business question it addresses.

## Tools Used
- **Power BI Desktop** — data model, DAX measures, report design
- **SQL** — data exploration and validation
- **DAX** — custom measures for revenue, ranking, and time intelligence

## How to Use This File
1. Download `report/Apex_Systems_People_Workforce_Analytics.pbix`
2. Open in Power BI Desktop (free download from Microsoft)
3. The embedded dataset loads automatically

## About
Built as part of my ongoing journey with data storytelling.
[LinkedIn](https://www.linkedin.com/in/emilypchee/) |
[Portfolio](https://seemly-existence-5eb.notion.site/You-got-questions-Emily-Chee-got-answers-02d623d6b64c496e818930e9b725b52c)

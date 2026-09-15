# Research Funding Trends and Strategic Investment Opportunities

## Project Overview

I built this project to analyze public research funding data from the Israeli Government Data Portal (data.gov.il). The goal was to identify trends in research investment, institutional funding patterns, emerging research areas, and international collaboration.

The analysis covers 1,649 research projects across 2019–2025, representing approximately ₪722M in total recorded funding.

The main question guiding the analysis is:

> **How has research funding evolved over the years, and what opportunities can be identified for future investment?**

The goal is to move beyond descriptive statistics and identify funding patterns that may help highlight areas for further investigation and potential future investment.

## Key Questions

The analysis explores five main questions:

1. Which institutions receive the largest number of research projects and the highest total funding?
2. How does research funding vary across years and research areas?
3. Which research sub-fields experienced the largest budget growth?
4. How do active and completed projects differ across institutions and international partners?
5. How do international research partnerships differ in scale and average project funding?

## Key Findings
Big Picture: Analyzed 1,649 projects (68.9% currently active) across 82 local institutions and 25 partner countries. Average project budget sits at ₪438K.

### Funding Trends

Recorded research funding varies substantially across the 2019–2025 period, with a particularly large decline in 2020 followed by a recovery in subsequent years.

Because the dataset alone does not establish the reason for this variation, the analysis treats these changes as funding patterns rather than causal effects.

### Emerging Research Areas

Several research sub-fields experienced substantial increases between their first and most recent recorded funding years.

For example:

* **AI Applications:** approximately ₪1.2M → ₪7.0M (**+481%**)
* **Healthy Aging:** approximately ₪68K → ₪3.9M (**+5,683%**)

These results highlight research areas that may warrant further investigation when considering future funding priorities.

### International Collaboration

International partnerships vary considerably in both project volume and average funding.

Germany has the largest number of recorded collaborative projects, while Sweden represents a smaller-volume partnership with a substantially higher average budget per project.

A deeper comparison also reveals differences in the research areas associated with these partnerships.

## Methodology

I extracted the raw dataset via REST API, cleaned and processed it in Python, and loaded it into an in-memory SQLite database for SQL querying.

Data Prep & Cleaning (Python / Pandas): Standardized messy institution names and converted EUR-denominated grants to ILS using historical yearly exchange rates.

Data Analysis (SQL): Used CTEs, subqueries, and window functions to aggregate budgets, track growth metrics, and compare active vs. completed projects.

Visualization (Matplotlib / Seaborn): Generated visual distributions and trend charts to support the findings.

For research sub-field growth, budget changes were calculated between each sub-field's **first and most recent recorded year**, rather than forcing all fields into a 2019–2025 comparison. This accounts for emerging fields that were introduced later in the dataset.

## Things to Keep in Mind

The analysis is descriptive and identifies associations and funding patterns rather than causal relationships; it doesn't explain why certain yearly changes occurred.

Descriptive, Not Causal: This project highlights trends and associations; it doesn't explain why certain yearly changes occurred.

Base-Effect Growth: Massive percentage gains (like Healthy Aging) often happen because the initial starting budget was very small.

Scope vs. Quality: International project data reflects financial metrics, not scientific impact.

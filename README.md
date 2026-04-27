# DataCo Supply Chain Analysis

## About This Project

This project analyses operational performance and profitability issues in a global supply chain dataset.
The goal was not just to calculate metrics, but to validate them and challenge assumptions before presenting results.

## Tools Used

* Excel: data cleaning, PivotTables, KPI dashboard, charts

## The Data

Source: [DataCo Smart Supply Chain for Big Data Analysis on Kaggle](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)

180,519 orders across 5 global markets between 2015 and 2018.

## What I Found

**Delivery performance is the biggest operational issue**
57.3% of orders arrived late. I initially calculated this as 54.8% but realised I was including cancelled orders in the denominator. Cancelled orders never entered the shipping process so I removed them before recalculating. Small methodological decisions like this change the numbers and matter in a real business context.

**The profit figure hides a bigger problem**
The headline net profit of $3.8M looks acceptable until you separate it out. Gross profit is $7.5M but $3.7M in losses almost cancels it out entirely. Nearly 1 in 5 orders is loss making. A business relying on that net figure alone would not see how close to breakeven it actually is.

**A small number of categories drive most of the profit**
Fishing generates $731k on its own, almost 20% of total profit. The top 3 categories account for 42% of profit combined. The remaining 47 categories contribute the rest. That kind of concentration is worth flagging to any stakeholder.

**Europe and LATAM lead on profitability**
Together they generate over $2.2M in profit. Africa generates $240k despite decent order volumes which points to a margin problem rather than a demand problem.

**Average order value needed correcting**
My first calculation gave $203 per order. I then noticed the dataset had multiple line items per order so I was averaging at row level, not order level. Grouping by Order ID first gave the correct figure of $1,119. That is the kind of error that is easy to miss and significant enough to affect business decisions if it does.

## My Approach

* Kept the raw data untouched and built a separate working sheet for all cleaning and analysis
* Removed cancelled orders before calculating delivery performance and documented why
* Broke profit into three components rather than reporting the net figure alone
* Corrected the average order value calculation after identifying the row level vs order level issue
* Built a KPI dashboard summarising the key findings for a non-technical audience

## What I Learned

The most important analytical skill is not just applying formulas, but questioning outputs before presenting them.
Every key metric in this project required judgement, not just calculation.

## Files

* `analysis/final_sample.xlsx` – cleaned data, calculations, and dashboard (lightweight version for GitHub)
* `data/sample_data.csv` – reduced dataset for reproducibility
* `dashboard.png` – screenshot of the final dashboard

## Full Dataset

Due to file size limitations, the complete dataset and full workbook are available here:
https://docs.google.com/spreadsheets/d/1dnt5muRa5PyRtaXqJDHBkDopIDd5L16G/edit?usp=sharing&ouid=105722416914194764069&rtpof=true&sd=true

*Note: The original dataset contains ~180,000 rows. A reduced sample is provided in this repository to ensure usability and performance.*

## Dashboard Preview

![Dashboard](dashboard.png)

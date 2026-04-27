# DataCo Supply Chain Analysis

## What This Project Is About

I wanted to take a large real-world dataset and treat it like an actual 
business problem, not just build charts for the sake of it. 
The DataCo dataset has 180,000+ supply chain orders and I used it to 
find out where the business was losing money and why delivery performance 
was so poor.

## Tools Used
- Excel: data cleaning, PivotTables, KPI dashboard, charts

## The Data

Source: [DataCo Smart Supply Chain for Big Data Analysis on Kaggle](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)

180,519 orders across 5 global markets between 2015 and 2018.

## What I Found

**Delivery is a serious problem**
Over half of all orders arrive late, 57.3% to be exact. That is not 
a minor issue, that is a fundamental operations failure. Standard Class 
shipping accounts for 60% of all orders and averages 4 days, which 
explains a lot.

**The profit picture is more complicated than it looks**
Net profit is $3.8M which sounds fine until you break it down. 
Gross profit is actually $7.5M but $3.7M in losses nearly wipes it out. 
Nearly 1 in 5 orders loses money. That is not noise, that needs fixing.

**A few categories carry everyone else**
Fishing alone generates $731k, almost 20% of total profit. 
The top 3 categories (Fishing, Cleats, Camping and Hiking) account for 
42% of all profit. The bottom 40 categories combined barely move the needle.

**Europe and LATAM are where the money is**
Together they generate over $2.2M in profit. Africa brings in $240k 
despite having a reasonable order volume, a margin problem worth 
investigating.

**The average order value was being understated**
Row level averaging gave $203 per order. When I grouped by Order ID 
properly the real figure was $1,119. That is a significant difference 
and the kind of thing that leads to bad pricing decisions if left 
uncorrected.

## How I Approached It

- Removed cancelled orders before calculating delivery rate. They never 
  entered the shipping process so including them would skew the metric
- Calculated profit at three levels: gross, losses and net. The headline 
  number alone tells you nothing
- Recalculated average order value at order level not row level. Each 
  order has multiple line items so row level averaging overstates volume 
  and understates value
- Built the dashboard to show findings at a glance without needing to 
  dig into the data

## Files

- `DataCo_Supply_Chain_Analysis.xlsx` full workbook with raw data, 
  working sheet and dashboard
- `dashboard.png` screenshot of the final dashboard

## Dashboard Preview

![Dashboard](dashboard.png)

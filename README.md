# DataCo Supply Chain Analysis

## About This Project

This is one of my portfolio projects as I transition into data analytics. 
I chose a supply chain dataset because I wanted to work with something 
that had real business complexity, not a clean tutorial dataset. 
The goal was to go beyond surface level analysis and actually question 
the numbers before presenting them.

## Tools Used
- Excel: data cleaning, PivotTables, KPI dashboard, charts

## The Data

Source: [DataCo Smart Supply Chain for Big Data Analysis on Kaggle](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)

180,519 orders across 5 global markets between 2015 and 2018.

## What I Found

**Delivery performance is the biggest operational issue**
57.3% of orders arrived late. I initially calculated this as 54.8% but 
realised I was including cancelled orders in the denominator. Cancelled 
orders never entered the shipping process so I removed them before 
recalculating. Small methodological decisions like this change the 
numbers and matter in a real business context.

**The profit figure hides a bigger problem**
The headline net profit of $3.8M looks acceptable until you separate 
it out. Gross profit is $7.5M but $3.7M in losses almost cancels it out 
entirely. Nearly 1 in 5 orders is loss making. A business relying on 
that net figure alone would not see how close to breakeven it actually is.

**A small number of categories drive most of the profit**
Fishing generates $731k on its own, almost 20% of total profit. 
The top 3 categories account for 42% of profit combined. 
The remaining 47 categories contribute the rest. 
That kind of concentration is worth flagging to any stakeholder.

**Europe and LATAM lead on profitability**
Together they generate over $2.2M in profit. Africa generates $240k 
despite decent order volumes which points to a margin problem 
rather than a demand problem.

**Average order value needed correcting**
My first calculation gave $203 per order. I then noticed the dataset 
had multiple line items per order so I was averaging at row level, 
not order level. Grouping by Order ID first gave the correct figure 
of $1,119. That is the kind of error that is easy to miss and 
significant enough to affect business decisions if it does.

## My Approach

- Kept the raw data untouched and built a separate working sheet 
  for all cleaning and analysis
- Removed cancelled orders before calculating delivery performance 
  and documented why
- Broke profit into three components rather than reporting the 
  net figure alone
- Corrected the average order value calculation after identifying 
  the row level vs order level issue
- Built a KPI dashboard summarising the key findings for a 
  non technical audience

## What I Learned

Working through this project taught me that the most important 
analytical skill is not knowing which formula to use. It is knowing 
when to question your own output before presenting it. 
Every key metric in this project required a judgement call, 
not just a calculation.

## Files

- [DataCo_Supply_Chain_Analysis Excel Files](https://docs.google.com/spreadsheets/d/1dnt5muRa5PyRtaXqJDHBkDopIDd5L16G/edit?usp=sharing&ouid=105722416914194764069&rtpof=true&sd=true) full workbook including raw data, 
  working sheet and dashboard
- `dashboard.png` screenshot of the final dashboard

## Dashboard Preview

![Dashboard](dashboard.png)

# Quantium Chips Category Trial Analysis (Excel)

## Project Overview

This project evaluates the effectiveness of a retail store trial in the chips category using transactional and customer data. The analysis replicates the logic of an existing R-based solution but was implemented entirely in Microsoft Excel.

The objective was to determine whether selected trial stores experienced a statistically significant increase in sales compared with comparable control stores, using historical performance to identify suitable matches.

## Tools Used

- Microsoft Excel
- PivotTables
- Structured Tables
- Data Cleaning and Transformation
- Correlation Analysis
- Statistical Confidence Intervals
- Data Visualization

## Data Preparation and Cleaning

Transaction and customer datasets were imported into Excel and converted into structured tables to enable efficient analysis.

Key preparation steps included:
- Checking for missing values and duplicate records
- Removing non-chip products and irrelevant transactions
- Creating derived variables:
- YEARMONTH extracted from transaction dates
- BRAND extracted from product names
- PACK_SIZE extracted from product descriptions
- Merging transaction and customer datasets using a common key

Outcome:
A clean, analysis-ready dataset suitable for store-level performance comparisons.

## Creation of Monthly Metrics

Using PivotTables, transaction data was aggregated to the store–month level.

The following core metrics were calculated:
- Total sales
- Number of transactions
- Number of customers
- Total units sold

Additional derived metrics were created:
- Transactions per customer
- Chips per transaction
- Average price per unit

## Pre-Trial Store Filtering

To ensure fair comparisons, stores were filtered to include only those with complete pre-trial data.

Steps included:
- Restricting the dataset to the pre-trial period (July 2018 – January 2019)
- Counting the number of distinct months of observations for each store
- Retaining only stores with all seven months of pre-trial data

Outcome:
A consistent dataset of stores with full historical data for control selection.

## Control Store Selection

For each trial store, an appropriate control store was selected using two similarity measures.

### 1. Correlation Analysis

Correlation was calculated between trial stores and candidate control stores using pre-trial performance metrics.

Higher correlation values indicated similar historical trends.

### 2. Magnitude Distance

Absolute differences in pre-trial sales magnitude were calculated between stores.

Smaller differences indicated similar sales scale.

### 3. Normalization

Magnitude distances were normalized to a 0–1 scale so they could be compared directly with correlation scores.

### 4. Combined Similarity Score

The final similarity score was calculated as:
(Correlation Score + Normalized Magnitude Score) / 2

The control store with the highest combined score was selected for each trial store.

## Trial Period Analysis

The trial period was defined as:

February 2019 – April 2019

For each trial store:
- Actual trial store sales were calculated
- Control store sales were scaled using pre-trial ratios
- Percentage differences between trial and scaled control sales were computed

This allowed a fair comparison between the stores during the trial.

## Statistical Significance Testing

To determine whether observed changes were meaningful:
1. The standard deviation of pre-trial percentage differences was calculated.
2. 95% confidence intervals were constructed using pre-trial data.
3, Trial period results were compared to these confidence bands.

If trial store sales exceeded the upper confidence bound, the increase was considered statistically significant.

## Visual Analysis 

Line charts were created to compare:
- Trial store sales
- Scaled control store sales
- Upper and lower confidence intervals

These visualizations clearly illustrate whether trial stores outperformed expectations during the trial period.

## Key Findings

- Store 86 showed a statistically significant increase in sales during the trial period.
- Stores 77 and 88 did not demonstrate consistent or significant improvement compared with their control stores.
- Results were consistent with the conclusions from the original R-based analysis.

## Conclusion

The Excel implementation successfully replicated the analytical framework of the original R solution.

Despite minor numerical differences due to rounding and manual filtering, the methodology, statistical reasoning, and conclusions remain consistent.

The analysis suggests that the store trial was effective only for Store 86, indicating that the intervention may not scale uniformly across all locations.



## Walmart-Market-Basket-Analysis

Market Basket Analysis (MBA) is a powerful retail analytics technique used to identify product pairs that are frequently purchased together. 


## Table of Contents

[Background & Overview](#Background-&-Overview)

[Objectives](#Objectives)

[Methodology](#Methodology)

[Analysis Overview](#Analysis-Overview)

[Key Insights](#Key-Insights)

[Recommendations](#Recommendations)

[Conclusion](#Conclusion)

[Appendix: DAX Measures](#Appendix-DAX-Measures)

[Interactive Dashboard](#Interactive-Dashboard)


## Background & Overview

Market Basket Analysis (MBA) is a powerful retail analytics technique used to identify product pairs that are frequently purchased together. 

This project leverages Walmart’s grocery transaction data to uncover customer buying patterns.

Insights from this analysis inform cross-selling, promotional strategies, and product placement to boost sales and improve customer experience.

## Objectives

The key goals of this analysis include:

Identifying product pairs frequently purchased together.

Calculating Support, Confidence, and Lift metrics to evaluate the strength of product associations.

Recommending actionable strategies for product bundling, promotions, and shelf placement.

## Methodology

### Tools

Excel & Power BI were used for ETL, data cleaning, transformation, DAX calculations and data visualization.

### Data Collection

The dataset comprises Walmart’s grocery transaction data, detailing product purchases across multiple transactions.

![mba](https://github.com/user-attachments/assets/60597b4a-1b51-4309-b931-669efa8f95c3)


### Data Cleaning

Handling Missing Values: Incomplete records were removed to maintain accuracy.

Standardizing Product Names: Ensured uniform naming conventions for all products.

Removing Duplicates: Eliminated duplicate entries to avoid skewing results.

## Metrics: Support, Confidence, Lift

1. Support:

Definition: Proportion of transactions containing a given product pair.

Calculation:

Support = Transactions containing both Product1 and Product2 / Total Transactions

Threshold: Product pairs with support > 0.60% were included.

2. Confidence:

Definition: Probability of purchasing one product given the purchase of another.

Calculations:

Confidence1: Likelihood of buying Product2 given Product1 is in the cart.

Confidence2: Likelihood of buying Product1 given Product2 is in the cart.

3. Lift:

Definition: Strength of the association, comparing observed and expected co-purchase frequencies.

Calculation:
Lift = Confidence / Expected Confidence if Independent

Threshold: Lift > 2.20 indicates a strong association.


## Analysis Overview

### Chord Diagram

![Screenshot 2024-12-04 135440](https://github.com/user-attachments/assets/e4e9a33d-7280-485b-81ac-820c98659dbe)

Purpose: Visualizes the relationships between products based on co-purchase frequencies.

Findings:

Thicker lines between products indicate stronger associations.

Pairs like "Whipped/Sour Cream & Root Vegetables" show high frequency and strong connections.

### Scatter Plot

![Screenshot 2024-12-12 145222](https://github.com/user-attachments/assets/545120ac-c5f2-4be2-9b6a-63bb1e3d579b)


Purpose: Maps product pairs based on Lift (X-axis) and Support (Y-axis).

Findings:

High-Lift, High-Support pairs like "Root Vegetables & Other Vegetables" are strong candidates for cross-selling strategies.

### Matrix Table

![Screenshot 2024-12-12 145353](https://github.com/user-attachments/assets/efe7113a-c9c3-4820-9339-1eb37a243b25)


Purpose: Detailed view of Confidence and Lift values for each product pair.

Structure:

Columns: Potential purchases.

Rows: Current purchases and their associations.

Values: Confidence and Lift metrics.

## Findings:

High-confidence pairs, such as "Yogurt & Soft Cheese," suggest targeted promotions can drive sales.


### Key Insights

1. Strong Product Associations:

Pairs like "Whipped/Sour Cream & Root Vegetables" have high Support and Lift values, highlighting their strong relationship.

2. Cross-Selling Opportunities:

High Confidence values for pairs like "Yogurt & Soft Cheese" suggest potential for targeted promotions.

3. Product Bundling:

Products with strong associations, such as "Root Vegetables & Whipped/Sour Cream," can be bundled to encourage purchase.


## Recommendations

1. Strategic Product Placement:

Place associated products, like "Whipped/Sour Cream" and "Root Vegetables," closer in-store to encourage co-purchases.

2. Targeted Promotions:

Offer discounts on complementary products, such as "Soft Cheese," when customers purchase "Yogurt."

3. Bundling Strategy:

Create bundles based on identified strong pairs (e.g., "Root Vegetables & Whipped/Sour Cream") to appeal to specific customer segments.

## Conclusion

The Market Basket Analysis of Walmart's grocery transactions provides actionable insights into customer buying patterns.

By focusing on Support, Confidence, and Lift metrics, this project highlights opportunities for cross-selling, product placement, and promotions. 

These strategies can help Walmart optimize sales, enhance the shopping experience, and drive business growth.

## Appendix: DAX Measures

Confidence1 = 

VAR Prod1 = Basket_Analysis[Product1]
VAR Support1 = COUNTROWS(FILTER(Groceries, Groceries[Products] = Prod1)) / [Total Transactions]
RETURN Basket_Analysis[Support Basket] / Support1

Confidence2 = 

VAR Prod2 = Basket_Analysis[Product2]
VAR Support2 = COUNTROWS(FILTER(Groceries, Groceries[Products] = Prod2)) / [Total Transactions]
RETURN Basket_Analysis[Support Basket] / Support2

## Interactive Dashboard

https://app.powerbi.com/groups/me/reports/5f46410b-a82e-48cb-87a9-50f077cae24b/bceaa7e609e0e5be7538?experience=power-bi






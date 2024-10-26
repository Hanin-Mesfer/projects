# Instacart Market Basket Analysis

#Project Description 

This project performs Market Basket Analysis on the Instacart dataset to discover common product associations using Apriori algorithm. Association rules mined from the data can help in identifying frequently co-purchased products, aiding in inventory planning, product bundling, and targeted promotions.
(https://www.kaggle.com/c/instacart-market-basket-analysis/data)



## Code Workflow

Merge and Pivot Data:

Data from the orders and products dataframes is merged to create a single dataset.
A pivot table is created where each row represents an order, and each column represents whether a specific product was purchased.

Convert to Binary Format:

The pivot table values are converted to binary (1 if purchased, 0 otherwise) to prepare the data for association analysis.
Apply Apriori Algorithm:

The Apriori algorithm is applied to find frequent itemsets with a minimum support threshold of 0.01.
Generate Association Rules:

Rules are generated using a confidence threshold of 0.2 and sorted by lift to highlight the strongest associations.
Save and Display Results:

The association rules are saved to a CSV file named market_basket_rules.csv.
The top 10 rules, sorted by lift, are printed to the console.
Visualization:

A scatter plot is created to show the relationship between support and confidence for the rules, with lift represented by color intensity.

Merge and Pivot Data:

Data from the orders and products dataframes is merged to create a single dataset.
A pivot table is created where each row represents an order, and each column represents whether a specific product was purchased.
Convert to Binary Format:

The pivot table values are converted to binary (1 if purchased, 0 otherwise) to prepare the data for association analysis.
Apply Apriori Algorithm:

The Apriori algorithm is applied to find frequent itemsets with a minimum support threshold of 0.01.
Generate Association Rules:

Rules are generated using a confidence threshold of 0.2 and sorted by lift to highlight the strongest associations.
Save and Display Results:

The association rules are saved to a CSV file named market_basket_rules.csv.
The top 10 rules, sorted by lift, are printed to the console.
Visualization:

A scatter plot is created to show the relationship between support and confidence for the rules, with lift represented by color intensity.

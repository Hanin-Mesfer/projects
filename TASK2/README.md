Instacart Market Basket Analysis

Project Description 

This project performs Market Basket Analysis on the Instacart dataset to discover common product associations using Apriori algorithm. Association rules mined from the data can help in identifying frequently co-purchased products, aiding in inventory planning, product bundling, and targeted promotions.
(https://www.kaggle.com/c/instacart-market-basket-analysis/data)


Project Workflow

Data Simulation: An example CSV structure for orders and products is generated for demonstration.

Data Preparation: The datasets are merged, and a basket format is created where each row represents an order, and each column represents a product.

Frequent Itemsets: The Apriori algorithm is applied to find itemsets that frequently occur together.

Association Rules: Rules are generated to highlight strong associations between itemsets, sorted by metrics such as support, confidence, and lift.

Visualization: A scatter plot visualizes the association rules, displaying support vs confidence, with lift as a color gradient.
Output: The rules are saved as a CSV file, allowing further analysis.

Requirements
Python 3.x
Libraries:
pandas
mlxtend
matplotlib
Install the required packages using:


pip install pandas mlxtend matplotlib

Code Overview

Import Libraries
python

import pandas as pd
from mlxtend.frequent_patterns import apriori, association_rules
import matplotlib.pyplot as plt
Data Preparation



merged_data = pd.merge(order_products, products, on='product_id')
basket = merged_data.groupby(['order_id', 'product_name'])['product_id'].count().unstack().fillna(0)
basket = basket.applymap(lambda x: 1 if x > 0 else 0)
Market Basket Analysis
python

# Finding frequent itemsets and generating association rules
frequent_itemsets = apriori(basket, min_support=0.01, use_colnames=True)
rules = association_rules(frequent_itemsets, metric="confidence", min_threshold=0.2)
rules = rules.sort_values(by='lift', ascending=False)
Export and Visualization
python

# Save to CSV and visualize rules
rules.to_csv('market_basket_rules.csv', index=False)
plt.scatter(rules['support'], rules['confidence'], alpha=0.6, c=rules['lift'], cmap='viridis')
plt.colorbar(label='Lift')
plt.xlabel('Support')
plt.ylabel('Confidence')
plt.title(f'Support vs Confidence for Instacart Market Basket Analysis')
plt.show()

Output

CSV File: The generated association rules are saved as market_basket_rules.csv.
Top Rules: Displays the top 10 association rules sorted by lift.
Visualization: A scatter plot shows support vs confidence with lift represented by color.
Example Usage

To execute the code, copy it into a Python script or Jupyter Notebook and run it within an environment with the required libraries installed.
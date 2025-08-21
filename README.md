MARKET BASKET ANALYSIS PROJECT DOCUMENTATION

1. Project Goal
- The objective of this project is to perform Market Basket Analysis to uncover frequent product combinations purchased together by customers.
- These insights can help retail businesses optimize product placement and create targeted marketing strategies like cross-selling and promotions.
  
2. Dataset Description

- Dataset: Groceries dataset containing transactions from a supermarket.
- Each row represents a single purchased item.
- Unique transactions are identified by customer ID and date.
- The dataset includes columns:
- Member_number: Customer identifier
- Date: Transaction date
- itemDescription: Purchased product name

3. Assumptions
   
- Each unique combination of Member_number and Date represents one shopping basket/transaction.
- Duplicate items within the same basket are treated as a single occurrence (only presence/absence matters).
- No missing or incorrect transaction data assumed.
- Minimum support is set considering data sparsity (adjusted to 0.01).

5. Data Preparation
- Group transactions by customer and date to form baskets.
- Convert lists of items per basket into a one-hot encoded DataFrame using TransactionEncoder from mlxtend.
- This format is required to apply the Apriori algorithm.

5. Methodology
   
- Use the Apriori algorithm to identify frequent itemsets with support ≥ 1%.
- Generate association rules based on lift ≥ 1 to find meaningful correlations.
- Analyze key metrics:
- Support: Frequency of itemset occurrence.
- Confidence: Likelihood of consequent given antecedent.
- Lift: How much more frequently items appear together versus random chance.

7. Results
   
- Extracted frequent itemsets showing commonly co-purchased products.
- Generated a set of association rules highlighting significant relationships.
- Visualized top rules by lift using horizontal bar charts.

7. Business Insights & Recommendations
   
- Products such as {Milk, Bread} are often bought together, suggesting grouping them on shelves or bundled promotions.
- Some product pairs (e.g., {Yogurt} and {Milk}) show strong association, indicating cross-selling opportunities.
- Insights can help reduce time customers spend searching by organizing store layout according to popular product combinations.
- Marketing campaigns targeted at high-confidence rules may increase sales and customer satisfaction.

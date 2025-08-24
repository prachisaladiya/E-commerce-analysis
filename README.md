# E-Commerce Customer Intelligence & Recommendation System

Tech: Python, Pandas, NumPy, Jupyter Notebook
Focus: Customer segmentation, rule-based recommendations, business insights

## Project Objective:
Analyze transaction data to understand customer behavior, segment users by value and frequency, and generate simple, explainable product recommendations that a business can act on immediately.

## Key Questions Answered:
Who are our most valuable and most frequent customers?
Which categories and products drive the most revenue?
What should we recommend to each customer based on historic behavior?

## Dataset:
Synthetic e-commerce transactions (~50K rows).
Columns: Transaction_ID, User_Name, Age, Country, Product_Category, Product_Name, Purchase_Amount, Payment_Method, Transaction_Date.

## Notes:
User_Name serves as a customer identifier for this dataset.
Product_Name aligns with Product_Category to enable product-level insights.

## Methodology:

1)Data Preparation
2)Data Cleaning & Preprocessing
3)Exploratory Data Analysis
2)Customer Aggregation:
  Computed per-customer totals (spend, transactions), per customer total transactions, most-purchased category (favorite).

3)Segmentation (Rule-Based)
  High-Value: top spenders based on a quantile threshold (e.g., top 10%).
  Frequent: above-average purchase frequency (e.g., above dataset mean).
## Final labels (mutually exclusive):
     Champion: high spend and high frequency
     Big Spender: high spend only
     Frequent Buyer: high frequency only
     Regular: neither condition met

4)Recommendations (Rule-Based)
  For each user, recommend the top 5 products within their favorite category.

## Business Outcomes:
  1)Clear identification of Champions and Big Spenders to prioritize with VIP offers.
  2)Targeted cross-sell strategies for Frequent Buyers based on favorite categories.
  3)Loyalty insights to design category-specific bundles and promotions.
  4)Cold-start recommendations for new or inactive users.

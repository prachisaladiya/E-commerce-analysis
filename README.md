# E-Commerce Customer Intelligence & Recommendation System
- Tech: Python · Pandas · Jupyter Notebook

## Project Objective : Analyze e-commerce transactions to:
- Understand customer behavior (spend & frequency).
- Segment customers into actionable groups.
- Generate simple, explainable product recommendations a business can use immediately.

## Key Questions

- Who are the most valuable and most frequent customers?
- Which categories and products drive the most revenue?
- What should we recommend to each customer based on historic behavior?

## Dataset

- Size: ~50K synthetic transactions
- Columns: Transaction_ID, User_Name, Age, Country, Product_Category, Product_Name, Purchase_Amount, Payment_Method, Transaction_Date

### Notes:

- User_Name serves as the customer identifier.
- Product_Name aligns with Product_Category to enable product-level insights.

## Methodology (High Level)

1) Data Preparation & Cleaning
- Parsed dates; standardized categorical fields; ensured numeric types.

2) Exploratory Data Analysis (EDA)
- Category/product leaders, monthly trends, repeat purchase behavior.

3) Customer Aggregation
- Per-customer totals: Total Spend, Total Transactions, Favorite Category.

4) Segmentation (Rule-Based)

- Champion = High spend & High frequency
- Big Spender = High spend only
- Frequent Buyer = High frequency only
- Regular = neither condition met

5) Recommendations (Rule-Based)

- For each user, recommend Top-5 products from their Favorite Category.
- Cold-start: overall/top-category best sellers.

## Business Outcomes

- Clear identification of Champions & Big Spenders → VIP offers & retention focus.
- Targeted cross-sell for Frequent Buyers using favorite categories.
- Loyalty insights to design category-specific bundles & promotions.
- Cold-start recommendations for new/inactive users.

# E-Commerce Customer Segmentation & Recommendation Analysis
## Project Overview: 
- This project analyzes transaction-level e-commerce data to understand customer behavior, identify high-value segments, and generate explainable product recommendations.
  Using Python (Pandas, NumPy) in Jupyter Notebook, it applies rule-based customer segmentation and recommendation logic, designed for easy understanding and deployment by business teams.

- Tech: Python · Pandas · NumPy · Jupyter Notebook
- Focus: Customer segmentation (rule-based), explainable product recommendations, and business insights for e-commerce teams.

## Project Objective:
-Analyze transaction-level e-commerce data to:
- Understand customer behavior, including spending patterns and purchase frequency.
- Segment customers into actionable groups that the marketing and sales teams can target.
- Generate simple, explainable product recommendations that can be deployed by the business immediately.

## Key Business Questions Answered

- Who are the most valuable and most frequent customers?
- Which categories and products drive the most revenue?
- What should we recommend to each customer based on their historic behavior?
- Who are the top 10 repeat customers?

#### Answering these enables targeted promotions, smarter bundling/cross-sell, and higher retention.

## Dataset (used in this project)

- Size: ~50,000 synthetic transactions
- Columns (required):
1. Transaction_ID — unique transaction identifier
2. User_Name — customer identifier (used in place of CustomerID)
3. Age — customer age (optional for demographic slicing)
4. Country — customer country (useful for regional analysis)
5. Product_Category — coarse product category (e.g., Electronics, Books)
6. Product_Name — specific product mapped to category
7. Purchase_Amount — numeric transaction value
8. Payment_Method — payment channel used
9. Transaction_Date — date of the transaction

### Notes:

- User_Name is used as the customer key in this dataset. If in real data names are not unique, a true customer id should be used.
- Product_Name is aligned to its Product_Category to allow both category-level and product-level analysis.

## Methodology (what was done)
1. Data Preparation & Cleaning
   - Parse and validate Transaction_Date as datetime.
   - Ensure numeric types for Purchase_Amount.
   - Remove or handle invalid records (duplicates, negative amounts).

2. Exploratory Data Analysis (EDA)
   - Identify top categories and top products by revenue and transaction count.
   - Analyze monthly/seasonal trends in revenue and order volume.
   - Evaluate payment method and country distributions.
   - Calculate repeat purchases and basic customer frequency statistics.

3. Customer Aggregation (per user): For each customer (User_Name), compute:
   - Total Spend — sum of Purchase_Amount.
   - Total Transactions — number of unique Transaction_IDs.
   - Favorite Category — most frequently purchased Product_Category (mode).
- These aggregates form the basis for segmentation and recommendations.

4. Segmentation (Rule-Based)
   - Create mutually exclusive segments using simple, explainable rules:
   - Champion — high spend and high frequency (example: spend in top 10% and transactions above dataset mean).
   - Big Spender — high spend only (top spenders but not frequent).
   - Frequent Buyer — high frequency only (buys often, average spend).
   - Regular — neither high spend nor high frequency.
- Thresholds (quantile for spend, mean or chosen cutoff for frequency) are configurable and should be set to reflect business goals.

5. Recommendations (Rule-Based)
    - For each user, recommend Top-N products (default N = 5) from the user’s Favorite Category.
    - Cold-start fallback: for new or inactive users, recommend overall top sellers or category trending products.
- Recommendations are explainable: “Recommend top products in user’s favorite category.”


## Business Outcomes & Actions
1) Prioritize Champions & Big Spenders.
   - Provide VIP offers, early access, and premium support to protect high revenue customers.

2) Target Frequent Buyers
   - Promote cross-sell offers and subscription/loyalty programs tailored to their favorite categories.

3) Design Category Bundles
   - Use favorite-category and co-purchase signals to create high-conversion bundles and “Frequently Bought Together” pairs.

4) Cold-Start Strategy
   - Apply global top-seller recommendations or category-based suggestions for new/inactive users.


## Configurable Parameters
   - High-Value threshold (spend): e.g., 90th percentile (top 10%).
   - Frequent threshold (transactions): e.g., mean or chosen numeric cutoff.
   - Top-N recommendations: default 5.
- Tune these parameters to match real business KPIs.

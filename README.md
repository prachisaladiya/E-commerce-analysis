E-Commerce Customer Intelligence & Recommendation System

Tech: Python, Pandas, NumPy, Jupyter Notebook
Focus: Customer segmentation, rule-based recommendations, business insights

📌 Project Objective

Analyze transaction data to:

Understand customer behavior

Segment users by value and frequency

Generate simple, explainable product recommendations that businesses can act on immediately

❓ Key Questions Answered

Who are our most valuable and most frequent customers?

Which categories and products drive the most revenue?

What should we recommend to each customer based on historic behavior?

📂 Dataset

Size: ~50K synthetic e-commerce transactions

Columns:

Transaction_ID

User_Name (serves as customer identifier)

Age

Country

Product_Category

Product_Name (aligned with Product_Category for product-level insights)

Purchase_Amount

Payment_Method

Transaction_Date

🛠️ Methodology

Data Preparation

Data Cleaning & Preprocessing

Exploratory Data Analysis

Customer Aggregation

Computed per-customer totals (spend, transactions)

Most-purchased category (favorite)

Segmentation (Rule-Based)

High-Value: Top spenders (top 10% quantile)

Frequent: Above-average purchase frequency (above dataset mean)

Final Labels (mutually exclusive):

Champion: High spend + high frequency

Big Spender: High spend only

Frequent Buyer: High frequency only

Regular: Neither condition met

Recommendations (Rule-Based)

For each user, recommend Top 5 products within their favorite category

📊 Business Outcomes

Clear identification of Champions and Big Spenders → prioritize with VIP offers

Targeted cross-sell strategies for Frequent Buyers based on favorite categories

Loyalty insights → design category-specific bundles and promotions

Cold-start recommendations for new or inactive users

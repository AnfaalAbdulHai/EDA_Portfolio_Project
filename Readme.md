# Customer & Sales Insights from Amazon Clothing Transactions  

## Project Overview  
This project performs **Exploratory Data Analysis (EDA)** on an **Amazon Clothing Sales dataset (2024–2025)** with 25,000+ records.  
The dataset includes customer demographics, order details, pricing, discounts, delivery times, payment methods, product categories, and return behavior.  

The goal is to:  
- Understand **sales performance** across categories, brands, and regions.  
- Explore **customer behavior** (ratings, returns, high-value vs one-time buyers).  
- Evaluate **pricing, discounts, and delivery impact** on satisfaction and returns.  
- Derive actionable **business insights** for product, marketing, and operations teams.  

---

## Dataset Description  
Each row represents a single order. Key fields include:  

- **order_id** → Unique order identifier  
- **customer_id** → Unique customer reference  
- **product_id, product_name, brand** → Product-level details  
- **main_category, sub_category** → Clothing categories (Men, Women, Kids, Baby, etc.)  
- **price, discount_percent, final_price** → Pricing and discounts  
- **payment_method** → Credit Card, PayPal, COD, Gift Card  
- **review_rating** → Customer rating (1–5)  
- **delivery_days** → Delivery time in days  
- **is_returned** → Whether the order was returned (1/0)  
- **region, customer_age_group, device_type** → Customer demographics and platform  

---

## Methodology  

1. **Data Cleaning & Preparation**  
   - Converted dates to datetime formats.  
   - Handled missing values (mean imputation for numeric, `"Unknown"` for categorical).  
   - Validated price/discount/final_price consistency.  
   - Engineered features:  
     - Delivery speed (fast/slow)  
     - Customer-level aggregates (spend, orders, rating, return rate)  
     - Monthly & weekly revenue trends  

2. **Univariate Analysis**  
   - Distribution of price, final_price, quantity, discount_percent, ratings, delivery_days.  
   - Frequency of categories, brands, payment methods, regions, devices.  

3. **Bivariate & Multivariate Analysis**  
   - Correlations (price vs quantity = **-0.58**, discount vs revenue = **-0.17**).  
   - Revenue trends (monthly peak: **March 2025**).  
   - Returns by category, brand, device, and age group.  
   - Average ratings by brand, category, and region.  
   - High-value vs one-time buyer segmentation.  
   - Average Order Value (AOV) by region and age group.  
   - Delivery days effect on review ratings and returns.  

4. **Visualization**  
   - Line plots (revenue trends, delivery effect).  
   - Boxplots, histograms, bar charts (distribution insights).  
   - Dual-axis plots (brand pricing vs return rate).  

---

## Key Findings  

- **Pricing & Discounts**  
  - Price and final_price distributions were initially inconsistent; corrected formula removed outliers.  
  - Discounts (avg. **12.5%**) had **no strong impact** on sales volume (correlation ≈ 0.00).  
  - Higher prices correlated with lower quantities sold (**-0.58**).  

- **Customer Behavior**  
  - Ratings are **stable across brands, categories, and regions (~3.7/5)**.  
  - Returns are **~10% overall**, with **no strong link to ratings** → customers sometimes return even highly rated items (e.g., sizing issues).  
  - **High-value customers (top 20%)** drive a disproportionate share of spend.  

- **Returns & Delivery**  
  - **Zara** has the **highest return rate**, while **Carter’s** the lowest.  
  - Return rates are almost equal across **categories, age groups, and devices**.  
  - Delivery averages ~5 days across regions. Longer deliveries (9 days) oddly had the **highest ratings**, while 5-day deliveries saw the **highest return rate**.  

- **Payment Behavior**  
  - **Gift Card** purchases had the **highest average spend (~$137)**.  
  - Other methods (Credit Card, PayPal, COD) showed nearly identical average spend (~$135).  

- **Revenue Trends**  
  - Revenue peaked in **March 2025** (seasonal surge).  
  - Weekly and monthly patterns show consistent fluctuations.  

---

## Business Insights  

1. **Returns are not driven by dissatisfaction** → focus on **fit, size guides, and logistics**.  
2. **Gift Card promotions** may encourage higher spending.  
3. **Zara’s high return rate** → review product fit/quality, improve descriptions.  
4. **High-value customers** (top 20%) should be targeted with loyalty rewards.  
5. **Delivery times** are consistent (~5 days), but optimizing logistics in Northeast regions may help.  

# Marketing Mix Modeling (MMM)
This repository stores data for a hypothetical company who is seeking to understand how each part of their marketing impacts customer behaviour, sales, and ROI.
# Problem Statement
Haven Home Living is a hypothetical home living company trying to understand which marketing channels truly drive sales. 
With budgets spread across digital (social, search, email) and traditional (radio, flyers, partnerships) platforms, it’s difficult to isolate which channels contribute most efficiently to revenue growth.
It wants to answer key business questions such as:
1. How much revenue does each marketing channel drive?
2. What is the optimal spend allocation across channels to maximize ROI?
3. How do external factors (holidays, pricing, promotions, and distribution) impact sales performance?
To address these, this project applies Marketing Mix Modeling (MMM) — a statistical approach that quantifies the impact of different marketing activities and external variables on sales outcomes.
# Approach
### Data Generation & Preparation
1. Created a synthetic but realistic dataset for Haven Home Living, modeled after a mid-sized retailer.
2. 6 months of daily data (January–June 2024) across multiple marketing and operational variables.
### Feature Engineering
1. Encoded holiday and event effects (e.g., Family Day, Easter, Mother’s Day).
2. Adjusted for product availability, price fluctuations, and promotion intensity.
### Modeling Techniques
To estimate the impact of marketing and operational factors on daily revenue, multiple modeling approaches were tested:
#### 1. Baseline Linear Regression
Provides interpretable coefficients to estimate elasticities (e.g., % change in sales per % change in spend).
#### 2. Regularized Regression (Ridge )
Handles multicollinearity between marketing channels and prevents overfitting.
#### 3. Tree-Based Models (XGBoost)
Captures non-linear effects and complex interactions (e.g., how spend effectiveness changes at high budgets).
#### 4. Adstock and Diminishing Returns Transformations
Preprocessing techniques to account for lag (carryover) and saturation (diminishing effect) of marketing activities.
Each model was trained and evaluated using a train/test split, and the final selection was based on both predictive accuracy and business interpretability.
### Insights & Visualization
1. Channel ROI comparison (revenue per $1 of spend).
2. Simulated optimal budget allocation scenarios.
3. Identified key seasonal uplift moments (e.g., Easter, Mother’s Day).
er $1 of spend).
# Data 
### Time Range
1. Period: 2024-01-01 → 2024-06-30 (6 months of daily data)
2. Granularity: Daily
3. Volume: ~30,000–35,000 rows.
### Product Categories
1. Cookware & Bakeware
2. Kitchen Appliances
3. Tabletop & Dining
4. Storage & Organization
5. Home Décor
6. Bedding & Bath
### Marketing Channels
1. Social
2. SEO (Natural Search)
3. SEM (Paid Search)
4. Display
5. Direct
6. Email
7. TV
8. Radio
9. Partnership / Affiliate
10. eFlyers
11. Referring Domain
### Target Segments & Audience Targeting
1. Target Customers: Home Enthusiasts, Professional Designers, DIY Decorators
2. Audience Targeting: Keywords, Broad, Interests, Retargeting

### Columns & Data Definitions

| Column              | Description                                   | Example                        |
|----------------------|-----------------------------------------------|--------------------------------|
| date                 | Calendar date (YYYY-MM-DD).                   | 2024-03-15                     |
| category             | Product category.                             | Kitchen Appliances              |
| channel              | Main marketing channel.                       | Social                         |
| ad_platform          | Platform or network within the channel.       | Pinterest                      |
| campaign_name        | Campaign identifier.                          | Spring Refresh 2024             |
| ad_name              | Specific ad creative name.                    | Pinterest – Air Fryer Carousel  |
| target_customer      | Audience segment.                             | Home Enthusiast                 |
| audience_targeting   | Targeting type.                               | Interests                      |
| price                | Average price for that category that day.     | 199.99                          |
| promotion_discount   | Fractional discount applied (0.10 = 10%).     | 0.15                            |
| distribution_index   | Product availability (0–1).                   | 0.90                            |
| holiday_flag         | 1 if date includes a retail holiday.          | 1                               |
| holiday_name         | Name of holiday (if any).                     | Mother’s Day                    |
| revenue              | Daily total revenue (CAD).                    | 25,000                          |
| sales_volume         | Total units sold.                             | 310                             |
| market_share         | Estimated market share (0–1).                 | 0.12                            |
| spend                | Daily ad spend (CAD).                         | 1,200                           |
| impressions          | Ads served that day.                          | 220,000                         |
| clicks               | Clicks generated.                             | 3,400                           |
| add_to_carts         | Add-to-cart actions.                          | 680                             |
| orders               | Completed orders.                             | 320                             |

### Results
#### Model Performance Summary
Our marketing mix model achieved an R² of 0.95, explaining 95% of daily revenue variation.

While linear and ridge regressions provided interpretable baselines, the XGBoost model delivered the best performance, reducing prediction error by 10% (RMSE 2,610 vs. 2,900).

| Model              | R²    | RMSE       | MAE        |
|-------------------|-------|-----------|-----------|
| Linear Regression  | 0.935 | 2,900.13  | 2,090.23  |
| Ridge Regression   | 0.933 | 2,926.86  | 2,079.70  |
| XGBoost            | 0.947 | 2,610.89  | 1,839.03  |

#### Marketing Channel Importance
Based on our XGBoost MMM model, Display ads contributed the largest share of incremental revenue (36%), followed by SEM (15%) and eFlyers (15%). 

Channels like Social, Email, and SEO contributed between 3–8%, while traditional channels such as Radio and TV contributed less than 3% each. 

This demonstrates the relative effectiveness of digital paid channels in driving short-term revenue for Haven Home Living. See ranking below

| Channel                | Importance | Percentage |
|------------------------|-----------|------------|
| Display                | 0.096790  | 36.48%     |
| SEM                    | 0.040212  | 15.16%     |
| eFlyers                | 0.039157  | 14.76%     |
| Partnership/Affiliate  | 0.024846  | 9.37%      |
| Social                 | 0.020590  | 7.76%      |
| Email                  | 0.010320  | 3.89%      |
| SEO                    | 0.008613  | 3.25%      |
| Referring Domain       | 0.007945  | 2.99%      |
| Direct                 | 0.007235  | 2.73%      |
| Radio                  | 0.006492  | 2.45%      |
| TV                     | 0.003108  | 1.17%      |

### Conclusion
1. Focus marketing dollars: Display, SEM, and eFlyers are top three — reallocating spend toward these may maximize revenue.

2. Optimization opportunities: Social, Email, and Affiliate could be tested for better targeting or messaging.

3. Budget justification: The percentages provide a clear quantitative justification for marketing spend allocation.

4. MMM insights: Stakeholders can now see relative ROI across channels rather than just raw spend or impressions.

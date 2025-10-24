# Marketing-mix-modeling-MMM-
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

## Columns & Data Definitions

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

AtliQ Mart’s Diwali & Sankranti Promotions
Overview
Welcome to the AtliQ Mart’s Diwali & Sankranti Promotions repository! This project features SQL scripts used to analyze the performance of promotional campaigns run by AtliQ Mart during Diwali 2023 and Sankranti 2024. Our goal is to gain insights into various aspects of these campaigns, including high-value discounted products, store distribution, campaign effectiveness, and product performance in terms of incremental sales and revenue.

Introduction
Promotional campaigns are vital in driving sales and attracting customers during festive periods. This project utilizes data analytics to assess the effectiveness of AtliQ Mart’s campaigns for Diwali 2023 and Sankranti 2024, providing insights that can enhance future marketing strategies and improve overall campaign performance.

Data Sources
The analysis is based on data from AtliQ Mart's internal databases, including:

fact_events: Data on promotional events.
dim_products: Product details.
dim_stores: Store locations.
sales_summary: Sales and campaign revenue summaries.
Project Overview
Data Analysis: Executed SQL queries to analyze promotional campaign data.
Business Requests: Addressed five core queries related to promotional performance.
Objective: Provide actionable insights to optimize future promotional strategies.
Business Requests
High-Value Products in 'BOGOF' Promotion

Objective: Identify high-value products featured in the 'BOGOF' (Buy One Get One Free) promotion.
Query:
sql
Copy code
SELECT
    DISTINCT p.product_name,
    f.base_price
FROM
    fact_events f
JOIN
    dim_products p ON f.product_code = p.product_code
WHERE
    f.promo_type = 'BOGOF' AND f.base_price > 500;
Store Presence Overview

Objective: Provide an overview of the number of stores in each city.
Query:
sql
Copy code
SELECT
    City,
    COUNT(store_id) AS Total_Stores
FROM
    dim_stores
GROUP BY
    City
ORDER BY
    Total_Stores DESC;
Promotional Campaign Revenue Analysis

Objective: Display total revenue generated before and after each promotional campaign.
Query:
sql
Copy code
SELECT
    campaign_name,
    CONCAT(ROUND(SUM(revenue_before) / 1000000, 2), 'M') AS Revenue_Before,
    CONCAT(ROUND(SUM(revenue) / 1000000, 2), 'M') AS Revenue_After
FROM
    sales_summary
GROUP BY
    campaign_name;
Incremental Sold Quantity Analysis during Diwali Campaign

Objective: Calculate Incremental Sold Quantity (ISU%) for each category during the Diwali campaign.
Query:
sql
Copy code
SELECT
    category,
    `ISU%`,
    RANK() OVER (ORDER BY `ISU%` DESC) AS Ranking
FROM
    (
        SELECT
            category,
            SUM(ISU) AS ISU,
            ROUND(SUM(ISU) / SUM(quantity_before_promo) * 100, 2) AS `ISU%`
        FROM
            sales_summary
        WHERE
            CAMPAIGN_NAME = "Diwali"
        GROUP BY 
            category
    ) AS subquery;
Top 5 Products by Incremental Revenue Percentage

Objective: Identify the top 5 products ranked by Incremental Revenue Percentage (IR%) across all campaigns.
Query:
sql
Copy code
SELECT
    product_name,
    category,
    ROUND(SUM(IR) / SUM(revenue_before) * 100, 2) AS `IR%`,
    RANK() OVER (ORDER BY SUM(IR) / SUM(revenue_before) * 100 DESC) AS ranking
FROM
    sales_summary
GROUP BY
    product_name, category
ORDER BY
    `IR%` DESC
LIMIT 5;
Limitations and Challenges
One notable limitation is related to the 'BOGOF' (Buy One Get One Free) promotion type, where the dataset may not accurately reflect the quantity of the free item. This limitation could impact the analysis, particularly when comparing 'BOGOF' promotions to other types.

Results and Insights
Identification of high-value products in 'BOGOF' promotions.
Overview of store distribution across cities.
Revenue analysis before and after each promotional campaign.
Incremental sales and revenue percentage during the Diwali campaign.
Top 5 products by incremental revenue percentage.
These insights can help AtliQ Mart refine future promotional strategies, optimize resource allocation, and enhance overall sales performance.

Conclusion
This analysis provides valuable insights into AtliQ Mart’s promotional campaigns during Diwali 2023 and Sankranti 2024. By applying these insights, AtliQ Mart can better tailor its marketing strategies to drive higher sales and attract more customers during festive seasons.

Additional Insights
Store Performance: Analysis of top and bottom-performing stores by incremental revenue and sold units.
Promotion Type: Evaluation of the effectiveness of different promotion types.
Product and Category: Insights into product performance and category responsiveness to promotions.
Visualizations
Explore the interactive Power BI dashboard for detailed visualizations:

View Power BI Dashboard
Future Work
Future enhancements could involve:

Exploring additional datasets for deeper customer insights.
Conducting more granular analysis by product category or region.
Implementing machine learning models for predictive analytics to forecast sales and optimize promotional strategies.

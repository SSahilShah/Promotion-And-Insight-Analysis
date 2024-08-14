# AtliQ Mart’s Diwali & Sankranti Promotions

## Overview

Welcome to the **AtliQ Mart’s Diwali & Sankranti Promotions** repository! This project contains SQL scripts used to analyze the performance of promotional campaigns run by AtliQ Mart during Diwali 2023 and Sankranti 2024. The analysis addresses various business requests related to identifying high-value discounted products, store distribution, campaign effectiveness, and product performance in terms of incremental sales and revenue.

## Introduction

Promotional campaigns are crucial for driving sales and attracting customers during festive periods. This project leverages data analytics to evaluate the effectiveness of AtliQ Mart’s campaigns for Diwali 2023 and Sankranti 2024. The insights gained will help in optimizing future marketing strategies and improving campaign performance.

## Data Sources

The analysis uses data from AtliQ Mart's internal databases:

- **`fact_events`**: Information about promotional events.
- **`dim_products`**: Details about products.
- **`dim_stores`**: Information on store locations.
- **`sales_summary`**: Data on sales and campaign revenues.

## Project Overview

- **Data Analysis**: SQL queries to analyze promotional campaign data.
- **Business Requests**: Five core queries addressing various aspects of promotional performance.
- **Objective**: Provide actionable insights to optimize future promotional strategies.

## Business Requests

### 1. High-Value Products in 'BOGOF' Promotion
**Objective**: Identify high-value products featured in the 'BOGOF' (Buy One Get One Free) promotion.

![image](https://github.com/user-attachments/assets/b26bc239-ab84-4cb3-8cef-747ac195206e)

### 2. Store Presence Overview
**Objective**: Provide an overview of the number of stores in each city.
![image](https://github.com/user-attachments/assets/73ba49fd-b270-4cc5-9a1c-295102686a36)

### 3. Promotional Campaign Revenue Analysis
**Objective**: Display total revenue generated before and after each promotional campaign.
![image](https://github.com/user-attachments/assets/f3e3b288-acc7-42e2-9d3a-096583d20a38)

### 4. Incremental Sold Quantity Analysis during Diwali Campaign
**Objective**: Calculate Incremental Sold Quantity (ISU%) for each category during the Diwali campaign.
![image](https://github.com/user-attachments/assets/c7d7e2c3-96f9-4cac-8965-3cecd1e2da52)

### 5. Top 5 Products by Incremental Revenue Percentage
**Objective**:Identify the top 5 products ranked by Incremental Revenue Percentage (IR%) across all campaigns.
![image](https://github.com/user-attachments/assets/cbb74b2e-a66b-4ed9-a992-1feefbebd15a)

## Limitations and Challenges

One significant limitation encountered during the analysis is related to the handling of promotions with the 'BOGOF' (Buy One Get One Free) promotion type. The dataset does not accurately account for the quantity of the free item provided as part of the promotion. This limitation may lead to some discrepancies or misunderstandings in the analysis, particularly when evaluating the effectiveness of 'BOGOF' promotions and comparing them with other promotion types.

## Results and Insights

The analysis revealed several key insights:

- **High-value products** featured in 'BOGOF' promotions.
- **Distribution of stores** across different cities.
- **Total revenue** generated before and after each promotional campaign.
- **Incremental sold quantity and revenue percentage** during the Diwali campaign.
- **Top 5 products** ranked by incremental revenue percentage.

These insights can help AtliQ Mart make informed decisions for future promotional activities, optimize resource allocation, and improve overall sales performance.

## Conclusion

Overall, the analysis provides valuable insights into the performance of promotional campaigns conducted by AtliQ Mart during Diwali 2023 and Sankranti 2024. By leveraging data analytics, AtliQ Mart can enhance its marketing strategies, attract more customers, and drive higher sales during festive seasons.

## Additional Insights

In addition to the main business requests, the following recommended insights were explored during the analysis:

### Store Performance Analysis
![Store performance analysis](https://github.com/user-attachments/assets/b19ec539-1161-4d8b-b061-2563e864fd13)


- **Top 10 Stores by Incremental Revenue (IR):** Identify the top-performing stores in terms of incremental revenue generated from promotions.
- **Bottom 10 Stores by Incremental Sold Units (ISU):** Identify the stores with the lowest performance in terms of incremental sold units during the promotional period.
- **City-wise Store Performance:** Analyze how store performance varies by city and identify any common characteristics among top-performing stores.

### Promotion Type Analysis
![promotion Type analysis](https://github.com/user-attachments/assets/8cff1134-61c8-443c-a2bc-ebffe14c1b06)

- **Top 2 Promotion Types by Incremental Revenue:** Determine the top-performing promotion types that resulted in the highest incremental revenue.
- **Bottom 2 Promotion Types by Incremental Sold Units:** Identify the least effective promotion types in terms of their impact on incremental sold units.
- **Comparison of Promotion Types:** Analyze the performance differences between discount-based promotions, BOGOF (Buy One Get One Free), and cashback promotions.
- **Optimal Promotion Type:** Determine which promotions strike the best balance between incremental sold units and maintaining healthy margins.

### Product and Category Analysis
![product and category analysis](https://github.com/user-attachments/assets/d0db826e-0069-4ddd-bc1a-ec84345570a1)

- **High-Lifting Product Categories:** Identify product categories that saw significant increases in sales from the promotions.
- **Product Responsiveness to Promotions:** Analyze specific products that respond exceptionally well or poorly to promotions.
- **Correlation between Product Category and Promotion Type Effectiveness:** Investigate the relationship between product categories and the effectiveness of different promotion types.

## Visualizations

Explore the live Power BI dashboard for interactive visualizations:

[View Power BI Dashboard](https://project.novypro.com/Ar80bX)

## Future Work

Future work could include:

- Exploring additional datasets to gain deeper insights into customer behavior and preferences.
- Conducting more granular analysis on specific product categories or regions.
- Implementing machine learning models for predictive analytics to forecast sales and optimize promotional strategies.





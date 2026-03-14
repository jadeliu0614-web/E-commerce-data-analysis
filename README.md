# E-commerce-data-analysis
## Project Overview
Based on Kaggle office supplies e-commerce data, sales and operations analysis is conducted from three perspectives: time, customer, and region, and extends to simple forecasting and customer operation recommendations. Technically, pandas is mainly used for cleaning and aggregation, and matplotlib/seaborn is used for visualization.
In terms of data preprocessing, only the necessary type conversion was made: Order Date and Ship Date were converted to dates, a df_raw was kept for basic cleaning, and each analysis module started with df_raw.copy() to avoid interfering with each other.
## Key Findings¶

Overall Sales Trends：
Monthly sales from 2015 to 2018 showed a fluctuating upward trend, with the overall level in the latter two years significantly higher than the former.
Each year had 1-2 distinct peaks, but these peaks did not completely overlap, suggesting they were driven by promotions or concentrated procurement rather than regular seasonality.

Customer Structure：
Among the three customer types, Consumers accounted for the largest share and formed the current revenue base; Corporate was next, while Home Offices had a smaller volume.
This indicates that the business is primarily driven by scattered orders, with room for improvement in large B2B clients, which can be achieved through targeted breakthroughs via pricing, framework agreements, etc.

Regional Distribution：
Sales volume varied significantly between different regions, with 1-2 regions contributing the majority of sales.
These regions are suitable as priority battlegrounds for market deployment and channel development, while other regions are more suitable for small-scale pilot programs and strategy validation.

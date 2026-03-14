# E-commerce-data-analysis
## Project Overview
Based on Kaggle office supplies e-commerce data, sales and operations analysis is conducted from three perspectives: time, customer, and region, and extends to simple forecasting and customer operation recommendations. Technically, pandas is mainly used for cleaning and aggregation, and matplotlib/seaborn is used for visualization.
In terms of data preprocessing, only the necessary type conversion was made: Order Date and Ship Date were converted to dates, a df_raw was kept for basic cleaning, and each analysis module started with df_raw.copy() to avoid interfering with each other.
## Key Findings

**Overall Sales Trends:**
Monthly sales from 2015 to 2018 showed a fluctuating upward trend, with the overall level in the latter two years significantly higher than the former.
Each year had 1-2 distinct peaks, but these peaks did not completely overlap, suggesting they were driven by promotions or concentrated procurement rather than regular seasonality.

**Customer Structure：**
Among the three customer types, Consumers accounted for the largest share and formed the current revenue base; Corporate was next, while Home Offices had a smaller volume.
This indicates that the business is primarily driven by scattered orders, with room for improvement in large B2B clients, which can be achieved through targeted breakthroughs via pricing, framework agreements, etc.

Regional Distribution：
Sales volume varied significantly between different regions, with 1-2 regions contributing the majority of sales.
These regions are suitable as priority battlegrounds for market deployment and channel development, while other regions are more suitable for small-scale pilot programs and strategy validation.
## Time Series Forecasting and Customer Operations

Simple Monthly Sales Forecasting：
After aggregating orders by month, an ADF test was performed on the monthly sales figures. The original series showed a clear trend, which became closer to stationary after first differencing.
Based on this, a simple ARIMA(1,1,1) model was used to perform a one-period (monthly) forecast. The results mainly serve as a "reference baseline," suitable for rough judgments in short-term budgeting and manpower scheduling.
Due to the limited data length (approximately 4 years), I will use this model as a reference signal for decision-making in practical scenarios, rather than the sole basis.

RMF Customer Segmentation：
Recency / Frequency / Monetary are calculated at the Customer ID level, and scores are generated using quantiles to synthesize the RFM_Score.
High-scoring customers tend to have recent purchases, high order frequency, and high cumulative spending, making them "key value customers," suitable for differentiated services and targeted marketing.
Customers with good spending but high recency are in a "high-risk" stage and can be re-engaged using coupons or exclusive activities.

Association Rules (Shopping Basket Analysis)：
Using Order ID as the shopping basket, we performed simple association rule mining at the Category level.
This revealed some intuitive co-purchase relationships (such as the combination of technology and office supplies), which can provide a basis for "You May Also Like," bundled sales, or shelf placement.
## Implementation Recommendations

Targeting: Prioritize high-sales regions and peak months based on monthly trends. For Consumers, leverage major promotions and featured placements to increase average order value and repeat purchases. For Corporate/Home Offices, experiment with more refined Key Account (KA) operations.

Inventory: Increase safety stock in advance for peak months and high-value categories (e.g., technology, some furniture). Shorten replenishment cycles for categories with high volatility. For regions with slow shipping but high sales, evaluate forward warehouses or logistics solutions.

Service/Customer Operations: Based on RFM segmentation, provide more timely after-sales service and targeted discounts to high-scoring customers. Implement repurchase actions for customers at risk of churn. Incorporate association rules to add simple "bundle recommendations" to the order process, aiming to include one or two related items in each order.

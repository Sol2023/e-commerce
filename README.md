# E-Commerce Project Overview

## Overview
E-commerce is the activity of buying or selling products on online services or over the Internet. The e-commerce market has changed the way business is transacted, whether in retail or business-to-business, locally or globally.

The dataset of this project is from an online store, which includes product information and customer transaction records from 2016 to 2018. **The ultimate goal of the company is to improve sales.** In this project, you’re supposed to find out the **online shopping behaviors** of the customers and make marketing suggestions for the store in order to increase the **customers’ lifetime value** to the company.

## Dataset
The dataset has 7 tables, which include customer transaction information for each order and the product information:
- onlineshop_customers.sql
- onlineshop_orders_items.sql: one order can contain more than one item.
- onlineshop_orders.sql: ‘fulfilled’ indicates the order was completed.
- onlineshop_products_sku.sql: ‘sku’ represents stock keeping unit, which is used to track inventory in the store.
- onlineshop_products.sql
- onlineshop_traffic.sql: page_views: each time a user visits a web page, it is called a page view; sessions: a session is a group of user interactions with your website that take place within a given time frame; avg_session_in_s: average seconds in one session.
- onlineshop_transactions.sql: status success indicates the transaction was completed.

## Task
The objective of this E-commerce project is to test your SQL skills as well as data analytics skills.

1. Firstly, because the dataset is in SQL format, you need to load the dataset into the database. For future analysis, you can either convert the dataset to CSV format, or connect to the database directly in Python/R.
2. Secondly, please clean the dataset if it contains wrong records, then explore the dataset to answer the following questions:
    1. How’s the trend of website traffic and the number of orders over time? Is there any correlation between the orders and the website traffic?
    2. How’s the sales from the different products over the seasons or months? What are the popular products? Is there any correlation between different products?
    3. How’s the sales of different products with discount? Does the discount promote sales?
    4. Dig more into the data and gain more insights, you can choose some E-commerce metrics or analysis (e.g. churn rate, conversion rate, retention rate, RFM analysis). Based on the insights from all above questions, do you have any suggestion for the growth of sales?

## Main Findings

1. **Sales Trend**

<p align="center">

![07_sales_trend](https://github.gatech.edu/storage/user/75133/files/b862d956-50df-4359-a9f1-6b646e855d36)

</p>

- The sale is highest at the first month 2016-08.
- At the second month, the sale droped sharply.
- After the second month, the sales went smoothly and fluctuated with the seasons and holidays.

2. **Sales funnel**

<p align="center">
    
![03_sales_funnel](https://github.gatech.edu/storage/user/75133/files/3997b09a-df03-4214-a8e7-03b91520ed9d)

</p>

**The overall conversion rate from page_views to final placed_orders is only 0.19%:**

- The conversion rate from page_views to product_detail_views is 26.7%.
- The conversion rate from product_detail_view to product_adds_to_carts is 10.1%, which is the lowest.
- The conversion rate from product_adds_to_carts to product_checkouts is 29.2%.
- The conversion rate from product_checkouts to final placed_orders is 24.7%.

3. **Correlation between Traffic and Order**

<p align="center">

![04_cor_between_traffic_and_order](https://github.gatech.edu/storage/user/75133/files/7f456711-1b95-4497-a37c-85d355247332)

</p>

- The result shows a strong positive correlation between page_views, and the number of orders, coefficient is 0.82.
- Also, there is a strong positive correlation between sessions, product_detail_views and the number of orders.
- Therefore, we conclude that the website traffic has a significant correlation to the number of orders.

4. **Order trend and page views**

<p align="center">
    
![06_orders_and_page-view_trend](https://github.gatech.edu/storage/user/75133/files/7d868bb8-9540-4863-9cc7-e364c90e2a17)

</p>

- From the plot, we can see the trend of the number of orders is highly related to the page views.
- From August 2016 to March 2018, the traffic and the number of orders are decreasing in the long term.
- The trend of orders and traffic fluctuated with seasons and holidays. For example, there is a peak during the Thanksgiving holidays. The traffic and orders are higher during the August than January.

5. **Correlation between Promotion and Orders**

<p align="center">
    
![08_correlation_between_promotion_and_orders](https://github.gatech.edu/storage/user/75133/files/c725fb92-dffa-4ad2-a1a5-79947c1a54ab)

</p>

- The correlation coefficient of discount_percentage and discount_quantity is 0.75.
- The correlation coefficient of discount_percentage and discount_orders is 0.82.
- We can conclude that discount does promote sales.

6. **Churn Rate**

<p align="center">
    
![09_churn_rate](https://github.gatech.edu/storage/user/75133/files/b154248e-3a99-437f-bfda-7e6845d6a8fb)

</p>

- The number of unique customers is decreasing overally.

7. **Retention Rate**

<p align="center">
    
![10_retention_rate](https://github.gatech.edu/storage/user/75133/files/1cc0aaf4-00aa-49cc-a241-5ac17dbd9f46)

</p>

- In the cohort period 2, the retentin rate is less than 10%. After the first purchase, we can see that over 90% customers will not purchase again in the second month. It is not good for this online store if the store seeks for sustainable growth, we should focus on the old customers.

8. **RFM Analysis**

Summary of the clusters and marketing strategy based on RFM analysis

- In order to improve the retention rate, we need to get a better understanding of the old customers.
- Instead of analyzing the entire customer base as a whole, it’s better to segment them into homogeneous groups, understand the traits of each group, and engage them with relevant campaigns rather than segmenting on just customer age or geography.
- One of the most popular, easy-to-use, and effective segmentation methods to enable marketers to analyze customer behavior is RFM analysis.

<p align="center">
    
![image](https://github.com/Sol2023/e-commerce/assets/92194263/ee2e5d45-9dcf-41e8-bb25-4a519af130e6)

</p>

*Cluster 1**

- Champions This group of customers are the best customers, who bought most recently, most often, and are heavy spenders.
- Reward these customers. They can become early adopters for new products and will help promote the brand.

*Cluster 2**

- New Customers This group of customers who have a high overall recency score but are not frequent shoppers.
- Start building relationships with these customers by providing onboarding support and special offers to increase their visits.

*Cluster 3**

- Potential Loyalists This group of customers with average frequency and who spent a good amount.
- Offer membership or loyalty programs or recommend related products to upsell them and help them become your Loyalists or Champions.

*Cluster 4**

- At Risk Customers This group of customers who spent big amounts, but haven’t purchased recently.
- Send them personalized reactivation campaigns to reconnect, and offer renewals and helpful products to encourage another purchase.

*Cluster 0**

- Require Activation Poorest performers of our RFM model. They might have went with our competitors for now and will require a different activation strategy to win them back.
- Bring them back with relevant promotions, and run surveys to find out what went wrong and avoid losing them to a competitor.

## Suggestions for sales

1. **Improve website conversion rates**

*The overall conversion rate from page_views to final placed_orders is only 0.19%:*
- The funnel shows the conversion from page_views to product_detail_views is 26.7%. 
- The conversion rate from product_detail_view to product_adds_to_carts is 10.1%, which is the lowest. No fatal problems but still space for improvement.
- The conversion rate from product_adds_to_carts to product_checkouts is 29.2%.
- The conversion rate from product_checkouts to final placed_orders is 24.7%.

*Improve product detail page*

Because the conversion from product_detail_view to product_adds_to_carts is low. We need to improve product detail page.
- Informative product page would ease decision-making. Check if there are enough images fully display the product, do the images look real, is the description specific and concrete
- Personalized and non-personalized recommendation system. User can shop the suits, compare similar items, or browse other items if this one doesn't fit. Non-personalized recommendations can be provided based on the association rules discovered, popular items and highly-reated items. Personalized recommender can be built with algorithms like collaborative filtering.

*Recover abandoned cart*

- Check and remove possible frictions that prevent checkout, e.g., do they hide shipping and tax until the last step, is the checkout process too complex, are there enough payment options etc.
- It's common people use cart as favorite list, they add items but are just watching with low purchasing intent. Incentivize them to make the purchase by ad retargeting (remarketing the items to the user on different platforms), or sending a follow-up email with time-limited coupon.


2. **Promote popular products at certain seasons and improve recommendation system**

*Improve the variety of popular products at certain seasons*

From the sales trend analysis, we find that the sales revenue and quantity of different product type fluctuated seasonly.

- The Top product is the best seller in terms of quantity. The quantity is higher in summer and autumn, and lower in the winter.  To help the sales growth, we can increase the variety of Top product, have more promotions  for this type of product in summer and autumn.

- The quantity of Dress is highest in summer, especially in June. We should increase the variety of Dress, have more promotion and recommendation for this type of product in summer.

- The quantity of Sweater is highest in autumn. In order to improve the sales, we should increase the variety of Sweater in autumn.

*Improve the recommendation system*

From the product bucket analysis, we can see some products were oftenly bought together by the customers. To achieve the sales growth, we should improve the algorithms of recommendation system. Recommend the items to customers that could potentially bought together.


3. **Offer discount at larger rate**

- From the previous analysis, we observe that the correlation coefficient of discount_percentage and discount_quantity is 0.75. The correlation coefficient of discount_percentage and discount_orders is 0.82. 
- We can say that discount does promote sales. In order to increase the sales revenue and quantity, we can offer discount at larger rate.

*Offer more discount at holidays*

We also observe that the sales is high at holidays, especially during Thanksgiving. To boost the sales, we can have more promotions at holidays.

4. **Build loyalty**

The overall sales is decreasing. Customer retention rate is low. After the first purchase, over 90% customers will not purchase again in the second month. Over 80% users made only one purchase.

- Launch or improve current loyalty program.
- Do customer satisfaction research and improve customer experience. e.g., Do customer find what they need/like? Are they satisfied with the product/service? Does the company capture the latest fashion trends?
- see the marketing strategy which provided at the send of RFM analysis (Part 7).

5. **Create awareness and interests**

The pricing, user size and sales volume suggest the company is probably a fast fashion startup. Given that web traffic has significant impact on sales, it would be good for them to focus on creating awareness by boosting traffic.
Possible solutions:

- Collaborate with designers to provide exclusive editions
- Collaborate with influencers/carry out social media campaigns
- Ads

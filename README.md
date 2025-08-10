# DSA-PROJECT_KMS-CASE-STUDY

## PROJECT OVERVIEW
THIS PROJECT IS AN ANALYSIS OF ACTIVITIES AT A LARGE CORPORATE THAT DEALS IN SUPPLY OF FURNITURE AND FITTINGS WITH HEAD QUARTERS IN LAGOS I.E KMS STORES

### DATA SOURCE:
CARGO.COM, EXCEL, CSV FILES

### TOOLS USED:
MICROSOFT EXCEL FOR DATE CLEANING  [Donwload here(https://microsoft-excel.en.softonic.com/download)]
SQL SERVER MANAGEMENT STUDIO FOR DATA ANALYSIS[DOWNLOAD HERE (https://learn.microsoft.com/en-us/ssms/sql-server-management-studio-ssms)]
### EXPLORATORY DATA ANALYSIS
- USING THE SQL MANAGEMENT STUDIO TO ANALYSE DATA 

************KMS QUERY************


SELECT * FROM [KMS SQL CASE STUDY]

1)****PRODUCT CATEGORY WITH HIGHEST SALES****

SELECT TOP 1 * FROM (
          SELECT ROW_ID, ORDER_ID, PRODUCT_CATEGORY, SALES, PROVINCE, REGION,CUSTOMER_SEGMENT FROM [KMS Sql Case Study]) AS KMS
		  ORDER BY SALES DESC
#### ANSWER: The product category with the highest sale at KMS for the period under consideration are technology products.
******TOP 3 REGIONS IN TERMS OF SALES****

SELECT TOP 3 * FROM (
          SELECT ROW_ID, ORDER_ID, PRODUCT_CATEGORY, SALES, PROVINCE, REGION,CUSTOMER_SEGMENT FROM [KMS Sql Case Study]) AS KMS
		  ORDER BY SALES DESC
#### ANSWER: The top 3 regions in terms of sales are Atlantic, Quebec and Prarie.
2)******BOTTOM 3 IN TERMS OF SALES**********

SELECT TOP 3 * FROM (
          SELECT ROW_ID, ORDER_ID, PRODUCT_CATEGORY, SALES, PROVINCE, REGION,CUSTOMER_SEGMENT FROM [KMS Sql Case Study]) AS KMS
		  ORDER BY SALES ASC
#### ANSWER: The last 3 regions in terms of sales are West and Yukon.
3)******TOTAL SALES OF APPLIANCES IN ONTARIO*****

SELECT PROVINCE, sum(SALES) AS TOTALSALES 
FROM 
[KMS Sql Case Study]
where 
province= 'ontario'
group by province

#### ANSWER: The total sales of appliances in Ontario is 3,063,212.47638369
4)******************TO INCREASE REVENUE FROM BOTTOM 10****************

SELECT TOP 10 * FROM (
          SELECT ROW_ID, ORDER_ID, PRODUCT_CATEGORY, SALES, SHIP_MODE, SHIPPING_COST, DISCOUNT, UNIT_PRICE, PROFIT, PROVINCE,Customer_Name, REGION,CUSTOMER_SEGMENT FROM [KMS Sql Case Study]) AS KMS
		  ORDER BY PROFIT ASC
#### ANSWER: To increase the revenue from bottom 10 customers KMS can run promo that will be tied to customers buying more to benefit good incentive.


5)********SHIPPING METHODS WITH HIGHEST SHIPPING COST**********

SELECT TOP 1 * FROM (
          SELECT ROW_ID, ORDER_ID, PRODUCT_CATEGORY, SALES, PROVINCE,Customer_Name, REGION, SHIP_MODE, Shipping_Cost FROM [KMS Sql Case Study]) AS KMS
		  ORDER BY Shipping_Cost DESC

#### ANSWER: DELIVERY TRUCK HAS THE HIGHEST SHIPPING COST


6) ***********THE MOST VALUABLE CUSTOMERS AND THE PRODUCTS THEY USE*************

SELECT TOP 10 * FROM (
          SELECT ROW_ID, ORDER_ID, PRODUCT_CATEGORY, SALES, SHIP_MODE, SHIPPING_COST, DISCOUNT, UNIT_PRICE, PROFIT, PROVINCE,Customer_Name, REGION,CUSTOMER_SEGMENT FROM [KMS Sql Case Study]) AS KMS
		  ORDER BY PROFIT DESC
#### ANSWER: The 10 most valuable customers are: Emily Phan, Andy Reiter, Deborah Brumfield, Karen Carlisle, Rick Wilson, Raymond Book, Logan Haushalter, Nick Crebassa, John Stevenson and Grant Carroll. The top 8 subscribe to Technology based products.

7) ************THE SMALL BUSINESS CUSTOMER WITH THE HIGHEST SALES*************************

SELECT customer_name, customer_segment, (SALES) AS sumSALES FROM [KMS Sql Case Study]

ORDER BY sumSALES desc

#### ANSWER: THE SMALL BUSINESS CUSTOMER WITH HIGHEST SALES IS Dennis Kane.

8)*************CORPORATE CUSTOMER THAT PLACED MOST NUMBER OF ORDER***********

SELECT CUSTOMER_NAME, CUSTOMER_SEGMENT, SALES, ORDER_DATE, ORDER_QUANTITY FROM [KMS Sql Case Study]
WHERE Customer_Segment= 'CORPORATE'
ORDER BY Order_Quantity DESC
#### ANSWER: 69 corporate customers placed most number of orders.

9)************MOST PROFITABLE CONSUMER CUSTOMER***********
SELECT CUSTOMER_NAME, CUSTOMER_SEGMENT, SALES, PROFIT, ORDER_QUANTITY FROM [KMS Sql Case Study]
WHERE Customer_Segment= 'CONSUMER'
ORDER BY PROFIT DESC

#### ANSWER: THE MOST PROFITABLE CONSUMER CUSTOMER IS EMILY PHAN

10) *************CUSTOMERS THAT RETURNED ITEMS AND SEGMENT*******************
SELECT [KMS Sql Case Study].Order_ID, [KMS Sql Case Study].Customer_Name, [KMS Sql Case Study].Customer_Segment , Order_Status.Order_ID, Order_Status.STATUS

FROM [KMS Sql Case Study]
JOIN Order_Status ON [KMS Sql Case Study].Order_ID= Order_Status.Order_ID

ORDER BY Customer_Segment
 
 #### ANSWER: 872 CUSTOMERS RETURNED ITEMS- 147 CONSUMER CUSTOMERS, 334 CORPORATE CUSTOMERS, 201 HOME OFFICE CUSTOMERS, 190 SMALL BUSINESS CUSTOMERS RETURNED ITEMS.

11) ***************
 

### RESULTS AND FINDINGS
1. The product category with the highest sale at KMS for the period under consideration are technology products.
2. The top 3 regions in terms of sales are Atlantic, Quebec and Prarie.
3. The last 3 regions in terms of sales are West and Yukon.
4. The total sales of appliances in Ontario is 3,063,212.47638369
5. To increase the revenue from bottom 10 customers KMS can run promo that will be tied to customers buying more to benefit good incentive.
6. DELIVERY TRUCK HAS THE HIGHEST SHIPPING COST.
7. The 10 most valuable customers are: Emily Phan, Andy Reiter, Deborah Brumfield, Karen Carlisle, Rick Wilson, Raymond Book, Logan Haushalter, Nick Crebassa, John Stevenson and Grant Carroll. The top 8 subscribe to Technology based products.
8. THE SMALL BUSINESS CUSTOMER WITH HIGHEST SALES IS Dennis Kane.
9. 69 corporate customers placed most number of orders.
10. THE MOST PROFITABLE CONSUMER IS EMILY PHAN
11. 872 CUSTOMERS RETURNED ITEMS- 147 CONSUMER CUSTOMERS, 334 CORPORATE CUSTOMERS, 201 HOME OFFICE CUSTOMERS, 190 SMALL BUSINESS CUSTOMERS RETURNED ITEMS.

### RECOMMENDATION
- There is a high demand for technology based products. The company should channel more of her production energy to tech based products to meet market demand and maximise profit.
- A market survey should be done at regions like west and Yukon to understand the customers needs in the region so as to know the products that can best suit them.
- The top 8 most profitable customers buy technology based items.
- The company should have a separate and more responsive dest to give priority to the corporate customer as they make most number of orders.
- The company should take feedbacks from the customers that returned items to know how to improve on their products as 10.1% return rate is much for the company's reputation.

Thank you



